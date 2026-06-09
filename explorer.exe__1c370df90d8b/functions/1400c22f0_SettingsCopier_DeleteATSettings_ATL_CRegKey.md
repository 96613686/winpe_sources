# SettingsCopier::DeleteATSettings(ATL::CRegKey &)

- ea: `0x1400c22f0`
- end: `0x1400c25e5`
- name: `?DeleteATSettings@SettingsCopier@@CAJAEAVCRegKey@ATL@@@Z`
- size: `757`
- prototype: `__int64 __fastcall(HKEY *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1401bf1f0`

## callees

- `0x1400158a4`
- `0x1400847f8`
- `0x1400c22f0`
- `0x1400c25ec`
- `0x1401b893c`
- `0x1401b8aec`
- `0x1401b9574`
- `0x1401ba6b4`
- `0x1401bfa88`
- `0x1401bfb4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c23f6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c2427`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c2499`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c256b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c259c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c25b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c25c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c23f6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c2427`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c2499`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c256b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c259c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c25b3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400c25c1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400c2553`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400c2553`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400c2470`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400c2470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c247e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400c247e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c24cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c2505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c255e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c24cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c2505`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400c255e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1400c24f5`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1400c24f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c250f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c2548`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c250f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400c2548`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400c24bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400c24bf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400c258e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400c258e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400c253b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400c253b`

## string_xrefs

- `0x1400c2530`: `SymbolicLinkValue`
- `0x1400c23ad`: `%s\ATConfig`
- `0x1400c240a`: `%s\ATConfig`
- `0x1400c245b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATConfig`

## pseudocode

```c
__int64 __fastcall SettingsCopier::DeleteATSettings(HKEY *a1)
{
  void *v2; // rbx
  __int64 v3; // rdx
  _QWORD *v4; // rcx
  unsigned __int16 *v5; // rdi
  int *v6; // rbx
  __int64 v7; // rdi
  unsigned int v8; // r11d
  unsigned __int64 v9; // rbx
  LSTATUS v10; // r14d
  unsigned __int64 v11; // rdx
  __int64 v13; // rsi
  const WCHAR *v14; // r14
  void *v15; // rcx
  HANDLE EventW; // r15
  signed int LastError; // eax
  DWORD v18; // esi
  LSTATUS v19; // eax
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v23; // [rsp+48h] [rbp-18h] BYREF
  __int64 v24; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int16 *v27; // [rsp+B8h] [rbp+58h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v27);
  v22 = 0;
  v23 = 0;
  v2 = 0;
  Block = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( !CATUtils::IsInteractiveUser() )
  {
    v13 = -2147483647;
    v14 = SettingsCopier::_ATConfigKeyString;
    v5 = v27;
LABEL_17:
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError <= 0 )
      {
LABEL_21:
        free(v2);
        goto LABEL_37;
      }
      v10 = (unsigned __int16)LastError;
LABEL_20:
      v10 |= 0x80070000;
      goto LABEL_21;
    }
    v10 = RegOpenKeyExW((HKEY)v13, v14, 8u, 0x20019u, &hKey);
    if ( v10 )
    {
      CloseHandle(EventW);
LABEL_24:
      if ( v10 <= 0 )
        goto LABEL_21;
      v10 = (unsigned __int16)v10;
      goto LABEL_20;
    }
    v10 = RegNotifyChangeKeyValue(hKey, 0, 5u, EventW, 1);
    if ( v10 )
    {
      CloseHandle(EventW);
      RegCloseKey(hKey);
      goto LABEL_24;
    }
    v10 = RegQueryValueExW(hKey, L"SymbolicLinkValue", 0, &Type, 0, &cbData);
    RegCloseKey(hKey);
    v18 = WaitForSingleObject(EventW, 0);
    CloseHandle(EventW);
    if ( !v18 )
    {
      free(v2);
      v10 = -2147023590;
      goto LABEL_37;
    }
    if ( v10 )
    {
      if ( v10 != 2 )
        goto LABEL_24;
    }
    else if ( Type == 6 )
    {
      free(v2);
      v10 = -2147023432;
      goto LABEL_37;
    }
    v19 = RegDeleteTreeW(*a1, 0);
    v15 = v2;
    if ( !v19 )
    {
      free(v2);
      v10 = 0;
      goto LABEL_37;
    }
LABEL_33:
    free(v15);
    v10 = -2147467259;
    goto LABEL_37;
  }
  v3 = *(_QWORD *)CATUtils::SessionKeyString(&v24);
  v4 = (_QWORD *)(v3 - 24);
  v5 = v27;
  v6 = (int *)(v27 - 12);
  if ( (unsigned __int16 *)(v3 - 24) != v27 - 12 )
  {
    if ( v6[4] >= 0 && *v4 == *(_QWORD *)v6 )
    {
      v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v4);
      ATL::CStringData::Release((ATL::CStringData *)v6);
      v5 = (unsigned __int16 *)(v7 + 24);
      v27 = v5;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v27, v3, *(unsigned int *)(v3 - 16));
      v5 = v27;
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  if ( (int)StringCchLengthW(SettingsCopier::_ATSessionConfigKeyString, 0x7FFFFFFFu, &v22) < 0
    || (int)StringCchLengthW(v5, v8, &v23) < 0
    || (v9 = v22 + v23, v22 + v23 < v22) )
  {
    v15 = 0;
    goto LABEL_33;
  }
  if ( (unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v22 + v23) )
  {
    v11 = v9;
    v2 = Block;
    if ( (int)StringCchPrintfW((unsigned __int16 *)Block, v11, SettingsCopier::_ATSessionConfigKeyString, v5) < 0 )
    {
      free(v2);
      ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
      return 2147500037LL;
    }
    v13 = -2147483646;
    v14 = (const WCHAR *)v2;
    goto LABEL_17;
  }
  free(Block);
  v10 = -2147024882;
LABEL_37:
  ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400c22f0  push    rbp
0x1400c22f2  push    rbx
0x1400c22f3  push    rsi
0x1400c22f4  push    rdi
0x1400c22f5  push    r12
0x1400c22f7  push    r14
0x1400c22f9  push    r15
0x1400c22fb  mov     rbp, rsp
0x1400c22fe  sub     rsp, 60h
0x1400c2302  mov     r12, rcx
0x1400c2305  lea     rcx, [rbp+arg_18]
0x1400c2309  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1400c230e  nop
0x1400c230f  mov     [rbp+var_20], 0
0x1400c2317  mov     [rbp+var_18], 0
0x1400c231f  xor     ebx, ebx
0x1400c2321  mov     [rbp+Block], rbx
0x1400c2325  mov     [rbp+hKey], rbx
0x1400c2329  mov     [rbp+Type], ebx
0x1400c232c  mov     [rbp+cbData], ebx
0x1400c232f  call    ?IsInteractiveUser@CATUtils@@SAHXZ; CATUtils::IsInteractiveUser(void)
0x1400c2334  test    eax, eax
0x1400c2336  jz      loc_1400C2454
0x1400c233c  lea     rcx, [rbp+var_10]
0x1400c2340  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x1400c2345  nop
0x1400c2346  mov     rdx, [rax]
0x1400c2349  lea     rcx, [rdx-18h]
0x1400c234d  mov     rdi, [rbp+arg_18]
0x1400c2351  lea     rbx, [rdi-18h]
0x1400c2355  cmp     rcx, rbx
0x1400c2358  jz      short loc_1400C2393
0x1400c235a  cmp     dword ptr [rbx+10h], 0
0x1400c235e  jl      short loc_1400C2382
0x1400c2360  mov     rax, [rbx]
0x1400c2363  cmp     [rcx], rax
0x1400c2366  jnz     short loc_1400C2382
0x1400c2368  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1400c236d  mov     rdi, rax
0x1400c2370  mov     rcx, rbx; this
0x1400c2373  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c2378  add     rdi, 18h
0x1400c237c  mov     [rbp+arg_18], rdi
0x1400c2380  jmp     short loc_1400C2393
0x1400c2382  mov     r8d, [rdx-10h]
0x1400c2386  lea     rcx, [rbp+arg_18]
0x1400c238a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400c238f  mov     rdi, [rbp+arg_18]
0x1400c2393  mov     rcx, [rbp+var_10]
0x1400c2397  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1400c239b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c23a0  lea     r8, [rbp+var_20]; unsigned __int64 *
0x1400c23a4  mov     r11d, 7FFFFFFFh
0x1400c23aa  mov     edx, r11d; unsigned __int64
0x1400c23ad  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x1400c23b4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400c23b9  test    eax, eax
0x1400c23bb  js      loc_1400C244D
0x1400c23c1  lea     r8, [rbp+var_18]; unsigned __int64 *
0x1400c23c5  mov     edx, r11d; unsigned __int64
0x1400c23c8  mov     rcx, rdi; unsigned __int16 *
0x1400c23cb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1400c23d0  test    eax, eax
0x1400c23d2  js      short loc_1400C244D
0x1400c23d4  mov     rbx, [rbp+var_18]
0x1400c23d8  add     rbx, [rbp+var_20]
0x1400c23dc  cmp     rbx, [rbp+var_20]
0x1400c23e0  jb      short loc_1400C244D
0x1400c23e2  mov     rdx, rbx
0x1400c23e5  lea     rcx, [rbp+Block]
0x1400c23e9  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1400c23ee  test    al, al
0x1400c23f0  jnz     short loc_1400C2407
0x1400c23f2  mov     rcx, [rbp+Block]; Block
0x1400c23f6  call    cs:__imp_free
0x1400c23fc  mov     r14d, 8007000Eh
0x1400c2402  jmp     loc_1400C25CA
0x1400c2407  mov     r9, rdi
0x1400c240a  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x1400c2411  mov     rdx, rbx; unsigned __int64
0x1400c2414  mov     rbx, [rbp+Block]
0x1400c2418  mov     rcx, rbx; unsigned __int16 *
0x1400c241b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400c2420  test    eax, eax
0x1400c2422  jns     short loc_1400C2441
0x1400c2424  mov     rcx, rbx; Block
0x1400c2427  call    cs:__imp_free
0x1400c242d  nop
0x1400c242e  lea     rcx, [rdi-18h]; this
0x1400c2432  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c2437  mov     eax, 80004005h
0x1400c243c  jmp     loc_1400C25D6
0x1400c2441  mov     rsi, 0FFFFFFFF80000002h
0x1400c2448  mov     r14, rbx
0x1400c244b  jmp     short loc_1400C2466
0x1400c244d  xor     ecx, ecx
0x1400c244f  jmp     loc_1400C259C
0x1400c2454  mov     rsi, 0FFFFFFFF80000001h
0x1400c245b  lea     r14, ?_ATConfigKeyString@SettingsCopier@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400c2462  mov     rdi, [rbp+arg_18]
0x1400c2466  xor     r9d, r9d; lpName
0x1400c2469  xor     r8d, r8d; bInitialState
0x1400c246c  xor     edx, edx; bManualReset
0x1400c246e  xor     ecx, ecx; lpEventAttributes
0x1400c2470  call    cs:__imp_CreateEventW
0x1400c2476  mov     r15, rax
0x1400c2479  test    rax, rax
0x1400c247c  jnz     short loc_1400C24A4
0x1400c247e  call    cs:__imp_GetLastError
0x1400c2484  mov     r14d, eax
0x1400c2487  test    eax, eax
0x1400c2489  jle     short loc_1400C2496
0x1400c248b  movzx   r14d, ax
0x1400c248f  or      r14d, 80070000h
0x1400c2496  mov     rcx, rbx; Block
0x1400c2499  call    cs:__imp_free
0x1400c249f  jmp     loc_1400C25CA
0x1400c24a4  lea     rax, [rbp+hKey]
0x1400c24a8  mov     [rsp+60h+phkResult], rax; phkResult
0x1400c24ad  mov     r9d, 20019h; samDesired
0x1400c24b3  mov     r8d, 8; ulOptions
0x1400c24b9  mov     rdx, r14; lpSubKey
0x1400c24bc  mov     rcx, rsi; hKey
0x1400c24bf  call    cs:__imp_RegOpenKeyExW
0x1400c24c5  mov     r14d, eax
0x1400c24c8  test    eax, eax
0x1400c24ca  jz      short loc_1400C24E0
0x1400c24cc  mov     rcx, r15; hObject
0x1400c24cf  call    cs:__imp_CloseHandle
0x1400c24d5  test    r14d, r14d
0x1400c24d8  jle     short loc_1400C2496
0x1400c24da  movzx   r14d, r14w
0x1400c24de  jmp     short loc_1400C248F
0x1400c24e0  mov     dword ptr [rsp+60h+phkResult], 1; fAsynchronous
0x1400c24e8  mov     r9, r15; hEvent
0x1400c24eb  xor     edx, edx; bWatchSubtree
0x1400c24ed  lea     r8d, [rdx+5]; dwNotifyFilter
0x1400c24f1  mov     rcx, [rbp+hKey]; hKey
0x1400c24f5  call    cs:__imp_RegNotifyChangeKeyValue
0x1400c24fb  mov     r14d, eax
0x1400c24fe  test    eax, eax
0x1400c2500  jz      short loc_1400C2517
0x1400c2502  mov     rcx, r15; hObject
0x1400c2505  call    cs:__imp_CloseHandle
0x1400c250b  mov     rcx, [rbp+hKey]; hKey
0x1400c250f  call    cs:__imp_RegCloseKey
0x1400c2515  jmp     short loc_1400C24D5
0x1400c2517  lea     rax, [rbp+cbData]
0x1400c251b  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1400c2520  mov     [rsp+60h+phkResult], 0; lpData
0x1400c2529  lea     r9, [rbp+Type]; lpType
0x1400c252d  xor     r8d, r8d; lpReserved
0x1400c2530  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x1400c2537  mov     rcx, [rbp+hKey]; hKey
0x1400c253b  call    cs:__imp_RegQueryValueExW
0x1400c2541  mov     r14d, eax
0x1400c2544  mov     rcx, [rbp+hKey]; hKey
0x1400c2548  call    cs:__imp_RegCloseKey
0x1400c254e  xor     edx, edx; dwMilliseconds
0x1400c2550  mov     rcx, r15; hHandle
0x1400c2553  call    cs:__imp_WaitForSingleObject
0x1400c2559  mov     esi, eax
0x1400c255b  mov     rcx, r15; hObject
0x1400c255e  call    cs:__imp_CloseHandle
0x1400c2564  test    esi, esi
0x1400c2566  jnz     short loc_1400C2579
0x1400c2568  mov     rcx, rbx; Block
0x1400c256b  call    cs:__imp_free
0x1400c2571  mov     r14d, 8007051Ah
0x1400c2577  jmp     short loc_1400C25CA
0x1400c2579  test    r14d, r14d
0x1400c257c  jz      short loc_1400C25AA
0x1400c257e  cmp     r14d, 2
0x1400c2582  jnz     loc_1400C24D5
0x1400c2588  xor     edx, edx; lpSubKey
0x1400c258a  mov     rcx, [r12]; hKey
0x1400c258e  call    cs:__imp_RegDeleteTreeW
0x1400c2594  nop
0x1400c2595  mov     rcx, rbx; Block
0x1400c2598  test    eax, eax
0x1400c259a  jz      short loc_1400C25C1
0x1400c259c  call    cs:__imp_free
0x1400c25a2  mov     r14d, 80004005h
0x1400c25a8  jmp     short loc_1400C25CA
0x1400c25aa  cmp     [rbp+Type], 6
0x1400c25ae  jnz     short loc_1400C2588
0x1400c25b0  mov     rcx, rbx; Block
0x1400c25b3  call    cs:__imp_free
0x1400c25b9  mov     r14d, 800705B8h
0x1400c25bf  jmp     short loc_1400C25CA
0x1400c25c1  call    cs:__imp_free
0x1400c25c7  xor     r14d, r14d
0x1400c25ca  lea     rcx, [rdi-18h]; this
0x1400c25ce  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1400c25d3  mov     eax, r14d
0x1400c25d6  add     rsp, 60h
0x1400c25da  pop     r15
0x1400c25dc  pop     r14
0x1400c25de  pop     r12
0x1400c25e0  pop     rdi
0x1400c25e1  pop     rsi
0x1400c25e2  pop     rbx
0x1400c25e3  pop     rbp
0x1400c25e4  retn
```
