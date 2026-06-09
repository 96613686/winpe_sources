# AddRegistry

- ea: `0x14000672c`
- end: `0x140006e63`
- name: `AddRegistry`
- size: `1847`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400031f4`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140002004`
- `0x1400022dc`
- `0x140002b6c`
- `0x140002c20`
- `0x140002ce4`
- `0x140003068`
- `0x14000672c`
- `0x140006e6c`
- `0x14000ce50`
- `0x14000cf2c`
- `0x14000d214`
- `0x14000d2d0`
- `0x14000d65c`
- `0x14000d694`
- `0x14000df14`
- `0x14000e75c`
- `0x14000e798`
- `0x14000e864`
- `0x14000eecc`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006a13`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006a4a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006a13`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006a4a`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x140006a2f`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x140006a2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400068c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400068c1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006bb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006d74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006bb9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006d74`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006861`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140006861`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006896`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000691b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000697c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006d8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006896`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000691b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000697c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006d8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006e18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006e18`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006a8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006a9f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006b34`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006c45`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006c9e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006d40`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006a8c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006a9f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006b34`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006c45`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006c9e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006d40`

## pseudocode

```c
__int64 __fastcall AddRegistry(unsigned int a1, __int64 a2)
{
  unsigned int v4; // esi
  FILE *v5; // rax
  BOOL v6; // r15d
  __int64 v7; // rcx
  unsigned int v8; // edi
  unsigned int Value; // eax
  __int64 v10; // rcx
  const WCHAR *ResString2FromModule; // rbx
  __int64 v12; // rcx
  int v13; // eax
  FILE *v14; // rax
  FILE *v15; // rax
  unsigned int v17; // ebx
  const BYTE *v18; // rax
  LSTATUS v19; // eax
  int v20; // r14d
  __int64 v21; // rax
  __int64 v22; // r8
  const BYTE *v23; // rdi
  unsigned int v24; // r12d
  const WCHAR *v25; // rbx
  int String2; // eax
  int v27; // r13d
  int v28; // eax
  const BYTE *v29; // rbx
  LSTATUS v30; // eax
  unsigned int v31; // ebx
  unsigned int v32; // eax
  unsigned int v33; // r12d
  const BYTE *v34; // r14
  const WCHAR *v35; // rbx
  int *v36; // rax
  DWORD v37; // edi
  __int64 v38; // rcx
  unsigned int v39; // eax
  WCHAR v40; // ax
  BYTE v41; // al
  __int64 v42; // rcx
  FILE *v43; // rbx
  const WCHAR *ResString; // rax
  FILE *v45; // rax
  unsigned int v46; // ebx
  FILE *v47; // rax
  FILE *v48; // rax
  DWORD samDesired; // [rsp+28h] [rbp-D8h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v51; // [rsp+58h] [rbp-A8h] BYREF
  int v52; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v53; // [rsp+60h] [rbp-A0h]
  DWORD dwDisposition; // [rsp+64h] [rbp-9Ch] BYREF
  int v55; // [rsp+68h] [rbp-98h]
  __int64 Memory; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v57; // [rsp+78h] [rbp-88h] BYREF
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v59[4]; // [rsp+90h] [rbp-70h] BYREF
  int v60; // [rsp+94h] [rbp-6Ch]
  HKEY hKey; // [rsp+98h] [rbp-68h]
  DWORD dwType; // [rsp+C8h] [rbp-38h]
  WCHAR String[10]; // [rsp+CCh] [rbp-34h] BYREF
  LPCWSTR lpSubKey; // [rsp+E0h] [rbp-20h]
  LPCWSTR lpValueName; // [rsp+F0h] [rbp-10h]
  LPCWSTR lpString; // [rsp+F8h] [rbp-8h]
  int v67; // [rsp+11Ch] [rbp+1Ch]
  int v68; // [rsp+130h] [rbp+30h] BYREF
  __int16 v69; // [rsp+134h] [rbp+34h]

  v51 = 0;
  phkResult = 0;
  v60 = 0;
  memset_0(v59, 0, 0x94u);
  dwDisposition = 0;
  v68 = 0;
  v69 = 0;
  v52 = 0;
  v58 = 0;
  v57 = 0;
  if ( a1 && a2 )
  {
    v4 = 1;
    InitGlobalData(1, v59);
    if ( !(unsigned int)ParseAddCmdLine(a1, a2, v59, &v52) )
    {
      v5 = o___acrt_iob_func_0(2u);
LABEL_11:
      ShowLastErrorEx(v5);
      goto LABEL_27;
    }
    if ( v52 == 1 )
    {
      Usage(1);
LABEL_7:
      v4 = 0;
LABEL_27:
      FreeGlobalData(v59);
      return v4;
    }
    v6 = RegConnectMachine((__int64)v59);
    if ( !v6 )
    {
      v7 = 0xFFFFFFFFLL;
LABEL_10:
      SaveErrorMessage(v7);
      v5 = o___acrt_iob_func_0(2u);
      goto LABEL_11;
    }
    v8 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, v67 | 0x2001F, 0, &phkResult, &dwDisposition);
    if ( v8 )
    {
LABEL_87:
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      FreeGlobalData(v59);
      if ( v6 )
      {
        if ( !v8 )
        {
          v46 = 0;
          SaveErrorMessage(0);
          v47 = o___acrt_iob_func_0(1u);
          ShowLastErrorEx(v47);
          return v46;
        }
        SaveErrorMessage(v8);
        v45 = o___acrt_iob_func_0(2u);
        ShowLastErrorEx(v45);
      }
      else
      {
        v43 = o___acrt_iob_func_0(2u);
        ResString = (const WCHAR *)GetResString(v8);
        ShowMessage(v43, ResString);
      }
      return 1;
    }
    if ( !phkResult )
    {
      v7 = 1067;
      goto LABEL_10;
    }
    if ( !lpValueName )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
      v7 = 87;
      goto LABEL_10;
    }
    Value = RegQueryValueExW(phkResult, lpValueName, 0, 0, 0, 0);
    if ( Value )
    {
      if ( Value != 2 )
      {
        SaveErrorMessage(Value);
        v15 = o___acrt_iob_func_0(2u);
        ShowLastErrorEx(v15);
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        goto LABEL_27;
      }
    }
    else
    {
      ResString2FromModule = (const WCHAR *)GetResString2FromModule(v10, 202, 0);
      GetResString2FromModule(v12, 206, 1);
      do
        v13 = Prompt(ResString2FromModule);
      while ( v13 > 2 );
      if ( v13 != 1 )
      {
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        SaveErrorMessage(1223);
        v14 = o___acrt_iob_func_0(1u);
        ShowLastErrorEx(v14);
        goto LABEL_7;
      }
    }
    v6 = 1;
    if ( dwType <= 2 )
      goto LABEL_83;
    switch ( dwType )
    {
      case 3u:
        if ( !lpString )
          goto LABEL_84;
        v32 = lstrlenW(lpString);
        v33 = (v32 >> 1) + (v32 & 1) + 1;
        Memory = AllocateMemory(v33);
        v34 = (const BYTE *)Memory;
        if ( !Memory )
          goto LABEL_44;
        v35 = lpString;
        v36 = &v68;
        v37 = 0;
        v38 = 6;
        do
        {
          *(_BYTE *)v36 = 0;
          v36 = (int *)((char *)v36 + 1);
          --v38;
        }
        while ( v38 );
        while ( v35 )
        {
          v39 = lstrlenW(v35);
          v51 = v39;
          if ( v39 <= 1 )
            goto LABEL_82;
          if ( (v39 & 1) != 0 )
            v40 = 48;
          else
            v40 = *v35++;
          LOWORD(v68) = v40;
          HIWORD(v68) = *v35;
          if ( !(unsigned int)IsNumeric(&v68, 16, 1) )
          {
            v6 = 0;
            v8 = 122;
            goto LABEL_63;
          }
          v41 = AsLong(&v68, 16);
          v42 = v37++;
          v34[v42] = v41;
          if ( v37 >= v33 )
          {
            v8 = 1067;
            goto LABEL_63;
          }
          ++v35;
        }
        v51 = 0;
LABEL_82:
        v30 = RegSetValueExW(phkResult, lpValueName, 0, dwType, v34, v37);
        break;
      case 4u:
      case 5u:
        if ( lpString )
        {
          v31 = (unsigned int)StringCompareW(lpString, L"0x") != 0 ? 0xFFFFFFFA : 0;
          if ( (unsigned int)IsNumeric(lpString, v31 + 16, 0) )
          {
            v51 = AsLong(lpString, v31 + 16);
            v18 = (const BYTE *)&v51;
            samDesired = 4;
            goto LABEL_38;
          }
LABEL_39:
          v6 = 0;
          v8 = 121;
          goto LABEL_87;
        }
LABEL_84:
        v8 = 87;
        goto LABEL_87;
      case 7u:
        if ( lpString )
          v20 = lstrlenW(lpString);
        else
          v20 = 0;
        v55 = lstrlenW(String);
        v21 = AllocateMemory((unsigned int)(2 * v20 + 6));
        Memory = v21;
        v23 = (const BYTE *)v21;
        if ( !v21 )
        {
LABEL_44:
          v8 = 8;
          goto LABEL_87;
        }
        v53 = 0;
        v24 = 0;
        v25 = (const WCHAR *)v21;
        if ( v20 > 0 )
        {
          do
          {
            String2 = FindString2(lpString, String, v22, v24);
            v27 = String2;
            if ( String2 == -1 )
            {
              v27 = v20;
            }
            else if ( String2 == v24 )
            {
              v24 = 1;
              goto LABEL_56;
            }
            StringCopyW(v25, &lpString[v24], v27 - v24 + 1);
            if ( v25 )
              v28 = lstrlenW(v25);
            else
              v28 = 0;
            v25 += (unsigned int)(v28 + 1);
            if ( v25 >= (const WCHAR *)&v23[2 * (v20 + 2)] )
              break;
            v24 = v27 + v55;
          }
          while ( v27 + v55 < v20 );
          v24 = v53;
        }
LABEL_56:
        if ( (unsigned int)StringCompareW(lpString, String) )
        {
          if ( v24 == 1 )
          {
            v6 = 0;
            v8 = 123;
LABEL_63:
            FreeMemory(&Memory);
            goto LABEL_87;
          }
          v29 = (const BYTE *)(v25 + 1);
        }
        else
        {
          v29 = v23 + 4;
        }
        v30 = RegSetValueExW(phkResult, lpValueName, 0, dwType, v23, 2 * ((v29 - v23) >> 1));
        break;
      case 0xBu:
        if ( lpString )
        {
          v17 = (unsigned int)StringCompareW(lpString, L"0x") != 0 ? 0xFFFFFFFA : 0;
          *(_DWORD *)_o__errno() = 0;
          v58 = _o__wcstoui64(lpString, &v57, v17 + 16);
          if ( !*v57 && *(_DWORD *)_o__errno() != 34 )
          {
            samDesired = 8;
            v18 = (const BYTE *)&v58;
LABEL_38:
            v19 = RegSetValueExW(phkResult, lpValueName, 0, dwType, v18, samDesired);
LABEL_86:
            v8 = v19;
            goto LABEL_87;
          }
          goto LABEL_39;
        }
        goto LABEL_84;
      default:
LABEL_83:
        if ( lpString )
        {
          v51 = 2 * lstrlenW(lpString) + 2;
          v19 = RegSetValueExW(phkResult, lpValueName, 0, dwType, (const BYTE *)lpString, v51);
          goto LABEL_86;
        }
        goto LABEL_84;
    }
    v8 = v30;
    goto LABEL_63;
  }
  SetLastError(0x57u);
  v48 = o___acrt_iob_func_0(2u);
  ShowLastError(v48);
  return 1;
}

```

## disassembly

```asm
0x14000672c  mov     [rsp-8+arg_10], rbx
0x140006731  push    rbp
0x140006732  push    rsi
0x140006733  push    rdi
0x140006734  push    r12
0x140006736  push    r13
0x140006738  push    r14
0x14000673a  push    r15
0x14000673c  lea     rbp, [rsp-40h]
0x140006741  sub     rsp, 140h
0x140006748  mov     rax, cs:__security_cookie
0x14000674f  xor     rax, rsp
0x140006752  mov     [rbp+70h+var_38], rax
0x140006756  mov     rbx, rdx
0x140006759  mov     edi, ecx
0x14000675b  xor     r13d, r13d
0x14000675e  lea     rcx, [rbp+70h+var_E0]; void *
0x140006762  xor     eax, eax
0x140006764  mov     [rsp+170h+var_118], r13d
0x140006769  xor     edx, edx; Val
0x14000676b  mov     [rsp+170h+var_120], r13
0x140006770  mov     r8d, 94h; Size
0x140006776  mov     [rbp+70h+var_DC], eax
0x140006779  call    memset_0
0x14000677e  xor     eax, eax
0x140006780  mov     [rsp+170h+dwDisposition], r13d
0x140006785  mov     [rbp+70h+var_40], r13d
0x140006789  mov     [rbp+70h+var_3C], ax
0x14000678d  mov     [rsp+170h+var_114], r13d
0x140006792  mov     [rbp+70h+var_F0], r13
0x140006796  mov     [rsp+170h+var_F8], r13
0x14000679b  test    edi, edi
0x14000679d  jz      loc_140006E13
0x1400067a3  test    rbx, rbx
0x1400067a6  jz      loc_140006E13
0x1400067ac  lea     esi, [rax+1]
0x1400067af  mov     ecx, esi
0x1400067b1  lea     rdx, [rbp+70h+var_E0]
0x1400067b5  call    InitGlobalData
0x1400067ba  lea     r9, [rsp+170h+var_114]
0x1400067bf  mov     rdx, rbx
0x1400067c2  lea     r8, [rbp+70h+var_E0]
0x1400067c6  mov     ecx, edi
0x1400067c8  call    ParseAddCmdLine
0x1400067cd  test    eax, eax
0x1400067cf  jnz     short loc_1400067E0
0x1400067d1  lea     ecx, [rsi+1]; Ix
0x1400067d4  call    _o___acrt_iob_func_0
0x1400067d9  mov     edx, 20000h
0x1400067de  jmp     short loc_14000681C
0x1400067e0  cmp     [rsp+170h+var_114], esi
0x1400067e4  jnz     short loc_1400067F5
0x1400067e6  mov     ecx, esi
0x1400067e8  call    Usage
0x1400067ed  mov     esi, r13d
0x1400067f0  jmp     loc_14000698D
0x1400067f5  lea     rcx, [rbp+70h+var_E0]
0x1400067f9  call    RegConnectMachine
0x1400067fe  mov     r15d, eax
0x140006801  test    eax, eax
0x140006803  jnz     short loc_140006829
0x140006805  or      ecx, 0FFFFFFFFh
0x140006808  call    SaveErrorMessage
0x14000680d  mov     ecx, 2; Ix
0x140006812  call    _o___acrt_iob_func_0
0x140006817  mov     edx, 20001h
0x14000681c  mov     rcx, rax
0x14000681f  call    ShowLastErrorEx
0x140006824  jmp     loc_14000698D
0x140006829  mov     eax, [rbp+70h+var_54]
0x14000682c  lea     rcx, [rsp+170h+dwDisposition]
0x140006831  mov     rdx, [rbp+70h+lpSubKey]; lpSubKey
0x140006835  or      eax, 2001Fh
0x14000683a  mov     [rsp+170h+lpdwDisposition], rcx; lpdwDisposition
0x14000683f  xor     r9d, r9d; lpClass
0x140006842  lea     rcx, [rsp+170h+var_120]
0x140006847  xor     r8d, r8d; Reserved
0x14000684a  mov     [rsp+170h+phkResult], rcx; phkResult
0x14000684f  mov     rcx, [rbp+70h+hKey]; hKey
0x140006853  mov     [rsp+170h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140006858  mov     [rsp+170h+samDesired], eax; samDesired
0x14000685c  mov     [rsp+170h+dwOptions], r13d; dwOptions
0x140006861  call    cs:__imp_RegCreateKeyExW
0x140006868  nop     dword ptr [rax+rax+00h]
0x14000686d  mov     edi, eax
0x14000686f  test    eax, eax
0x140006871  jnz     loc_140006D82
0x140006877  mov     rcx, [rsp+170h+var_120]; hKey
0x14000687c  test    rcx, rcx
0x14000687f  jnz     short loc_140006888
0x140006881  mov     ecx, 42Bh
0x140006886  jmp     short loc_140006808
0x140006888  mov     rdx, [rbp+70h+lpValueName]; lpValueName
0x14000688c  test    rdx, rdx
0x14000688f  jnz     short loc_1400068B1
0x140006891  test    rcx, rcx
0x140006894  jz      short loc_1400068A7
0x140006896  call    cs:__imp_RegCloseKey
0x14000689d  nop     dword ptr [rax+rax+00h]
0x1400068a2  mov     [rsp+170h+var_120], r13
0x1400068a7  mov     ecx, 57h ; 'W'
0x1400068ac  jmp     loc_140006808
0x1400068b1  mov     qword ptr [rsp+170h+samDesired], r13; lpcbData
0x1400068b6  xor     r9d, r9d; lpType
0x1400068b9  xor     r8d, r8d; lpReserved
0x1400068bc  mov     qword ptr [rsp+170h+dwOptions], r13; lpData
0x1400068c1  call    cs:__imp_RegQueryValueExW
0x1400068c8  nop     dword ptr [rax+rax+00h]
0x1400068cd  test    eax, eax
0x1400068cf  jnz     short loc_14000694F
0x1400068d1  xor     r8d, r8d
0x1400068d4  mov     edx, 0CAh
0x1400068d9  call    GetResString2FromModule
0x1400068de  mov     r8d, esi
0x1400068e1  mov     edx, 0CEh
0x1400068e6  mov     rbx, rax
0x1400068e9  call    GetResString2FromModule
0x1400068ee  mov     rdi, rax
0x1400068f1  mov     r9d, [rbp+70h+var_C8]
0x1400068f5  mov     r8, rdi
0x1400068f8  mov     rdx, [rbp+70h+lpValueName]
0x1400068fc  mov     rcx, rbx
0x1400068ff  call    Prompt
0x140006904  cmp     eax, 2
0x140006907  jg      short loc_1400068F1
0x140006909  cmp     eax, esi
0x14000690b  jz      loc_14000699D
0x140006911  mov     rcx, [rsp+170h+var_120]; hKey
0x140006916  test    rcx, rcx
0x140006919  jz      short loc_14000692C
0x14000691b  call    cs:__imp_RegCloseKey
0x140006922  nop     dword ptr [rax+rax+00h]
0x140006927  mov     [rsp+170h+var_120], r13
0x14000692c  mov     ecx, 4C7h
0x140006931  call    SaveErrorMessage
0x140006936  mov     ecx, esi; Ix
0x140006938  call    _o___acrt_iob_func_0
0x14000693d  mov     rcx, rax
0x140006940  mov     edx, 20000h
0x140006945  call    ShowLastErrorEx
0x14000694a  jmp     loc_1400067ED
0x14000694f  cmp     eax, 2
0x140006952  jz      short loc_14000699D
0x140006954  mov     ecx, eax
0x140006956  call    SaveErrorMessage
0x14000695b  mov     ecx, 2; Ix
0x140006960  call    _o___acrt_iob_func_0
0x140006965  mov     rcx, rax
0x140006968  mov     edx, 20001h
0x14000696d  call    ShowLastErrorEx
0x140006972  mov     rcx, [rsp+170h+var_120]; hKey
0x140006977  test    rcx, rcx
0x14000697a  jz      short loc_14000698D
0x14000697c  call    cs:__imp_RegCloseKey
0x140006983  nop     dword ptr [rax+rax+00h]
0x140006988  mov     [rsp+170h+var_120], r13
0x14000698d  lea     rcx, [rbp+70h+var_E0]
0x140006991  call    FreeGlobalData
0x140006996  mov     eax, esi
0x140006998  jmp     loc_140006E3B
0x14000699d  mov     r9d, [rbp+70h+dwType]
0x1400069a1  mov     r15d, esi
0x1400069a4  mov     ecx, r9d
0x1400069a7  test    r9d, r9d
0x1400069aa  jz      loc_140006D30
0x1400069b0  sub     ecx, esi
0x1400069b2  jz      loc_140006D30
0x1400069b8  sub     ecx, esi
0x1400069ba  jz      loc_140006D30
0x1400069c0  sub     ecx, esi
0x1400069c2  jz      loc_140006C38
0x1400069c8  sub     ecx, esi
0x1400069ca  jz      loc_140006BD6
0x1400069d0  sub     ecx, esi
0x1400069d2  jz      loc_140006BD6
0x1400069d8  sub     ecx, 2
0x1400069db  jz      loc_140006A7E
0x1400069e1  cmp     ecx, 4
0x1400069e4  jnz     loc_140006D30
0x1400069ea  mov     rcx, [rbp+70h+lpString]; lpString1
0x1400069ee  test    rcx, rcx
0x1400069f1  jz      loc_140006D39
0x1400069f7  mov     r9d, 2
0x1400069fd  lea     rdx, a0x; "0x"
0x140006a04  mov     r8d, esi
0x140006a07  call    StringCompareW
0x140006a0c  neg     eax
0x140006a0e  sbb     ebx, ebx
0x140006a10  and     ebx, 0FFFFFFFAh
0x140006a13  call    cs:__imp__o__errno
0x140006a1a  nop     dword ptr [rax+rax+00h]
0x140006a1f  lea     r8d, [rbx+10h]
0x140006a23  lea     rdx, [rsp+170h+var_F8]
0x140006a28  mov     [rax], r13d
0x140006a2b  mov     rcx, [rbp+70h+lpString]
0x140006a2f  call    cs:__imp__o__wcstoui64
0x140006a36  nop     dword ptr [rax+rax+00h]
0x140006a3b  mov     [rbp+70h+var_F0], rax
0x140006a3f  mov     rax, [rsp+170h+var_F8]
0x140006a44  cmp     [rax], r13w
0x140006a48  jnz     short loc_140006A71
0x140006a4a  call    cs:__imp__o__errno
0x140006a51  nop     dword ptr [rax+rax+00h]
0x140006a56  cmp     dword ptr [rax], 22h ; '"'
0x140006a59  jz      short loc_140006A71
0x140006a5b  mov     [rsp+170h+samDesired], 8
0x140006a63  lea     rax, [rbp+70h+var_F0]
0x140006a67  mov     qword ptr [rsp+170h+dwOptions], rax
0x140006a6c  jmp     loc_140006D64
0x140006a71  mov     r15d, r13d
0x140006a74  mov     edi, 79h ; 'y'
0x140006a79  jmp     loc_140006D82
0x140006a7e  mov     rcx, [rbp+70h+lpString]; lpString
0x140006a82  test    rcx, rcx
0x140006a85  jnz     short loc_140006A8C
0x140006a87  mov     r14d, r13d
0x140006a8a  jmp     short loc_140006A9B
0x140006a8c  call    cs:__imp_lstrlenW
0x140006a93  nop     dword ptr [rax+rax+00h]
0x140006a98  mov     r14d, eax
0x140006a9b  lea     rcx, [rbp+70h+String]; lpString
0x140006a9f  call    cs:__imp_lstrlenW
0x140006aa6  nop     dword ptr [rax+rax+00h]
0x140006aab  lea     ecx, ds:6[r14*2]; dwBytes
0x140006ab3  mov     [rsp+170h+var_108], eax
0x140006ab7  call    AllocateMemory
0x140006abc  mov     [rsp+170h+var_100], rax
0x140006ac1  mov     rdi, rax
0x140006ac4  test    rax, rax
0x140006ac7  jnz     short loc_140006AD3
0x140006ac9  mov     edi, 8
0x140006ace  jmp     loc_140006D82
0x140006ad3  mov     [rsp+170h+var_110], r13d
0x140006ad8  mov     r12d, r13d
0x140006adb  mov     rbx, rdi
0x140006ade  test    r14d, r14d
0x140006ae1  jle     loc_140006B68
0x140006ae7  mov     rcx, [rbp+70h+lpString]
0x140006aeb  lea     rdx, [rbp+70h+String]
0x140006aef  mov     r9d, r12d
0x140006af2  call    FindString2
0x140006af7  mov     r13d, eax
0x140006afa  cmp     eax, 0FFFFFFFFh
0x140006afd  jz      short loc_140006B09
0x140006aff  cmp     eax, r12d
0x140006b02  jnz     short loc_140006B0C
0x140006b04  mov     r12d, esi
0x140006b07  jmp     short loc_140006B65
0x140006b09  mov     r13d, r14d
0x140006b0c  mov     rax, [rbp+70h+lpString]
0x140006b10  mov     r8d, r13d
0x140006b13  movsxd  rcx, r12d
0x140006b16  sub     r8d, r12d
0x140006b19  add     r8d, esi
0x140006b1c  lea     rdx, [rax+rcx*2]
0x140006b20  mov     rcx, rbx
0x140006b23  call    StringCopyW
0x140006b28  test    rbx, rbx
0x140006b2b  jnz     short loc_140006B31
0x140006b2d  xor     eax, eax
0x140006b2f  jmp     short loc_140006B40
0x140006b31  mov     rcx, rbx; lpString
0x140006b34  call    cs:__imp_lstrlenW
0x140006b3b  nop     dword ptr [rax+rax+00h]
0x140006b40  inc     eax
0x140006b42  lea     rbx, [rbx+rax*2]
0x140006b46  lea     eax, [r14+2]
0x140006b4a  lea     rcx, [rdi+rax*2]
0x140006b4e  cmp     rbx, rcx
0x140006b51  jnb     short loc_140006B60
0x140006b53  mov     r12d, [rsp+170h+var_108]
0x140006b58  add     r12d, r13d
0x140006b5b  cmp     r12d, r14d
0x140006b5e  jl      short loc_140006AE7
0x140006b60  mov     r12d, [rsp+170h+var_110]
0x140006b65  xor     r13d, r13d
0x140006b68  mov     rcx, [rbp+70h+lpString]; lpString1
0x140006b6c  lea     rdx, [rbp+70h+String]; lpString2
0x140006b70  xor     r9d, r9d
0x140006b73  mov     r8d, esi
0x140006b76  call    StringCompareW
0x140006b7b  test    eax, eax
0x140006b7d  jnz     short loc_140006B85
0x140006b7f  lea     rbx, [rdi+4]
0x140006b83  jmp     short loc_140006B98
0x140006b85  cmp     r12d, esi
0x140006b88  jnz     short loc_140006B94
0x140006b8a  mov     r15d, r13d
0x140006b8d  mov     edi, 7Bh ; '{'
0x140006b92  jmp     short loc_140006BC7
0x140006b94  add     rbx, 2
0x140006b98  sub     rbx, rdi
0x140006b9b  sar     rbx, 1
0x140006b9e  add     ebx, ebx
0x140006ba0  mov     [rsp+170h+samDesired], ebx; cbData
0x140006ba4  mov     qword ptr [rsp+170h+dwOptions], rdi; lpData
0x140006ba9  mov     r9d, [rbp+70h+dwType]; dwType
0x140006bad  xor     r8d, r8d; Reserved
0x140006bb0  mov     rdx, [rbp+70h+lpValueName]; lpValueName
0x140006bb4  mov     rcx, [rsp+170h+var_120]; hKey
  ... truncated ...
```
