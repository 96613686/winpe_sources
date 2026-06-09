# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180005a90`
- end: `0x180006069`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000576c`
- `0x180005a90`

## callees

- `0x180003aec`
- `0x180004184`
- `0x1800041f4`
- `0x18000434c`
- `0x180004464`
- `0x180004d4c`
- `0x180004e88`
- `0x180005004`
- `0x18000517c`
- `0x180005658`
- `0x180005a90`
- `0x1800064f0`
- `0x1800065c0`
- `0x180031680`
- `0x180031740`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180005e96`
- `msvcrt!wcsncpy_s` at `0x180005e96`
- `ADVAPI32!RegCreateKeyExW` at `0x180005d97`
- `ADVAPI32!RegCreateKeyExW` at `0x180005d97`
- `ADVAPI32!RegDeleteValueW` at `0x180005ce5`
- `ADVAPI32!RegDeleteValueW` at `0x180005ce5`
- `KERNEL32!lstrcmpiW` at `0x180005b0b`
- `KERNEL32!lstrcmpiW` at `0x180005b1e`
- `KERNEL32!lstrcmpiW` at `0x180005bf2`
- `KERNEL32!lstrcmpiW` at `0x180005c21`
- `KERNEL32!lstrcmpiW` at `0x180005b0b`
- `KERNEL32!lstrcmpiW` at `0x180005b1e`
- `KERNEL32!lstrcmpiW` at `0x180005bf2`
- `KERNEL32!lstrcmpiW` at `0x180005c21`

## string_xrefs

- `0x180005b14`: `ForceRemove`
- `0x180005be8`: `NoRemove`
- `0x180005b01`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  errno_t v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v28 = 0;
          v29 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey(&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey(v30, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v28 = 0;
    v29 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005a90  push    rbp
0x180005a92  push    rbx
0x180005a93  push    rsi
0x180005a94  push    rdi
0x180005a95  push    r12
0x180005a97  push    r13
0x180005a99  push    r14
0x180005a9b  push    r15
0x180005a9d  lea     rbp, [rsp-21C8h]
0x180005aa5  mov     eax, 22C8h
0x180005aaa  call    _alloca_probe
0x180005aaf  sub     rsp, rax
0x180005ab2  mov     rax, cs:__security_cookie
0x180005ab9  xor     rax, rsp
0x180005abc  mov     [rbp+2200h+var_50], rax
0x180005ac3  mov     r15d, r9d
0x180005ac6  mov     [rsp+2300h+var_22B0], r9d
0x180005acb  mov     r13, r8
0x180005ace  mov     rdi, rdx
0x180005ad1  mov     rsi, rcx
0x180005ad4  xor     r14d, r14d
0x180005ad7  mov     [rsp+2300h+var_2290], r14
0x180005adc  mov     [rsp+2300h+var_2288], r14
0x180005ae1  mov     [rbp+2200h+var_2280], r14
0x180005ae5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005aea  test    eax, eax
0x180005aec  mov     ebx, eax
0x180005aee  js      loc_18000601D
0x180005af4  xor     r12d, r12d
0x180005af7  cmp     word ptr [rdi], 7Dh ; '}'
0x180005afb  jz      loc_18000601D
0x180005b01  lea     rdx, String2; "Delete"
0x180005b08  mov     rcx, rdi; lpString1
0x180005b0b  call    cs:__imp_lstrcmpiW
0x180005b11  mov     r14d, eax
0x180005b14  lea     rdx, aForceremove; "ForceRemove"
0x180005b1b  mov     rcx, rdi; lpString1
0x180005b1e  call    cs:__imp_lstrcmpiW
0x180005b24  test    eax, eax
0x180005b26  jz      short loc_180005B31
0x180005b28  test    r14d, r14d
0x180005b2b  jnz     loc_180005BE2
0x180005b31  mov     rdx, rdi; unsigned __int16 *
0x180005b34  mov     rcx, rsi; this
0x180005b37  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005b3c  mov     ebx, eax
0x180005b3e  test    eax, eax
0x180005b40  js      loc_18000601D
0x180005b46  test    r15d, r15d
0x180005b49  jz      loc_180005BE2
0x180005b4f  mov     [rsp+2300h+hKey], r12
0x180005b54  mov     [rsp+2300h+var_22A0], r12
0x180005b59  mov     [rsp+2300h+var_2298], r12
0x180005b5e  mov     edx, 5Ch ; '\'; unsigned __int16
0x180005b63  mov     rcx, rdi; lpsz
0x180005b66  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180005b6b  test    rax, rax
0x180005b6e  jnz     loc_18000600E
0x180005b74  mov     rdx, rdi; unsigned __int16 *
0x180005b77  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180005b7c  test    eax, eax
0x180005b7e  jz      short loc_180005B97
0x180005b80  mov     [rsp+2300h+hKey], r13
0x180005b85  mov     rdx, rdi; unsigned __int16 *
0x180005b88  lea     rcx, [rsp+2300h+hKey]; this
0x180005b8d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180005b92  mov     [rsp+2300h+hKey], r12
0x180005b97  test    r14d, r14d
0x180005b9a  jnz     short loc_180005BD8
0x180005b9c  mov     rdx, rdi; unsigned __int16 *
0x180005b9f  mov     rcx, rsi; this
0x180005ba2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005ba7  mov     ebx, eax
0x180005ba9  xor     r14d, r14d
0x180005bac  test    eax, eax
0x180005bae  js      loc_180006055
0x180005bb4  mov     rdx, rdi; unsigned __int16 *
0x180005bb7  mov     rcx, rsi; this
0x180005bba  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005bbf  mov     ebx, eax
0x180005bc1  test    eax, eax
0x180005bc3  lea     rcx, [rsp+2300h+hKey]; this
0x180005bc8  js      loc_18000605A
0x180005bce  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005bd3  jmp     loc_180005DFC
0x180005bd8  lea     rcx, [rsp+2300h+hKey]; this
0x180005bdd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005be2  mov     r12d, 1
0x180005be8  lea     rdx, aNoremove; "NoRemove"
0x180005bef  mov     rcx, rdi; lpString1
0x180005bf2  call    cs:__imp_lstrcmpiW
0x180005bf8  xor     r14d, r14d
0x180005bfb  test    eax, eax
0x180005bfd  jnz     short loc_180005C17
0x180005bff  mov     r12d, r14d
0x180005c02  mov     rdx, rdi; unsigned __int16 *
0x180005c05  mov     rcx, rsi; this
0x180005c08  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005c0d  mov     ebx, eax
0x180005c0f  test    eax, eax
0x180005c11  js      loc_18000601D
0x180005c17  lea     rdx, aVal; "Val"
0x180005c1e  mov     rcx, rdi; lpString1
0x180005c21  call    cs:__imp_lstrcmpiW
0x180005c27  test    eax, eax
0x180005c29  jnz     loc_180005D10
0x180005c2f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180005c36  mov     rcx, rsi; this
0x180005c39  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005c3e  mov     ebx, eax
0x180005c40  test    eax, eax
0x180005c42  js      loc_18000601D
0x180005c48  mov     rdx, rdi; unsigned __int16 *
0x180005c4b  mov     rcx, rsi; this
0x180005c4e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005c53  mov     ebx, eax
0x180005c55  test    eax, eax
0x180005c57  js      loc_18000601D
0x180005c5d  cmp     word ptr [rdi], 3Dh ; '='
0x180005c61  jnz     loc_180006018
0x180005c67  test    r15d, r15d
0x180005c6a  jz      short loc_180005C9E
0x180005c6c  mov     [rsp+2300h+var_22A0], r14
0x180005c71  mov     [rsp+2300h+var_2298], r14
0x180005c76  mov     [rsp+2300h+hKey], r13
0x180005c7b  mov     r9, rdi; unsigned __int16 *
0x180005c7e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180005c85  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180005c8a  mov     rcx, rsi; this
0x180005c8d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005c92  mov     ebx, eax
0x180005c94  mov     [rsp+2300h+hKey], r14
0x180005c99  jmp     loc_180005BC1
0x180005c9e  cmp     [rbp+2200h+arg_20], r14d
0x180005ca5  jnz     short loc_180005D00
0x180005ca7  test    r12d, r12d
0x180005caa  jz      short loc_180005D00
0x180005cac  mov     [rsp+2300h+hKey], r14
0x180005cb1  mov     [rsp+2300h+var_22A0], r14
0x180005cb6  mov     [rsp+2300h+var_2298], r14
0x180005cbb  mov     r9d, 20006h; unsigned int
0x180005cc1  xor     r8d, r8d; lpSubKey
0x180005cc4  mov     rdx, r13; hKey
0x180005cc7  lea     rcx, [rsp+2300h+hKey]; this
0x180005ccc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005cd1  test    eax, eax
0x180005cd3  jnz     loc_18000604C
0x180005cd9  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180005ce0  mov     rcx, [rsp+2300h+hKey]; hKey
0x180005ce5  call    cs:__imp_RegDeleteValueW
0x180005ceb  test    eax, 0FFFFFFFDh
0x180005cf0  jnz     loc_18000604C
0x180005cf6  lea     rcx, [rsp+2300h+hKey]; this
0x180005cfb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005d00  mov     rdx, rdi; unsigned __int16 *
0x180005d03  mov     rcx, rsi; this
0x180005d06  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005d0b  jmp     loc_180005AEA
0x180005d10  mov     edx, 5Ch ; '\'; unsigned __int16
0x180005d15  mov     rcx, rdi; lpsz
0x180005d18  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180005d1d  test    rax, rax
0x180005d20  jnz     loc_180006018
0x180005d26  test    r15d, r15d
0x180005d29  jz      loc_180005E4B
0x180005d2f  mov     ebx, 2001Fh
0x180005d34  mov     r9d, ebx; unsigned int
0x180005d37  mov     r8, rdi; lpSubKey
0x180005d3a  mov     rdx, r13; hKey
0x180005d3d  lea     rcx, [rsp+2300h+var_2290]; this
0x180005d42  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005d47  test    eax, eax
0x180005d49  jz      short loc_180005DC4
0x180005d4b  lea     r9d, [rbx-6]; unsigned int
0x180005d4f  mov     r8, rdi; lpSubKey
0x180005d52  mov     rdx, r13; hKey
0x180005d55  lea     rcx, [rsp+2300h+var_2290]; this
0x180005d5a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005d5f  test    eax, eax
0x180005d61  jz      short loc_180005DC4
0x180005d63  mov     [rbp+2200h+dwDisposition], r14d
0x180005d67  mov     [rbp+2200h+var_2270], r14
0x180005d6b  lea     rax, [rbp+2200h+dwDisposition]
0x180005d6f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180005d74  lea     rax, [rbp+2200h+var_2270]
0x180005d78  mov     [rsp+2300h+phkResult], rax; phkResult
0x180005d7d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180005d82  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180005d86  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x180005d8b  xor     r9d, r9d; lpClass
0x180005d8e  xor     r8d, r8d; Reserved
0x180005d91  mov     rdx, rdi; lpSubKey
0x180005d94  mov     rcx, r13; hKey
0x180005d97  call    cs:__imp_RegCreateKeyExW
0x180005d9d  mov     ecx, eax
0x180005d9f  test    eax, eax
0x180005da1  jnz     loc_180005F4B
0x180005da7  lea     rcx, [rsp+2300h+var_2290]; this
0x180005dac  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005db1  mov     ecx, eax
0x180005db3  mov     rax, [rbp+2200h+var_2270]
0x180005db7  mov     [rsp+2300h+var_2290], rax
0x180005dbc  test    ecx, ecx
0x180005dbe  jnz     loc_180005F4B
0x180005dc4  mov     rdx, rdi; unsigned __int16 *
0x180005dc7  mov     rcx, rsi; this
0x180005dca  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005dcf  mov     ebx, eax
0x180005dd1  test    eax, eax
0x180005dd3  js      loc_18000601D
0x180005dd9  cmp     word ptr [rdi], 3Dh ; '='
0x180005ddd  jnz     short loc_180005DFC
0x180005ddf  mov     r9, rdi; unsigned __int16 *
0x180005de2  xor     r8d, r8d; unsigned __int16 *
0x180005de5  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180005dea  mov     rcx, rsi; this
0x180005ded  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005df2  mov     ebx, eax
0x180005df4  test    eax, eax
0x180005df6  js      loc_18000601D
0x180005dfc  cmp     word ptr [rdi], 7Bh ; '{'
0x180005e00  jnz     loc_180005AF4
0x180005e06  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005e0a  inc     rax
0x180005e0d  cmp     [rdi+rax*2], r14w
0x180005e12  jnz     short loc_180005E0A
0x180005e14  cmp     rax, 1
0x180005e18  jnz     loc_180005AF4
0x180005e1e  mov     [rsp+2300h+dwOptions], r14d; int
0x180005e23  mov     r9d, r15d; int
0x180005e26  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180005e2b  mov     rdx, rdi; unsigned __int16 *
0x180005e2e  mov     rcx, rsi; this
0x180005e31  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005e36  mov     ebx, eax
0x180005e38  test    eax, eax
0x180005e3a  js      loc_18000601D
0x180005e40  mov     rdx, rdi
0x180005e43  mov     rcx, rsi
0x180005e46  jmp     loc_180005AE5
0x180005e4b  cmp     [rbp+2200h+arg_20], r14d
0x180005e52  jnz     short loc_180005E6F
0x180005e54  mov     r9d, 20019h; unsigned int
0x180005e5a  mov     r8, rdi; lpSubKey
0x180005e5d  mov     rdx, r13; hKey
0x180005e60  lea     rcx, [rsp+2300h+var_2290]; this
0x180005e65  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005e6a  mov     r14d, eax
0x180005e6d  jmp     short loc_180005E75
0x180005e6f  mov     r14d, 2
0x180005e75  mov     r15d, 1
0x180005e7b  test    r14d, r14d
0x180005e7e  cmovz   r15d, [rbp+2200h+arg_20]
0x180005e86  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180005e8a  mov     r8, rdi; Source
0x180005e8d  mov     edx, 104h; SizeInWords
0x180005e92  lea     rcx, [rbp+2200h+Destination]; Destination
0x180005e96  call    cs:__imp_wcsncpy_s
0x180005e9c  mov     ecx, eax; int
0x180005e9e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005ea3  mov     rdx, rdi; unsigned __int16 *
0x180005ea6  mov     rcx, rsi; this
0x180005ea9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005eae  mov     ebx, eax
0x180005eb0  test    eax, eax
0x180005eb2  js      loc_18000601D
0x180005eb8  mov     rdx, rdi; unsigned __int16 *
0x180005ebb  mov     rcx, rsi; this
0x180005ebe  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005ec3  mov     ebx, eax
0x180005ec5  xor     ecx, ecx
0x180005ec7  test    eax, eax
0x180005ec9  js      loc_18000601D
0x180005ecf  cmp     word ptr [rdi], 7Bh ; '{'
0x180005ed3  jnz     short loc_180005F24
0x180005ed5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005ed9  inc     rax
0x180005edc  cmp     [rdi+rax*2], cx
0x180005ee0  jnz     short loc_180005ED9
0x180005ee2  cmp     rax, 1
0x180005ee6  jnz     short loc_180005F24
0x180005ee8  mov     [rsp+2300h+dwOptions], r15d; int
0x180005eed  xor     r9d, r9d; int
0x180005ef0  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180005ef5  mov     rdx, rdi; unsigned __int16 *
0x180005ef8  mov     rcx, rsi; this
0x180005efb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005f00  mov     ebx, eax
0x180005f02  test    eax, eax
0x180005f04  jns     short loc_180005F0F
0x180005f06  test    r15d, r15d
0x180005f09  jz      loc_18000601D
0x180005f0f  mov     rdx, rdi; unsigned __int16 *
0x180005f12  mov     rcx, rsi; this
0x180005f15  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005f1a  mov     ebx, eax
0x180005f1c  test    eax, eax
0x180005f1e  js      loc_18000601D
0x180005f24  cmp     r14d, 2
0x180005f28  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
