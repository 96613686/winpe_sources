# CSpWmiMethod<_SPACES_StorageTier_GetSupportedSize>::RunMethod<CSpStorageTier::GetSupportedSize,12>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180102944`
- end: `0x180102cc1`
- name: `??$RunMethod@VGetSupportedSize@CSpStorageTier@@$0M@@?$CSpWmiMethod@U_SPACES_StorageTier_GetSupportedSize@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180105a90`

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
- `0x180102944`
- `0x180103fc4`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180102b22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180102af7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180102af7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180102b12`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180102b12`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180102ad7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180102ad7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102bcc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180102bcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180102c8b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180102c8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102c77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180102c77`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageTier_GetSupportedSize>::RunMethod<CSpStorageTier::GetSupportedSize,12>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 SupportedSize; // rax
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
  CSpStorageTier::GetSupportedSize *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageTier::GetSupportedSize *)operator new(0x178u);
  SupportedSize = CSpStorageTier::GetSupportedSize::GetSupportedSize(v25);
  v8 = SupportedSize;
  if ( SupportedSize )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)SupportedSize + 8LL))(SupportedSize, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageTier::GetSupportedSize *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1803410A9,
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
0x180102944  mov     [rsp-38h+arg_18], rbx
0x180102949  push    rbp
0x18010294a  push    rsi
0x18010294b  push    rdi
0x18010294c  push    r12
0x18010294e  push    r13
0x180102950  push    r14
0x180102952  push    r15
0x180102954  mov     rbp, rsp
0x180102957  sub     rsp, 80h
0x18010295e  mov     rax, cs:__security_cookie
0x180102965  xor     rax, rsp
0x180102968  mov     [rbp+var_8], rax
0x18010296c  xor     eax, eax
0x18010296e  mov     rsi, rcx
0x180102971  xorps   xmm0, xmm0
0x180102974  mov     [rbp+var_10], eax
0x180102977  mov     ecx, 178h; Size
0x18010297c  mov     [rbp+var_40], eax
0x18010297f  movups  [rbp+var_20], xmm0
0x180102983  mov     [rbp+TokenHandle], rax
0x180102987  mov     r12, r8
0x18010298a  mov     r13, rdx
0x18010298d  xor     r14d, r14d
0x180102990  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102995  mov     rcx, rax; this
0x180102998  mov     [rbp+var_28], rax
0x18010299c  call    ??0GetSupportedSize@CSpStorageTier@@QEAA@XZ; CSpStorageTier::GetSupportedSize::GetSupportedSize(void)
0x1801029a1  mov     rdi, rax
0x1801029a4  test    rax, rax
0x1801029a7  jnz     short loc_1801029B1
0x1801029a9  lea     ebx, [rax+1Bh]
0x1801029ac  jmp     loc_180102C6E
0x1801029b1  mov     rax, [rax]
0x1801029b4  mov     rdx, rsi
0x1801029b7  mov     rcx, rdi
0x1801029ba  xor     r15d, r15d
0x1801029bd  mov     rax, [rax+8]
0x1801029c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801029c6  lea     rcx, [rbp+var_40]
0x1801029ca  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1801029cf  mov     [rdi+1Ch], eax
0x1801029d2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1801029d6  mov     ecx, [rsi+14h]; unsigned int
0x1801029d9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1801029de  mov     eax, cs:dword_18039EB68
0x1801029e4  cmp     eax, 5
0x1801029e7  jbe     short loc_180102A57
0x1801029e9  mov     rdx, 400000000000h
0x1801029f3  lea     rcx, dword_18039EB68
0x1801029fa  call    _tlgKeywordOn
0x1801029ff  test    al, al
0x180102a01  jz      short loc_180102A57
0x180102a03  mov     eax, [rbp+var_40]
0x180102a06  lea     rdx, byte_1803410A9
0x180102a0d  xor     ecx, ecx
0x180102a0f  cmp     [rdi+1Ch], eax
0x180102a12  movzx   eax, word ptr [rbp+var_10]
0x180102a16  mov     word ptr [rbp+var_40], ax
0x180102a1a  setnz   cl
0x180102a1d  mov     eax, [rsi+14h]
0x180102a20  mov     [rbp+var_38], eax
0x180102a23  lea     rax, [rbp+var_20]
0x180102a27  mov     [rbp+var_28], rax
0x180102a2b  lea     rax, [rbp+var_3C]
0x180102a2f  mov     [rsp+80h+var_48], rax
0x180102a34  lea     rax, [rbp+var_40]
0x180102a38  mov     [rsp+80h+var_50], rax
0x180102a3d  lea     rax, [rbp+var_38]
0x180102a41  mov     [rsp+80h+var_58], rax
0x180102a46  lea     rax, [rbp+var_28]
0x180102a4a  mov     [rsp+80h+var_60], rax
0x180102a4f  mov     [rbp+var_3C], ecx
0x180102a52  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180102a57  mov     rcx, [rsi]
0x180102a5a  test    rcx, rcx
0x180102a5d  jz      loc_180102C44
0x180102a63  mov     rax, [rcx]
0x180102a66  test    rax, rax
0x180102a69  jz      loc_180102C44
0x180102a6f  mov     rax, [rax+18h]
0x180102a73  lea     r8, [rdi+20h]
0x180102a77  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180102a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102a83  mov     ebx, eax
0x180102a85  test    eax, eax
0x180102a87  jnz     loc_180102C49
0x180102a8d  cmp     [rsi+10h], r14d
0x180102a91  jz      loc_180102BDD
0x180102a97  lea     rbx, [rdi+148h]
0x180102a9e  mov     rcx, rbx
0x180102aa1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180102aa6  mov     rcx, rbx; struct CSpJobMgr **
0x180102aa9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180102aae  test    eax, eax
0x180102ab0  jnz     short loc_180102ABA
0x180102ab2  lea     ebx, [rax+1Ch]
0x180102ab5  jmp     loc_180102C49
0x180102aba  mov     ecx, 10h; Size
0x180102abf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102ac4  xor     r8d, r8d; pcbe
0x180102ac7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180102ace  mov     rdx, rax; pv
0x180102ad1  mov     r15, rax
0x180102ad4  mov     [rax], rdi
0x180102ad7  call    cs:__imp_CreateThreadpoolWork
0x180102ade  nop     dword ptr [rax+rax+00h]
0x180102ae3  mov     r14, rax
0x180102ae6  test    rax, rax
0x180102ae9  jnz     short loc_180102AF7
0x180102aeb  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180102af0  mov     ebx, eax
0x180102af2  jmp     loc_180102C49
0x180102af7  call    cs:__imp_GetCurrentThread
0x180102afe  nop     dword ptr [rax+rax+00h]
0x180102b03  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180102b07  xor     r8d, r8d; OpenAsSelf
0x180102b0a  mov     rcx, rax; ThreadHandle
0x180102b0d  mov     edx, 2000Ch; DesiredAccess
0x180102b12  call    cs:__imp_OpenThreadToken
0x180102b19  nop     dword ptr [rax+rax+00h]
0x180102b1e  test    eax, eax
0x180102b20  jnz     short loc_180102B35
0x180102b22  call    cs:__imp_GetLastError
0x180102b29  nop     dword ptr [rax+rax+00h]
0x180102b2e  cmp     eax, 3F0h
0x180102b33  jnz     short loc_180102AEB
0x180102b35  mov     rax, [rbp+TokenHandle]
0x180102b39  mov     r8, r13
0x180102b3c  mov     [r15+8], rax
0x180102b40  mov     rcx, rdi
0x180102b43  mov     rax, [rdi]
0x180102b46  mov     rdx, [rsi+8]
0x180102b4a  mov     rax, [rax+18h]
0x180102b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102b53  mov     rax, [rdi]
0x180102b56  mov     rdx, r12
0x180102b59  mov     rcx, rdi
0x180102b5c  mov     rax, [rax+28h]
0x180102b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102b65  mov     ebx, eax
0x180102b67  test    eax, eax
0x180102b69  jz      short loc_180102B74
0x180102b6b  cmp     eax, 7
0x180102b6e  jnz     loc_180102C49
0x180102b74  mov     rax, [rdi]
0x180102b77  mov     rdx, r12
0x180102b7a  mov     rcx, rdi
0x180102b7d  mov     rax, [rax+38h]
0x180102b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102b86  mov     ebx, eax
0x180102b88  test    eax, eax
0x180102b8a  jnz     loc_180102C49
0x180102b90  mov     rax, [rdi+150h]
0x180102b97  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180102b9e  jnz     short loc_180102BB4
0x180102ba0  mov     rax, [rdi+158h]
0x180102ba7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180102bae  jz      loc_180102C49
0x180102bb4  mov     rdx, r12
0x180102bb7  mov     rcx, rdi
0x180102bba  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180102bbf  mov     ebx, eax
0x180102bc1  test    eax, eax
0x180102bc3  jnz     loc_180102C49
0x180102bc9  mov     rcx, r14; pwk
0x180102bcc  call    cs:__imp_SubmitThreadpoolWork
0x180102bd3  nop     dword ptr [rax+rax+00h]
0x180102bd8  jmp     loc_180102C97
0x180102bdd  mov     rax, [rdi]
0x180102be0  mov     r8, r13
0x180102be3  mov     rdx, [rsi+8]
0x180102be7  mov     rcx, rdi
0x180102bea  mov     rax, [rax+10h]
0x180102bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102bf3  mov     rax, [rdi]
0x180102bf6  mov     rdx, r12
0x180102bf9  mov     rcx, rdi
0x180102bfc  mov     rax, [rax+30h]
0x180102c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102c05  mov     ebx, eax
0x180102c07  test    eax, eax
0x180102c09  jz      short loc_180102C10
0x180102c0b  cmp     eax, 7
0x180102c0e  jnz     short loc_180102C49
0x180102c10  mov     rax, [rdi]
0x180102c13  mov     rdx, r12
0x180102c16  mov     rcx, rdi
0x180102c19  mov     rax, [rax+28h]
0x180102c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102c22  mov     ebx, eax
0x180102c24  test    eax, eax
0x180102c26  jz      short loc_180102C2D
0x180102c28  cmp     eax, 7
0x180102c2b  jnz     short loc_180102C49
0x180102c2d  mov     rax, [rdi]
0x180102c30  mov     rdx, r12
0x180102c33  mov     rcx, rdi
0x180102c36  mov     rax, [rax+38h]
0x180102c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102c3f  jmp     loc_180102AF0
0x180102c44  mov     ebx, 4
0x180102c49  mov     rax, [rdi]
0x180102c4c  mov     edx, 1
0x180102c51  mov     rcx, rdi
0x180102c54  mov     rax, [rax]
0x180102c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102c5c  test    r15, r15
0x180102c5f  jz      short loc_180102C6E
0x180102c61  mov     edx, 10h
0x180102c66  mov     rcx, r15; Block
0x180102c69  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180102c6e  mov     rcx, [rbp+TokenHandle]; hObject
0x180102c72  test    rcx, rcx
0x180102c75  jz      short loc_180102C83
0x180102c77  call    cs:__imp_CloseHandle
0x180102c7e  nop     dword ptr [rax+rax+00h]
0x180102c83  test    r14, r14
0x180102c86  jz      short loc_180102C97
0x180102c88  mov     rcx, r14; pwk
0x180102c8b  call    cs:__imp_CloseThreadpoolWork
0x180102c92  nop     dword ptr [rax+rax+00h]
0x180102c97  mov     eax, ebx
0x180102c99  mov     rcx, [rbp+var_8]
0x180102c9d  xor     rcx, rsp; StackCookie
0x180102ca0  call    __security_check_cookie
0x180102ca5  mov     rbx, [rsp+80h+arg_18]
0x180102cad  add     rsp, 80h
0x180102cb4  pop     r15
0x180102cb6  pop     r14
0x180102cb8  pop     r13
0x180102cba  pop     r12
0x180102cbc  pop     rdi
0x180102cbd  pop     rsi
0x180102cbe  pop     rbp
0x180102cbf  retn
```
