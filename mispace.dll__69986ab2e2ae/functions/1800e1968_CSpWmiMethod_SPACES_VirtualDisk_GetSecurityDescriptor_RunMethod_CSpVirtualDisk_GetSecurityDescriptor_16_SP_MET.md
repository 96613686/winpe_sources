# CSpWmiMethod<_SPACES_VirtualDisk_GetSecurityDescriptor>::RunMethod<CSpVirtualDisk::GetSecurityDescriptor,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e1968`
- end: `0x1800e1ce5`
- name: `??$RunMethod@VGetSecurityDescriptor@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_GetSecurityDescriptor@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800e7d60`

## callees

- `0x180001504`
- `0x180001994`
- `0x180006350`
- `0x1800063a0`
- `0x1800063ac`
- `0x18000c644`
- `0x180013b4c`
- `0x1800142e8`
- `0x180014a54`
- `0x1800257fc`
- `0x18005f41c`
- `0x1800e1968`
- `0x1800e3f4c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1b46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1b46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e1b1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e1b1b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e1b36`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e1b36`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e1afb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e1afb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e1bf0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e1bf0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e1caf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e1caf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e1c9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e1c9b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_GetSecurityDescriptor>::RunMethod<CSpVirtualDisk::GetSecurityDescriptor,16>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 SecurityDescriptor; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  __int64 *v10; // r15
  int v11; // r8d
  int v12; // r9d
  bool v13; // zf
  __int64 v14; // rcx
  enum _MI_Result v15; // eax
  HANDLE CurrentThread; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v21; // [rsp+40h] [rbp-40h] BYREF
  BOOL v22; // [rsp+44h] [rbp-3Ch] BYREF
  int v23; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  CSpVirtualDisk::GetSecurityDescriptor *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::GetSecurityDescriptor *)operator new(0x168u);
  SecurityDescriptor = CSpVirtualDisk::GetSecurityDescriptor::GetSecurityDescriptor(v25);
  v8 = SecurityDescriptor;
  if ( SecurityDescriptor )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)SecurityDescriptor + 8LL))(SecurityDescriptor, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpVirtualDisk::GetSecurityDescriptor *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_180338C00,
        v11,
        v12,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v22);
    }
    v14 = *a1;
    if ( *a1 && *(_QWORD *)v14 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v14 + 24LL))(
             v14,
             &MSFT_StorageExtendedStatus_rtti,
             v8 + 32);
      if ( v9 )
        goto LABEL_30;
      if ( *((_DWORD *)a1 + 4) )
      {
        CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v8 + 328);
        if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)(v8 + 328)) )
        {
          v9 = 28;
          goto LABEL_30;
        }
        v10 = (__int64 *)operator new(0x10u);
        *v10 = v8;
        ThreadpoolWork = CreateThreadpoolWork(
                           CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                           v10,
                           0);
        if ( ThreadpoolWork )
        {
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
          {
            v10[1] = (__int64)TokenHandle;
            (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
            v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
            v9 = v17;
            if ( !v17 || v17 == 7 )
            {
              v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
              if ( !v9
                && (*(_QWORD *)(v8 + 336) != *(_QWORD *)&GUID_NULL.Data1
                 || *(_QWORD *)(v8 + 344) != *(_QWORD *)GUID_NULL.Data4) )
              {
                v9 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
                if ( !v9 )
                {
                  SubmitThreadpoolWork(ThreadpoolWork);
                  return v9;
                }
              }
            }
            goto LABEL_30;
          }
        }
        v15 = GleToMiResult();
        goto LABEL_14;
      }
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v9 = v18;
      if ( !v18 || v18 == 7 )
      {
        v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
        v9 = v19;
        if ( !v19 || v19 == 7 )
        {
          v15 = (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
LABEL_14:
          v9 = v15;
        }
      }
    }
    else
    {
      v9 = 4;
    }
LABEL_30:
    (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
    if ( v10 )
      operator delete(v10);
    goto LABEL_32;
  }
  v9 = 27;
LABEL_32:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v9;
}

```

## disassembly

```asm
0x1800e1968  mov     [rsp-38h+arg_18], rbx
0x1800e196d  push    rbp
0x1800e196e  push    rsi
0x1800e196f  push    rdi
0x1800e1970  push    r12
0x1800e1972  push    r13
0x1800e1974  push    r14
0x1800e1976  push    r15
0x1800e1978  mov     rbp, rsp
0x1800e197b  sub     rsp, 80h
0x1800e1982  mov     rax, cs:__security_cookie
0x1800e1989  xor     rax, rsp
0x1800e198c  mov     [rbp+var_8], rax
0x1800e1990  xor     eax, eax
0x1800e1992  mov     rsi, rcx
0x1800e1995  xorps   xmm0, xmm0
0x1800e1998  mov     [rbp+var_10], eax
0x1800e199b  mov     ecx, 168h; Size
0x1800e19a0  mov     [rbp+var_40], eax
0x1800e19a3  movups  [rbp+var_20], xmm0
0x1800e19a7  mov     [rbp+TokenHandle], rax
0x1800e19ab  mov     r12, r8
0x1800e19ae  mov     r13, rdx
0x1800e19b1  xor     r14d, r14d
0x1800e19b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e19b9  mov     rcx, rax; this
0x1800e19bc  mov     [rbp+var_28], rax
0x1800e19c0  call    ??0GetSecurityDescriptor@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::GetSecurityDescriptor::GetSecurityDescriptor(void)
0x1800e19c5  mov     rdi, rax
0x1800e19c8  test    rax, rax
0x1800e19cb  jnz     short loc_1800E19D5
0x1800e19cd  lea     ebx, [rax+1Bh]
0x1800e19d0  jmp     loc_1800E1C92
0x1800e19d5  mov     rax, [rax]
0x1800e19d8  mov     rdx, rsi
0x1800e19db  mov     rcx, rdi
0x1800e19de  xor     r15d, r15d
0x1800e19e1  mov     rax, [rax+8]
0x1800e19e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e19ea  lea     rcx, [rbp+var_40]
0x1800e19ee  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e19f3  mov     [rdi+1Ch], eax
0x1800e19f6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e19fa  mov     ecx, [rsi+14h]; unsigned int
0x1800e19fd  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e1a02  mov     eax, cs:dword_18039EB68
0x1800e1a08  cmp     eax, 5
0x1800e1a0b  jbe     short loc_1800E1A7B
0x1800e1a0d  mov     rdx, 400000000000h
0x1800e1a17  lea     rcx, dword_18039EB68
0x1800e1a1e  call    _tlgKeywordOn
0x1800e1a23  test    al, al
0x1800e1a25  jz      short loc_1800E1A7B
0x1800e1a27  mov     eax, [rbp+var_40]
0x1800e1a2a  lea     rdx, unk_180338C00
0x1800e1a31  xor     ecx, ecx
0x1800e1a33  cmp     [rdi+1Ch], eax
0x1800e1a36  movzx   eax, word ptr [rbp+var_10]
0x1800e1a3a  mov     word ptr [rbp+var_40], ax
0x1800e1a3e  setnz   cl
0x1800e1a41  mov     eax, [rsi+14h]
0x1800e1a44  mov     [rbp+var_38], eax
0x1800e1a47  lea     rax, [rbp+var_20]
0x1800e1a4b  mov     [rbp+var_28], rax
0x1800e1a4f  lea     rax, [rbp+var_3C]
0x1800e1a53  mov     [rsp+80h+var_48], rax
0x1800e1a58  lea     rax, [rbp+var_40]
0x1800e1a5c  mov     [rsp+80h+var_50], rax
0x1800e1a61  lea     rax, [rbp+var_38]
0x1800e1a65  mov     [rsp+80h+var_58], rax
0x1800e1a6a  lea     rax, [rbp+var_28]
0x1800e1a6e  mov     [rsp+80h+var_60], rax
0x1800e1a73  mov     [rbp+var_3C], ecx
0x1800e1a76  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e1a7b  mov     rcx, [rsi]
0x1800e1a7e  test    rcx, rcx
0x1800e1a81  jz      loc_1800E1C68
0x1800e1a87  mov     rax, [rcx]
0x1800e1a8a  test    rax, rax
0x1800e1a8d  jz      loc_1800E1C68
0x1800e1a93  mov     rax, [rax+18h]
0x1800e1a97  lea     r8, [rdi+20h]
0x1800e1a9b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e1aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1aa7  mov     ebx, eax
0x1800e1aa9  test    eax, eax
0x1800e1aab  jnz     loc_1800E1C6D
0x1800e1ab1  cmp     [rsi+10h], r14d
0x1800e1ab5  jz      loc_1800E1C01
0x1800e1abb  lea     rbx, [rdi+148h]
0x1800e1ac2  mov     rcx, rbx
0x1800e1ac5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e1aca  mov     rcx, rbx; struct CSpJobMgr **
0x1800e1acd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e1ad2  test    eax, eax
0x1800e1ad4  jnz     short loc_1800E1ADE
0x1800e1ad6  lea     ebx, [rax+1Ch]
0x1800e1ad9  jmp     loc_1800E1C6D
0x1800e1ade  mov     ecx, 10h; Size
0x1800e1ae3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e1ae8  xor     r8d, r8d; pcbe
0x1800e1aeb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e1af2  mov     rdx, rax; pv
0x1800e1af5  mov     r15, rax
0x1800e1af8  mov     [rax], rdi
0x1800e1afb  call    cs:__imp_CreateThreadpoolWork
0x1800e1b02  nop     dword ptr [rax+rax+00h]
0x1800e1b07  mov     r14, rax
0x1800e1b0a  test    rax, rax
0x1800e1b0d  jnz     short loc_1800E1B1B
0x1800e1b0f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e1b14  mov     ebx, eax
0x1800e1b16  jmp     loc_1800E1C6D
0x1800e1b1b  call    cs:__imp_GetCurrentThread
0x1800e1b22  nop     dword ptr [rax+rax+00h]
0x1800e1b27  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e1b2b  xor     r8d, r8d; OpenAsSelf
0x1800e1b2e  mov     rcx, rax; ThreadHandle
0x1800e1b31  mov     edx, 2000Ch; DesiredAccess
0x1800e1b36  call    cs:__imp_OpenThreadToken
0x1800e1b3d  nop     dword ptr [rax+rax+00h]
0x1800e1b42  test    eax, eax
0x1800e1b44  jnz     short loc_1800E1B59
0x1800e1b46  call    cs:__imp_GetLastError
0x1800e1b4d  nop     dword ptr [rax+rax+00h]
0x1800e1b52  cmp     eax, 3F0h
0x1800e1b57  jnz     short loc_1800E1B0F
0x1800e1b59  mov     rax, [rbp+TokenHandle]
0x1800e1b5d  mov     r8, r13
0x1800e1b60  mov     [r15+8], rax
0x1800e1b64  mov     rcx, rdi
0x1800e1b67  mov     rax, [rdi]
0x1800e1b6a  mov     rdx, [rsi+8]
0x1800e1b6e  mov     rax, [rax+18h]
0x1800e1b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1b77  mov     rax, [rdi]
0x1800e1b7a  mov     rdx, r12
0x1800e1b7d  mov     rcx, rdi
0x1800e1b80  mov     rax, [rax+28h]
0x1800e1b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1b89  mov     ebx, eax
0x1800e1b8b  test    eax, eax
0x1800e1b8d  jz      short loc_1800E1B98
0x1800e1b8f  cmp     eax, 7
0x1800e1b92  jnz     loc_1800E1C6D
0x1800e1b98  mov     rax, [rdi]
0x1800e1b9b  mov     rdx, r12
0x1800e1b9e  mov     rcx, rdi
0x1800e1ba1  mov     rax, [rax+38h]
0x1800e1ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1baa  mov     ebx, eax
0x1800e1bac  test    eax, eax
0x1800e1bae  jnz     loc_1800E1C6D
0x1800e1bb4  mov     rax, [rdi+150h]
0x1800e1bbb  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e1bc2  jnz     short loc_1800E1BD8
0x1800e1bc4  mov     rax, [rdi+158h]
0x1800e1bcb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e1bd2  jz      loc_1800E1C6D
0x1800e1bd8  mov     rdx, r12
0x1800e1bdb  mov     rcx, rdi
0x1800e1bde  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e1be3  mov     ebx, eax
0x1800e1be5  test    eax, eax
0x1800e1be7  jnz     loc_1800E1C6D
0x1800e1bed  mov     rcx, r14; pwk
0x1800e1bf0  call    cs:__imp_SubmitThreadpoolWork
0x1800e1bf7  nop     dword ptr [rax+rax+00h]
0x1800e1bfc  jmp     loc_1800E1CBB
0x1800e1c01  mov     rax, [rdi]
0x1800e1c04  mov     r8, r13
0x1800e1c07  mov     rdx, [rsi+8]
0x1800e1c0b  mov     rcx, rdi
0x1800e1c0e  mov     rax, [rax+10h]
0x1800e1c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1c17  mov     rax, [rdi]
0x1800e1c1a  mov     rdx, r12
0x1800e1c1d  mov     rcx, rdi
0x1800e1c20  mov     rax, [rax+30h]
0x1800e1c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1c29  mov     ebx, eax
0x1800e1c2b  test    eax, eax
0x1800e1c2d  jz      short loc_1800E1C34
0x1800e1c2f  cmp     eax, 7
0x1800e1c32  jnz     short loc_1800E1C6D
0x1800e1c34  mov     rax, [rdi]
0x1800e1c37  mov     rdx, r12
0x1800e1c3a  mov     rcx, rdi
0x1800e1c3d  mov     rax, [rax+28h]
0x1800e1c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1c46  mov     ebx, eax
0x1800e1c48  test    eax, eax
0x1800e1c4a  jz      short loc_1800E1C51
0x1800e1c4c  cmp     eax, 7
0x1800e1c4f  jnz     short loc_1800E1C6D
0x1800e1c51  mov     rax, [rdi]
0x1800e1c54  mov     rdx, r12
0x1800e1c57  mov     rcx, rdi
0x1800e1c5a  mov     rax, [rax+38h]
0x1800e1c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1c63  jmp     loc_1800E1B14
0x1800e1c68  mov     ebx, 4
0x1800e1c6d  mov     rax, [rdi]
0x1800e1c70  mov     edx, 1
0x1800e1c75  mov     rcx, rdi
0x1800e1c78  mov     rax, [rax]
0x1800e1c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1c80  test    r15, r15
0x1800e1c83  jz      short loc_1800E1C92
0x1800e1c85  mov     edx, 10h
0x1800e1c8a  mov     rcx, r15; Block
0x1800e1c8d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e1c92  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e1c96  test    rcx, rcx
0x1800e1c99  jz      short loc_1800E1CA7
0x1800e1c9b  call    cs:__imp_CloseHandle
0x1800e1ca2  nop     dword ptr [rax+rax+00h]
0x1800e1ca7  test    r14, r14
0x1800e1caa  jz      short loc_1800E1CBB
0x1800e1cac  mov     rcx, r14; pwk
0x1800e1caf  call    cs:__imp_CloseThreadpoolWork
0x1800e1cb6  nop     dword ptr [rax+rax+00h]
0x1800e1cbb  mov     eax, ebx
0x1800e1cbd  mov     rcx, [rbp+var_8]
0x1800e1cc1  xor     rcx, rsp; StackCookie
0x1800e1cc4  call    __security_check_cookie
0x1800e1cc9  mov     rbx, [rsp+80h+arg_18]
0x1800e1cd1  add     rsp, 80h
0x1800e1cd8  pop     r15
0x1800e1cda  pop     r14
0x1800e1cdc  pop     r13
0x1800e1cde  pop     r12
0x1800e1ce0  pop     rdi
0x1800e1ce1  pop     rsi
0x1800e1ce2  pop     rbp
0x1800e1ce3  retn
```
