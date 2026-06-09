# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x18001a7d4`
- end: `0x18001adad`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18001a418`
- `0x18001a7d4`

## callees

- `0x18000fcd0`
- `0x180016dfc`
- `0x18001760c`
- `0x180017658`
- `0x1800179d4`
- `0x180017ae4`
- `0x180017dac`
- `0x180019968`
- `0x180019a40`
- `0x180019e30`
- `0x18001a304`
- `0x18001a7d4`
- `0x18001b8cc`
- `0x18001b99c`
- `0x180024dc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001abda`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001abda`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001aa29`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001aa29`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001aadb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001aadb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a84f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a862`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a936`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a965`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a84f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a862`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a936`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a965`

## string_xrefs

- `0x18001a858`: `ForceRemove`
- `0x18001a92c`: `NoRemove`
- `0x18001a845`: `Delete`

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
  unsigned int v15; // eax
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
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
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
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
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
0x18001a7d4  push    rbp
0x18001a7d6  push    rbx
0x18001a7d7  push    rsi
0x18001a7d8  push    rdi
0x18001a7d9  push    r12
0x18001a7db  push    r13
0x18001a7dd  push    r14
0x18001a7df  push    r15
0x18001a7e1  lea     rbp, [rsp-21C8h]
0x18001a7e9  mov     eax, 22C8h
0x18001a7ee  call    _alloca_probe
0x18001a7f3  sub     rsp, rax
0x18001a7f6  mov     rax, cs:__security_cookie
0x18001a7fd  xor     rax, rsp
0x18001a800  mov     [rbp+2200h+var_50], rax
0x18001a807  mov     r15d, r9d
0x18001a80a  mov     [rsp+2300h+var_22B0], r9d
0x18001a80f  mov     r13, r8
0x18001a812  mov     rdi, rdx
0x18001a815  mov     rsi, rcx
0x18001a818  xor     r14d, r14d
0x18001a81b  mov     [rsp+2300h+var_2290], r14
0x18001a820  mov     [rsp+2300h+var_2288], r14
0x18001a825  mov     [rbp+2200h+var_2280], r14
0x18001a829  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001a82e  test    eax, eax
0x18001a830  mov     ebx, eax
0x18001a832  js      loc_18001AD61
0x18001a838  xor     r12d, r12d
0x18001a83b  cmp     word ptr [rdi], 7Dh ; '}'
0x18001a83f  jz      loc_18001AD61
0x18001a845  lea     rdx, aDelete; "Delete"
0x18001a84c  mov     rcx, rdi; lpString1
0x18001a84f  call    cs:__imp_lstrcmpiW
0x18001a855  mov     r14d, eax
0x18001a858  lea     rdx, aForceremove; "ForceRemove"
0x18001a85f  mov     rcx, rdi; lpString1
0x18001a862  call    cs:__imp_lstrcmpiW
0x18001a868  test    eax, eax
0x18001a86a  jz      short loc_18001A875
0x18001a86c  test    r14d, r14d
0x18001a86f  jnz     loc_18001A926
0x18001a875  mov     rdx, rdi; wchar_t *
0x18001a878  mov     rcx, rsi; this
0x18001a87b  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001a880  mov     ebx, eax
0x18001a882  test    eax, eax
0x18001a884  js      loc_18001AD61
0x18001a88a  test    r15d, r15d
0x18001a88d  jz      loc_18001A926
0x18001a893  mov     [rsp+2300h+hKey], r12
0x18001a898  mov     [rsp+2300h+var_22A0], r12
0x18001a89d  mov     [rsp+2300h+var_2298], r12
0x18001a8a2  mov     edx, 5Ch ; '\'; wchar_t
0x18001a8a7  mov     rcx, rdi; lpsz
0x18001a8aa  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18001a8af  test    rax, rax
0x18001a8b2  jnz     loc_18001AD52
0x18001a8b8  mov     rdx, rdi; wchar_t *
0x18001a8bb  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x18001a8c0  test    eax, eax
0x18001a8c2  jz      short loc_18001A8DB
0x18001a8c4  mov     [rsp+2300h+hKey], r13
0x18001a8c9  mov     rdx, rdi; wchar_t *
0x18001a8cc  lea     rcx, [rsp+2300h+hKey]; this
0x18001a8d1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18001a8d6  mov     [rsp+2300h+hKey], r12
0x18001a8db  test    r14d, r14d
0x18001a8de  jnz     short loc_18001A91C
0x18001a8e0  mov     rdx, rdi; wchar_t *
0x18001a8e3  mov     rcx, rsi; this
0x18001a8e6  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001a8eb  mov     ebx, eax
0x18001a8ed  xor     r14d, r14d
0x18001a8f0  test    eax, eax
0x18001a8f2  js      loc_18001AD99
0x18001a8f8  mov     rdx, rdi; wchar_t *
0x18001a8fb  mov     rcx, rsi; this
0x18001a8fe  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18001a903  mov     ebx, eax
0x18001a905  test    eax, eax
0x18001a907  lea     rcx, [rsp+2300h+hKey]; this
0x18001a90c  js      loc_18001AD9E
0x18001a912  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a917  jmp     loc_18001AB40
0x18001a91c  lea     rcx, [rsp+2300h+hKey]; this
0x18001a921  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a926  mov     r12d, 1
0x18001a92c  lea     rdx, aNoremove; "NoRemove"
0x18001a933  mov     rcx, rdi; lpString1
0x18001a936  call    cs:__imp_lstrcmpiW
0x18001a93c  xor     r14d, r14d
0x18001a93f  test    eax, eax
0x18001a941  jnz     short loc_18001A95B
0x18001a943  mov     r12d, r14d
0x18001a946  mov     rdx, rdi; wchar_t *
0x18001a949  mov     rcx, rsi; this
0x18001a94c  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001a951  mov     ebx, eax
0x18001a953  test    eax, eax
0x18001a955  js      loc_18001AD61
0x18001a95b  lea     rdx, aVal; "Val"
0x18001a962  mov     rcx, rdi; lpString1
0x18001a965  call    cs:__imp_lstrcmpiW
0x18001a96b  test    eax, eax
0x18001a96d  jnz     loc_18001AA54
0x18001a973  lea     rdx, [rbp+2200h+ValueName]; wchar_t *
0x18001a97a  mov     rcx, rsi; this
0x18001a97d  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001a982  mov     ebx, eax
0x18001a984  test    eax, eax
0x18001a986  js      loc_18001AD61
0x18001a98c  mov     rdx, rdi; wchar_t *
0x18001a98f  mov     rcx, rsi; this
0x18001a992  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001a997  mov     ebx, eax
0x18001a999  test    eax, eax
0x18001a99b  js      loc_18001AD61
0x18001a9a1  cmp     word ptr [rdi], 3Dh ; '='
0x18001a9a5  jnz     loc_18001AD5C
0x18001a9ab  test    r15d, r15d
0x18001a9ae  jz      short loc_18001A9E2
0x18001a9b0  mov     [rsp+2300h+var_22A0], r14
0x18001a9b5  mov     [rsp+2300h+var_2298], r14
0x18001a9ba  mov     [rsp+2300h+hKey], r13
0x18001a9bf  mov     r9, rdi; wchar_t *
0x18001a9c2  lea     r8, [rbp+2200h+ValueName]; wchar_t *
0x18001a9c9  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18001a9ce  mov     rcx, rsi; this
0x18001a9d1  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18001a9d6  mov     ebx, eax
0x18001a9d8  mov     [rsp+2300h+hKey], r14
0x18001a9dd  jmp     loc_18001A905
0x18001a9e2  cmp     [rbp+2200h+arg_20], r14d
0x18001a9e9  jnz     short loc_18001AA44
0x18001a9eb  test    r12d, r12d
0x18001a9ee  jz      short loc_18001AA44
0x18001a9f0  mov     [rsp+2300h+hKey], r14
0x18001a9f5  mov     [rsp+2300h+var_22A0], r14
0x18001a9fa  mov     [rsp+2300h+var_2298], r14
0x18001a9ff  mov     r9d, 20006h; unsigned int
0x18001aa05  xor     r8d, r8d; lpSubKey
0x18001aa08  mov     rdx, r13; hKey
0x18001aa0b  lea     rcx, [rsp+2300h+hKey]; this
0x18001aa10  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001aa15  test    eax, eax
0x18001aa17  jnz     loc_18001AD90
0x18001aa1d  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18001aa24  mov     rcx, [rsp+2300h+hKey]; hKey
0x18001aa29  call    cs:__imp_RegDeleteValueW
0x18001aa2f  test    eax, 0FFFFFFFDh
0x18001aa34  jnz     loc_18001AD90
0x18001aa3a  lea     rcx, [rsp+2300h+hKey]; this
0x18001aa3f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001aa44  mov     rdx, rdi; wchar_t *
0x18001aa47  mov     rcx, rsi; this
0x18001aa4a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18001aa4f  jmp     loc_18001A82E
0x18001aa54  mov     edx, 5Ch ; '\'; wchar_t
0x18001aa59  mov     rcx, rdi; lpsz
0x18001aa5c  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x18001aa61  test    rax, rax
0x18001aa64  jnz     loc_18001AD5C
0x18001aa6a  test    r15d, r15d
0x18001aa6d  jz      loc_18001AB8F
0x18001aa73  mov     ebx, 2001Fh
0x18001aa78  mov     r9d, ebx; unsigned int
0x18001aa7b  mov     r8, rdi; lpSubKey
0x18001aa7e  mov     rdx, r13; hKey
0x18001aa81  lea     rcx, [rsp+2300h+var_2290]; this
0x18001aa86  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001aa8b  test    eax, eax
0x18001aa8d  jz      short loc_18001AB08
0x18001aa8f  lea     r9d, [rbx-6]; unsigned int
0x18001aa93  mov     r8, rdi; lpSubKey
0x18001aa96  mov     rdx, r13; hKey
0x18001aa99  lea     rcx, [rsp+2300h+var_2290]; this
0x18001aa9e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001aaa3  test    eax, eax
0x18001aaa5  jz      short loc_18001AB08
0x18001aaa7  mov     [rbp+2200h+dwDisposition], r14d
0x18001aaab  mov     [rbp+2200h+var_2270], r14
0x18001aaaf  lea     rax, [rbp+2200h+dwDisposition]
0x18001aab3  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18001aab8  lea     rax, [rbp+2200h+var_2270]
0x18001aabc  mov     [rsp+2300h+phkResult], rax; phkResult
0x18001aac1  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001aac6  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18001aaca  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18001aacf  xor     r9d, r9d; lpClass
0x18001aad2  xor     r8d, r8d; Reserved
0x18001aad5  mov     rdx, rdi; lpSubKey
0x18001aad8  mov     rcx, r13; hKey
0x18001aadb  call    cs:__imp_RegCreateKeyExW
0x18001aae1  mov     ecx, eax
0x18001aae3  test    eax, eax
0x18001aae5  jnz     loc_18001AC8F
0x18001aaeb  lea     rcx, [rsp+2300h+var_2290]; this
0x18001aaf0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001aaf5  mov     ecx, eax
0x18001aaf7  mov     rax, [rbp+2200h+var_2270]
0x18001aafb  mov     [rsp+2300h+var_2290], rax
0x18001ab00  test    ecx, ecx
0x18001ab02  jnz     loc_18001AC8F
0x18001ab08  mov     rdx, rdi; wchar_t *
0x18001ab0b  mov     rcx, rsi; this
0x18001ab0e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001ab13  mov     ebx, eax
0x18001ab15  test    eax, eax
0x18001ab17  js      loc_18001AD61
0x18001ab1d  cmp     word ptr [rdi], 3Dh ; '='
0x18001ab21  jnz     short loc_18001AB40
0x18001ab23  mov     r9, rdi; wchar_t *
0x18001ab26  xor     r8d, r8d; wchar_t *
0x18001ab29  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18001ab2e  mov     rcx, rsi; this
0x18001ab31  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x18001ab36  mov     ebx, eax
0x18001ab38  test    eax, eax
0x18001ab3a  js      loc_18001AD61
0x18001ab40  cmp     word ptr [rdi], 7Bh ; '{'
0x18001ab44  jnz     loc_18001A838
0x18001ab4a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ab4e  inc     rax
0x18001ab51  cmp     [rdi+rax*2], r14w
0x18001ab56  jnz     short loc_18001AB4E
0x18001ab58  cmp     rax, 1
0x18001ab5c  jnz     loc_18001A838
0x18001ab62  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x18001ab67  mov     r9d, r15d; int
0x18001ab6a  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001ab6f  mov     rdx, rdi; wchar_t *
0x18001ab72  mov     rcx, rsi; this
0x18001ab75  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001ab7a  mov     ebx, eax
0x18001ab7c  test    eax, eax
0x18001ab7e  js      loc_18001AD61
0x18001ab84  mov     rdx, rdi
0x18001ab87  mov     rcx, rsi
0x18001ab8a  jmp     loc_18001A829
0x18001ab8f  cmp     [rbp+2200h+arg_20], r14d
0x18001ab96  jnz     short loc_18001ABB3
0x18001ab98  mov     r9d, 20019h; unsigned int
0x18001ab9e  mov     r8, rdi; lpSubKey
0x18001aba1  mov     rdx, r13; hKey
0x18001aba4  lea     rcx, [rsp+2300h+var_2290]; this
0x18001aba9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18001abae  mov     r14d, eax
0x18001abb1  jmp     short loc_18001ABB9
0x18001abb3  mov     r14d, 2
0x18001abb9  mov     r15d, 1
0x18001abbf  test    r14d, r14d
0x18001abc2  cmovz   r15d, [rbp+2200h+arg_20]
0x18001abca  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001abce  mov     r8, rdi
0x18001abd1  mov     edx, 104h
0x18001abd6  lea     rcx, [rbp+2200h+var_2260]
0x18001abda  call    cs:__imp__o_wcsncpy_s
0x18001abe0  mov     ecx, eax; int
0x18001abe2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001abe7  mov     rdx, rdi; wchar_t *
0x18001abea  mov     rcx, rsi; this
0x18001abed  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001abf2  mov     ebx, eax
0x18001abf4  test    eax, eax
0x18001abf6  js      loc_18001AD61
0x18001abfc  mov     rdx, rdi; wchar_t *
0x18001abff  mov     rcx, rsi; this
0x18001ac02  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18001ac07  mov     ebx, eax
0x18001ac09  xor     ecx, ecx
0x18001ac0b  test    eax, eax
0x18001ac0d  js      loc_18001AD61
0x18001ac13  cmp     word ptr [rdi], 7Bh ; '{'
0x18001ac17  jnz     short loc_18001AC68
0x18001ac19  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ac1d  inc     rax
0x18001ac20  cmp     [rdi+rax*2], cx
0x18001ac24  jnz     short loc_18001AC1D
0x18001ac26  cmp     rax, 1
0x18001ac2a  jnz     short loc_18001AC68
0x18001ac2c  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x18001ac31  xor     r9d, r9d; int
0x18001ac34  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001ac39  mov     rdx, rdi; wchar_t *
0x18001ac3c  mov     rcx, rsi; this
0x18001ac3f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x18001ac44  mov     ebx, eax
0x18001ac46  test    eax, eax
0x18001ac48  jns     short loc_18001AC53
0x18001ac4a  test    r15d, r15d
0x18001ac4d  jz      loc_18001AD61
0x18001ac53  mov     rdx, rdi; wchar_t *
0x18001ac56  mov     rcx, rsi; this
0x18001ac59  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001ac5e  mov     ebx, eax
0x18001ac60  test    eax, eax
0x18001ac62  js      loc_18001AD61
0x18001ac68  cmp     r14d, 2
0x18001ac6c  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
