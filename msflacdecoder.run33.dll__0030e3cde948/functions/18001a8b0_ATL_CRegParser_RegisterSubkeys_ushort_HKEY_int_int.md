# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18001a8b0`
- end: `0x18001ae89`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18001a3cc`
- `0x18001a8b0`

## callees

- `0x180001e80`
- `0x180016aa0`
- `0x1800176cc`
- `0x180017ebc`
- `0x180017f2c`
- `0x180018384`
- `0x180018494`
- `0x180018d38`
- `0x180019640`
- `0x180019970`
- `0x180019ad0`
- `0x18001a2b8`
- `0x18001a8b0`
- `0x18001b534`
- `0x18001b604`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001acb6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001acb6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001abb7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001abb7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001ab05`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001ab05`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a92b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a93e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001aa12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001aa41`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a92b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a93e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001aa12`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001aa41`

## string_xrefs

- `0x18001a934`: `ForceRemove`
- `0x18001aa08`: `NoRemove`
- `0x18001a921`: `Delete`

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
0x18001a8b0  push    rbp
0x18001a8b2  push    rbx
0x18001a8b3  push    rsi
0x18001a8b4  push    rdi
0x18001a8b5  push    r12
0x18001a8b7  push    r13
0x18001a8b9  push    r14
0x18001a8bb  push    r15
0x18001a8bd  lea     rbp, [rsp-21C8h]
0x18001a8c5  mov     eax, 22C8h
0x18001a8ca  call    _alloca_probe
0x18001a8cf  sub     rsp, rax
0x18001a8d2  mov     rax, cs:__security_cookie
0x18001a8d9  xor     rax, rsp
0x18001a8dc  mov     [rbp+2200h+var_50], rax
0x18001a8e3  mov     r15d, r9d
0x18001a8e6  mov     [rsp+2300h+var_22B0], r9d
0x18001a8eb  mov     r13, r8
0x18001a8ee  mov     rdi, rdx
0x18001a8f1  mov     rsi, rcx
0x18001a8f4  xor     r14d, r14d
0x18001a8f7  mov     [rsp+2300h+var_2290], r14
0x18001a8fc  mov     [rsp+2300h+var_2288], r14
0x18001a901  mov     [rbp+2200h+var_2280], r14
0x18001a905  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a90a  test    eax, eax
0x18001a90c  mov     ebx, eax
0x18001a90e  js      loc_18001AE3D
0x18001a914  xor     r12d, r12d
0x18001a917  cmp     word ptr [rdi], 7Dh ; '}'
0x18001a91b  jz      loc_18001AE3D
0x18001a921  lea     rdx, String2; "Delete"
0x18001a928  mov     rcx, rdi; lpString1
0x18001a92b  call    cs:__imp_lstrcmpiW
0x18001a931  mov     r14d, eax
0x18001a934  lea     rdx, aForceremove; "ForceRemove"
0x18001a93b  mov     rcx, rdi; lpString1
0x18001a93e  call    cs:__imp_lstrcmpiW
0x18001a944  test    eax, eax
0x18001a946  jz      short loc_18001A951
0x18001a948  test    r14d, r14d
0x18001a94b  jnz     loc_18001AA02
0x18001a951  mov     rdx, rdi; unsigned __int16 *
0x18001a954  mov     rcx, rsi; this
0x18001a957  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a95c  mov     ebx, eax
0x18001a95e  test    eax, eax
0x18001a960  js      loc_18001AE3D
0x18001a966  test    r15d, r15d
0x18001a969  jz      loc_18001AA02
0x18001a96f  mov     [rsp+2300h+hKey], r12
0x18001a974  mov     [rsp+2300h+var_22A0], r12
0x18001a979  mov     [rsp+2300h+var_2298], r12
0x18001a97e  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001a983  mov     rcx, rdi; lpsz
0x18001a986  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001a98b  test    rax, rax
0x18001a98e  jnz     loc_18001AE2E
0x18001a994  mov     rdx, rdi; unsigned __int16 *
0x18001a997  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18001a99c  test    eax, eax
0x18001a99e  jz      short loc_18001A9B7
0x18001a9a0  mov     [rsp+2300h+hKey], r13
0x18001a9a5  mov     rdx, rdi; unsigned __int16 *
0x18001a9a8  lea     rcx, [rsp+2300h+hKey]; this
0x18001a9ad  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001a9b2  mov     [rsp+2300h+hKey], r12
0x18001a9b7  test    r14d, r14d
0x18001a9ba  jnz     short loc_18001A9F8
0x18001a9bc  mov     rdx, rdi; unsigned __int16 *
0x18001a9bf  mov     rcx, rsi; this
0x18001a9c2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a9c7  mov     ebx, eax
0x18001a9c9  xor     r14d, r14d
0x18001a9cc  test    eax, eax
0x18001a9ce  js      loc_18001AE75
0x18001a9d4  mov     rdx, rdi; unsigned __int16 *
0x18001a9d7  mov     rcx, rsi; this
0x18001a9da  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a9df  mov     ebx, eax
0x18001a9e1  test    eax, eax
0x18001a9e3  lea     rcx, [rsp+2300h+hKey]; this
0x18001a9e8  js      loc_18001AE7A
0x18001a9ee  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a9f3  jmp     loc_18001AC1C
0x18001a9f8  lea     rcx, [rsp+2300h+hKey]; this
0x18001a9fd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001aa02  mov     r12d, 1
0x18001aa08  lea     rdx, aNoremove; "NoRemove"
0x18001aa0f  mov     rcx, rdi; lpString1
0x18001aa12  call    cs:__imp_lstrcmpiW
0x18001aa18  xor     r14d, r14d
0x18001aa1b  test    eax, eax
0x18001aa1d  jnz     short loc_18001AA37
0x18001aa1f  mov     r12d, r14d
0x18001aa22  mov     rdx, rdi; unsigned __int16 *
0x18001aa25  mov     rcx, rsi; this
0x18001aa28  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001aa2d  mov     ebx, eax
0x18001aa2f  test    eax, eax
0x18001aa31  js      loc_18001AE3D
0x18001aa37  lea     rdx, aVal; "Val"
0x18001aa3e  mov     rcx, rdi; lpString1
0x18001aa41  call    cs:__imp_lstrcmpiW
0x18001aa47  test    eax, eax
0x18001aa49  jnz     loc_18001AB30
0x18001aa4f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001aa56  mov     rcx, rsi; this
0x18001aa59  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001aa5e  mov     ebx, eax
0x18001aa60  test    eax, eax
0x18001aa62  js      loc_18001AE3D
0x18001aa68  mov     rdx, rdi; unsigned __int16 *
0x18001aa6b  mov     rcx, rsi; this
0x18001aa6e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001aa73  mov     ebx, eax
0x18001aa75  test    eax, eax
0x18001aa77  js      loc_18001AE3D
0x18001aa7d  cmp     word ptr [rdi], 3Dh ; '='
0x18001aa81  jnz     loc_18001AE38
0x18001aa87  test    r15d, r15d
0x18001aa8a  jz      short loc_18001AABE
0x18001aa8c  mov     [rsp+2300h+var_22A0], r14
0x18001aa91  mov     [rsp+2300h+var_2298], r14
0x18001aa96  mov     [rsp+2300h+hKey], r13
0x18001aa9b  mov     r9, rdi; unsigned __int16 *
0x18001aa9e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001aaa5  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18001aaaa  mov     rcx, rsi; this
0x18001aaad  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001aab2  mov     ebx, eax
0x18001aab4  mov     [rsp+2300h+hKey], r14
0x18001aab9  jmp     loc_18001A9E1
0x18001aabe  cmp     [rbp+2200h+arg_20], r14d
0x18001aac5  jnz     short loc_18001AB20
0x18001aac7  test    r12d, r12d
0x18001aaca  jz      short loc_18001AB20
0x18001aacc  mov     [rsp+2300h+hKey], r14
0x18001aad1  mov     [rsp+2300h+var_22A0], r14
0x18001aad6  mov     [rsp+2300h+var_2298], r14
0x18001aadb  mov     r9d, 20006h; unsigned int
0x18001aae1  xor     r8d, r8d; lpSubKey
0x18001aae4  mov     rdx, r13; hKey
0x18001aae7  lea     rcx, [rsp+2300h+hKey]; this
0x18001aaec  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001aaf1  test    eax, eax
0x18001aaf3  jnz     loc_18001AE6C
0x18001aaf9  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18001ab00  mov     rcx, [rsp+2300h+hKey]; hKey
0x18001ab05  call    cs:__imp_RegDeleteValueW
0x18001ab0b  test    eax, 0FFFFFFFDh
0x18001ab10  jnz     loc_18001AE6C
0x18001ab16  lea     rcx, [rsp+2300h+hKey]; this
0x18001ab1b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001ab20  mov     rdx, rdi; unsigned __int16 *
0x18001ab23  mov     rcx, rsi; this
0x18001ab26  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001ab2b  jmp     loc_18001A90A
0x18001ab30  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001ab35  mov     rcx, rdi; lpsz
0x18001ab38  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001ab3d  test    rax, rax
0x18001ab40  jnz     loc_18001AE38
0x18001ab46  test    r15d, r15d
0x18001ab49  jz      loc_18001AC6B
0x18001ab4f  mov     ebx, 2001Fh
0x18001ab54  mov     r9d, ebx; unsigned int
0x18001ab57  mov     r8, rdi; lpSubKey
0x18001ab5a  mov     rdx, r13; hKey
0x18001ab5d  lea     rcx, [rsp+2300h+var_2290]; this
0x18001ab62  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001ab67  test    eax, eax
0x18001ab69  jz      short loc_18001ABE4
0x18001ab6b  lea     r9d, [rbx-6]; unsigned int
0x18001ab6f  mov     r8, rdi; lpSubKey
0x18001ab72  mov     rdx, r13; hKey
0x18001ab75  lea     rcx, [rsp+2300h+var_2290]; this
0x18001ab7a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001ab7f  test    eax, eax
0x18001ab81  jz      short loc_18001ABE4
0x18001ab83  mov     [rbp+2200h+dwDisposition], r14d
0x18001ab87  mov     [rbp+2200h+var_2270], r14
0x18001ab8b  lea     rax, [rbp+2200h+dwDisposition]
0x18001ab8f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18001ab94  lea     rax, [rbp+2200h+var_2270]
0x18001ab98  mov     [rsp+2300h+phkResult], rax; phkResult
0x18001ab9d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001aba2  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18001aba6  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x18001abab  xor     r9d, r9d; lpClass
0x18001abae  xor     r8d, r8d; Reserved
0x18001abb1  mov     rdx, rdi; lpSubKey
0x18001abb4  mov     rcx, r13; hKey
0x18001abb7  call    cs:__imp_RegCreateKeyExW
0x18001abbd  mov     ecx, eax
0x18001abbf  test    eax, eax
0x18001abc1  jnz     loc_18001AD6B
0x18001abc7  lea     rcx, [rsp+2300h+var_2290]; this
0x18001abcc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001abd1  mov     ecx, eax
0x18001abd3  mov     rax, [rbp+2200h+var_2270]
0x18001abd7  mov     [rsp+2300h+var_2290], rax
0x18001abdc  test    ecx, ecx
0x18001abde  jnz     loc_18001AD6B
0x18001abe4  mov     rdx, rdi; unsigned __int16 *
0x18001abe7  mov     rcx, rsi; this
0x18001abea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001abef  mov     ebx, eax
0x18001abf1  test    eax, eax
0x18001abf3  js      loc_18001AE3D
0x18001abf9  cmp     word ptr [rdi], 3Dh ; '='
0x18001abfd  jnz     short loc_18001AC1C
0x18001abff  mov     r9, rdi; unsigned __int16 *
0x18001ac02  xor     r8d, r8d; unsigned __int16 *
0x18001ac05  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18001ac0a  mov     rcx, rsi; this
0x18001ac0d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001ac12  mov     ebx, eax
0x18001ac14  test    eax, eax
0x18001ac16  js      loc_18001AE3D
0x18001ac1c  cmp     word ptr [rdi], 7Bh ; '{'
0x18001ac20  jnz     loc_18001A914
0x18001ac26  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ac2a  inc     rax
0x18001ac2d  cmp     [rdi+rax*2], r14w
0x18001ac32  jnz     short loc_18001AC2A
0x18001ac34  cmp     rax, 1
0x18001ac38  jnz     loc_18001A914
0x18001ac3e  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x18001ac43  mov     r9d, r15d; int
0x18001ac46  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001ac4b  mov     rdx, rdi; unsigned __int16 *
0x18001ac4e  mov     rcx, rsi; this
0x18001ac51  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001ac56  mov     ebx, eax
0x18001ac58  test    eax, eax
0x18001ac5a  js      loc_18001AE3D
0x18001ac60  mov     rdx, rdi
0x18001ac63  mov     rcx, rsi
0x18001ac66  jmp     loc_18001A905
0x18001ac6b  cmp     [rbp+2200h+arg_20], r14d
0x18001ac72  jnz     short loc_18001AC8F
0x18001ac74  mov     r9d, 20019h; unsigned int
0x18001ac7a  mov     r8, rdi; lpSubKey
0x18001ac7d  mov     rdx, r13; hKey
0x18001ac80  lea     rcx, [rsp+2300h+var_2290]; this
0x18001ac85  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001ac8a  mov     r14d, eax
0x18001ac8d  jmp     short loc_18001AC95
0x18001ac8f  mov     r14d, 2
0x18001ac95  mov     r15d, 1
0x18001ac9b  test    r14d, r14d
0x18001ac9e  cmovz   r15d, [rbp+2200h+arg_20]
0x18001aca6  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001acaa  mov     r8, rdi
0x18001acad  mov     edx, 104h
0x18001acb2  lea     rcx, [rbp+2200h+var_2260]
0x18001acb6  call    cs:__imp__o_wcsncpy_s
0x18001acbc  mov     ecx, eax; int
0x18001acbe  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001acc3  mov     rdx, rdi; unsigned __int16 *
0x18001acc6  mov     rcx, rsi; this
0x18001acc9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001acce  mov     ebx, eax
0x18001acd0  test    eax, eax
0x18001acd2  js      loc_18001AE3D
0x18001acd8  mov     rdx, rdi; unsigned __int16 *
0x18001acdb  mov     rcx, rsi; this
0x18001acde  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001ace3  mov     ebx, eax
0x18001ace5  xor     ecx, ecx
0x18001ace7  test    eax, eax
0x18001ace9  js      loc_18001AE3D
0x18001acef  cmp     word ptr [rdi], 7Bh ; '{'
0x18001acf3  jnz     short loc_18001AD44
0x18001acf5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001acf9  inc     rax
0x18001acfc  cmp     [rdi+rax*2], cx
0x18001ad00  jnz     short loc_18001ACF9
0x18001ad02  cmp     rax, 1
0x18001ad06  jnz     short loc_18001AD44
0x18001ad08  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x18001ad0d  xor     r9d, r9d; int
0x18001ad10  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001ad15  mov     rdx, rdi; unsigned __int16 *
0x18001ad18  mov     rcx, rsi; this
0x18001ad1b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001ad20  mov     ebx, eax
0x18001ad22  test    eax, eax
0x18001ad24  jns     short loc_18001AD2F
0x18001ad26  test    r15d, r15d
0x18001ad29  jz      loc_18001AE3D
0x18001ad2f  mov     rdx, rdi; unsigned __int16 *
0x18001ad32  mov     rcx, rsi; this
0x18001ad35  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001ad3a  mov     ebx, eax
0x18001ad3c  test    eax, eax
0x18001ad3e  js      loc_18001AE3D
0x18001ad44  cmp     r14d, 2
0x18001ad48  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
