# CopyEnumerateKey

- ea: `0x14000329c`
- end: `0x140003756`
- name: `CopyEnumerateKey`
- size: `1210`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, HKEY, const WCHAR *, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14000329c`
- `0x14000375c`

## callees

- `0x140001bb2`
- `0x140002b70`
- `0x14000329c`
- `0x140003a58`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000dc24`
- `0x14000e2f8`
- `0x14000e450`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400033fc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400033fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400034e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400034e4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400034b5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400034b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003529`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003529`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000366d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003680`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400036bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400036ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000366d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003680`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400036bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400036ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003361`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003361`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000353c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003550`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003578`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400035b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400035ca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400035f2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000353c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003550`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003578`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400035b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400035ca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400035f2`

## pseudocode

```c
__int64 __fastcall CopyEnumerateKey(
        HKEY a1,
        const WCHAR *a2,
        HKEY a3,
        const WCHAR *a4,
        __int64 a5,
        int a6,
        int a7,
        int a8)
{
  WCHAR *v8; // rsi
  const WCHAR *v9; // r13
  __int64 v12; // r14
  unsigned int v13; // ebx
  DWORD v14; // edi
  HKEY v15; // r13
  WCHAR *v16; // rdi
  DWORD v17; // r14d
  int v18; // esi
  int v19; // eax
  int v20; // ebx
  int v21; // eax
  int v22; // ebx
  int v23; // eax
  __int64 v24; // rbx
  unsigned int v25; // eax
  FILE *v26; // rax
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-39h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+6Ch] [rbp-35h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-31h] BYREF
  DWORD cValues; // [rsp+74h] [rbp-2Dh] BYREF
  HKEY hKey; // [rsp+78h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-21h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-19h] BYREF
  __int64 Memory; // [rsp+90h] [rbp-11h] BYREF
  __int64 v36; // [rsp+98h] [rbp-9h] BYREF
  _QWORD v37[7]; // [rsp+A0h] [rbp-1h] BYREF
  DWORD cchValueName; // [rsp+E8h] [rbp+47h] BYREF
  HKEY v39; // [rsp+F8h] [rbp+57h]
  const WCHAR *v40; // [rsp+100h] [rbp+5Fh]

  v40 = a4;
  v39 = a3;
  LODWORD(v8) = 0;
  v9 = a4;
  cValues = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  v36 = 0;
  v37[0] = 0;
  if ( a1 && a2 && a3 && a4 && (v12 = a5) != 0 )
  {
    v13 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( !v13 )
    {
      if ( !cSubKeys || cbMaxSubKeyLen )
      {
        if ( cbMaxSubKeyLen < 0x100 )
          cbMaxSubKeyLen *= 2;
      }
      else
      {
        cbMaxSubKeyLen = 256;
      }
      ++cbMaxValueNameLen;
      Memory = AllocateMemory(2 * cbMaxValueNameLen);
      v8 = (WCHAR *)Memory;
      if ( Memory )
      {
        v13 = 0;
        v14 = 0;
        if ( cValues )
        {
          v15 = v39;
          do
          {
            if ( v13 )
              break;
            cchValueName = cbMaxValueNameLen;
            v13 = RegEnumValueW(a1, v14, v8, &cchValueName, 0, 0, 0, 0);
            if ( !v13 )
            {
              v13 = CopyValue(a1, v8, v15, v8, v12, (__int64)a2);
              if ( v13 == 1223 )
                v13 = 0;
            }
            ++v14;
          }
          while ( v14 < cValues );
          v9 = v40;
        }
        FreeMemory(&Memory);
        LODWORD(v8) = 0;
        if ( a6 && !v13 )
        {
          ++cbMaxSubKeyLen;
          Memory = AllocateMemory(2 * cbMaxSubKeyLen);
          v16 = (WCHAR *)Memory;
          if ( Memory )
          {
            v17 = 0;
            hKey = 0;
            phkResult = 0;
            if ( cSubKeys )
            {
              do
              {
                cchValueName = cbMaxSubKeyLen;
                v13 = RegEnumKeyExW(a1, v17, v16, &cchValueName, 0, 0, 0, 0);
                if ( v13 )
                  break;
                v18 = a8;
                v13 = RegOpenKeyExW(a1, v16, 0, a8 | 0x20019, &hKey);
                if ( v13 )
                  goto LABEL_49;
                v19 = v18;
                LODWORD(v8) = 0;
                v13 = RegCreateKeyExW(v39, v16, 0, 0, 0, v19 | 0xF003F, 0, &phkResult, &dwDisposition);
                if ( v13 )
                  break;
                v20 = lstrlenW(a2);
                if ( v16 )
                  v21 = lstrlenW(v16);
                else
                  v21 = 0;
                cchValueName = v21 + v20 + 3;
                v36 = AllocateMemory(2 * cchValueName);
                v8 = (WCHAR *)v36;
                if ( !v36 )
                  goto LABEL_48;
                if ( lstrlenW(a2) )
                {
                  StringCopyW(v8, a2, cchValueName);
                  StringConcatW(v8, L"\\", cchValueName);
                }
                StringConcatW(v8, v16, cchValueName);
                v22 = lstrlenW(v9);
                v23 = v16 ? lstrlenW(v16) : 0;
                cchValueName = v22 + v23 + 3;
                v37[0] = AllocateMemory(2 * cchValueName);
                v24 = v37[0];
                if ( !v37[0] )
                {
LABEL_48:
                  v13 = 14;
LABEL_49:
                  LODWORD(v8) = 0;
                  break;
                }
                if ( lstrlenW(v9) )
                {
                  StringCopyW(v24, v9, cchValueName);
                  StringConcatW(v24, L"\\", cchValueName);
                }
                StringConcatW(v24, v16, cchValueName);
                v25 = CopyEnumerateKey((_DWORD)hKey, (_DWORD)v8, (_DWORD)phkResult, v24, a5, a6, a7 + 1, a8);
                LODWORD(v8) = 0;
                v13 = v25;
                if ( hKey )
                {
                  RegCloseKey(hKey);
                  hKey = 0;
                }
                if ( phkResult )
                {
                  RegCloseKey(phkResult);
                  phkResult = 0;
                }
                FreeMemory(&v36);
                FreeMemory(v37);
                ++v17;
              }
              while ( v17 < cSubKeys );
              if ( hKey )
              {
                RegCloseKey(hKey);
                hKey = 0;
              }
              if ( phkResult )
              {
                RegCloseKey(phkResult);
                phkResult = 0;
              }
            }
            FreeMemory(&Memory);
            FreeMemory(&v36);
            FreeMemory(v37);
          }
          else
          {
            v13 = 8;
          }
        }
      }
      else
      {
        v13 = 14;
      }
    }
  }
  else
  {
    v13 = 87;
  }
  if ( a7 == (_DWORD)v8 )
  {
    if ( v13 )
    {
      SaveErrorMessage(v13);
      v26 = o___acrt_iob_func_0(2u);
    }
    else
    {
      SaveErrorMessage(0);
      v26 = o___acrt_iob_func_0(1u);
    }
    ShowLastErrorEx(v26);
  }
  return v13;
}

```

## disassembly

```asm
0x14000329c  mov     r11, rsp
0x14000329f  mov     [r11+10h], rbx
0x1400032a3  mov     [r11+20h], r9
0x1400032a7  mov     [r11+18h], r8
0x1400032ab  push    rbp
0x1400032ac  push    rsi
0x1400032ad  push    rdi
0x1400032ae  push    r12
0x1400032b0  push    r13
0x1400032b2  push    r14
0x1400032b4  push    r15
0x1400032b6  lea     rbp, [r11-3Fh]
0x1400032ba  sub     rsp, 0A0h
0x1400032c1  xor     esi, esi
0x1400032c3  mov     r13, r9
0x1400032c6  mov     [rbp+37h+cValues], esi
0x1400032c9  mov     rax, r8
0x1400032cc  mov     [rbp+37h+cSubKeys], esi
0x1400032cf  mov     r12, rdx
0x1400032d2  mov     [rbp+37h+cbMaxSubKeyLen], esi
0x1400032d5  mov     r15, rcx
0x1400032d8  mov     [rbp+37h+cbMaxValueNameLen], esi
0x1400032db  mov     [rbp+37h+cchValueName], esi
0x1400032de  mov     [rbp+37h+dwDisposition], esi
0x1400032e1  mov     [rbp+37h+hKey], rsi
0x1400032e5  mov     [rbp+37h+phkResult], rsi
0x1400032e9  mov     [rbp+37h+var_40], rsi
0x1400032ed  mov     [rbp+37h+var_38], rsi
0x1400032f1  test    rcx, rcx
0x1400032f4  jz      loc_1400036F5
0x1400032fa  test    rdx, rdx
0x1400032fd  jz      loc_1400036F5
0x140003303  test    rax, rax
0x140003306  jz      loc_1400036F5
0x14000330c  test    r9, r9
0x14000330f  jz      loc_1400036F5
0x140003315  mov     r14, [rbp+37h+arg_20]
0x140003319  test    r14, r14
0x14000331c  jz      loc_1400036F5
0x140003322  mov     [r11-80h], rsi
0x140003326  lea     rax, [rbp+37h+cbMaxValueNameLen]
0x14000332a  mov     [rsp+50h], rsi; lpcbSecurityDescriptor
0x14000332f  xor     r9d, r9d; lpReserved
0x140003332  mov     [rsp+0D0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x140003337  xor     r8d, r8d; lpcchClass
0x14000333a  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x14000333f  xor     edx, edx; lpClass
0x140003341  lea     rax, [rbp+37h+cValues]
0x140003345  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x14000334a  lea     rax, [rbp+37h+cbMaxSubKeyLen]
0x14000334e  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x140003353  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140003358  lea     rax, [rbp+37h+cSubKeys]
0x14000335c  mov     [rsp+0D0h+lpcSubKeys], rax; lpcSubKeys
0x140003361  call    cs:__imp_RegQueryInfoKeyW
0x140003367  mov     ebx, eax
0x140003369  test    eax, eax
0x14000336b  jnz     loc_1400036FA
0x140003371  mov     eax, [rbp+37h+cbMaxSubKeyLen]
0x140003374  cmp     [rbp+37h+cSubKeys], esi
0x140003377  jz      short loc_140003386
0x140003379  test    eax, eax
0x14000337b  jnz     short loc_140003386
0x14000337d  mov     [rbp+37h+cbMaxSubKeyLen], 100h
0x140003384  jmp     short loc_140003392
0x140003386  cmp     eax, 100h
0x14000338b  jnb     short loc_140003392
0x14000338d  add     eax, eax
0x14000338f  mov     [rbp+37h+cbMaxSubKeyLen], eax
0x140003392  mov     ecx, [rbp+37h+cbMaxValueNameLen]
0x140003395  inc     ecx
0x140003397  mov     [rbp+37h+cbMaxValueNameLen], ecx
0x14000339a  add     ecx, ecx; dwBytes
0x14000339c  call    AllocateMemory
0x1400033a1  mov     [rbp+37h+var_48], rax
0x1400033a5  mov     rsi, rax
0x1400033a8  test    rax, rax
0x1400033ab  jnz     short loc_1400033B5
0x1400033ad  lea     ebx, [rax+0Eh]
0x1400033b0  jmp     loc_1400036FA
0x1400033b5  xor     ebx, ebx
0x1400033b7  xor     edi, edi
0x1400033b9  cmp     [rbp+37h+cValues], ebx
0x1400033bc  jbe     short loc_14000343B
0x1400033be  mov     r13, [rbp+37h+arg_10]
0x1400033c2  test    ebx, ebx
0x1400033c4  jnz     short loc_140003437
0x1400033c6  mov     eax, [rbp+37h+cbMaxValueNameLen]
0x1400033c9  lea     r9, [rbp+37h+cchValueName]; lpcchValueName
0x1400033cd  mov     [rsp+0D0h+lpcValues], 0; lpcbData
0x1400033d6  mov     r8, rsi; lpValueName
0x1400033d9  mov     [rsp+0D0h+lpcbMaxClassLen], 0; lpData
0x1400033e2  mov     edx, edi; dwIndex
0x1400033e4  mov     [rsp+0D0h+lpcbMaxSubKeyLen], 0; lpType
0x1400033ed  mov     rcx, r15; hKey
0x1400033f0  mov     [rsp+0D0h+lpcSubKeys], 0; lpReserved
0x1400033f9  mov     [rbp+37h+cchValueName], eax
0x1400033fc  call    cs:__imp_RegEnumValueW
0x140003402  mov     ebx, eax
0x140003404  test    eax, eax
0x140003406  jnz     short loc_140003430
0x140003408  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; __int64
0x14000340d  mov     r9, rsi; LPCWSTR
0x140003410  mov     r8, r13; HKEY
0x140003413  mov     [rsp+0D0h+lpcSubKeys], r14; __int64
0x140003418  mov     rdx, rsi; lpValueName
0x14000341b  mov     rcx, r15; hKey
0x14000341e  call    CopyValue
0x140003423  mov     ebx, eax
0x140003425  xor     eax, eax
0x140003427  cmp     ebx, 4C7h
0x14000342d  cmovz   ebx, eax
0x140003430  inc     edi
0x140003432  cmp     edi, [rbp+37h+cValues]
0x140003435  jb      short loc_1400033C2
0x140003437  mov     r13, [rbp+37h+arg_18]
0x14000343b  lea     rcx, [rbp+37h+var_48]
0x14000343f  call    FreeMemory
0x140003444  xor     esi, esi
0x140003446  cmp     [rbp+37h+arg_28], esi
0x140003449  jz      loc_1400036FA
0x14000344f  test    ebx, ebx
0x140003451  jnz     loc_1400036FA
0x140003457  mov     ecx, [rbp+37h+cbMaxSubKeyLen]
0x14000345a  inc     ecx
0x14000345c  mov     [rbp+37h+cbMaxSubKeyLen], ecx
0x14000345f  add     ecx, ecx; dwBytes
0x140003461  call    AllocateMemory
0x140003466  mov     [rbp+37h+var_48], rax
0x14000346a  mov     rdi, rax
0x14000346d  test    rax, rax
0x140003470  jnz     short loc_14000347A
0x140003472  lea     ebx, [rsi+8]
0x140003475  jmp     loc_1400036FA
0x14000347a  mov     r14d, esi
0x14000347d  mov     [rbp+37h+hKey], rsi
0x140003481  mov     [rbp+37h+phkResult], rsi
0x140003485  cmp     [rbp+37h+cSubKeys], esi
0x140003488  jbe     loc_1400036D8
0x14000348e  mov     eax, [rbp+37h+cbMaxSubKeyLen]
0x140003491  lea     r9, [rbp+37h+cchValueName]; lpcchName
0x140003495  mov     [rsp+0D0h+lpcValues], rsi; lpftLastWriteTime
0x14000349a  mov     r8, rdi; lpName
0x14000349d  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpcchClass
0x1400034a2  mov     edx, r14d; dwIndex
0x1400034a5  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rsi; lpClass
0x1400034aa  mov     rcx, r15; hKey
0x1400034ad  mov     [rsp+0D0h+lpcSubKeys], rsi; lpReserved
0x1400034b2  mov     [rbp+37h+cchValueName], eax
0x1400034b5  call    cs:__imp_RegEnumKeyExW
0x1400034bb  mov     ebx, eax
0x1400034bd  test    eax, eax
0x1400034bf  jnz     loc_1400036B2
0x1400034c5  mov     esi, [rbp+37h+arg_38]
0x1400034c8  lea     rax, [rbp+37h+hKey]
0x1400034cc  mov     r9d, esi
0x1400034cf  mov     [rsp+0D0h+lpcSubKeys], rax; phkResult
0x1400034d4  or      r9d, 20019h; samDesired
0x1400034db  xor     r8d, r8d; ulOptions
0x1400034de  mov     rdx, rdi; lpSubKey
0x1400034e1  mov     rcx, r15; hKey
0x1400034e4  call    cs:__imp_RegOpenKeyExW
0x1400034ea  mov     ebx, eax
0x1400034ec  test    eax, eax
0x1400034ee  jnz     loc_1400036B0
0x1400034f4  mov     eax, esi
0x1400034f6  lea     rcx, [rbp+37h+dwDisposition]
0x1400034fa  mov     [rsp+0D0h+lpcbMaxValueNameLen], rcx; lpdwDisposition
0x1400034ff  xor     esi, esi
0x140003501  lea     rcx, [rbp+37h+phkResult]
0x140003505  or      eax, 0F003Fh
0x14000350a  mov     [rsp+0D0h+lpcValues], rcx; phkResult
0x14000350f  xor     r9d, r9d; lpClass
0x140003512  mov     rcx, [rbp+37h+arg_10]; hKey
0x140003516  xor     r8d, r8d; Reserved
0x140003519  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpSecurityAttributes
0x14000351e  mov     rdx, rdi; lpSubKey
0x140003521  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], eax; samDesired
0x140003525  mov     dword ptr [rsp+0D0h+lpcSubKeys], esi; dwOptions
0x140003529  call    cs:__imp_RegCreateKeyExW
0x14000352f  mov     ebx, eax
0x140003531  test    eax, eax
0x140003533  jnz     loc_1400036B2
0x140003539  mov     rcx, r12; lpString
0x14000353c  call    cs:__imp_lstrlenW
0x140003542  mov     ebx, eax
0x140003544  test    rdi, rdi
0x140003547  jnz     short loc_14000354D
0x140003549  mov     eax, esi
0x14000354b  jmp     short loc_140003556
0x14000354d  mov     rcx, rdi; lpString
0x140003550  call    cs:__imp_lstrlenW
0x140003556  lea     ecx, [rbx+3]
0x140003559  add     ecx, eax
0x14000355b  mov     [rbp+37h+cchValueName], ecx
0x14000355e  add     ecx, ecx; dwBytes
0x140003560  call    AllocateMemory
0x140003565  mov     [rbp+37h+var_40], rax
0x140003569  mov     rsi, rax
0x14000356c  test    rax, rax
0x14000356f  jz      loc_1400036AB
0x140003575  mov     rcx, r12; lpString
0x140003578  call    cs:__imp_lstrlenW
0x14000357e  test    eax, eax
0x140003580  jz      short loc_1400035A4
0x140003582  mov     r8d, [rbp+37h+cchValueName]
0x140003586  mov     rdx, r12
0x140003589  mov     rcx, rsi
0x14000358c  call    StringCopyW
0x140003591  mov     r8d, [rbp+37h+cchValueName]
0x140003595  lea     rdx, asc_14001081C; "\\"
0x14000359c  mov     rcx, rsi
0x14000359f  call    StringConcatW
0x1400035a4  mov     r8d, [rbp+37h+cchValueName]
0x1400035a8  mov     rdx, rdi
0x1400035ab  mov     rcx, rsi
0x1400035ae  call    StringConcatW
0x1400035b3  mov     rcx, r13; lpString
0x1400035b6  call    cs:__imp_lstrlenW
0x1400035bc  mov     ebx, eax
0x1400035be  test    rdi, rdi
0x1400035c1  jnz     short loc_1400035C7
0x1400035c3  xor     eax, eax
0x1400035c5  jmp     short loc_1400035D0
0x1400035c7  mov     rcx, rdi; lpString
0x1400035ca  call    cs:__imp_lstrlenW
0x1400035d0  lea     ecx, [rax+3]
0x1400035d3  add     ecx, ebx
0x1400035d5  mov     [rbp+37h+cchValueName], ecx
0x1400035d8  add     ecx, ecx; dwBytes
0x1400035da  call    AllocateMemory
0x1400035df  mov     [rbp+37h+var_38], rax
0x1400035e3  mov     rbx, rax
0x1400035e6  test    rax, rax
0x1400035e9  jz      loc_1400036AB
0x1400035ef  mov     rcx, r13; lpString
0x1400035f2  call    cs:__imp_lstrlenW
0x1400035f8  test    eax, eax
0x1400035fa  jz      short loc_14000361E
0x1400035fc  mov     r8d, [rbp+37h+cchValueName]
0x140003600  mov     rdx, r13
0x140003603  mov     rcx, rbx
0x140003606  call    StringCopyW
0x14000360b  mov     r8d, [rbp+37h+cchValueName]
0x14000360f  lea     rdx, asc_14001081C; "\\"
0x140003616  mov     rcx, rbx
0x140003619  call    StringConcatW
0x14000361e  mov     r8d, [rbp+37h+cchValueName]
0x140003622  mov     rdx, rdi
0x140003625  mov     rcx, rbx
0x140003628  call    StringConcatW
0x14000362d  mov     eax, [rbp+37h+arg_30]
0x140003630  mov     r9, rbx
0x140003633  mov     ecx, [rbp+37h+arg_38]
0x140003636  inc     eax
0x140003638  mov     r8, [rbp+37h+phkResult]
0x14000363c  mov     rdx, rsi
0x14000363f  mov     dword ptr [rsp+0D0h+lpcValues], ecx
0x140003643  mov     rcx, [rbp+37h+hKey]
0x140003647  mov     dword ptr [rsp+0D0h+lpcbMaxClassLen], eax
0x14000364b  mov     eax, [rbp+37h+arg_28]
0x14000364e  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], eax
0x140003652  mov     rax, [rbp+37h+arg_20]
0x140003656  mov     [rsp+0D0h+lpcSubKeys], rax
0x14000365b  call    CopyEnumerateKey
0x140003660  mov     rcx, [rbp+37h+hKey]; hKey
0x140003664  xor     esi, esi
0x140003666  mov     ebx, eax
0x140003668  test    rcx, rcx
0x14000366b  jz      short loc_140003677
0x14000366d  call    cs:__imp_RegCloseKey
0x140003673  mov     [rbp+37h+hKey], rsi
0x140003677  mov     rcx, [rbp+37h+phkResult]; hKey
0x14000367b  test    rcx, rcx
0x14000367e  jz      short loc_14000368A
0x140003680  call    cs:__imp_RegCloseKey
0x140003686  mov     [rbp+37h+phkResult], rsi
0x14000368a  lea     rcx, [rbp+37h+var_40]
0x14000368e  call    FreeMemory
0x140003693  lea     rcx, [rbp+37h+var_38]
0x140003697  call    FreeMemory
0x14000369c  inc     r14d
0x14000369f  cmp     r14d, [rbp+37h+cSubKeys]
0x1400036a3  jb      loc_14000348E
0x1400036a9  jmp     short loc_1400036B2
0x1400036ab  mov     ebx, 0Eh
0x1400036b0  xor     esi, esi
0x1400036b2  mov     rcx, [rbp+37h+hKey]; hKey
0x1400036b6  test    rcx, rcx
0x1400036b9  jz      short loc_1400036C5
0x1400036bb  call    cs:__imp_RegCloseKey
0x1400036c1  mov     [rbp+37h+hKey], rsi
0x1400036c5  mov     rcx, [rbp+37h+phkResult]; hKey
0x1400036c9  test    rcx, rcx
0x1400036cc  jz      short loc_1400036D8
0x1400036ce  call    cs:__imp_RegCloseKey
0x1400036d4  mov     [rbp+37h+phkResult], rsi
0x1400036d8  lea     rcx, [rbp+37h+var_48]
0x1400036dc  call    FreeMemory
0x1400036e1  lea     rcx, [rbp+37h+var_40]
  ... truncated ...
```
