# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180024d50`
- end: `0x18002532b`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1499`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180024a2c`
- `0x180024d50`

## callees

- `0x18001d8e0`
- `0x18002396c`
- `0x180024068`
- `0x1800240d8`
- `0x180024110`
- `0x180024224`
- `0x180024250`
- `0x180024438`
- `0x1800244d4`
- `0x180024634`
- `0x180024918`
- `0x180024d50`
- `0x180025388`
- `0x180025458`
- `0x180032090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180025156`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180025156`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025057`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180025057`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024fa5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180024fa5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024dcb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024dde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024eb2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024ee1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024dcb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024dde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024eb2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180024ee1`

## string_xrefs

- `0x180024dd4`: `ForceRemove`
- `0x180024ea8`: `NoRemove`
- `0x180024dc1`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned __int16 v34[264]; // [rsp+A0h] [rbp-60h] BYREF
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
      goto LABEL_80;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_80;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( v5 )
        {
          hKey = 0;
          v29 = 0;
          v30 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
            v10 = -2147352567;
            goto LABEL_80;
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
              goto LABEL_82;
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
          goto LABEL_80;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_79;
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
          goto LABEL_80;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
          if ( v10 < 0 )
            goto LABEL_80;
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
              goto LABEL_80;
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
          goto LABEL_80;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_80;
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
              goto LABEL_80;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_80;
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
              goto LABEL_80;
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
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_80;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_80;
    if ( *v7 != 61 )
      goto LABEL_79;
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
        goto LABEL_82;
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
LABEL_81:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_82:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180024d50  push    rbp
0x180024d52  push    rbx
0x180024d53  push    rsi
0x180024d54  push    rdi
0x180024d55  push    r12
0x180024d57  push    r13
0x180024d59  push    r14
0x180024d5b  push    r15
0x180024d5d  lea     rbp, [rsp-21C8h]
0x180024d65  mov     eax, 22C8h
0x180024d6a  call    _alloca_probe
0x180024d6f  sub     rsp, rax
0x180024d72  mov     rax, cs:__security_cookie
0x180024d79  xor     rax, rsp
0x180024d7c  mov     [rbp+2200h+var_50], rax
0x180024d83  mov     r15d, r9d
0x180024d86  mov     [rsp+2300h+var_22B0], r9d
0x180024d8b  mov     r13, r8
0x180024d8e  mov     rdi, rdx
0x180024d91  mov     rsi, rcx
0x180024d94  xor     r14d, r14d
0x180024d97  mov     [rsp+2300h+var_2290], r14
0x180024d9c  mov     [rsp+2300h+var_2288], r14
0x180024da1  mov     [rbp+2200h+var_2280], r14
0x180024da5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180024daa  test    eax, eax
0x180024dac  mov     ebx, eax
0x180024dae  js      loc_1800252DF
0x180024db4  xor     r12d, r12d
0x180024db7  cmp     word ptr [rdi], 7Dh ; '}'
0x180024dbb  jz      loc_1800252DF
0x180024dc1  lea     rdx, aDelete; "Delete"
0x180024dc8  mov     rcx, rdi; lpString1
0x180024dcb  call    cs:__imp_lstrcmpiW
0x180024dd1  mov     r14d, eax
0x180024dd4  lea     rdx, aForceremove; "ForceRemove"
0x180024ddb  mov     rcx, rdi; lpString1
0x180024dde  call    cs:__imp_lstrcmpiW
0x180024de4  test    eax, eax
0x180024de6  jz      short loc_180024DF1
0x180024de8  test    r14d, r14d
0x180024deb  jnz     loc_180024EA2
0x180024df1  mov     rdx, rdi; unsigned __int16 *
0x180024df4  mov     rcx, rsi; this
0x180024df7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180024dfc  mov     ebx, eax
0x180024dfe  test    eax, eax
0x180024e00  js      loc_1800252DF
0x180024e06  test    r15d, r15d
0x180024e09  jz      loc_180024EA2
0x180024e0f  mov     [rsp+2300h+hKey], r12
0x180024e14  mov     [rsp+2300h+var_22A0], r12
0x180024e19  mov     [rsp+2300h+var_2298], r12
0x180024e1e  mov     edx, 5Ch ; '\'; unsigned __int16
0x180024e23  mov     rcx, rdi; lpsz
0x180024e26  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180024e2b  test    rax, rax
0x180024e2e  jnz     loc_1800252D0
0x180024e34  mov     rdx, rdi; unsigned __int16 *
0x180024e37  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180024e3c  test    eax, eax
0x180024e3e  jz      short loc_180024E57
0x180024e40  mov     [rsp+2300h+hKey], r13
0x180024e45  mov     rdx, rdi; unsigned __int16 *
0x180024e48  lea     rcx, [rsp+2300h+hKey]; this
0x180024e4d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180024e52  mov     [rsp+2300h+hKey], r12
0x180024e57  test    r14d, r14d
0x180024e5a  jnz     short loc_180024E98
0x180024e5c  mov     rdx, rdi; unsigned __int16 *
0x180024e5f  mov     rcx, rsi; this
0x180024e62  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180024e67  mov     ebx, eax
0x180024e69  xor     r14d, r14d
0x180024e6c  test    eax, eax
0x180024e6e  js      loc_1800252CE
0x180024e74  mov     rdx, rdi; unsigned __int16 *
0x180024e77  mov     rcx, rsi; this
0x180024e7a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180024e7f  mov     ebx, eax
0x180024e81  test    eax, eax
0x180024e83  lea     rcx, [rsp+2300h+hKey]; this
0x180024e88  js      loc_18002531C
0x180024e8e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180024e93  jmp     loc_1800250BC
0x180024e98  lea     rcx, [rsp+2300h+hKey]; this
0x180024e9d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180024ea2  mov     r12d, 1
0x180024ea8  lea     rdx, aNoremove; "NoRemove"
0x180024eaf  mov     rcx, rdi; lpString1
0x180024eb2  call    cs:__imp_lstrcmpiW
0x180024eb8  xor     r14d, r14d
0x180024ebb  test    eax, eax
0x180024ebd  jnz     short loc_180024ED7
0x180024ebf  mov     r12d, r14d
0x180024ec2  mov     rdx, rdi; unsigned __int16 *
0x180024ec5  mov     rcx, rsi; this
0x180024ec8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180024ecd  mov     ebx, eax
0x180024ecf  test    eax, eax
0x180024ed1  js      loc_1800252DF
0x180024ed7  lea     rdx, aVal; "Val"
0x180024ede  mov     rcx, rdi; lpString1
0x180024ee1  call    cs:__imp_lstrcmpiW
0x180024ee7  test    eax, eax
0x180024ee9  jnz     loc_180024FD0
0x180024eef  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180024ef6  mov     rcx, rsi; this
0x180024ef9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180024efe  mov     ebx, eax
0x180024f00  test    eax, eax
0x180024f02  js      loc_1800252DF
0x180024f08  mov     rdx, rdi; unsigned __int16 *
0x180024f0b  mov     rcx, rsi; this
0x180024f0e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180024f13  mov     ebx, eax
0x180024f15  test    eax, eax
0x180024f17  js      loc_1800252DF
0x180024f1d  cmp     word ptr [rdi], 3Dh ; '='
0x180024f21  jnz     loc_1800252DA
0x180024f27  test    r15d, r15d
0x180024f2a  jz      short loc_180024F5E
0x180024f2c  mov     [rsp+2300h+var_22A0], r14
0x180024f31  mov     [rsp+2300h+var_2298], r14
0x180024f36  mov     [rsp+2300h+hKey], r13
0x180024f3b  mov     r9, rdi; unsigned __int16 *
0x180024f3e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180024f45  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180024f4a  mov     rcx, rsi; this
0x180024f4d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180024f52  mov     ebx, eax
0x180024f54  mov     [rsp+2300h+hKey], r14
0x180024f59  jmp     loc_180024E81
0x180024f5e  cmp     [rbp+2200h+arg_20], r14d
0x180024f65  jnz     short loc_180024FC0
0x180024f67  test    r12d, r12d
0x180024f6a  jz      short loc_180024FC0
0x180024f6c  mov     [rsp+2300h+hKey], r14
0x180024f71  mov     [rsp+2300h+var_22A0], r14
0x180024f76  mov     [rsp+2300h+var_2298], r14
0x180024f7b  mov     r9d, 20006h; unsigned int
0x180024f81  xor     r8d, r8d; lpSubKey
0x180024f84  mov     rdx, r13; hKey
0x180024f87  lea     rcx, [rsp+2300h+hKey]; this
0x180024f8c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180024f91  test    eax, eax
0x180024f93  jnz     loc_18002530E
0x180024f99  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180024fa0  mov     rcx, [rsp+2300h+hKey]; hKey
0x180024fa5  call    cs:__imp_RegDeleteValueW
0x180024fab  test    eax, 0FFFFFFFDh
0x180024fb0  jnz     loc_18002530E
0x180024fb6  lea     rcx, [rsp+2300h+hKey]; this
0x180024fbb  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180024fc0  mov     rdx, rdi; unsigned __int16 *
0x180024fc3  mov     rcx, rsi; this
0x180024fc6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180024fcb  jmp     loc_180024DAA
0x180024fd0  mov     edx, 5Ch ; '\'; unsigned __int16
0x180024fd5  mov     rcx, rdi; lpsz
0x180024fd8  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180024fdd  test    rax, rax
0x180024fe0  jnz     loc_1800252DA
0x180024fe6  test    r15d, r15d
0x180024fe9  jz      loc_18002510B
0x180024fef  mov     ebx, 2001Fh
0x180024ff4  mov     r9d, ebx; unsigned int
0x180024ff7  mov     r8, rdi; lpSubKey
0x180024ffa  mov     rdx, r13; hKey
0x180024ffd  lea     rcx, [rsp+2300h+var_2290]; this
0x180025002  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180025007  test    eax, eax
0x180025009  jz      short loc_180025084
0x18002500b  lea     r9d, [rbx-6]; unsigned int
0x18002500f  mov     r8, rdi; lpSubKey
0x180025012  mov     rdx, r13; hKey
0x180025015  lea     rcx, [rsp+2300h+var_2290]; this
0x18002501a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002501f  test    eax, eax
0x180025021  jz      short loc_180025084
0x180025023  mov     [rbp+2200h+dwDisposition], r14d
0x180025027  mov     [rbp+2200h+var_2270], r14
0x18002502b  lea     rax, [rbp+2200h+dwDisposition]
0x18002502f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180025034  lea     rax, [rbp+2200h+var_2270]
0x180025038  mov     [rsp+2300h+phkResult], rax; phkResult
0x18002503d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180025042  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180025046  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18002504b  xor     r9d, r9d; lpClass
0x18002504e  xor     r8d, r8d; Reserved
0x180025051  mov     rdx, rdi; lpSubKey
0x180025054  mov     rcx, r13; hKey
0x180025057  call    cs:__imp_RegCreateKeyExW
0x18002505d  mov     ecx, eax
0x18002505f  test    eax, eax
0x180025061  jnz     loc_18002520B
0x180025067  lea     rcx, [rsp+2300h+var_2290]; this
0x18002506c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180025071  mov     ecx, eax
0x180025073  mov     rax, [rbp+2200h+var_2270]
0x180025077  mov     [rsp+2300h+var_2290], rax
0x18002507c  test    ecx, ecx
0x18002507e  jnz     loc_18002520B
0x180025084  mov     rdx, rdi; unsigned __int16 *
0x180025087  mov     rcx, rsi; this
0x18002508a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002508f  mov     ebx, eax
0x180025091  test    eax, eax
0x180025093  js      loc_1800252DF
0x180025099  cmp     word ptr [rdi], 3Dh ; '='
0x18002509d  jnz     short loc_1800250BC
0x18002509f  mov     r9, rdi; unsigned __int16 *
0x1800250a2  xor     r8d, r8d; unsigned __int16 *
0x1800250a5  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x1800250aa  mov     rcx, rsi; this
0x1800250ad  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800250b2  mov     ebx, eax
0x1800250b4  test    eax, eax
0x1800250b6  js      loc_1800252DF
0x1800250bc  cmp     word ptr [rdi], 7Bh ; '{'
0x1800250c0  jnz     loc_180024DB4
0x1800250c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800250ca  inc     rax
0x1800250cd  cmp     [rdi+rax*2], r14w
0x1800250d2  jnz     short loc_1800250CA
0x1800250d4  cmp     rax, 1
0x1800250d8  jnz     loc_180024DB4
0x1800250de  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x1800250e3  mov     r9d, r15d; int
0x1800250e6  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800250eb  mov     rdx, rdi; unsigned __int16 *
0x1800250ee  mov     rcx, rsi; this
0x1800250f1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800250f6  mov     ebx, eax
0x1800250f8  test    eax, eax
0x1800250fa  js      loc_1800252DF
0x180025100  mov     rdx, rdi
0x180025103  mov     rcx, rsi
0x180025106  jmp     loc_180024DA5
0x18002510b  cmp     [rbp+2200h+arg_20], r14d
0x180025112  jnz     short loc_18002512F
0x180025114  mov     r9d, 20019h; unsigned int
0x18002511a  mov     r8, rdi; lpSubKey
0x18002511d  mov     rdx, r13; hKey
0x180025120  lea     rcx, [rsp+2300h+var_2290]; this
0x180025125  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002512a  mov     r14d, eax
0x18002512d  jmp     short loc_180025135
0x18002512f  mov     r14d, 2
0x180025135  mov     r15d, 1
0x18002513b  test    r14d, r14d
0x18002513e  cmovz   r15d, [rbp+2200h+arg_20]
0x180025146  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002514a  mov     r8, rdi
0x18002514d  mov     edx, 104h
0x180025152  lea     rcx, [rbp+2200h+var_2260]
0x180025156  call    cs:__imp__o_wcsncpy_s
0x18002515c  mov     ecx, eax; int
0x18002515e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180025163  mov     rdx, rdi; unsigned __int16 *
0x180025166  mov     rcx, rsi; this
0x180025169  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002516e  mov     ebx, eax
0x180025170  test    eax, eax
0x180025172  js      loc_1800252DF
0x180025178  mov     rdx, rdi; unsigned __int16 *
0x18002517b  mov     rcx, rsi; this
0x18002517e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180025183  mov     ebx, eax
0x180025185  xor     ecx, ecx
0x180025187  test    eax, eax
0x180025189  js      loc_1800252DF
0x18002518f  cmp     word ptr [rdi], 7Bh ; '{'
0x180025193  jnz     short loc_1800251E4
0x180025195  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025199  inc     rax
0x18002519c  cmp     [rdi+rax*2], cx
0x1800251a0  jnz     short loc_180025199
0x1800251a2  cmp     rax, 1
0x1800251a6  jnz     short loc_1800251E4
0x1800251a8  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x1800251ad  xor     r9d, r9d; int
0x1800251b0  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800251b5  mov     rdx, rdi; unsigned __int16 *
0x1800251b8  mov     rcx, rsi; this
0x1800251bb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800251c0  mov     ebx, eax
0x1800251c2  test    eax, eax
0x1800251c4  jns     short loc_1800251CF
0x1800251c6  test    r15d, r15d
0x1800251c9  jz      loc_1800252DF
0x1800251cf  mov     rdx, rdi; unsigned __int16 *
0x1800251d2  mov     rcx, rsi; this
0x1800251d5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800251da  mov     ebx, eax
0x1800251dc  test    eax, eax
0x1800251de  js      loc_1800252DF
0x1800251e4  cmp     r14d, 2
0x1800251e8  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
