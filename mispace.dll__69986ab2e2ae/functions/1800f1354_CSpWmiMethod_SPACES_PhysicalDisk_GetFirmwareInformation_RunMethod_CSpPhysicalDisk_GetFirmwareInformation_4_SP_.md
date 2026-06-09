# CSpWmiMethod<_SPACES_PhysicalDisk_GetFirmwareInformation>::RunMethod<CSpPhysicalDisk::GetFirmwareInformation,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f1354`
- end: `0x1800f16d1`
- name: `??$RunMethod@VGetFirmwareInformation@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetFirmwareInformation@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800f1354`
- `0x1800f3afc`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1532`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f1507`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f1507`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f1522`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f1522`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f14e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f14e7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f15dc`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f15dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f169b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f169b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1687`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1687`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_GetFirmwareInformation>::RunMethod<CSpPhysicalDisk::GetFirmwareInformation,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 FirmwareInformation; // rax
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
  CSpPhysicalDisk::GetFirmwareInformation *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::GetFirmwareInformation *)operator new(0x168u);
  FirmwareInformation = CSpPhysicalDisk::GetFirmwareInformation::GetFirmwareInformation(v25);
  v8 = FirmwareInformation;
  if ( FirmwareInformation )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)FirmwareInformation + 8LL))(FirmwareInformation, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::GetFirmwareInformation *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18033C4ED,
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
0x1800f1354  mov     [rsp-38h+arg_18], rbx
0x1800f1359  push    rbp
0x1800f135a  push    rsi
0x1800f135b  push    rdi
0x1800f135c  push    r12
0x1800f135e  push    r13
0x1800f1360  push    r14
0x1800f1362  push    r15
0x1800f1364  mov     rbp, rsp
0x1800f1367  sub     rsp, 80h
0x1800f136e  mov     rax, cs:__security_cookie
0x1800f1375  xor     rax, rsp
0x1800f1378  mov     [rbp+var_8], rax
0x1800f137c  xor     eax, eax
0x1800f137e  mov     rsi, rcx
0x1800f1381  xorps   xmm0, xmm0
0x1800f1384  mov     [rbp+var_10], eax
0x1800f1387  mov     ecx, 168h; Size
0x1800f138c  mov     [rbp+var_40], eax
0x1800f138f  movups  [rbp+var_20], xmm0
0x1800f1393  mov     [rbp+TokenHandle], rax
0x1800f1397  mov     r12, r8
0x1800f139a  mov     r13, rdx
0x1800f139d  xor     r14d, r14d
0x1800f13a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f13a5  mov     rcx, rax; this
0x1800f13a8  mov     [rbp+var_28], rax
0x1800f13ac  call    ??0GetFirmwareInformation@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::GetFirmwareInformation::GetFirmwareInformation(void)
0x1800f13b1  mov     rdi, rax
0x1800f13b4  test    rax, rax
0x1800f13b7  jnz     short loc_1800F13C1
0x1800f13b9  lea     ebx, [rax+1Bh]
0x1800f13bc  jmp     loc_1800F167E
0x1800f13c1  mov     rax, [rax]
0x1800f13c4  mov     rdx, rsi
0x1800f13c7  mov     rcx, rdi
0x1800f13ca  xor     r15d, r15d
0x1800f13cd  mov     rax, [rax+8]
0x1800f13d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f13d6  lea     rcx, [rbp+var_40]
0x1800f13da  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f13df  mov     [rdi+1Ch], eax
0x1800f13e2  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f13e6  mov     ecx, [rsi+14h]; unsigned int
0x1800f13e9  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f13ee  mov     eax, cs:dword_18039EB68
0x1800f13f4  cmp     eax, 5
0x1800f13f7  jbe     short loc_1800F1467
0x1800f13f9  mov     rdx, 400000000000h
0x1800f1403  lea     rcx, dword_18039EB68
0x1800f140a  call    _tlgKeywordOn
0x1800f140f  test    al, al
0x1800f1411  jz      short loc_1800F1467
0x1800f1413  mov     eax, [rbp+var_40]
0x1800f1416  lea     rdx, byte_18033C4ED
0x1800f141d  xor     ecx, ecx
0x1800f141f  cmp     [rdi+1Ch], eax
0x1800f1422  movzx   eax, word ptr [rbp+var_10]
0x1800f1426  mov     word ptr [rbp+var_40], ax
0x1800f142a  setnz   cl
0x1800f142d  mov     eax, [rsi+14h]
0x1800f1430  mov     [rbp+var_38], eax
0x1800f1433  lea     rax, [rbp+var_20]
0x1800f1437  mov     [rbp+var_28], rax
0x1800f143b  lea     rax, [rbp+var_3C]
0x1800f143f  mov     [rsp+80h+var_48], rax
0x1800f1444  lea     rax, [rbp+var_40]
0x1800f1448  mov     [rsp+80h+var_50], rax
0x1800f144d  lea     rax, [rbp+var_38]
0x1800f1451  mov     [rsp+80h+var_58], rax
0x1800f1456  lea     rax, [rbp+var_28]
0x1800f145a  mov     [rsp+80h+var_60], rax
0x1800f145f  mov     [rbp+var_3C], ecx
0x1800f1462  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f1467  mov     rcx, [rsi]
0x1800f146a  test    rcx, rcx
0x1800f146d  jz      loc_1800F1654
0x1800f1473  mov     rax, [rcx]
0x1800f1476  test    rax, rax
0x1800f1479  jz      loc_1800F1654
0x1800f147f  mov     rax, [rax+18h]
0x1800f1483  lea     r8, [rdi+20h]
0x1800f1487  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f148e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1493  mov     ebx, eax
0x1800f1495  test    eax, eax
0x1800f1497  jnz     loc_1800F1659
0x1800f149d  cmp     [rsi+10h], r14d
0x1800f14a1  jz      loc_1800F15ED
0x1800f14a7  lea     rbx, [rdi+148h]
0x1800f14ae  mov     rcx, rbx
0x1800f14b1  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f14b6  mov     rcx, rbx; struct CSpJobMgr **
0x1800f14b9  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f14be  test    eax, eax
0x1800f14c0  jnz     short loc_1800F14CA
0x1800f14c2  lea     ebx, [rax+1Ch]
0x1800f14c5  jmp     loc_1800F1659
0x1800f14ca  mov     ecx, 10h; Size
0x1800f14cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f14d4  xor     r8d, r8d; pcbe
0x1800f14d7  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f14de  mov     rdx, rax; pv
0x1800f14e1  mov     r15, rax
0x1800f14e4  mov     [rax], rdi
0x1800f14e7  call    cs:__imp_CreateThreadpoolWork
0x1800f14ee  nop     dword ptr [rax+rax+00h]
0x1800f14f3  mov     r14, rax
0x1800f14f6  test    rax, rax
0x1800f14f9  jnz     short loc_1800F1507
0x1800f14fb  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f1500  mov     ebx, eax
0x1800f1502  jmp     loc_1800F1659
0x1800f1507  call    cs:__imp_GetCurrentThread
0x1800f150e  nop     dword ptr [rax+rax+00h]
0x1800f1513  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f1517  xor     r8d, r8d; OpenAsSelf
0x1800f151a  mov     rcx, rax; ThreadHandle
0x1800f151d  mov     edx, 2000Ch; DesiredAccess
0x1800f1522  call    cs:__imp_OpenThreadToken
0x1800f1529  nop     dword ptr [rax+rax+00h]
0x1800f152e  test    eax, eax
0x1800f1530  jnz     short loc_1800F1545
0x1800f1532  call    cs:__imp_GetLastError
0x1800f1539  nop     dword ptr [rax+rax+00h]
0x1800f153e  cmp     eax, 3F0h
0x1800f1543  jnz     short loc_1800F14FB
0x1800f1545  mov     rax, [rbp+TokenHandle]
0x1800f1549  mov     r8, r13
0x1800f154c  mov     [r15+8], rax
0x1800f1550  mov     rcx, rdi
0x1800f1553  mov     rax, [rdi]
0x1800f1556  mov     rdx, [rsi+8]
0x1800f155a  mov     rax, [rax+18h]
0x1800f155e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1563  mov     rax, [rdi]
0x1800f1566  mov     rdx, r12
0x1800f1569  mov     rcx, rdi
0x1800f156c  mov     rax, [rax+28h]
0x1800f1570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1575  mov     ebx, eax
0x1800f1577  test    eax, eax
0x1800f1579  jz      short loc_1800F1584
0x1800f157b  cmp     eax, 7
0x1800f157e  jnz     loc_1800F1659
0x1800f1584  mov     rax, [rdi]
0x1800f1587  mov     rdx, r12
0x1800f158a  mov     rcx, rdi
0x1800f158d  mov     rax, [rax+38h]
0x1800f1591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1596  mov     ebx, eax
0x1800f1598  test    eax, eax
0x1800f159a  jnz     loc_1800F1659
0x1800f15a0  mov     rax, [rdi+150h]
0x1800f15a7  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f15ae  jnz     short loc_1800F15C4
0x1800f15b0  mov     rax, [rdi+158h]
0x1800f15b7  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f15be  jz      loc_1800F1659
0x1800f15c4  mov     rdx, r12
0x1800f15c7  mov     rcx, rdi
0x1800f15ca  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f15cf  mov     ebx, eax
0x1800f15d1  test    eax, eax
0x1800f15d3  jnz     loc_1800F1659
0x1800f15d9  mov     rcx, r14; pwk
0x1800f15dc  call    cs:__imp_SubmitThreadpoolWork
0x1800f15e3  nop     dword ptr [rax+rax+00h]
0x1800f15e8  jmp     loc_1800F16A7
0x1800f15ed  mov     rax, [rdi]
0x1800f15f0  mov     r8, r13
0x1800f15f3  mov     rdx, [rsi+8]
0x1800f15f7  mov     rcx, rdi
0x1800f15fa  mov     rax, [rax+10h]
0x1800f15fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1603  mov     rax, [rdi]
0x1800f1606  mov     rdx, r12
0x1800f1609  mov     rcx, rdi
0x1800f160c  mov     rax, [rax+30h]
0x1800f1610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1615  mov     ebx, eax
0x1800f1617  test    eax, eax
0x1800f1619  jz      short loc_1800F1620
0x1800f161b  cmp     eax, 7
0x1800f161e  jnz     short loc_1800F1659
0x1800f1620  mov     rax, [rdi]
0x1800f1623  mov     rdx, r12
0x1800f1626  mov     rcx, rdi
0x1800f1629  mov     rax, [rax+28h]
0x1800f162d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1632  mov     ebx, eax
0x1800f1634  test    eax, eax
0x1800f1636  jz      short loc_1800F163D
0x1800f1638  cmp     eax, 7
0x1800f163b  jnz     short loc_1800F1659
0x1800f163d  mov     rax, [rdi]
0x1800f1640  mov     rdx, r12
0x1800f1643  mov     rcx, rdi
0x1800f1646  mov     rax, [rax+38h]
0x1800f164a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f164f  jmp     loc_1800F1500
0x1800f1654  mov     ebx, 4
0x1800f1659  mov     rax, [rdi]
0x1800f165c  mov     edx, 1
0x1800f1661  mov     rcx, rdi
0x1800f1664  mov     rax, [rax]
0x1800f1667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f166c  test    r15, r15
0x1800f166f  jz      short loc_1800F167E
0x1800f1671  mov     edx, 10h
0x1800f1676  mov     rcx, r15; Block
0x1800f1679  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f167e  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f1682  test    rcx, rcx
0x1800f1685  jz      short loc_1800F1693
0x1800f1687  call    cs:__imp_CloseHandle
0x1800f168e  nop     dword ptr [rax+rax+00h]
0x1800f1693  test    r14, r14
0x1800f1696  jz      short loc_1800F16A7
0x1800f1698  mov     rcx, r14; pwk
0x1800f169b  call    cs:__imp_CloseThreadpoolWork
0x1800f16a2  nop     dword ptr [rax+rax+00h]
0x1800f16a7  mov     eax, ebx
0x1800f16a9  mov     rcx, [rbp+var_8]
0x1800f16ad  xor     rcx, rsp; StackCookie
0x1800f16b0  call    __security_check_cookie
0x1800f16b5  mov     rbx, [rsp+80h+arg_18]
0x1800f16bd  add     rsp, 80h
0x1800f16c4  pop     r15
0x1800f16c6  pop     r14
0x1800f16c8  pop     r13
0x1800f16ca  pop     r12
0x1800f16cc  pop     rdi
0x1800f16cd  pop     rsi
0x1800f16ce  pop     rbp
0x1800f16cf  retn
```
