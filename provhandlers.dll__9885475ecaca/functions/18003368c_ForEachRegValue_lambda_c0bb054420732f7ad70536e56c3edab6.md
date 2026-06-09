# ForEachRegValue__lambda_c0bb054420732f7ad70536e56c3edab6_

- ea: `0x18003368c`
- end: `0x1800338fe`
- name: `ForEachRegValue__lambda_c0bb054420732f7ad70536e56c3edab6___`
- size: `626`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18003303c`

## callees

- `0x18000e308`
- `0x180012390`
- `0x180012d04`
- `0x180012d80`
- `0x1800248c4`
- `0x180032f9c`
- `0x18003368c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003387e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003388d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003387e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003388d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800336f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800336f1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800337e3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800337e3`

## string_xrefs

- `0x1800338b3`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x1800338c5`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x1800338da`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x1800338ec`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ForEachRegValue__lambda_c0bb054420732f7ad70536e56c3edab6_(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  DWORD v5; // edx
  DWORD v6; // eax
  __int64 v7; // r8
  const char *v8; // r9
  DWORD v9; // edi
  WCHAR *v10; // r15
  BYTE *i; // r14
  unsigned __int64 v12; // rsi
  DWORD v13; // eax
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  _QWORD *v17; // rcx
  unsigned __int64 v18; // r8
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-59h]
  DWORD cValues; // [rsp+60h] [rbp-19h] BYREF
  DWORD Type; // [rsp+64h] [rbp-15h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-11h] BYREF
  LPBYTE lpData[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v25; // [rsp+80h] [rbp+7h]
  LPWSTR lpValueName[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DWORD cbMaxValueNameLen; // [rsp+F0h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+F8h] [rbp+7Fh] BYREF

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
  v27 = 0;
  if ( (_DWORD)v7 )
    std::vector<unsigned short>::_Reallocate((__int64)lpValueName, (unsigned int)v7);
  *(_OWORD *)lpData = 0;
  v25 = 0;
  std::vector<unsigned char>::_Reallocate(lpData, 260, v7, v8);
  cbData = 0;
  v9 = 0;
  v10 = lpValueName[0];
  for ( i = lpData[0]; v9 < cValues; ++v9 )
  {
    cchValueName = cbMaxValueNameLen;
    Type = 0;
    v12 = v25 - (_QWORD)i;
    v13 = v25 - (_DWORD)i;
    if ( (unsigned __int64)(v25 - (_QWORD)i) > 0xFFFFFFFF )
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
      if ( *(_QWORD *)(a2 + 8) == *(_QWORD *)(a2 + 16) )
        std::vector<std::wstring>::_Reserve(a2);
      v17 = *(_QWORD **)(a2 + 8);
      v17[3] = 7;
      v17[2] = 0;
      *(_WORD *)v17 = 0;
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
      std::wstring::assign(v17, (char *)v10, v18);
      *(_QWORD *)(a2 + 8) += 32LL;
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
0x18003368c  mov     [rsp-8+arg_0], rbx
0x180033691  push    rbp
0x180033692  push    rsi
0x180033693  push    rdi
0x180033694  push    r12
0x180033696  push    r13
0x180033698  push    r14
0x18003369a  push    r15
0x18003369c  lea     rbp, [rsp-27h]
0x1800336a1  sub     rsp, 0A0h
0x1800336a8  mov     rbx, rdx
0x1800336ab  mov     r12, rcx
0x1800336ae  xor     r13d, r13d
0x1800336b1  mov     [rbp+57h+cValues], r13d
0x1800336b5  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x1800336b9  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800336be  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800336c3  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800336c8  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800336cc  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800336d1  lea     rax, [rbp+57h+cValues]
0x1800336d5  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x1800336da  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800336df  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1800336e4  mov     [rsp+0D0h+lpcSubKeys], r13; int
0x1800336e9  xor     r9d, r9d; lpReserved
0x1800336ec  xor     r8d, r8d; lpcchClass
0x1800336ef  xor     edx, edx; lpClass
0x1800336f1  call    cs:__imp_RegQueryInfoKeyW
0x1800336f7  mov     rcx, [rbp+5Fh]; this
0x1800336fb  test    eax, eax
0x1800336fd  jnz     loc_1800338D7
0x180033703  mov     edx, [rbp+57h+cbMaxValueNameLen]
0x180033706  lea     eax, [rdx+1]
0x180033709  mov     r8d, 0FFFFFFFFh
0x18003370f  cmp     eax, edx
0x180033711  cmovnb  r8d, eax
0x180033715  sbb     r9d, r9d
0x180033718  and     r9d, 80070216h; char *
0x18003371f  mov     [rbp+57h+cbMaxValueNameLen], r8d
0x180033723  mov     rcx, [rbp+5Fh]; this
0x180033727  cmp     eax, edx
0x180033729  jb      loc_1800338EC
0x18003372f  xorps   xmm0, xmm0
0x180033732  movdqu  xmmword ptr [rbp+57h+lpValueName], xmm0
0x180033737  mov     [rbp+57h+var_38], r13
0x18003373b  mov     edx, r8d
0x18003373e  test    r8d, r8d
0x180033741  jz      short loc_18003374C
0x180033743  lea     rcx, [rbp+57h+lpValueName]
0x180033747  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18003374c  xorps   xmm0, xmm0
0x18003374f  movdqu  xmmword ptr [rbp+57h+lpData], xmm0
0x180033754  mov     [rbp+57h+var_50], r13
0x180033758  mov     edx, 104h
0x18003375d  lea     rcx, [rbp+57h+lpData]
0x180033761  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x180033766  mov     [rbp+57h+cbData], r13d
0x18003376a  mov     edi, r13d
0x18003376d  mov     r15, [rbp+57h+lpValueName]
0x180033771  mov     r14, [rbp+57h+lpData]
0x180033775  cmp     [rbp+57h+cValues], r13d
0x180033779  jbe     loc_180033876
0x18003377f  mov     edx, 0FFFFFFFFh
0x180033784  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x180033787  mov     [rbp+57h+cchValueName], eax
0x18003378a  mov     [rbp+57h+Type], r13d
0x18003378e  mov     rsi, [rbp+57h+var_50]
0x180033792  sub     rsi, r14
0x180033795  cmp     rsi, rdx
0x180033798  mov     eax, esi
0x18003379a  jbe     short loc_18003379E
0x18003379c  mov     eax, edx
0x18003379e  cmp     rdx, rsi
0x1800337a1  sbb     r9d, r9d
0x1800337a4  and     r9d, 80070216h; char *
0x1800337ab  mov     [rbp+57h+cbData], eax
0x1800337ae  mov     rcx, [rbp+5Fh]; this
0x1800337b2  cmp     rsi, rdx
0x1800337b5  ja      loc_1800338C5
0x1800337bb  lea     rax, [rbp+57h+cbData]
0x1800337bf  mov     [rsp+0D0h+lpcValues], rax; lpcbData
0x1800337c4  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpData
0x1800337c9  lea     rax, [rbp+57h+Type]
0x1800337cd  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpType
0x1800337d2  mov     [rsp+0D0h+lpcSubKeys], r13; unsigned int
0x1800337d7  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800337db  mov     r8, r15; lpValueName
0x1800337de  mov     edx, edi; dwIndex
0x1800337e0  mov     rcx, r12; hKey
0x1800337e3  call    cs:__imp_RegEnumValueW
0x1800337e9  cmp     eax, 0EAh
0x1800337ee  jnz     short loc_18003380E
0x1800337f0  mov     edx, [rbp+57h+cbData]
0x1800337f3  cmp     rsi, rdx
0x1800337f6  jnb     short loc_180033805
0x1800337f8  lea     rcx, [rbp+57h+lpData]
0x1800337fc  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x180033801  mov     r14, [rbp+57h+lpData]
0x180033805  mov     edx, 0FFFFFFFFh
0x18003380a  add     edi, edx
0x18003380c  jmp     short loc_18003386B
0x18003380e  mov     rcx, [rbp+5Fh]; this
0x180033812  test    eax, eax
0x180033814  jnz     loc_1800338B0
0x18003381a  mov     rax, [rbx+10h]
0x18003381e  cmp     [rbx+8], rax
0x180033822  jnz     short loc_18003382C
0x180033824  mov     rcx, rbx
0x180033827  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18003382c  mov     rcx, [rbx+8]; void *
0x180033830  mov     qword ptr [rcx+18h], 7
0x180033838  mov     [rcx+10h], r13
0x18003383c  mov     [rcx], r13w
0x180033840  cmp     [r15], r13w
0x180033844  jnz     short loc_18003384B
0x180033846  mov     r8, r13
0x180033849  jmp     short loc_180033859
0x18003384b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003384f  inc     r8
0x180033852  cmp     [r15+r8*2], r13w
0x180033857  jnz     short loc_18003384F
0x180033859  mov     rdx, r15; Src
0x18003385c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180033861  add     qword ptr [rbx+8], 20h ; ' '
0x180033866  mov     edx, 0FFFFFFFFh
0x18003386b  inc     edi
0x18003386d  cmp     edi, [rbp+57h+cValues]
0x180033870  jb      loc_180033784
0x180033876  test    r14, r14
0x180033879  jz      short loc_180033885
0x18003387b  mov     rcx, r14
0x18003387e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033884  nop
0x180033885  test    r15, r15
0x180033888  jz      short loc_180033893
0x18003388a  mov     rcx, r15
0x18003388d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180033893  mov     eax, edi
0x180033895  mov     rbx, [rsp+0D0h+arg_0]
0x18003389d  add     rsp, 0A0h
0x1800338a4  pop     r15
0x1800338a6  pop     r14
0x1800338a8  pop     r13
0x1800338aa  pop     r12
0x1800338ac  pop     rdi
0x1800338ad  pop     rsi
0x1800338ae  pop     rbp
0x1800338af  retn
0x1800338b0  mov     r9d, eax; char *
0x1800338b3  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x1800338ba  mov     edx, 2Eh ; '.'; void *
0x1800338bf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800338c5  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x1800338cc  mov     edx, 1Fh; void *
0x1800338d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800338d7  mov     r9d, eax; char *
0x1800338da  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x1800338e1  mov     edx, 10h; void *
0x1800338e6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800338ec  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x1800338f3  mov     edx, 13h; void *
0x1800338f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
