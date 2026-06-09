# CSpWmiMethod<_SPACES_VirtualDisk_SetUsage>::RunMethod<CSpVirtualDisk::SetUsage,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e390c`
- end: `0x1800e3c89`
- name: `??$RunMethod@VSetUsage@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_SetUsage@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

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
- `0x1800e390c`
- `0x1800e434c`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3aea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3aea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e3abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e3abf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e3ada`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e3ada`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e3a9f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e3a9f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e3b94`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e3b94`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e3c53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e3c53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e3c3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e3c3f`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_SetUsage>::RunMethod<CSpVirtualDisk::SetUsage,16>(
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
  CSpVirtualDisk::SetUsage *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::SetUsage *)operator new(0x160u);
  v7 = CSpVirtualDisk::SetUsage::SetUsage(v25);
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
      v25 = (CSpVirtualDisk::SetUsage *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1803396FD,
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
0x1800e390c  mov     [rsp-38h+arg_18], rbx
0x1800e3911  push    rbp
0x1800e3912  push    rsi
0x1800e3913  push    rdi
0x1800e3914  push    r12
0x1800e3916  push    r13
0x1800e3918  push    r14
0x1800e391a  push    r15
0x1800e391c  mov     rbp, rsp
0x1800e391f  sub     rsp, 80h
0x1800e3926  mov     rax, cs:__security_cookie
0x1800e392d  xor     rax, rsp
0x1800e3930  mov     [rbp+var_8], rax
0x1800e3934  xor     eax, eax
0x1800e3936  mov     rsi, rcx
0x1800e3939  xorps   xmm0, xmm0
0x1800e393c  mov     [rbp+var_10], eax
0x1800e393f  mov     ecx, 160h; Size
0x1800e3944  mov     [rbp+var_40], eax
0x1800e3947  movups  [rbp+var_20], xmm0
0x1800e394b  mov     [rbp+TokenHandle], rax
0x1800e394f  mov     r12, r8
0x1800e3952  mov     r13, rdx
0x1800e3955  xor     r14d, r14d
0x1800e3958  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e395d  mov     rcx, rax; this
0x1800e3960  mov     [rbp+var_28], rax
0x1800e3964  call    ??0SetUsage@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::SetUsage::SetUsage(void)
0x1800e3969  mov     rdi, rax
0x1800e396c  test    rax, rax
0x1800e396f  jnz     short loc_1800E3979
0x1800e3971  lea     ebx, [rax+1Bh]
0x1800e3974  jmp     loc_1800E3C36
0x1800e3979  mov     rax, [rax]
0x1800e397c  mov     rdx, rsi
0x1800e397f  mov     rcx, rdi
0x1800e3982  xor     r15d, r15d
0x1800e3985  mov     rax, [rax+8]
0x1800e3989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e398e  lea     rcx, [rbp+var_40]
0x1800e3992  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e3997  mov     [rdi+1Ch], eax
0x1800e399a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e399e  mov     ecx, [rsi+14h]; unsigned int
0x1800e39a1  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e39a6  mov     eax, cs:dword_18039EB68
0x1800e39ac  cmp     eax, 5
0x1800e39af  jbe     short loc_1800E3A1F
0x1800e39b1  mov     rdx, 400000000000h
0x1800e39bb  lea     rcx, dword_18039EB68
0x1800e39c2  call    _tlgKeywordOn
0x1800e39c7  test    al, al
0x1800e39c9  jz      short loc_1800E3A1F
0x1800e39cb  mov     eax, [rbp+var_40]
0x1800e39ce  lea     rdx, byte_1803396FD
0x1800e39d5  xor     ecx, ecx
0x1800e39d7  cmp     [rdi+1Ch], eax
0x1800e39da  movzx   eax, word ptr [rbp+var_10]
0x1800e39de  mov     word ptr [rbp+var_40], ax
0x1800e39e2  setnz   cl
0x1800e39e5  mov     eax, [rsi+14h]
0x1800e39e8  mov     [rbp+var_38], eax
0x1800e39eb  lea     rax, [rbp+var_20]
0x1800e39ef  mov     [rbp+var_28], rax
0x1800e39f3  lea     rax, [rbp+var_3C]
0x1800e39f7  mov     [rsp+80h+var_48], rax
0x1800e39fc  lea     rax, [rbp+var_40]
0x1800e3a00  mov     [rsp+80h+var_50], rax
0x1800e3a05  lea     rax, [rbp+var_38]
0x1800e3a09  mov     [rsp+80h+var_58], rax
0x1800e3a0e  lea     rax, [rbp+var_28]
0x1800e3a12  mov     [rsp+80h+var_60], rax
0x1800e3a17  mov     [rbp+var_3C], ecx
0x1800e3a1a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e3a1f  mov     rcx, [rsi]
0x1800e3a22  test    rcx, rcx
0x1800e3a25  jz      loc_1800E3C0C
0x1800e3a2b  mov     rax, [rcx]
0x1800e3a2e  test    rax, rax
0x1800e3a31  jz      loc_1800E3C0C
0x1800e3a37  mov     rax, [rax+18h]
0x1800e3a3b  lea     r8, [rdi+20h]
0x1800e3a3f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e3a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3a4b  mov     ebx, eax
0x1800e3a4d  test    eax, eax
0x1800e3a4f  jnz     loc_1800E3C11
0x1800e3a55  cmp     [rsi+10h], r14d
0x1800e3a59  jz      loc_1800E3BA5
0x1800e3a5f  lea     rbx, [rdi+148h]
0x1800e3a66  mov     rcx, rbx
0x1800e3a69  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e3a6e  mov     rcx, rbx; struct CSpJobMgr **
0x1800e3a71  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e3a76  test    eax, eax
0x1800e3a78  jnz     short loc_1800E3A82
0x1800e3a7a  lea     ebx, [rax+1Ch]
0x1800e3a7d  jmp     loc_1800E3C11
0x1800e3a82  mov     ecx, 10h; Size
0x1800e3a87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e3a8c  xor     r8d, r8d; pcbe
0x1800e3a8f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e3a96  mov     rdx, rax; pv
0x1800e3a99  mov     r15, rax
0x1800e3a9c  mov     [rax], rdi
0x1800e3a9f  call    cs:__imp_CreateThreadpoolWork
0x1800e3aa6  nop     dword ptr [rax+rax+00h]
0x1800e3aab  mov     r14, rax
0x1800e3aae  test    rax, rax
0x1800e3ab1  jnz     short loc_1800E3ABF
0x1800e3ab3  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e3ab8  mov     ebx, eax
0x1800e3aba  jmp     loc_1800E3C11
0x1800e3abf  call    cs:__imp_GetCurrentThread
0x1800e3ac6  nop     dword ptr [rax+rax+00h]
0x1800e3acb  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e3acf  xor     r8d, r8d; OpenAsSelf
0x1800e3ad2  mov     rcx, rax; ThreadHandle
0x1800e3ad5  mov     edx, 2000Ch; DesiredAccess
0x1800e3ada  call    cs:__imp_OpenThreadToken
0x1800e3ae1  nop     dword ptr [rax+rax+00h]
0x1800e3ae6  test    eax, eax
0x1800e3ae8  jnz     short loc_1800E3AFD
0x1800e3aea  call    cs:__imp_GetLastError
0x1800e3af1  nop     dword ptr [rax+rax+00h]
0x1800e3af6  cmp     eax, 3F0h
0x1800e3afb  jnz     short loc_1800E3AB3
0x1800e3afd  mov     rax, [rbp+TokenHandle]
0x1800e3b01  mov     r8, r13
0x1800e3b04  mov     [r15+8], rax
0x1800e3b08  mov     rcx, rdi
0x1800e3b0b  mov     rax, [rdi]
0x1800e3b0e  mov     rdx, [rsi+8]
0x1800e3b12  mov     rax, [rax+18h]
0x1800e3b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b1b  mov     rax, [rdi]
0x1800e3b1e  mov     rdx, r12
0x1800e3b21  mov     rcx, rdi
0x1800e3b24  mov     rax, [rax+28h]
0x1800e3b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b2d  mov     ebx, eax
0x1800e3b2f  test    eax, eax
0x1800e3b31  jz      short loc_1800E3B3C
0x1800e3b33  cmp     eax, 7
0x1800e3b36  jnz     loc_1800E3C11
0x1800e3b3c  mov     rax, [rdi]
0x1800e3b3f  mov     rdx, r12
0x1800e3b42  mov     rcx, rdi
0x1800e3b45  mov     rax, [rax+38h]
0x1800e3b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3b4e  mov     ebx, eax
0x1800e3b50  test    eax, eax
0x1800e3b52  jnz     loc_1800E3C11
0x1800e3b58  mov     rax, [rdi+150h]
0x1800e3b5f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e3b66  jnz     short loc_1800E3B7C
0x1800e3b68  mov     rax, [rdi+158h]
0x1800e3b6f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e3b76  jz      loc_1800E3C11
0x1800e3b7c  mov     rdx, r12
0x1800e3b7f  mov     rcx, rdi
0x1800e3b82  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e3b87  mov     ebx, eax
0x1800e3b89  test    eax, eax
0x1800e3b8b  jnz     loc_1800E3C11
0x1800e3b91  mov     rcx, r14; pwk
0x1800e3b94  call    cs:__imp_SubmitThreadpoolWork
0x1800e3b9b  nop     dword ptr [rax+rax+00h]
0x1800e3ba0  jmp     loc_1800E3C5F
0x1800e3ba5  mov     rax, [rdi]
0x1800e3ba8  mov     r8, r13
0x1800e3bab  mov     rdx, [rsi+8]
0x1800e3baf  mov     rcx, rdi
0x1800e3bb2  mov     rax, [rax+10h]
0x1800e3bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3bbb  mov     rax, [rdi]
0x1800e3bbe  mov     rdx, r12
0x1800e3bc1  mov     rcx, rdi
0x1800e3bc4  mov     rax, [rax+30h]
0x1800e3bc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3bcd  mov     ebx, eax
0x1800e3bcf  test    eax, eax
0x1800e3bd1  jz      short loc_1800E3BD8
0x1800e3bd3  cmp     eax, 7
0x1800e3bd6  jnz     short loc_1800E3C11
0x1800e3bd8  mov     rax, [rdi]
0x1800e3bdb  mov     rdx, r12
0x1800e3bde  mov     rcx, rdi
0x1800e3be1  mov     rax, [rax+28h]
0x1800e3be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3bea  mov     ebx, eax
0x1800e3bec  test    eax, eax
0x1800e3bee  jz      short loc_1800E3BF5
0x1800e3bf0  cmp     eax, 7
0x1800e3bf3  jnz     short loc_1800E3C11
0x1800e3bf5  mov     rax, [rdi]
0x1800e3bf8  mov     rdx, r12
0x1800e3bfb  mov     rcx, rdi
0x1800e3bfe  mov     rax, [rax+38h]
0x1800e3c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3c07  jmp     loc_1800E3AB8
0x1800e3c0c  mov     ebx, 4
0x1800e3c11  mov     rax, [rdi]
0x1800e3c14  mov     edx, 1
0x1800e3c19  mov     rcx, rdi
0x1800e3c1c  mov     rax, [rax]
0x1800e3c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3c24  test    r15, r15
0x1800e3c27  jz      short loc_1800E3C36
0x1800e3c29  mov     edx, 10h
0x1800e3c2e  mov     rcx, r15; Block
0x1800e3c31  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e3c36  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e3c3a  test    rcx, rcx
0x1800e3c3d  jz      short loc_1800E3C4B
0x1800e3c3f  call    cs:__imp_CloseHandle
0x1800e3c46  nop     dword ptr [rax+rax+00h]
0x1800e3c4b  test    r14, r14
0x1800e3c4e  jz      short loc_1800E3C5F
0x1800e3c50  mov     rcx, r14; pwk
0x1800e3c53  call    cs:__imp_CloseThreadpoolWork
0x1800e3c5a  nop     dword ptr [rax+rax+00h]
0x1800e3c5f  mov     eax, ebx
0x1800e3c61  mov     rcx, [rbp+var_8]
0x1800e3c65  xor     rcx, rsp; StackCookie
0x1800e3c68  call    __security_check_cookie
0x1800e3c6d  mov     rbx, [rsp+80h+arg_18]
0x1800e3c75  add     rsp, 80h
0x1800e3c7c  pop     r15
0x1800e3c7e  pop     r14
0x1800e3c80  pop     r13
0x1800e3c82  pop     r12
0x1800e3c84  pop     rdi
0x1800e3c85  pop     rsi
0x1800e3c86  pop     rbp
0x1800e3c87  retn
```
