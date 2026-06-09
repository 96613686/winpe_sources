# CSpWmiMethod<_SPACES_StorageEnclosure_GetVendorData>::RunMethod<CSpStorageEnclosure::GetVendorData,8>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800d6028`
- end: `0x1800d6376`
- name: `??$RunMethod@VGetVendorData@CSpStorageEnclosure@@$07@?$CSpWmiMethod@U_SPACES_StorageEnclosure_GetVendorData@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800d8f20`

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
- `0x1800d6028`
- `0x1800d7144`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d61f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d61f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d61d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d61d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d61ea`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d61ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d61bb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800d61bb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6294`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6294`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d6347`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800d6347`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6339`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d6339`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_StorageEnclosure_GetVendorData>::RunMethod<CSpStorageEnclosure::GetVendorData,8>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 VendorData; // rax
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
  CSpStorageEnclosure::GetVendorData *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpStorageEnclosure::GetVendorData *)operator new(0x168u);
  VendorData = CSpStorageEnclosure::GetVendorData::GetVendorData(v25);
  v8 = VendorData;
  if ( VendorData )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)VendorData + 8LL))(VendorData, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpStorageEnclosure::GetVendorData *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&dword_18032F234,
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
0x1800d6028  mov     [rsp-38h+arg_18], rbx
0x1800d602d  push    rbp
0x1800d602e  push    rsi
0x1800d602f  push    rdi
0x1800d6030  push    r12
0x1800d6032  push    r13
0x1800d6034  push    r14
0x1800d6036  push    r15
0x1800d6038  mov     rbp, rsp
0x1800d603b  sub     rsp, 80h
0x1800d6042  mov     rax, cs:__security_cookie
0x1800d6049  xor     rax, rsp
0x1800d604c  mov     [rbp+var_8], rax
0x1800d6050  xor     eax, eax
0x1800d6052  mov     rsi, rcx
0x1800d6055  xorps   xmm0, xmm0
0x1800d6058  mov     [rbp+var_10], eax
0x1800d605b  mov     ecx, 168h; Size
0x1800d6060  mov     [rbp+var_40], eax
0x1800d6063  movups  [rbp+var_20], xmm0
0x1800d6067  mov     [rbp+TokenHandle], rax
0x1800d606b  mov     r12, r8
0x1800d606e  mov     r13, rdx
0x1800d6071  xor     r14d, r14d
0x1800d6074  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d6079  mov     rcx, rax; this
0x1800d607c  mov     [rbp+var_28], rax
0x1800d6080  call    ??0GetVendorData@CSpStorageEnclosure@@QEAA@XZ; CSpStorageEnclosure::GetVendorData::GetVendorData(void)
0x1800d6085  mov     rdi, rax
0x1800d6088  test    rax, rax
0x1800d608b  jnz     short loc_1800D6095
0x1800d608d  lea     ebx, [rax+1Bh]
0x1800d6090  jmp     loc_1800D6330
0x1800d6095  mov     rax, [rax]
0x1800d6098  mov     rdx, rsi
0x1800d609b  mov     rcx, rdi
0x1800d609e  xor     r15d, r15d
0x1800d60a1  mov     rax, [rax+8]
0x1800d60a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d60aa  lea     rcx, [rbp+var_40]
0x1800d60ae  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800d60b3  mov     [rdi+1Ch], eax
0x1800d60b6  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800d60ba  mov     ecx, [rsi+14h]; unsigned int
0x1800d60bd  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800d60c2  mov     eax, cs:dword_180397B68
0x1800d60c8  cmp     eax, 5
0x1800d60cb  jbe     short loc_1800D613B
0x1800d60cd  mov     rdx, 400000000000h
0x1800d60d7  lea     rcx, dword_180397B68
0x1800d60de  call    _tlgKeywordOn
0x1800d60e3  test    al, al
0x1800d60e5  jz      short loc_1800D613B
0x1800d60e7  mov     eax, [rbp+var_40]
0x1800d60ea  lea     rdx, dword_18032F234
0x1800d60f1  xor     ecx, ecx
0x1800d60f3  cmp     [rdi+1Ch], eax
0x1800d60f6  movzx   eax, word ptr [rbp+var_10]
0x1800d60fa  mov     word ptr [rbp+var_40], ax
0x1800d60fe  setnz   cl
0x1800d6101  mov     eax, [rsi+14h]
0x1800d6104  mov     [rbp+var_38], eax
0x1800d6107  lea     rax, [rbp+var_20]
0x1800d610b  mov     [rbp+var_28], rax
0x1800d610f  lea     rax, [rbp+var_3C]
0x1800d6113  mov     [rsp+80h+var_48], rax
0x1800d6118  lea     rax, [rbp+var_40]
0x1800d611c  mov     [rsp+80h+var_50], rax
0x1800d6121  lea     rax, [rbp+var_38]
0x1800d6125  mov     [rsp+80h+var_58], rax
0x1800d612a  lea     rax, [rbp+var_28]
0x1800d612e  mov     [rsp+80h+var_60], rax
0x1800d6133  mov     [rbp+var_3C], ecx
0x1800d6136  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800d613b  mov     rcx, [rsi]
0x1800d613e  test    rcx, rcx
0x1800d6141  jz      loc_1800D6306
0x1800d6147  mov     rax, [rcx]
0x1800d614a  test    rax, rax
0x1800d614d  jz      loc_1800D6306
0x1800d6153  mov     rax, [rax+18h]
0x1800d6157  lea     r8, [rdi+20h]
0x1800d615b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800d6162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6167  mov     ebx, eax
0x1800d6169  test    eax, eax
0x1800d616b  jnz     loc_1800D630B
0x1800d6171  cmp     [rsi+10h], r14d
0x1800d6175  jz      loc_1800D629F
0x1800d617b  lea     rbx, [rdi+148h]
0x1800d6182  mov     rcx, rbx
0x1800d6185  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800d618a  mov     rcx, rbx; struct CSpJobMgr **
0x1800d618d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800d6192  test    eax, eax
0x1800d6194  jnz     short loc_1800D619E
0x1800d6196  lea     ebx, [rax+1Ch]
0x1800d6199  jmp     loc_1800D630B
0x1800d619e  mov     ecx, 10h; Size
0x1800d61a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d61a8  xor     r8d, r8d; pcbe
0x1800d61ab  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800d61b2  mov     rdx, rax; pv
0x1800d61b5  mov     r15, rax
0x1800d61b8  mov     [rax], rdi
0x1800d61bb  call    cs:__imp_CreateThreadpoolWork
0x1800d61c1  mov     r14, rax
0x1800d61c4  test    rax, rax
0x1800d61c7  jnz     short loc_1800D61D5
0x1800d61c9  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800d61ce  mov     ebx, eax
0x1800d61d0  jmp     loc_1800D630B
0x1800d61d5  call    cs:__imp_GetCurrentThread
0x1800d61db  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800d61df  xor     r8d, r8d; OpenAsSelf
0x1800d61e2  mov     rcx, rax; ThreadHandle
0x1800d61e5  mov     edx, 2000Ch; DesiredAccess
0x1800d61ea  call    cs:__imp_OpenThreadToken
0x1800d61f0  test    eax, eax
0x1800d61f2  jnz     short loc_1800D6201
0x1800d61f4  call    cs:__imp_GetLastError
0x1800d61fa  cmp     eax, 3F0h
0x1800d61ff  jnz     short loc_1800D61C9
0x1800d6201  mov     rax, [rbp+TokenHandle]
0x1800d6205  mov     r8, r13
0x1800d6208  mov     [r15+8], rax
0x1800d620c  mov     rcx, rdi
0x1800d620f  mov     rax, [rdi]
0x1800d6212  mov     rdx, [rsi+8]
0x1800d6216  mov     rax, [rax+18h]
0x1800d621a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d621f  mov     rax, [rdi]
0x1800d6222  mov     rdx, r12
0x1800d6225  mov     rcx, rdi
0x1800d6228  mov     rax, [rax+28h]
0x1800d622c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6231  mov     ebx, eax
0x1800d6233  test    eax, eax
0x1800d6235  jz      short loc_1800D6240
0x1800d6237  cmp     eax, 7
0x1800d623a  jnz     loc_1800D630B
0x1800d6240  mov     rax, [rdi]
0x1800d6243  mov     rdx, r12
0x1800d6246  mov     rcx, rdi
0x1800d6249  mov     rax, [rax+38h]
0x1800d624d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6252  mov     ebx, eax
0x1800d6254  test    eax, eax
0x1800d6256  jnz     loc_1800D630B
0x1800d625c  mov     rax, [rdi+150h]
0x1800d6263  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800d626a  jnz     short loc_1800D6280
0x1800d626c  mov     rax, [rdi+158h]
0x1800d6273  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800d627a  jz      loc_1800D630B
0x1800d6280  mov     rdx, r12
0x1800d6283  mov     rcx, rdi
0x1800d6286  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800d628b  mov     ebx, eax
0x1800d628d  test    eax, eax
0x1800d628f  jnz     short loc_1800D630B
0x1800d6291  mov     rcx, r14; pwk
0x1800d6294  call    cs:__imp_SubmitThreadpoolWork
0x1800d629a  jmp     loc_1800D634D
0x1800d629f  mov     rax, [rdi]
0x1800d62a2  mov     r8, r13
0x1800d62a5  mov     rdx, [rsi+8]
0x1800d62a9  mov     rcx, rdi
0x1800d62ac  mov     rax, [rax+10h]
0x1800d62b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d62b5  mov     rax, [rdi]
0x1800d62b8  mov     rdx, r12
0x1800d62bb  mov     rcx, rdi
0x1800d62be  mov     rax, [rax+30h]
0x1800d62c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d62c7  mov     ebx, eax
0x1800d62c9  test    eax, eax
0x1800d62cb  jz      short loc_1800D62D2
0x1800d62cd  cmp     eax, 7
0x1800d62d0  jnz     short loc_1800D630B
0x1800d62d2  mov     rax, [rdi]
0x1800d62d5  mov     rdx, r12
0x1800d62d8  mov     rcx, rdi
0x1800d62db  mov     rax, [rax+28h]
0x1800d62df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d62e4  mov     ebx, eax
0x1800d62e6  test    eax, eax
0x1800d62e8  jz      short loc_1800D62EF
0x1800d62ea  cmp     eax, 7
0x1800d62ed  jnz     short loc_1800D630B
0x1800d62ef  mov     rax, [rdi]
0x1800d62f2  mov     rdx, r12
0x1800d62f5  mov     rcx, rdi
0x1800d62f8  mov     rax, [rax+38h]
0x1800d62fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6301  jmp     loc_1800D61CE
0x1800d6306  mov     ebx, 4
0x1800d630b  mov     rax, [rdi]
0x1800d630e  mov     edx, 1
0x1800d6313  mov     rcx, rdi
0x1800d6316  mov     rax, [rax]
0x1800d6319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d631e  test    r15, r15
0x1800d6321  jz      short loc_1800D6330
0x1800d6323  mov     edx, 10h
0x1800d6328  mov     rcx, r15; Block
0x1800d632b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d6330  mov     rcx, [rbp+TokenHandle]; hObject
0x1800d6334  test    rcx, rcx
0x1800d6337  jz      short loc_1800D633F
0x1800d6339  call    cs:__imp_CloseHandle
0x1800d633f  test    r14, r14
0x1800d6342  jz      short loc_1800D634D
0x1800d6344  mov     rcx, r14; pwk
0x1800d6347  call    cs:__imp_CloseThreadpoolWork
0x1800d634d  mov     eax, ebx
0x1800d634f  mov     rcx, [rbp+var_8]
0x1800d6353  xor     rcx, rsp; StackCookie
0x1800d6356  call    __security_check_cookie
0x1800d635b  mov     rbx, [rsp+80h+arg_18]
0x1800d6363  add     rsp, 80h
0x1800d636a  pop     r15
0x1800d636c  pop     r14
0x1800d636e  pop     r13
0x1800d6370  pop     r12
0x1800d6372  pop     rdi
0x1800d6373  pop     rsi
0x1800d6374  pop     rbp
0x1800d6375  retn
```
