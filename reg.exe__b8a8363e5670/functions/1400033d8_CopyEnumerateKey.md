# CopyEnumerateKey

- ea: `0x1400033d8`
- end: `0x1400038f1`
- name: `CopyEnumerateKey`
- size: `1305`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, HKEY, const WCHAR *, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400033d8`
- `0x1400038f8`

## callees

- `0x140001bb2`
- `0x140002ce4`
- `0x1400033d8`
- `0x140003c24`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000e798`
- `0x14000ef5c`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140003542`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140003542`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003636`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003636`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140003601`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140003601`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003681`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140003681`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400037ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003808`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003849`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003862`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400037ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003808`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003849`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003862`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000349d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000349d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000369a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400036b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400036e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003726`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003740`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000376e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000369a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400036b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400036e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003726`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003740`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000376e`

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
  const WCHAR *v8; // r13
  __int64 v11; // r14
  unsigned int v12; // ebx
  WCHAR *v13; // rsi
  DWORD v14; // edi
  HKEY v15; // r13
  WCHAR *v16; // rdi
  DWORD v17; // r14d
  int v18; // esi
  int v19; // ebx
  int v20; // eax
  __int64 v21; // rsi
  int v22; // ebx
  int v23; // eax
  __int64 v24; // rbx
  FILE *v25; // rax
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-39h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+6Ch] [rbp-35h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-31h] BYREF
  DWORD cValues; // [rsp+74h] [rbp-2Dh] BYREF
  HKEY hKey; // [rsp+78h] [rbp-29h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-21h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-19h] BYREF
  __int64 Memory; // [rsp+90h] [rbp-11h] BYREF
  __int64 v35; // [rsp+98h] [rbp-9h] BYREF
  _QWORD v36[7]; // [rsp+A0h] [rbp-1h] BYREF
  DWORD cchValueName; // [rsp+E8h] [rbp+47h] BYREF
  HKEY v38; // [rsp+F8h] [rbp+57h]
  const WCHAR *v39; // [rsp+100h] [rbp+5Fh]

  v39 = a4;
  v38 = a3;
  v8 = a4;
  cValues = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  v35 = 0;
  v36[0] = 0;
  if ( a1 && a2 && a3 && a4 && (v11 = a5) != 0 )
  {
    v12 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    if ( !v12 )
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
      v13 = (WCHAR *)Memory;
      if ( Memory )
      {
        v12 = 0;
        v14 = 0;
        if ( cValues )
        {
          v15 = v38;
          do
          {
            if ( v12 )
              break;
            cchValueName = cbMaxValueNameLen;
            v12 = RegEnumValueW(a1, v14, v13, &cchValueName, 0, 0, 0, 0);
            if ( !v12 )
            {
              v12 = CopyValue(a1, v13, v15, v13, v11, (__int64)a2);
              if ( v12 == 1223 )
                v12 = 0;
            }
            ++v14;
          }
          while ( v14 < cValues );
          v8 = v39;
        }
        FreeMemory(&Memory);
        if ( a6 && !v12 )
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
                v12 = RegEnumKeyExW(a1, v17, v16, &cchValueName, 0, 0, 0, 0);
                if ( v12 )
                  break;
                v18 = a8;
                v12 = RegOpenKeyExW(a1, v16, 0, a8 | 0x20019, &hKey);
                if ( v12 )
                  break;
                v12 = RegCreateKeyExW(v38, v16, 0, 0, 0, v18 | 0xF003F, 0, &phkResult, &dwDisposition);
                if ( v12 )
                  break;
                v19 = lstrlenW(a2);
                if ( v16 )
                  v20 = lstrlenW(v16);
                else
                  v20 = 0;
                cchValueName = v20 + v19 + 3;
                v35 = AllocateMemory(2 * cchValueName);
                v21 = v35;
                if ( !v35 )
                  goto LABEL_48;
                if ( lstrlenW(a2) )
                {
                  StringCopyW(v21, a2, cchValueName);
                  StringConcatW(v21, L"\\", cchValueName);
                }
                StringConcatW(v21, v16, cchValueName);
                v22 = lstrlenW(v8);
                v23 = v16 ? lstrlenW(v16) : 0;
                cchValueName = v22 + v23 + 3;
                v36[0] = AllocateMemory(2 * cchValueName);
                v24 = v36[0];
                if ( !v36[0] )
                {
LABEL_48:
                  v12 = 14;
                  break;
                }
                if ( lstrlenW(v8) )
                {
                  StringCopyW(v24, v8, cchValueName);
                  StringConcatW(v24, L"\\", cchValueName);
                }
                StringConcatW(v24, v16, cchValueName);
                v12 = CopyEnumerateKey((_DWORD)hKey, v21, (_DWORD)phkResult, v24, a5, a6, a7 + 1, a8);
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
                FreeMemory(&v35);
                FreeMemory(v36);
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
            FreeMemory(&v35);
            FreeMemory(v36);
          }
          else
          {
            v12 = 8;
          }
        }
      }
      else
      {
        v12 = 14;
      }
    }
  }
  else
  {
    v12 = 87;
  }
  if ( !a7 )
  {
    if ( v12 )
    {
      SaveErrorMessage(v12);
      v25 = o___acrt_iob_func_0(2u);
    }
    else
    {
      SaveErrorMessage(0);
      v25 = o___acrt_iob_func_0(1u);
    }
    ShowLastErrorEx(v25);
  }
  return v12;
}

```

## disassembly

```asm
0x1400033d8  mov     r11, rsp
0x1400033db  mov     [r11+10h], rbx
0x1400033df  mov     [r11+20h], r9
0x1400033e3  mov     [r11+18h], r8
0x1400033e7  push    rbp
0x1400033e8  push    rsi
0x1400033e9  push    rdi
0x1400033ea  push    r12
0x1400033ec  push    r13
0x1400033ee  push    r14
0x1400033f0  push    r15
0x1400033f2  lea     rbp, [r11-3Fh]
0x1400033f6  sub     rsp, 0A0h
0x1400033fd  xor     esi, esi
0x1400033ff  mov     r13, r9
0x140003402  mov     [rbp+37h+cValues], esi
0x140003405  mov     rax, r8
0x140003408  mov     [rbp+37h+cSubKeys], esi
0x14000340b  mov     r12, rdx
0x14000340e  mov     [rbp+37h+cbMaxSubKeyLen], esi
0x140003411  mov     r15, rcx
0x140003414  mov     [rbp+37h+cbMaxValueNameLen], esi
0x140003417  mov     [rbp+37h+cchValueName], esi
0x14000341a  mov     [rbp+37h+dwDisposition], esi
0x14000341d  mov     [rbp+37h+hKey], rsi
0x140003421  mov     [rbp+37h+phkResult], rsi
0x140003425  mov     [rbp+37h+var_40], rsi
0x140003429  mov     [rbp+37h+var_38], rsi
0x14000342d  test    rcx, rcx
0x140003430  jz      loc_14000388F
0x140003436  test    rdx, rdx
0x140003439  jz      loc_14000388F
0x14000343f  test    rax, rax
0x140003442  jz      loc_14000388F
0x140003448  test    r9, r9
0x14000344b  jz      loc_14000388F
0x140003451  mov     r14, [rbp+37h+arg_20]
0x140003455  test    r14, r14
0x140003458  jz      loc_14000388F
0x14000345e  mov     [r11-80h], rsi
0x140003462  lea     rax, [rbp+37h+cbMaxValueNameLen]
0x140003466  mov     [rsp+50h], rsi; lpcbSecurityDescriptor
0x14000346b  xor     r9d, r9d; lpReserved
0x14000346e  mov     [rsp+0D0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x140003473  xor     r8d, r8d; lpcchClass
0x140003476  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x14000347b  xor     edx, edx; lpClass
0x14000347d  lea     rax, [rbp+37h+cValues]
0x140003481  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x140003486  lea     rax, [rbp+37h+cbMaxSubKeyLen]
0x14000348a  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x14000348f  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140003494  lea     rax, [rbp+37h+cSubKeys]
0x140003498  mov     [rsp+0D0h+lpcSubKeys], rax; lpcSubKeys
0x14000349d  call    cs:__imp_RegQueryInfoKeyW
0x1400034a4  nop     dword ptr [rax+rax+00h]
0x1400034a9  mov     ebx, eax
0x1400034ab  test    eax, eax
0x1400034ad  jnz     loc_140003894
0x1400034b3  mov     eax, [rbp+37h+cbMaxSubKeyLen]
0x1400034b6  cmp     [rbp+37h+cSubKeys], esi
0x1400034b9  jz      short loc_1400034C8
0x1400034bb  test    eax, eax
0x1400034bd  jnz     short loc_1400034C8
0x1400034bf  mov     [rbp+37h+cbMaxSubKeyLen], 100h
0x1400034c6  jmp     short loc_1400034D4
0x1400034c8  cmp     eax, 100h
0x1400034cd  jnb     short loc_1400034D4
0x1400034cf  add     eax, eax
0x1400034d1  mov     [rbp+37h+cbMaxSubKeyLen], eax
0x1400034d4  mov     ecx, [rbp+37h+cbMaxValueNameLen]
0x1400034d7  inc     ecx
0x1400034d9  mov     [rbp+37h+cbMaxValueNameLen], ecx
0x1400034dc  add     ecx, ecx; dwBytes
0x1400034de  call    AllocateMemory
0x1400034e3  mov     [rbp+37h+var_48], rax
0x1400034e7  mov     rsi, rax
0x1400034ea  test    rax, rax
0x1400034ed  jnz     short loc_1400034F7
0x1400034ef  lea     ebx, [rax+0Eh]
0x1400034f2  jmp     loc_140003894
0x1400034f7  xor     ebx, ebx
0x1400034f9  xor     edi, edi
0x1400034fb  cmp     [rbp+37h+cValues], ebx
0x1400034fe  jbe     loc_140003587
0x140003504  mov     r13, [rbp+37h+arg_10]
0x140003508  test    ebx, ebx
0x14000350a  jnz     short loc_140003583
0x14000350c  mov     eax, [rbp+37h+cbMaxValueNameLen]
0x14000350f  lea     r9, [rbp+37h+cchValueName]; lpcchValueName
0x140003513  mov     [rsp+0D0h+lpcValues], 0; lpcbData
0x14000351c  mov     r8, rsi; lpValueName
0x14000351f  mov     [rsp+0D0h+lpcbMaxClassLen], 0; lpData
0x140003528  mov     edx, edi; dwIndex
0x14000352a  mov     [rsp+0D0h+lpcbMaxSubKeyLen], 0; lpType
0x140003533  mov     rcx, r15; hKey
0x140003536  mov     [rsp+0D0h+lpcSubKeys], 0; lpReserved
0x14000353f  mov     [rbp+37h+cchValueName], eax
0x140003542  call    cs:__imp_RegEnumValueW
0x140003549  nop     dword ptr [rax+rax+00h]
0x14000354e  mov     ebx, eax
0x140003550  test    eax, eax
0x140003552  jnz     short loc_14000357C
0x140003554  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r12; __int64
0x140003559  mov     r9, rsi; LPCWSTR
0x14000355c  mov     r8, r13; HKEY
0x14000355f  mov     [rsp+0D0h+lpcSubKeys], r14; __int64
0x140003564  mov     rdx, rsi; lpValueName
0x140003567  mov     rcx, r15; hKey
0x14000356a  call    CopyValue
0x14000356f  mov     ebx, eax
0x140003571  xor     eax, eax
0x140003573  cmp     ebx, 4C7h
0x140003579  cmovz   ebx, eax
0x14000357c  inc     edi
0x14000357e  cmp     edi, [rbp+37h+cValues]
0x140003581  jb      short loc_140003508
0x140003583  mov     r13, [rbp+37h+arg_18]
0x140003587  lea     rcx, [rbp+37h+var_48]
0x14000358b  call    FreeMemory
0x140003590  xor     esi, esi
0x140003592  cmp     [rbp+37h+arg_28], esi
0x140003595  jz      loc_140003894
0x14000359b  test    ebx, ebx
0x14000359d  jnz     loc_140003894
0x1400035a3  mov     ecx, [rbp+37h+cbMaxSubKeyLen]
0x1400035a6  inc     ecx
0x1400035a8  mov     [rbp+37h+cbMaxSubKeyLen], ecx
0x1400035ab  add     ecx, ecx; dwBytes
0x1400035ad  call    AllocateMemory
0x1400035b2  mov     [rbp+37h+var_48], rax
0x1400035b6  mov     rdi, rax
0x1400035b9  test    rax, rax
0x1400035bc  jnz     short loc_1400035C6
0x1400035be  lea     ebx, [rsi+8]
0x1400035c1  jmp     loc_140003894
0x1400035c6  mov     r14d, esi
0x1400035c9  mov     [rbp+37h+hKey], rsi
0x1400035cd  mov     [rbp+37h+phkResult], rsi
0x1400035d1  cmp     [rbp+37h+cSubKeys], esi
0x1400035d4  jbe     loc_140003872
0x1400035da  mov     eax, [rbp+37h+cbMaxSubKeyLen]
0x1400035dd  lea     r9, [rbp+37h+cchValueName]; lpcchName
0x1400035e1  mov     [rsp+0D0h+lpcValues], rsi; lpftLastWriteTime
0x1400035e6  mov     r8, rdi; lpName
0x1400035e9  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpcchClass
0x1400035ee  mov     edx, r14d; dwIndex
0x1400035f1  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rsi; lpClass
0x1400035f6  mov     rcx, r15; hKey
0x1400035f9  mov     [rsp+0D0h+lpcSubKeys], rsi; lpReserved
0x1400035fe  mov     [rbp+37h+cchValueName], eax
0x140003601  call    cs:__imp_RegEnumKeyExW
0x140003608  nop     dword ptr [rax+rax+00h]
0x14000360d  mov     ebx, eax
0x14000360f  test    eax, eax
0x140003611  jnz     loc_140003840
0x140003617  mov     esi, [rbp+37h+arg_38]
0x14000361a  lea     rax, [rbp+37h+hKey]
0x14000361e  mov     r9d, esi
0x140003621  mov     [rsp+0D0h+lpcSubKeys], rax; phkResult
0x140003626  or      r9d, 20019h; samDesired
0x14000362d  xor     r8d, r8d; ulOptions
0x140003630  mov     rdx, rdi; lpSubKey
0x140003633  mov     rcx, r15; hKey
0x140003636  call    cs:__imp_RegOpenKeyExW
0x14000363d  nop     dword ptr [rax+rax+00h]
0x140003642  mov     ebx, eax
0x140003644  test    eax, eax
0x140003646  jnz     loc_14000383E
0x14000364c  mov     eax, esi
0x14000364e  lea     rcx, [rbp+37h+dwDisposition]
0x140003652  mov     [rsp+0D0h+lpcbMaxValueNameLen], rcx; lpdwDisposition
0x140003657  xor     esi, esi
0x140003659  lea     rcx, [rbp+37h+phkResult]
0x14000365d  or      eax, 0F003Fh
0x140003662  mov     [rsp+0D0h+lpcValues], rcx; phkResult
0x140003667  xor     r9d, r9d; lpClass
0x14000366a  mov     rcx, [rbp+37h+arg_10]; hKey
0x14000366e  xor     r8d, r8d; Reserved
0x140003671  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpSecurityAttributes
0x140003676  mov     rdx, rdi; lpSubKey
0x140003679  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], eax; samDesired
0x14000367d  mov     dword ptr [rsp+0D0h+lpcSubKeys], esi; dwOptions
0x140003681  call    cs:__imp_RegCreateKeyExW
0x140003688  nop     dword ptr [rax+rax+00h]
0x14000368d  mov     ebx, eax
0x14000368f  test    eax, eax
0x140003691  jnz     loc_140003840
0x140003697  mov     rcx, r12; lpString
0x14000369a  call    cs:__imp_lstrlenW
0x1400036a1  nop     dword ptr [rax+rax+00h]
0x1400036a6  mov     ebx, eax
0x1400036a8  test    rdi, rdi
0x1400036ab  jnz     short loc_1400036B1
0x1400036ad  mov     eax, esi
0x1400036af  jmp     short loc_1400036C0
0x1400036b1  mov     rcx, rdi; lpString
0x1400036b4  call    cs:__imp_lstrlenW
0x1400036bb  nop     dword ptr [rax+rax+00h]
0x1400036c0  lea     ecx, [rbx+3]
0x1400036c3  add     ecx, eax
0x1400036c5  mov     [rbp+37h+cchValueName], ecx
0x1400036c8  add     ecx, ecx; dwBytes
0x1400036ca  call    AllocateMemory
0x1400036cf  mov     [rbp+37h+var_40], rax
0x1400036d3  mov     rsi, rax
0x1400036d6  test    rax, rax
0x1400036d9  jz      loc_140003839
0x1400036df  mov     rcx, r12; lpString
0x1400036e2  call    cs:__imp_lstrlenW
0x1400036e9  nop     dword ptr [rax+rax+00h]
0x1400036ee  test    eax, eax
0x1400036f0  jz      short loc_140003714
0x1400036f2  mov     r8d, [rbp+37h+cchValueName]
0x1400036f6  mov     rdx, r12
0x1400036f9  mov     rcx, rsi
0x1400036fc  call    StringCopyW
0x140003701  mov     r8d, [rbp+37h+cchValueName]
0x140003705  lea     rdx, asc_14001181C; "\\"
0x14000370c  mov     rcx, rsi
0x14000370f  call    StringConcatW
0x140003714  mov     r8d, [rbp+37h+cchValueName]
0x140003718  mov     rdx, rdi
0x14000371b  mov     rcx, rsi
0x14000371e  call    StringConcatW
0x140003723  mov     rcx, r13; lpString
0x140003726  call    cs:__imp_lstrlenW
0x14000372d  nop     dword ptr [rax+rax+00h]
0x140003732  mov     ebx, eax
0x140003734  test    rdi, rdi
0x140003737  jnz     short loc_14000373D
0x140003739  xor     eax, eax
0x14000373b  jmp     short loc_14000374C
0x14000373d  mov     rcx, rdi; lpString
0x140003740  call    cs:__imp_lstrlenW
0x140003747  nop     dword ptr [rax+rax+00h]
0x14000374c  lea     ecx, [rax+3]
0x14000374f  add     ecx, ebx
0x140003751  mov     [rbp+37h+cchValueName], ecx
0x140003754  add     ecx, ecx; dwBytes
0x140003756  call    AllocateMemory
0x14000375b  mov     [rbp+37h+var_38], rax
0x14000375f  mov     rbx, rax
0x140003762  test    rax, rax
0x140003765  jz      loc_140003839
0x14000376b  mov     rcx, r13; lpString
0x14000376e  call    cs:__imp_lstrlenW
0x140003775  nop     dword ptr [rax+rax+00h]
0x14000377a  test    eax, eax
0x14000377c  jz      short loc_1400037A0
0x14000377e  mov     r8d, [rbp+37h+cchValueName]
0x140003782  mov     rdx, r13
0x140003785  mov     rcx, rbx
0x140003788  call    StringCopyW
0x14000378d  mov     r8d, [rbp+37h+cchValueName]
0x140003791  lea     rdx, asc_14001181C; "\\"
0x140003798  mov     rcx, rbx
0x14000379b  call    StringConcatW
0x1400037a0  mov     r8d, [rbp+37h+cchValueName]
0x1400037a4  mov     rdx, rdi
0x1400037a7  mov     rcx, rbx
0x1400037aa  call    StringConcatW
0x1400037af  mov     eax, [rbp+37h+arg_30]
0x1400037b2  mov     r9, rbx
0x1400037b5  mov     ecx, [rbp+37h+arg_38]
0x1400037b8  inc     eax
0x1400037ba  mov     r8, [rbp+37h+phkResult]
0x1400037be  mov     rdx, rsi
0x1400037c1  mov     dword ptr [rsp+0D0h+lpcValues], ecx
0x1400037c5  mov     rcx, [rbp+37h+hKey]
0x1400037c9  mov     dword ptr [rsp+0D0h+lpcbMaxClassLen], eax
0x1400037cd  mov     eax, [rbp+37h+arg_28]
0x1400037d0  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], eax
0x1400037d4  mov     rax, [rbp+37h+arg_20]
0x1400037d8  mov     [rsp+0D0h+lpcSubKeys], rax
0x1400037dd  call    CopyEnumerateKey
0x1400037e2  mov     rcx, [rbp+37h+hKey]; hKey
0x1400037e6  xor     esi, esi
0x1400037e8  mov     ebx, eax
0x1400037ea  test    rcx, rcx
0x1400037ed  jz      short loc_1400037FF
0x1400037ef  call    cs:__imp_RegCloseKey
0x1400037f6  nop     dword ptr [rax+rax+00h]
0x1400037fb  mov     [rbp+37h+hKey], rsi
0x1400037ff  mov     rcx, [rbp+37h+phkResult]; hKey
0x140003803  test    rcx, rcx
0x140003806  jz      short loc_140003818
0x140003808  call    cs:__imp_RegCloseKey
0x14000380f  nop     dword ptr [rax+rax+00h]
0x140003814  mov     [rbp+37h+phkResult], rsi
0x140003818  lea     rcx, [rbp+37h+var_40]
0x14000381c  call    FreeMemory
0x140003821  lea     rcx, [rbp+37h+var_38]
0x140003825  call    FreeMemory
0x14000382a  inc     r14d
0x14000382d  cmp     r14d, [rbp+37h+cSubKeys]
0x140003831  jb      loc_1400035DA
0x140003837  jmp     short loc_140003840
0x140003839  mov     ebx, 0Eh
0x14000383e  xor     esi, esi
  ... truncated ...
```
