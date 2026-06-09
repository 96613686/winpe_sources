# CSpWmiMethod<_SPACES_VirtualDisk_DeleteObject>::RunMethod<CSpVirtualDisk::DeleteObject,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800ddb6c`
- end: `0x1800ddeba`
- name: `??$RunMethod@VDeleteObject@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_DeleteObject@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800e4700`

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
- `0x1800ddb6c`
- `0x1800e07f4`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddd38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ddd38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ddd19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ddd19`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ddd2e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800ddd2e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ddcff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800ddcff`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dddd8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dddd8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dde8b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800dde8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dde7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dde7d`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_DeleteObject>::RunMethod<CSpVirtualDisk::DeleteObject,16>(
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
  CSpVirtualDisk::DeleteObject *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::DeleteObject *)operator new(0x168u);
  v7 = CSpVirtualDisk::DeleteObject::DeleteObject(v25);
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
      v25 = (CSpVirtualDisk::DeleteObject *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_1803336A1,
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
0x1800ddb6c  mov     [rsp-38h+arg_18], rbx
0x1800ddb71  push    rbp
0x1800ddb72  push    rsi
0x1800ddb73  push    rdi
0x1800ddb74  push    r12
0x1800ddb76  push    r13
0x1800ddb78  push    r14
0x1800ddb7a  push    r15
0x1800ddb7c  mov     rbp, rsp
0x1800ddb7f  sub     rsp, 80h
0x1800ddb86  mov     rax, cs:__security_cookie
0x1800ddb8d  xor     rax, rsp
0x1800ddb90  mov     [rbp+var_8], rax
0x1800ddb94  xor     eax, eax
0x1800ddb96  mov     rsi, rcx
0x1800ddb99  xorps   xmm0, xmm0
0x1800ddb9c  mov     [rbp+var_10], eax
0x1800ddb9f  mov     ecx, 168h; Size
0x1800ddba4  mov     [rbp+var_40], eax
0x1800ddba7  movups  [rbp+var_20], xmm0
0x1800ddbab  mov     [rbp+TokenHandle], rax
0x1800ddbaf  mov     r12, r8
0x1800ddbb2  mov     r13, rdx
0x1800ddbb5  xor     r14d, r14d
0x1800ddbb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ddbbd  mov     rcx, rax; this
0x1800ddbc0  mov     [rbp+var_28], rax
0x1800ddbc4  call    ??0DeleteObject@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::DeleteObject::DeleteObject(void)
0x1800ddbc9  mov     rdi, rax
0x1800ddbcc  test    rax, rax
0x1800ddbcf  jnz     short loc_1800DDBD9
0x1800ddbd1  lea     ebx, [rax+1Bh]
0x1800ddbd4  jmp     loc_1800DDE74
0x1800ddbd9  mov     rax, [rax]
0x1800ddbdc  mov     rdx, rsi
0x1800ddbdf  mov     rcx, rdi
0x1800ddbe2  xor     r15d, r15d
0x1800ddbe5  mov     rax, [rax+8]
0x1800ddbe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddbee  lea     rcx, [rbp+var_40]
0x1800ddbf2  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800ddbf7  mov     [rdi+1Ch], eax
0x1800ddbfa  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800ddbfe  mov     ecx, [rsi+14h]; unsigned int
0x1800ddc01  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800ddc06  mov     eax, cs:dword_180397B68
0x1800ddc0c  cmp     eax, 5
0x1800ddc0f  jbe     short loc_1800DDC7F
0x1800ddc11  mov     rdx, 400000000000h
0x1800ddc1b  lea     rcx, dword_180397B68
0x1800ddc22  call    _tlgKeywordOn
0x1800ddc27  test    al, al
0x1800ddc29  jz      short loc_1800DDC7F
0x1800ddc2b  mov     eax, [rbp+var_40]
0x1800ddc2e  lea     rdx, byte_1803336A1
0x1800ddc35  xor     ecx, ecx
0x1800ddc37  cmp     [rdi+1Ch], eax
0x1800ddc3a  movzx   eax, word ptr [rbp+var_10]
0x1800ddc3e  mov     word ptr [rbp+var_40], ax
0x1800ddc42  setnz   cl
0x1800ddc45  mov     eax, [rsi+14h]
0x1800ddc48  mov     [rbp+var_38], eax
0x1800ddc4b  lea     rax, [rbp+var_20]
0x1800ddc4f  mov     [rbp+var_28], rax
0x1800ddc53  lea     rax, [rbp+var_3C]
0x1800ddc57  mov     [rsp+80h+var_48], rax
0x1800ddc5c  lea     rax, [rbp+var_40]
0x1800ddc60  mov     [rsp+80h+var_50], rax
0x1800ddc65  lea     rax, [rbp+var_38]
0x1800ddc69  mov     [rsp+80h+var_58], rax
0x1800ddc6e  lea     rax, [rbp+var_28]
0x1800ddc72  mov     [rsp+80h+var_60], rax
0x1800ddc77  mov     [rbp+var_3C], ecx
0x1800ddc7a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800ddc7f  mov     rcx, [rsi]
0x1800ddc82  test    rcx, rcx
0x1800ddc85  jz      loc_1800DDE4A
0x1800ddc8b  mov     rax, [rcx]
0x1800ddc8e  test    rax, rax
0x1800ddc91  jz      loc_1800DDE4A
0x1800ddc97  mov     rax, [rax+18h]
0x1800ddc9b  lea     r8, [rdi+20h]
0x1800ddc9f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800ddca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddcab  mov     ebx, eax
0x1800ddcad  test    eax, eax
0x1800ddcaf  jnz     loc_1800DDE4F
0x1800ddcb5  cmp     [rsi+10h], r14d
0x1800ddcb9  jz      loc_1800DDDE3
0x1800ddcbf  lea     rbx, [rdi+148h]
0x1800ddcc6  mov     rcx, rbx
0x1800ddcc9  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800ddcce  mov     rcx, rbx; struct CSpJobMgr **
0x1800ddcd1  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800ddcd6  test    eax, eax
0x1800ddcd8  jnz     short loc_1800DDCE2
0x1800ddcda  lea     ebx, [rax+1Ch]
0x1800ddcdd  jmp     loc_1800DDE4F
0x1800ddce2  mov     ecx, 10h; Size
0x1800ddce7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ddcec  xor     r8d, r8d; pcbe
0x1800ddcef  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800ddcf6  mov     rdx, rax; pv
0x1800ddcf9  mov     r15, rax
0x1800ddcfc  mov     [rax], rdi
0x1800ddcff  call    cs:__imp_CreateThreadpoolWork
0x1800ddd05  mov     r14, rax
0x1800ddd08  test    rax, rax
0x1800ddd0b  jnz     short loc_1800DDD19
0x1800ddd0d  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800ddd12  mov     ebx, eax
0x1800ddd14  jmp     loc_1800DDE4F
0x1800ddd19  call    cs:__imp_GetCurrentThread
0x1800ddd1f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800ddd23  xor     r8d, r8d; OpenAsSelf
0x1800ddd26  mov     rcx, rax; ThreadHandle
0x1800ddd29  mov     edx, 2000Ch; DesiredAccess
0x1800ddd2e  call    cs:__imp_OpenThreadToken
0x1800ddd34  test    eax, eax
0x1800ddd36  jnz     short loc_1800DDD45
0x1800ddd38  call    cs:__imp_GetLastError
0x1800ddd3e  cmp     eax, 3F0h
0x1800ddd43  jnz     short loc_1800DDD0D
0x1800ddd45  mov     rax, [rbp+TokenHandle]
0x1800ddd49  mov     r8, r13
0x1800ddd4c  mov     [r15+8], rax
0x1800ddd50  mov     rcx, rdi
0x1800ddd53  mov     rax, [rdi]
0x1800ddd56  mov     rdx, [rsi+8]
0x1800ddd5a  mov     rax, [rax+18h]
0x1800ddd5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddd63  mov     rax, [rdi]
0x1800ddd66  mov     rdx, r12
0x1800ddd69  mov     rcx, rdi
0x1800ddd6c  mov     rax, [rax+28h]
0x1800ddd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddd75  mov     ebx, eax
0x1800ddd77  test    eax, eax
0x1800ddd79  jz      short loc_1800DDD84
0x1800ddd7b  cmp     eax, 7
0x1800ddd7e  jnz     loc_1800DDE4F
0x1800ddd84  mov     rax, [rdi]
0x1800ddd87  mov     rdx, r12
0x1800ddd8a  mov     rcx, rdi
0x1800ddd8d  mov     rax, [rax+38h]
0x1800ddd91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ddd96  mov     ebx, eax
0x1800ddd98  test    eax, eax
0x1800ddd9a  jnz     loc_1800DDE4F
0x1800ddda0  mov     rax, [rdi+150h]
0x1800ddda7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800dddae  jnz     short loc_1800DDDC4
0x1800dddb0  mov     rax, [rdi+158h]
0x1800dddb7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800dddbe  jz      loc_1800DDE4F
0x1800dddc4  mov     rdx, r12
0x1800dddc7  mov     rcx, rdi
0x1800dddca  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800dddcf  mov     ebx, eax
0x1800dddd1  test    eax, eax
0x1800dddd3  jnz     short loc_1800DDE4F
0x1800dddd5  mov     rcx, r14; pwk
0x1800dddd8  call    cs:__imp_SubmitThreadpoolWork
0x1800dddde  jmp     loc_1800DDE91
0x1800ddde3  mov     rax, [rdi]
0x1800ddde6  mov     r8, r13
0x1800ddde9  mov     rdx, [rsi+8]
0x1800ddded  mov     rcx, rdi
0x1800dddf0  mov     rax, [rax+10h]
0x1800dddf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dddf9  mov     rax, [rdi]
0x1800dddfc  mov     rdx, r12
0x1800dddff  mov     rcx, rdi
0x1800dde02  mov     rax, [rax+30h]
0x1800dde06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde0b  mov     ebx, eax
0x1800dde0d  test    eax, eax
0x1800dde0f  jz      short loc_1800DDE16
0x1800dde11  cmp     eax, 7
0x1800dde14  jnz     short loc_1800DDE4F
0x1800dde16  mov     rax, [rdi]
0x1800dde19  mov     rdx, r12
0x1800dde1c  mov     rcx, rdi
0x1800dde1f  mov     rax, [rax+28h]
0x1800dde23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde28  mov     ebx, eax
0x1800dde2a  test    eax, eax
0x1800dde2c  jz      short loc_1800DDE33
0x1800dde2e  cmp     eax, 7
0x1800dde31  jnz     short loc_1800DDE4F
0x1800dde33  mov     rax, [rdi]
0x1800dde36  mov     rdx, r12
0x1800dde39  mov     rcx, rdi
0x1800dde3c  mov     rax, [rax+38h]
0x1800dde40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde45  jmp     loc_1800DDD12
0x1800dde4a  mov     ebx, 4
0x1800dde4f  mov     rax, [rdi]
0x1800dde52  mov     edx, 1
0x1800dde57  mov     rcx, rdi
0x1800dde5a  mov     rax, [rax]
0x1800dde5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dde62  test    r15, r15
0x1800dde65  jz      short loc_1800DDE74
0x1800dde67  mov     edx, 10h
0x1800dde6c  mov     rcx, r15; Block
0x1800dde6f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800dde74  mov     rcx, [rbp+TokenHandle]; hObject
0x1800dde78  test    rcx, rcx
0x1800dde7b  jz      short loc_1800DDE83
0x1800dde7d  call    cs:__imp_CloseHandle
0x1800dde83  test    r14, r14
0x1800dde86  jz      short loc_1800DDE91
0x1800dde88  mov     rcx, r14; pwk
0x1800dde8b  call    cs:__imp_CloseThreadpoolWork
0x1800dde91  mov     eax, ebx
0x1800dde93  mov     rcx, [rbp+var_8]
0x1800dde97  xor     rcx, rsp; StackCookie
0x1800dde9a  call    __security_check_cookie
0x1800dde9f  mov     rbx, [rsp+80h+arg_18]
0x1800ddea7  add     rsp, 80h
0x1800ddeae  pop     r15
0x1800ddeb0  pop     r14
0x1800ddeb2  pop     r13
0x1800ddeb4  pop     r12
0x1800ddeb6  pop     rdi
0x1800ddeb7  pop     rsi
0x1800ddeb8  pop     rbp
0x1800ddeb9  retn
```
