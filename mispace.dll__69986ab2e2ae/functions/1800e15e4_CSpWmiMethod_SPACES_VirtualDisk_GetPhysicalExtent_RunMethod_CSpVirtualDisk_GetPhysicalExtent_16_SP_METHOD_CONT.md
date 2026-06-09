# CSpWmiMethod<_SPACES_VirtualDisk_GetPhysicalExtent>::RunMethod<CSpVirtualDisk::GetPhysicalExtent,16>(_SP_METHOD_CONTEXT *,void const *,void *)

- ea: `0x1800e15e4`
- end: `0x1800e1961`
- name: `??$RunMethod@VGetPhysicalExtent@CSpVirtualDisk@@$0BA@@?$CSpWmiMethod@U_SPACES_VirtualDisk_GetPhysicalExtent@@@@SA?AW4_MI_Result@@PEAU_SP_METHOD_CONTEXT@@PEBXPEAX@Z`
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
- `0x1800e15e4`
- `0x1800e3ec8`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e17c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e17c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e1797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e1797`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e17b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e17b2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e1777`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800e1777`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e186c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e186c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e192b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800e192b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e1917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e1917`

## pseudocode

```c
__int64 __fastcall CSpWmiMethod<_SPACES_VirtualDisk_GetPhysicalExtent>::RunMethod<CSpVirtualDisk::GetPhysicalExtent,16>(
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
  CSpVirtualDisk::GetPhysicalExtent *v25; // [rsp+58h] [rbp-28h] BYREF
  __int128 v26; // [rsp+60h] [rbp-20h] BYREF
  int v27; // [rsp+70h] [rbp-10h]

  v27 = 0;
  v21 = 0;
  v26 = 0;
  TokenHandle = 0;
  ThreadpoolWork = 0;
  v25 = (CSpVirtualDisk::GetPhysicalExtent *)operator new(0x170u);
  PhysicalExtent = CSpVirtualDisk::GetPhysicalExtent::GetPhysicalExtent(v25);
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
      v25 = (CSpVirtualDisk::GetPhysicalExtent *)&v26;
      v22 = !v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)word_18033ABEA,
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
0x1800e15e4  mov     [rsp-38h+arg_18], rbx
0x1800e15e9  push    rbp
0x1800e15ea  push    rsi
0x1800e15eb  push    rdi
0x1800e15ec  push    r12
0x1800e15ee  push    r13
0x1800e15f0  push    r14
0x1800e15f2  push    r15
0x1800e15f4  mov     rbp, rsp
0x1800e15f7  sub     rsp, 80h
0x1800e15fe  mov     rax, cs:__security_cookie
0x1800e1605  xor     rax, rsp
0x1800e1608  mov     [rbp+var_8], rax
0x1800e160c  xor     eax, eax
0x1800e160e  mov     rsi, rcx
0x1800e1611  xorps   xmm0, xmm0
0x1800e1614  mov     [rbp+var_10], eax
0x1800e1617  mov     ecx, 170h; Size
0x1800e161c  mov     [rbp+var_40], eax
0x1800e161f  movups  [rbp+var_20], xmm0
0x1800e1623  mov     [rbp+TokenHandle], rax
0x1800e1627  mov     r12, r8
0x1800e162a  mov     r13, rdx
0x1800e162d  xor     r14d, r14d
0x1800e1630  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e1635  mov     rcx, rax; this
0x1800e1638  mov     [rbp+var_28], rax
0x1800e163c  call    ??0GetPhysicalExtent@CSpVirtualDisk@@QEAA@XZ; CSpVirtualDisk::GetPhysicalExtent::GetPhysicalExtent(void)
0x1800e1641  mov     rdi, rax
0x1800e1644  test    rax, rax
0x1800e1647  jnz     short loc_1800E1651
0x1800e1649  lea     ebx, [rax+1Bh]
0x1800e164c  jmp     loc_1800E190E
0x1800e1651  mov     rax, [rax]
0x1800e1654  mov     rdx, rsi
0x1800e1657  mov     rcx, rdi
0x1800e165a  xor     r15d, r15d
0x1800e165d  mov     rax, [rax+8]
0x1800e1661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1666  lea     rcx, [rbp+var_40]
0x1800e166a  call    ?_GetSubsystemVersion@@YA?AW4WSP_SUBSYSTEM_VERSION@@PEAW41@@Z; _GetSubsystemVersion(WSP_SUBSYSTEM_VERSION *)
0x1800e166f  mov     [rdi+1Ch], eax
0x1800e1672  lea     rdx, [rbp+var_20]; struct _SUBSYSTEM_INFO *
0x1800e1676  mov     ecx, [rsi+14h]; unsigned int
0x1800e1679  call    ?WspGetSubsystemInfo@@YAXIPEAU_SUBSYSTEM_INFO@@@Z; WspGetSubsystemInfo(uint,_SUBSYSTEM_INFO *)
0x1800e167e  mov     eax, cs:dword_18039EB68
0x1800e1684  cmp     eax, 5
0x1800e1687  jbe     short loc_1800E16F7
0x1800e1689  mov     rdx, 400000000000h
0x1800e1693  lea     rcx, dword_18039EB68
0x1800e169a  call    _tlgKeywordOn
0x1800e169f  test    al, al
0x1800e16a1  jz      short loc_1800E16F7
0x1800e16a3  mov     eax, [rbp+var_40]
0x1800e16a6  lea     rdx, word_18033ABEA
0x1800e16ad  xor     ecx, ecx
0x1800e16af  cmp     [rdi+1Ch], eax
0x1800e16b2  movzx   eax, word ptr [rbp+var_10]
0x1800e16b6  mov     word ptr [rbp+var_40], ax
0x1800e16ba  setnz   cl
0x1800e16bd  mov     eax, [rsi+14h]
0x1800e16c0  mov     [rbp+var_38], eax
0x1800e16c3  lea     rax, [rbp+var_20]
0x1800e16c7  mov     [rbp+var_28], rax
0x1800e16cb  lea     rax, [rbp+var_3C]
0x1800e16cf  mov     [rsp+80h+var_48], rax
0x1800e16d4  lea     rax, [rbp+var_40]
0x1800e16d8  mov     [rsp+80h+var_50], rax
0x1800e16dd  lea     rax, [rbp+var_38]
0x1800e16e1  mov     [rsp+80h+var_58], rax
0x1800e16e6  lea     rax, [rbp+var_28]
0x1800e16ea  mov     [rsp+80h+var_60], rax
0x1800e16ef  mov     [rbp+var_3C], ecx
0x1800e16f2  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)
0x1800e16f7  mov     rcx, [rsi]
0x1800e16fa  test    rcx, rcx
0x1800e16fd  jz      loc_1800E18E4
0x1800e1703  mov     rax, [rcx]
0x1800e1706  test    rax, rax
0x1800e1709  jz      loc_1800E18E4
0x1800e170f  mov     rax, [rax+18h]
0x1800e1713  lea     r8, [rdi+20h]
0x1800e1717  lea     rdx, MSFT_StorageExtendedStatus_rtti
0x1800e171e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1723  mov     ebx, eax
0x1800e1725  test    eax, eax
0x1800e1727  jnz     loc_1800E18E9
0x1800e172d  cmp     [rsi+10h], r14d
0x1800e1731  jz      loc_1800E187D
0x1800e1737  lea     rbx, [rdi+148h]
0x1800e173e  mov     rcx, rbx
0x1800e1741  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x1800e1746  mov     rcx, rbx; struct CSpJobMgr **
0x1800e1749  call    ?GetInstance@CSpJobMgr@@SAHPEAPEAV1@@Z; CSpJobMgr::GetInstance(CSpJobMgr * *)
0x1800e174e  test    eax, eax
0x1800e1750  jnz     short loc_1800E175A
0x1800e1752  lea     ebx, [rax+1Ch]
0x1800e1755  jmp     loc_1800E18E9
0x1800e175a  mov     ecx, 10h; Size
0x1800e175f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e1764  xor     r8d, r8d; pcbe
0x1800e1767  lea     rcx, ?ResumeMethodWorker@?$CSpWmiMethod@U_SPACES_PhysicalDisk_GetPhysicalExtent@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800e176e  mov     rdx, rax; pv
0x1800e1771  mov     r15, rax
0x1800e1774  mov     [rax], rdi
0x1800e1777  call    cs:__imp_CreateThreadpoolWork
0x1800e177e  nop     dword ptr [rax+rax+00h]
0x1800e1783  mov     r14, rax
0x1800e1786  test    rax, rax
0x1800e1789  jnz     short loc_1800E1797
0x1800e178b  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800e1790  mov     ebx, eax
0x1800e1792  jmp     loc_1800E18E9
0x1800e1797  call    cs:__imp_GetCurrentThread
0x1800e179e  nop     dword ptr [rax+rax+00h]
0x1800e17a3  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800e17a7  xor     r8d, r8d; OpenAsSelf
0x1800e17aa  mov     rcx, rax; ThreadHandle
0x1800e17ad  mov     edx, 2000Ch; DesiredAccess
0x1800e17b2  call    cs:__imp_OpenThreadToken
0x1800e17b9  nop     dword ptr [rax+rax+00h]
0x1800e17be  test    eax, eax
0x1800e17c0  jnz     short loc_1800E17D5
0x1800e17c2  call    cs:__imp_GetLastError
0x1800e17c9  nop     dword ptr [rax+rax+00h]
0x1800e17ce  cmp     eax, 3F0h
0x1800e17d3  jnz     short loc_1800E178B
0x1800e17d5  mov     rax, [rbp+TokenHandle]
0x1800e17d9  mov     r8, r13
0x1800e17dc  mov     [r15+8], rax
0x1800e17e0  mov     rcx, rdi
0x1800e17e3  mov     rax, [rdi]
0x1800e17e6  mov     rdx, [rsi+8]
0x1800e17ea  mov     rax, [rax+18h]
0x1800e17ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e17f3  mov     rax, [rdi]
0x1800e17f6  mov     rdx, r12
0x1800e17f9  mov     rcx, rdi
0x1800e17fc  mov     rax, [rax+28h]
0x1800e1800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1805  mov     ebx, eax
0x1800e1807  test    eax, eax
0x1800e1809  jz      short loc_1800E1814
0x1800e180b  cmp     eax, 7
0x1800e180e  jnz     loc_1800E18E9
0x1800e1814  mov     rax, [rdi]
0x1800e1817  mov     rdx, r12
0x1800e181a  mov     rcx, rdi
0x1800e181d  mov     rax, [rax+38h]
0x1800e1821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1826  mov     ebx, eax
0x1800e1828  test    eax, eax
0x1800e182a  jnz     loc_1800E18E9
0x1800e1830  mov     rax, [rdi+150h]
0x1800e1837  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800e183e  jnz     short loc_1800E1854
0x1800e1840  mov     rax, [rdi+158h]
0x1800e1847  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800e184e  jz      loc_1800E18E9
0x1800e1854  mov     rdx, r12
0x1800e1857  mov     rcx, rdi
0x1800e185a  call    ?SetCreatedJob@?$CSpWmiMethod@U_SPACES_StoragePool_SetAttributes@@@@AEAA?AW4_MI_Result@@PEAU_SPACES_StoragePool_SetAttributes@@@Z; CSpWmiMethod<_SPACES_StoragePool_SetAttributes>::SetCreatedJob(_SPACES_StoragePool_SetAttributes *)
0x1800e185f  mov     ebx, eax
0x1800e1861  test    eax, eax
0x1800e1863  jnz     loc_1800E18E9
0x1800e1869  mov     rcx, r14; pwk
0x1800e186c  call    cs:__imp_SubmitThreadpoolWork
0x1800e1873  nop     dword ptr [rax+rax+00h]
0x1800e1878  jmp     loc_1800E1937
0x1800e187d  mov     rax, [rdi]
0x1800e1880  mov     r8, r13
0x1800e1883  mov     rdx, [rsi+8]
0x1800e1887  mov     rcx, rdi
0x1800e188a  mov     rax, [rax+10h]
0x1800e188e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1893  mov     rax, [rdi]
0x1800e1896  mov     rdx, r12
0x1800e1899  mov     rcx, rdi
0x1800e189c  mov     rax, [rax+30h]
0x1800e18a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e18a5  mov     ebx, eax
0x1800e18a7  test    eax, eax
0x1800e18a9  jz      short loc_1800E18B0
0x1800e18ab  cmp     eax, 7
0x1800e18ae  jnz     short loc_1800E18E9
0x1800e18b0  mov     rax, [rdi]
0x1800e18b3  mov     rdx, r12
0x1800e18b6  mov     rcx, rdi
0x1800e18b9  mov     rax, [rax+28h]
0x1800e18bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e18c2  mov     ebx, eax
0x1800e18c4  test    eax, eax
0x1800e18c6  jz      short loc_1800E18CD
0x1800e18c8  cmp     eax, 7
0x1800e18cb  jnz     short loc_1800E18E9
0x1800e18cd  mov     rax, [rdi]
0x1800e18d0  mov     rdx, r12
0x1800e18d3  mov     rcx, rdi
0x1800e18d6  mov     rax, [rax+38h]
0x1800e18da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e18df  jmp     loc_1800E1790
0x1800e18e4  mov     ebx, 4
0x1800e18e9  mov     rax, [rdi]
0x1800e18ec  mov     edx, 1
0x1800e18f1  mov     rcx, rdi
0x1800e18f4  mov     rax, [rax]
0x1800e18f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e18fc  test    r15, r15
0x1800e18ff  jz      short loc_1800E190E
0x1800e1901  mov     edx, 10h
0x1800e1906  mov     rcx, r15; Block
0x1800e1909  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e190e  mov     rcx, [rbp+TokenHandle]; hObject
0x1800e1912  test    rcx, rcx
0x1800e1915  jz      short loc_1800E1923
0x1800e1917  call    cs:__imp_CloseHandle
0x1800e191e  nop     dword ptr [rax+rax+00h]
0x1800e1923  test    r14, r14
0x1800e1926  jz      short loc_1800E1937
0x1800e1928  mov     rcx, r14; pwk
0x1800e192b  call    cs:__imp_CloseThreadpoolWork
0x1800e1932  nop     dword ptr [rax+rax+00h]
0x1800e1937  mov     eax, ebx
0x1800e1939  mov     rcx, [rbp+var_8]
0x1800e193d  xor     rcx, rsp; StackCookie
0x1800e1940  call    __security_check_cookie
0x1800e1945  mov     rbx, [rsp+80h+arg_18]
0x1800e194d  add     rsp, 80h
0x1800e1954  pop     r15
0x1800e1956  pop     r14
0x1800e1958  pop     r13
0x1800e195a  pop     r12
0x1800e195c  pop     rdi
0x1800e195d  pop     rsi
0x1800e195e  pop     rbp
0x1800e195f  retn
```
