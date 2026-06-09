# CscSync_EncryptOrUnencryptCache(HWND__ *,int,ulong,CSyncAggregator *,IOfflineFilesUserSessionCallback *,IOfflineFilesSyncProgressInternal *)

- ea: `0x18000e51c`
- end: `0x18000ea1f`
- name: `?CscSync_EncryptOrUnencryptCache@@YAJPEAUHWND__@@HKPEAVCSyncAggregator@@PEAUIOfflineFilesUserSessionCallback@@PEAUIOfflineFilesSyncProgressInternal@@@Z`
- size: `1283`
- prototype: `int(HWND, int, unsigned int, struct CSyncAggregator *, struct IOfflineFilesUserSessionCallback *, struct IOfflineFilesSyncProgressInternal *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003f3b0`
- `0x180061400`

## callees

- `0x18000d640`
- `0x18000da64`
- `0x18000e51c`
- `0x18000ed20`
- `0x18000f348`
- `0x18002f5a0`
- `0x180030234`
- `0x180036394`
- `0x1800391b8`
- `0x18003c488`
- `0x18004b5e0`
- `0x180062d54`
- `0x18006ceb4`
- `0x180089010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000e9ff`
- `ntdll!RtlNtStatusToDosError` at `0x18000e9ff`
- `KERNEL32!lstrcmpiW` at `0x18000e598`
- `KERNEL32!lstrcmpiW` at `0x18000e61e`
- `KERNEL32!lstrcmpiW` at `0x18000e598`
- `KERNEL32!lstrcmpiW` at `0x18000e61e`

## string_xrefs

- `0x18000e585`: `EncryptCache`
- `0x18000e609`: `EncryptCache`
- `0x18000e67a`: `EncryptCache`
- `0x18000e7d1`: `EncryptCache`

## pseudocode

```c
__int64 __fastcall CscSync_EncryptOrUnencryptCache(
        HWND a1,
        int a2,
        int a3,
        struct CSyncAggregator *a4,
        struct IOfflineFilesUserSessionCallback *a5,
        struct IOfflineFilesSyncProgressInternal *a6)
{
  unsigned int v7; // r13d
  int Instance; // ebx
  __int64 v9; // rsi
  int v10; // r14d
  unsigned int i; // edi
  COfflineFilesSetting *v12; // rax
  COfflineFilesSetting *v13; // rax
  COfflineFilesSetting *v14; // rdi
  unsigned int j; // r14d
  LPCWSTR *v16; // r15
  int v17; // eax
  int v18; // eax
  const struct _GUID *v19; // rcx
  struct IOfflineFilesSyncProgressInternal *v20; // rsi
  CFastSyncControllerFactoryBase *v21; // rax
  CFastSyncControllerFactoryBase *v22; // rdi
  void **v23; // r15
  unsigned int v24; // r12d
  __int64 v25; // r14
  void *v26; // rdx
  __int64 v27; // rax
  __int64 (__fastcall **v28)(struct IOfflineFilesSyncProgressInternal *, GUID *, struct IOfflineFilesSyncConflictHandler **); // rax
  int v29; // edi
  NTSTATUS v30; // edi
  unsigned int v31; // eax
  struct _GUID *v33; // [rsp+30h] [rbp-40h]
  struct IOfflineFilesSyncConflictHandler *v34; // [rsp+40h] [rbp-30h] BYREF
  void *lpMem; // [rsp+48h] [rbp-28h] BYREF
  struct _GUID v36; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v39; // [rsp+C8h] [rbp+58h] BYREF
  int v40; // [rsp+CCh] [rbp+5Ch]

  v40 = HIDWORD(a4);
  LODWORD(v34) = 0;
  v39 = 0;
  v7 = 0;
  Instance = CscLib_SetCacheEncryptionBeginStatus(a2, (int *)&v34);
  if ( Instance < 0 )
    goto LABEL_49;
  v9 = 0;
  v10 = -2147024773;
  for ( i = 0; i < 0x42; ++i )
  {
    Instance = 0;
    if ( lstrcmpiW((&off_18008A820)[6 * (int)i], L"EncryptCache") )
      Instance = v10;
    v10 = Instance;
  }
  v7 = v39;
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids,
        L"EncryptCache");
    }
  }
  else
  {
    Instance = -2147024882;
    v12 = (COfflineFilesSetting *)operator new(0x40u);
    if ( !v12 )
      goto LABEL_48;
    v13 = COfflineFilesSetting::COfflineFilesSetting(v12);
    v14 = v13;
    if ( !v13 )
      goto LABEL_48;
    if ( *((_QWORD *)v13 + 7) )
    {
      v17 = -2147467259;
    }
    else
    {
      Instance = -2147024773;
      *((_QWORD *)v13 + 7) = 0;
      for ( j = 0; j < 0x42; ++j )
      {
        v16 = (LPCWSTR *)&(&off_18008A820)[6 * (int)j];
        if ( !lstrcmpiW(*v16, L"EncryptCache") )
        {
          *((_QWORD *)v14 + 7) = v16;
          Instance = 0;
        }
      }
      v7 = v39;
      v17 = Instance;
      if ( Instance == -2147024773
        && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids,
          L"EncryptCache");
LABEL_18:
        (**(void (__fastcall ***)(COfflineFilesSetting *, __int64))v14)(v14, 1);
        goto LABEL_19;
      }
    }
    Instance = v17;
    if ( v17 < 0 )
      goto LABEL_18;
    v9 = ((unsigned __int64)v14 + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)v14 >> 64);
  }
LABEL_19:
  if ( Instance < 0 )
  {
LABEL_48:
    v30 = 0;
    goto LABEL_54;
  }
  LOWORD(v36.Data1) = 3;
  *(_DWORD *)v36.Data4 = a2 != 0;
  v18 = (*(__int64 (__fastcall **)(__int64, struct _GUID *, __int64))(*(_QWORD *)v9 + 24LL))(v9, &v36, 1);
  Instance = v18;
  if ( v18 < 0
    && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      219,
      WPP_7967f24143133d59f1b33f7a742017bc_Traceguids,
      (unsigned int)v18);
  }
  (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
  ATL::CComVariant::Clear((ATL::CComVariant *)&v36);
  if ( Instance < 0 )
    goto LABEL_49;
  if ( (_DWORD)v34 )
  {
    v20 = a6;
    v39 = 0;
    (*(void (__fastcall **)(struct IOfflineFilesSyncProgressInternal *, unsigned int *))(*(_QWORD *)a6 + 24LL))(
      a6,
      &v39);
    (*(void (__fastcall **)(struct IOfflineFilesSyncProgressInternal *, _QWORD))(*(_QWORD *)v20 + 40LL))(
      v20,
      v39 != 0 ? 0x800704C7 : 0);
  }
  else
  {
    v34 = 0;
    Instance = CDefaultSyncConflictHandler::CreateInstance(v19, (void **)&v34);
    if ( Instance < 0 )
      goto LABEL_49;
    Instance = -2147024882;
    v21 = (CFastSyncControllerFactoryBase *)operator new(0x30u);
    v20 = a6;
    v22 = v21;
    if ( v21 )
    {
      CFastSyncControllerFactoryBase::CFastSyncControllerFactoryBase(v21, v34, a5, a6, 0);
      *((_DWORD *)v22 + 10) = a2;
      *(_QWORD *)v22 = &CEncryptionControllerFactory::`vftable';
      *((_DWORD *)v22 + 11) = a3;
      lpMem = 0;
      v39 = 0;
      Instance = CscEnum_QueryCachedSharePaths((unsigned __int16 ***)&lpMem, &v39);
      if ( Instance < 0 )
      {
        v27 = *(_QWORD *)v20;
        v39 = 0;
        (*(void (__fastcall **)(struct IOfflineFilesSyncProgressInternal *, unsigned int *))(v27 + 24))(v20, &v39);
        (*(void (__fastcall **)(struct IOfflineFilesSyncProgressInternal *, _QWORD))(*(_QWORD *)v20 + 40LL))(
          v20,
          v39 != 0 ? -2147023673 : 1);
      }
      else
      {
        v23 = (void **)lpMem;
        v24 = v39;
        v36 = GUID_NULL;
        v25 = 0;
        for ( Instance = CscSync_SyncWorker(a1, v22, 0, (const unsigned __int16 **)lpMem, v39, v20, &v36);
              (unsigned int)v25 < v24;
              v25 = (unsigned int)(v25 + 1) )
        {
          CscUtil_HeapFree(v23[v25], v26);
        }
        CscUtil_HeapFree(v23, v26);
      }
      (**(void (__fastcall ***)(CFastSyncControllerFactoryBase *, __int64))v22)(v22, 1);
    }
    ((void (__fastcall *)(struct IOfflineFilesSyncConflictHandler *))v34->lpVtbl->Release)(v34);
    if ( Instance < 0 )
      goto LABEL_49;
  }
  v28 = *(__int64 (__fastcall ***)(struct IOfflineFilesSyncProgressInternal *, GUID *, struct IOfflineFilesSyncConflictHandler **))v20;
  v34 = 0;
  v29 = (*v28)(v20, &IID_IOfflineFilesErrorCount, &v34);
  if ( v29 >= 0 )
  {
    v39 = 0;
    v29 = ((__int64 (__fastcall *)(struct IOfflineFilesSyncConflictHandler *, unsigned int *))v34->lpVtbl->ResolveConflict)(
            v34,
            &v39);
    if ( v29 >= 0 )
      v7 = v39 == 0;
    ((void (__fastcall *)(struct IOfflineFilesSyncConflictHandler *))v34->lpVtbl->Release)(v34);
  }
  if ( v29 < 0 )
    Instance = v29;
LABEL_49:
  v30 = 0;
  if ( v7 )
  {
    v40 = 0;
    v39 = 2;
    v31 = CscUmSetDatabase(&v39, 0, 0, 0, 0, 0, v33);
    v30 = v31;
    if ( v31 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_640353d05de230bd321f309b7bf8540c_Traceguids, v31);
    }
  }
LABEL_54:
  RtlNtStatusToDosError(v30);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000e51c  mov     rax, rsp
0x18000e51f  mov     [rax+10h], rbx
0x18000e523  mov     [rax+20h], r9
0x18000e527  mov     [rax+18h], r8d
0x18000e52b  mov     [rax+8], rcx
0x18000e52f  push    rbp
0x18000e530  push    rsi
0x18000e531  push    rdi
0x18000e532  push    r12
0x18000e534  push    r13
0x18000e536  push    r14
0x18000e538  push    r15
0x18000e53a  mov     rbp, rsp
0x18000e53d  sub     rsp, 70h
0x18000e541  mov     r12d, edx
0x18000e544  xor     r15d, r15d
0x18000e547  mov     ecx, r12d; int
0x18000e54a  mov     dword ptr [rbp+var_30], r15d
0x18000e54e  lea     rdx, [rbp+var_30]; int *
0x18000e552  mov     [rbp+arg_18], r15d
0x18000e556  mov     r13d, r15d
0x18000e559  call    ?CscLib_SetCacheEncryptionBeginStatus@@YAJHPEAH@Z; CscLib_SetCacheEncryptionBeginStatus(int,int *)
0x18000e55e  lea     r14, WPP_GLOBAL_Control
0x18000e565  mov     ebx, eax
0x18000e567  test    eax, eax
0x18000e569  js      loc_18000E99F
0x18000e56f  mov     esi, r15d
0x18000e572  lea     r13, off_18008A820; "AlwaysPinSubFolders"
0x18000e579  mov     r14d, 8007007Bh
0x18000e57f  mov     edi, r15d
0x18000e582  movsxd  rax, edi
0x18000e585  lea     rdx, String2; "EncryptCache"
0x18000e58c  lea     rcx, [rax+rax*2]
0x18000e590  add     rcx, rcx
0x18000e593  mov     rcx, [r13+rcx*8+0]; lpString1
0x18000e598  call    cs:__imp_lstrcmpiW
0x18000e59e  test    eax, eax
0x18000e5a0  mov     ebx, r15d
0x18000e5a3  cmovnz  ebx, r14d
0x18000e5a7  inc     edi
0x18000e5a9  mov     r14d, ebx
0x18000e5ac  cmp     edi, 42h ; 'B'
0x18000e5af  jb      short loc_18000E582
0x18000e5b1  mov     r13d, [rbp+arg_18]
0x18000e5b5  test    ebx, ebx
0x18000e5b7  js      loc_18000E79D
0x18000e5bd  mov     ecx, 40h ; '@'; Size
0x18000e5c2  mov     ebx, 8007000Eh
0x18000e5c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e5cc  test    rax, rax
0x18000e5cf  jz      loc_18000E993
0x18000e5d5  mov     rcx, rax; this
0x18000e5d8  call    ??0COfflineFilesSetting@@AEAA@XZ; COfflineFilesSetting::COfflineFilesSetting(void)
0x18000e5dd  mov     rdi, rax
0x18000e5e0  test    rax, rax
0x18000e5e3  jz      loc_18000E993
0x18000e5e9  cmp     [rax+38h], r15
0x18000e5ed  jnz     loc_18000E77C
0x18000e5f3  mov     ebx, 8007007Bh
0x18000e5f8  mov     [rax+38h], r15
0x18000e5fc  mov     r14d, r15d
0x18000e5ff  lea     r13, off_18008A820; "AlwaysPinSubFolders"
0x18000e606  movsxd  rax, r14d
0x18000e609  lea     rdx, String2; "EncryptCache"
0x18000e610  lea     r15, [rax+rax*2]
0x18000e614  shl     r15, 4
0x18000e618  add     r15, r13
0x18000e61b  mov     rcx, [r15]; lpString1
0x18000e61e  call    cs:__imp_lstrcmpiW
0x18000e624  test    eax, eax
0x18000e626  jnz     short loc_18000E634
0x18000e628  mov     [rdi+38h], r15
0x18000e62c  xor     r15d, r15d
0x18000e62f  mov     ebx, r15d
0x18000e632  jmp     short loc_18000E637
0x18000e634  xor     r15d, r15d
0x18000e637  inc     r14d
0x18000e63a  cmp     r14d, 42h ; 'B'
0x18000e63e  jb      short loc_18000E606
0x18000e640  mov     r13d, [rbp+arg_18]
0x18000e644  mov     eax, ebx
0x18000e646  cmp     ebx, 8007007Bh
0x18000e64c  jnz     loc_18000E781
0x18000e652  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e659  lea     rdx, WPP_GLOBAL_Control
0x18000e660  cmp     rcx, rdx
0x18000e663  jz      loc_18000E781
0x18000e669  test    dword ptr [rcx+1Ch], 10000h
0x18000e670  jz      loc_18000E781
0x18000e676  mov     rcx, [rcx+10h]
0x18000e67a  lea     r9, String2; "EncryptCache"
0x18000e681  mov     edx, 15h
0x18000e686  lea     r8, WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids
0x18000e68d  call    WPP_SF_S
0x18000e692  mov     rax, [rdi]
0x18000e695  mov     edx, 1
0x18000e69a  mov     rcx, rdi
0x18000e69d  mov     rax, [rax]
0x18000e6a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a5  lea     r14, WPP_GLOBAL_Control
0x18000e6ac  test    ebx, ebx
0x18000e6ae  js      loc_18000E993
0x18000e6b4  mov     eax, 3
0x18000e6b9  lea     rdx, [rbp+var_20]
0x18000e6bd  mov     word ptr [rbp+var_20.Data1], ax
0x18000e6c1  test    r12d, r12d
0x18000e6c4  mov     eax, r15d
0x18000e6c7  mov     r8d, 1
0x18000e6cd  setnz   al
0x18000e6d0  mov     rcx, rsi
0x18000e6d3  mov     dword ptr [rbp+var_20.Data4], eax
0x18000e6d6  mov     rax, [rsi]
0x18000e6d9  mov     rax, [rax+18h]
0x18000e6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6e2  mov     ebx, eax
0x18000e6e4  test    eax, eax
0x18000e6e6  jns     short loc_18000E712
0x18000e6e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6ef  cmp     rcx, r14
0x18000e6f2  jz      short loc_18000E712
0x18000e6f4  test    byte ptr [rcx+1Ch], 2
0x18000e6f8  jz      short loc_18000E712
0x18000e6fa  mov     rcx, [rcx+10h]
0x18000e6fe  lea     r8, WPP_7967f24143133d59f1b33f7a742017bc_Traceguids
0x18000e705  mov     edx, 0DBh
0x18000e70a  mov     r9d, eax
0x18000e70d  call    WPP_SF_d
0x18000e712  mov     rax, [rsi]
0x18000e715  mov     edx, 1
0x18000e71a  mov     rcx, rsi
0x18000e71d  mov     rax, [rax]
0x18000e720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e725  lea     rcx, [rbp+var_20]; this
0x18000e729  call    ?Clear@CComVariant@ATL@@QEAAJXZ; ATL::CComVariant::Clear(void)
0x18000e72e  test    ebx, ebx
0x18000e730  js      loc_18000E99F
0x18000e736  cmp     dword ptr [rbp+var_30], r15d
0x18000e73a  jz      loc_18000E7EE
0x18000e740  mov     rsi, [rbp+arg_28]
0x18000e744  lea     rdx, [rbp+arg_18]
0x18000e748  mov     rcx, rsi
0x18000e74b  mov     [rbp+arg_18], r15d
0x18000e74f  mov     rax, [rsi]
0x18000e752  mov     rax, [rax+18h]
0x18000e756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e75b  mov     ecx, [rbp+arg_18]
0x18000e75e  mov     rax, [rsi]
0x18000e761  neg     ecx
0x18000e763  mov     rcx, rsi
0x18000e766  sbb     edx, edx
0x18000e768  and     edx, 800704C7h
0x18000e76e  mov     rax, [rax+28h]
0x18000e772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e777  jmp     loc_18000E928
0x18000e77c  mov     eax, 80004005h
0x18000e781  mov     ebx, eax
0x18000e783  test    eax, eax
0x18000e785  js      loc_18000E692
0x18000e78b  lea     rax, [rdi+20h]
0x18000e78f  neg     rdi
0x18000e792  sbb     rsi, rsi
0x18000e795  and     rsi, rax
0x18000e798  jmp     loc_18000E6A5
0x18000e79d  cmp     ebx, 8007007Bh
0x18000e7a3  jnz     loc_18000E6A5
0x18000e7a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7b0  lea     r14, WPP_GLOBAL_Control
0x18000e7b7  cmp     rcx, r14
0x18000e7ba  jz      loc_18000E6AC
0x18000e7c0  test    dword ptr [rcx+1Ch], 10000h
0x18000e7c7  jz      loc_18000E6AC
0x18000e7cd  mov     rcx, [rcx+10h]
0x18000e7d1  lea     r9, String2; "EncryptCache"
0x18000e7d8  mov     edx, 16h
0x18000e7dd  lea     r8, WPP_8efcffa2381534b4e0c94c54ca70b20c_Traceguids
0x18000e7e4  call    WPP_SF_S
0x18000e7e9  jmp     loc_18000E6AC
0x18000e7ee  lea     rdx, [rbp+var_30]; void **
0x18000e7f2  mov     [rbp+var_30], r15
0x18000e7f6  call    ?CreateInstance@CDefaultSyncConflictHandler@@SAJAEBU_GUID@@PEAPEAX@Z; CDefaultSyncConflictHandler::CreateInstance(_GUID const &,void * *)
0x18000e7fb  mov     ebx, eax
0x18000e7fd  test    eax, eax
0x18000e7ff  js      loc_18000E99F
0x18000e805  mov     ecx, 30h ; '0'; Size
0x18000e80a  mov     ebx, 8007000Eh
0x18000e80f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e814  mov     rsi, [rbp+arg_28]
0x18000e818  mov     rdi, rax
0x18000e81b  test    rax, rax
0x18000e81e  jz      loc_18000E914
0x18000e824  mov     r8, [rbp+arg_20]; struct IOfflineFilesUserSessionCallback *
0x18000e828  mov     r9, rsi; struct IOfflineFilesSyncProgressInternal *
0x18000e82b  mov     rdx, [rbp+var_30]; struct IOfflineFilesSyncConflictHandler *
0x18000e82f  mov     rcx, rax; this
0x18000e832  mov     [rsp+70h+var_50], r15; struct _GUID *
0x18000e837  call    ??0CFastSyncControllerFactoryBase@@QEAA@PEAUIOfflineFilesSyncConflictHandler@@PEAUIOfflineFilesUserSessionCallback@@PEAUIOfflineFilesSyncProgressInternal@@PEAU_GUID@@@Z; CFastSyncControllerFactoryBase::CFastSyncControllerFactoryBase(IOfflineFilesSyncConflictHandler *,IOfflineFilesUserSessionCallback *,IOfflineFilesSyncProgressInternal *,_GUID *)
0x18000e83c  lea     rax, ??_7CEncryptionControllerFactory@@6B@; const CEncryptionControllerFactory::`vftable'
0x18000e843  mov     [rdi+28h], r12d
0x18000e847  mov     [rdi], rax
0x18000e84a  lea     rdx, [rbp+arg_18]; unsigned int *
0x18000e84e  mov     eax, [rbp+arg_10]
0x18000e851  lea     rcx, [rbp+lpMem]; unsigned __int16 ***
0x18000e855  mov     [rdi+2Ch], eax
0x18000e858  mov     [rbp+lpMem], r15
0x18000e85c  mov     [rbp+arg_18], r15d
0x18000e860  call    ?CscEnum_QueryCachedSharePaths@@YAJPEAPEAPEAGPEAK@Z; CscEnum_QueryCachedSharePaths(ushort * * *,ulong *)
0x18000e865  mov     ebx, eax
0x18000e867  test    eax, eax
0x18000e869  js      short loc_18000E8CC
0x18000e86b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000e872  mov     r15, [rbp+lpMem]
0x18000e876  lea     rax, [rbp+var_20]
0x18000e87a  mov     r12d, [rbp+arg_18]
0x18000e87e  mov     r9, r15; unsigned __int16 **
0x18000e881  mov     rcx, [rbp+arg_0]; HWND
0x18000e885  xor     r8d, r8d; struct CSyncAggregator *
0x18000e888  mov     [rsp+70h+var_40], rax; struct _GUID *
0x18000e88d  mov     rdx, rdi; struct CFastSyncControllerFactory *
0x18000e890  mov     [rsp+70h+var_48], rsi; struct IOfflineFilesSyncProgressInternal *
0x18000e895  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x18000e89a  mov     dword ptr [rsp+70h+var_50], r12d; unsigned int
0x18000e89f  call    ?CscSync_SyncWorker@@YAJPEAUHWND__@@PEAVCFastSyncControllerFactory@@PEAVCSyncAggregator@@PEAPEBGKPEAUIOfflineFilesSyncProgressInternal@@PEAU_GUID@@@Z; CscSync_SyncWorker(HWND__ *,CFastSyncControllerFactory *,CSyncAggregator *,ushort const * *,ulong,IOfflineFilesSyncProgressInternal *,_GUID *)
0x18000e8a4  xor     r14d, r14d
0x18000e8a7  mov     ebx, eax
0x18000e8a9  test    r12d, r12d
0x18000e8ac  jz      short loc_18000E8BF
0x18000e8ae  mov     rcx, [r15+r14*8]; lpMem
0x18000e8b2  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18000e8b7  inc     r14d
0x18000e8ba  cmp     r14d, r12d
0x18000e8bd  jb      short loc_18000E8AE
0x18000e8bf  mov     rcx, r15; lpMem
0x18000e8c2  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x18000e8c7  xor     r15d, r15d
0x18000e8ca  jmp     short loc_18000E901
0x18000e8cc  mov     rax, [rsi]
0x18000e8cf  lea     rdx, [rbp+arg_18]
0x18000e8d3  mov     rcx, rsi
0x18000e8d6  mov     [rbp+arg_18], r15d
0x18000e8da  mov     rax, [rax+18h]
0x18000e8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8e3  mov     ecx, [rbp+arg_18]
0x18000e8e6  mov     rax, [rsi]
0x18000e8e9  neg     ecx
0x18000e8eb  mov     rcx, rsi
0x18000e8ee  sbb     edx, edx
0x18000e8f0  and     edx, 800704C6h
0x18000e8f6  mov     rax, [rax+28h]
0x18000e8fa  inc     edx
0x18000e8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e901  mov     rax, [rdi]
0x18000e904  mov     edx, 1
0x18000e909  mov     rcx, rdi
0x18000e90c  mov     rax, [rax]
0x18000e90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e914  mov     rcx, [rbp+var_30]
0x18000e918  mov     rax, [rcx]
0x18000e91b  mov     rax, [rax+10h]
0x18000e91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e924  test    ebx, ebx
0x18000e926  js      short loc_18000E998
0x18000e928  mov     rax, [rsi]
0x18000e92b  lea     r8, [rbp+var_30]
0x18000e92f  lea     rdx, IID_IOfflineFilesErrorCount
0x18000e936  mov     [rbp+var_30], r15
0x18000e93a  mov     rcx, rsi
0x18000e93d  mov     rax, [rax]
0x18000e940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e945  mov     edi, eax
0x18000e947  test    eax, eax
0x18000e949  js      short loc_18000E984
0x18000e94b  mov     rcx, [rbp+var_30]
0x18000e94f  lea     rdx, [rbp+arg_18]
0x18000e953  mov     [rbp+arg_18], r15d
0x18000e957  mov     rax, [rcx]
0x18000e95a  mov     rax, [rax+18h]
0x18000e95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e963  mov     edi, eax
0x18000e965  test    eax, eax
0x18000e967  js      short loc_18000E974
0x18000e969  cmp     [rbp+arg_18], r15d
0x18000e96d  mov     r13d, r15d
0x18000e970  setz    r13b
0x18000e974  mov     rcx, [rbp+var_30]
0x18000e978  mov     rax, [rcx]
0x18000e97b  mov     rax, [rax+10h]
0x18000e97f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e984  lea     r14, WPP_GLOBAL_Control
0x18000e98b  test    edi, edi
0x18000e98d  jns     short loc_18000E99F
0x18000e98f  mov     ebx, edi
0x18000e991  jmp     short loc_18000E99F
0x18000e993  mov     edi, r15d
0x18000e996  jmp     short loc_18000E9FD
0x18000e998  lea     r14, WPP_GLOBAL_Control
0x18000e99f  mov     edi, r15d
0x18000e9a2  test    r13d, r13d
0x18000e9a5  jz      short loc_18000E9FD
0x18000e9a7  mov     qword ptr [rbp+arg_18], r15
0x18000e9ab  lea     rcx, [rbp+arg_18]
  ... truncated ...
```
