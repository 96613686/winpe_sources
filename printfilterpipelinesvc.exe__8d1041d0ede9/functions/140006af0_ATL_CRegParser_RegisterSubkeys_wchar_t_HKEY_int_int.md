# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x140006af0`
- end: `0x1400070c9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1400067cc`
- `0x140006af0`

## callees

- `0x140002070`
- `0x140004b9c`
- `0x1400052a0`
- `0x14000537c`
- `0x1400054a4`
- `0x140005644`
- `0x1400058ec`
- `0x140005cb8`
- `0x140005eb0`
- `0x14000601c`
- `0x1400066b8`
- `0x140006af0`
- `0x1400074b4`
- `0x140007584`
- `0x14005d370`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x140006df7`
- `ADVAPI32!RegCreateKeyExW` at `0x140006df7`
- `ADVAPI32!RegDeleteValueW` at `0x140006d45`
- `ADVAPI32!RegDeleteValueW` at `0x140006d45`
- `KERNEL32!lstrcmpiW` at `0x140006b6b`
- `KERNEL32!lstrcmpiW` at `0x140006b7e`
- `KERNEL32!lstrcmpiW` at `0x140006c52`
- `KERNEL32!lstrcmpiW` at `0x140006c81`
- `KERNEL32!lstrcmpiW` at `0x140006b6b`
- `KERNEL32!lstrcmpiW` at `0x140006b7e`
- `KERNEL32!lstrcmpiW` at `0x140006c52`
- `KERNEL32!lstrcmpiW` at `0x140006c81`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140006ef6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140006ef6`

## string_xrefs

- `0x140006b74`: `ForceRemove`
- `0x140006c48`: `NoRemove`
- `0x140006b61`: `Delete`

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
  int v16; // edx
  unsigned int v17; // eax
  int v18; // edx
  unsigned __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // r14d
  int v23; // r15d
  int v24; // eax
  ATL::CRegParser *v25; // rcx
  __int64 v26; // rax
  int HasSubKeys; // r14d
  unsigned int v28; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34; // [rsp+68h] [rbp-98h]
  HKEY v35[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v38[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v35, 0, sizeof(v35));
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
          v33 = 0;
          v34 = 0;
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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v17 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            v19 = v17;
            if ( v17 )
              goto LABEL_65;
            v20 = ATL::CRegKey::Close((ATL::CRegKey *)v35);
            v19 = v20;
            v35[0] = phkResult;
            if ( v20 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v35, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v21 = -1;
          do
            ++v21;
          while ( v7[v21] );
          if ( v21 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], v5, 0);
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
          v22 = 2;
        else
          v22 = ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u);
        v23 = 1;
        if ( !v22 )
          v23 = a5;
        v24 = _o_wcsncpy_s(v38, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v24);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v25 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v26 = -1;
          do
            ++v26;
          while ( v7[v26] );
          if ( v26 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], 0, v23);
            if ( v10 < 0 && !v23 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v22 != 2 )
        {
          if ( v22 )
          {
            if ( !a5 )
            {
              v19 = v22;
LABEL_65:
              v10 = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v19, v18);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v25, v35[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v25, v38) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v35, v38);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v25, v35[0]);
            v28 = ATL::CRegKey::Close((ATL::CRegKey *)v35);
            if ( v28 )
            {
              v19 = v28;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v33 = 0;
              v34 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v38);
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
      v33 = 0;
      v34 = 0;
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
    v33 = 0;
    v34 = 0;
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
  v10 = NCoreLibrary::HResultFromWin32((NCoreLibrary *)v15, v16);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v35);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140006af0  push    rbp
0x140006af2  push    rbx
0x140006af3  push    rsi
0x140006af4  push    rdi
0x140006af5  push    r12
0x140006af7  push    r13
0x140006af9  push    r14
0x140006afb  push    r15
0x140006afd  lea     rbp, [rsp-21C8h]
0x140006b05  mov     eax, 22C8h
0x140006b0a  call    _alloca_probe
0x140006b0f  sub     rsp, rax
0x140006b12  mov     rax, cs:__security_cookie
0x140006b19  xor     rax, rsp
0x140006b1c  mov     [rbp+2200h+var_50], rax
0x140006b23  mov     r15d, r9d
0x140006b26  mov     [rsp+2300h+var_22B0], r9d
0x140006b2b  mov     r13, r8
0x140006b2e  mov     rdi, rdx
0x140006b31  mov     rsi, rcx
0x140006b34  xor     r14d, r14d
0x140006b37  mov     [rsp+2300h+var_2290], r14
0x140006b3c  mov     [rsp+2300h+var_2288], r14
0x140006b41  mov     [rbp+2200h+var_2280], r14
0x140006b45  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006b4a  test    eax, eax
0x140006b4c  mov     ebx, eax
0x140006b4e  js      loc_14000707D
0x140006b54  xor     r12d, r12d
0x140006b57  cmp     word ptr [rdi], 7Dh ; '}'
0x140006b5b  jz      loc_14000707D
0x140006b61  lea     rdx, String2; "Delete"
0x140006b68  mov     rcx, rdi; lpString1
0x140006b6b  call    cs:__imp_lstrcmpiW
0x140006b71  mov     r14d, eax
0x140006b74  lea     rdx, aForceremove; "ForceRemove"
0x140006b7b  mov     rcx, rdi; lpString1
0x140006b7e  call    cs:__imp_lstrcmpiW
0x140006b84  test    eax, eax
0x140006b86  jz      short loc_140006B91
0x140006b88  test    r14d, r14d
0x140006b8b  jnz     loc_140006C42
0x140006b91  mov     rdx, rdi; wchar_t *
0x140006b94  mov     rcx, rsi; this
0x140006b97  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006b9c  mov     ebx, eax
0x140006b9e  test    eax, eax
0x140006ba0  js      loc_14000707D
0x140006ba6  test    r15d, r15d
0x140006ba9  jz      loc_140006C42
0x140006baf  mov     [rsp+2300h+hKey], r12
0x140006bb4  mov     [rsp+2300h+var_22A0], r12
0x140006bb9  mov     [rsp+2300h+var_2298], r12
0x140006bbe  mov     edx, 5Ch ; '\'; wchar_t
0x140006bc3  mov     rcx, rdi; lpsz
0x140006bc6  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x140006bcb  test    rax, rax
0x140006bce  jnz     loc_14000706E
0x140006bd4  mov     rdx, rdi; wchar_t *
0x140006bd7  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x140006bdc  test    eax, eax
0x140006bde  jz      short loc_140006BF7
0x140006be0  mov     [rsp+2300h+hKey], r13
0x140006be5  mov     rdx, rdi; wchar_t *
0x140006be8  lea     rcx, [rsp+2300h+hKey]; this
0x140006bed  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x140006bf2  mov     [rsp+2300h+hKey], r12
0x140006bf7  test    r14d, r14d
0x140006bfa  jnz     short loc_140006C38
0x140006bfc  mov     rdx, rdi; wchar_t *
0x140006bff  mov     rcx, rsi; this
0x140006c02  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006c07  mov     ebx, eax
0x140006c09  xor     r14d, r14d
0x140006c0c  test    eax, eax
0x140006c0e  js      loc_1400070B5
0x140006c14  mov     rdx, rdi; wchar_t *
0x140006c17  mov     rcx, rsi; this
0x140006c1a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x140006c1f  mov     ebx, eax
0x140006c21  test    eax, eax
0x140006c23  lea     rcx, [rsp+2300h+hKey]; this
0x140006c28  js      loc_1400070BA
0x140006c2e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140006c33  jmp     loc_140006E5C
0x140006c38  lea     rcx, [rsp+2300h+hKey]; this
0x140006c3d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140006c42  mov     r12d, 1
0x140006c48  lea     rdx, aNoremove; "NoRemove"
0x140006c4f  mov     rcx, rdi; lpString1
0x140006c52  call    cs:__imp_lstrcmpiW
0x140006c58  xor     r14d, r14d
0x140006c5b  test    eax, eax
0x140006c5d  jnz     short loc_140006C77
0x140006c5f  mov     r12d, r14d
0x140006c62  mov     rdx, rdi; wchar_t *
0x140006c65  mov     rcx, rsi; this
0x140006c68  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006c6d  mov     ebx, eax
0x140006c6f  test    eax, eax
0x140006c71  js      loc_14000707D
0x140006c77  lea     rdx, aVal; "Val"
0x140006c7e  mov     rcx, rdi; lpString1
0x140006c81  call    cs:__imp_lstrcmpiW
0x140006c87  test    eax, eax
0x140006c89  jnz     loc_140006D70
0x140006c8f  lea     rdx, [rbp+2200h+ValueName]; wchar_t *
0x140006c96  mov     rcx, rsi; this
0x140006c99  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006c9e  mov     ebx, eax
0x140006ca0  test    eax, eax
0x140006ca2  js      loc_14000707D
0x140006ca8  mov     rdx, rdi; wchar_t *
0x140006cab  mov     rcx, rsi; this
0x140006cae  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006cb3  mov     ebx, eax
0x140006cb5  test    eax, eax
0x140006cb7  js      loc_14000707D
0x140006cbd  cmp     word ptr [rdi], 3Dh ; '='
0x140006cc1  jnz     loc_140007078
0x140006cc7  test    r15d, r15d
0x140006cca  jz      short loc_140006CFE
0x140006ccc  mov     [rsp+2300h+var_22A0], r14
0x140006cd1  mov     [rsp+2300h+var_2298], r14
0x140006cd6  mov     [rsp+2300h+hKey], r13
0x140006cdb  mov     r9, rdi; wchar_t *
0x140006cde  lea     r8, [rbp+2200h+ValueName]; wchar_t *
0x140006ce5  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x140006cea  mov     rcx, rsi; this
0x140006ced  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x140006cf2  mov     ebx, eax
0x140006cf4  mov     [rsp+2300h+hKey], r14
0x140006cf9  jmp     loc_140006C21
0x140006cfe  cmp     [rbp+2200h+arg_20], r14d
0x140006d05  jnz     short loc_140006D60
0x140006d07  test    r12d, r12d
0x140006d0a  jz      short loc_140006D60
0x140006d0c  mov     [rsp+2300h+hKey], r14
0x140006d11  mov     [rsp+2300h+var_22A0], r14
0x140006d16  mov     [rsp+2300h+var_2298], r14
0x140006d1b  mov     r9d, 20006h; unsigned int
0x140006d21  xor     r8d, r8d; lpSubKey
0x140006d24  mov     rdx, r13; hKey
0x140006d27  lea     rcx, [rsp+2300h+hKey]; this
0x140006d2c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x140006d31  test    eax, eax
0x140006d33  jnz     loc_1400070AC
0x140006d39  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x140006d40  mov     rcx, [rsp+2300h+hKey]; hKey
0x140006d45  call    cs:__imp_RegDeleteValueW
0x140006d4b  test    eax, 0FFFFFFFDh
0x140006d50  jnz     loc_1400070AC
0x140006d56  lea     rcx, [rsp+2300h+hKey]; this
0x140006d5b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140006d60  mov     rdx, rdi; wchar_t *
0x140006d63  mov     rcx, rsi; this
0x140006d66  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x140006d6b  jmp     loc_140006B4A
0x140006d70  mov     edx, 5Ch ; '\'; wchar_t
0x140006d75  mov     rcx, rdi; lpsz
0x140006d78  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x140006d7d  test    rax, rax
0x140006d80  jnz     loc_140007078
0x140006d86  test    r15d, r15d
0x140006d89  jz      loc_140006EAB
0x140006d8f  mov     ebx, 2001Fh
0x140006d94  mov     r9d, ebx; unsigned int
0x140006d97  mov     r8, rdi; lpSubKey
0x140006d9a  mov     rdx, r13; hKey
0x140006d9d  lea     rcx, [rsp+2300h+var_2290]; this
0x140006da2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x140006da7  test    eax, eax
0x140006da9  jz      short loc_140006E24
0x140006dab  lea     r9d, [rbx-6]; unsigned int
0x140006daf  mov     r8, rdi; lpSubKey
0x140006db2  mov     rdx, r13; hKey
0x140006db5  lea     rcx, [rsp+2300h+var_2290]; this
0x140006dba  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x140006dbf  test    eax, eax
0x140006dc1  jz      short loc_140006E24
0x140006dc3  mov     [rbp+2200h+dwDisposition], r14d
0x140006dc7  mov     [rbp+2200h+var_2270], r14
0x140006dcb  lea     rax, [rbp+2200h+dwDisposition]
0x140006dcf  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x140006dd4  lea     rax, [rbp+2200h+var_2270]
0x140006dd8  mov     [rsp+2300h+phkResult], rax; phkResult
0x140006ddd  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x140006de2  mov     [rsp+2300h+samDesired], ebx; samDesired
0x140006de6  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x140006deb  xor     r9d, r9d; lpClass
0x140006dee  xor     r8d, r8d; Reserved
0x140006df1  mov     rdx, rdi; lpSubKey
0x140006df4  mov     rcx, r13; hKey
0x140006df7  call    cs:__imp_RegCreateKeyExW
0x140006dfd  mov     ecx, eax
0x140006dff  test    eax, eax
0x140006e01  jnz     loc_140006FAB
0x140006e07  lea     rcx, [rsp+2300h+var_2290]; this
0x140006e0c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140006e11  mov     ecx, eax
0x140006e13  mov     rax, [rbp+2200h+var_2270]
0x140006e17  mov     [rsp+2300h+var_2290], rax
0x140006e1c  test    ecx, ecx
0x140006e1e  jnz     loc_140006FAB
0x140006e24  mov     rdx, rdi; wchar_t *
0x140006e27  mov     rcx, rsi; this
0x140006e2a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006e2f  mov     ebx, eax
0x140006e31  test    eax, eax
0x140006e33  js      loc_14000707D
0x140006e39  cmp     word ptr [rdi], 3Dh ; '='
0x140006e3d  jnz     short loc_140006E5C
0x140006e3f  mov     r9, rdi; wchar_t *
0x140006e42  xor     r8d, r8d; wchar_t *
0x140006e45  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x140006e4a  mov     rcx, rsi; this
0x140006e4d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)
0x140006e52  mov     ebx, eax
0x140006e54  test    eax, eax
0x140006e56  js      loc_14000707D
0x140006e5c  cmp     word ptr [rdi], 7Bh ; '{'
0x140006e60  jnz     loc_140006B54
0x140006e66  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006e6a  inc     rax
0x140006e6d  cmp     [rdi+rax*2], r14w
0x140006e72  jnz     short loc_140006E6A
0x140006e74  cmp     rax, 1
0x140006e78  jnz     loc_140006B54
0x140006e7e  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x140006e83  mov     r9d, r15d; int
0x140006e86  mov     r8, [rsp+2300h+var_2290]; HKEY
0x140006e8b  mov     rdx, rdi; wchar_t *
0x140006e8e  mov     rcx, rsi; this
0x140006e91  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x140006e96  mov     ebx, eax
0x140006e98  test    eax, eax
0x140006e9a  js      loc_14000707D
0x140006ea0  mov     rdx, rdi
0x140006ea3  mov     rcx, rsi
0x140006ea6  jmp     loc_140006B45
0x140006eab  cmp     [rbp+2200h+arg_20], r14d
0x140006eb2  jnz     short loc_140006ECF
0x140006eb4  mov     r9d, 20019h; unsigned int
0x140006eba  mov     r8, rdi; lpSubKey
0x140006ebd  mov     rdx, r13; hKey
0x140006ec0  lea     rcx, [rsp+2300h+var_2290]; this
0x140006ec5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)
0x140006eca  mov     r14d, eax
0x140006ecd  jmp     short loc_140006ED5
0x140006ecf  mov     r14d, 2
0x140006ed5  mov     r15d, 1
0x140006edb  test    r14d, r14d
0x140006ede  cmovz   r15d, [rbp+2200h+arg_20]
0x140006ee6  or      r9, 0FFFFFFFFFFFFFFFFh
0x140006eea  mov     r8, rdi
0x140006eed  mov     edx, 104h
0x140006ef2  lea     rcx, [rbp+2200h+var_2260]
0x140006ef6  call    cs:__imp__o_wcsncpy_s
0x140006efc  mov     ecx, eax; int
0x140006efe  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140006f03  mov     rdx, rdi; wchar_t *
0x140006f06  mov     rcx, rsi; this
0x140006f09  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006f0e  mov     ebx, eax
0x140006f10  test    eax, eax
0x140006f12  js      loc_14000707D
0x140006f18  mov     rdx, rdi; wchar_t *
0x140006f1b  mov     rcx, rsi; this
0x140006f1e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x140006f23  mov     ebx, eax
0x140006f25  xor     ecx, ecx
0x140006f27  test    eax, eax
0x140006f29  js      loc_14000707D
0x140006f2f  cmp     word ptr [rdi], 7Bh ; '{'
0x140006f33  jnz     short loc_140006F84
0x140006f35  or      rax, 0FFFFFFFFFFFFFFFFh
0x140006f39  inc     rax
0x140006f3c  cmp     [rdi+rax*2], cx
0x140006f40  jnz     short loc_140006F39
0x140006f42  cmp     rax, 1
0x140006f46  jnz     short loc_140006F84
0x140006f48  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x140006f4d  xor     r9d, r9d; int
0x140006f50  mov     r8, [rsp+2300h+var_2290]; HKEY
0x140006f55  mov     rdx, rdi; wchar_t *
0x140006f58  mov     rcx, rsi; this
0x140006f5b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x140006f60  mov     ebx, eax
0x140006f62  test    eax, eax
0x140006f64  jns     short loc_140006F6F
0x140006f66  test    r15d, r15d
0x140006f69  jz      loc_14000707D
0x140006f6f  mov     rdx, rdi; wchar_t *
0x140006f72  mov     rcx, rsi; this
0x140006f75  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140006f7a  mov     ebx, eax
0x140006f7c  test    eax, eax
0x140006f7e  js      loc_14000707D
0x140006f84  cmp     r14d, 2
0x140006f88  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
