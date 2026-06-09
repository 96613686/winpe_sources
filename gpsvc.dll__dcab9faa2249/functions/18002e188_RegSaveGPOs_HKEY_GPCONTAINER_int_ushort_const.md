# RegSaveGPOs(HKEY__ *,_GPCONTAINER *,int,ushort const *)

- ea: `0x18002e188`
- end: `0x18002e597`
- name: `?RegSaveGPOs@@YAKPEAUHKEY__@@PEAU_GPCONTAINER@@HPEBG@Z`
- size: `1039`
- prototype: `unsigned int __fastcall(HKEY hKey, struct _GPCONTAINER *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18009dfc8`

## callees

- `0x18001dcf0`
- `0x18002e188`
- `0x18002f6e0`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18002e22f`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18002e22f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e571`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e29f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e2ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e2fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e33a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e369`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e3c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e427`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e492`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e4f5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e29f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e2ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e2fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e33a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e369`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e3c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e427`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e492`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002e4f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e1fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e262`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e1fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002e262`

## string_xrefs

- `0x18002e2f6`: `AccessDenied`

## pseudocode

```c
__int64 __fastcall RegSaveGPOs(HKEY hKey, const BYTE *a2, int a3, const unsigned __int16 *a4)
{
  unsigned int v8; // ebx
  int i; // esi
  wchar_t *v10; // rax
  LSTATUS v11; // eax
  HKEY v12; // rcx
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // r9
  __int64 v16; // rcx
  const BYTE *v17; // r9
  __int64 v18; // r9
  __int64 v19; // rcx
  const BYTE *v20; // r9
  bool v21; // zf
  const WCHAR *v22; // r9
  __int64 v23; // rcx
  const BYTE *v24; // r9
  const WCHAR *v25; // r9
  __int64 v26; // rcx
  const BYTE *v27; // r9
  LSTATUS v28; // eax
  DWORD cbData; // [rsp+50h] [rbp-49h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-41h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-39h] BYREF
  wchar_t Buffer[32]; // [rsp+70h] [rbp-29h] BYREF

  v8 = GPRegDelnode(hKey, a4);
  if ( !v8 )
  {
    hKeya = 0;
    v8 = RegCreateKeyExW(hKey, a4, 0, 0, 0, 0xF003Fu, 0, &hKeya, 0);
    if ( !v8 )
    {
      for ( i = 0; a2; ++i )
      {
        phkResult = 0;
        v10 = _itow(i, Buffer, 16);
        v8 = RegCreateKeyExW(hKeya, v10, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
        if ( v8 )
          break;
        v11 = RegSetValueExW(phkResult, L"Version", 0, 4u, &a2[(-(__int64)(a3 != 0) & 4) + 48], 4u);
        v12 = phkResult;
        v8 = v11;
        if ( v11 )
          goto LABEL_39;
        v13 = RegSetValueExW(phkResult, L"WQLFilterPass", 0, 4u, a2 + 68, 4u);
        v12 = phkResult;
        v8 = v13;
        if ( v13 )
          goto LABEL_39;
        v8 = RegSetValueExW(phkResult, L"AccessDenied", 0, 4u, a2 + 36, 4u);
        if ( v8 )
          goto LABEL_38;
        v14 = RegSetValueExW(phkResult, L"GPO-Disabled", 0, 4u, &a2[(-(__int64)(a3 != 0) & 4) + 40], 4u);
        v12 = phkResult;
        v8 = v14;
        if ( v14 )
          goto LABEL_39;
        v8 = RegSetValueExW(phkResult, L"Options", 0, 4u, a2 + 88, 4u);
        if ( v8 )
          goto LABEL_38;
        v15 = *((_QWORD *)a2 + 1);
        v16 = -1;
        cbData = 0;
        do
          ++v16;
        while ( *(_WORD *)(v15 + 2 * v16) );
        if ( (int)ULongLongToULong(2 * v16 + 2, &cbData) < 0 )
          goto LABEL_32;
        v8 = RegSetValueExW(phkResult, L"GPOID", 0, 1u, v17, cbData);
        if ( v8 )
          goto LABEL_38;
        v18 = *((_QWORD *)a2 + 10);
        v19 = -1;
        cbData = 0;
        do
          ++v19;
        while ( *(_WORD *)(v18 + 2 * v19) );
        if ( (int)ULongLongToULong(2 * v19 + 2, &cbData) < 0 )
          goto LABEL_32;
        v8 = RegSetValueExW(phkResult, L"SOM", 0, 1u, v20, cbData);
        if ( v8 )
          goto LABEL_38;
        v21 = *((_QWORD *)a2 + 2) == 0;
        v22 = &DomainName;
        cbData = 0;
        if ( !v21 )
          v22 = (const WCHAR *)*((_QWORD *)a2 + 2);
        v23 = -1;
        do
          ++v23;
        while ( v22[v23] );
        if ( (int)ULongLongToULong(2 * v23 + 2, &cbData) < 0 )
        {
LABEL_32:
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(2u, L"SizeTToDWord() Failed to convert to DWORD");
            }
          }
          break;
        }
        v8 = RegSetValueExW(phkResult, L"DisplayName", 0, 1u, v24, cbData);
        if ( v8 )
        {
LABEL_38:
          v12 = phkResult;
LABEL_39:
          RegCloseKey(v12);
          break;
        }
        v25 = &DomainName;
        if ( *((_QWORD *)a2 + 9) )
          v25 = (const WCHAR *)*((_QWORD *)a2 + 9);
        v26 = -1;
        do
          ++v26;
        while ( v25[v26] );
        if ( (int)ULongLongToULong(2 * v26 + 2, &cbData) < 0 )
          goto LABEL_32;
        v28 = RegSetValueExW(phkResult, L"WQL-Id", 0, 1u, v27, cbData);
        v12 = phkResult;
        v8 = v28;
        if ( v28 )
          goto LABEL_39;
        RegCloseKey(phkResult);
        a2 = (const BYTE *)*((_QWORD *)a2 + 14);
      }
      RegCloseKey(hKeya);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18002e188  push    rbp
0x18002e18a  push    rbx
0x18002e18b  push    rsi
0x18002e18c  push    rdi
0x18002e18d  push    r12
0x18002e18f  push    r14
0x18002e191  push    r15
0x18002e193  lea     rbp, [rsp-27h]
0x18002e198  sub     rsp, 0C0h
0x18002e19f  mov     rax, cs:__security_cookie
0x18002e1a6  xor     rax, rsp
0x18002e1a9  mov     [rbp+57h+var_40], rax
0x18002e1ad  mov     rdi, rdx
0x18002e1b0  mov     r14, r9
0x18002e1b3  mov     rdx, r9; unsigned __int16 *
0x18002e1b6  mov     r15d, r8d
0x18002e1b9  mov     rsi, rcx
0x18002e1bc  call    ?GPRegDelnode@@YAKPEAUHKEY__@@PEBG@Z; GPRegDelnode(HKEY__ *,ushort const *)
0x18002e1c1  xor     r12d, r12d
0x18002e1c4  mov     ebx, eax
0x18002e1c6  test    eax, eax
0x18002e1c8  jnz     loc_18002E577
0x18002e1ce  mov     [rsp+0F0h+lpdwDisposition], r12; lpdwDisposition
0x18002e1d3  lea     rax, [rbp+57h+hKey]
0x18002e1d7  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18002e1dc  xor     r9d, r9d; lpClass
0x18002e1df  mov     [rsp+0F0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18002e1e4  xor     r8d, r8d; Reserved
0x18002e1e7  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x18002e1ef  mov     rdx, r14; lpSubKey
0x18002e1f2  mov     rcx, rsi; hKey
0x18002e1f5  mov     [rsp+0F0h+dwOptions], r12d; dwOptions
0x18002e1fa  mov     [rbp+57h+hKey], r12
0x18002e1fe  call    cs:__imp_RegCreateKeyExW
0x18002e204  mov     ebx, eax
0x18002e206  test    eax, eax
0x18002e208  jnz     loc_18002E577
0x18002e20e  mov     esi, r12d
0x18002e211  lea     r14d, [r12+4]
0x18002e216  test    rdi, rdi
0x18002e219  jz      loc_18002E56D
0x18002e21f  mov     r8d, 10h; Radix
0x18002e225  mov     [rbp+57h+var_98], r12
0x18002e229  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18002e22d  mov     ecx, esi; Value
0x18002e22f  call    cs:__imp__itow
0x18002e235  mov     [rsp+0F0h+lpdwDisposition], r12; lpdwDisposition
0x18002e23a  lea     rcx, [rbp+57h+var_98]
0x18002e23e  mov     [rsp+0F0h+phkResult], rcx; phkResult
0x18002e243  xor     r9d, r9d; lpClass
0x18002e246  mov     rcx, [rbp+57h+hKey]; hKey
0x18002e24a  xor     r8d, r8d; Reserved
0x18002e24d  mov     [rsp+0F0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18002e252  mov     rdx, rax; lpSubKey
0x18002e255  mov     [rsp+0F0h+samDesired], 0F003Fh; samDesired
0x18002e25d  mov     [rsp+0F0h+dwOptions], r12d; dwOptions
0x18002e262  call    cs:__imp_RegCreateKeyExW
0x18002e268  mov     ebx, eax
0x18002e26a  test    eax, eax
0x18002e26c  jnz     loc_18002E56D
0x18002e272  mov     eax, r15d
0x18002e275  mov     [rsp+0F0h+samDesired], r14d; cbData
0x18002e27a  neg     eax
0x18002e27c  lea     rdx, aVersion_1; "Version"
0x18002e283  mov     r9d, r14d; dwType
0x18002e286  sbb     rcx, rcx
0x18002e289  xor     r8d, r8d; Reserved
0x18002e28c  and     rcx, r14
0x18002e28f  add     rcx, 30h ; '0'
0x18002e293  add     rcx, rdi
0x18002e296  mov     qword ptr [rsp+0F0h+dwOptions], rcx; lpData
0x18002e29b  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e29f  call    cs:__imp_RegSetValueExW
0x18002e2a5  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e2a9  mov     ebx, eax
0x18002e2ab  test    eax, eax
0x18002e2ad  jnz     loc_18002E567
0x18002e2b3  lea     rax, [rdi+44h]
0x18002e2b7  mov     [rsp+0F0h+samDesired], r14d; cbData
0x18002e2bc  mov     r9d, r14d; dwType
0x18002e2bf  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18002e2c4  xor     r8d, r8d; Reserved
0x18002e2c7  lea     rdx, aWqlfilterpass; "WQLFilterPass"
0x18002e2ce  call    cs:__imp_RegSetValueExW
0x18002e2d4  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e2d8  mov     ebx, eax
0x18002e2da  test    eax, eax
0x18002e2dc  jnz     loc_18002E567
0x18002e2e2  lea     rax, [rdi+24h]
0x18002e2e6  mov     [rsp+0F0h+samDesired], r14d; cbData
0x18002e2eb  mov     r9d, r14d; dwType
0x18002e2ee  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18002e2f3  xor     r8d, r8d; Reserved
0x18002e2f6  lea     rdx, aAccessdenied; "AccessDenied"
0x18002e2fd  call    cs:__imp_RegSetValueExW
0x18002e303  mov     ebx, eax
0x18002e305  test    eax, eax
0x18002e307  jnz     loc_18002E563
0x18002e30d  mov     eax, r15d
0x18002e310  mov     [rsp+0F0h+samDesired], r14d; cbData
0x18002e315  neg     eax
0x18002e317  lea     rdx, aGpoDisabled; "GPO-Disabled"
0x18002e31e  mov     r9d, r14d; dwType
0x18002e321  sbb     rcx, rcx
0x18002e324  xor     r8d, r8d; Reserved
0x18002e327  and     rcx, r14
0x18002e32a  add     rcx, 28h ; '('
0x18002e32e  add     rcx, rdi
0x18002e331  mov     qword ptr [rsp+0F0h+dwOptions], rcx; lpData
0x18002e336  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e33a  call    cs:__imp_RegSetValueExW
0x18002e340  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e344  mov     ebx, eax
0x18002e346  test    eax, eax
0x18002e348  jnz     loc_18002E567
0x18002e34e  lea     rax, [rdi+58h]
0x18002e352  mov     [rsp+0F0h+samDesired], r14d; cbData
0x18002e357  mov     r9d, r14d; dwType
0x18002e35a  mov     qword ptr [rsp+0F0h+dwOptions], rax; lpData
0x18002e35f  xor     r8d, r8d; Reserved
0x18002e362  lea     rdx, aOptions; "Options"
0x18002e369  call    cs:__imp_RegSetValueExW
0x18002e36f  mov     ebx, eax
0x18002e371  test    eax, eax
0x18002e373  jnz     loc_18002E563
0x18002e379  mov     r9, [rdi+8]
0x18002e37d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e381  mov     [rbp+57h+cbData], r12d
0x18002e385  inc     rcx
0x18002e388  cmp     [r9+rcx*2], r12w
0x18002e38d  jnz     short loc_18002E385
0x18002e38f  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18002e397  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x18002e39b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002e3a0  test    eax, eax
0x18002e3a2  js      loc_18002E516
0x18002e3a8  mov     eax, [rbp+57h+cbData]
0x18002e3ab  lea     rdx, aGpoid; "GPOID"
0x18002e3b2  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e3b6  xor     r8d, r8d; Reserved
0x18002e3b9  mov     [rsp+0F0h+samDesired], eax; cbData
0x18002e3bd  mov     qword ptr [rsp+0F0h+dwOptions], r9; lpData
0x18002e3c2  mov     r9d, 1; dwType
0x18002e3c8  call    cs:__imp_RegSetValueExW
0x18002e3ce  mov     ebx, eax
0x18002e3d0  test    eax, eax
0x18002e3d2  jnz     loc_18002E563
0x18002e3d8  mov     r9, [rdi+50h]
0x18002e3dc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e3e0  mov     [rbp+57h+cbData], r12d
0x18002e3e4  inc     rcx
0x18002e3e7  cmp     [r9+rcx*2], r12w
0x18002e3ec  jnz     short loc_18002E3E4
0x18002e3ee  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18002e3f6  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x18002e3fa  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002e3ff  test    eax, eax
0x18002e401  js      loc_18002E516
0x18002e407  mov     eax, [rbp+57h+cbData]
0x18002e40a  lea     rdx, aSom; "SOM"
0x18002e411  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e415  xor     r8d, r8d; Reserved
0x18002e418  mov     [rsp+0F0h+samDesired], eax; cbData
0x18002e41c  mov     qword ptr [rsp+0F0h+dwOptions], r9; lpData
0x18002e421  mov     r9d, 1; dwType
0x18002e427  call    cs:__imp_RegSetValueExW
0x18002e42d  mov     ebx, eax
0x18002e42f  test    eax, eax
0x18002e431  jnz     loc_18002E563
0x18002e437  cmp     [rdi+10h], r12
0x18002e43b  lea     r9, DomainName
0x18002e442  mov     [rbp+57h+cbData], r12d
0x18002e446  cmovnz  r9, [rdi+10h]
0x18002e44b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e44f  inc     rcx
0x18002e452  cmp     [r9+rcx*2], r12w
0x18002e457  jnz     short loc_18002E44F
0x18002e459  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18002e461  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x18002e465  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002e46a  test    eax, eax
0x18002e46c  js      loc_18002E516
0x18002e472  mov     eax, [rbp+57h+cbData]
0x18002e475  lea     rdx, aDisplayname; "DisplayName"
0x18002e47c  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e480  xor     r8d, r8d; Reserved
0x18002e483  mov     [rsp+0F0h+samDesired], eax; cbData
0x18002e487  mov     qword ptr [rsp+0F0h+dwOptions], r9; lpData
0x18002e48c  mov     r9d, 1; dwType
0x18002e492  call    cs:__imp_RegSetValueExW
0x18002e498  mov     ebx, eax
0x18002e49a  test    eax, eax
0x18002e49c  jnz     loc_18002E563
0x18002e4a2  cmp     [rdi+48h], r12
0x18002e4a6  lea     r9, DomainName
0x18002e4ad  cmovnz  r9, [rdi+48h]
0x18002e4b2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002e4b6  inc     rcx
0x18002e4b9  cmp     [r9+rcx*2], r12w
0x18002e4be  jnz     short loc_18002E4B6
0x18002e4c0  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x18002e4c8  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x18002e4cc  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18002e4d1  test    eax, eax
0x18002e4d3  js      short loc_18002E516
0x18002e4d5  mov     eax, [rbp+57h+cbData]
0x18002e4d8  lea     rdx, aWqlId; "WQL-Id"
0x18002e4df  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e4e3  xor     r8d, r8d; Reserved
0x18002e4e6  mov     [rsp+0F0h+samDesired], eax; cbData
0x18002e4ea  mov     qword ptr [rsp+0F0h+dwOptions], r9; lpData
0x18002e4ef  mov     r9d, 1; dwType
0x18002e4f5  call    cs:__imp_RegSetValueExW
0x18002e4fb  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e4ff  mov     ebx, eax
0x18002e501  test    eax, eax
0x18002e503  jnz     short loc_18002E567
0x18002e505  call    cs:__imp_RegCloseKey
0x18002e50b  mov     rdi, [rdi+70h]
0x18002e50f  inc     esi
0x18002e511  jmp     loc_18002E216
0x18002e516  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18002e51d  jz      short loc_18002E56D
0x18002e51f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002e526  test    rax, rax
0x18002e529  jz      short loc_18002E53E
0x18002e52b  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18002e532  mov     ecx, 2
0x18002e537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e53c  jmp     short loc_18002E56D
0x18002e53e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18002e545  jz      short loc_18002E56D
0x18002e547  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002e54e  jz      short loc_18002E56D
0x18002e550  lea     rdx, aSizettodwordFa_1; "SizeTToDWord() Failed to convert to DWO"...
0x18002e557  mov     ecx, 2; unsigned int
0x18002e55c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002e561  jmp     short loc_18002E56D
0x18002e563  mov     rcx, [rbp+57h+var_98]; hKey
0x18002e567  call    cs:__imp_RegCloseKey
0x18002e56d  mov     rcx, [rbp+57h+hKey]; hKey
0x18002e571  call    cs:__imp_RegCloseKey
0x18002e577  mov     eax, ebx
0x18002e579  mov     rcx, [rbp+57h+var_40]
0x18002e57d  xor     rcx, rsp; StackCookie
0x18002e580  call    __security_check_cookie
0x18002e585  add     rsp, 0C0h
0x18002e58c  pop     r15
0x18002e58e  pop     r14
0x18002e590  pop     r12
0x18002e592  pop     rdi
0x18002e593  pop     rsi
0x18002e594  pop     rbx
0x18002e595  pop     rbp
0x18002e596  retn
```
