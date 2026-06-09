# CSpWmiMethod<_SPACES_StoragePool_SetSecurityDescriptor>::RunMethod<CSpStoragePool::SetSecurityDescriptor,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bfd58`
- end: `0x1800c00d5`
- name: `??$RunMethod@VSetSecurityDescriptor@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_SetSecurityDescriptor@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800c5060`

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
- `0x1800bfd58`
- `0x1800c1340`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bff36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bff36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bff0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bff0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bff26`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bff26`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bfeeb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bfeeb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bffe0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bffe0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800c009f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800c009f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c008b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c008b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StoragePool_SetSecurityDescriptor>::RunMethod<CSpStoragePool::SetSecurityDescriptor,11>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 v7; // rax
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
  CSpStoragePool::SetSecurityDescriptor *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStoragePool::SetSecurityDescriptor *)operator new(0x160u);
  v7 = CSpStoragePool::SetSecurityDescriptor::SetSecurityDescriptor(v25);
  v8 = v7;
  if ( v7 )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 8LL))(v7, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::SetSecurityDescriptor *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_180330DC6,
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
0x1800bfd58  mov     [rsp-38h+arg_18], rbx
0x1800bfd5d  push    rbp
0x1800bfd5e  push    rsi
0x1800bfd5f  push    rdi
0x1800bfd60  push    r12
0x1800bfd62  push    r13
0x1800bfd64  push    r14
0x1800bfd66  push    r15
0x1800bfd68  mov     rbp, rsp
0x1800bfd6b  sub     rsp, 80h
0x1800bfd72  mov     rax, cs:__security_cookie
0x1800bfd79  xor     rax, rsp
0x1800bfd7c  mov     [rbp+var_8], rax
0x1800bfd80  xor     eax, eax
0x1800bfd82  mov     rsi, rcx
0x1800bfd85  xorps   xmm0, xmm0
0x1800bfd88  mov     [rbp+var_10], eax
0x1800bfd8b  mov     ecx, 160h; Size
0x1800bfd90  mov     [rbp+var_40], eax
0x1800bfd93  movups  [rbp+var_20], xmm0
0x1800bfd97  mov     [rbp+TokenHandle], rax
0x1800bfd9b  mov     r12, r8
0x1800bfd9e  mov     r13, rdx
0x1800bfda1  xor     r14d, r14d
0x1800bfda4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bfda9  mov     rcx, rax; this
0x1800bfdac  mov     [rbp+var_28], rax
0x1800bfdb0  call    ??0SetSecurityDescriptor@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetSecurityDescriptor::SetSecurityDescriptor(void)
0x1800bfdb5  mov     rdi, rax
0x1800bfdb8  test    rax, rax
0x1800bfdbb  jnz     short loc_1800BFDC5
0x1800bfdbd  lea     ebx, [rax+1Bh]
0x1800bfdc0  jmp     loc_1800C0082
0x1800bfdc5  mov     rax, [rax]
0x1800bfdc8  mov     rdx, rsi
0x1800bfdcb  mov     rcx, rdi
0x1800bfdce  xor     r15d, r15d
0x1800bfdd1  mov     rax, [rax+8]
0x1800bfdd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfdda  lea     rcx, [rbp+var_40]
0x1800bfdde  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bfde3  mov     [rdi+1Ch], eax
0x1800bfde6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bfdea  mov     ecx, [rsi+14h]; unsigned int
0x1800bfded  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bfdf2  mov     eax, cs:dword_18039EB68
0x1800bfdf8  cmp     eax, 5
0x1800bfdfb  jbe     short loc_1800BFE6B
0x1800bfdfd  mov     rdx, 400000000000h
0x1800bfe07  lea     rcx, dword_18039EB68
0x1800bfe0e  call    _tlgKeywordOn
0x1800bfe13  test    al, al
0x1800bfe15  jz      short loc_1800BFE6B
0x1800bfe17  mov     eax, [rbp+var_40]
0x1800bfe1a  lea     rdx, word_180330DC6
0x1800bfe21  xor     ecx, ecx
0x1800bfe23  cmp     [rdi+1Ch], eax
0x1800bfe26  movzx   eax, word ptr [rbp+var_10]
0x1800bfe2a  mov     word ptr [rbp+var_40], ax
0x1800bfe2e  setnz   cl
0x1800bfe31  mov     eax, [rsi+14h]
0x1800bfe34  mov     [rbp+var_38], eax
0x1800bfe37  lea     rax, [rbp+var_20]
0x1800bfe3b  mov     [rbp+var_28], rax
0x1800bfe3f  lea     rax, [rbp+var_3C]
0x1800bfe43  mov     [rsp+80h+var_48], rax
0x1800bfe48  lea     rax, [rbp+var_40]
0x1800bfe4c  mov     [rsp+80h+var_50], rax
0x1800bfe51  lea     rax, [rbp+var_38]
0x1800bfe55  mov     [rsp+80h+var_58], rax
0x1800bfe5a  lea     rax, [rbp+var_28]
0x1800bfe5e  mov     [rsp+80h+var_60], rax
0x1800bfe63  mov     [rbp+var_3C], ecx
0x1800bfe66  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bfe6b  mov     rcx, [rsi]
0x1800bfe6e  test    rcx, rcx
0x1800bfe71  jz      loc_1800C0058
0x1800bfe77  mov     rax, [rcx]
0x1800bfe7a  test    rax, rax
0x1800bfe7d  jz      loc_1800C0058
0x1800bfe83  mov     rax, [rax+18h]
0x1800bfe87  lea     r8, [rdi+20h]
0x1800bfe8b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bfe92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe97  mov     ebx, eax
0x1800bfe99  test    eax, eax
0x1800bfe9b  jnz     loc_1800C005D
0x1800bfea1  cmp     [rsi+10h], r14d
0x1800bfea5  jz      loc_1800BFFF1
0x1800bfeab  lea     rbx, [rdi+148h]
0x1800bfeb2  mov     rcx, rbx
0x1800bfeb5  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bfeba  mov     rcx, rbx; struct CSpJobMgr **
0x1800bfebd  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bfec2  test    eax, eax
0x1800bfec4  jnz     short loc_1800BFECE
0x1800bfec6  lea     ebx, [rax+1Ch]
0x1800bfec9  jmp     loc_1800C005D
0x1800bfece  mov     ecx, 10h; Size
0x1800bfed3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bfed8  xor     r8d, r8d; pcbe
0x1800bfedb  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bfee2  mov     rdx, rax; pv
0x1800bfee5  mov     r15, rax
0x1800bfee8  mov     [rax], rdi
0x1800bfeeb  call    cs:__imp_CreateThreadpoolWork
0x1800bfef2  nop     dword ptr [rax+rax+00h]
0x1800bfef7  mov     r14, rax
0x1800bfefa  test    rax, rax
0x1800bfefd  jnz     short loc_1800BFF0B
0x1800bfeff  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bff04  mov     ebx, eax
0x1800bff06  jmp     loc_1800C005D
0x1800bff0b  call    cs:__imp_GetCurrentThread
0x1800bff12  nop     dword ptr [rax+rax+00h]
0x1800bff17  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bff1b  xor     r8d, r8d; OpenAsSelf
0x1800bff1e  mov     rcx, rax; ThreadHandle
0x1800bff21  mov     edx, 2000Ch; DesiredAccess
0x1800bff26  call    cs:__imp_OpenThreadToken
0x1800bff2d  nop     dword ptr [rax+rax+00h]
0x1800bff32  test    eax, eax
0x1800bff34  jnz     short loc_1800BFF49
0x1800bff36  call    cs:__imp_GetLastError
0x1800bff3d  nop     dword ptr [rax+rax+00h]
0x1800bff42  cmp     eax, 3F0h
0x1800bff47  jnz     short loc_1800BFEFF
0x1800bff49  mov     rax, [rbp+TokenHandle]
0x1800bff4d  mov     r8, r13
0x1800bff50  mov     [r15+8], rax
0x1800bff54  mov     rcx, rdi
0x1800bff57  mov     rax, [rdi]
0x1800bff5a  mov     rdx, [rsi+8]
0x1800bff5e  mov     rax, [rax+18h]
0x1800bff62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bff67  mov     rax, [rdi]
0x1800bff6a  mov     rdx, r12
0x1800bff6d  mov     rcx, rdi
0x1800bff70  mov     rax, [rax+28h]
0x1800bff74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bff79  mov     ebx, eax
0x1800bff7b  test    eax, eax
0x1800bff7d  jz      short loc_1800BFF88
0x1800bff7f  cmp     eax, 7
0x1800bff82  jnz     loc_1800C005D
0x1800bff88  mov     rax, [rdi]
0x1800bff8b  mov     rdx, r12
0x1800bff8e  mov     rcx, rdi
0x1800bff91  mov     rax, [rax+38h]
0x1800bff95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bff9a  mov     ebx, eax
0x1800bff9c  test    eax, eax
0x1800bff9e  jnz     loc_1800C005D
0x1800bffa4  mov     rax, [rdi+150h]
0x1800bffab  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bffb2  jnz     short loc_1800BFFC8
0x1800bffb4  mov     rax, [rdi+158h]
0x1800bffbb  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bffc2  jz      loc_1800C005D
0x1800bffc8  mov     rdx, r12
0x1800bffcb  mov     rcx, rdi
0x1800bffce  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bffd3  mov     ebx, eax
0x1800bffd5  test    eax, eax
0x1800bffd7  jnz     loc_1800C005D
0x1800bffdd  mov     rcx, r14; pwk
0x1800bffe0  call    cs:__imp_SubmitThreadpoolWork
0x1800bffe7  nop     dword ptr [rax+rax+00h]
0x1800bffec  jmp     loc_1800C00AB
0x1800bfff1  mov     rax, [rdi]
0x1800bfff4  mov     r8, r13
0x1800bfff7  mov     rdx, [rsi+8]
0x1800bfffb  mov     rcx, rdi
0x1800bfffe  mov     rax, [rax+10h]
0x1800c0002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0007  mov     rax, [rdi]
0x1800c000a  mov     rdx, r12
0x1800c000d  mov     rcx, rdi
0x1800c0010  mov     rax, [rax+30h]
0x1800c0014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0019  mov     ebx, eax
0x1800c001b  test    eax, eax
0x1800c001d  jz      short loc_1800C0024
0x1800c001f  cmp     eax, 7
0x1800c0022  jnz     short loc_1800C005D
0x1800c0024  mov     rax, [rdi]
0x1800c0027  mov     rdx, r12
0x1800c002a  mov     rcx, rdi
0x1800c002d  mov     rax, [rax+28h]
0x1800c0031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0036  mov     ebx, eax
0x1800c0038  test    eax, eax
0x1800c003a  jz      short loc_1800C0041
0x1800c003c  cmp     eax, 7
0x1800c003f  jnz     short loc_1800C005D
0x1800c0041  mov     rax, [rdi]
0x1800c0044  mov     rdx, r12
0x1800c0047  mov     rcx, rdi
0x1800c004a  mov     rax, [rax+38h]
0x1800c004e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0053  jmp     loc_1800BFF04
0x1800c0058  mov     ebx, 4
0x1800c005d  mov     rax, [rdi]
0x1800c0060  mov     edx, 1
0x1800c0065  mov     rcx, rdi
0x1800c0068  mov     rax, [rax]
0x1800c006b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0070  test    r15, r15
0x1800c0073  jz      short loc_1800C0082
0x1800c0075  mov     edx, 10h
0x1800c007a  mov     rcx, r15; Block
0x1800c007d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800c0082  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c0086  test    rcx, rcx
0x1800c0089  jz      short loc_1800C0097
0x1800c008b  call    cs:__imp_CloseHandle
0x1800c0092  nop     dword ptr [rax+rax+00h]
0x1800c0097  test    r14, r14
0x1800c009a  jz      short loc_1800C00AB
0x1800c009c  mov     rcx, r14; pwk
0x1800c009f  call    cs:__imp_CloseThreadpoolWork
0x1800c00a6  nop     dword ptr [rax+rax+00h]
0x1800c00ab  mov     eax, ebx
0x1800c00ad  mov     rcx, [rbp+var_8]
0x1800c00b1  xor     rcx, rsp; StackCookie
0x1800c00b4  call    __security_check_cookie
0x1800c00b9  mov     rbx, [rsp+80h+arg_18]
0x1800c00c1  add     rsp, 80h
0x1800c00c8  pop     r15
0x1800c00ca  pop     r14
0x1800c00cc  pop     r13
0x1800c00ce  pop     r12
0x1800c00d0  pop     rdi
0x1800c00d1  pop     rsi
0x1800c00d2  pop     rbp
0x1800c00d3  retn
```
