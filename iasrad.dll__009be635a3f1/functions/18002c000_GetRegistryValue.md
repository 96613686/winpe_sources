# GetRegistryValue

- ea: `0x18002c000`
- end: `0x18002c4bc`
- name: `GetRegistryValue`
- size: `1212`
- prototype: `__int64 __fastcall(int, int, int, int, VARIANTARG *pvarg)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x180014e98`
- `0x1800178b8`

## callees

- `0x1800094e4`
- `0x180009540`
- `0x18000a430`
- `0x18000dc54`
- `0x18000e4e0`
- `0x1800160b4`
- `0x18001d31c`
- `0x18002b110`
- `0x18002b1d4`
- `0x18002be2c`
- `0x18002c000`
- `0x18002c4c4`
- `0x18002e202`

## import_xrefs

- `msvcrt!free` at `0x18002c4a5`
- `msvcrt!free` at `0x18002c4a5`
- `ADVAPI32!RegQueryValueExW` at `0x18002c0f5`
- `ADVAPI32!RegQueryValueExW` at `0x18002c210`
- `ADVAPI32!RegQueryValueExW` at `0x18002c0f5`
- `ADVAPI32!RegQueryValueExW` at `0x18002c210`
- `ADVAPI32!RegOpenKeyExW` at `0x18002c051`
- `ADVAPI32!RegOpenKeyExW` at `0x18002c051`
- `ADVAPI32!RegCloseKey` at `0x18002c497`
- `ADVAPI32!RegCloseKey` at `0x18002c497`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c45d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c484`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c45d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002c484`
- `OLEAUT32!__imp_VariantInit` at `0x18002c2f1`
- `OLEAUT32!__imp_VariantInit` at `0x18002c2f1`

## string_xrefs

- `0x18002c02b`: `SYSTEM\CurrentControlSet\Services\EapHost\Configuration`
- `0x18002c08b`: `RegOpenKeyEx (HKLM\%S) failed with 0x%x`
- `0x18002c1af`: `Not enough memory to allocate registry value`
- `0x18002c2b3`: `Mismatched registry value type %S`

## pseudocode

```c
__int64 __fastcall GetRegistryValue(__int64 a1, const OLECHAR **a2, __int64 a3, __int64 a4, VARIANTARG *pvarg)
{
  BYTE *lpData; // rdi
  unsigned int v6; // ebx
  LSTATUS Value; // eax
  const struct std::nothrow_t *v8; // rdx
  BYTE *v9; // rax
  LSTATUS v10; // eax
  VARIANTARG *v11; // rsi
  const unsigned __int16 *v12; // r14
  __int64 v13; // rax
  const OLECHAR *v14; // rcx
  _BYTE v16[8]; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v17[8]; // [rsp+48h] [rbp-18h] BYREF
  _BYTE v18[8]; // [rsp+50h] [rbp-10h] BYREF
  _BYTE v19[8]; // [rsp+58h] [rbp-8h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+40h] BYREF
  const OLECHAR **v21; // [rsp+A8h] [rbp+48h] BYREF
  __int64 cbData; // [rsp+B0h] [rbp+50h] BYREF
  __int64 Type; // [rsp+B8h] [rbp+58h] BYREF

  Type = a4;
  cbData = a3;
  v21 = a2;
  hKey = 0;
  lpData = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\EapHost\\Configuration", 0, 1u, &hKey);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("RegOpenKeyEx (HKLM\\%S) failed with 0x%x");
      WPP_SF_sSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\EapHost\\Configuration",
        v6);
    }
    goto LABEL_47;
  }
  LODWORD(cbData) = 0;
  LODWORD(Type) = 0;
  Value = RegQueryValueExW(hKey, L"IdentityEncodingFormat", 0, (LPDWORD)&Type, 0, (LPDWORD)&cbData);
  v6 = Value;
  if ( Value )
  {
    if ( Value == 2
      || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_47;
    }
    goto LABEL_11;
  }
  v9 = (BYTE *)operator new[]((unsigned int)cbData, v8);
  lpData = v9;
  if ( v9 )
  {
    memset_0(v9, 0, (unsigned int)cbData);
    v10 = RegQueryValueExW(hKey, L"IdentityEncodingFormat", 0, (LPDWORD)&Type, lpData, (LPDWORD)&cbData);
    v6 = v10;
    if ( v10 )
    {
      if ( v10 == 2
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_47;
      }
LABEL_11:
      WppDbgPrint("RegQueryValueEx(%S\\%S) failed with 0x%x");
      WPP_SF_sSSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\EapHost\\Configuration",
        (__int64)L"IdentityEncodingFormat",
        v6);
      goto LABEL_47;
    }
    if ( (_DWORD)Type == (unsigned int)GetRegistryValueType() )
    {
      v11 = pvarg;
      VariantInit(pvarg);
      switch ( (_DWORD)Type )
      {
        case 1:
          v11->vt = 8;
          v11->llVal = (LONGLONG)SysAllocString((const OLECHAR *)lpData);
          break;
        case 4:
          v11->vt = 3;
          v11->lVal = *(_DWORD *)lpData;
          break;
        case 7:
          v11->vt = 8;
          v12 = (const unsigned __int16 *)lpData;
          v21 = 0;
          if ( !*(_WORD *)lpData )
            goto LABEL_43;
          do
          {
            _bstr_t::_bstr_t((_bstr_t *)v16, L"\"");
            _bstr_t::operator+=((struct _bstr_t *)&v21, (struct _bstr_t *)v16);
            _bstr_t::_Free((_bstr_t *)v16);
            _bstr_t::_bstr_t((_bstr_t *)v17, v12);
            _bstr_t::operator+=((struct _bstr_t *)&v21, (struct _bstr_t *)v17);
            _bstr_t::_Free((_bstr_t *)v17);
            _bstr_t::_bstr_t((_bstr_t *)v18, L"\"");
            _bstr_t::operator+=((struct _bstr_t *)&v21, (struct _bstr_t *)v18);
            _bstr_t::_Free((_bstr_t *)v18);
            v13 = -1;
            do
              ++v13;
            while ( v12[v13] );
            v12 += v13 + 1;
            if ( !*v12 )
              break;
            _bstr_t::_bstr_t((_bstr_t *)v19, L",");
            _bstr_t::operator+=((struct _bstr_t *)&v21, (struct _bstr_t *)v19);
            _bstr_t::_Free((_bstr_t *)v19);
          }
          while ( *v12 );
          if ( v21 )
            v14 = *v21;
          else
LABEL_43:
            v14 = 0;
          v11->llVal = (LONGLONG)SysAllocString(v14);
          _bstr_t::_Free((_bstr_t *)&v21);
          break;
        default:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WppDbgPrint("Unexpected reg type %d");
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              (unsigned int)WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
              (unsigned int)"NAPBASE",
              Type);
          }
          break;
      }
    }
    else
    {
      v6 = 87;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WppDbgPrint("Mismatched registry value type %S");
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          (unsigned int)WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
          (unsigned int)"NAPBASE",
          (__int64)L"REG_DWORD");
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("Not enough memory to allocate registry value");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids, "NAPBASE");
    }
    v6 = 14;
  }
LABEL_47:
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpData )
    free(lpData);
  return v6;
}

```

## disassembly

```asm
0x18002c000  mov     r11, rsp
0x18002c003  mov     [r11+20h], r9
0x18002c007  mov     [r11+18h], r8
0x18002c00b  mov     [r11+10h], rdx
0x18002c00f  mov     [r11+8], rcx
0x18002c013  push    rbp
0x18002c014  push    rbx
0x18002c015  push    rsi
0x18002c016  push    rdi
0x18002c017  push    r12
0x18002c019  push    r14
0x18002c01b  push    r15
0x18002c01d  mov     rbp, rsp
0x18002c020  sub     rsp, 60h
0x18002c024  xor     r15d, r15d
0x18002c027  lea     rax, [rbp+hKey]
0x18002c02b  lea     rsi, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x18002c032  mov     [rbp+hKey], r15
0x18002c036  xor     r8d, r8d; ulOptions
0x18002c039  mov     [r11-78h], rax
0x18002c03d  mov     rdx, rsi; lpSubKey
0x18002c040  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c047  lea     r14d, [r15+1]
0x18002c04b  mov     edi, r15d
0x18002c04e  mov     r9d, r14d; samDesired
0x18002c051  call    cs:__imp_RegOpenKeyExW
0x18002c057  mov     ebx, eax
0x18002c059  test    eax, eax
0x18002c05b  jz      short loc_18002C0CA
0x18002c05d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c064  lea     rax, WPP_GLOBAL_Control
0x18002c06b  cmp     rcx, rax
0x18002c06e  jz      loc_18002C48E
0x18002c074  cmp     byte ptr [rcx+19h], 2
0x18002c078  jb      loc_18002C48E
0x18002c07e  test    [rcx+1Ch], r14b
0x18002c082  jz      loc_18002C48E
0x18002c088  mov     r8d, ebx
0x18002c08b  lea     rcx, aRegopenkeyexHk; "RegOpenKeyEx (HKLM\\%S) failed with 0x%"...
0x18002c092  mov     rdx, rsi
0x18002c095  call    WppDbgPrint
0x18002c09a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0a1  lea     edx, [r15+22h]
0x18002c0a5  mov     dword ptr [rsp+60h+lpcbData], ebx
0x18002c0a9  lea     r9, aNapbase; "NAPBASE"
0x18002c0b0  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002c0b7  mov     [rsp+60h+lpData], rsi
0x18002c0bc  mov     rcx, [rcx+10h]
0x18002c0c0  call    WPP_SF_sSD
0x18002c0c5  jmp     loc_18002C48E
0x18002c0ca  mov     rcx, [rbp+hKey]; hKey
0x18002c0ce  lea     rax, [rbp+cbData]
0x18002c0d2  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002c0d7  lea     r12, aIdentityencodi; "IdentityEncodingFormat"
0x18002c0de  mov     rdx, r12; lpValueName
0x18002c0e1  mov     [rsp+60h+lpData], r15; lpData
0x18002c0e6  lea     r9, [rbp+Type]; lpType
0x18002c0ea  mov     dword ptr [rbp+cbData], r15d
0x18002c0ee  xor     r8d, r8d; lpReserved
0x18002c0f1  mov     dword ptr [rbp+Type], r15d
0x18002c0f5  call    cs:__imp_RegQueryValueExW
0x18002c0fb  mov     ebx, eax
0x18002c0fd  test    eax, eax
0x18002c0ff  jz      short loc_18002C180
0x18002c101  cmp     eax, 2
0x18002c104  jz      loc_18002C48E
0x18002c10a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c111  lea     rax, WPP_GLOBAL_Control
0x18002c118  cmp     rcx, rax
0x18002c11b  jz      loc_18002C48E
0x18002c121  cmp     byte ptr [rcx+19h], 2
0x18002c125  jb      loc_18002C48E
0x18002c12b  test    [rcx+1Ch], r14b
0x18002c12f  jz      loc_18002C48E
0x18002c135  mov     r9d, ebx
0x18002c138  lea     rcx, aRegqueryvaluee; "RegQueryValueEx(%S\\%S) failed with 0x%"...
0x18002c13f  mov     r8, r12
0x18002c142  mov     rdx, rsi
0x18002c145  call    WppDbgPrint
0x18002c14a  mov     edx, 23h ; '#'
0x18002c14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c156  lea     r9, aNapbase; "NAPBASE"
0x18002c15d  mov     dword ptr [rsp+60h+var_30], ebx; char
0x18002c161  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002c168  mov     [rsp+60h+lpcbData], r12; __int64
0x18002c16d  mov     [rsp+60h+lpData], rsi; __int64
0x18002c172  mov     rcx, [rcx+10h]; LoggerHandle
0x18002c176  call    WPP_SF_sSSD
0x18002c17b  jmp     loc_18002C48E
0x18002c180  mov     ecx, dword ptr [rbp+cbData]; Size
0x18002c183  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002c188  mov     rdi, rax
0x18002c18b  test    rax, rax
0x18002c18e  jnz     short loc_18002C1E6
0x18002c190  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c197  lea     rax, WPP_GLOBAL_Control
0x18002c19e  cmp     rcx, rax
0x18002c1a1  jz      short loc_18002C1DC
0x18002c1a3  cmp     byte ptr [rcx+19h], 2
0x18002c1a7  jb      short loc_18002C1DC
0x18002c1a9  test    [rcx+1Ch], r14b
0x18002c1ad  jz      short loc_18002C1DC
0x18002c1af  lea     rcx, aNotEnoughMemor_2; "Not enough memory to allocate registry "...
0x18002c1b6  call    WppDbgPrint
0x18002c1bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c1c2  lea     edx, [rdi+24h]
0x18002c1c5  lea     r9, aNapbase; "NAPBASE"
0x18002c1cc  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002c1d3  mov     rcx, [rcx+10h]
0x18002c1d7  call    WPP_SF_s
0x18002c1dc  mov     ebx, 0Eh
0x18002c1e1  jmp     loc_18002C48E
0x18002c1e6  mov     r8d, dword ptr [rbp+cbData]; Size
0x18002c1ea  xor     edx, edx; Val
0x18002c1ec  mov     rcx, rdi; void *
0x18002c1ef  call    memset_0
0x18002c1f4  mov     rcx, [rbp+hKey]; hKey
0x18002c1f8  lea     rax, [rbp+cbData]
0x18002c1fc  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18002c201  lea     r9, [rbp+Type]; lpType
0x18002c205  xor     r8d, r8d; lpReserved
0x18002c208  mov     [rsp+60h+lpData], rdi; lpData
0x18002c20d  mov     rdx, r12; lpValueName
0x18002c210  call    cs:__imp_RegQueryValueExW
0x18002c216  mov     ebx, eax
0x18002c218  test    eax, eax
0x18002c21a  jz      short loc_18002C26F
0x18002c21c  cmp     eax, 2
0x18002c21f  jz      loc_18002C48E
0x18002c225  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c22c  lea     rax, WPP_GLOBAL_Control
0x18002c233  cmp     rcx, rax
0x18002c236  jz      loc_18002C48E
0x18002c23c  cmp     byte ptr [rcx+19h], 2
0x18002c240  jb      loc_18002C48E
0x18002c246  test    [rcx+1Ch], r14b
0x18002c24a  jz      loc_18002C48E
0x18002c250  mov     r9d, ebx
0x18002c253  lea     rcx, aRegqueryvaluee; "RegQueryValueEx(%S\\%S) failed with 0x%"...
0x18002c25a  mov     r8, r12
0x18002c25d  mov     rdx, rsi
0x18002c260  call    WppDbgPrint
0x18002c265  mov     edx, 25h ; '%'
0x18002c26a  jmp     loc_18002C14F
0x18002c26f  call    GetRegistryValueType
0x18002c274  cmp     dword ptr [rbp+Type], eax
0x18002c277  jz      short loc_18002C2EA
0x18002c279  mov     ebx, 57h ; 'W'
0x18002c27e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c285  lea     rax, WPP_GLOBAL_Control
0x18002c28c  cmp     rcx, rax
0x18002c28f  jz      loc_18002C48E
0x18002c295  cmp     byte ptr [rcx+19h], 2
0x18002c299  jb      loc_18002C48E
0x18002c29f  test    [rcx+1Ch], r14b
0x18002c2a3  jz      loc_18002C48E
0x18002c2a9  lea     rsi, String1; "REG_DWORD"
0x18002c2b0  mov     rdx, rsi
0x18002c2b3  lea     rcx, aMismatchedRegi; "Mismatched registry value type %S"
0x18002c2ba  call    WppDbgPrint
0x18002c2bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c2c6  lea     edx, [rbx-31h]
0x18002c2c9  lea     r9, aNapbase; "NAPBASE"
0x18002c2d0  mov     [rsp+60h+lpData], rsi
0x18002c2d5  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002c2dc  mov     rcx, [rcx+10h]
0x18002c2e0  call    WPP_SF_sS
0x18002c2e5  jmp     loc_18002C48E
0x18002c2ea  mov     rsi, [rbp+pvarg]
0x18002c2ee  mov     rcx, rsi; pvarg
0x18002c2f1  call    cs:__imp_VariantInit
0x18002c2f7  mov     edx, dword ptr [rbp+Type]
0x18002c2fa  mov     eax, edx
0x18002c2fc  sub     eax, r14d
0x18002c2ff  jz      loc_18002C47C
0x18002c305  mov     ecx, 3
0x18002c30a  sub     eax, ecx
0x18002c30c  jz      loc_18002C472
0x18002c312  cmp     eax, ecx
0x18002c314  jz      short loc_18002C37C
0x18002c316  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c31d  lea     rax, WPP_GLOBAL_Control
0x18002c324  cmp     rcx, rax
0x18002c327  jz      loc_18002C48E
0x18002c32d  cmp     byte ptr [rcx+19h], 2
0x18002c331  jb      loc_18002C48E
0x18002c337  test    [rcx+1Ch], r14b
0x18002c33b  jz      loc_18002C48E
0x18002c341  lea     rcx, aUnexpectedRegT; "Unexpected reg type %d"
0x18002c348  call    WppDbgPrint
0x18002c34d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c354  lea     r9, aNapbase; "NAPBASE"
0x18002c35b  mov     eax, dword ptr [rbp+Type]
0x18002c35e  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002c365  mov     edx, 27h ; '''
0x18002c36a  mov     dword ptr [rsp+60h+lpData], eax
0x18002c36e  mov     rcx, [rcx+10h]
0x18002c372  call    WPP_SF_sd
0x18002c377  jmp     loc_18002C48E
0x18002c37c  mov     word ptr [rsi], 8
0x18002c381  mov     r14, rdi
0x18002c384  mov     [rbp+arg_8], r15
0x18002c388  cmp     [rdi], r15w
0x18002c38c  jz      loc_18002C45A
0x18002c392  lea     rdx, asc_18003AC1C; "\""
0x18002c399  lea     rcx, [rbp+var_20]; this
0x18002c39d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002c3a2  lea     rdx, [rbp+var_20]; struct _bstr_t *
0x18002c3a6  lea     rcx, [rbp+arg_8]; struct _bstr_t *
0x18002c3aa  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18002c3af  lea     rcx, [rbp+var_20]; this
0x18002c3b3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002c3b8  mov     rdx, r14; unsigned __int16 *
0x18002c3bb  lea     rcx, [rbp+var_18]; this
0x18002c3bf  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002c3c4  lea     rdx, [rbp+var_18]; struct _bstr_t *
0x18002c3c8  lea     rcx, [rbp+arg_8]; struct _bstr_t *
0x18002c3cc  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18002c3d1  lea     rcx, [rbp+var_18]; this
0x18002c3d5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002c3da  lea     rdx, asc_18003AC1C; "\""
0x18002c3e1  lea     rcx, [rbp+var_10]; this
0x18002c3e5  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002c3ea  lea     rdx, [rbp+var_10]; struct _bstr_t *
0x18002c3ee  lea     rcx, [rbp+arg_8]; struct _bstr_t *
0x18002c3f2  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18002c3f7  lea     rcx, [rbp+var_10]; this
0x18002c3fb  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002c400  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c404  inc     rax
0x18002c407  cmp     [r14+rax*2], r15w
0x18002c40c  jnz     short loc_18002C404
0x18002c40e  lea     r14, [r14+rax*2]
0x18002c412  add     r14, 2
0x18002c416  cmp     [r14], r15w
0x18002c41a  jz      short loc_18002C44C
0x18002c41c  lea     rdx, asc_18003AC20; ","
0x18002c423  lea     rcx, [rbp+var_8]; this
0x18002c427  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18002c42c  lea     rdx, [rbp+var_8]; struct _bstr_t *
0x18002c430  lea     rcx, [rbp+arg_8]; struct _bstr_t *
0x18002c434  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x18002c439  lea     rcx, [rbp+var_8]; this
0x18002c43d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002c442  cmp     [r14], r15w
0x18002c446  jnz     loc_18002C392
0x18002c44c  mov     rax, [rbp+arg_8]
0x18002c450  test    rax, rax
0x18002c453  jz      short loc_18002C45A
0x18002c455  mov     rcx, [rax]
0x18002c458  jmp     short loc_18002C45D
0x18002c45a  mov     rcx, r15; psz
0x18002c45d  call    cs:__imp_SysAllocString
0x18002c463  lea     rcx, [rbp+arg_8]; this
0x18002c467  mov     [rsi+8], rax
0x18002c46b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002c470  jmp     short loc_18002C48E
0x18002c472  mov     [rsi], cx
0x18002c475  mov     eax, [rdi]
0x18002c477  mov     [rsi+8], eax
0x18002c47a  jmp     short loc_18002C48E
0x18002c47c  mov     rcx, rdi; psz
0x18002c47f  mov     word ptr [rsi], 8
0x18002c484  call    cs:__imp_SysAllocString
0x18002c48a  mov     [rsi+8], rax
0x18002c48e  mov     rcx, [rbp+hKey]; hKey
0x18002c492  test    rcx, rcx
0x18002c495  jz      short loc_18002C49D
0x18002c497  call    cs:__imp_RegCloseKey
0x18002c49d  test    rdi, rdi
0x18002c4a0  jz      short loc_18002C4AB
0x18002c4a2  mov     rcx, rdi; Block
0x18002c4a5  call    cs:__imp_free
0x18002c4ab  mov     eax, ebx
0x18002c4ad  add     rsp, 60h
0x18002c4b1  pop     r15
0x18002c4b3  pop     r14
0x18002c4b5  pop     r12
0x18002c4b7  pop     rdi
0x18002c4b8  pop     rsi
0x18002c4b9  pop     rbx
0x18002c4ba  pop     rbp
0x18002c4bb  retn
```
