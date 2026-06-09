# AddRegistry

- ea: `0x140006394`
- end: `0x140006a56`
- name: `AddRegistry`
- size: `1730`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400030b8`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140001fec`
- `0x140002234`
- `0x140002a28`
- `0x140002ac8`
- `0x140002b70`
- `0x140002f30`
- `0x140006394`
- `0x140006a5c`
- `0x14000c62c`
- `0x14000c6d0`
- `0x14000c924`
- `0x14000c9c0`
- `0x14000cd10`
- `0x14000cd48`
- `0x14000d4cc`
- `0x14000dbe8`
- `0x14000dc24`
- `0x14000dce0`
- `0x14000e284`
- `0x14000e450`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000665d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006688`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000665d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140006688`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x140006673`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x140006673`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000651d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000651d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400067db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000697a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400067db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000697a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400064c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400064c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400064f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400065cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000698c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400064f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006571`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400065cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000698c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006a12`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140006a12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400066c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400066d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000675c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006861`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400068b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000694c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400066c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400066d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000675c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140006861`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1400068b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000694c`

## pseudocode

```c
__int64 __fastcall AddRegistry(unsigned int a1, __int64 a2)
{
  unsigned int v4; // esi
  FILE *v5; // rax
  int v6; // r15d
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
  const BYTE *v21; // rax
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
  const BYTE *Memory; // [rsp+70h] [rbp-90h] BYREF
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
    v6 = RegConnectMachine(v59);
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
        Memory = (const BYTE *)AllocateMemory(v33);
        v34 = Memory;
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
        v21 = (const BYTE *)AllocateMemory((unsigned int)(2 * v20 + 6));
        Memory = v21;
        v23 = v21;
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
0x140006394  mov     [rsp-8+arg_10], rbx
0x140006399  push    rbp
0x14000639a  push    rsi
0x14000639b  push    rdi
0x14000639c  push    r12
0x14000639e  push    r13
0x1400063a0  push    r14
0x1400063a2  push    r15
0x1400063a4  lea     rbp, [rsp-40h]
0x1400063a9  sub     rsp, 140h
0x1400063b0  mov     rax, cs:__security_cookie
0x1400063b7  xor     rax, rsp
0x1400063ba  mov     [rbp+70h+var_38], rax
0x1400063be  mov     rbx, rdx
0x1400063c1  mov     edi, ecx
0x1400063c3  xor     r13d, r13d
0x1400063c6  lea     rcx, [rbp+70h+var_E0]; void *
0x1400063ca  xor     eax, eax
0x1400063cc  mov     [rsp+170h+var_118], r13d
0x1400063d1  xor     edx, edx; Val
0x1400063d3  mov     [rsp+170h+var_120], r13
0x1400063d8  mov     r8d, 94h; Size
0x1400063de  mov     [rbp+70h+var_DC], eax
0x1400063e1  call    memset_0
0x1400063e6  xor     eax, eax
0x1400063e8  mov     [rsp+170h+dwDisposition], r13d
0x1400063ed  mov     [rbp+70h+var_40], r13d
0x1400063f1  mov     [rbp+70h+var_3C], ax
0x1400063f5  mov     [rsp+170h+var_114], r13d
0x1400063fa  mov     [rbp+70h+var_F0], r13
0x1400063fe  mov     [rsp+170h+var_F8], r13
0x140006403  test    edi, edi
0x140006405  jz      loc_140006A0D
0x14000640b  test    rbx, rbx
0x14000640e  jz      loc_140006A0D
0x140006414  lea     esi, [rax+1]
0x140006417  mov     ecx, esi
0x140006419  lea     rdx, [rbp+70h+var_E0]
0x14000641d  call    InitGlobalData
0x140006422  lea     r9, [rsp+170h+var_114]
0x140006427  mov     rdx, rbx
0x14000642a  lea     r8, [rbp+70h+var_E0]
0x14000642e  mov     ecx, edi
0x140006430  call    ParseAddCmdLine
0x140006435  test    eax, eax
0x140006437  jnz     short loc_140006448
0x140006439  lea     ecx, [rsi+1]; Ix
0x14000643c  call    _o___acrt_iob_func_0
0x140006441  mov     edx, 20000h
0x140006446  jmp     short loc_140006484
0x140006448  cmp     [rsp+170h+var_114], esi
0x14000644c  jnz     short loc_14000645D
0x14000644e  mov     ecx, esi
0x140006450  call    Usage
0x140006455  mov     esi, r13d
0x140006458  jmp     loc_1400065D7
0x14000645d  lea     rcx, [rbp+70h+var_E0]
0x140006461  call    RegConnectMachine
0x140006466  mov     r15d, eax
0x140006469  test    eax, eax
0x14000646b  jnz     short loc_140006491
0x14000646d  or      ecx, 0FFFFFFFFh
0x140006470  call    SaveErrorMessage
0x140006475  mov     ecx, 2; Ix
0x14000647a  call    _o___acrt_iob_func_0
0x14000647f  mov     edx, 20001h
0x140006484  mov     rcx, rax
0x140006487  call    ShowLastErrorEx
0x14000648c  jmp     loc_1400065D7
0x140006491  mov     eax, [rbp+70h+var_54]
0x140006494  lea     rcx, [rsp+170h+dwDisposition]
0x140006499  mov     rdx, [rbp+70h+lpSubKey]; lpSubKey
0x14000649d  or      eax, 2001Fh
0x1400064a2  mov     [rsp+170h+lpdwDisposition], rcx; lpdwDisposition
0x1400064a7  xor     r9d, r9d; lpClass
0x1400064aa  lea     rcx, [rsp+170h+var_120]
0x1400064af  xor     r8d, r8d; Reserved
0x1400064b2  mov     [rsp+170h+phkResult], rcx; phkResult
0x1400064b7  mov     rcx, [rbp+70h+hKey]; hKey
0x1400064bb  mov     [rsp+170h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1400064c0  mov     [rsp+170h+samDesired], eax; samDesired
0x1400064c4  mov     [rsp+170h+dwOptions], r13d; dwOptions
0x1400064c9  call    cs:__imp_RegCreateKeyExW
0x1400064cf  mov     edi, eax
0x1400064d1  test    eax, eax
0x1400064d3  jnz     loc_140006982
0x1400064d9  mov     rcx, [rsp+170h+var_120]; hKey
0x1400064de  test    rcx, rcx
0x1400064e1  jnz     short loc_1400064EA
0x1400064e3  mov     ecx, 42Bh
0x1400064e8  jmp     short loc_140006470
0x1400064ea  mov     rdx, [rbp+70h+lpValueName]; lpValueName
0x1400064ee  test    rdx, rdx
0x1400064f1  jnz     short loc_14000650D
0x1400064f3  test    rcx, rcx
0x1400064f6  jz      short loc_140006503
0x1400064f8  call    cs:__imp_RegCloseKey
0x1400064fe  mov     [rsp+170h+var_120], r13
0x140006503  mov     ecx, 57h ; 'W'
0x140006508  jmp     loc_140006470
0x14000650d  mov     qword ptr [rsp+170h+samDesired], r13; lpcbData
0x140006512  xor     r9d, r9d; lpType
0x140006515  xor     r8d, r8d; lpReserved
0x140006518  mov     qword ptr [rsp+170h+dwOptions], r13; lpData
0x14000651d  call    cs:__imp_RegQueryValueExW
0x140006523  test    eax, eax
0x140006525  jnz     short loc_14000659F
0x140006527  xor     r8d, r8d
0x14000652a  mov     edx, 0CAh
0x14000652f  call    GetResString2FromModule
0x140006534  mov     r8d, esi
0x140006537  mov     edx, 0CEh
0x14000653c  mov     rbx, rax
0x14000653f  call    GetResString2FromModule
0x140006544  mov     rdi, rax
0x140006547  mov     r9d, [rbp+70h+var_C8]
0x14000654b  mov     r8, rdi
0x14000654e  mov     rdx, [rbp+70h+lpValueName]
0x140006552  mov     rcx, rbx
0x140006555  call    Prompt
0x14000655a  cmp     eax, 2
0x14000655d  jg      short loc_140006547
0x14000655f  cmp     eax, esi
0x140006561  jz      loc_1400065E7
0x140006567  mov     rcx, [rsp+170h+var_120]; hKey
0x14000656c  test    rcx, rcx
0x14000656f  jz      short loc_14000657C
0x140006571  call    cs:__imp_RegCloseKey
0x140006577  mov     [rsp+170h+var_120], r13
0x14000657c  mov     ecx, 4C7h
0x140006581  call    SaveErrorMessage
0x140006586  mov     ecx, esi; Ix
0x140006588  call    _o___acrt_iob_func_0
0x14000658d  mov     rcx, rax
0x140006590  mov     edx, 20000h
0x140006595  call    ShowLastErrorEx
0x14000659a  jmp     loc_140006455
0x14000659f  cmp     eax, 2
0x1400065a2  jz      short loc_1400065E7
0x1400065a4  mov     ecx, eax
0x1400065a6  call    SaveErrorMessage
0x1400065ab  mov     ecx, 2; Ix
0x1400065b0  call    _o___acrt_iob_func_0
0x1400065b5  mov     rcx, rax
0x1400065b8  mov     edx, 20001h
0x1400065bd  call    ShowLastErrorEx
0x1400065c2  mov     rcx, [rsp+170h+var_120]; hKey
0x1400065c7  test    rcx, rcx
0x1400065ca  jz      short loc_1400065D7
0x1400065cc  call    cs:__imp_RegCloseKey
0x1400065d2  mov     [rsp+170h+var_120], r13
0x1400065d7  lea     rcx, [rbp+70h+var_E0]
0x1400065db  call    FreeGlobalData
0x1400065e0  mov     eax, esi
0x1400065e2  jmp     loc_140006A2F
0x1400065e7  mov     r9d, [rbp+70h+dwType]
0x1400065eb  mov     r15d, esi
0x1400065ee  mov     ecx, r9d
0x1400065f1  test    r9d, r9d
0x1400065f4  jz      loc_14000693C
0x1400065fa  sub     ecx, esi
0x1400065fc  jz      loc_14000693C
0x140006602  sub     ecx, esi
0x140006604  jz      loc_14000693C
0x14000660a  sub     ecx, esi
0x14000660c  jz      loc_140006854
0x140006612  sub     ecx, esi
0x140006614  jz      loc_1400067F2
0x14000661a  sub     ecx, esi
0x14000661c  jz      loc_1400067F2
0x140006622  sub     ecx, 2
0x140006625  jz      loc_1400066B6
0x14000662b  cmp     ecx, 4
0x14000662e  jnz     loc_14000693C
0x140006634  mov     rcx, [rbp+70h+lpString]; lpString1
0x140006638  test    rcx, rcx
0x14000663b  jz      loc_140006945
0x140006641  mov     r9d, 2
0x140006647  lea     rdx, a0x; "0x"
0x14000664e  mov     r8d, esi
0x140006651  call    StringCompareW
0x140006656  neg     eax
0x140006658  sbb     ebx, ebx
0x14000665a  and     ebx, 0FFFFFFFAh
0x14000665d  call    cs:__imp__o__errno
0x140006663  lea     r8d, [rbx+10h]
0x140006667  lea     rdx, [rsp+170h+var_F8]
0x14000666c  mov     [rax], r13d
0x14000666f  mov     rcx, [rbp+70h+lpString]
0x140006673  call    cs:__imp__o__wcstoui64
0x140006679  mov     [rbp+70h+var_F0], rax
0x14000667d  mov     rax, [rsp+170h+var_F8]
0x140006682  cmp     [rax], r13w
0x140006686  jnz     short loc_1400066A9
0x140006688  call    cs:__imp__o__errno
0x14000668e  cmp     dword ptr [rax], 22h ; '"'
0x140006691  jz      short loc_1400066A9
0x140006693  mov     [rsp+170h+samDesired], 8
0x14000669b  lea     rax, [rbp+70h+var_F0]
0x14000669f  mov     qword ptr [rsp+170h+dwOptions], rax
0x1400066a4  jmp     loc_14000696A
0x1400066a9  mov     r15d, r13d
0x1400066ac  mov     edi, 79h ; 'y'
0x1400066b1  jmp     loc_140006982
0x1400066b6  mov     rcx, [rbp+70h+lpString]; lpString
0x1400066ba  test    rcx, rcx
0x1400066bd  jnz     short loc_1400066C4
0x1400066bf  mov     r14d, r13d
0x1400066c2  jmp     short loc_1400066CD
0x1400066c4  call    cs:__imp_lstrlenW
0x1400066ca  mov     r14d, eax
0x1400066cd  lea     rcx, [rbp+70h+String]; lpString
0x1400066d1  call    cs:__imp_lstrlenW
0x1400066d7  lea     ecx, ds:6[r14*2]; dwBytes
0x1400066df  mov     [rsp+170h+var_108], eax
0x1400066e3  call    AllocateMemory
0x1400066e8  mov     [rsp+170h+var_100], rax
0x1400066ed  mov     rdi, rax
0x1400066f0  test    rax, rax
0x1400066f3  jnz     short loc_1400066FF
0x1400066f5  mov     edi, 8
0x1400066fa  jmp     loc_140006982
0x1400066ff  mov     [rsp+170h+var_110], r13d
0x140006704  mov     r12d, r13d
0x140006707  mov     rbx, rdi
0x14000670a  test    r14d, r14d
0x14000670d  jle     short loc_14000678A
0x14000670f  mov     rcx, [rbp+70h+lpString]
0x140006713  lea     rdx, [rbp+70h+String]
0x140006717  mov     r9d, r12d
0x14000671a  call    FindString2
0x14000671f  mov     r13d, eax
0x140006722  cmp     eax, 0FFFFFFFFh
0x140006725  jz      short loc_140006731
0x140006727  cmp     eax, r12d
0x14000672a  jnz     short loc_140006734
0x14000672c  mov     r12d, esi
0x14000672f  jmp     short loc_140006787
0x140006731  mov     r13d, r14d
0x140006734  mov     rax, [rbp+70h+lpString]
0x140006738  mov     r8d, r13d
0x14000673b  movsxd  rcx, r12d
0x14000673e  sub     r8d, r12d
0x140006741  add     r8d, esi
0x140006744  lea     rdx, [rax+rcx*2]
0x140006748  mov     rcx, rbx
0x14000674b  call    StringCopyW
0x140006750  test    rbx, rbx
0x140006753  jnz     short loc_140006759
0x140006755  xor     eax, eax
0x140006757  jmp     short loc_140006762
0x140006759  mov     rcx, rbx; lpString
0x14000675c  call    cs:__imp_lstrlenW
0x140006762  inc     eax
0x140006764  lea     rbx, [rbx+rax*2]
0x140006768  lea     eax, [r14+2]
0x14000676c  lea     rcx, [rdi+rax*2]
0x140006770  cmp     rbx, rcx
0x140006773  jnb     short loc_140006782
0x140006775  mov     r12d, [rsp+170h+var_108]
0x14000677a  add     r12d, r13d
0x14000677d  cmp     r12d, r14d
0x140006780  jl      short loc_14000670F
0x140006782  mov     r12d, [rsp+170h+var_110]
0x140006787  xor     r13d, r13d
0x14000678a  mov     rcx, [rbp+70h+lpString]; lpString1
0x14000678e  lea     rdx, [rbp+70h+String]; lpString2
0x140006792  xor     r9d, r9d
0x140006795  mov     r8d, esi
0x140006798  call    StringCompareW
0x14000679d  test    eax, eax
0x14000679f  jnz     short loc_1400067A7
0x1400067a1  lea     rbx, [rdi+4]
0x1400067a5  jmp     short loc_1400067BA
0x1400067a7  cmp     r12d, esi
0x1400067aa  jnz     short loc_1400067B6
0x1400067ac  mov     r15d, r13d
0x1400067af  mov     edi, 7Bh ; '{'
0x1400067b4  jmp     short loc_1400067E3
0x1400067b6  add     rbx, 2
0x1400067ba  sub     rbx, rdi
0x1400067bd  sar     rbx, 1
0x1400067c0  add     ebx, ebx
0x1400067c2  mov     [rsp+170h+samDesired], ebx; cbData
0x1400067c6  mov     qword ptr [rsp+170h+dwOptions], rdi; lpData
0x1400067cb  mov     r9d, [rbp+70h+dwType]; dwType
0x1400067cf  xor     r8d, r8d; Reserved
0x1400067d2  mov     rdx, [rbp+70h+lpValueName]; lpValueName
0x1400067d6  mov     rcx, [rsp+170h+var_120]; hKey
0x1400067db  call    cs:__imp_RegSetValueExW
0x1400067e1  mov     edi, eax
0x1400067e3  lea     rcx, [rsp+170h+var_100]
0x1400067e8  call    FreeMemory
0x1400067ed  jmp     loc_140006982
0x1400067f2  mov     rcx, [rbp+70h+lpString]; lpString1
0x1400067f6  test    rcx, rcx
0x1400067f9  jz      loc_140006945
0x1400067ff  mov     r9d, 2
0x140006805  lea     rdx, a0x; "0x"
0x14000680c  mov     r8d, esi
  ... truncated ...
```
