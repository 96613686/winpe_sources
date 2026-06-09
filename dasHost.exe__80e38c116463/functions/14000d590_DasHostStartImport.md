# DasHostStartImport

- ea: `0x14000d590`
- end: `0x14000d7f8`
- name: `DasHostStartImport`
- size: `616`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, unsigned int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000ceec`
- `0x14000d590`
- `0x14001211c`
- `0x140014d74`
- `0x140018634`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d6a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000d6a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d758`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000d758`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000d613`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000d613`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14000d69b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14000d69b`

## pseudocode

```c
__int64 __fastcall DasHostStartImport(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v7; // rdi
  int v11; // edx
  int ProviderFromAepId; // ebx
  int v13; // r8d
  ProviderContext *v14; // rsi
  void *v15; // rcx
  signed int LastError; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 result; // rax
  volatile signed __int32 *v20; // rbx
  signed __int32 v21; // eax
  bool v22; // zf
  int v23; // [rsp+28h] [rbp-38h]
  __int64 v24; // [rsp+40h] [rbp-20h] BYREF
  ProviderContext *v25[2]; // [rsp+48h] [rbp-18h] BYREF
  void *DuplicateTokenHandle; // [rsp+90h] [rbp+30h] BYREF
  struct IClassFactory *v27; // [rsp+98h] [rbp+38h] BYREF

  v7 = *a2;
  *(_OWORD *)v25 = 0;
  v27 = 0;
  v24 = 0;
  DuplicateTokenHandle = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      12,
      &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids);
  EventActivityIdControl(2u, (LPGUID)v7);
  *(_QWORD *)(v7 + 16) = a1;
  ProviderFromAepId = DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(g_providerManager, a3, v25);
  if ( ProviderFromAepId >= 0 )
  {
    v14 = v25[0];
    ProviderFromAepId = ProviderContext::GetClassFactory((RTL_SRWLOCK *)v25[0], &v27);
    if ( ProviderFromAepId >= 0 )
    {
      ProviderFromAepId = ((__int64 (__fastcall *)(struct IClassFactory *, _QWORD, GUID *, __int64))v27->lpVtbl->CreateInstance)(
                            v27,
                            0,
                            &IID_IAepImportExport,
                            v7 + 24);
      if ( ProviderFromAepId >= 0 )
      {
        ((void (__fastcall *)(struct IClassFactory *))v27->lpVtbl->Release)(v27);
        v15 = *(void **)(v7 + 88);
        if ( !v15 || DuplicateToken(v15, SecurityImpersonation, &DuplicateTokenHandle) )
          goto LABEL_11;
        LastError = GetLastError();
        ProviderFromAepId = LastError;
        if ( LastError > 0 )
          ProviderFromAepId = (unsigned __int16)LastError | 0x80070000;
        if ( ProviderFromAepId >= 0 )
        {
LABEL_11:
          ProviderFromAepId = CImportExportCallback::Create(
                                *(const unsigned __int16 **)v14,
                                (void *)v7,
                                *((_DWORD *)v14 + 19),
                                DuplicateTokenHandle,
                                (struct CImportExportCallback **)(v7 + 32));
          if ( ProviderFromAepId >= 0 )
          {
            DuplicateTokenHandle = 0;
            ProviderFromAepId = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v7 + 32))(
                                  *(_QWORD *)(v7 + 32),
                                  &GUID_0c512544_e485_46b6_b339_7a301e1e412d,
                                  &v24);
            if ( ProviderFromAepId >= 0 )
            {
              v17 = *(_QWORD *)(v7 + 24);
              v18 = a5;
              *(_QWORD *)(v7 + 96) = a6;
              *(_QWORD *)(v7 + 104) = a7;
              ProviderFromAepId = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v17 + 24LL))(
                                    v17,
                                    a4,
                                    v18,
                                    v24);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            }
          }
        }
      }
    }
  }
  if ( DuplicateTokenHandle )
    CloseHandle(DuplicateTokenHandle);
  if ( ProviderFromAepId < 0 )
    OnAepImportCompleteStub(0, 0, ProviderFromAepId, (void *)v7);
  result = (__int64)&WPP_RECORDER_INITIALIZED;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    result = WPP_RECORDER_SF_sd(
               *((_QWORD *)WPP_GLOBAL_Control + 5),
               v11,
               v13,
               13,
               &WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids,
               v23,
               ProviderFromAepId);
  v20 = (volatile signed __int32 *)v25[1];
  if ( v25[1] )
  {
    v21 = _InterlockedExchangeAdd((volatile signed __int32 *)v25[1] + 2, 0xFFFFFFFF);
    v22 = v21 == 1;
    result = (unsigned int)(v21 - 1);
    if ( v22 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      result = (unsigned int)_InterlockedDecrement(v20 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d590  mov     [rsp-28h+arg_10], rbx
0x14000d595  mov     [rsp-28h+arg_18], rsi
0x14000d59a  push    rbp
0x14000d59b  push    rdi
0x14000d59c  push    r12
0x14000d59e  push    r14
0x14000d5a0  push    r15
0x14000d5a2  mov     rbp, rsp
0x14000d5a5  sub     rsp, 60h
0x14000d5a9  mov     rdi, [rdx]
0x14000d5ac  xorps   xmm0, xmm0
0x14000d5af  movdqu  xmmword ptr [rbp+var_18], xmm0
0x14000d5b4  mov     r12d, r9d
0x14000d5b7  mov     [rbp+arg_8], 0
0x14000d5bf  mov     rbx, r8
0x14000d5c2  mov     [rbp+var_20], 0
0x14000d5ca  mov     rsi, rcx
0x14000d5cd  mov     [rbp+DuplicateTokenHandle], 0
0x14000d5d5  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d5dc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d5e3  lea     r15, WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids
0x14000d5ea  jz      short loc_14000D607
0x14000d5ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d5f3  mov     r9d, 0Ch; int
0x14000d5f9  mov     [rsp+60h+MessageGuid], r15; MessageGuid
0x14000d5fe  mov     rcx, [rcx+28h]; int
0x14000d602  call    WPP_RECORDER_SF_s
0x14000d607  mov     r14d, 2
0x14000d60d  mov     rdx, rdi; ActivityId
0x14000d610  mov     ecx, r14d; ControlCode
0x14000d613  call    cs:__imp_EventActivityIdControl
0x14000d619  mov     [rdi+10h], rsi
0x14000d61d  lea     r8, [rbp+var_18]
0x14000d621  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x14000d628  mov     rdx, rbx
0x14000d62b  call    ?GetProviderFromAepId@ProviderManager@ProviderManagement@DAS@@QEAAJPEBGAEAV?$shared_ptr@VProviderContext@@@std@@@Z; DAS::ProviderManagement::ProviderManager::GetProviderFromAepId(ushort const *,std::shared_ptr<ProviderContext> &)
0x14000d630  mov     ebx, eax
0x14000d632  test    eax, eax
0x14000d634  js      loc_14000D74F
0x14000d63a  mov     rsi, [rbp+var_18]
0x14000d63e  lea     rdx, [rbp+arg_8]; struct IClassFactory **
0x14000d642  mov     rcx, rsi; this
0x14000d645  call    ?GetClassFactory@ProviderContext@@QEAAJPEAPEAUIClassFactory@@@Z; ProviderContext::GetClassFactory(IClassFactory * *)
0x14000d64a  mov     ebx, eax
0x14000d64c  test    eax, eax
0x14000d64e  js      loc_14000D74F
0x14000d654  mov     rcx, [rbp+arg_8]
0x14000d658  lea     r9, [rdi+18h]
0x14000d65c  lea     r8, IID_IAepImportExport
0x14000d663  xor     edx, edx
0x14000d665  mov     rax, [rcx]
0x14000d668  mov     rax, [rax+18h]
0x14000d66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d671  mov     ebx, eax
0x14000d673  test    eax, eax
0x14000d675  js      loc_14000D748
0x14000d67b  mov     rcx, [rbp+arg_8]
0x14000d67f  mov     rax, [rcx]
0x14000d682  mov     rax, [rax+10h]
0x14000d686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d68b  mov     rcx, [rdi+58h]; ExistingTokenHandle
0x14000d68f  test    rcx, rcx
0x14000d692  jz      short loc_14000D6C2
0x14000d694  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x14000d698  mov     edx, r14d; ImpersonationLevel
0x14000d69b  call    cs:__imp_DuplicateToken
0x14000d6a1  test    eax, eax
0x14000d6a3  jnz     short loc_14000D6C2
0x14000d6a5  call    cs:__imp_GetLastError
0x14000d6ab  mov     ebx, eax
0x14000d6ad  test    eax, eax
0x14000d6af  jle     short loc_14000D6BA
0x14000d6b1  movzx   ebx, ax
0x14000d6b4  or      ebx, 80070000h
0x14000d6ba  test    ebx, ebx
0x14000d6bc  js      loc_14000D748
0x14000d6c2  mov     r9, [rbp+DuplicateTokenHandle]; void *
0x14000d6c6  lea     r14, [rdi+20h]
0x14000d6ca  mov     r8d, [rsi+4Ch]; int
0x14000d6ce  mov     rdx, rdi; void *
0x14000d6d1  mov     rcx, [rsi]; Src
0x14000d6d4  mov     [rsp+60h+MessageGuid], r14; struct CImportExportCallback **
0x14000d6d9  call    ?Create@CImportExportCallback@@SAJPEBGPEAXH1PEAPEAV1@@Z; CImportExportCallback::Create(ushort const *,void *,int,void *,CImportExportCallback * *)
0x14000d6de  mov     ebx, eax
0x14000d6e0  test    eax, eax
0x14000d6e2  js      short loc_14000D748
0x14000d6e4  mov     [rbp+DuplicateTokenHandle], 0
0x14000d6ec  lea     r8, [rbp+var_20]
0x14000d6f0  mov     rcx, [r14]
0x14000d6f3  lea     rdx, _GUID_0c512544_e485_46b6_b339_7a301e1e412d
0x14000d6fa  mov     rax, [rcx]
0x14000d6fd  mov     rax, [rax]
0x14000d700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d705  mov     ebx, eax
0x14000d707  test    eax, eax
0x14000d709  js      short loc_14000D748
0x14000d70b  mov     rax, [rbp+arg_28]
0x14000d70f  mov     edx, r12d
0x14000d712  mov     rcx, [rdi+18h]
0x14000d716  mov     r8, [rbp+arg_20]
0x14000d71a  mov     [rdi+60h], rax
0x14000d71e  mov     rax, [rbp+arg_30]
0x14000d722  mov     [rdi+68h], rax
0x14000d726  mov     rax, [rcx]
0x14000d729  mov     r9, [rbp+var_20]
0x14000d72d  mov     rax, [rax+18h]
0x14000d731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d736  mov     rcx, [rbp+var_20]
0x14000d73a  mov     ebx, eax
0x14000d73c  mov     rax, [rcx]
0x14000d73f  mov     rax, [rax+10h]
0x14000d743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d748  lea     r15, WPP_344ea40e1f873519cdb41334aa7e6fb5_Traceguids
0x14000d74f  mov     rcx, [rbp+DuplicateTokenHandle]; hObject
0x14000d753  test    rcx, rcx
0x14000d756  jz      short loc_14000D75E
0x14000d758  call    cs:__imp_CloseHandle
0x14000d75e  test    ebx, ebx
0x14000d760  jns     short loc_14000D771
0x14000d762  mov     r9, rdi; void *
0x14000d765  mov     r8d, ebx; int
0x14000d768  xor     edx, edx; struct _DEVPROPERTY *
0x14000d76a  xor     ecx, ecx; unsigned int
0x14000d76c  call    ?OnAepImportCompleteStub@@YAJKQEAU_DEVPROPERTY@@JPEAX@Z; OnAepImportCompleteStub(ulong,_DEVPROPERTY * const,long,void *)
0x14000d771  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d778  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d77f  jz      short loc_14000D7A0
0x14000d781  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d788  mov     r9d, 0Dh; int
0x14000d78e  mov     dword ptr [rsp+60h+var_30], ebx; char
0x14000d792  mov     [rsp+60h+MessageGuid], r15; MessageGuid
0x14000d797  mov     rcx, [rcx+28h]; int
0x14000d79b  call    WPP_RECORDER_SF_sd
0x14000d7a0  mov     rbx, [rbp+var_18+8]
0x14000d7a4  test    rbx, rbx
0x14000d7a7  jz      short loc_14000D7DF
0x14000d7a9  or      edi, 0FFFFFFFFh
0x14000d7ac  mov     eax, edi
0x14000d7ae  lock xadd [rbx+8], eax
0x14000d7b3  add     eax, edi
0x14000d7b5  jnz     short loc_14000D7DF
0x14000d7b7  mov     rax, [rbx]
0x14000d7ba  mov     rcx, rbx
0x14000d7bd  mov     rax, [rax]
0x14000d7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7c5  mov     eax, edi
0x14000d7c7  lock xadd [rbx+0Ch], eax
0x14000d7cc  add     eax, edi
0x14000d7ce  jnz     short loc_14000D7DF
0x14000d7d0  mov     rax, [rbx]
0x14000d7d3  mov     rcx, rbx
0x14000d7d6  mov     rax, [rax+8]
0x14000d7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7df  lea     r11, [rsp+60h+var_s0]
0x14000d7e4  mov     rbx, [r11+40h]
0x14000d7e8  mov     rsi, [r11+48h]
0x14000d7ec  mov     rsp, r11
0x14000d7ef  pop     r15
0x14000d7f1  pop     r14
0x14000d7f3  pop     r12
0x14000d7f5  pop     rdi
0x14000d7f6  pop     rbp
0x14000d7f7  retn
```
