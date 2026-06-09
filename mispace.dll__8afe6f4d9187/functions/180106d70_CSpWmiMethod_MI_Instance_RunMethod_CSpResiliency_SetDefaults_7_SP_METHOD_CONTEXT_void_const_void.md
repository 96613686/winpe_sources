# CSpWmiMethod<_MI_Instance>::RunMethod<CSpResiliency::SetDefaults,7>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x180106d70`
- end: `0x1801070c2`
- name: `??$RunMethod@VSetDefaults@CSpResiliency@@$06@?$CSpWmiMethod@U_MI_Instance@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `850`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180107720`

## callees

- `0x1800014ec`
- `0x180001970`
- `0x180006290`
- `0x1800062e0`
- `0x1800062ec`
- `0x18000c704`
- `0x180013898`
- `0x180014000`
- `0x180014720`
- `0x180024dfc`
- `0x18005d58c`
- `0x18006baa8`
- `0x180106d70`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180106f3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106f1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180106f1f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180106f34`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180106f34`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180106f05`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180106f05`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180106fdf`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180106fdf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180107093`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180107093`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180107085`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180107085`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_MI_Instance>::RunMethod<CSpResiliency::SetDefaults,7>(
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
  *(_QWORD *)v24 = &CSpResiliency::SetDefaults::`vftable';
  ((void (__fastcall *)(__int128 *, __int64 *))CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::SetContext)(v8, a1);
  *((_DWORD *)v8 + 7) = _GetSubsystemVersion(&v20);
  WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v25);
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v11 = *((_DWORD *)v8 + 7) == v20;
    LOWORD(v20) = v26;
    v22 = *((_DWORD *)a1 + 5);
    v24 = &v25;
    v21 = !v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v21,
      (unsigned int)byte_18033AE7D,
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
0x180106d70  mov     [rsp-38h+arg_18], rbx
0x180106d75  push    rbp
0x180106d76  push    rsi
0x180106d77  push    rdi
0x180106d78  push    r12
0x180106d7a  push    r13
0x180106d7c  push    r14
0x180106d7e  push    r15
0x180106d80  mov     rbp, rsp
0x180106d83  sub     rsp, 80h
0x180106d8a  mov     rax, cs:__security_cookie
0x180106d91  xor     rax, rsp
0x180106d94  mov     [rbp+var_8], rax
0x180106d98  xor     eax, eax
0x180106d9a  mov     r12, rcx
0x180106d9d  xorps   xmm0, xmm0
0x180106da0  mov     [rbp+var_10], eax
0x180106da3  mov     ecx, 160h; Size
0x180106da8  mov     [rbp+var_40], eax
0x180106dab  movups  [rbp+var_20], xmm0
0x180106daf  mov     [rbp+TokenHandle], rax
0x180106db3  mov     r15, r8
0x180106db6  mov     r13, rdx
0x180106db9  xor     r14d, r14d
0x180106dbc  xor     esi, esi
0x180106dbe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180106dc3  mov     rcx, rax
0x180106dc6  mov     [rbp+var_28], rax
0x180106dca  mov     rdi, rax
0x180106dcd  call    ??0?$CSpWmiMethod@U_MI_Instance@@@@QEAA@XZ; CSpWmiMethod<_MI_Instance>::CSpWmiMethod<_MI_Instance>(void)
0x180106dd2  lea     rax, ??_7SetDefaults@CSpResiliency@@6B@; const CSpResiliency::SetDefaults::`vftable'
0x180106dd9  mov     rdx, r12
0x180106ddc  mov     [rdi], rax
0x180106ddf  mov     rcx, rdi
0x180106de2  mov     rax, cs:off_1802038D8
0x180106de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106dee  lea     rcx, [rbp+var_40]
0x180106df2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x180106df7  mov     [rdi+1Ch], eax
0x180106dfa  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x180106dfe  mov     ecx, [r12+14h]; unsigned int
0x180106e03  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x180106e08  mov     eax, cs:dword_180397B68
0x180106e0e  cmp     eax, 5
0x180106e11  jbe     short loc_180106E83
0x180106e13  mov     rdx, 400000000000h
0x180106e1d  lea     rcx, dword_180397B68
0x180106e24  call    _tlgKeywordOn
0x180106e29  test    al, al
0x180106e2b  jz      short loc_180106E83
0x180106e2d  mov     eax, [rbp+var_40]
0x180106e30  lea     rdx, byte_18033AE7D
0x180106e37  xor     ecx, ecx
0x180106e39  cmp     [rdi+1Ch], eax
0x180106e3c  movzx   eax, word ptr [rbp+var_10]
0x180106e40  mov     word ptr [rbp+var_40], ax
0x180106e44  setnz   cl
0x180106e47  mov     eax, [r12+14h]
0x180106e4c  mov     [rbp+var_38], eax
0x180106e4f  lea     rax, [rbp+var_20]
0x180106e53  mov     [rbp+var_28], rax
0x180106e57  lea     rax, [rbp+var_3C]
0x180106e5b  mov     [rsp+80h+var_48], rax
0x180106e60  lea     rax, [rbp+var_40]
0x180106e64  mov     [rsp+80h+var_50], rax
0x180106e69  lea     rax, [rbp+var_38]
0x180106e6d  mov     [rsp+80h+var_58], rax
0x180106e72  lea     rax, [rbp+var_28]
0x180106e76  mov     [rsp+80h+var_60], rax
0x180106e7b  mov     [rbp+var_3C], ecx
0x180106e7e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x180106e83  mov     rcx, [r12]
0x180106e87  test    rcx, rcx
0x180106e8a  jz      loc_180107052
0x180106e90  mov     rax, [rcx]
0x180106e93  test    rax, rax
0x180106e96  jz      loc_180107052
0x180106e9c  mov     rax, [rax+18h]
0x180106ea0  lea     r8, [rdi+20h]
0x180106ea4  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x180106eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106eb0  mov     ebx, eax
0x180106eb2  test    eax, eax
0x180106eb4  jnz     loc_180107057
0x180106eba  cmp     [r12+10h], esi
0x180106ebf  jz      loc_180106FEA
0x180106ec5  lea     rbx, [rdi+148h]
0x180106ecc  mov     rcx, rbx
0x180106ecf  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180106ed4  mov     rcx, rbx; struct CSpJobMgr **
0x180106ed7  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x180106edc  test    eax, eax
0x180106ede  jnz     short loc_180106EE8
0x180106ee0  lea     ebx, [rax+1Ch]
0x180106ee3  jmp     loc_180107057
0x180106ee8  mov     ecx, 10h; Size
0x180106eed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180106ef2  xor     r8d, r8d; pcbe
0x180106ef5  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180106efc  mov     rdx, rax; pv
0x180106eff  mov     r14, rax
0x180106f02  mov     [rax], rdi
0x180106f05  call    cs:__imp_CreateThreadpoolWork
0x180106f0b  mov     rsi, rax
0x180106f0e  test    rax, rax
0x180106f11  jnz     short loc_180106F1F
0x180106f13  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180106f18  mov     ebx, eax
0x180106f1a  jmp     loc_180107057
0x180106f1f  call    cs:__imp_GetCurrentThread
0x180106f25  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180106f29  xor     r8d, r8d; OpenAsSelf
0x180106f2c  mov     rcx, rax; ThreadHandle
0x180106f2f  mov     edx, 2000Ch; DesiredAccess
0x180106f34  call    cs:__imp_OpenThreadToken
0x180106f3a  test    eax, eax
0x180106f3c  jnz     short loc_180106F4B
0x180106f3e  call    cs:__imp_GetLastError
0x180106f44  cmp     eax, 3F0h
0x180106f49  jnz     short loc_180106F13
0x180106f4b  mov     rax, [rbp+TokenHandle]
0x180106f4f  mov     r8, r13
0x180106f52  mov     [r14+8], rax
0x180106f56  mov     rcx, rdi
0x180106f59  mov     rax, [rdi]
0x180106f5c  mov     rdx, [r12+8]
0x180106f61  mov     rax, [rax+18h]
0x180106f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106f6a  mov     rax, [rdi]
0x180106f6d  mov     rdx, r15
0x180106f70  mov     rcx, rdi
0x180106f73  mov     rax, [rax+28h]
0x180106f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106f7c  mov     ebx, eax
0x180106f7e  test    eax, eax
0x180106f80  jz      short loc_180106F8B
0x180106f82  cmp     eax, 7
0x180106f85  jnz     loc_180107057
0x180106f8b  mov     rax, [rdi]
0x180106f8e  mov     rdx, r15
0x180106f91  mov     rcx, rdi
0x180106f94  mov     rax, [rax+38h]
0x180106f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180106f9d  mov     ebx, eax
0x180106f9f  test    eax, eax
0x180106fa1  jnz     loc_180107057
0x180106fa7  mov     rax, [rdi+150h]
0x180106fae  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180106fb5  jnz     short loc_180106FCB
0x180106fb7  mov     rax, [rdi+158h]
0x180106fbe  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180106fc5  jz      loc_180107057
0x180106fcb  mov     rdx, r15
0x180106fce  mov     rcx, rdi
0x180106fd1  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x180106fd6  mov     ebx, eax
0x180106fd8  test    eax, eax
0x180106fda  jnz     short loc_180107057
0x180106fdc  mov     rcx, rsi; pwk
0x180106fdf  call    cs:__imp_SubmitThreadpoolWork
0x180106fe5  jmp     loc_180107099
0x180106fea  mov     rax, [rdi]
0x180106fed  mov     r8, r13
0x180106ff0  mov     rdx, [r12+8]
0x180106ff5  mov     rcx, rdi
0x180106ff8  mov     rax, [rax+10h]
0x180106ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107001  mov     rax, [rdi]
0x180107004  mov     rdx, r15
0x180107007  mov     rcx, rdi
0x18010700a  mov     rax, [rax+30h]
0x18010700e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107013  mov     ebx, eax
0x180107015  test    eax, eax
0x180107017  jz      short loc_18010701E
0x180107019  cmp     eax, 7
0x18010701c  jnz     short loc_180107057
0x18010701e  mov     rax, [rdi]
0x180107021  mov     rdx, r15
0x180107024  mov     rcx, rdi
0x180107027  mov     rax, [rax+28h]
0x18010702b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180107030  mov     ebx, eax
0x180107032  test    eax, eax
0x180107034  jz      short loc_18010703B
0x180107036  cmp     eax, 7
0x180107039  jnz     short loc_180107057
0x18010703b  mov     rax, [rdi]
0x18010703e  mov     rdx, r15
0x180107041  mov     rcx, rdi
0x180107044  mov     rax, [rax+38h]
0x180107048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010704d  jmp     loc_180106F18
0x180107052  mov     ebx, 4
0x180107057  mov     rax, [rdi]
0x18010705a  mov     edx, 1
0x18010705f  mov     rcx, rdi
0x180107062  mov     rax, [rax]
0x180107065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010706a  test    r14, r14
0x18010706d  jz      short loc_18010707C
0x18010706f  mov     edx, 10h
0x180107074  mov     rcx, r14; Block
0x180107077  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18010707c  mov     rcx, [rbp+TokenHandle]; hObject
0x180107080  test    rcx, rcx
0x180107083  jz      short loc_18010708B
0x180107085  call    cs:__imp_CloseHandle
0x18010708b  test    rsi, rsi
0x18010708e  jz      short loc_180107099
0x180107090  mov     rcx, rsi; pwk
0x180107093  call    cs:__imp_CloseThreadpoolWork
0x180107099  mov     eax, ebx
0x18010709b  mov     rcx, [rbp+var_8]
0x18010709f  xor     rcx, rsp; StackCookie
0x1801070a2  call    __security_check_cookie
0x1801070a7  mov     rbx, [rsp+80h+arg_18]
0x1801070af  add     rsp, 80h
0x1801070b6  pop     r15
0x1801070b8  pop     r14
0x1801070ba  pop     r13
0x1801070bc  pop     r12
0x1801070be  pop     rdi
0x1801070bf  pop     rsi
0x1801070c0  pop     rbp
0x1801070c1  retn
```
