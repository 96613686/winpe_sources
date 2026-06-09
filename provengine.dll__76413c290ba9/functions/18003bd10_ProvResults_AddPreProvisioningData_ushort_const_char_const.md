# ProvResults::AddPreProvisioningData(ushort const *,char const *)

- ea: `0x18003bd10`
- end: `0x18003c028`
- name: `?AddPreProvisioningData@ProvResults@@QEBAXPEBGPEBD@Z`
- size: `792`
- prototype: `void __fastcall(ProvResults *this, const BYTE *, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001a6fc`

## callees

- `0x18000b030`
- `0x18000b31c`
- `0x180021cf4`
- `0x18002f9bc`
- `0x18003bd10`
- `0x18003d048`
- `0x180043750`

## import_xrefs

- `msvcrt!gmtime` at `0x18003bd85`
- `msvcrt!gmtime` at `0x18003bd85`
- `msvcrt!time` at `0x18003bd77`
- `msvcrt!time` at `0x18003bd77`
- `msvcrt!wcsftime` at `0x18003bda2`
- `msvcrt!wcsftime` at `0x18003bda2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bf7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bf98`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bf7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003bf98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003bd66`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003bd66`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bdd6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003be6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bf69`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bdd6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003be6a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003bf69`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003be93`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003bedd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003be93`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003bedd`

## string_xrefs

- `0x18003bd5f`: `PackageInstallStart`
- `0x18003bdcb`: `PackageInstallStart`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall ProvResults::AddPreProvisioningData(ProvResults *this, const BYTE *a2, const char *a3)
{
  HKEY v6; // rcx
  struct tm *v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rbx
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  __int64 v13; // r9
  unsigned int v14; // eax
  int v15; // eax
  LPWSTR v16; // rdi
  __int64 v17; // r8
  BYTE **v18; // rax
  BYTE *v19; // rcx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rbx
  const BYTE *v22; // rax
  int lpData; // [rsp+20h] [rbp-69h]
  unsigned int lpDataa; // [rsp+20h] [rbp-69h]
  unsigned int lpDatab; // [rsp+20h] [rbp-69h]
  time_t Time; // [rsp+30h] [rbp-59h] BYREF
  LPWSTR lpWideCharStr[2]; // [rsp+38h] [rbp-51h] BYREF
  __int64 v28; // [rsp+48h] [rbp-41h]
  BYTE *v29[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v30; // [rsp+68h] [rbp-21h]
  unsigned __int64 v31; // [rsp+70h] [rbp-19h]
  wchar_t Buffer[20]; // [rsp+78h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  ProvResults::LazyCreatePackageKey((LPCWSTR)this);
  v6 = (HKEY)*((_QWORD *)this + 4);
  if ( !v6 || RegQueryValueExW(v6, L"PackageInstallStart", 0, 0, 0, 0) == 2 )
  {
    Time = time(0);
    v7 = gmtime(&Time);
    if ( !wcsftime(Buffer, 0x14u, L"%Y-%m-%d %H:%M:%S", v7) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)0x80070057LL,
        lpData);
    v8 = RegSetValueExW(*((HKEY *)this + 4), L"PackageInstallStart", 0, 1u, (const BYTE *)Buffer, 0x28u);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x4A,
        (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v8,
        lpDataa);
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&a2[2 * v10] );
    v11 = v10 + 1;
    v12 = 2 * v11;
    if ( is_mul_ok(v11, 2u) )
    {
      v13 = 0;
    }
    else
    {
      v12 = -1;
      v13 = 2147942934LL;
    }
    if ( (int)v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v13,
        lpDataa);
    if ( v12 > 0xFFFFFFFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        v12 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
        lpDataa);
    v14 = RegSetValueExW(*((HKEY *)this + 4), L"PackageFileName", 0, 1u, a2, v12);
    if ( v14 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x52,
        (int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
        (const char *)v14,
        lpDatab);
    v15 = MultiByteToWideChar(0xFDE9u, 0, a3, -1, 0, 0);
    if ( v15 > 0 )
    {
      *(_OWORD *)lpWideCharStr = 0;
      v28 = 0;
      std::vector<unsigned short>::resize(lpWideCharStr, v15);
      v16 = lpWideCharStr[0];
      MultiByteToWideChar(
        0xFDE9u,
        0,
        a3,
        -1,
        lpWideCharStr[0],
        (signed __int64)(v28 - (unsigned __int64)lpWideCharStr[0]) >> 1);
      v31 = 7;
      v30 = 0;
      LOWORD(v29[0]) = 0;
      if ( *v16 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v16[v17] );
      }
      std::wstring::assign(v29, v16);
      v18 = v29;
      v19 = v29[0];
      v20 = v31;
      if ( v31 >= 8 )
        v18 = (BYTE **)v29[0];
      do
        ++v9;
      while ( *((_WORD *)v18 + v9) );
      v21 = 2 * v9;
      if ( v21 <= 0xFFFFFFFF )
      {
        v22 = (const BYTE *)v29;
        if ( v31 >= 8 )
          v22 = v29[0];
        RegSetValueExW(*((HKEY *)this + 4), L"Session", 0, 1u, v22, v21);
        v20 = v31;
        v19 = v29[0];
      }
      if ( v20 >= 8 )
        operator delete(v19);
      v31 = 7;
      v30 = 0;
      LOWORD(v29[0]) = 0;
      if ( v16 )
        operator delete(v16);
    }
  }
}

```

## disassembly

```asm
0x18003bd10  push    rbp
0x18003bd12  push    rbx
0x18003bd13  push    rsi
0x18003bd14  push    rdi
0x18003bd15  push    r12
0x18003bd17  push    r14
0x18003bd19  push    r15
0x18003bd1b  lea     rbp, [rsp-27h]
0x18003bd20  sub     rsp, 0B0h
0x18003bd27  mov     rax, cs:__security_cookie
0x18003bd2e  xor     rax, rsp
0x18003bd31  mov     [rbp+57h+var_40], rax
0x18003bd35  mov     r14, r8
0x18003bd38  mov     rdi, rdx
0x18003bd3b  mov     rsi, rcx
0x18003bd3e  call    ?LazyCreatePackageKey@ProvResults@@AEBAXXZ; ProvResults::LazyCreatePackageKey(void)
0x18003bd43  mov     rcx, [rsi+20h]; hKey
0x18003bd47  xor     r15d, r15d
0x18003bd4a  test    rcx, rcx
0x18003bd4d  jz      short loc_18003BD75
0x18003bd4f  mov     [rsp+0E0h+lpcbData], r15; lpcbData
0x18003bd54  mov     [rsp+0E0h+lpData], r15; int
0x18003bd59  xor     r9d, r9d; lpType
0x18003bd5c  xor     r8d, r8d; lpReserved
0x18003bd5f  lea     rdx, aPackageinstall; "PackageInstallStart"
0x18003bd66  call    cs:__imp_RegQueryValueExW
0x18003bd6c  cmp     eax, 2
0x18003bd6f  jnz     loc_18003BF9E
0x18003bd75  xor     ecx, ecx; Time
0x18003bd77  call    cs:__imp_time
0x18003bd7d  mov     [rbp+57h+Time], rax
0x18003bd81  lea     rcx, [rbp+57h+Time]; Time
0x18003bd85  call    cs:__imp_gmtime
0x18003bd8b  mov     rbx, [rbp+5Fh]
0x18003bd8f  mov     r9, rax; Tm
0x18003bd92  lea     r8, aYMDHMS; "%Y-%m-%d %H:%M:%S"
0x18003bd99  mov     edx, 14h; SizeInWords
0x18003bd9e  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18003bda2  call    cs:__imp_wcsftime
0x18003bda8  test    rax, rax
0x18003bdab  jz      loc_18003BFD1
0x18003bdb1  mov     dword ptr [rsp+0E0h+lpcbData], 28h ; '('; cbData
0x18003bdb9  lea     rax, [rbp+57h+Buffer]
0x18003bdbd  mov     [rsp+0E0h+lpData], rax; int
0x18003bdc2  mov     r9d, 1; dwType
0x18003bdc8  xor     r8d, r8d; Reserved
0x18003bdcb  lea     rdx, aPackageinstall; "PackageInstallStart"
0x18003bdd2  mov     rcx, [rsi+20h]; hKey
0x18003bdd6  call    cs:__imp_RegSetValueExW
0x18003bddc  mov     rcx, [rbp+5Fh]; this
0x18003bde0  test    eax, eax
0x18003bde2  jnz     loc_18003BFEC
0x18003bde8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003bdec  mov     rcx, rbx
0x18003bdef  inc     rcx
0x18003bdf2  cmp     [rdi+rcx*2], r15w
0x18003bdf7  jnz     short loc_18003BDEF
0x18003bdf9  inc     rcx
0x18003bdfc  mov     eax, 2
0x18003be01  mul     rcx
0x18003be04  mov     r8d, 80070216h
0x18003be0a  test    rdx, rdx
0x18003be0d  jnz     short loc_18003BE14
0x18003be0f  mov     r9d, r15d
0x18003be12  jmp     short loc_18003BE1A
0x18003be14  mov     rax, rbx
0x18003be17  mov     r9d, r8d; char *
0x18003be1a  mov     rcx, [rbp+5Fh]; this
0x18003be1e  test    r9d, r9d
0x18003be21  js      loc_18003C001
0x18003be27  mov     r12d, 0FFFFFFFFh
0x18003be2d  cmp     rax, r12
0x18003be30  mov     ecx, eax
0x18003be32  jbe     short loc_18003BE37
0x18003be34  mov     ecx, r12d
0x18003be37  cmp     r12, rax
0x18003be3a  sbb     r9d, r9d
0x18003be3d  and     r9d, r8d; char *
0x18003be40  mov     r10, [rbp+5Fh]
0x18003be44  cmp     rax, r12
0x18003be47  ja      loc_18003C013
0x18003be4d  mov     dword ptr [rsp+0E0h+lpcbData], ecx; cbData
0x18003be51  mov     [rsp+0E0h+lpData], rdi; unsigned int
0x18003be56  mov     r9d, 1; dwType
0x18003be5c  xor     r8d, r8d; Reserved
0x18003be5f  lea     rdx, aPackagefilenam; "PackageFileName"
0x18003be66  mov     rcx, [rsi+20h]; hKey
0x18003be6a  call    cs:__imp_RegSetValueExW
0x18003be70  mov     rcx, [rbp+5Fh]; this
0x18003be74  test    eax, eax
0x18003be76  jnz     loc_18003BFBC
0x18003be7c  mov     dword ptr [rsp+0E0h+lpcbData], r15d; cchWideChar
0x18003be81  mov     [rsp+0E0h+lpData], r15; lpWideCharStr
0x18003be86  mov     r9d, ebx; cbMultiByte
0x18003be89  mov     r8, r14; lpMultiByteStr
0x18003be8c  xor     edx, edx; dwFlags
0x18003be8e  mov     ecx, 0FDE9h; CodePage
0x18003be93  call    cs:__imp_MultiByteToWideChar
0x18003be99  test    eax, eax
0x18003be9b  jle     loc_18003BF9E
0x18003bea1  xorps   xmm0, xmm0
0x18003bea4  movdqu  xmmword ptr [rbp+57h+lpWideCharStr], xmm0
0x18003bea9  mov     [rbp+57h+var_98], r15
0x18003bead  movsxd  rdx, eax
0x18003beb0  lea     rcx, [rbp+57h+lpWideCharStr]
0x18003beb4  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003beb9  mov     rax, [rbp+57h+var_98]
0x18003bebd  mov     rdi, [rbp+57h+lpWideCharStr]
0x18003bec1  sub     rax, rdi
0x18003bec4  sar     rax, 1
0x18003bec7  mov     dword ptr [rsp+0E0h+lpcbData], eax; cchWideChar
0x18003becb  mov     [rsp+0E0h+lpData], rdi; lpWideCharStr
0x18003bed0  mov     r9d, ebx; cbMultiByte
0x18003bed3  mov     r8, r14; lpMultiByteStr
0x18003bed6  xor     edx, edx; dwFlags
0x18003bed8  mov     ecx, 0FDE9h; CodePage
0x18003bedd  call    cs:__imp_MultiByteToWideChar
0x18003bee3  mov     r14d, 7
0x18003bee9  mov     [rbp+57h+var_70], r14
0x18003beed  mov     [rbp+57h+var_78], r15
0x18003bef1  mov     word ptr [rbp+57h+var_88], r15w
0x18003bef6  cmp     [rdi], r15w
0x18003befa  jnz     short loc_18003BF01
0x18003befc  mov     r8, r15
0x18003beff  jmp     short loc_18003BF0E
0x18003bf01  mov     r8, rbx
0x18003bf04  inc     r8
0x18003bf07  cmp     [rdi+r8*2], r15w
0x18003bf0c  jnz     short loc_18003BF04
0x18003bf0e  mov     rdx, rdi; Src
0x18003bf11  lea     rcx, [rbp+57h+var_88]; void *
0x18003bf15  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003bf1a  lea     rax, [rbp+57h+var_88]
0x18003bf1e  mov     rcx, [rbp+57h+var_88]
0x18003bf22  mov     rdx, [rbp+57h+var_70]
0x18003bf26  cmp     rdx, 8
0x18003bf2a  cmovnb  rax, rcx
0x18003bf2e  inc     rbx
0x18003bf31  cmp     [rax+rbx*2], r15w
0x18003bf36  jnz     short loc_18003BF2E
0x18003bf38  add     rbx, rbx
0x18003bf3b  cmp     rbx, r12
0x18003bf3e  ja      short loc_18003BF77
0x18003bf40  lea     rax, [rbp+57h+var_88]
0x18003bf44  cmp     rdx, 8
0x18003bf48  cmovnb  rax, rcx
0x18003bf4c  mov     dword ptr [rsp+0E0h+lpcbData], ebx; cbData
0x18003bf50  mov     [rsp+0E0h+lpData], rax; lpData
0x18003bf55  mov     r9d, 1; dwType
0x18003bf5b  xor     r8d, r8d; Reserved
0x18003bf5e  lea     rdx, aSession; "Session"
0x18003bf65  mov     rcx, [rsi+20h]; hKey
0x18003bf69  call    cs:__imp_RegSetValueExW
0x18003bf6f  mov     rdx, [rbp+57h+var_70]
0x18003bf73  mov     rcx, [rbp+57h+var_88]
0x18003bf77  cmp     rdx, 8
0x18003bf7b  jb      short loc_18003BF83
0x18003bf7d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003bf83  mov     [rbp+57h+var_70], r14
0x18003bf87  mov     [rbp+57h+var_78], r15
0x18003bf8b  mov     word ptr [rbp+57h+var_88], r15w
0x18003bf90  test    rdi, rdi
0x18003bf93  jz      short loc_18003BF9E
0x18003bf95  mov     rcx, rdi
0x18003bf98  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003bf9e  mov     rcx, [rbp+57h+var_40]
0x18003bfa2  xor     rcx, rsp; StackCookie
0x18003bfa5  call    __security_check_cookie
0x18003bfaa  add     rsp, 0B0h
0x18003bfb1  pop     r15
0x18003bfb3  pop     r14
0x18003bfb5  pop     r12
0x18003bfb7  pop     rdi
0x18003bfb8  pop     rsi
0x18003bfb9  pop     rbx
0x18003bfba  pop     rbp
0x18003bfbb  retn
0x18003bfbc  mov     r9d, eax; char *
0x18003bfbf  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003bfc6  mov     edx, 52h ; 'R'; void *
0x18003bfcb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003bfd1  mov     r9d, 80070057h; char *
0x18003bfd7  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003bfde  mov     edx, 47h ; 'G'; void *
0x18003bfe3  mov     rcx, rbx; this
0x18003bfe6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003bfec  mov     r9d, eax; char *
0x18003bfef  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003bff6  mov     edx, 4Ah ; 'J'; void *
0x18003bffb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18003c001  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c008  mov     edx, 4Fh ; 'O'; void *
0x18003c00d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c013  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\prov\\lib\\provresul"...
0x18003c01a  mov     edx, 50h ; 'P'; void *
0x18003c01f  mov     rcx, r10; this
0x18003c022  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
