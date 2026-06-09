# InitializePluginCacheRoots(HKEY__ *,ushort *,ushort const *,ushort * *,HKEY__ * *)

- ea: `0x18001b1ec`
- end: `0x18001b4b6`
- name: `?InitializePluginCacheRoots@@YAJPEAUHKEY__@@PEAGPEBGPEAPEAGPEAPEAU1@@Z`
- size: `714`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, const unsigned __int16 *, unsigned __int16 **, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a624`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18001b1ec`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b34d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b34d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001b343`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001b343`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b49d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b49d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b3ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b3ca`

## string_xrefs

- `0x18001b450`: `pwszCacheDir`
- `0x18001b269`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001b2f6`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001b369`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001b3e1`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001b42d`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001b380`: `CreateDirectoryW`
- `0x18001b3ff`: `RegCreateKeyEx`

## pseudocode

```c
__int64 __fastcall InitializePluginCacheRoots(
        HKEY hKey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        HKEY *a5)
{
  HKEY *v5; // r15
  __int64 v10; // rax
  __int64 v11; // r10
  unsigned int v12; // ebp
  unsigned __int16 *v13; // rax
  const char *v14; // rdi
  unsigned __int16 *v15; // rsi
  unsigned int v16; // ebx
  const char *v17; // r9
  const char *v18; // rax
  bool v19; // zf
  const char *v20; // r9
  signed int LastError; // eax
  const char *v22; // r9
  LSTATUS v23; // eax
  const char *v24; // r9
  HKEY v25; // rax
  const char *v26; // rax
  bool v27; // zf
  DWORD dwOptions[2]; // [rsp+20h] [rbp-88h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-88h]
  HKEY hKeya; // [rsp+50h] [rbp-58h] BYREF
  DWORD dwDisposition; // [rsp+C8h] [rbp+20h] BYREF

  v5 = a5;
  dwDisposition = 0;
  hKeya = 0;
  v10 = -1;
  *a4 = 0;
  v11 = -1;
  *v5 = 0;
  do
    ++v11;
  while ( a3[v11] );
  do
    ++v10;
  while ( g_pwszCacheRootDirectory[v10] );
  v12 = 2 * (v11 + v10) + 4;
  v13 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(v12);
  v14 = "";
  v15 = v13;
  if ( !v13 )
  {
    v16 = -1073741801;
    v17 = "";
    do
    {
      v18 = v17--;
      v19 = *v17 == 92;
      if ( *v17 == 92 )
        goto LABEL_9;
    }
    while ( v17 > "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" );
    v19 = *v17 == 92;
LABEL_9:
    if ( v19 )
      v17 = v18;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v17, 59, "AllocateLsaHeap", &Class);
    goto LABEL_24;
  }
  v16 = RtlStringCchPrintfW(v13, (unsigned __int64)v12 >> 1, L"%ws\\%ws", g_pwszCacheRootDirectory, a3);
  if ( v16 )
  {
    v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    dwOptionsa[0] = 68;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v16, v20, *(_QWORD *)dwOptionsa, "RtlStringCchPrintfW", &Class);
  }
  else if ( CreateDirectoryW(v15, 0) || (LastError = GetLastError(), v16 = LastError, LastError == 183) )
  {
    v23 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKeya, &dwDisposition);
    v16 = v23;
    if ( v23 )
    {
      if ( v23 > 0 )
        v16 = (unsigned __int16)v23 | 0xC0070000;
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      dwOptions[0] = 99;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v16, v24, *(_QWORD *)dwOptions, L"RegCreateKeyEx", &Class);
    }
    else
    {
      v25 = hKeya;
      v16 = 0;
      *a4 = v15;
      v15 = 0;
      *v5 = v25;
      hKeya = 0;
    }
  }
  else
  {
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0xC0070000;
    v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    dwOptionsa[0] = 82;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v16, v22, *(_QWORD *)dwOptionsa, "CreateDirectoryW", v15);
  }
LABEL_24:
  while ( 1 )
  {
    v26 = v14--;
    v27 = *v14 == 92;
    if ( *v14 == 92 )
      break;
    if ( v14 <= "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" )
    {
      v27 = *v14 == 92;
      break;
    }
  }
  if ( v27 )
    v14 = v26;
  dwOptions[0] = 110;
  WPPTraceLogA(2, "0x%08x %s:%u : %s:%ws", v16, v14, *(_QWORD *)dwOptions, "pwszCacheDir", v15);
  if ( v15 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v15);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v16;
}

```

## disassembly

```asm
0x18001b1ec  mov     rax, rsp
0x18001b1ef  push    rbx
0x18001b1f0  push    rbp
0x18001b1f1  push    rsi
0x18001b1f2  push    rdi
0x18001b1f3  push    r12
0x18001b1f5  push    r13
0x18001b1f7  push    r14
0x18001b1f9  push    r15
0x18001b1fb  sub     rsp, 68h
0x18001b1ff  mov     r15, [rsp+0A8h+arg_20]
0x18001b207  mov     r12, rdx
0x18001b20a  xor     edx, edx
0x18001b20c  mov     r14, r9
0x18001b20f  mov     [rax+20h], edx
0x18001b212  mov     rbx, r8
0x18001b215  mov     [rax-58h], rdx
0x18001b219  mov     r13, rcx
0x18001b21c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b220  mov     [r9], rdx
0x18001b223  mov     r10, rax
0x18001b226  mov     [r15], rdx
0x18001b229  inc     r10
0x18001b22c  cmp     [r8+r10*2], dx
0x18001b231  jnz     short loc_18001B229
0x18001b233  mov     rcx, cs:?g_pwszCacheRootDirectory@@3PEAGEA; ushort * g_pwszCacheRootDirectory
0x18001b23a  inc     rax
0x18001b23d  cmp     [rcx+rax*2], dx
0x18001b241  jnz     short loc_18001B23A
0x18001b243  add     eax, r10d
0x18001b246  lea     ebp, ds:4[rax*2]
0x18001b24d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001b254  mov     ecx, ebp
0x18001b256  mov     rax, [rax+28h]
0x18001b25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b25f  lea     rdi, aOnecoreDsExtCl+2Eh; ""
0x18001b266  mov     rsi, rax
0x18001b269  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001b270  test    rax, rax
0x18001b273  jnz     short loc_18001B2CE
0x18001b275  mov     ebx, 0C0000017h
0x18001b27a  mov     r9, rdi
0x18001b27d  mov     rax, r9
0x18001b280  dec     r9
0x18001b283  cmp     byte ptr [r9], 5Ch ; '\'
0x18001b287  jz      short loc_18001B292
0x18001b289  cmp     r9, rcx
0x18001b28c  ja      short loc_18001B27D
0x18001b28e  cmp     byte ptr [r9], 5Ch ; '\'
0x18001b292  cmovz   r9, rax
0x18001b296  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001b29d  lea     rax, Class
0x18001b2a4  mov     r8d, ebx
0x18001b2a7  mov     [rsp+0A8h+lpSecurityAttributes], rax
0x18001b2ac  xor     ecx, ecx
0x18001b2ae  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18001b2b5  mov     qword ptr [rsp+0A8h+samDesired], rax
0x18001b2ba  mov     [rsp+0A8h+dwOptions], 3Bh ; ';'
0x18001b2c2  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001b2c7  xor     ebp, ebp
0x18001b2c9  jmp     loc_18001B42D
0x18001b2ce  mov     r9, cs:?g_pwszCacheRootDirectory@@3PEAGEA; ushort * g_pwszCacheRootDirectory
0x18001b2d5  lea     r8, aWsWs_1; "%ws\\%ws"
0x18001b2dc  mov     edx, ebp
0x18001b2de  mov     rcx, rsi; unsigned __int16 *
0x18001b2e1  shr     rdx, 1; unsigned __int64
0x18001b2e4  mov     qword ptr [rsp+0A8h+dwOptions], rbx
0x18001b2e9  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b2ee  xor     ebp, ebp
0x18001b2f0  mov     ebx, eax
0x18001b2f2  test    eax, eax
0x18001b2f4  jz      short loc_18001B33E
0x18001b2f6  lea     r14, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001b2fd  mov     rcx, r14; char *
0x18001b300  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001b305  mov     r9, rax
0x18001b308  lea     rax, Class
0x18001b30f  mov     [rsp+0A8h+lpSecurityAttributes], rax
0x18001b314  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18001b31b  mov     qword ptr [rsp+0A8h+samDesired], rax
0x18001b320  mov     [rsp+0A8h+dwOptions], 44h ; 'D'
0x18001b328  mov     r8d, ebx
0x18001b32b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001b332  xor     ecx, ecx
0x18001b334  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001b339  jmp     loc_18001B434
0x18001b33e  xor     edx, edx; lpSecurityAttributes
0x18001b340  mov     rcx, rsi; lpPathName
0x18001b343  call    cs:__imp_CreateDirectoryW
0x18001b349  test    eax, eax
0x18001b34b  jnz     short loc_18001B396
0x18001b34d  call    cs:__imp_GetLastError
0x18001b353  mov     ebx, eax
0x18001b355  cmp     eax, 0B7h
0x18001b35a  jz      short loc_18001B396
0x18001b35c  test    eax, eax
0x18001b35e  jle     short loc_18001B369
0x18001b360  movzx   ebx, ax
0x18001b363  or      ebx, 0C0070000h
0x18001b369  lea     r14, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001b370  mov     rcx, r14; char *
0x18001b373  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001b378  mov     [rsp+0A8h+lpSecurityAttributes], rsi
0x18001b37d  mov     r9, rax
0x18001b380  lea     rax, aCreatedirector; "CreateDirectoryW"
0x18001b387  mov     qword ptr [rsp+0A8h+samDesired], rax
0x18001b38c  mov     [rsp+0A8h+dwOptions], 52h ; 'R'
0x18001b394  jmp     short loc_18001B328
0x18001b396  lea     rax, [rsp+0A8h+dwDisposition]
0x18001b39e  xor     r9d, r9d; lpClass
0x18001b3a1  mov     [rsp+0A8h+lpdwDisposition], rax; lpdwDisposition
0x18001b3a6  xor     r8d, r8d; Reserved
0x18001b3a9  lea     rax, [rsp+0A8h+hKey]
0x18001b3ae  mov     rdx, r12; lpSubKey
0x18001b3b1  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18001b3b6  mov     rcx, r13; hKey
0x18001b3b9  mov     [rsp+0A8h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18001b3be  mov     [rsp+0A8h+samDesired], 0F003Fh; samDesired
0x18001b3c6  mov     [rsp+0A8h+dwOptions], ebp; dwOptions
0x18001b3ca  call    cs:__imp_RegCreateKeyExW
0x18001b3d0  mov     ebx, eax
0x18001b3d2  test    eax, eax
0x18001b3d4  jz      short loc_18001B418
0x18001b3d6  jle     short loc_18001B3E1
0x18001b3d8  movzx   ebx, ax
0x18001b3db  or      ebx, 0C0070000h
0x18001b3e1  lea     r14, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001b3e8  mov     rcx, r14; char *
0x18001b3eb  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001b3f0  mov     r9, rax
0x18001b3f3  lea     rax, Class
0x18001b3fa  mov     [rsp+0A8h+lpSecurityAttributes], rax
0x18001b3ff  lea     rax, aRegcreatekeyex_0; "RegCreateKeyEx"
0x18001b406  mov     qword ptr [rsp+0A8h+samDesired], rax
0x18001b40b  mov     [rsp+0A8h+dwOptions], 63h ; 'c'
0x18001b413  jmp     loc_18001B328
0x18001b418  mov     rax, [rsp+0A8h+hKey]
0x18001b41d  mov     ebx, ebp
0x18001b41f  mov     [r14], rsi
0x18001b422  mov     rsi, rbp
0x18001b425  mov     [r15], rax
0x18001b428  mov     [rsp+0A8h+hKey], rbp
0x18001b42d  lea     r14, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001b434  mov     rax, rdi
0x18001b437  dec     rdi
0x18001b43a  cmp     byte ptr [rdi], 5Ch ; '\'
0x18001b43d  jz      short loc_18001B447
0x18001b43f  cmp     rdi, r14
0x18001b442  ja      short loc_18001B434
0x18001b444  cmp     byte ptr [rdi], 5Ch ; '\'
0x18001b447  cmovz   rdi, rax
0x18001b44b  mov     [rsp+0A8h+lpSecurityAttributes], rsi
0x18001b450  lea     rax, aPwszcachedir; "pwszCacheDir"
0x18001b457  mov     r9, rdi
0x18001b45a  mov     qword ptr [rsp+0A8h+samDesired], rax
0x18001b45f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18001b466  mov     r8d, ebx
0x18001b469  mov     [rsp+0A8h+dwOptions], 6Eh ; 'n'
0x18001b471  mov     ecx, 2
0x18001b476  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18001b47b  test    rsi, rsi
0x18001b47e  jz      short loc_18001B493
0x18001b480  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001b487  mov     rcx, rsi
0x18001b48a  mov     rax, [rax+30h]
0x18001b48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b493  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001b498  test    rcx, rcx
0x18001b49b  jz      short loc_18001B4A3
0x18001b49d  call    cs:__imp_RegCloseKey
0x18001b4a3  mov     eax, ebx
0x18001b4a5  add     rsp, 68h
0x18001b4a9  pop     r15
0x18001b4ab  pop     r14
0x18001b4ad  pop     r13
0x18001b4af  pop     r12
0x18001b4b1  pop     rdi
0x18001b4b2  pop     rsi
0x18001b4b3  pop     rbp
0x18001b4b4  pop     rbx
0x18001b4b5  retn
```
