# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180110bf8`
- end: `0x1801111f5`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1533`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1801108ec`
- `0x180110bf8`

## callees

- `0x1801099f0`
- `0x18010cc38`
- `0x18010d374`
- `0x18010d3e4`
- `0x18010d42c`
- `0x18010d544`
- `0x18010f0e8`
- `0x18010fb44`
- `0x18010fd0c`
- `0x18010fe6c`
- `0x1801107d8`
- `0x180110bf8`
- `0x180111d74`
- `0x180111e44`
- `0x180172350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180111012`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180111012`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180110f13`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180110f13`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180110e53`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180110e53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180110c6b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180110c7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180110d62`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180110d91`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180110c6b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180110c7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180110d62`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180110d91`

## string_xrefs

- `0x180110c71`: `ForceRemove`
- `0x180110d52`: `NoRemove`
- `0x180110c61`: `Delete`

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
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // r14d
  int v11; // ebx
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ebx
  __int64 v17; // rax
  unsigned int v18; // r14d
  int v19; // r15d
  int v20; // eax
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r15d
  unsigned int v25; // r14d
  unsigned int v27; // ecx
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+68h] [rbp-98h]
  HKEY v33[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v36[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset(v33, 0, sizeof(v33));
  v5 = a4;
  v7 = a2;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_31:
    v11 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v10 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v10 )
        {
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( v5 )
          {
            hKey = 0;
            v31 = 0;
            v32 = 0;
            if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
              v11 = -2147352567;
              goto LABEL_79;
            }
            if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
            {
              hKey = a3;
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
              hKey = 0;
            }
            if ( !v10 )
            {
              v11 = ATL::CRegParser::NextToken(i, v7);
              if ( v11 < 0 )
                goto LABEL_81;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_14:
              v11 = v13;
              if ( v13 < 0 )
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              goto LABEL_42;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v11 = ATL::CRegParser::NextToken(i, ValueName);
          if ( v11 < 0 )
            goto LABEL_79;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( *v7 != 61 )
            goto LABEL_78;
          if ( !v5 )
          {
            if ( a5 || !v14 )
              goto LABEL_30;
            hKey = 0;
            v31 = 0;
            v32 = 0;
            v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(hKey, ValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_30:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_31;
              }
            }
LABEL_80:
            v11 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_79;
          }
          v31 = 0;
          v32 = 0;
          hKey = a3;
          v13 = ATL::CRegParser::AddValue(i, &hKey, ValueName, v7);
          hKey = 0;
          goto LABEL_14;
        }
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          goto LABEL_78;
        if ( v5 )
          break;
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v36, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v20);
        v11 = ATL::CRegParser::NextToken(i, v7);
        if ( v11 < 0 )
          goto LABEL_79;
        v21 = ATL::CRegParser::SkipAssignment(i, v7);
        v22 = 0;
        v11 = v21;
        if ( v21 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          if ( v23 == 1 )
          {
            v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v33[0], 0, v19);
            if ( v11 < 0 && !v19 )
              goto LABEL_79;
            v11 = ATL::CRegParser::NextToken(i, v7);
            if ( v11 < 0 )
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
              v11 = ATL::AtlHresultFromWin32(v18);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v33[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, v36) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v33, v36);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v33[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v33);
            if ( v25 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v33);
              v27 = v25;
              return ATL::AtlHresultFromWin32(v27);
            }
            if ( v14 && !HasSubKeys )
            {
              v31 = 0;
              v32 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v36);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            v5 = a4;
          }
        }
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v16 || (v16 = ATL::CRegKey::Close((ATL::CRegKey *)v33), v33[0] = phkResult, v16) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v33);
            v27 = v16;
            return ATL::AtlHresultFromWin32(v27);
          }
        }
      }
      v11 = ATL::CRegParser::NextToken(i, v7);
      if ( v11 < 0 )
        goto LABEL_79;
      if ( *v7 == 61 )
      {
        v11 = ATL::CRegParser::AddValue(i, v33, 0, v7);
        if ( v11 < 0 )
          goto LABEL_79;
      }
LABEL_42:
      if ( *v7 == 123 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v7[v17] );
        if ( v17 == 1 )
          break;
      }
    }
    v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v33[0], v5, 0);
    if ( v11 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v33);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180110bf8  push    rbp
0x180110bfa  push    rbx
0x180110bfb  push    rsi
0x180110bfc  push    rdi
0x180110bfd  push    r12
0x180110bff  push    r13
0x180110c01  push    r14
0x180110c03  push    r15
0x180110c05  lea     rbp, [rsp-21C8h]
0x180110c0d  mov     eax, 22C8h
0x180110c12  call    _alloca_probe
0x180110c17  sub     rsp, rax
0x180110c1a  mov     rax, cs:__security_cookie
0x180110c21  xor     rax, rsp
0x180110c24  mov     [rbp+2200h+var_50], rax
0x180110c2b  xor     r14d, r14d
0x180110c2e  mov     [rsp+2300h+var_22B0], r9d
0x180110c33  mov     [rsp+2300h+var_2290], r14
0x180110c38  mov     r15d, r9d
0x180110c3b  mov     [rsp+2300h+var_2288], r14
0x180110c40  mov     r13, r8
0x180110c43  mov     [rbp+2200h+var_2280], r14
0x180110c47  mov     rdi, rdx
0x180110c4a  mov     rsi, rcx
0x180110c4d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180110c52  jmp     loc_180110E79
0x180110c57  cmp     word ptr [rdi], 7Dh ; '}'
0x180110c5b  jz      loc_18011118F
0x180110c61  lea     rdx, aDelete; "Delete"
0x180110c68  mov     rcx, rdi; lpString1
0x180110c6b  call    cs:__imp_lstrcmpiW
0x180110c71  lea     rdx, aForceremove; "ForceRemove"
0x180110c78  mov     rcx, rdi; lpString1
0x180110c7b  mov     r14d, eax
0x180110c7e  call    cs:__imp_lstrcmpiW
0x180110c84  test    eax, eax
0x180110c86  jz      short loc_180110C91
0x180110c88  test    r14d, r14d
0x180110c8b  jnz     loc_180110D52
0x180110c91  mov     rdx, rdi; unsigned __int16 *
0x180110c94  mov     rcx, rsi; this
0x180110c97  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180110c9c  mov     ebx, eax
0x180110c9e  test    eax, eax
0x180110ca0  js      loc_18011118F
0x180110ca6  test    r15d, r15d
0x180110ca9  jz      loc_180110D52
0x180110caf  mov     edx, 5Ch ; '\'; unsigned __int16
0x180110cb4  mov     [rsp+2300h+hKey], 0
0x180110cbd  mov     rcx, rdi; lpsz
0x180110cc0  mov     [rsp+2300h+var_22A0], 0
0x180110cc9  mov     [rsp+2300h+var_2298], 0
0x180110cd2  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180110cd7  test    rax, rax
0x180110cda  jnz     loc_180111180
0x180110ce0  mov     rdx, rdi; unsigned __int16 *
0x180110ce3  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180110ce8  test    eax, eax
0x180110cea  jz      short loc_180110D07
0x180110cec  mov     rdx, rdi; unsigned __int16 *
0x180110cef  mov     [rsp+2300h+hKey], r13
0x180110cf4  lea     rcx, [rsp+2300h+hKey]; this
0x180110cf9  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180110cfe  mov     [rsp+2300h+hKey], 0
0x180110d07  test    r14d, r14d
0x180110d0a  jnz     short loc_180110D48
0x180110d0c  mov     rdx, rdi; unsigned __int16 *
0x180110d0f  mov     rcx, rsi; this
0x180110d12  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180110d17  xor     r14d, r14d
0x180110d1a  mov     ebx, eax
0x180110d1c  test    eax, eax
0x180110d1e  js      loc_1801111C7
0x180110d24  mov     rdx, rdi; unsigned __int16 *
0x180110d27  mov     rcx, rsi; this
0x180110d2a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180110d2f  lea     rcx, [rsp+2300h+hKey]; this
0x180110d34  mov     ebx, eax
0x180110d36  test    eax, eax
0x180110d38  js      loc_1801111CC
0x180110d3e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180110d43  jmp     loc_180110F78
0x180110d48  lea     rcx, [rsp+2300h+hKey]; this
0x180110d4d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180110d52  lea     rdx, aNoremove; "NoRemove"
0x180110d59  mov     rcx, rdi; lpString1
0x180110d5c  mov     r12d, 1
0x180110d62  call    cs:__imp_lstrcmpiW
0x180110d68  xor     r14d, r14d
0x180110d6b  test    eax, eax
0x180110d6d  jnz     short loc_180110D87
0x180110d6f  mov     rdx, rdi; unsigned __int16 *
0x180110d72  mov     rcx, rsi; this
0x180110d75  mov     r12d, r14d
0x180110d78  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180110d7d  mov     ebx, eax
0x180110d7f  test    eax, eax
0x180110d81  js      loc_18011118F
0x180110d87  lea     rdx, aVal; "Val"
0x180110d8e  mov     rcx, rdi; lpString1
0x180110d91  call    cs:__imp_lstrcmpiW
0x180110d97  test    eax, eax
0x180110d99  jnz     loc_180110E88
0x180110d9f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180110da6  mov     rcx, rsi; this
0x180110da9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180110dae  mov     ebx, eax
0x180110db0  test    eax, eax
0x180110db2  js      loc_18011118F
0x180110db8  mov     rdx, rdi; unsigned __int16 *
0x180110dbb  mov     rcx, rsi; this
0x180110dbe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180110dc3  mov     ebx, eax
0x180110dc5  test    eax, eax
0x180110dc7  js      loc_18011118F
0x180110dcd  cmp     word ptr [rdi], 3Dh ; '='
0x180110dd1  jnz     loc_18011118A
0x180110dd7  test    r15d, r15d
0x180110dda  jz      short loc_180110E0C
0x180110ddc  mov     r9, rdi; unsigned __int16 *
0x180110ddf  mov     [rsp+2300h+var_22A0], r14
0x180110de4  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180110deb  mov     [rsp+2300h+var_2298], r14
0x180110df0  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180110df5  mov     [rsp+2300h+hKey], r13
0x180110dfa  mov     rcx, rsi; this
0x180110dfd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180110e02  mov     [rsp+2300h+hKey], r14
0x180110e07  jmp     loc_180110D2F
0x180110e0c  cmp     [rbp+2200h+arg_20], r14d
0x180110e13  jnz     short loc_180110E6E
0x180110e15  test    r12d, r12d
0x180110e18  jz      short loc_180110E6E
0x180110e1a  mov     r9d, 20006h; unsigned int
0x180110e20  mov     [rsp+2300h+hKey], r14
0x180110e25  xor     r8d, r8d; lpSubKey
0x180110e28  mov     [rsp+2300h+var_22A0], r14
0x180110e2d  mov     rdx, r13; hKey
0x180110e30  mov     [rsp+2300h+var_2298], r14
0x180110e35  lea     rcx, [rsp+2300h+hKey]; this
0x180110e3a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180110e3f  test    eax, eax
0x180110e41  jnz     loc_1801111BE
0x180110e47  mov     rcx, [rsp+2300h+hKey]; hKey
0x180110e4c  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180110e53  call    cs:__imp_RegDeleteValueW
0x180110e59  test    eax, 0FFFFFFFDh
0x180110e5e  jnz     loc_1801111BE
0x180110e64  lea     rcx, [rsp+2300h+hKey]; this
0x180110e69  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180110e6e  mov     rdx, rdi; unsigned __int16 *
0x180110e71  mov     rcx, rsi; this
0x180110e74  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180110e79  mov     ebx, eax
0x180110e7b  test    eax, eax
0x180110e7d  jns     loc_180110C57
0x180110e83  jmp     loc_18011118F
0x180110e88  mov     edx, 5Ch ; '\'; unsigned __int16
0x180110e8d  mov     rcx, rdi; lpsz
0x180110e90  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180110e95  test    rax, rax
0x180110e98  jnz     loc_18011118A
0x180110e9e  test    r15d, r15d
0x180110ea1  jz      loc_180110FC7
0x180110ea7  mov     r9d, 2001Fh; unsigned int
0x180110ead  lea     rcx, [rsp+2300h+var_2290]; this
0x180110eb2  mov     r8, rdi; lpSubKey
0x180110eb5  mov     rdx, r13; hKey
0x180110eb8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180110ebd  test    eax, eax
0x180110ebf  jz      short loc_180110F40
0x180110ec1  mov     r9d, 20019h; unsigned int
0x180110ec7  lea     rcx, [rsp+2300h+var_2290]; this
0x180110ecc  mov     r8, rdi; lpSubKey
0x180110ecf  mov     rdx, r13; hKey
0x180110ed2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180110ed7  test    eax, eax
0x180110ed9  jz      short loc_180110F40
0x180110edb  lea     rax, [rbp+2200h+dwDisposition]
0x180110edf  mov     [rbp+2200h+dwDisposition], r14d
0x180110ee3  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180110ee8  xor     r9d, r9d; lpClass
0x180110eeb  lea     rax, [rbp+2200h+var_2270]
0x180110eef  mov     [rbp+2200h+var_2270], r14
0x180110ef3  mov     [rsp+2300h+phkResult], rax; phkResult
0x180110ef8  xor     r8d, r8d; Reserved
0x180110efb  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180110f00  mov     rdx, rdi; lpSubKey
0x180110f03  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x180110f0b  mov     rcx, r13; hKey
0x180110f0e  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x180110f13  call    cs:__imp_RegCreateKeyExW
0x180110f19  mov     ebx, eax
0x180110f1b  test    eax, eax
0x180110f1d  jnz     loc_1801111D3
0x180110f23  lea     rcx, [rsp+2300h+var_2290]; this
0x180110f28  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180110f2d  mov     ebx, eax
0x180110f2f  mov     rax, [rbp+2200h+var_2270]
0x180110f33  mov     [rsp+2300h+var_2290], rax
0x180110f38  test    ebx, ebx
0x180110f3a  jnz     loc_1801111D3
0x180110f40  mov     rdx, rdi; unsigned __int16 *
0x180110f43  mov     rcx, rsi; this
0x180110f46  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180110f4b  mov     ebx, eax
0x180110f4d  test    eax, eax
0x180110f4f  js      loc_18011118F
0x180110f55  cmp     word ptr [rdi], 3Dh ; '='
0x180110f59  jnz     short loc_180110F78
0x180110f5b  mov     r9, rdi; unsigned __int16 *
0x180110f5e  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180110f63  xor     r8d, r8d; unsigned __int16 *
0x180110f66  mov     rcx, rsi; this
0x180110f69  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180110f6e  mov     ebx, eax
0x180110f70  test    eax, eax
0x180110f72  js      loc_18011118F
0x180110f78  cmp     word ptr [rdi], 7Bh ; '{'
0x180110f7c  jnz     loc_180110C57
0x180110f82  or      rax, 0FFFFFFFFFFFFFFFFh
0x180110f86  inc     rax
0x180110f89  cmp     [rdi+rax*2], r14w
0x180110f8e  jnz     short loc_180110F86
0x180110f90  cmp     rax, 1
0x180110f94  jnz     loc_180110C57
0x180110f9a  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180110f9f  mov     r9d, r15d; int
0x180110fa2  mov     rdx, rdi; unsigned __int16 *
0x180110fa5  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180110faa  mov     rcx, rsi; this
0x180110fad  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180110fb2  mov     ebx, eax
0x180110fb4  test    eax, eax
0x180110fb6  js      loc_18011118F
0x180110fbc  mov     rdx, rdi
0x180110fbf  mov     rcx, rsi
0x180110fc2  jmp     loc_180110C4D
0x180110fc7  cmp     [rbp+2200h+arg_20], r14d
0x180110fce  jnz     short loc_180110FEB
0x180110fd0  mov     r9d, 20019h; unsigned int
0x180110fd6  lea     rcx, [rsp+2300h+var_2290]; this
0x180110fdb  mov     r8, rdi; lpSubKey
0x180110fde  mov     rdx, r13; hKey
0x180110fe1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180110fe6  mov     r14d, eax
0x180110fe9  jmp     short loc_180110FF1
0x180110feb  mov     r14d, 2
0x180110ff1  test    r14d, r14d
0x180110ff4  lea     rcx, [rbp+2200h+var_2260]
0x180110ff8  mov     r15d, 1
0x180110ffe  mov     r8, rdi
0x180111001  cmovz   r15d, [rbp+2200h+arg_20]
0x180111009  mov     edx, 104h
0x18011100e  or      r9, 0FFFFFFFFFFFFFFFFh
0x180111012  call    cs:__imp__o_wcsncpy_s
0x180111018  mov     ecx, eax; int
0x18011101a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18011101f  mov     rdx, rdi; unsigned __int16 *
0x180111022  mov     rcx, rsi; this
0x180111025  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18011102a  mov     ebx, eax
0x18011102c  test    eax, eax
0x18011102e  js      loc_18011118F
0x180111034  mov     rdx, rdi; unsigned __int16 *
0x180111037  mov     rcx, rsi; this
0x18011103a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18011103f  xor     ecx, ecx
0x180111041  mov     ebx, eax
0x180111043  test    eax, eax
0x180111045  js      loc_18011118F
0x18011104b  cmp     word ptr [rdi], 7Bh ; '{'
0x18011104f  jnz     short loc_1801110A0
0x180111051  or      rax, 0FFFFFFFFFFFFFFFFh
0x180111055  inc     rax
0x180111058  cmp     [rdi+rax*2], cx
0x18011105c  jnz     short loc_180111055
0x18011105e  cmp     rax, 1
0x180111062  jnz     short loc_1801110A0
0x180111064  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180111069  xor     r9d, r9d; int
0x18011106c  mov     rdx, rdi; unsigned __int16 *
0x18011106f  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180111074  mov     rcx, rsi; this
0x180111077  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18011107c  mov     ebx, eax
0x18011107e  test    eax, eax
0x180111080  jns     short loc_18011108B
0x180111082  test    r15d, r15d
0x180111085  jz      loc_18011118F
0x18011108b  mov     rdx, rdi; unsigned __int16 *
0x18011108e  mov     rcx, rsi; this
0x180111091  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180111096  mov     ebx, eax
0x180111098  test    eax, eax
0x18011109a  js      loc_18011118F
0x1801110a0  mov     r15d, [rsp+2300h+var_22B0]
0x1801110a5  cmp     r14d, 2
0x1801110a9  jz      loc_180110C57
0x1801110af  test    r14d, r14d
  ... truncated ...
```
