# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x18000fea0`
- end: `0x180010479`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000fb7c`
- `0x18000fea0`

## callees

- `0x180002a90`
- `0x18000e89c`
- `0x18000eff4`
- `0x18000f064`
- `0x18000f09c`
- `0x18000f1b4`
- `0x18000f2dc`
- `0x18000f548`
- `0x18000f5e4`
- `0x18000f788`
- `0x18000fa68`
- `0x18000fea0`
- `0x1800104d4`
- `0x1800105a4`
- `0x180033d00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800102a6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800102a6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800100f5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800100f5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800101a7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800101a7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ff1b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ff2e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010002`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010031`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ff1b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ff2e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010002`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010031`

## string_xrefs

- `0x18000ff24`: `ForceRemove`
- `0x18000fff8`: `NoRemove`
- `0x18000ff11`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(ATL::CRegParser *this, wchar_t *a2, HKEY a3, int a4, int a5)
{
  int v5; // r15d
  wchar_t *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  HKEY v31[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v34[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v31, 0, sizeof(v31));
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
          v29 = 0;
          v30 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            v31[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v19);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v31[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v34);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v31[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v29 = 0;
              v30 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
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
      v29 = 0;
      v30 = 0;
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
    v29 = 0;
    v30 = 0;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000fea0  push    rbp
0x18000fea2  push    rbx
0x18000fea3  push    rsi
0x18000fea4  push    rdi
0x18000fea5  push    r12
0x18000fea7  push    r13
0x18000fea9  push    r14
0x18000feab  push    r15
0x18000fead  lea     rbp, [rsp-21C8h]
0x18000feb5  mov     eax, 22C8h
0x18000feba  call    _alloca_probe
0x18000febf  sub     rsp, rax
0x18000fec2  mov     rax, cs:__security_cookie
0x18000fec9  xor     rax, rsp
0x18000fecc  mov     [rbp+2200h+var_50], rax
0x18000fed3  mov     r15d, r9d
0x18000fed6  mov     [rsp+2300h+var_22B0], r9d
0x18000fedb  mov     r13, r8
0x18000fede  mov     rdi, rdx
0x18000fee1  mov     rsi, rcx
0x18000fee4  xor     r14d, r14d
0x18000fee7  mov     [rsp+2300h+var_2290], r14
0x18000feec  mov     [rsp+2300h+var_2288], r14
0x18000fef1  mov     [rbp+2200h+var_2280], r14
0x18000fef5  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000fefa  test    eax, eax
0x18000fefc  mov     ebx, eax
0x18000fefe  js      loc_18001042D
0x18000ff04  xor     r12d, r12d
0x18000ff07  cmp     word ptr [rdi], 7Dh ; '}'
0x18000ff0b  jz      loc_18001042D
0x18000ff11  lea     rdx, String2; "Delete"
0x18000ff18  mov     rcx, rdi; lpString1
0x18000ff1b  call    cs:__imp_lstrcmpiW
0x18000ff21  mov     r14d, eax
0x18000ff24  lea     rdx, aForceremove; "ForceRemove"
0x18000ff2b  mov     rcx, rdi; lpString1
0x18000ff2e  call    cs:__imp_lstrcmpiW
0x18000ff34  test    eax, eax
0x18000ff36  jz      short loc_18000FF41
0x18000ff38  test    r14d, r14d
0x18000ff3b  jnz     loc_18000FFF2
0x18000ff41  mov     rdx, rdi; wchar_t *
0x18000ff44  mov     rcx, rsi; this
0x18000ff47  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000ff4c  mov     ebx, eax
0x18000ff4e  test    eax, eax
0x18000ff50  js      loc_18001042D
0x18000ff56  test    r15d, r15d
0x18000ff59  jz      loc_18000FFF2
0x18000ff5f  mov     [rsp+2300h+hKey], r12
0x18000ff64  mov     [rsp+2300h+var_22A0], r12
0x18000ff69  mov     [rsp+2300h+var_2298], r12
0x18000ff6e  mov     edx, 5Ch ; '\'; wchar_t
0x18000ff73  mov     rcx, rdi; lpsz
0x18000ff76  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18000ff7b  test    rax, rax
0x18000ff7e  jnz     loc_18001041E
0x18000ff84  mov     rdx, rdi; wchar_t *
0x18000ff87  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x18000ff8c  test    eax, eax
0x18000ff8e  jz      short loc_18000FFA7
0x18000ff90  mov     [rsp+2300h+hKey], r13
0x18000ff95  mov     rdx, rdi; wchar_t *
0x18000ff98  lea     rcx, [rsp+2300h+hKey]; this
0x18000ff9d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18000ffa2  mov     [rsp+2300h+hKey], r12
0x18000ffa7  test    r14d, r14d
0x18000ffaa  jnz     short loc_18000FFE8
0x18000ffac  mov     rdx, rdi; wchar_t *
0x18000ffaf  mov     rcx, rsi; this
0x18000ffb2  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000ffb7  mov     ebx, eax
0x18000ffb9  xor     r14d, r14d
0x18000ffbc  test    eax, eax
0x18000ffbe  js      loc_180010465
0x18000ffc4  mov     rdx, rdi; wchar_t *
0x18000ffc7  mov     rcx, rsi; this
0x18000ffca  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18000ffcf  mov     ebx, eax
0x18000ffd1  test    eax, eax
0x18000ffd3  lea     rcx, [rsp+2300h+hKey]; this
0x18000ffd8  js      loc_18001046A
0x18000ffde  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ffe3  jmp     loc_18001020C
0x18000ffe8  lea     rcx, [rsp+2300h+hKey]; this
0x18000ffed  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000fff2  mov     r12d, 1
0x18000fff8  lea     rdx, aNoremove; "NoRemove"
0x18000ffff  mov     rcx, rdi; lpString1
0x180010002  call    cs:__imp_lstrcmpiW
0x180010008  xor     r14d, r14d
0x18001000b  test    eax, eax
0x18001000d  jnz     short loc_180010027
0x18001000f  mov     r12d, r14d
0x180010012  mov     rdx, rdi; wchar_t *
0x180010015  mov     rcx, rsi; this
0x180010018  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001001d  mov     ebx, eax
0x18001001f  test    eax, eax
0x180010021  js      loc_18001042D
0x180010027  lea     rdx, aVal; "Val"
0x18001002e  mov     rcx, rdi; lpString1
0x180010031  call    cs:__imp_lstrcmpiW
0x180010037  test    eax, eax
0x180010039  jnz     loc_180010120
0x18001003f  lea     rdx, [rbp+2200h+ValueName]; wchar_t *
0x180010046  mov     rcx, rsi; this
0x180010049  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001004e  mov     ebx, eax
0x180010050  test    eax, eax
0x180010052  js      loc_18001042D
0x180010058  mov     rdx, rdi; wchar_t *
0x18001005b  mov     rcx, rsi; this
0x18001005e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180010063  mov     ebx, eax
0x180010065  test    eax, eax
0x180010067  js      loc_18001042D
0x18001006d  cmp     word ptr [rdi], 3Dh ; '='
0x180010071  jnz     loc_180010428
0x180010077  test    r15d, r15d
0x18001007a  jz      short loc_1800100AE
0x18001007c  mov     [rsp+2300h+var_22A0], r14
0x180010081  mov     [rsp+2300h+var_2298], r14
0x180010086  mov     [rsp+2300h+hKey], r13
0x18001008b  mov     r9, rdi; wchar_t *
0x18001008e  lea     r8, [rbp+2200h+ValueName]; wchar_t *
0x180010095  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18001009a  mov     rcx, rsi; this
0x18001009d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x1800100a2  mov     ebx, eax
0x1800100a4  mov     [rsp+2300h+hKey], r14
0x1800100a9  jmp     loc_18000FFD1
0x1800100ae  cmp     [rbp+2200h+arg_20], r14d
0x1800100b5  jnz     short loc_180010110
0x1800100b7  test    r12d, r12d
0x1800100ba  jz      short loc_180010110
0x1800100bc  mov     [rsp+2300h+hKey], r14
0x1800100c1  mov     [rsp+2300h+var_22A0], r14
0x1800100c6  mov     [rsp+2300h+var_2298], r14
0x1800100cb  mov     r9d, 20006h; unsigned int
0x1800100d1  xor     r8d, r8d; lpSubKey
0x1800100d4  mov     rdx, r13; hKey
0x1800100d7  lea     rcx, [rsp+2300h+hKey]; this
0x1800100dc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x1800100e1  test    eax, eax
0x1800100e3  jnz     loc_18001045C
0x1800100e9  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800100f0  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800100f5  call    cs:__imp_RegDeleteValueW
0x1800100fb  test    eax, 0FFFFFFFDh
0x180010100  jnz     loc_18001045C
0x180010106  lea     rcx, [rsp+2300h+hKey]; this
0x18001010b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010110  mov     rdx, rdi; wchar_t *
0x180010113  mov     rcx, rsi; this
0x180010116  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18001011b  jmp     loc_18000FEFA
0x180010120  mov     edx, 5Ch ; '\'; wchar_t
0x180010125  mov     rcx, rdi; lpsz
0x180010128  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18001012d  test    rax, rax
0x180010130  jnz     loc_180010428
0x180010136  test    r15d, r15d
0x180010139  jz      loc_18001025B
0x18001013f  mov     ebx, 2001Fh
0x180010144  mov     r9d, ebx; unsigned int
0x180010147  mov     r8, rdi; lpSubKey
0x18001014a  mov     rdx, r13; hKey
0x18001014d  lea     rcx, [rsp+2300h+var_2290]; this
0x180010152  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x180010157  test    eax, eax
0x180010159  jz      short loc_1800101D4
0x18001015b  lea     r9d, [rbx-6]; unsigned int
0x18001015f  mov     r8, rdi; lpSubKey
0x180010162  mov     rdx, r13; hKey
0x180010165  lea     rcx, [rsp+2300h+var_2290]; this
0x18001016a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001016f  test    eax, eax
0x180010171  jz      short loc_1800101D4
0x180010173  mov     [rbp+2200h+dwDisposition], r14d
0x180010177  mov     [rbp+2200h+var_2270], r14
0x18001017b  lea     rax, [rbp+2200h+dwDisposition]
0x18001017f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180010184  lea     rax, [rbp+2200h+var_2270]
0x180010188  mov     [rsp+2300h+phkResult], rax; phkResult
0x18001018d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180010192  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180010196  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18001019b  xor     r9d, r9d; lpClass
0x18001019e  xor     r8d, r8d; Reserved
0x1800101a1  mov     rdx, rdi; lpSubKey
0x1800101a4  mov     rcx, r13; hKey
0x1800101a7  call    cs:__imp_RegCreateKeyExW
0x1800101ad  mov     ecx, eax
0x1800101af  test    eax, eax
0x1800101b1  jnz     loc_18001035B
0x1800101b7  lea     rcx, [rsp+2300h+var_2290]; this
0x1800101bc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800101c1  mov     ecx, eax
0x1800101c3  mov     rax, [rbp+2200h+var_2270]
0x1800101c7  mov     [rsp+2300h+var_2290], rax
0x1800101cc  test    ecx, ecx
0x1800101ce  jnz     loc_18001035B
0x1800101d4  mov     rdx, rdi; wchar_t *
0x1800101d7  mov     rcx, rsi; this
0x1800101da  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800101df  mov     ebx, eax
0x1800101e1  test    eax, eax
0x1800101e3  js      loc_18001042D
0x1800101e9  cmp     word ptr [rdi], 3Dh ; '='
0x1800101ed  jnz     short loc_18001020C
0x1800101ef  mov     r9, rdi; wchar_t *
0x1800101f2  xor     r8d, r8d; wchar_t *
0x1800101f5  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x1800101fa  mov     rcx, rsi; this
0x1800101fd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x180010202  mov     ebx, eax
0x180010204  test    eax, eax
0x180010206  js      loc_18001042D
0x18001020c  cmp     word ptr [rdi], 7Bh ; '{'
0x180010210  jnz     loc_18000FF04
0x180010216  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001021a  inc     rax
0x18001021d  cmp     [rdi+rax*2], r14w
0x180010222  jnz     short loc_18001021A
0x180010224  cmp     rax, 1
0x180010228  jnz     loc_18000FF04
0x18001022e  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180010233  mov     r9d, r15d; int
0x180010236  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001023b  mov     rdx, rdi; wchar_t *
0x18001023e  mov     rcx, rsi; this
0x180010241  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010246  mov     ebx, eax
0x180010248  test    eax, eax
0x18001024a  js      loc_18001042D
0x180010250  mov     rdx, rdi
0x180010253  mov     rcx, rsi
0x180010256  jmp     loc_18000FEF5
0x18001025b  cmp     [rbp+2200h+arg_20], r14d
0x180010262  jnz     short loc_18001027F
0x180010264  mov     r9d, 20019h; unsigned int
0x18001026a  mov     r8, rdi; lpSubKey
0x18001026d  mov     rdx, r13; hKey
0x180010270  lea     rcx, [rsp+2300h+var_2290]; this
0x180010275  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001027a  mov     r14d, eax
0x18001027d  jmp     short loc_180010285
0x18001027f  mov     r14d, 2
0x180010285  mov     r15d, 1
0x18001028b  test    r14d, r14d
0x18001028e  cmovz   r15d, [rbp+2200h+arg_20]
0x180010296  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001029a  mov     r8, rdi
0x18001029d  mov     edx, 104h
0x1800102a2  lea     rcx, [rbp+2200h+var_2260]
0x1800102a6  call    cs:__imp__o_wcsncpy_s
0x1800102ac  mov     ecx, eax; int
0x1800102ae  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800102b3  mov     rdx, rdi; wchar_t *
0x1800102b6  mov     rcx, rsi; this
0x1800102b9  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800102be  mov     ebx, eax
0x1800102c0  test    eax, eax
0x1800102c2  js      loc_18001042D
0x1800102c8  mov     rdx, rdi; wchar_t *
0x1800102cb  mov     rcx, rsi; this
0x1800102ce  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x1800102d3  mov     ebx, eax
0x1800102d5  xor     ecx, ecx
0x1800102d7  test    eax, eax
0x1800102d9  js      loc_18001042D
0x1800102df  cmp     word ptr [rdi], 7Bh ; '{'
0x1800102e3  jnz     short loc_180010334
0x1800102e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800102e9  inc     rax
0x1800102ec  cmp     [rdi+rax*2], cx
0x1800102f0  jnz     short loc_1800102E9
0x1800102f2  cmp     rax, 1
0x1800102f6  jnz     short loc_180010334
0x1800102f8  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x1800102fd  xor     r9d, r9d; int
0x180010300  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180010305  mov     rdx, rdi; wchar_t *
0x180010308  mov     rcx, rsi; this
0x18001030b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180010310  mov     ebx, eax
0x180010312  test    eax, eax
0x180010314  jns     short loc_18001031F
0x180010316  test    r15d, r15d
0x180010319  jz      loc_18001042D
0x18001031f  mov     rdx, rdi; wchar_t *
0x180010322  mov     rcx, rsi; this
0x180010325  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001032a  mov     ebx, eax
0x18001032c  test    eax, eax
0x18001032e  js      loc_18001042D
0x180010334  cmp     r14d, 2
0x180010338  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
