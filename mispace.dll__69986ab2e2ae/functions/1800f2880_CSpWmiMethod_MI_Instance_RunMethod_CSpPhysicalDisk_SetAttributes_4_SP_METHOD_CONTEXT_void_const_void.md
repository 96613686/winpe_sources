# CSpWmiMethod<_MI_Instance>::RunMethod<CSpPhysicalDisk::SetAttributes,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f2880`
- end: `0x1800f2c01`
- name: `??$RunMethod@VSetAttributes@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800f77c0`

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
- `0x18006de84`
- `0x1800f2880`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f2a60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f2a35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f2a35`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f2a50`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f2a50`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f2a15`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f2a15`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f2b0b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f2b0b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f2bcb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f2bcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2bb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f2bb7`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpPhysicalDisk::SetAttributes,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int128 **v6; // r14
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int128 *v8; // rdi
  int v9; // r8d
  int v10; // r9d
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v13; // ebx
  enum _MI_Result v14; // eax
  HANDLE CurrentThread; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v20; // [rsp+40h] [rbp-40h] BYREF
  BOOL v21; // [rsp+44h] [rbp-3Ch] BYREF
  int v22; // [rsp+48h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-30h] BYREF
  __int128 *v24; // [rsp+58h] [rbp-28h] BYREF
  __int128 v25; // [rsp+60h] [rbp-20h] BYREF
  int v26; // [rsp+70h] [rbp-10h]

  v26 = 0;
  v20 = 0;
  v25 = 0;
  TokenHandle = 0;
  v6 = 0;
  ThreadpoolWork = 0;
  v24 = (__int128 *)operator new(0x160u);
  v8 = v24;
  CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(v24);
  *(_QWORD *)v24 = &CSpPhysicalDisk::SetAttributes::`vftable';
  ((void (__fastcall *)(__int128 *, __int64 *))CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::SetContext)(v8, a1);
  *((_DWORD *)v8 + 7) = _GetSubsystemVersion(&v20);
  WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v25);
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v11 = *((_DWORD *)v8 + 7) == v20;
    LOWORD(v20) = v26;
    v22 = *((_DWORD *)a1 + 5);
    v24 = &v25;
    v21 = !v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)&dword_18033E724,
      v9,
      v10,
      (__int64)&v24,
      (__int64)&v22,
      (__int64)&v20,
      (__int64)&v21);
  }
  v12 = *a1;
  if ( !*a1 || !*(_QWORD *)v12 )
  {
    v13 = 4;
    goto LABEL_28;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD *))(*(_QWORD *)v12 + 24LL))(
          v12,
          &MSFT_StorageExtendedStatus_rtti,
          (_QWORD *)v8 + 4);
  if ( !v13 )
  {
    if ( *((_DWORD *)a1 + 4) )
    {
      CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release((char *)v8 + 328);
      if ( !(unsigned int)CSpJobMgr::GetInstance((struct CSpJobMgr **)v8 + 41) )
      {
        v13 = 28;
        goto LABEL_28;
      }
      v6 = (__int128 **)operator new(0x10u);
      *v6 = v8;
      ThreadpoolWork = CreateThreadpoolWork(
                         CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::ResumeMethodWorker,
                         v6,
                         0);
      if ( ThreadpoolWork )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
        {
          v6[1] = (__int128 *)TokenHandle;
          (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 24LL))(v8, a1[1], a2);
          v16 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
          v13 = v16;
          if ( !v16 || v16 == 7 )
          {
            v13 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
            if ( !v13
              && (*((_QWORD *)v8 + 42) != *(_QWORD *)&GUID_NULL.Data1
               || *((_QWORD *)v8 + 43) != *(_QWORD *)GUID_NULL.Data4) )
            {
              v13 = CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(v8, a3);
              if ( !v13 )
              {
                SubmitThreadpoolWork(ThreadpoolWork);
                return v13;
              }
            }
          }
          goto LABEL_28;
        }
      }
      v14 = GleToMiResult();
    }
    else
    {
      (*(void (__fastcall **)(__int128 *, __int64, __int64))(*(_QWORD *)v8 + 16LL))(v8, a1[1], a2);
      v17 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 48LL))(v8, a3);
      v13 = v17;
      if ( v17 && v17 != 7 )
        goto LABEL_28;
      v18 = (*(__int64 (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 40LL))(v8, a3);
      v13 = v18;
      if ( v18 )
      {
        if ( v18 != 7 )
          goto LABEL_28;
      }
      v14 = (*(unsigned int (__fastcall **)(__int128 *, __int64))(*(_QWORD *)v8 + 56LL))(v8, a3);
    }
    v13 = v14;
  }
LABEL_28:
  (**(void (__fastcall ***)(__int128 *, __int64))v8)(v8, 1);
  if ( v6 )
    operator delete(v6);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  return v13;
}

```

## disassembly

```asm
0x1800f2880  mov     [rsp-38h+arg_18], rbx
0x1800f2885  push    rbp
0x1800f2886  push    rsi
0x1800f2887  push    rdi
0x1800f2888  push    r12
0x1800f288a  push    r13
0x1800f288c  push    r14
0x1800f288e  push    r15
0x1800f2890  mov     rbp, rsp
0x1800f2893  sub     rsp, 80h
0x1800f289a  mov     rax, cs:__security_cookie
0x1800f28a1  xor     rax, rsp
0x1800f28a4  mov     [rbp+var_8], rax
0x1800f28a8  xor     eax, eax
0x1800f28aa  mov     r12, rcx
0x1800f28ad  xorps   xmm0, xmm0
0x1800f28b0  mov     [rbp+var_10], eax
0x1800f28b3  mov     ecx, 160h; Size
0x1800f28b8  mov     [rbp+var_40], eax
0x1800f28bb  movups  [rbp+var_20], xmm0
0x1800f28bf  mov     [rbp+TokenHandle], rax
0x1800f28c3  mov     r15, r8
0x1800f28c6  mov     r13, rdx
0x1800f28c9  xor     r14d, r14d
0x1800f28cc  xor     esi, esi
0x1800f28ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f28d3  mov     rcx, rax
0x1800f28d6  mov     [rbp+var_28], rax
0x1800f28da  mov     rdi, rax
0x1800f28dd  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x1800f28e2  lea     rax, ??_7SetAttributes@CSpPhysicalDisk@@6B@; const CSpPhysicalDisk::SetAttributes::`vftable'
0x1800f28e9  mov     rdx, r12
0x1800f28ec  mov     [rdi], rax
0x1800f28ef  mov     rcx, rdi
0x1800f28f2  mov     rax, cs:off_180209D78
0x1800f28f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f28fe  lea     rcx, [rbp+var_40]
0x1800f2902  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f2907  mov     [rdi+1Ch], eax
0x1800f290a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f290e  mov     ecx, [r12+14h]; unsigned int
0x1800f2913  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f2918  mov     eax, cs:dword_18039EB68
0x1800f291e  cmp     eax, 5
0x1800f2921  jbe     short loc_1800F2993
0x1800f2923  mov     rdx, 400000000000h
0x1800f292d  lea     rcx, dword_18039EB68
0x1800f2934  call    _tlgKeywordOn
0x1800f2939  test    al, al
0x1800f293b  jz      short loc_1800F2993
0x1800f293d  mov     eax, [rbp+var_40]
0x1800f2940  lea     rdx, dword_18033E724
0x1800f2947  xor     ecx, ecx
0x1800f2949  cmp     [rdi+1Ch], eax
0x1800f294c  movzx   eax, word ptr [rbp+var_10]
0x1800f2950  mov     word ptr [rbp+var_40], ax
0x1800f2954  setnz   cl
0x1800f2957  mov     eax, [r12+14h]
0x1800f295c  mov     [rbp+var_38], eax
0x1800f295f  lea     rax, [rbp+var_20]
0x1800f2963  mov     [rbp+var_28], rax
0x1800f2967  lea     rax, [rbp+var_3C]
0x1800f296b  mov     [rsp+80h+var_48], rax
0x1800f2970  lea     rax, [rbp+var_40]
0x1800f2974  mov     [rsp+80h+var_50], rax
0x1800f2979  lea     rax, [rbp+var_38]
0x1800f297d  mov     [rsp+80h+var_58], rax
0x1800f2982  lea     rax, [rbp+var_28]
0x1800f2986  mov     [rsp+80h+var_60], rax
0x1800f298b  mov     [rbp+var_3C], ecx
0x1800f298e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f2993  mov     rcx, [r12]
0x1800f2997  test    rcx, rcx
0x1800f299a  jz      loc_1800F2B84
0x1800f29a0  mov     rax, [rcx]
0x1800f29a3  test    rax, rax
0x1800f29a6  jz      loc_1800F2B84
0x1800f29ac  mov     rax, [rax+18h]
0x1800f29b0  lea     r8, [rdi+20h]
0x1800f29b4  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f29bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f29c0  mov     ebx, eax
0x1800f29c2  test    eax, eax
0x1800f29c4  jnz     loc_1800F2B89
0x1800f29ca  cmp     [r12+10h], esi
0x1800f29cf  jz      loc_1800F2B1C
0x1800f29d5  lea     rbx, [rdi+148h]
0x1800f29dc  mov     rcx, rbx
0x1800f29df  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f29e4  mov     rcx, rbx; struct CSpJobMgr **
0x1800f29e7  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f29ec  test    eax, eax
0x1800f29ee  jnz     short loc_1800F29F8
0x1800f29f0  lea     ebx, [rax+1Ch]
0x1800f29f3  jmp     loc_1800F2B89
0x1800f29f8  mov     ecx, 10h; Size
0x1800f29fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f2a02  xor     r8d, r8d; pcbe
0x1800f2a05  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f2a0c  mov     rdx, rax; pv
0x1800f2a0f  mov     r14, rax
0x1800f2a12  mov     [rax], rdi
0x1800f2a15  call    cs:__imp_CreateThreadpoolWork
0x1800f2a1c  nop     dword ptr [rax+rax+00h]
0x1800f2a21  mov     rsi, rax
0x1800f2a24  test    rax, rax
0x1800f2a27  jnz     short loc_1800F2A35
0x1800f2a29  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f2a2e  mov     ebx, eax
0x1800f2a30  jmp     loc_1800F2B89
0x1800f2a35  call    cs:__imp_GetCurrentThread
0x1800f2a3c  nop     dword ptr [rax+rax+00h]
0x1800f2a41  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f2a45  xor     r8d, r8d; OpenAsSelf
0x1800f2a48  mov     rcx, rax; ThreadHandle
0x1800f2a4b  mov     edx, 2000Ch; DesiredAccess
0x1800f2a50  call    cs:__imp_OpenThreadToken
0x1800f2a57  nop     dword ptr [rax+rax+00h]
0x1800f2a5c  test    eax, eax
0x1800f2a5e  jnz     short loc_1800F2A73
0x1800f2a60  call    cs:__imp_GetLastError
0x1800f2a67  nop     dword ptr [rax+rax+00h]
0x1800f2a6c  cmp     eax, 3F0h
0x1800f2a71  jnz     short loc_1800F2A29
0x1800f2a73  mov     rax, [rbp+TokenHandle]
0x1800f2a77  mov     r8, r13
0x1800f2a7a  mov     [r14+8], rax
0x1800f2a7e  mov     rcx, rdi
0x1800f2a81  mov     rax, [rdi]
0x1800f2a84  mov     rdx, [r12+8]
0x1800f2a89  mov     rax, [rax+18h]
0x1800f2a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2a92  mov     rax, [rdi]
0x1800f2a95  mov     rdx, r15
0x1800f2a98  mov     rcx, rdi
0x1800f2a9b  mov     rax, [rax+28h]
0x1800f2a9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2aa4  mov     ebx, eax
0x1800f2aa6  test    eax, eax
0x1800f2aa8  jz      short loc_1800F2AB3
0x1800f2aaa  cmp     eax, 7
0x1800f2aad  jnz     loc_1800F2B89
0x1800f2ab3  mov     rax, [rdi]
0x1800f2ab6  mov     rdx, r15
0x1800f2ab9  mov     rcx, rdi
0x1800f2abc  mov     rax, [rax+38h]
0x1800f2ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2ac5  mov     ebx, eax
0x1800f2ac7  test    eax, eax
0x1800f2ac9  jnz     loc_1800F2B89
0x1800f2acf  mov     rax, [rdi+150h]
0x1800f2ad6  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f2add  jnz     short loc_1800F2AF3
0x1800f2adf  mov     rax, [rdi+158h]
0x1800f2ae6  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f2aed  jz      loc_1800F2B89
0x1800f2af3  mov     rdx, r15
0x1800f2af6  mov     rcx, rdi
0x1800f2af9  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f2afe  mov     ebx, eax
0x1800f2b00  test    eax, eax
0x1800f2b02  jnz     loc_1800F2B89
0x1800f2b08  mov     rcx, rsi; pwk
0x1800f2b0b  call    cs:__imp_SubmitThreadpoolWork
0x1800f2b12  nop     dword ptr [rax+rax+00h]
0x1800f2b17  jmp     loc_1800F2BD7
0x1800f2b1c  mov     rax, [rdi]
0x1800f2b1f  mov     r8, r13
0x1800f2b22  mov     rdx, [r12+8]
0x1800f2b27  mov     rcx, rdi
0x1800f2b2a  mov     rax, [rax+10h]
0x1800f2b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2b33  mov     rax, [rdi]
0x1800f2b36  mov     rdx, r15
0x1800f2b39  mov     rcx, rdi
0x1800f2b3c  mov     rax, [rax+30h]
0x1800f2b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2b45  mov     ebx, eax
0x1800f2b47  test    eax, eax
0x1800f2b49  jz      short loc_1800F2B50
0x1800f2b4b  cmp     eax, 7
0x1800f2b4e  jnz     short loc_1800F2B89
0x1800f2b50  mov     rax, [rdi]
0x1800f2b53  mov     rdx, r15
0x1800f2b56  mov     rcx, rdi
0x1800f2b59  mov     rax, [rax+28h]
0x1800f2b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2b62  mov     ebx, eax
0x1800f2b64  test    eax, eax
0x1800f2b66  jz      short loc_1800F2B6D
0x1800f2b68  cmp     eax, 7
0x1800f2b6b  jnz     short loc_1800F2B89
0x1800f2b6d  mov     rax, [rdi]
0x1800f2b70  mov     rdx, r15
0x1800f2b73  mov     rcx, rdi
0x1800f2b76  mov     rax, [rax+38h]
0x1800f2b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2b7f  jmp     loc_1800F2A2E
0x1800f2b84  mov     ebx, 4
0x1800f2b89  mov     rax, [rdi]
0x1800f2b8c  mov     edx, 1
0x1800f2b91  mov     rcx, rdi
0x1800f2b94  mov     rax, [rax]
0x1800f2b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2b9c  test    r14, r14
0x1800f2b9f  jz      short loc_1800F2BAE
0x1800f2ba1  mov     edx, 10h
0x1800f2ba6  mov     rcx, r14; Block
0x1800f2ba9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f2bae  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f2bb2  test    rcx, rcx
0x1800f2bb5  jz      short loc_1800F2BC3
0x1800f2bb7  call    cs:__imp_CloseHandle
0x1800f2bbe  nop     dword ptr [rax+rax+00h]
0x1800f2bc3  test    rsi, rsi
0x1800f2bc6  jz      short loc_1800F2BD7
0x1800f2bc8  mov     rcx, rsi; pwk
0x1800f2bcb  call    cs:__imp_CloseThreadpoolWork
0x1800f2bd2  nop     dword ptr [rax+rax+00h]
0x1800f2bd7  mov     eax, ebx
0x1800f2bd9  mov     rcx, [rbp+var_8]
0x1800f2bdd  xor     rcx, rsp; StackCookie
0x1800f2be0  call    __security_check_cookie
0x1800f2be5  mov     rbx, [rsp+80h+arg_18]
0x1800f2bed  add     rsp, 80h
0x1800f2bf4  pop     r15
0x1800f2bf6  pop     r14
0x1800f2bf8  pop     r13
0x1800f2bfa  pop     r12
0x1800f2bfc  pop     rdi
0x1800f2bfd  pop     rsi
0x1800f2bfe  pop     rbp
0x1800f2bff  retn
```
