# CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::RunMethod<CSpPhysicalDisk::GetPhysicalExtent,4>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800f16d8`
- end: `0x1800f1a55`
- name: `??$RunMethod@VGetPhysicalExtent@CSpPhysicalDisk@@$03@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800f16d8`
- `0x1800f3b74`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f18b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f18b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f188b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f188b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f18a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f18a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f186b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800f186b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f1960`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800f1960`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f1a1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800f1a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1a0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f1a0b`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_PhysicalDisk_GetPhysicalExtent>::RunMethod<CSpPhysicalDisk::GetPhysicalExtent,4>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  struct _TP_WORK *ThreadpoolWork; // r14
  __int64 PhysicalExtent; // rax
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
  CSpPhysicalDisk::GetPhysicalExtent *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpPhysicalDisk::GetPhysicalExtent *)operator new(0x170u);
  PhysicalExtent = CSpPhysicalDisk::GetPhysicalExtent::GetPhysicalExtent(v25);
  v8 = PhysicalExtent;
  if ( PhysicalExtent )
  {
    v10 = 0;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)PhysicalExtent + 8LL))(PhysicalExtent, a1);
    *(_DWORD *)(v8 + 28) = _GetSubsystemVersion(&v21);
    WspGetSubsystemInfo(*((_DWORD *)a1 + 5), (struct _SUBSYSTEM_INFO *)&v26);
    if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
    {
      v13 = *(_DWORD *)(v8 + 28) == v21;
      LOWORD(v21) = v27;
      v23 = *((_DWORD *)a1 + 5);
      v25 = (CSpPhysicalDisk::GetPhysicalExtent *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_18033B3EA,
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
0x1800f16d8  mov     [rsp-38h+arg_18], rbx
0x1800f16dd  push    rbp
0x1800f16de  push    rsi
0x1800f16df  push    rdi
0x1800f16e0  push    r12
0x1800f16e2  push    r13
0x1800f16e4  push    r14
0x1800f16e6  push    r15
0x1800f16e8  mov     rbp, rsp
0x1800f16eb  sub     rsp, 80h
0x1800f16f2  mov     rax, cs:__security_cookie
0x1800f16f9  xor     rax, rsp
0x1800f16fc  mov     [rbp+var_8], rax
0x1800f1700  xor     eax, eax
0x1800f1702  mov     rsi, rcx
0x1800f1705  xorps   xmm0, xmm0
0x1800f1708  mov     [rbp+var_10], eax
0x1800f170b  mov     ecx, 170h; Size
0x1800f1710  mov     [rbp+var_40], eax
0x1800f1713  movups  [rbp+var_20], xmm0
0x1800f1717  mov     [rbp+TokenHandle], rax
0x1800f171b  mov     r12, r8
0x1800f171e  mov     r13, rdx
0x1800f1721  xor     r14d, r14d
0x1800f1724  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f1729  mov     rcx, rax; this
0x1800f172c  mov     [rbp+var_28], rax
0x1800f1730  call    ??0GetPhysicalExtent@CSpPhysicalDisk@@QEAA@XZ; CSpPhysicalDisk::GetPhysicalExtent::GetPhysicalExtent(void)
0x1800f1735  mov     rdi, rax
0x1800f1738  test    rax, rax
0x1800f173b  jnz     short loc_1800F1745
0x1800f173d  lea     ebx, [rax+1Bh]
0x1800f1740  jmp     loc_1800F1A02
0x1800f1745  mov     rax, [rax]
0x1800f1748  mov     rdx, rsi
0x1800f174b  mov     rcx, rdi
0x1800f174e  xor     r15d, r15d
0x1800f1751  mov     rax, [rax+8]
0x1800f1755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f175a  lea     rcx, [rbp+var_40]
0x1800f175e  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800f1763  mov     [rdi+1Ch], eax
0x1800f1766  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800f176a  mov     ecx, [rsi+14h]; unsigned int
0x1800f176d  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800f1772  mov     eax, cs:dword_18039EB68
0x1800f1778  cmp     eax, 5
0x1800f177b  jbe     short loc_1800F17EB
0x1800f177d  mov     rdx, 400000000000h
0x1800f1787  lea     rcx, dword_18039EB68
0x1800f178e  call    _tlgKeywordOn
0x1800f1793  test    al, al
0x1800f1795  jz      short loc_1800F17EB
0x1800f1797  mov     eax, [rbp+var_40]
0x1800f179a  lea     rdx, word_18033B3EA
0x1800f17a1  xor     ecx, ecx
0x1800f17a3  cmp     [rdi+1Ch], eax
0x1800f17a6  movzx   eax, word ptr [rbp+var_10]
0x1800f17aa  mov     word ptr [rbp+var_40], ax
0x1800f17ae  setnz   cl
0x1800f17b1  mov     eax, [rsi+14h]
0x1800f17b4  mov     [rbp+var_38], eax
0x1800f17b7  lea     rax, [rbp+var_20]
0x1800f17bb  mov     [rbp+var_28], rax
0x1800f17bf  lea     rax, [rbp+var_3C]
0x1800f17c3  mov     [rsp+80h+var_48], rax
0x1800f17c8  lea     rax, [rbp+var_40]
0x1800f17cc  mov     [rsp+80h+var_50], rax
0x1800f17d1  lea     rax, [rbp+var_38]
0x1800f17d5  mov     [rsp+80h+var_58], rax
0x1800f17da  lea     rax, [rbp+var_28]
0x1800f17de  mov     [rsp+80h+var_60], rax
0x1800f17e3  mov     [rbp+var_3C], ecx
0x1800f17e6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800f17eb  mov     rcx, [rsi]
0x1800f17ee  test    rcx, rcx
0x1800f17f1  jz      loc_1800F19D8
0x1800f17f7  mov     rax, [rcx]
0x1800f17fa  test    rax, rax
0x1800f17fd  jz      loc_1800F19D8
0x1800f1803  mov     rax, [rax+18h]
0x1800f1807  lea     r8, [rdi+20h]
0x1800f180b  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800f1812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1817  mov     ebx, eax
0x1800f1819  test    eax, eax
0x1800f181b  jnz     loc_1800F19DD
0x1800f1821  cmp     [rsi+10h], r14d
0x1800f1825  jz      loc_1800F1971
0x1800f182b  lea     rbx, [rdi+148h]
0x1800f1832  mov     rcx, rbx
0x1800f1835  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800f183a  mov     rcx, rbx; struct CSpJobMgr **
0x1800f183d  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800f1842  test    eax, eax
0x1800f1844  jnz     short loc_1800F184E
0x1800f1846  lea     ebx, [rax+1Ch]
0x1800f1849  jmp     loc_1800F19DD
0x1800f184e  mov     ecx, 10h; Size
0x1800f1853  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f1858  xor     r8d, r8d; pcbe
0x1800f185b  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800f1862  mov     rdx, rax; pv
0x1800f1865  mov     r15, rax
0x1800f1868  mov     [rax], rdi
0x1800f186b  call    cs:__imp_CreateThreadpoolWork
0x1800f1872  nop     dword ptr [rax+rax+00h]
0x1800f1877  mov     r14, rax
0x1800f187a  test    rax, rax
0x1800f187d  jnz     short loc_1800F188B
0x1800f187f  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800f1884  mov     ebx, eax
0x1800f1886  jmp     loc_1800F19DD
0x1800f188b  call    cs:__imp_GetCurrentThread
0x1800f1892  nop     dword ptr [rax+rax+00h]
0x1800f1897  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800f189b  xor     r8d, r8d; OpenAsSelf
0x1800f189e  mov     rcx, rax; ThreadHandle
0x1800f18a1  mov     edx, 2000Ch; DesiredAccess
0x1800f18a6  call    cs:__imp_OpenThreadToken
0x1800f18ad  nop     dword ptr [rax+rax+00h]
0x1800f18b2  test    eax, eax
0x1800f18b4  jnz     short loc_1800F18C9
0x1800f18b6  call    cs:__imp_GetLastError
0x1800f18bd  nop     dword ptr [rax+rax+00h]
0x1800f18c2  cmp     eax, 3F0h
0x1800f18c7  jnz     short loc_1800F187F
0x1800f18c9  mov     rax, [rbp+TokenHandle]
0x1800f18cd  mov     r8, r13
0x1800f18d0  mov     [r15+8], rax
0x1800f18d4  mov     rcx, rdi
0x1800f18d7  mov     rax, [rdi]
0x1800f18da  mov     rdx, [rsi+8]
0x1800f18de  mov     rax, [rax+18h]
0x1800f18e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f18e7  mov     rax, [rdi]
0x1800f18ea  mov     rdx, r12
0x1800f18ed  mov     rcx, rdi
0x1800f18f0  mov     rax, [rax+28h]
0x1800f18f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f18f9  mov     ebx, eax
0x1800f18fb  test    eax, eax
0x1800f18fd  jz      short loc_1800F1908
0x1800f18ff  cmp     eax, 7
0x1800f1902  jnz     loc_1800F19DD
0x1800f1908  mov     rax, [rdi]
0x1800f190b  mov     rdx, r12
0x1800f190e  mov     rcx, rdi
0x1800f1911  mov     rax, [rax+38h]
0x1800f1915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f191a  mov     ebx, eax
0x1800f191c  test    eax, eax
0x1800f191e  jnz     loc_1800F19DD
0x1800f1924  mov     rax, [rdi+150h]
0x1800f192b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800f1932  jnz     short loc_1800F1948
0x1800f1934  mov     rax, [rdi+158h]
0x1800f193b  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800f1942  jz      loc_1800F19DD
0x1800f1948  mov     rdx, r12
0x1800f194b  mov     rcx, rdi
0x1800f194e  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800f1953  mov     ebx, eax
0x1800f1955  test    eax, eax
0x1800f1957  jnz     loc_1800F19DD
0x1800f195d  mov     rcx, r14; pwk
0x1800f1960  call    cs:__imp_SubmitThreadpoolWork
0x1800f1967  nop     dword ptr [rax+rax+00h]
0x1800f196c  jmp     loc_1800F1A2B
0x1800f1971  mov     rax, [rdi]
0x1800f1974  mov     r8, r13
0x1800f1977  mov     rdx, [rsi+8]
0x1800f197b  mov     rcx, rdi
0x1800f197e  mov     rax, [rax+10h]
0x1800f1982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1987  mov     rax, [rdi]
0x1800f198a  mov     rdx, r12
0x1800f198d  mov     rcx, rdi
0x1800f1990  mov     rax, [rax+30h]
0x1800f1994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1999  mov     ebx, eax
0x1800f199b  test    eax, eax
0x1800f199d  jz      short loc_1800F19A4
0x1800f199f  cmp     eax, 7
0x1800f19a2  jnz     short loc_1800F19DD
0x1800f19a4  mov     rax, [rdi]
0x1800f19a7  mov     rdx, r12
0x1800f19aa  mov     rcx, rdi
0x1800f19ad  mov     rax, [rax+28h]
0x1800f19b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f19b6  mov     ebx, eax
0x1800f19b8  test    eax, eax
0x1800f19ba  jz      short loc_1800F19C1
0x1800f19bc  cmp     eax, 7
0x1800f19bf  jnz     short loc_1800F19DD
0x1800f19c1  mov     rax, [rdi]
0x1800f19c4  mov     rdx, r12
0x1800f19c7  mov     rcx, rdi
0x1800f19ca  mov     rax, [rax+38h]
0x1800f19ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f19d3  jmp     loc_1800F1884
0x1800f19d8  mov     ebx, 4
0x1800f19dd  mov     rax, [rdi]
0x1800f19e0  mov     edx, 1
0x1800f19e5  mov     rcx, rdi
0x1800f19e8  mov     rax, [rax]
0x1800f19eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f19f0  test    r15, r15
0x1800f19f3  jz      short loc_1800F1A02
0x1800f19f5  mov     edx, 10h
0x1800f19fa  mov     rcx, r15; Block
0x1800f19fd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800f1a02  mov     rcx, [rbp+TokenHandle]; hObject
0x1800f1a06  test    rcx, rcx
0x1800f1a09  jz      short loc_1800F1A17
0x1800f1a0b  call    cs:__imp_CloseHandle
0x1800f1a12  nop     dword ptr [rax+rax+00h]
0x1800f1a17  test    r14, r14
0x1800f1a1a  jz      short loc_1800F1A2B
0x1800f1a1c  mov     rcx, r14; pwk
0x1800f1a1f  call    cs:__imp_CloseThreadpoolWork
0x1800f1a26  nop     dword ptr [rax+rax+00h]
0x1800f1a2b  mov     eax, ebx
0x1800f1a2d  mov     rcx, [rbp+var_8]
0x1800f1a31  xor     rcx, rsp; StackCookie
0x1800f1a34  call    __security_check_cookie
0x1800f1a39  mov     rbx, [rsp+80h+arg_18]
0x1800f1a41  add     rsp, 80h
0x1800f1a48  pop     r15
0x1800f1a4a  pop     r14
0x1800f1a4c  pop     r13
0x1800f1a4e  pop     r12
0x1800f1a50  pop     rdi
0x1800f1a51  pop     rsi
0x1800f1a52  pop     rbp
0x1800f1a53  retn
```
