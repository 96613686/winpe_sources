# ForEachRegValue__lambda_fbd86aa7485f14e8675becbcee7181c7_

- ea: `0x18000a3e4`
- end: `0x18000a615`
- name: `ForEachRegValue__lambda_fbd86aa7485f14e8675becbcee7181c7___`
- size: `561`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18001df00`

## callees

- `0x18000a3e4`
- `0x18000ed20`
- `0x18001b388`
- `0x18001b3a8`
- `0x180020260`
- `0x1800202e4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a592`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a5a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a592`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a5a3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000a537`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000a537`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a448`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a448`

## string_xrefs

- `0x18000a5ca`: `onecoreuap\admin\prov\inc\RegistryUtils.h`
- `0x18000a5dc`: `onecoreuap\admin\prov\inc\RegistryUtils.h`
- `0x18000a5f1`: `onecoreuap\admin\prov\inc\RegistryUtils.h`
- `0x18000a603`: `onecoreuap\admin\prov\inc\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ForEachRegValue__lambda_fbd86aa7485f14e8675becbcee7181c7_(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  DWORD v5; // edx
  DWORD v6; // eax
  __int64 v7; // r8
  const char *v8; // r9
  DWORD v9; // ebx
  BYTE *i; // rdi
  unsigned __int64 v11; // rsi
  DWORD v12; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int lpcSubKeys; // [rsp+28h] [rbp-49h]
  DWORD cValues; // [rsp+68h] [rbp-9h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-5h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-1h] BYREF
  LPBYTE lpData[2]; // [rsp+78h] [rbp+7h] BYREF
  __int64 v23; // [rsp+88h] [rbp+17h]
  LPWSTR lpValueName[2]; // [rsp+90h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+A0h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  DWORD cbMaxValueNameLen; // [rsp+E8h] [rbp+77h] BYREF
  DWORD cbData; // [rsp+F0h] [rbp+7Fh] BYREF

  cValues = 0;
  cbMaxValueNameLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\admin\\prov\\inc\\RegistryUtils.h",
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
      (unsigned int)"onecoreuap\\admin\\prov\\inc\\RegistryUtils.h",
      v8,
      lpcSubKeys);
  *(_OWORD *)lpValueName = 0;
  v25 = 0;
  if ( (_DWORD)v7 )
    std::vector<unsigned short>::_Reallocate(lpValueName, (unsigned int)v7);
  *(_OWORD *)lpData = 0;
  v23 = 0;
  std::vector<unsigned char>::_Reallocate(lpData, 260, v7, v8);
  cbData = 0;
  v9 = 0;
  for ( i = lpData[0]; v9 < cValues; ++v9 )
  {
    cchValueName = cbMaxValueNameLen;
    Type = 0;
    v11 = v23 - (_QWORD)i;
    v12 = v23 - (_DWORD)i;
    if ( (unsigned __int64)(v23 - (_QWORD)i) > 0xFFFFFFFF )
      v12 = -1;
    cbData = v12;
    if ( v11 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecoreuap\\admin\\prov\\inc\\RegistryUtils.h",
        v11 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
        lpcSubKeys);
    v13 = RegEnumValueW(hKey, v9, lpValueName[0], &cchValueName, 0, &Type, i, &cbData);
    if ( v13 == 234 )
    {
      if ( v11 < cbData )
      {
        std::vector<unsigned char>::_Reallocate(lpData, cbData, v15, v16);
        i = lpData[0];
      }
      --v9;
    }
    else
    {
      if ( v13 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x2E,
          (unsigned int)"onecoreuap\\admin\\prov\\inc\\RegistryUtils.h",
          (const char *)v13,
          lpcSubKeys);
      if ( !(unsigned __int8)lambda_fbd86aa7485f14e8675becbcee7181c7_::operator()(a2, v14, lpValueName[0]) )
        break;
    }
  }
  if ( i )
    operator delete(i);
  if ( lpValueName[0] )
    operator delete(lpValueName[0]);
  return v9;
}

```

## disassembly

```asm
0x18000a3e4  mov     rax, rsp
0x18000a3e7  mov     [rax+8], rbx
0x18000a3eb  mov     [rax+10h], rsi
0x18000a3ef  push    rbp
0x18000a3f0  push    rdi
0x18000a3f1  push    r12
0x18000a3f3  push    r13
0x18000a3f5  push    r15
0x18000a3f7  lea     rbp, [rax-5Fh]
0x18000a3fb  sub     rsp, 0A0h
0x18000a402  mov     r12, rdx
0x18000a405  mov     r15, rcx
0x18000a408  xor     r13d, r13d
0x18000a40b  mov     [rbp+57h+cValues], r13d
0x18000a40f  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x18000a413  mov     [rax-70h], r13
0x18000a417  mov     [rax-78h], r13
0x18000a41b  mov     [rax-80h], r13
0x18000a41f  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18000a423  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000a428  lea     rax, [rbp+57h+cValues]
0x18000a42c  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x18000a431  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18000a436  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18000a43b  mov     [rsp+0C0h+lpcSubKeys], r13; int
0x18000a440  xor     r9d, r9d; lpReserved
0x18000a443  xor     r8d, r8d; lpcchClass
0x18000a446  xor     edx, edx; lpClass
0x18000a448  call    cs:__imp_RegQueryInfoKeyW
0x18000a44e  mov     rcx, [rbp+5Fh]; this
0x18000a452  test    eax, eax
0x18000a454  jnz     loc_18000A5EE
0x18000a45a  mov     edx, [rbp+57h+cbMaxValueNameLen]
0x18000a45d  lea     eax, [rdx+1]
0x18000a460  mov     r8d, 0FFFFFFFFh
0x18000a466  cmp     eax, edx
0x18000a468  cmovnb  r8d, eax
0x18000a46c  sbb     r9d, r9d
0x18000a46f  and     r9d, 80070216h; char *
0x18000a476  mov     [rbp+57h+cbMaxValueNameLen], r8d
0x18000a47a  mov     rcx, [rbp+5Fh]; this
0x18000a47e  cmp     eax, edx
0x18000a480  jb      loc_18000A603
0x18000a486  xorps   xmm0, xmm0
0x18000a489  movdqu  xmmword ptr [rbp+57h+lpValueName], xmm0
0x18000a48e  mov     [rbp+57h+var_28], r13
0x18000a492  mov     edx, r8d
0x18000a495  test    r8d, r8d
0x18000a498  jz      short loc_18000A4A3
0x18000a49a  lea     rcx, [rbp+57h+lpValueName]
0x18000a49e  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18000a4a3  xorps   xmm0, xmm0
0x18000a4a6  movdqu  xmmword ptr [rbp+57h+lpData], xmm0
0x18000a4ab  mov     [rbp+57h+var_40], r13
0x18000a4af  mov     edx, 104h
0x18000a4b4  lea     rcx, [rbp+57h+lpData]
0x18000a4b8  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x18000a4bd  mov     [rbp+57h+cbData], r13d
0x18000a4c1  mov     ebx, r13d
0x18000a4c4  mov     rdi, [rbp+57h+lpData]
0x18000a4c8  cmp     [rbp+57h+cValues], r13d
0x18000a4cc  jbe     loc_18000A58A
0x18000a4d2  mov     edx, 0FFFFFFFFh
0x18000a4d7  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18000a4da  mov     [rbp+57h+cchValueName], eax
0x18000a4dd  mov     [rbp+57h+Type], r13d
0x18000a4e1  mov     rsi, [rbp+57h+var_40]
0x18000a4e5  sub     rsi, rdi
0x18000a4e8  cmp     rsi, rdx
0x18000a4eb  mov     eax, esi
0x18000a4ed  jbe     short loc_18000A4F1
0x18000a4ef  mov     eax, edx
0x18000a4f1  cmp     rdx, rsi
0x18000a4f4  sbb     r9d, r9d
0x18000a4f7  and     r9d, 80070216h; char *
0x18000a4fe  mov     [rbp+57h+cbData], eax
0x18000a501  mov     rcx, [rbp+5Fh]; this
0x18000a505  cmp     rsi, rdx
0x18000a508  ja      loc_18000A5DC
0x18000a50e  lea     rax, [rbp+57h+cbData]
0x18000a512  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x18000a517  mov     [rsp+0C0h+lpcbMaxClassLen], rdi; lpData
0x18000a51c  lea     rax, [rbp+57h+Type]
0x18000a520  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x18000a525  mov     [rsp+0C0h+lpcSubKeys], r13; unsigned int
0x18000a52a  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18000a52e  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x18000a532  mov     edx, ebx; dwIndex
0x18000a534  mov     rcx, r15; hKey
0x18000a537  call    cs:__imp_RegEnumValueW
0x18000a53d  cmp     eax, 0EAh
0x18000a542  jnz     short loc_18000A562
0x18000a544  mov     edx, [rbp+57h+cbData]
0x18000a547  cmp     rsi, rdx
0x18000a54a  jnb     short loc_18000A559
0x18000a54c  lea     rcx, [rbp+57h+lpData]
0x18000a550  call    ?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z; std::vector<uchar>::_Reallocate(unsigned __int64)
0x18000a555  mov     rdi, [rbp+57h+lpData]
0x18000a559  mov     edx, 0FFFFFFFFh
0x18000a55e  add     ebx, edx
0x18000a560  jmp     short loc_18000A57F
0x18000a562  mov     rcx, [rbp+5Fh]; this
0x18000a566  test    eax, eax
0x18000a568  jnz     short loc_18000A5C7
0x18000a56a  mov     r8, [rbp+57h+lpValueName]
0x18000a56e  mov     rcx, r12
0x18000a571  call    _lambda_fbd86aa7485f14e8675becbcee7181c7___operator__
0x18000a576  test    al, al
0x18000a578  jz      short loc_18000A58A
0x18000a57a  mov     edx, 0FFFFFFFFh
0x18000a57f  inc     ebx
0x18000a581  cmp     ebx, [rbp+57h+cValues]
0x18000a584  jb      loc_18000A4D7
0x18000a58a  test    rdi, rdi
0x18000a58d  jz      short loc_18000A599
0x18000a58f  mov     rcx, rdi
0x18000a592  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a598  nop
0x18000a599  cmp     [rbp+57h+lpValueName], r13
0x18000a59d  jz      short loc_18000A5A9
0x18000a59f  mov     rcx, [rbp+57h+lpValueName]
0x18000a5a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a5a9  mov     eax, ebx
0x18000a5ab  lea     r11, [rsp+0C0h+var_20]
0x18000a5b3  mov     rbx, [r11+30h]
0x18000a5b7  mov     rsi, [r11+38h]
0x18000a5bb  mov     rsp, r11
0x18000a5be  pop     r15
0x18000a5c0  pop     r13
0x18000a5c2  pop     r12
0x18000a5c4  pop     rdi
0x18000a5c5  pop     rbp
0x18000a5c6  retn
0x18000a5c7  mov     r9d, eax; char *
0x18000a5ca  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\inc\\RegistryU"...
0x18000a5d1  mov     edx, 2Eh ; '.'; void *
0x18000a5d6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000a5dc  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\inc\\RegistryU"...
0x18000a5e3  mov     edx, 1Fh; void *
0x18000a5e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000a5ee  mov     r9d, eax; char *
0x18000a5f1  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\inc\\RegistryU"...
0x18000a5f8  mov     edx, 10h; void *
0x18000a5fd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000a603  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\inc\\RegistryU"...
0x18000a60a  mov     edx, 13h; void *
0x18000a60f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
