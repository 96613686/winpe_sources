# CSpWmiMethod<_SPACES_VirtualDisk_DeleteObject>::RunMethod<CSpVirtualDisk::DeleteObject,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e0edc`
- end: `0x1800e1259`
- name: `??$RunMethod@VDeleteObject@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_DeleteObject@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800e0edc`
- `0x1800e3de0`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e10ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e108f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e108f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e10aa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e10aa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e106f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e106f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e1164`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e1164`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e1223`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e1223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e120f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e120f`

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
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpVirtualDisk::DeleteObject *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&word_18033A656,
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
0x1800e0edc  mov     [rsp-38h+arg_18], rbx
0x1800e0ee1  push    rbp
0x1800e0ee2  push    rsi
0x1800e0ee3  push    rdi
0x1800e0ee4  push    r12
0x1800e0ee6  push    r13
0x1800e0ee8  push    r14
0x1800e0eea  push    r15
0x1800e0eec  mov     rbp, rsp
0x1800e0eef  sub     rsp, 80h
0x1800e0ef6  mov     rax, cs:__security_cookie
0x1800e0efd  xor     rax, rsp
0x1800e0f00  mov     [rbp+var_8], rax
0x1800e0f04  xor     eax, eax
0x1800e0f06  mov     rsi, rcx
0x1800e0f09  xorps   xmm0, xmm0
0x1800e0f0c  mov     [rbp+var_10], eax
0x1800e0f0f  mov     ecx, 168h; Size
0x1800e0f14  mov     [rbp+var_40], eax
0x1800e0f17  movups  [rbp+var_20], xmm0
0x1800e0f1b  mov     [rbp+TokenHandle], rax
0x1800e0f1f  mov     r12, r8
0x1800e0f22  mov     r13, rdx
0x1800e0f25  xor     r14d, r14d
0x1800e0f28  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e0f2d  mov     rcx, rax; this
0x1800e0f30  mov     [rbp+var_28], rax
0x1800e0f34  call    ??0DeleteObject@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::DeleteObject::DeleteObject(void)
0x1800e0f39  mov     rdi, rax
0x1800e0f3c  test    rax, rax
0x1800e0f3f  jnz     short loc_1800E0F49
0x1800e0f41  lea     ebx, [rax+1Bh]
0x1800e0f44  jmp     loc_1800E1206
0x1800e0f49  mov     rax, [rax]
0x1800e0f4c  mov     rdx, rsi
0x1800e0f4f  mov     rcx, rdi
0x1800e0f52  xor     r15d, r15d
0x1800e0f55  mov     rax, [rax+8]
0x1800e0f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e0f5e  lea     rcx, [rbp+var_40]
0x1800e0f62  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e0f67  mov     [rdi+1Ch], eax
0x1800e0f6a  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e0f6e  mov     ecx, [rsi+14h]; unsigned int
0x1800e0f71  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e0f76  mov     eax, cs:dword_18039EB68
0x1800e0f7c  cmp     eax, 5
0x1800e0f7f  jbe     short loc_1800E0FEF
0x1800e0f81  mov     rdx, 400000000000h
0x1800e0f8b  lea     rcx, dword_18039EB68
0x1800e0f92  call    _tlgKeywordOn
0x1800e0f97  test    al, al
0x1800e0f99  jz      short loc_1800E0FEF
0x1800e0f9b  mov     eax, [rbp+var_40]
0x1800e0f9e  lea     rdx, word_18033A656
0x1800e0fa5  xor     ecx, ecx
0x1800e0fa7  cmp     [rdi+1Ch], eax
0x1800e0faa  movzx   eax, word ptr [rbp+var_10]
0x1800e0fae  mov     word ptr [rbp+var_40], ax
0x1800e0fb2  setnz   cl
0x1800e0fb5  mov     eax, [rsi+14h]
0x1800e0fb8  mov     [rbp+var_38], eax
0x1800e0fbb  lea     rax, [rbp+var_20]
0x1800e0fbf  mov     [rbp+var_28], rax
0x1800e0fc3  lea     rax, [rbp+var_3C]
0x1800e0fc7  mov     [rsp+80h+var_48], rax
0x1800e0fcc  lea     rax, [rbp+var_40]
0x1800e0fd0  mov     [rsp+80h+var_50], rax
0x1800e0fd5  lea     rax, [rbp+var_38]
0x1800e0fd9  mov     [rsp+80h+var_58], rax
0x1800e0fde  lea     rax, [rbp+var_28]
0x1800e0fe2  mov     [rsp+80h+var_60], rax
0x1800e0fe7  mov     [rbp+var_3C], ecx
0x1800e0fea  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e0fef  mov     rcx, [rsi]
0x1800e0ff2  test    rcx, rcx
0x1800e0ff5  jz      loc_1800E11DC
0x1800e0ffb  mov     rax, [rcx]
0x1800e0ffe  test    rax, rax
0x1800e1001  jz      loc_1800E11DC
0x1800e1007  mov     rax, [rax+18h]
0x1800e100b  lea     r8, [rdi+20h]
0x1800e100f  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e1016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e101b  mov     ebx, eax
0x1800e101d  test    eax, eax
0x1800e101f  jnz     loc_1800E11E1
0x1800e1025  cmp     [rsi+10h], r14d
0x1800e1029  jz      loc_1800E1175
0x1800e102f  lea     rbx, [rdi+148h]
0x1800e1036  mov     rcx, rbx
0x1800e1039  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e103e  mov     rcx, rbx; struct CSpJobMgr **
0x1800e1041  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e1046  test    eax, eax
0x1800e1048  jnz     short loc_1800E1052
0x1800e104a  lea     ebx, [rax+1Ch]
0x1800e104d  jmp     loc_1800E11E1
0x1800e1052  mov     ecx, 10h; Size
0x1800e1057  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e105c  xor     r8d, r8d; pcbe
0x1800e105f  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e1066  mov     rdx, rax; pv
0x1800e1069  mov     r15, rax
0x1800e106c  mov     [rax], rdi
0x1800e106f  call    cs:__imp_CreateThreadpoolWork
0x1800e1076  nop     dword ptr [rax+rax+00h]
0x1800e107b  mov     r14, rax
0x1800e107e  test    rax, rax
0x1800e1081  jnz     short loc_1800E108F
0x1800e1083  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e1088  mov     ebx, eax
0x1800e108a  jmp     loc_1800E11E1
0x1800e108f  call    cs:__imp_GetCurrentThread
0x1800e1096  nop     dword ptr [rax+rax+00h]
0x1800e109b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e109f  xor     r8d, r8d; OpenAsSelf
0x1800e10a2  mov     rcx, rax; ThreadHandle
0x1800e10a5  mov     edx, 2000Ch; DesiredAccess
0x1800e10aa  call    cs:__imp_OpenThreadToken
0x1800e10b1  nop     dword ptr [rax+rax+00h]
0x1800e10b6  test    eax, eax
0x1800e10b8  jnz     short loc_1800E10CD
0x1800e10ba  call    cs:__imp_GetLastError
0x1800e10c1  nop     dword ptr [rax+rax+00h]
0x1800e10c6  cmp     eax, 3F0h
0x1800e10cb  jnz     short loc_1800E1083
0x1800e10cd  mov     rax, [rbp+TokenHandle]
0x1800e10d1  mov     r8, r13
0x1800e10d4  mov     [r15+8], rax
0x1800e10d8  mov     rcx, rdi
0x1800e10db  mov     rax, [rdi]
0x1800e10de  mov     rdx, [rsi+8]
0x1800e10e2  mov     rax, [rax+18h]
0x1800e10e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e10eb  mov     rax, [rdi]
0x1800e10ee  mov     rdx, r12
0x1800e10f1  mov     rcx, rdi
0x1800e10f4  mov     rax, [rax+28h]
0x1800e10f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e10fd  mov     ebx, eax
0x1800e10ff  test    eax, eax
0x1800e1101  jz      short loc_1800E110C
0x1800e1103  cmp     eax, 7
0x1800e1106  jnz     loc_1800E11E1
0x1800e110c  mov     rax, [rdi]
0x1800e110f  mov     rdx, r12
0x1800e1112  mov     rcx, rdi
0x1800e1115  mov     rax, [rax+38h]
0x1800e1119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e111e  mov     ebx, eax
0x1800e1120  test    eax, eax
0x1800e1122  jnz     loc_1800E11E1
0x1800e1128  mov     rax, [rdi+150h]
0x1800e112f  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e1136  jnz     short loc_1800E114C
0x1800e1138  mov     rax, [rdi+158h]
0x1800e113f  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e1146  jz      loc_1800E11E1
0x1800e114c  mov     rdx, r12
0x1800e114f  mov     rcx, rdi
0x1800e1152  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e1157  mov     ebx, eax
0x1800e1159  test    eax, eax
0x1800e115b  jnz     loc_1800E11E1
0x1800e1161  mov     rcx, r14; pwk
0x1800e1164  call    cs:__imp_SubmitThreadpoolWork
0x1800e116b  nop     dword ptr [rax+rax+00h]
0x1800e1170  jmp     loc_1800E122F
0x1800e1175  mov     rax, [rdi]
0x1800e1178  mov     r8, r13
0x1800e117b  mov     rdx, [rsi+8]
0x1800e117f  mov     rcx, rdi
0x1800e1182  mov     rax, [rax+10h]
0x1800e1186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e118b  mov     rax, [rdi]
0x1800e118e  mov     rdx, r12
0x1800e1191  mov     rcx, rdi
0x1800e1194  mov     rax, [rax+30h]
0x1800e1198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e119d  mov     ebx, eax
0x1800e119f  test    eax, eax
0x1800e11a1  jz      short loc_1800E11A8
0x1800e11a3  cmp     eax, 7
0x1800e11a6  jnz     short loc_1800E11E1
0x1800e11a8  mov     rax, [rdi]
0x1800e11ab  mov     rdx, r12
0x1800e11ae  mov     rcx, rdi
0x1800e11b1  mov     rax, [rax+28h]
0x1800e11b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e11ba  mov     ebx, eax
0x1800e11bc  test    eax, eax
0x1800e11be  jz      short loc_1800E11C5
0x1800e11c0  cmp     eax, 7
0x1800e11c3  jnz     short loc_1800E11E1
0x1800e11c5  mov     rax, [rdi]
0x1800e11c8  mov     rdx, r12
0x1800e11cb  mov     rcx, rdi
0x1800e11ce  mov     rax, [rax+38h]
0x1800e11d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e11d7  jmp     loc_1800E1088
0x1800e11dc  mov     ebx, 4
0x1800e11e1  mov     rax, [rdi]
0x1800e11e4  mov     edx, 1
0x1800e11e9  mov     rcx, rdi
0x1800e11ec  mov     rax, [rax]
0x1800e11ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e11f4  test    r15, r15
0x1800e11f7  jz      short loc_1800E1206
0x1800e11f9  mov     edx, 10h
0x1800e11fe  mov     rcx, r15; Block
0x1800e1201  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e1206  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e120a  test    rcx, rcx
0x1800e120d  jz      short loc_1800E121B
0x1800e120f  call    cs:__imp_CloseHandle
0x1800e1216  nop     dword ptr [rax+rax+00h]
0x1800e121b  test    r14, r14
0x1800e121e  jz      short loc_1800E122F
0x1800e1220  mov     rcx, r14; pwk
0x1800e1223  call    cs:__imp_CloseThreadpoolWork
0x1800e122a  nop     dword ptr [rax+rax+00h]
0x1800e122f  mov     eax, ebx
0x1800e1231  mov     rcx, [rbp+var_8]
0x1800e1235  xor     rcx, rsp; StackCookie
0x1800e1238  call    __security_check_cookie
0x1800e123d  mov     rbx, [rsp+80h+arg_18]
0x1800e1245  add     rsp, 80h
0x1800e124c  pop     r15
0x1800e124e  pop     r14
0x1800e1250  pop     r13
0x1800e1252  pop     r12
0x1800e1254  pop     rdi
0x1800e1255  pop     rsi
0x1800e1256  pop     rbp
0x1800e1257  retn
```
