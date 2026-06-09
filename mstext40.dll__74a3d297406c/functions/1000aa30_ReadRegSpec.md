# ReadRegSpec

- ea: `0x1000aa30`
- end: `0x1000ad45`
- name: `ReadRegSpec`
- size: `789`
- prototype: `int __stdcall(STRSAFE_LPCWSTR pszSrc, int, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x10009fc0`

## callees

- `0x10009010`
- `0x1000aa30`
- `0x1000ad60`
- `0x1000ae20`
- `0x1002b080`
- `0x1002b140`
- `0x1002b81a`
- `0x1002c253`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1000ad0e`
- `ADVAPI32!RegCloseKey` at `0x1000ad34`
- `ADVAPI32!RegCloseKey` at `0x1000ad0e`
- `ADVAPI32!RegCloseKey` at `0x1000ad34`

## pseudocode

```c
int __stdcall ReadRegSpec(STRSAFE_LPCWSTR pszSrc, int a2, char *a3, int **a4)
{
  int v4; // edi
  wchar_t *v5; // ecx
  int v6; // edx
  wchar_t v7; // ax
  int *v8; // esi
  DWORD cbData; // [esp+Ch] [ebp-91Ch] BYREF
  BYTE v11; // [esp+13h] [ebp-915h] BYREF
  DWORD Type; // [esp+14h] [ebp-914h] BYREF
  HKEY hKey; // [esp+18h] [ebp-910h] BYREF
  BYTE Data[4]; // [esp+1Ch] [ebp-90Ch] BYREF
  wchar_t pszDest[128]; // [esp+20h] [ebp-908h] BYREF
  wchar_t v16[1026]; // [esp+120h] [ebp-808h] BYREF

  v4 = a2;
  cbData = 128;
  if ( !*(_WORD *)a3 )
    return 0;
  v5 = pszDest;
  v6 = 128;
  while ( v6 != -2147483518 )
  {
    v7 = *(wchar_t *)((char *)v5 + a3 - (char *)pszDest);
    if ( !v7 )
      break;
    *v5++ = v7;
    if ( !--v6 )
    {
      --v5;
      break;
    }
  }
  *v5 = 0;
  StringCchCatW(pszDest, 0x80u, L"\\Engines\\");
  StringCchCatW(pszDest, 0x80u, pszSrc);
  if ( !a2 )
    v4 = -2147483646;
  if ( JetRegOpenKeyW((HKEY)v4, pszDest, &hKey) )
    return 0;
  v8 = *a4;
  if ( !*a4 )
  {
LABEL_39:
    RegCloseKey(hKey);
    return 0;
  }
  while ( 2 )
  {
    switch ( *((_BYTE *)v8 + 4) )
    {
      case 0:
        cbData = 1025;
        if ( JetRegQueryValueExW(hKey, (LPCWSTR)v8[2], 0, &Type, (LPBYTE)v16, &cbData) || (int)cbData <= 0 || Type != 1 )
          goto LABEL_38;
        if ( 2 * cbData >= 0x804 )
          goto LABEL_42;
        v16[cbData] = 0;
        StringCchCopyW((STRSAFE_LPWSTR)v8[3], v8[4], v16);
        goto LABEL_38;
      case 1:
        cbData = 4;
        if ( !JetRegQueryValueExW(hKey, (LPCWSTR)v8[2], 0, &Type, Data, &cbData) && (int)cbData > 0 && Type == 4 )
          *(_DWORD *)v8[3] = *(_DWORD *)Data;
        goto LABEL_38;
      case 2:
        cbData = 1;
        if ( !JetRegQueryValueExW(hKey, (LPCWSTR)v8[2], 0, &Type, &v11, &cbData) && (int)cbData > 0 && Type == 3 )
          *(_DWORD *)v8[3] = v11 != 0;
        goto LABEL_38;
      case 3:
        cbData = 2052;
        if ( JetRegQueryValueExW(hKey, (LPCWSTR)v8[2], 0, &Type, (LPBYTE)v16, &cbData) || (int)cbData <= 0 || Type != 1 )
          goto LABEL_38;
        if ( 2 * cbData >= 0x804 )
LABEL_42:
          __report_rangecheckfailure();
        v16[cbData] = 0;
        if ( v8[5] && !ascii_wcsicmp(v16, v8[5]) )
        {
          *(_DWORD *)v8[3] = 0;
LABEL_38:
          v8 = (int *)*v8;
          if ( !v8 )
            goto LABEL_39;
          continue;
        }
        if ( v8[6] && !ascii_wcsicmp(v16, v8[6]) )
        {
          *(_DWORD *)v8[3] = 1;
          goto LABEL_38;
        }
        if ( v8[7] && !ascii_wcsicmp(v16, v8[7]) )
        {
          *(_DWORD *)v8[3] = 2;
          goto LABEL_38;
        }
        RegCloseKey(hKey);
        return *((unsigned __int8 *)v8 + 5);
      default:
        goto LABEL_38;
    }
  }
}

```

## disassembly

```asm
0x1000aa30  sub     esp, 91Ch
0x1000aa36  mov     eax, ___security_cookie
0x1000aa3b  xor     eax, esp
0x1000aa3d  mov     [esp+91Ch+var_4], eax
0x1000aa44  push    ebx
0x1000aa45  mov     ebx, [esp+920h+arg_C]
0x1000aa4c  push    esi
0x1000aa4d  mov     esi, [esp+924h+arg_8]
0x1000aa54  push    edi
0x1000aa55  mov     edi, [esp+928h+arg_4]
0x1000aa5c  mov     [esp+928h+cbData], 80h
0x1000aa64  cmp     word ptr [esi], 0
0x1000aa68  jz      loc_1000AD14
0x1000aa6e  lea     ecx, [esp+928h+pszDest]
0x1000aa72  mov     edx, 80h
0x1000aa77  mov     eax, ecx
0x1000aa79  sub     esi, eax
0x1000aa7b  jmp     short loc_1000AA80
0x1000aa80  lea     eax, [edx+7FFFFF7Eh]
0x1000aa86  test    eax, eax
0x1000aa88  jz      short loc_1000AA9E
0x1000aa8a  movzx   eax, word ptr [esi+ecx]
0x1000aa8e  test    ax, ax
0x1000aa91  jz      short loc_1000AA9E
0x1000aa93  mov     [ecx], ax
0x1000aa96  add     ecx, 2
0x1000aa99  dec     edx
0x1000aa9a  jnz     short loc_1000AA80
0x1000aa9c  jmp     short loc_1000AAA2
0x1000aa9e  test    edx, edx
0x1000aaa0  jnz     short loc_1000AAA5
0x1000aaa2  sub     ecx, 2
0x1000aaa5  xor     eax, eax
0x1000aaa7  push    offset aEngines; "\\Engines\\"
0x1000aaac  mov     [ecx], ax
0x1000aaaf  lea     eax, [esp+92Ch+pszDest]
0x1000aab3  push    80h; cchDest
0x1000aab8  push    eax; pszDest
0x1000aab9  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000aabe  push    [esp+928h+pszSrc]; pszSrc
0x1000aac5  lea     eax, [esp+92Ch+pszDest]
0x1000aac9  push    80h; cchDest
0x1000aace  push    eax; pszDest
0x1000aacf  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000aad4  mov     eax, 80000002h
0x1000aad9  test    edi, edi
0x1000aadb  cmovz   edi, eax
0x1000aade  lea     eax, [esp+928h+hKey]
0x1000aae2  push    eax; phkResult
0x1000aae3  lea     eax, [esp+92Ch+pszDest]
0x1000aae7  push    eax; lpSubKey
0x1000aae8  push    edi; hKey
0x1000aae9  call    _JetRegOpenKeyW@12; JetRegOpenKeyW(x,x,x)
0x1000aaee  test    eax, eax
0x1000aaf0  jnz     loc_1000AD14
0x1000aaf6  mov     esi, [ebx]
0x1000aaf8  test    esi, esi
0x1000aafa  jz      loc_1000AD0A
0x1000ab00  movzx   eax, byte ptr [esi+4]
0x1000ab04  cmp     eax, 3; switch 4 cases
0x1000ab07  ja      def_1000AB0D; jumptable 1000AB0D default case
0x1000ab0d  jmp     ds:jpt_1000AB0D[eax*4]; switch jump
0x1000ab14  lea     eax, [esp+928h+cbData]; jumptable 1000AB0D case 0
0x1000ab18  mov     [esp+928h+cbData], 401h
0x1000ab20  push    eax; lpcbData
0x1000ab21  lea     eax, [esp+92Ch+var_808]
0x1000ab28  push    eax; lpData
0x1000ab29  lea     eax, [esp+930h+Type]
0x1000ab2d  push    eax; lpType
0x1000ab2e  push    0; lpReserved
0x1000ab30  push    dword ptr [esi+8]; lpValueName
0x1000ab33  push    [esp+93Ch+hKey]; hKey
0x1000ab37  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x1000ab3c  test    eax, eax
0x1000ab3e  jnz     def_1000AB0D; jumptable 1000AB0D default case
0x1000ab44  mov     eax, [esp+928h+cbData]
0x1000ab48  test    eax, eax
0x1000ab4a  jle     def_1000AB0D; jumptable 1000AB0D default case
0x1000ab50  cmp     [esp+928h+Type], 1
0x1000ab55  jnz     def_1000AB0D; jumptable 1000AB0D default case
0x1000ab5b  add     eax, eax
0x1000ab5d  cmp     eax, 804h
0x1000ab62  jnb     loc_1000AD40
0x1000ab68  xor     ecx, ecx
0x1000ab6a  mov     [esp+eax+928h+var_808], cx
0x1000ab72  lea     eax, [esp+928h+var_808]
0x1000ab79  push    eax; pszSrc
0x1000ab7a  push    dword ptr [esi+10h]; cchDest
0x1000ab7d  push    dword ptr [esi+0Ch]; pszDest
0x1000ab80  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1000ab85  jmp     def_1000AB0D; jumptable 1000AB0D default case
0x1000ab8a  lea     eax, [esp+928h+cbData]; jumptable 1000AB0D case 1
0x1000ab8e  mov     [esp+928h+cbData], 4
0x1000ab96  push    eax; lpcbData
0x1000ab97  lea     eax, [esp+92Ch+Data]
0x1000ab9b  push    eax; lpData
0x1000ab9c  lea     eax, [esp+930h+Type]
0x1000aba0  push    eax; lpType
0x1000aba1  push    0; lpReserved
0x1000aba3  push    dword ptr [esi+8]; lpValueName
0x1000aba6  push    [esp+93Ch+hKey]; hKey
0x1000abaa  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x1000abaf  test    eax, eax
0x1000abb1  jnz     def_1000AB0D; jumptable 1000AB0D default case
0x1000abb7  cmp     [esp+928h+cbData], eax
0x1000abbb  jle     def_1000AB0D; jumptable 1000AB0D default case
0x1000abc1  cmp     [esp+928h+Type], 4
0x1000abc6  jnz     def_1000AB0D; jumptable 1000AB0D default case
0x1000abcc  mov     ecx, [esi+0Ch]
0x1000abcf  mov     eax, dword ptr [esp+928h+Data]
0x1000abd3  mov     [ecx], eax
0x1000abd5  jmp     def_1000AB0D; jumptable 1000AB0D default case
0x1000abda  lea     eax, [esp+928h+cbData]; jumptable 1000AB0D case 2
0x1000abde  mov     [esp+928h+cbData], 1
0x1000abe6  push    eax; lpcbData
0x1000abe7  lea     eax, [esp+92Ch+var_915]
0x1000abeb  push    eax; lpData
0x1000abec  lea     eax, [esp+930h+Type]
0x1000abf0  push    eax; lpType
0x1000abf1  push    0; lpReserved
0x1000abf3  push    dword ptr [esi+8]; lpValueName
0x1000abf6  push    [esp+93Ch+hKey]; hKey
0x1000abfa  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x1000abff  test    eax, eax
0x1000ac01  jnz     def_1000AB0D; jumptable 1000AB0D default case
0x1000ac07  cmp     [esp+928h+cbData], eax
0x1000ac0b  jle     def_1000AB0D; jumptable 1000AB0D default case
0x1000ac11  cmp     [esp+928h+Type], 3
0x1000ac16  jnz     def_1000AB0D; jumptable 1000AB0D default case
0x1000ac1c  mov     eax, [esi+0Ch]
0x1000ac1f  xor     ecx, ecx
0x1000ac21  cmp     [esp+928h+var_915], cl
0x1000ac25  setnz   cl
0x1000ac28  mov     [eax], ecx
0x1000ac2a  jmp     def_1000AB0D; jumptable 1000AB0D default case
0x1000ac2f  lea     eax, [esp+928h+cbData]; jumptable 1000AB0D case 3
0x1000ac33  mov     [esp+928h+cbData], 804h
0x1000ac3b  push    eax; lpcbData
0x1000ac3c  lea     eax, [esp+92Ch+var_808]
0x1000ac43  push    eax; lpData
0x1000ac44  lea     eax, [esp+930h+Type]
0x1000ac48  push    eax; lpType
0x1000ac49  push    0; lpReserved
0x1000ac4b  push    dword ptr [esi+8]; lpValueName
0x1000ac4e  push    [esp+93Ch+hKey]; hKey
0x1000ac52  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x1000ac57  test    eax, eax
0x1000ac59  jnz     def_1000AB0D; jumptable 1000AB0D default case
0x1000ac5f  mov     eax, [esp+928h+cbData]
0x1000ac63  test    eax, eax
0x1000ac65  jle     def_1000AB0D; jumptable 1000AB0D default case
0x1000ac6b  cmp     [esp+928h+Type], 1
0x1000ac70  jnz     def_1000AB0D; jumptable 1000AB0D default case
0x1000ac76  add     eax, eax
0x1000ac78  cmp     eax, 804h
0x1000ac7d  jnb     loc_1000AD40
0x1000ac83  xor     ecx, ecx
0x1000ac85  mov     [esp+eax+928h+var_808], cx
0x1000ac8d  mov     eax, [esi+14h]
0x1000ac90  test    eax, eax
0x1000ac92  jz      short loc_1000ACB4
0x1000ac94  push    eax
0x1000ac95  lea     eax, [esp+92Ch+var_808]
0x1000ac9c  push    eax
0x1000ac9d  call    _ascii_wcsicmp
0x1000aca2  add     esp, 8
0x1000aca5  test    eax, eax
0x1000aca7  jnz     short loc_1000ACB4
0x1000aca9  mov     eax, [esi+0Ch]
0x1000acac  mov     dword ptr [eax], 0
0x1000acb2  jmp     short def_1000AB0D; jumptable 1000AB0D default case
0x1000acb4  mov     eax, [esi+18h]
0x1000acb7  test    eax, eax
0x1000acb9  jz      short loc_1000ACDB
0x1000acbb  push    eax
0x1000acbc  lea     eax, [esp+92Ch+var_808]
0x1000acc3  push    eax
0x1000acc4  call    _ascii_wcsicmp
0x1000acc9  add     esp, 8
0x1000accc  test    eax, eax
0x1000acce  jnz     short loc_1000ACDB
0x1000acd0  mov     eax, [esi+0Ch]
0x1000acd3  mov     dword ptr [eax], 1
0x1000acd9  jmp     short def_1000AB0D; jumptable 1000AB0D default case
0x1000acdb  mov     eax, [esi+1Ch]
0x1000acde  test    eax, eax
0x1000ace0  jz      short loc_1000AD30
0x1000ace2  push    eax
0x1000ace3  lea     eax, [esp+92Ch+var_808]
0x1000acea  push    eax
0x1000aceb  call    _ascii_wcsicmp
0x1000acf0  add     esp, 8
0x1000acf3  test    eax, eax
0x1000acf5  jnz     short loc_1000AD30
0x1000acf7  mov     eax, [esi+0Ch]
0x1000acfa  mov     dword ptr [eax], 2
0x1000ad00  mov     esi, [esi]; jumptable 1000AB0D default case
0x1000ad02  test    esi, esi
0x1000ad04  jnz     loc_1000AB00
0x1000ad0a  push    [esp+928h+hKey]; hKey
0x1000ad0e  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1000ad14  xor     eax, eax
0x1000ad16  mov     ecx, [esp+928h+var_4]
0x1000ad1d  pop     edi
0x1000ad1e  pop     esi
0x1000ad1f  pop     ebx
0x1000ad20  xor     ecx, esp; StackCookie
0x1000ad22  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000ad27  add     esp, 91Ch
0x1000ad2d  retn    10h
0x1000ad30  push    [esp+928h+hKey]; hKey
0x1000ad34  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x1000ad3a  movzx   eax, byte ptr [esi+5]
0x1000ad3e  jmp     short loc_1000AD16
0x1000ad40  call    ___report_rangecheckfailure
```
