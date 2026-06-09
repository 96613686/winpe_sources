# ForEachRegValue__lambda_e405e640301f66b5d70cf538f601e620_

- ea: `0x180027bfc`
- end: `0x180027e99`
- name: `ForEachRegValue__lambda_e405e640301f66b5d70cf538f601e620___`
- size: `669`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180028854`

## callees

- `0x18001b388`
- `0x18001b3a8`
- `0x180020260`
- `0x1800202e4`
- `0x1800210f0`
- `0x180027bfc`
- `0x180028a48`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180027df6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027e14`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027e23`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027df6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027e14`
- `msvcrt!??3@YAXPEAX@Z` at `0x180027e23`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027d5f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027d5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027c6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180027c6c`

## string_xrefs

- `0x180027e4e`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x180027e60`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x180027e75`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x180027e87`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ForEachRegValue__lambda_e405e640301f66b5d70cf538f601e620_(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  DWORD v5; // edx
  DWORD v6; // eax
  __int64 v7; // r8
  const char *v8; // r9
  DWORD v9; // esi
  WCHAR *v10; // r15
  BYTE *i; // rdi
  unsigned __int64 v12; // r14
  DWORD v13; // eax
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // r14d
  unsigned __int64 v18; // r8
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-99h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-59h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-55h] BYREF
  DWORD cValues; // [rsp+68h] [rbp-51h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-4Dh] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-49h] BYREF
  LPBYTE lpData[2]; // [rsp+78h] [rbp-41h] BYREF
  __int64 v27; // [rsp+88h] [rbp-31h]
  LPWSTR lpValueName[2]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-19h]
  void *v30[3]; // [rsp+A8h] [rbp-11h] BYREF
  unsigned __int64 v31; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  cValues = 0;
  cbMaxValueNameLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      (const char *)v4,
      lpcSubKeys);
  v5 = cbMaxValueNameLen;
  v6 = cbMaxValueNameLen + 1;
  v7 = 0xFFFFFFFFLL;
  if ( cbMaxValueNameLen + 1 >= cbMaxValueNameLen )
    v7 = v6;
  v8 = v6 < cbMaxValueNameLen ? (const char *)0x80070216LL : 0LL;
  cbMaxValueNameLen = v7;
  if ( v6 < v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      v8,
      lpcSubKeys);
  *(_OWORD *)lpValueName = 0;
  v29 = 0;
  if ( (_DWORD)v7 )
    std::vector<unsigned short>::_Reallocate(lpValueName, (unsigned int)v7);
  *(_OWORD *)lpData = 0;
  v27 = 0;
  std::vector<unsigned char>::_Reallocate(lpData, 260, v7, v8);
  cbData = 0;
  v9 = 0;
  v10 = lpValueName[0];
  for ( i = lpData[0]; v9 < cValues; ++v9 )
  {
    cchValueName = cbMaxValueNameLen;
    Type = 0;
    v12 = v27 - (_QWORD)i;
    v13 = v27 - (_DWORD)i;
    if ( (unsigned __int64)(v27 - (_QWORD)i) > 0xFFFFFFFF )
      v13 = -1;
    cbData = v13;
    if ( v12 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
        v12 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
        lpcSubKeys);
    v14 = RegEnumValueW(hKey, v9, v10, &cchValueName, 0, &Type, i, &cbData);
    if ( v14 == 234 )
    {
      if ( v12 < cbData )
      {
        std::vector<unsigned char>::_Reallocate(lpData, cbData, v15, v16);
        i = lpData[0];
      }
      --v9;
    }
    else
    {
      if ( v14 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
          (const char *)v14,
          lpcSubKeys);
      if ( Type == 4 && cbData == 4 )
      {
        v17 = *(_DWORD *)i;
        v31 = 7;
        v30[2] = 0;
        LOWORD(v30[0]) = 0;
        if ( *v10 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v10[v18] );
        }
        else
        {
          v18 = 0;
        }
        std::wstring::assign(v30, (char *)v10, v18);
        *(_DWORD *)std::map<std::wstring,unsigned long>::operator[](a2, v30) = v17;
        if ( v31 >= 8 )
          operator delete(v30[0]);
      }
    }
  }
  if ( i )
    operator delete(i);
  if ( v10 )
    operator delete(v10);
  return v9;
}

```

## disassembly

```asm
0x180027bfc  push    rbp
0x180027bfe  push    rbx
0x180027bff  push    rsi
0x180027c00  push    rdi
0x180027c01  push    r12
0x180027c03  push    r13
0x180027c05  push    r14
0x180027c07  push    r15
0x180027c09  lea     rbp, [rsp-1Fh]
0x180027c0e  sub     rsp, 0D8h
0x180027c15  mov     rax, cs:__security_cookie
0x180027c1c  xor     rax, rsp
0x180027c1f  mov     [rbp+57h+var_48], rax
0x180027c23  mov     rbx, rdx
0x180027c26  mov     r12, rcx
0x180027c29  xor     r13d, r13d
0x180027c2c  mov     [rbp+57h+cValues], r13d
0x180027c30  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x180027c34  mov     [rsp+110h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180027c39  mov     [rsp+110h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180027c3e  mov     [rsp+110h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180027c43  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180027c47  mov     [rsp+110h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180027c4c  lea     rax, [rbp+57h+cValues]
0x180027c50  mov     [rsp+110h+lpcValues], rax; lpcValues
0x180027c55  mov     [rsp+110h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180027c5a  mov     [rsp+110h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180027c5f  mov     [rsp+110h+lpcSubKeys], r13; int
0x180027c64  xor     r9d, r9d; lpReserved
0x180027c67  xor     r8d, r8d; lpcchClass
0x180027c6a  xor     edx, edx; lpClass
0x180027c6c  call    cs:__imp_RegQueryInfoKeyW
0x180027c72  mov     rcx, [rbp+5Fh]; this
0x180027c76  test    eax, eax
0x180027c78  jnz     loc_180027E72
0x180027c7e  mov     edx, [rbp+57h+cbMaxValueNameLen]
0x180027c81  lea     eax, [rdx+1]
0x180027c84  mov     r8d, 0FFFFFFFFh
0x180027c8a  cmp     eax, edx
0x180027c8c  cmovnb  r8d, eax
0x180027c90  sbb     r9d, r9d
0x180027c93  and     r9d, 80070216h; char *
0x180027c9a  mov     [rbp+57h+cbMaxValueNameLen], r8d
0x180027c9e  mov     rcx, [rbp+5Fh]; this
0x180027ca2  cmp     eax, edx
0x180027ca4  jb      loc_180027E87
0x180027caa  xorps   xmm0, xmm0
0x180027cad  movdqu  xmmword ptr [rbp+57h+lpValueName], xmm0
0x180027cb2  mov     [rbp+57h+var_70], r13
0x180027cb6  mov     edx, r8d
0x180027cb9  test    r8d, r8d
0x180027cbc  jz      short loc_180027CC7
0x180027cbe  lea     rcx, [rbp+57h+lpValueName]
0x180027cc2  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x180027cc7  xorps   xmm0, xmm0
0x180027cca  movdqu  xmmword ptr [rbp+57h+lpData], xmm0
0x180027ccf  mov     [rbp+57h+var_88], r13
0x180027cd3  mov     edx, 104h
0x180027cd8  lea     rcx, [rbp+57h+lpData]
0x180027cdc  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x180027ce1  mov     [rbp+57h+cbData], r13d
0x180027ce5  mov     esi, r13d
0x180027ce8  mov     r15, [rbp+57h+lpValueName]
0x180027cec  mov     rdi, [rbp+57h+lpData]
0x180027cf0  cmp     [rbp+57h+cValues], r13d
0x180027cf4  jbe     loc_180027E0C
0x180027cfa  mov     edx, 0FFFFFFFFh
0x180027cff  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180027d02  mov     [rbp+57h+cchValueName], eax
0x180027d05  mov     [rbp+57h+Type], r13d
0x180027d09  mov     r14, [rbp+57h+var_88]
0x180027d0d  sub     r14, rdi
0x180027d10  cmp     r14, rdx
0x180027d13  mov     eax, r14d
0x180027d16  jbe     short loc_180027D1A
0x180027d18  mov     eax, edx
0x180027d1a  cmp     rdx, r14
0x180027d1d  sbb     r9d, r9d
0x180027d20  and     r9d, 80070216h; char *
0x180027d27  mov     [rbp+57h+cbData], eax
0x180027d2a  mov     rcx, [rbp+5Fh]; this
0x180027d2e  cmp     r14, rdx
0x180027d31  ja      loc_180027E60
0x180027d37  lea     rax, [rbp+57h+cbData]
0x180027d3b  mov     [rsp+110h+lpcValues], rax; lpcbData
0x180027d40  mov     [rsp+110h+lpcbMaxClassLen], rdi; lpData
0x180027d45  lea     rax, [rbp+57h+Type]
0x180027d49  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpType
0x180027d4e  mov     [rsp+110h+lpcSubKeys], r13; unsigned int
0x180027d53  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180027d57  mov     r8, r15; lpValueName
0x180027d5a  mov     edx, esi; dwIndex
0x180027d5c  mov     rcx, r12; hKey
0x180027d5f  call    cs:__imp_RegEnumValueW
0x180027d65  cmp     eax, 0EAh
0x180027d6a  jnz     short loc_180027D8A
0x180027d6c  mov     edx, [rbp+57h+cbData]
0x180027d6f  cmp     r14, rdx
0x180027d72  jnb     short loc_180027D81
0x180027d74  lea     rcx, [rbp+57h+lpData]
0x180027d78  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x180027d7d  mov     rdi, [rbp+57h+lpData]
0x180027d81  mov     edx, 0FFFFFFFFh
0x180027d86  add     esi, edx
0x180027d88  jmp     short loc_180027E01
0x180027d8a  mov     rcx, [rbp+5Fh]; this
0x180027d8e  test    eax, eax
0x180027d90  jnz     loc_180027E4B
0x180027d96  cmp     [rbp+57h+Type], 4
0x180027d9a  jnz     short loc_180027DFC
0x180027d9c  cmp     [rbp+57h+cbData], 4
0x180027da0  jnz     short loc_180027DFC
0x180027da2  mov     r14d, [rdi]
0x180027da5  mov     [rbp+57h+var_50], 7
0x180027dad  mov     [rbp+57h+var_58], r13
0x180027db1  mov     word ptr [rbp+57h+var_68], r13w
0x180027db6  cmp     [r15], r13w
0x180027dba  jnz     short loc_180027DC1
0x180027dbc  mov     r8, r13
0x180027dbf  jmp     short loc_180027DCF
0x180027dc1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027dc5  inc     r8
0x180027dc8  cmp     [r15+r8*2], r13w
0x180027dcd  jnz     short loc_180027DC5
0x180027dcf  mov     rdx, r15; Src
0x180027dd2  lea     rcx, [rbp+57h+var_68]; void *
0x180027dd6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180027ddb  nop
0x180027ddc  lea     rdx, [rbp+57h+var_68]
0x180027de0  mov     rcx, rbx
0x180027de3  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring &&)
0x180027de8  mov     [rax], r14d
0x180027deb  cmp     [rbp+57h+var_50], 8
0x180027df0  jb      short loc_180027DFC
0x180027df2  mov     rcx, [rbp+57h+var_68]
0x180027df6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027dfc  mov     edx, 0FFFFFFFFh
0x180027e01  inc     esi
0x180027e03  cmp     esi, [rbp+57h+cValues]
0x180027e06  jb      loc_180027CFF
0x180027e0c  test    rdi, rdi
0x180027e0f  jz      short loc_180027E1B
0x180027e11  mov     rcx, rdi
0x180027e14  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027e1a  nop
0x180027e1b  test    r15, r15
0x180027e1e  jz      short loc_180027E29
0x180027e20  mov     rcx, r15
0x180027e23  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027e29  mov     eax, esi
0x180027e2b  mov     rcx, [rbp+57h+var_48]
0x180027e2f  xor     rcx, rsp; StackCookie
0x180027e32  call    __security_check_cookie
0x180027e37  add     rsp, 0D8h
0x180027e3e  pop     r15
0x180027e40  pop     r14
0x180027e42  pop     r13
0x180027e44  pop     r12
0x180027e46  pop     rdi
0x180027e47  pop     rsi
0x180027e48  pop     rbx
0x180027e49  pop     rbp
0x180027e4a  retn
0x180027e4b  mov     r9d, eax; char *
0x180027e4e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180027e55  mov     edx, 2Eh ; '.'; void *
0x180027e5a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180027e60  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180027e67  mov     edx, 1Fh; void *
0x180027e6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027e72  mov     r9d, eax; char *
0x180027e75  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180027e7c  mov     edx, 10h; void *
0x180027e81  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180027e87  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180027e8e  mov     edx, 13h; void *
0x180027e93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
