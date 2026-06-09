# CSpWmiMethod<_SPACES_PhysicalDisk_Convert>::RunMethod<CSpPhysicalDisk::Convert,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f0fd0`
- end: `0x1800f134d`
- name: `??$RunMethod@VConvert@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_Convert@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
- size: `893`
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
- `0x1800f0fd0`
- `0x1800f3a18`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f11ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f11ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f1183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f1183`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f119e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f119e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f1163`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f1163`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f1258`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f1258`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f1317`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f1317`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1303`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1303`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_Convert>::RunMethod<CSpPhysicalDisk::Convert,4>(
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
  CSpPhysicalDisk::Convert *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::Convert *)operator new(0x1D0u);
  v7 = CSpPhysicalDisk::Convert::Convert(v25);
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
      v25 = (CSpPhysicalDisk::Convert *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)&unk_18033C680,
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
0x1800f0fd0  mov     [rsp-38h+arg_18], rbx
0x1800f0fd5  push    rbp
0x1800f0fd6  push    rsi
0x1800f0fd7  push    rdi
0x1800f0fd8  push    r12
0x1800f0fda  push    r13
0x1800f0fdc  push    r14
0x1800f0fde  push    r15
0x1800f0fe0  mov     rbp, rsp
0x1800f0fe3  sub     rsp, 80h
0x1800f0fea  mov     rax, cs:__security_cookie
0x1800f0ff1  xor     rax, rsp
0x1800f0ff4  mov     [rbp+var_8], rax
0x1800f0ff8  xor     eax, eax
0x1800f0ffa  mov     rsi, rcx
0x1800f0ffd  xorps   xmm0, xmm0
0x1800f1000  mov     [rbp+var_10], eax
0x1800f1003  mov     ecx, 1D0h; Size
0x1800f1008  mov     [rbp+var_40], eax
0x1800f100b  movups  [rbp+var_20], xmm0
0x1800f100f  mov     [rbp+TokenHandle], rax
0x1800f1013  mov     r12, r8
0x1800f1016  mov     r13, rdx
0x1800f1019  xor     r14d, r14d
0x1800f101c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f1021  mov     rcx, rax; this
0x1800f1024  mov     [rbp+var_28], rax
0x1800f1028  call    ??0Convert@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::Convert::Convert(void)
0x1800f102d  mov     rdi, rax
0x1800f1030  test    rax, rax
0x1800f1033  jnz     short loc_1800F103D
0x1800f1035  lea     ebx, [rax+1Bh]
0x1800f1038  jmp     loc_1800F12FA
0x1800f103d  mov     rax, [rax]
0x1800f1040  mov     rdx, rsi
0x1800f1043  mov     rcx, rdi
0x1800f1046  xor     r15d, r15d
0x1800f1049  mov     rax, [rax+8]
0x1800f104d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1052  lea     rcx, [rbp+var_40]
0x1800f1056  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f105b  mov     [rdi+1Ch], eax
0x1800f105e  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f1062  mov     ecx, [rsi+14h]; unsigned int
0x1800f1065  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f106a  mov     eax, cs:dword_18039EB68
0x1800f1070  cmp     eax, 5
0x1800f1073  jbe     short loc_1800F10E3
0x1800f1075  mov     rdx, 400000000000h
0x1800f107f  lea     rcx, dword_18039EB68
0x1800f1086  call    _tlgKeywordOn
0x1800f108b  test    al, al
0x1800f108d  jz      short loc_1800F10E3
0x1800f108f  mov     eax, [rbp+var_40]
0x1800f1092  lea     rdx, unk_18033C680
0x1800f1099  xor     ecx, ecx
0x1800f109b  cmp     [rdi+1Ch], eax
0x1800f109e  movzx   eax, word ptr [rbp+var_10]
0x1800f10a2  mov     word ptr [rbp+var_40], ax
0x1800f10a6  setnz   cl
0x1800f10a9  mov     eax, [rsi+14h]
0x1800f10ac  mov     [rbp+var_38], eax
0x1800f10af  lea     rax, [rbp+var_20]
0x1800f10b3  mov     [rbp+var_28], rax
0x1800f10b7  lea     rax, [rbp+var_3C]
0x1800f10bb  mov     [rsp+80h+var_48], rax
0x1800f10c0  lea     rax, [rbp+var_40]
0x1800f10c4  mov     [rsp+80h+var_50], rax
0x1800f10c9  lea     rax, [rbp+var_38]
0x1800f10cd  mov     [rsp+80h+var_58], rax
0x1800f10d2  lea     rax, [rbp+var_28]
0x1800f10d6  mov     [rsp+80h+var_60], rax
0x1800f10db  mov     [rbp+var_3C], ecx
0x1800f10de  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f10e3  mov     rcx, [rsi]
0x1800f10e6  test    rcx, rcx
0x1800f10e9  jz      loc_1800F12D0
0x1800f10ef  mov     rax, [rcx]
0x1800f10f2  test    rax, rax
0x1800f10f5  jz      loc_1800F12D0
0x1800f10fb  mov     rax, [rax+18h]
0x1800f10ff  lea     r8, [rdi+20h]
0x1800f1103  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f110a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f110f  mov     ebx, eax
0x1800f1111  test    eax, eax
0x1800f1113  jnz     loc_1800F12D5
0x1800f1119  cmp     [rsi+10h], r14d
0x1800f111d  jz      loc_1800F1269
0x1800f1123  lea     rbx, [rdi+148h]
0x1800f112a  mov     rcx, rbx
0x1800f112d  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f1132  mov     rcx, rbx; struct CSpJobMgr **
0x1800f1135  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f113a  test    eax, eax
0x1800f113c  jnz     short loc_1800F1146
0x1800f113e  lea     ebx, [rax+1Ch]
0x1800f1141  jmp     loc_1800F12D5
0x1800f1146  mov     ecx, 10h; Size
0x1800f114b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f1150  xor     r8d, r8d; pcbe
0x1800f1153  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f115a  mov     rdx, rax; pv
0x1800f115d  mov     r15, rax
0x1800f1160  mov     [rax], rdi
0x1800f1163  call    cs:__imp_CreateThreadpoolWork
0x1800f116a  nop     dword ptr [rax+rax+00h]
0x1800f116f  mov     r14, rax
0x1800f1172  test    rax, rax
0x1800f1175  jnz     short loc_1800F1183
0x1800f1177  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f117c  mov     ebx, eax
0x1800f117e  jmp     loc_1800F12D5
0x1800f1183  call    cs:__imp_GetCurrentThread
0x1800f118a  nop     dword ptr [rax+rax+00h]
0x1800f118f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f1193  xor     r8d, r8d; OpenAsSelf
0x1800f1196  mov     rcx, rax; ThreadHandle
0x1800f1199  mov     edx, 2000Ch; DesiredAccess
0x1800f119e  call    cs:__imp_OpenThreadToken
0x1800f11a5  nop     dword ptr [rax+rax+00h]
0x1800f11aa  test    eax, eax
0x1800f11ac  jnz     short loc_1800F11C1
0x1800f11ae  call    cs:__imp_GetLastError
0x1800f11b5  nop     dword ptr [rax+rax+00h]
0x1800f11ba  cmp     eax, 3F0h
0x1800f11bf  jnz     short loc_1800F1177
0x1800f11c1  mov     rax, [rbp+TokenHandle]
0x1800f11c5  mov     r8, r13
0x1800f11c8  mov     [r15+8], rax
0x1800f11cc  mov     rcx, rdi
0x1800f11cf  mov     rax, [rdi]
0x1800f11d2  mov     rdx, [rsi+8]
0x1800f11d6  mov     rax, [rax+18h]
0x1800f11da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f11df  mov     rax, [rdi]
0x1800f11e2  mov     rdx, r12
0x1800f11e5  mov     rcx, rdi
0x1800f11e8  mov     rax, [rax+28h]
0x1800f11ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f11f1  mov     ebx, eax
0x1800f11f3  test    eax, eax
0x1800f11f5  jz      short loc_1800F1200
0x1800f11f7  cmp     eax, 7
0x1800f11fa  jnz     loc_1800F12D5
0x1800f1200  mov     rax, [rdi]
0x1800f1203  mov     rdx, r12
0x1800f1206  mov     rcx, rdi
0x1800f1209  mov     rax, [rax+38h]
0x1800f120d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1212  mov     ebx, eax
0x1800f1214  test    eax, eax
0x1800f1216  jnz     loc_1800F12D5
0x1800f121c  mov     rax, [rdi+150h]
0x1800f1223  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f122a  jnz     short loc_1800F1240
0x1800f122c  mov     rax, [rdi+158h]
0x1800f1233  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f123a  jz      loc_1800F12D5
0x1800f1240  mov     rdx, r12
0x1800f1243  mov     rcx, rdi
0x1800f1246  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f124b  mov     ebx, eax
0x1800f124d  test    eax, eax
0x1800f124f  jnz     loc_1800F12D5
0x1800f1255  mov     rcx, r14; pwk
0x1800f1258  call    cs:__imp_SubmitThreadpoolWork
0x1800f125f  nop     dword ptr [rax+rax+00h]
0x1800f1264  jmp     loc_1800F1323
0x1800f1269  mov     rax, [rdi]
0x1800f126c  mov     r8, r13
0x1800f126f  mov     rdx, [rsi+8]
0x1800f1273  mov     rcx, rdi
0x1800f1276  mov     rax, [rax+10h]
0x1800f127a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f127f  mov     rax, [rdi]
0x1800f1282  mov     rdx, r12
0x1800f1285  mov     rcx, rdi
0x1800f1288  mov     rax, [rax+30h]
0x1800f128c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1291  mov     ebx, eax
0x1800f1293  test    eax, eax
0x1800f1295  jz      short loc_1800F129C
0x1800f1297  cmp     eax, 7
0x1800f129a  jnz     short loc_1800F12D5
0x1800f129c  mov     rax, [rdi]
0x1800f129f  mov     rdx, r12
0x1800f12a2  mov     rcx, rdi
0x1800f12a5  mov     rax, [rax+28h]
0x1800f12a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f12ae  mov     ebx, eax
0x1800f12b0  test    eax, eax
0x1800f12b2  jz      short loc_1800F12B9
0x1800f12b4  cmp     eax, 7
0x1800f12b7  jnz     short loc_1800F12D5
0x1800f12b9  mov     rax, [rdi]
0x1800f12bc  mov     rdx, r12
0x1800f12bf  mov     rcx, rdi
0x1800f12c2  mov     rax, [rax+38h]
0x1800f12c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f12cb  jmp     loc_1800F117C
0x1800f12d0  mov     ebx, 4
0x1800f12d5  mov     rax, [rdi]
0x1800f12d8  mov     edx, 1
0x1800f12dd  mov     rcx, rdi
0x1800f12e0  mov     rax, [rax]
0x1800f12e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f12e8  test    r15, r15
0x1800f12eb  jz      short loc_1800F12FA
0x1800f12ed  mov     edx, 10h
0x1800f12f2  mov     rcx, r15; Block
0x1800f12f5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f12fa  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f12fe  test    rcx, rcx
0x1800f1301  jz      short loc_1800F130F
0x1800f1303  call    cs:__imp_CloseHandle
0x1800f130a  nop     dword ptr [rax+rax+00h]
0x1800f130f  test    r14, r14
0x1800f1312  jz      short loc_1800F1323
0x1800f1314  mov     rcx, r14; pwk
0x1800f1317  call    cs:__imp_CloseThreadpoolWork
0x1800f131e  nop     dword ptr [rax+rax+00h]
0x1800f1323  mov     eax, ebx
0x1800f1325  mov     rcx, [rbp+var_8]
0x1800f1329  xor     rcx, rsp; StackCookie
0x1800f132c  call    __security_check_cookie
0x1800f1331  mov     rbx, [rsp+80h+arg_18]
0x1800f1339  add     rsp, 80h
0x1800f1340  pop     r15
0x1800f1342  pop     r14
0x1800f1344  pop     r13
0x1800f1346  pop     r12
0x1800f1348  pop     rdi
0x1800f1349  pop     rsi
0x1800f134a  pop     rbp
0x1800f134b  retn
```
