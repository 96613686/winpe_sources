# CJob::StaticOnTransferComplete(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180053b90`
- end: `0x180054185`
- name: `?StaticOnTransferComplete@CJob@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `1525`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18001d830`
- `0x180053b90`
- `0x180054274`
- `0x18005579c`
- `0x180091fe0`
- `0x18009d024`
- `0x1800a1114`
- `0x1800a3444`
- `0x1800a7558`
- `0x1800b1160`
- `0x1800b1fe8`
- `0x1800caee4`
- `0x1800cc400`
- `0x1800f64f4`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053d5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053d5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180053ccd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180053ccd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180053c3c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005410b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180054162`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180053c3c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18005410b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180054162`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180054059`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180054059`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180053cfd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180053cfd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180054000`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180054000`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180053d49`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180053d49`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall CJob::StaticOnTransferComplete(
        PTP_CALLBACK_INSTANCE Instance,
        HANDLE *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  DWORD v5; // r12d
  char v6; // r14
  const char *CallbackName; // rax
  __int64 v8; // r10
  EVENT_LOG *v9; // rcx
  CJobManager *v10; // r15
  void *v11; // rbx
  _QWORD *Value; // rax
  void *v13; // rax
  EVENT_LOG *v14; // rcx
  __int64 v15; // rdx
  DWORD v16; // eax
  int v17; // ebx
  __int64 v18; // rax
  __int64 *v19; // r8
  const unsigned __int16 *v20; // rbx
  __int64 v21; // rax
  unsigned __int16 *v22; // rbx
  HANDLE v23; // rdx
  void (__fastcall ***v24)(_QWORD, __int64); // rbx
  signed __int32 v25; // r15d
  unsigned int v26; // edx
  struct _TP_WAIT *v27; // rcx
  CJobManager *v28; // rbx
  EVENT_LOG *v29; // r10
  EVENT_LOG *v30; // r10
  const char *v31; // rax
  __int64 v32; // r10
  const char *v33; // rax
  __int64 v34; // r10
  int v35; // [rsp+30h] [rbp-F8h]
  unsigned __int16 *v36; // [rsp+38h] [rbp-F0h] BYREF
  DWORD v37; // [rsp+40h] [rbp-E8h]
  void *v38; // [rsp+48h] [rbp-E0h] BYREF
  __int64 *v39; // [rsp+50h] [rbp-D8h]
  unsigned __int16 *v40; // [rsp+58h] [rbp-D0h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+70h] [rbp-B8h]
  __int64 v43; // [rsp+80h] [rbp-A8h]
  __int64 v44; // [rsp+88h] [rbp-A0h]
  __int64 v45; // [rsp+90h] [rbp-98h]
  DWORD v46; // [rsp+98h] [rbp-90h]

  v37 = *((_DWORD *)g_GlobalInfo + 52);
  v5 = v37;
  v42 = *((_QWORD *)g_GlobalInfo + 25);
  v6 = v42;
  v43 = *((_QWORD *)g_GlobalInfo + 24);
  v44 = v42;
  v45 = 1;
  v46 = v37;
  if ( (v43 & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      CallbackName = CallbackSleepHelper::GetCallbackName(1u);
      WPP_SF_s(*(_QWORD *)(v8 + 16), 10, &WPP_263cc8d6529f371e5fb175aafd999872_Traceguids, CallbackName);
    }
    Sleep(v37);
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      117,
      &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
      Context,
      Context[4],
      *Context);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = g_Manager;
  v11 = (void *)*((_QWORD *)*Context + 153);
  if ( v9 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)v9 + 2), 30, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
  if ( !v11 )
  {
    Value = TlsGetValue(*((_DWORD *)v10 + 143));
    if ( Value )
      v11 = (void *)Value[6];
    else
      v11 = 0;
  }
  v13 = (void *)*((_QWORD *)v10 + 70);
  if ( !v11 )
  {
    WaitForSingleObject(*((HANDLE *)v10 + 70), 0xFFFFFFFF);
    *((_DWORD *)v10 + 144) = GetCurrentThreadId();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_26;
    v15 = 31;
LABEL_25:
    WPP_SF_(*((_QWORD *)v14 + 2), v15, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
LABEL_26:
    Handles[0] = Context[2];
    v17 = *((_DWORD *)Context + 6);
    v35 = v17;
    if ( !*((_DWORD *)*Context + 166) && (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)Context[4] + 104LL))(Context[4]) )
    {
      v18 = (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)Context[4] + 104LL))(Context[4]);
      (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v18 + 320LL))(v18, &v38);
      v19 = (__int64 *)Context[1];
      v39 = v19;
      v20 = (const unsigned __int16 *)((char *)v38 + 12);
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          68,
          (unsigned int)&WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids,
          (_DWORD)v38 + 12,
          v19[4]);
      if ( v20 )
      {
        v36 = CopyString(v20, 0xFFFFFFFFFFFFFFFFuLL);
        std::unique_ptr<unsigned short>::operator=<std::default_delete<unsigned short>,0>(v39 + 4, &v36);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
      }
      v40 = 0;
      v21 = (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)Context[4] + 104LL))(Context[4]);
      (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v21 + 408LL))(v21, &v40);
      v22 = v40;
      v36 = v40;
      v39 = (__int64 *)Context[1];
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids, v40);
      if ( v22 )
      {
        v36 = CopyString(v22, 0xFFFFFFFFFFFFFFFFuLL);
        std::unique_ptr<unsigned short>::operator=<std::default_delete<unsigned short>,0>(v39 + 5, &v36);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
        operator delete(v22, 2u);
      }
      if ( v38 && _InterlockedExchangeAdd((volatile signed __int32 *)v38 + 2, 0xFFFFFFFF) == 1 )
        operator delete(v38, 0x10u);
      v17 = v35;
    }
    v23 = Context[10];
    Context[10] = 0;
    if ( v23 )
      std::default_delete<ScopedSmeTaskHolder>::operator()();
    ((void (__fastcall *)(char *, _QWORD))Handles[0])((char *)*Context + v17, 0);
    if ( Context == *((HANDLE **)*Context + 81) )
      *((_QWORD *)*Context + 81) = 0;
    v24 = (void (__fastcall ***)(_QWORD, __int64))((char *)*Context + 600);
    v25 = _InterlockedDecrement((volatile signed __int32 *)*Context + 152);
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_d16db4fdda8e3e911b60915595dfa5af_Traceguids, v24, v25);
    if ( !v25 && v24 )
      (**v24)(v24, 1);
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)Context[4] + 40LL))(Context[4]);
    v27 = (struct _TP_WAIT *)Context[6];
    if ( v27 )
    {
      CloseThreadpoolWait(v27);
      Context[6] = 0;
    }
    CJob::TRANSFER_GLOB::`scalar deleting destructor'((CJob::TRANSFER_GLOB *)Context, v26);
    v28 = g_Manager;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    *((_DWORD *)v28 + 144) = 0;
    ReleaseSemaphore(*((HANDLE *)v28 + 70), 1, 0);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
      v29 = WPP_GLOBAL_Control;
    }
    if ( (v6 & 1) != 0 )
    {
      if ( v29 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 )
      {
        v33 = CallbackSleepHelper::GetCallbackName(1u);
        WPP_SF_s(*(_QWORD *)(v34 + 16), 11, &WPP_263cc8d6529f371e5fb175aafd999872_Traceguids, v33);
      }
      Sleep(v5);
    }
    return;
  }
  Handles[0] = v11;
  Handles[1] = v13;
  v16 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( v16 )
  {
    if ( v16 != 1 )
      goto LABEL_26;
    *((_DWORD *)v10 + 144) = GetCurrentThreadId();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_26;
    v15 = 33;
    goto LABEL_25;
  }
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids);
    v30 = WPP_GLOBAL_Control;
  }
  if ( (v6 & 1) != 0 )
  {
    if ( v30 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 )
    {
      v31 = CallbackSleepHelper::GetCallbackName(1u);
      WPP_SF_s(*(_QWORD *)(v32 + 16), 11, &WPP_263cc8d6529f371e5fb175aafd999872_Traceguids, v31);
    }
    Sleep(v37);
  }
}

```

## disassembly

```asm
0x180053b90  mov     r11, rsp
0x180053b93  mov     [r11+8], rbx
0x180053b97  mov     [r11+18h], rsi
0x180053b9b  mov     [r11+10h], rdx
0x180053b9f  push    rdi
0x180053ba0  push    r12
0x180053ba2  push    r13
0x180053ba4  push    r14
0x180053ba6  push    r15
0x180053ba8  sub     rsp, 100h
0x180053baf  mov     rdi, rdx
0x180053bb2  mov     rax, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x180053bb9  mov     r12d, [rax+0D0h]
0x180053bc0  mov     [rsp+128h+var_E8], r12d
0x180053bc5  mov     r14, [rax+0C8h]
0x180053bcc  mov     [rsp+128h+var_B8], r14
0x180053bd1  mov     rcx, [rax+0C0h]
0x180053bd8  mov     [r11-0A8h], rcx
0x180053bdf  mov     [r11-0A0h], r14
0x180053be6  mov     qword ptr [r11-98h], 1
0x180053bf1  mov     [r11-90h], r12d
0x180053bf8  test    cl, 1
0x180053bfb  jz      short loc_180053C44
0x180053bfd  lea     rsi, WPP_GLOBAL_Control
0x180053c04  mov     r10, cs:WPP_GLOBAL_Control
0x180053c0b  cmp     r10, rsi
0x180053c0e  jz      short loc_180053C39
0x180053c10  test    byte ptr [r10+1Ch], 1
0x180053c15  jz      short loc_180053C39
0x180053c17  mov     ecx, 1; unsigned __int64
0x180053c1c  call    ?GetCallbackName@CallbackSleepHelper@@KAPEBD_K@Z; CallbackSleepHelper::GetCallbackName(unsigned __int64)
0x180053c21  mov     r9, rax
0x180053c24  mov     edx, 0Ah
0x180053c29  lea     r8, WPP_263cc8d6529f371e5fb175aafd999872_Traceguids
0x180053c30  mov     rcx, [r10+10h]
0x180053c34  call    WPP_SF_s
0x180053c39  mov     ecx, r12d; dwMilliseconds
0x180053c3c  call    cs:__imp_Sleep
0x180053c42  jmp     short loc_180053C4B
0x180053c44  lea     rsi, WPP_GLOBAL_Control
0x180053c4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180053c52  cmp     rcx, rsi
0x180053c55  jz      short loc_180053C8D
0x180053c57  test    byte ptr [rcx+1Ch], 1
0x180053c5b  jz      short loc_180053C8D
0x180053c5d  mov     edx, 75h ; 'u'
0x180053c62  mov     rax, [rdi]
0x180053c65  mov     [rsp+128h+var_100], rax
0x180053c6a  mov     rax, [rdi+20h]
0x180053c6e  mov     [rsp+128h+var_108], rax
0x180053c73  mov     r9, rdi
0x180053c76  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x180053c7d  mov     rcx, [rcx+10h]
0x180053c81  call    WPP_SF_qqq
0x180053c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180053c8d  mov     r15, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180053c94  mov     rax, [rdi]
0x180053c97  mov     rbx, [rax+4C8h]
0x180053c9e  cmp     rcx, rsi
0x180053ca1  jz      short loc_180053CC1
0x180053ca3  test    dword ptr [rcx+1Ch], 100h
0x180053caa  jz      short loc_180053CC1
0x180053cac  mov     edx, 1Eh
0x180053cb1  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180053cb8  mov     rcx, [rcx+10h]
0x180053cbc  call    WPP_SF_
0x180053cc1  test    rbx, rbx
0x180053cc4  jnz     short loc_180053CE6
0x180053cc6  mov     ecx, [r15+23Ch]; dwTlsIndex
0x180053ccd  call    cs:__imp_TlsGetValue
0x180053cd3  xor     r13d, r13d
0x180053cd6  test    rax, rax
0x180053cd9  jz      short loc_180053CE1
0x180053cdb  mov     rbx, [rax+30h]
0x180053cdf  jmp     short loc_180053CE9
0x180053ce1  mov     rbx, r13
0x180053ce4  jmp     short loc_180053CE9
0x180053ce6  xor     r13d, r13d
0x180053ce9  mov     rax, [r15+230h]
0x180053cf0  test    rbx, rbx
0x180053cf3  jnz     short loc_180053D2C
0x180053cf5  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180053cfa  mov     rcx, rax; hHandle
0x180053cfd  call    cs:__imp_WaitForSingleObject
0x180053d03  call    cs:__imp_GetCurrentThreadId
0x180053d09  mov     [r15+240h], eax
0x180053d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d17  cmp     rcx, rsi
0x180053d1a  jz      short loc_180053D93
0x180053d1c  test    dword ptr [rcx+1Ch], 100h
0x180053d23  jz      short loc_180053D93
0x180053d25  mov     edx, 1Fh
0x180053d2a  jmp     short loc_180053D83
0x180053d2c  mov     [rsp+128h+Handles], rbx
0x180053d31  mov     [rsp+128h+var_C0], rax
0x180053d36  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180053d3c  xor     r8d, r8d; bWaitAll
0x180053d3f  lea     rdx, [rsp+128h+Handles]; lpHandles
0x180053d44  mov     ecx, 2; nCount
0x180053d49  call    cs:__imp_WaitForMultipleObjects
0x180053d4f  test    eax, eax
0x180053d51  jz      loc_1800540A2
0x180053d57  cmp     eax, 1
0x180053d5a  jnz     short loc_180053D93
0x180053d5c  call    cs:__imp_GetCurrentThreadId
0x180053d62  mov     [r15+240h], eax
0x180053d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180053d70  cmp     rcx, rsi
0x180053d73  jz      short loc_180053D93
0x180053d75  test    dword ptr [rcx+1Ch], 100h
0x180053d7c  jz      short loc_180053D93
0x180053d7e  mov     edx, 21h ; '!'
0x180053d83  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180053d8a  mov     rcx, [rcx+10h]
0x180053d8e  call    WPP_SF_
0x180053d93  mov     rax, [rdi+10h]
0x180053d97  mov     [rsp+128h+Handles], rax
0x180053d9c  mov     ebx, [rdi+18h]
0x180053d9f  mov     [rsp+128h+var_F8], ebx
0x180053da3  mov     rax, [rdi]
0x180053da6  cmp     dword ptr [rax+298h], 0
0x180053dad  jnz     loc_180054096
0x180053db3  mov     rcx, [rdi+20h]
0x180053db7  mov     rax, [rcx]
0x180053dba  mov     rax, [rax+68h]
0x180053dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053dc3  test    rax, rax
0x180053dc6  jz      loc_180054096
0x180053dcc  mov     rcx, [rdi+20h]
0x180053dd0  mov     rax, [rcx]
0x180053dd3  mov     rax, [rax+68h]
0x180053dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ddc  mov     r8, rax
0x180053ddf  mov     rcx, [rax]
0x180053de2  mov     rax, [rcx+140h]
0x180053de9  lea     rdx, [rsp+128h+var_E0]
0x180053dee  mov     rcx, r8
0x180053df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053df6  nop
0x180053df7  mov     r8, [rdi+8]
0x180053dfb  mov     [rsp+128h+var_D8], r8
0x180053e00  mov     rbx, [rsp+128h+var_E0]
0x180053e05  add     rbx, 0Ch
0x180053e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180053e10  cmp     rcx, rsi
0x180053e13  jz      short loc_180053E3C
0x180053e15  test    byte ptr [rcx+1Ch], 1
0x180053e19  jz      short loc_180053E3C
0x180053e1b  mov     edx, 44h ; 'D'
0x180053e20  mov     rax, [r8+20h]
0x180053e24  mov     [rsp+128h+var_108], rax
0x180053e29  mov     r9, rbx
0x180053e2c  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x180053e33  mov     rcx, [rcx+10h]
0x180053e37  call    WPP_SF_SS
0x180053e3c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180053e43  test    rbx, rbx
0x180053e46  jz      short loc_180053E75
0x180053e48  mov     rdx, r15; unsigned __int64
0x180053e4b  mov     rcx, rbx; unsigned __int16 *
0x180053e4e  call    ?CopyString@@YAPEAGPEBG_K@Z; CopyString(ushort const *,unsigned __int64)
0x180053e53  mov     [rsp+128h+var_F0], rax
0x180053e58  mov     rcx, [rsp+128h+var_D8]
0x180053e5d  add     rcx, 20h ; ' '
0x180053e61  lea     rdx, [rsp+128h+var_F0]
0x180053e66  call    ??$?4U?$default_delete@G@std@@$0A@@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<ushort>::operator=<std::default_delete<ushort>,0>(std::unique_ptr<ushort> &&)
0x180053e6b  lea     rcx, [rsp+128h+var_F0]; void *
0x180053e70  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180053e75  mov     [rsp+128h+var_D0], r13
0x180053e7a  mov     rcx, [rdi+20h]
0x180053e7e  mov     rax, [rcx]
0x180053e81  mov     rax, [rax+68h]
0x180053e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e8a  mov     r8, rax
0x180053e8d  mov     rcx, [rax]
0x180053e90  mov     rax, [rcx+198h]
0x180053e97  lea     rdx, [rsp+128h+var_D0]
0x180053e9c  mov     rcx, r8
0x180053e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ea4  mov     rbx, [rsp+128h+var_D0]
0x180053ea9  mov     [rsp+128h+var_F0], rbx
0x180053eae  mov     rax, [rdi+8]
0x180053eb2  mov     [rsp+128h+var_D8], rax
0x180053eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180053ebe  cmp     rcx, rsi
0x180053ec1  jz      short loc_180053EE1
0x180053ec3  test    byte ptr [rcx+1Ch], 1
0x180053ec7  jz      short loc_180053EE1
0x180053ec9  mov     edx, 45h ; 'E'
0x180053ece  mov     r9, rbx
0x180053ed1  lea     r8, WPP_1fd7c32195bb3ee2a4a298f9a806e81a_Traceguids
0x180053ed8  mov     rcx, [rcx+10h]
0x180053edc  call    WPP_SF_S
0x180053ee1  test    rbx, rbx
0x180053ee4  jz      short loc_180053F14
0x180053ee6  mov     rdx, r15; unsigned __int64
0x180053ee9  mov     rcx, rbx; unsigned __int16 *
0x180053eec  call    ?CopyString@@YAPEAGPEBG_K@Z; CopyString(ushort const *,unsigned __int64)
0x180053ef1  mov     [rsp+128h+var_F0], rax
0x180053ef6  mov     rcx, [rsp+128h+var_D8]
0x180053efb  add     rcx, 28h ; '('
0x180053eff  lea     rdx, [rsp+128h+var_F0]
0x180053f04  call    ??$?4U?$default_delete@G@std@@$0A@@?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<ushort>::operator=<std::default_delete<ushort>,0>(std::unique_ptr<ushort> &&)
0x180053f09  lea     rcx, [rsp+128h+var_F0]; void *
0x180053f0e  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180053f13  nop
0x180053f14  test    rbx, rbx
0x180053f17  jz      short loc_180053F27
0x180053f19  mov     edx, 2; unsigned __int64
0x180053f1e  mov     rcx, rbx; void *
0x180053f21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180053f26  nop
0x180053f27  mov     rax, [rsp+128h+var_E0]
0x180053f2c  test    rax, rax
0x180053f2f  jz      short loc_180053F4D
0x180053f31  mov     ecx, r15d
0x180053f34  lock xadd [rax+8], ecx
0x180053f39  cmp     ecx, 1
0x180053f3c  jnz     short loc_180053F4D
0x180053f3e  mov     edx, 10h; unsigned __int64
0x180053f43  mov     rcx, [rsp+128h+var_E0]; void *
0x180053f48  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180053f4d  mov     ebx, [rsp+128h+var_F8]
0x180053f51  mov     rdx, [rdi+50h]
0x180053f55  mov     [rdi+50h], r13
0x180053f59  test    rdx, rdx
0x180053f5c  jz      short loc_180053F63
0x180053f5e  call    ??R?$default_delete@VScopedSmeTaskHolder@@@std@@QEBAXPEAVScopedSmeTaskHolder@@@Z; std::default_delete<ScopedSmeTaskHolder>::operator()(ScopedSmeTaskHolder *)
0x180053f63  movsxd  rcx, ebx
0x180053f66  add     rcx, [rdi]
0x180053f69  xor     edx, edx
0x180053f6b  mov     rax, [rsp+128h+Handles]
0x180053f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f75  mov     rax, [rdi]
0x180053f78  cmp     rdi, [rax+288h]
0x180053f7f  jnz     short loc_180053F88
0x180053f81  mov     [rax+288h], r13
0x180053f88  mov     rbx, [rdi]
0x180053f8b  add     rbx, 258h
0x180053f92  lock xadd [rbx+8], r15d
0x180053f98  dec     r15d
0x180053f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180053fa2  cmp     rcx, rsi
0x180053fa5  jz      short loc_180053FCA
0x180053fa7  test    byte ptr [rcx+1Ch], 10h
0x180053fab  jz      short loc_180053FCA
0x180053fad  mov     edx, 12h
0x180053fb2  mov     dword ptr [rsp+128h+var_108], r15d
0x180053fb7  mov     r9, rbx
0x180053fba  lea     r8, WPP_d16db4fdda8e3e911b60915595dfa5af_Traceguids
0x180053fc1  mov     rcx, [rcx+10h]
0x180053fc5  call    WPP_SF_qD
0x180053fca  test    r15d, r15d
0x180053fcd  jnz     short loc_180053FE7
0x180053fcf  test    rbx, rbx
0x180053fd2  jz      short loc_180053FE7
0x180053fd4  mov     rax, [rbx]
0x180053fd7  mov     edx, 1
0x180053fdc  mov     rcx, rbx
0x180053fdf  mov     rax, [rax]
0x180053fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fe7  mov     rcx, [rdi+20h]
0x180053feb  mov     rax, [rcx]
0x180053fee  mov     rax, [rax+28h]
0x180053ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ff7  mov     rcx, [rdi+30h]; pwa
0x180053ffb  test    rcx, rcx
0x180053ffe  jz      short loc_18005400A
0x180054000  call    cs:__imp_CloseThreadpoolWait
0x180054006  mov     [rdi+30h], r13
0x18005400a  mov     rcx, rdi; this
0x18005400d  call    ??_GTRANSFER_GLOB@CJob@@QEAAPEAXI@Z; CJob::TRANSFER_GLOB::`scalar deleting destructor'(uint)
0x180054012  mov     rbx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180054019  mov     rcx, cs:WPP_GLOBAL_Control
0x180054020  cmp     rcx, rsi
0x180054023  jz      short loc_180054043
0x180054025  test    dword ptr [rcx+1Ch], 100h
0x18005402c  jz      short loc_180054043
0x18005402e  mov     edx, 25h ; '%'
0x180054033  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x18005403a  mov     rcx, [rcx+10h]
0x18005403e  call    WPP_SF_
0x180054043  mov     [rbx+240h], r13d
0x18005404a  xor     r8d, r8d; lpPreviousCount
0x18005404d  mov     edx, 1; lReleaseCount
0x180054052  mov     rcx, [rbx+230h]; hSemaphore
0x180054059  call    cs:__imp_ReleaseSemaphore
0x18005405f  mov     r10, cs:WPP_GLOBAL_Control
0x180054066  cmp     r10, rsi
0x180054069  jz      short loc_180054091
0x18005406b  test    dword ptr [r10+1Ch], 100h
0x180054073  jz      short loc_180054091
0x180054075  mov     edx, 26h ; '&'
0x18005407a  lea     r8, WPP_4fe726ef5dcf3cca3fca6a18c3f036ea_Traceguids
0x180054081  mov     rcx, [r10+10h]
0x180054085  call    WPP_SF_
0x18005408a  mov     r10, cs:WPP_GLOBAL_Control
0x180054091  jmp     loc_18005412B
0x180054096  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18005409d  jmp     loc_180053F51
  ... truncated ...
```
