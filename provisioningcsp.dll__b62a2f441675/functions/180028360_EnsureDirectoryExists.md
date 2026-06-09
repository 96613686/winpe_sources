# EnsureDirectoryExists

- ea: `0x180028360`
- end: `0x18002850e`
- name: `EnsureDirectoryExists`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path`

## callers

- `0x1800287dc`

## callees

- `0x1800046ac`
- `0x1800090e0`
- `0x18000918c`
- `0x1800125f4`
- `0x180024508`
- `0x180028360`
- `0x180028ebc`
- `0x1800358a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180028469`
- `msvcrt!??3@YAXPEAX@Z` at `0x180028469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002841a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002841a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800283ff`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800283ff`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002844a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002844a`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800283a1`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x1800283a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall EnsureDirectoryExists(__int64 a1)
{
  const WCHAR *v2; // rdi
  HRESULT v3; // eax
  __int64 i; // r8
  const WCHAR *v5; // rcx
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  const WCHAR *v10; // rcx
  const char *v11; // r9
  unsigned __int64 v12; // rdi
  unsigned __int64 result; // rax
  unsigned int v14; // eax
  PCWSTR ppszRootEnd; // [rsp+20h] [rbp-30h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+28h] [rbp-28h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  if ( *(_QWORD *)(a1 + 24) < 8u )
    v2 = (const WCHAR *)a1;
  else
    v2 = *(const WCHAR **)a1;
  ppszRootEnd = 0;
  v3 = PathCchSkipRoot(v2, &ppszRootEnd);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
      (const char *)(unsigned int)v3,
      (int)ppszRootEnd);
  for ( i = ppszRootEnd - v2; ; i = v12 )
  {
    result = std::wstring::find(a1, 92, i);
    v12 = result;
    if ( result >= *(_QWORD *)(a1 + 16) )
      break;
    v17 = 7;
    lpFileName[2] = 0;
    LOWORD(lpFileName[0]) = 0;
    std::wstring::assign(lpFileName);
    v5 = (const WCHAR *)lpFileName;
    if ( v17 >= 8 )
      v5 = lpFileName[0];
    FileAttributesW = GetFileAttributesW(v5);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      if ( LastError != 5 )
      {
        if ( LastError - 2 > 1 )
          wil::details::in1diag3::Throw_Win32(retaddr, v8, v9, (const char *)LastError, (unsigned int)ppszRootEnd);
        v10 = (const WCHAR *)lpFileName;
        if ( v17 >= 8 )
          v10 = lpFileName[0];
        if ( !CreateDirectoryW(v10, 0) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x60,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
            v11);
      }
    }
    else if ( (FileAttributesW & 0x10) == 0 )
    {
      v14 = wil::verify_hresult<long>(2248146961LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetnode.cpp",
        (const char *)v14,
        (int)ppszRootEnd);
    }
    if ( v17 >= 8 )
      operator delete((void *)lpFileName[0]);
    if ( v12 < v12 + 1 )
      ++v12;
  }
  return result;
}

```

## disassembly

```asm
0x180028360  mov     [rsp-8+arg_8], rbx
0x180028365  mov     [rsp-8+arg_10], rdi
0x18002836a  push    rbp
0x18002836b  mov     rbp, rsp
0x18002836e  sub     rsp, 50h
0x180028372  mov     rax, cs:__security_cookie
0x180028379  xor     rax, rsp
0x18002837c  mov     [rbp+var_8], rax
0x180028380  mov     rbx, rcx
0x180028383  cmp     qword ptr [rcx+18h], 8
0x180028388  jb      short loc_18002838F
0x18002838a  mov     rdi, [rcx]
0x18002838d  jmp     short loc_180028392
0x18002838f  mov     rdi, rbx
0x180028392  mov     [rbp+ppszRootEnd], 0
0x18002839a  lea     rdx, [rbp+ppszRootEnd]; ppszRootEnd
0x18002839e  mov     rcx, rdi; pszPath
0x1800283a1  call    cs:__imp_PathCchSkipRoot
0x1800283a8  nop     dword ptr [rax+rax+00h]
0x1800283ad  mov     rcx, [rbp+8]; this
0x1800283b1  test    eax, eax
0x1800283b3  js      loc_1800284F9
0x1800283b9  mov     r8, [rbp+ppszRootEnd]
0x1800283bd  sub     r8, rdi
0x1800283c0  sar     r8, 1
0x1800283c3  jmp     loc_180028483
0x1800283c8  mov     [rbp+var_10], 7
0x1800283d0  mov     [rbp+var_18], 0
0x1800283d8  xor     ecx, ecx
0x1800283da  mov     word ptr [rbp+lpFileName], cx
0x1800283de  mov     r9, rdi
0x1800283e1  xor     r8d, r8d
0x1800283e4  mov     rdx, rbx
0x1800283e7  lea     rcx, [rbp+lpFileName]; void *
0x1800283eb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800283f0  nop
0x1800283f1  lea     rcx, [rbp+lpFileName]
0x1800283f5  cmp     [rbp+var_10], 8
0x1800283fa  cmovnb  rcx, [rbp+lpFileName]; lpFileName
0x1800283ff  call    cs:__imp_GetFileAttributesW
0x180028406  nop     dword ptr [rax+rax+00h]
0x18002840b  cmp     eax, 0FFFFFFFFh
0x18002840e  jz      short loc_18002841A
0x180028410  test    al, 10h
0x180028412  jz      loc_1800284CC
0x180028418  jmp     short loc_18002845E
0x18002841a  call    cs:__imp_GetLastError
0x180028421  nop     dword ptr [rax+rax+00h]
0x180028426  mov     r9d, eax; char *
0x180028429  cmp     eax, 5
0x18002842c  jz      short loc_18002845E
0x18002842e  add     eax, 0FFFFFFFEh
0x180028431  cmp     eax, 1
0x180028434  ja      loc_1800284EF
0x18002843a  lea     rcx, [rbp+lpFileName]
0x18002843e  cmp     [rbp+var_10], 8
0x180028443  cmovnb  rcx, [rbp+lpFileName]; lpPathName
0x180028448  xor     edx, edx; lpSecurityAttributes
0x18002844a  call    cs:__imp_CreateDirectoryW
0x180028451  nop     dword ptr [rax+rax+00h]
0x180028456  mov     rcx, [rbp+8]; this
0x18002845a  test    eax, eax
0x18002845c  jz      short loc_1800284BA
0x18002845e  cmp     [rbp+var_10], 8
0x180028463  jb      short loc_180028475
0x180028465  mov     rcx, [rbp+lpFileName]
0x180028469  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180028470  nop     dword ptr [rax+rax+00h]
0x180028475  lea     rax, [rdi+1]
0x180028479  cmp     rdi, rax
0x18002847c  cmovbe  rdi, rax
0x180028480  mov     r8, rdi
0x180028483  mov     edx, 5Ch ; '\'
0x180028488  mov     rcx, rbx
0x18002848b  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x180028490  cmp     rax, [rbx+10h]
0x180028494  mov     rdi, rax
0x180028497  jb      loc_1800283C8
0x18002849d  mov     rcx, [rbp+var_8]
0x1800284a1  xor     rcx, rsp; StackCookie
0x1800284a4  call    __security_check_cookie
0x1800284a9  mov     rbx, [rsp+50h+arg_8]
0x1800284ae  mov     rdi, [rsp+50h+arg_10]
0x1800284b3  add     rsp, 50h
0x1800284b7  pop     rbp
0x1800284b8  retn
0x1800284ba  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800284c1  mov     edx, 60h ; '`'; void *
0x1800284c6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800284cc  mov     ecx, 86000011h
0x1800284d1  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800284d6  mov     r9d, eax; char *
0x1800284d9  mov     rcx, [rbp+8]; this
0x1800284dd  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800284e4  mov     edx, 51h ; 'Q'; void *
0x1800284e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800284ef  mov     rcx, [rbp+8]; this
0x1800284f3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800284f9  mov     r9d, eax; char *
0x1800284fc  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180028503  mov     edx, 42h ; 'B'; void *
0x180028508  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
