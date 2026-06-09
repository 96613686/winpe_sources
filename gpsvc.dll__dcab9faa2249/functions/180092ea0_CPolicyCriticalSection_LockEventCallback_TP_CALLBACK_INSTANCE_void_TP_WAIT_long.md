# CPolicyCriticalSection::LockEventCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180092ea0`
- end: `0x18009322c`
- name: `?LockEventCallback@CPolicyCriticalSection@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `908`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x180007b38`
- `0x18000bbe0`
- `0x18004b498`
- `0x180052c7c`
- `0x180075530`
- `0x180075ec0`
- `0x18007d6f0`
- `0x180092ea0`
- `0x180093428`
- `0x1800935d0`
- `0x1800b4188`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180092fd2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180092fd2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800930e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800930f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800930e1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800930f2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800931dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800931e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800931dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800931e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800931fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800931fc`

## string_xrefs

- `0x180092f42`: `CreatePolicySectionContext failed with 0x%x`
- `0x180092f74`: `CreatePolicySectionContext failed with 0x%x`
- `0x180093089`: `AddReaderToList failed with 0x%x`
- `0x1800930b1`: `AddReaderToList failed with 0x%x`

## pseudocode

```c
void __fastcall CPolicyCriticalSection::LockEventCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  unsigned __int16 *v5; // rdx
  bool v8; // zf
  PTP_WAIT *v9; // rdi
  unsigned int v10; // esi
  char IsEnabled; // al
  _DWORD *v12; // rbp
  unsigned __int16 *v13; // rcx
  struct _TP_WAIT *v14; // rcx
  void *v15; // rcx
  __int64 v16; // [rsp+28h] [rbp-40h]
  HLOCAL hMem; // [rsp+78h] [rbp+10h] BYREF

  if ( Context )
  {
    v5 = (unsigned __int16 *)*Context;
    hMem = 0;
    if ( CPolicyCriticalSection::RemoveWaitingRpcReaderFromList(
           (CPolicyCriticalSection *)Context[6],
           (struct _RPC_ASYNC_STATE *)v5) )
    {
      v8 = WaitResult == 0;
      v9 = (PTP_WAIT *)(Context + 2);
      if ( v8 && Wait == *v9 )
      {
        v10 = CPolicyCriticalSection::CreatePolicySectionContext(
                (const unsigned __int16 *)Context[1],
                *((_DWORD *)Context + 8),
                Context[5],
                0,
                0,
                &hMem);
        if ( v10 )
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"CreatePolicySectionContext failed with 0x%x", v10);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"CreatePolicySectionContext failed with 0x%x", v10);
            }
          }
        }
        else
        {
          IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::GetImpl'::`2'::impl);
          v12 = hMem;
          if ( IsEnabled )
          {
            if ( hMem )
            {
              if ( (Context[4] & 0x20000000) != 0 )
              {
                *((_DWORD *)hMem + 12) = *((_DWORD *)Context + 18);
                _o_wcsncpy_s(v12 + 13, 260, (char *)Context + 76, 260);
                v12[143] = *((_DWORD *)Context + 149);
                *((_QWORD *)v12 + 4) = Context[8];
                if ( *(_DWORD *)&g_dwDebugLevel )
                {
                  if ( g_lpDebugMsg )
                  {
                    LODWORD(v16) = v12[143];
                    g_lpDebugMsg(
                      4u,
                      L"LockEventCallback: Propagated async caller info to context %p: PID=0x%x, Process=%ls, SessionId=%u",
                      v12,
                      (unsigned int)v12[12],
                      v12 + 13,
                      v16);
                  }
                  else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                  {
                    LODWORD(v16) = v12[143];
                    RedirectDebugMsg(
                      4u,
                      L"LockEventCallback: Propagated async caller info to context %p: PID=0x%x, Process=%ls, SessionId=%u",
                      v12,
                      (unsigned int)v12[12],
                      v12 + 13,
                      v16);
                  }
                }
              }
            }
          }
          v10 = CPolicyCriticalSection::AddReaderToList(
                  (CPolicyCriticalSection *)Context[6],
                  (struct _POLICY_SECTION_CONTEXT *)v12);
          if ( v10 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"AddReaderToList failed with 0x%x", v10);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"AddReaderToList failed with 0x%x", v10);
              }
            }
            CPolicyCriticalSection::DeletePolicySectionContext(v12);
          }
        }
      }
      else
      {
        v10 = 1460;
      }
      if ( Wait == *v9 )
        WaitForThreadpoolWaitCallbacks((PTP_WAIT)Context[3], 1);
      if ( Wait == (PTP_WAIT)Context[3] )
        WaitForThreadpoolWaitCallbacks(*v9, 1);
      v13 = (unsigned __int16 *)*Context;
      if ( v10 )
      {
        Server_LockAbortCall((struct _RPC_ASYNC_STATE *)v13, v10);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Lock timeout for 0x%p with error 0x%x", *Context, v10);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Lock timeout for 0x%p with error 0x%x", *Context, v10);
          }
        }
        CRWLock::CancelLock(*(CRWLock **)Context[6], (struct _RWLOCK_CONTEXT **)Context + 5);
        _InterlockedDecrement((volatile signed __int32 *)(Context[6] + 8LL));
      }
      else
      {
        Server_LockCompleteCall((PRPC_ASYNC_STATE)v13, (struct _POLICY_SECTION_CONTEXT **)&hMem);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Lock taken successfully for 0x%p", *Context);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Lock taken successfully for 0x%p", *Context);
          }
        }
      }
      CloseThreadpoolWait(*v9);
      v14 = (struct _TP_WAIT *)Context[3];
      *v9 = 0;
      CloseThreadpoolWait(v14);
      v15 = (void *)Context[7];
      Context[3] = 0;
      if ( v15 )
      {
        CloseHandle(v15);
        Context[7] = 0;
      }
      operator delete(Context);
    }
  }
}

```

## disassembly

```asm
0x180092ea0  test    rdx, rdx
0x180092ea3  jz      locret_18009322B
0x180092ea9  mov     [rsp+arg_0], rbx
0x180092eae  mov     [rsp+arg_10], rbp
0x180092eb3  push    rsi
0x180092eb4  push    rdi
0x180092eb5  push    r12
0x180092eb7  push    r14
0x180092eb9  push    r15
0x180092ebb  sub     rsp, 40h
0x180092ebf  mov     rbx, rdx
0x180092ec2  xor     r15d, r15d
0x180092ec5  mov     rdx, [rdx]; struct _RPC_ASYNC_STATE *
0x180092ec8  mov     edi, r9d
0x180092ecb  mov     r14, r8
0x180092ece  mov     [rsp+68h+hMem], r15
0x180092ed3  mov     rcx, [rbx+30h]; this
0x180092ed7  call    ?RemoveWaitingRpcReaderFromList@CPolicyCriticalSection@@AEAAPEAVCLockCallbackContext@1@PEAU_RPC_ASYNC_STATE@@@Z; CPolicyCriticalSection::RemoveWaitingRpcReaderFromList(_RPC_ASYNC_STATE *)
0x180092edc  test    rax, rax
0x180092edf  jz      loc_180093213
0x180092ee5  test    edi, edi
0x180092ee7  lea     r12d, [r15+4]
0x180092eeb  lea     rdi, [rbx+10h]
0x180092eef  jnz     loc_1800930CC
0x180092ef5  cmp     r14, [rdi]
0x180092ef8  jnz     loc_1800930CC
0x180092efe  mov     r8, [rbx+28h]
0x180092f02  lea     rax, [rsp+68h+hMem]
0x180092f07  mov     edx, [rbx+20h]
0x180092f0a  xor     r9d, r9d
0x180092f0d  mov     rcx, [rbx+8]
0x180092f11  mov     [rsp+68h+var_40], rax
0x180092f16  mov     dword ptr [rsp+68h+var_48], r15d
0x180092f1b  call    ?CreatePolicySectionContext@CPolicyCriticalSection@@CAKPEBGKPEAU_RWLOCK_CONTEXT@@HW4LockType@@PEAPEAU_POLICY_SECTION_CONTEXT@@@Z; CPolicyCriticalSection::CreatePolicySectionContext(ushort const *,ulong,_RWLOCK_CONTEXT *,int,LockType,_POLICY_SECTION_CONTEXT * *)
0x180092f20  mov     esi, eax
0x180092f22  test    eax, eax
0x180092f24  jz      short loc_180092F8A
0x180092f26  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180092f2d  jz      loc_1800930D1
0x180092f33  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180092f3a  test    rax, rax
0x180092f3d  jz      short loc_180092F57
0x180092f3f  mov     r8d, esi
0x180092f42  lea     rdx, aCreatepolicyse_1; "CreatePolicySectionContext failed with "...
0x180092f49  lea     ecx, [r15+2]
0x180092f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092f52  jmp     loc_1800930D1
0x180092f57  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180092f5e  jz      loc_1800930D1
0x180092f64  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180092f6b  jz      loc_1800930D1
0x180092f71  mov     r8d, esi
0x180092f74  lea     rdx, aCreatepolicyse_1; "CreatePolicySectionContext failed with "...
0x180092f7b  mov     ecx, 2; unsigned int
0x180092f80  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180092f85  jmp     loc_1800930D1
0x180092f8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement> `wil::Feature<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::GetImpl(void)'::`2'::impl
0x180092f91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_GPLockTracingEnhancement>::__private_IsEnabled(void)
0x180092f96  mov     rbp, [rsp+68h+hMem]
0x180092f9b  test    al, al
0x180092f9d  jz      loc_18009305F
0x180092fa3  test    rbp, rbp
0x180092fa6  jz      loc_18009305F
0x180092fac  test    dword ptr [rbx+20h], 20000000h
0x180092fb3  jz      loc_18009305F
0x180092fb9  mov     eax, [rbx+48h]
0x180092fbc  lea     rsi, [rbp+34h]
0x180092fc0  mov     edx, 104h
0x180092fc5  mov     [rbp+30h], eax
0x180092fc8  mov     r9d, edx
0x180092fcb  lea     r8, [rbx+4Ch]
0x180092fcf  mov     rcx, rsi
0x180092fd2  call    cs:__imp__o_wcsncpy_s
0x180092fd8  mov     eax, [rbx+254h]
0x180092fde  mov     [rbp+23Ch], eax
0x180092fe4  mov     rax, [rbx+40h]
0x180092fe8  mov     [rbp+20h], rax
0x180092fec  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180092ff3  jz      short loc_18009305F
0x180092ff5  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180092ffc  test    rax, rax
0x180092fff  jz      short loc_180093028
0x180093001  mov     ecx, [rbp+23Ch]
0x180093007  lea     rdx, aLockeventcallb; "LockEventCallback: Propagated async cal"...
0x18009300e  mov     r9d, [rbp+30h]
0x180093012  mov     r8, rbp
0x180093015  mov     dword ptr [rsp+68h+var_40], ecx
0x180093019  mov     ecx, r12d
0x18009301c  mov     [rsp+68h+var_48], rsi
0x180093021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093026  jmp     short loc_18009305F
0x180093028  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x18009302f  jz      short loc_18009305F
0x180093031  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180093038  jz      short loc_18009305F
0x18009303a  mov     eax, [rbp+23Ch]
0x180093040  lea     rdx, aLockeventcallb; "LockEventCallback: Propagated async cal"...
0x180093047  mov     r9d, [rbp+30h]
0x18009304b  mov     r8, rbp
0x18009304e  mov     dword ptr [rsp+68h+var_40], eax
0x180093052  mov     ecx, r12d; unsigned int
0x180093055  mov     [rsp+68h+var_48], rsi
0x18009305a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009305f  mov     rcx, [rbx+30h]; this
0x180093063  mov     rdx, rbp; struct _POLICY_SECTION_CONTEXT *
0x180093066  call    ?AddReaderToList@CPolicyCriticalSection@@AEAAKPEAU_POLICY_SECTION_CONTEXT@@@Z; CPolicyCriticalSection::AddReaderToList(_POLICY_SECTION_CONTEXT *)
0x18009306b  mov     esi, eax
0x18009306d  test    eax, eax
0x18009306f  jz      short loc_1800930D1
0x180093071  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180093078  jz      short loc_1800930C2
0x18009307a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093081  test    rax, rax
0x180093084  jz      short loc_18009309C
0x180093086  mov     r8d, esi
0x180093089  lea     rdx, aAddreadertolis; "AddReaderToList failed with 0x%x"
0x180093090  mov     ecx, 2
0x180093095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009309a  jmp     short loc_1800930C2
0x18009309c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800930a3  jz      short loc_1800930C2
0x1800930a5  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800930ac  jz      short loc_1800930C2
0x1800930ae  mov     r8d, esi
0x1800930b1  lea     rdx, aAddreadertolis; "AddReaderToList failed with 0x%x"
0x1800930b8  mov     ecx, 2; unsigned int
0x1800930bd  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800930c2  mov     rcx, rbp; hMem
0x1800930c5  call    ?DeletePolicySectionContext@CPolicyCriticalSection@@CAXPEAU_POLICY_SECTION_CONTEXT@@@Z; CPolicyCriticalSection::DeletePolicySectionContext(_POLICY_SECTION_CONTEXT *)
0x1800930ca  jmp     short loc_1800930D1
0x1800930cc  mov     esi, 5B4h
0x1800930d1  mov     ebp, 1
0x1800930d6  cmp     r14, [rdi]
0x1800930d9  jnz     short loc_1800930E7
0x1800930db  mov     rcx, [rbx+18h]; pwa
0x1800930df  mov     edx, ebp; fCancelPendingCallbacks
0x1800930e1  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800930e7  cmp     r14, [rbx+18h]
0x1800930eb  jnz     short loc_1800930F8
0x1800930ed  mov     rcx, [rdi]; pwa
0x1800930f0  mov     edx, ebp; fCancelPendingCallbacks
0x1800930f2  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800930f8  mov     rcx, [rbx]; struct _RPC_ASYNC_STATE *
0x1800930fb  test    esi, esi
0x1800930fd  jnz     short loc_180093167
0x1800930ff  lea     rdx, [rsp+68h+hMem]; struct _POLICY_SECTION_CONTEXT **
0x180093104  call    ?Server_LockCompleteCall@@YAKPEAU_RPC_ASYNC_STATE@@PEAPEAU_POLICY_SECTION_CONTEXT@@@Z; Server_LockCompleteCall(_RPC_ASYNC_STATE *,_POLICY_SECTION_CONTEXT * *)
0x180093109  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180093110  jz      loc_1800931D9
0x180093116  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009311d  test    rax, rax
0x180093120  jz      short loc_180093139
0x180093122  mov     r8, [rbx]
0x180093125  lea     rdx, aLockTakenSucce; "Lock taken successfully for 0x%p"
0x18009312c  mov     ecx, r12d
0x18009312f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093134  jmp     loc_1800931D9
0x180093139  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180093140  jz      loc_1800931D9
0x180093146  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009314d  jz      loc_1800931D9
0x180093153  mov     r8, [rbx]
0x180093156  lea     rdx, aLockTakenSucce; "Lock taken successfully for 0x%p"
0x18009315d  mov     ecx, r12d; unsigned int
0x180093160  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093165  jmp     short loc_1800931D9
0x180093167  mov     edx, esi; unsigned int
0x180093169  call    ?Server_LockAbortCall@@YAKPEAU_RPC_ASYNC_STATE@@K@Z; Server_LockAbortCall(_RPC_ASYNC_STATE *,ulong)
0x18009316e  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180093175  jz      short loc_1800931C1
0x180093177  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009317e  test    rax, rax
0x180093181  jz      short loc_18009319A
0x180093183  mov     r8, [rbx]
0x180093186  lea     rdx, aLockTimeoutFor; "Lock timeout for 0x%p with error 0x%x"
0x18009318d  mov     r9d, esi
0x180093190  mov     ecx, r12d
0x180093193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093198  jmp     short loc_1800931C1
0x18009319a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800931a1  jz      short loc_1800931C1
0x1800931a3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800931aa  jz      short loc_1800931C1
0x1800931ac  mov     r8, [rbx]
0x1800931af  lea     rdx, aLockTimeoutFor; "Lock timeout for 0x%p with error 0x%x"
0x1800931b6  mov     r9d, esi
0x1800931b9  mov     ecx, r12d; unsigned int
0x1800931bc  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800931c1  mov     rcx, [rbx+30h]
0x1800931c5  lea     rdx, [rbx+28h]; struct _RWLOCK_CONTEXT **
0x1800931c9  mov     rcx, [rcx]; this
0x1800931cc  call    ?CancelLock@CRWLock@@QEAAKPEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::CancelLock(_RWLOCK_CONTEXT * *)
0x1800931d1  mov     rax, [rbx+30h]
0x1800931d5  lock dec dword ptr [rax+8]
0x1800931d9  mov     rcx, [rdi]; pwa
0x1800931dc  call    cs:__imp_CloseThreadpoolWait
0x1800931e2  mov     rcx, [rbx+18h]; pwa
0x1800931e6  mov     [rdi], r15
0x1800931e9  call    cs:__imp_CloseThreadpoolWait
0x1800931ef  mov     rcx, [rbx+38h]; hObject
0x1800931f3  mov     [rbx+18h], r15
0x1800931f7  test    rcx, rcx
0x1800931fa  jz      short loc_180093206
0x1800931fc  call    cs:__imp_CloseHandle
0x180093202  mov     [rbx+38h], r15
0x180093206  mov     edx, 258h
0x18009320b  mov     rcx, rbx; Block
0x18009320e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180093213  lea     r11, [rsp+68h+var_28]
0x180093218  mov     rbx, [r11+30h]
0x18009321c  mov     rbp, [r11+40h]
0x180093220  mov     rsp, r11
0x180093223  pop     r15
0x180093225  pop     r14
0x180093227  pop     r12
0x180093229  pop     rdi
0x18009322a  pop     rsi
0x18009322b  retn
```
