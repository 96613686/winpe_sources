# CSpWmiMethod<_SPACES_StoragePool_SetSecurityDescriptor>::RunMethod<CSpStoragePool::SetSecurityDescriptor,11>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800bcd8c`
- end: `0x1800bd0da`
- name: `??$RunMethod@VSetSecurityDescriptor@CSpStoragePool@@$0L@@?$CSpWmiMethod@U_SPACES_StoragePool_SetSecurityDescriptor@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800c1f80`

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
- `0x1800bcd8c`
- `0x1800be2b4`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcf58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcf58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bcf39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bcf39`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bcf4e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800bcf4e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bcf1f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800bcf1f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bcff8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bcff8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd0ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800bd0ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd09d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd09d`

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
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStoragePool::SetSecurityDescriptor *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_180329E05,
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
0x1800bcd8c  mov     [rsp-38h+arg_18], rbx
0x1800bcd91  push    rbp
0x1800bcd92  push    rsi
0x1800bcd93  push    rdi
0x1800bcd94  push    r12
0x1800bcd96  push    r13
0x1800bcd98  push    r14
0x1800bcd9a  push    r15
0x1800bcd9c  mov     rbp, rsp
0x1800bcd9f  sub     rsp, 80h
0x1800bcda6  mov     rax, cs:__security_cookie
0x1800bcdad  xor     rax, rsp
0x1800bcdb0  mov     [rbp+var_8], rax
0x1800bcdb4  xor     eax, eax
0x1800bcdb6  mov     rsi, rcx
0x1800bcdb9  xorps   xmm0, xmm0
0x1800bcdbc  mov     [rbp+var_10], eax
0x1800bcdbf  mov     ecx, 160h; Size
0x1800bcdc4  mov     [rbp+var_40], eax
0x1800bcdc7  movups  [rbp+var_20], xmm0
0x1800bcdcb  mov     [rbp+TokenHandle], rax
0x1800bcdcf  mov     r12, r8
0x1800bcdd2  mov     r13, rdx
0x1800bcdd5  xor     r14d, r14d
0x1800bcdd8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bcddd  mov     rcx, rax; this
0x1800bcde0  mov     [rbp+var_28], rax
0x1800bcde4  call    ??0SetSecurityDescriptor@CSpStoragePool@@QEAA@XZ; CSpStoragePool::SetSecurityDescriptor::SetSecurityDescriptor(void)
0x1800bcde9  mov     rdi, rax
0x1800bcdec  test    rax, rax
0x1800bcdef  jnz     short loc_1800BCDF9
0x1800bcdf1  lea     ebx, [rax+1Bh]
0x1800bcdf4  jmp     loc_1800BD094
0x1800bcdf9  mov     rax, [rax]
0x1800bcdfc  mov     rdx, rsi
0x1800bcdff  mov     rcx, rdi
0x1800bce02  xor     r15d, r15d
0x1800bce05  mov     rax, [rax+8]
0x1800bce09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bce0e  lea     rcx, [rbp+var_40]
0x1800bce12  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800bce17  mov     [rdi+1Ch], eax
0x1800bce1a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800bce1e  mov     ecx, [rsi+14h]; unsigned int
0x1800bce21  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800bce26  mov     eax, cs:dword_180397B68
0x1800bce2c  cmp     eax, 5
0x1800bce2f  jbe     short loc_1800BCE9F
0x1800bce31  mov     rdx, 400000000000h
0x1800bce3b  lea     rcx, dword_180397B68
0x1800bce42  call    _tlgKeywordOn
0x1800bce47  test    al, al
0x1800bce49  jz      short loc_1800BCE9F
0x1800bce4b  mov     eax, [rbp+var_40]
0x1800bce4e  lea     rdx, byte_180329E05
0x1800bce55  xor     ecx, ecx
0x1800bce57  cmp     [rdi+1Ch], eax
0x1800bce5a  movzx   eax, word ptr [rbp+var_10]
0x1800bce5e  mov     word ptr [rbp+var_40], ax
0x1800bce62  setnz   cl
0x1800bce65  mov     eax, [rsi+14h]
0x1800bce68  mov     [rbp+var_38], eax
0x1800bce6b  lea     rax, [rbp+var_20]
0x1800bce6f  mov     [rbp+var_28], rax
0x1800bce73  lea     rax, [rbp+var_3C]
0x1800bce77  mov     [rsp+80h+var_48], rax
0x1800bce7c  lea     rax, [rbp+var_40]
0x1800bce80  mov     [rsp+80h+var_50], rax
0x1800bce85  lea     rax, [rbp+var_38]
0x1800bce89  mov     [rsp+80h+var_58], rax
0x1800bce8e  lea     rax, [rbp+var_28]
0x1800bce92  mov     [rsp+80h+var_60], rax
0x1800bce97  mov     [rbp+var_3C], ecx
0x1800bce9a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800bce9f  mov     rcx, [rsi]
0x1800bcea2  test    rcx, rcx
0x1800bcea5  jz      loc_1800BD06A
0x1800bceab  mov     rax, [rcx]
0x1800bceae  test    rax, rax
0x1800bceb1  jz      loc_1800BD06A
0x1800bceb7  mov     rax, [rax+18h]
0x1800bcebb  lea     r8, [rdi+20h]
0x1800bcebf  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800bcec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcecb  mov     ebx, eax
0x1800bcecd  test    eax, eax
0x1800bcecf  jnz     loc_1800BD06F
0x1800bced5  cmp     [rsi+10h], r14d
0x1800bced9  jz      loc_1800BD003
0x1800bcedf  lea     rbx, [rdi+148h]
0x1800bcee6  mov     rcx, rbx
0x1800bcee9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800bceee  mov     rcx, rbx; struct CSpJobMgr **
0x1800bcef1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800bcef6  test    eax, eax
0x1800bcef8  jnz     short loc_1800BCF02
0x1800bcefa  lea     ebx, [rax+1Ch]
0x1800bcefd  jmp     loc_1800BD06F
0x1800bcf02  mov     ecx, 10h; Size
0x1800bcf07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bcf0c  xor     r8d, r8d; pcbe
0x1800bcf0f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800bcf16  mov     rdx, rax; pv
0x1800bcf19  mov     r15, rax
0x1800bcf1c  mov     [rax], rdi
0x1800bcf1f  call    cs:__imp_CreateThreadpoolWork
0x1800bcf25  mov     r14, rax
0x1800bcf28  test    rax, rax
0x1800bcf2b  jnz     short loc_1800BCF39
0x1800bcf2d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800bcf32  mov     ebx, eax
0x1800bcf34  jmp     loc_1800BD06F
0x1800bcf39  call    cs:__imp_GetCurrentThread
0x1800bcf3f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800bcf43  xor     r8d, r8d; OpenAsSelf
0x1800bcf46  mov     rcx, rax; ThreadHandle
0x1800bcf49  mov     edx, 2000Ch; DesiredAccess
0x1800bcf4e  call    cs:__imp_OpenThreadToken
0x1800bcf54  test    eax, eax
0x1800bcf56  jnz     short loc_1800BCF65
0x1800bcf58  call    cs:__imp_GetLastError
0x1800bcf5e  cmp     eax, 3F0h
0x1800bcf63  jnz     short loc_1800BCF2D
0x1800bcf65  mov     rax, [rbp+TokenHandle]
0x1800bcf69  mov     r8, r13
0x1800bcf6c  mov     [r15+8], rax
0x1800bcf70  mov     rcx, rdi
0x1800bcf73  mov     rax, [rdi]
0x1800bcf76  mov     rdx, [rsi+8]
0x1800bcf7a  mov     rax, [rax+18h]
0x1800bcf7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcf83  mov     rax, [rdi]
0x1800bcf86  mov     rdx, r12
0x1800bcf89  mov     rcx, rdi
0x1800bcf8c  mov     rax, [rax+28h]
0x1800bcf90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcf95  mov     ebx, eax
0x1800bcf97  test    eax, eax
0x1800bcf99  jz      short loc_1800BCFA4
0x1800bcf9b  cmp     eax, 7
0x1800bcf9e  jnz     loc_1800BD06F
0x1800bcfa4  mov     rax, [rdi]
0x1800bcfa7  mov     rdx, r12
0x1800bcfaa  mov     rcx, rdi
0x1800bcfad  mov     rax, [rax+38h]
0x1800bcfb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcfb6  mov     ebx, eax
0x1800bcfb8  test    eax, eax
0x1800bcfba  jnz     loc_1800BD06F
0x1800bcfc0  mov     rax, [rdi+150h]
0x1800bcfc7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800bcfce  jnz     short loc_1800BCFE4
0x1800bcfd0  mov     rax, [rdi+158h]
0x1800bcfd7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800bcfde  jz      loc_1800BD06F
0x1800bcfe4  mov     rdx, r12
0x1800bcfe7  mov     rcx, rdi
0x1800bcfea  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800bcfef  mov     ebx, eax
0x1800bcff1  test    eax, eax
0x1800bcff3  jnz     short loc_1800BD06F
0x1800bcff5  mov     rcx, r14; pwk
0x1800bcff8  call    cs:__imp_SubmitThreadpoolWork
0x1800bcffe  jmp     loc_1800BD0B1
0x1800bd003  mov     rax, [rdi]
0x1800bd006  mov     r8, r13
0x1800bd009  mov     rdx, [rsi+8]
0x1800bd00d  mov     rcx, rdi
0x1800bd010  mov     rax, [rax+10h]
0x1800bd014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd019  mov     rax, [rdi]
0x1800bd01c  mov     rdx, r12
0x1800bd01f  mov     rcx, rdi
0x1800bd022  mov     rax, [rax+30h]
0x1800bd026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd02b  mov     ebx, eax
0x1800bd02d  test    eax, eax
0x1800bd02f  jz      short loc_1800BD036
0x1800bd031  cmp     eax, 7
0x1800bd034  jnz     short loc_1800BD06F
0x1800bd036  mov     rax, [rdi]
0x1800bd039  mov     rdx, r12
0x1800bd03c  mov     rcx, rdi
0x1800bd03f  mov     rax, [rax+28h]
0x1800bd043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd048  mov     ebx, eax
0x1800bd04a  test    eax, eax
0x1800bd04c  jz      short loc_1800BD053
0x1800bd04e  cmp     eax, 7
0x1800bd051  jnz     short loc_1800BD06F
0x1800bd053  mov     rax, [rdi]
0x1800bd056  mov     rdx, r12
0x1800bd059  mov     rcx, rdi
0x1800bd05c  mov     rax, [rax+38h]
0x1800bd060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd065  jmp     loc_1800BCF32
0x1800bd06a  mov     ebx, 4
0x1800bd06f  mov     rax, [rdi]
0x1800bd072  mov     edx, 1
0x1800bd077  mov     rcx, rdi
0x1800bd07a  mov     rax, [rax]
0x1800bd07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd082  test    r15, r15
0x1800bd085  jz      short loc_1800BD094
0x1800bd087  mov     edx, 10h
0x1800bd08c  mov     rcx, r15; Block
0x1800bd08f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bd094  mov     rcx, [rbp+TokenHandle]; hObject
0x1800bd098  test    rcx, rcx
0x1800bd09b  jz      short loc_1800BD0A3
0x1800bd09d  call    cs:__imp_CloseHandle
0x1800bd0a3  test    r14, r14
0x1800bd0a6  jz      short loc_1800BD0B1
0x1800bd0a8  mov     rcx, r14; pwk
0x1800bd0ab  call    cs:__imp_CloseThreadpoolWork
0x1800bd0b1  mov     eax, ebx
0x1800bd0b3  mov     rcx, [rbp+var_8]
0x1800bd0b7  xor     rcx, rsp; StackCookie
0x1800bd0ba  call    __security_check_cookie
0x1800bd0bf  mov     rbx, [rsp+80h+arg_18]
0x1800bd0c7  add     rsp, 80h
0x1800bd0ce  pop     r15
0x1800bd0d0  pop     r14
0x1800bd0d2  pop     r13
0x1800bd0d4  pop     r12
0x1800bd0d6  pop     rdi
0x1800bd0d7  pop     rsi
0x1800bd0d8  pop     rbp
0x1800bd0d9  retn
```
