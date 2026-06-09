# EnsureDirectoriesArePresent(ushort const *)

- ea: `0x180127a74`
- end: `0x180127bdd`
- name: `?EnsureDirectoriesArePresent@@YAJPEBG@Z`
- size: `361`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800fbba0`
- `0x1800fbe40`
- `0x18010cb20`
- `0x180111204`
- `0x180127638`

## callees

- `0x180019080`
- `0x1800198d0`
- `0x1800ed46c`
- `0x180105294`
- `0x180127a74`
- `0x180127e70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180127acd`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180127acd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180127b23`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180127b23`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180127b9f`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180127b9f`

## string_xrefs

- `0x180127aea`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`
- `0x180127b5c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`

## pseudocode

```c
signed int __fastcall EnsureDirectoriesArePresent(const unsigned __int16 *a1)
{
  unsigned int v1; // eax
  __int64 v2; // rdx
  signed int result; // eax
  size_t v4; // rax
  unsigned __int64 v5; // rcx
  unsigned int DirCount; // [rsp+20h] [rbp-468h]
  wchar_t Drive[264]; // [rsp+50h] [rbp-438h] BYREF
  wchar_t Dir[264]; // [rsp+260h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+0h]

  v1 = _wsplitpath_s(a1, Drive, 0x104u, Dir, 0x104u, 0, 0, 0, 0);
  if ( v1 )
  {
    v2 = 131;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v2,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\reportfromstreams\\registrydiagnosticreportfromstream.cpp",
             (const char *)v1,
             DirCount);
  }
  v1 = _o_wcscat_s(Drive, 260, Dir);
  if ( v1 )
  {
    v2 = 134;
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v2,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\reportfromstreams\\registrydiagnosticreportfromstream.cpp",
             (const char *)v1,
             DirCount);
  }
  v4 = wcsnlen_s(Drive, 0x104u);
  if ( ((v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v5 = 2 * v4 - 2;
    if ( v5 >= 0x208 )
      _report_rangecheckfailure();
    *(wchar_t *)((char *)Drive + v5) = 0;
    result = SHCreateDirectoryExW(0, Drive, 0);
    if ( !result || result == 80 || result == 183 )
    {
      return 0;
    }
    else if ( result > 0 )
    {
      return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\reportfromstreams\\registrydiagnosticreportfromstream.cpp",
      (const char *)0x80004005LL,
      DirCount);
    return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180127a74  push    rdi
0x180127a76  sub     rsp, 480h
0x180127a7d  mov     rax, cs:__security_cookie
0x180127a84  xor     rax, rsp
0x180127a87  mov     [rsp+488h+var_18], rax
0x180127a8f  mov     [rsp+488h+ExtCount], 0; ExtCount
0x180127a98  lea     r9, [rsp+488h+Dir]; Dir
0x180127aa0  mov     [rsp+488h+Ext], 0; Ext
0x180127aa9  lea     rdx, [rsp+488h+Drive]; Drive
0x180127aae  mov     edi, 104h
0x180127ab3  mov     [rsp+488h+FilenameCount], 0; FilenameCount
0x180127abc  mov     [rsp+488h+Filename], 0; Filename
0x180127ac5  mov     r8d, edi; DriveCount
0x180127ac8  mov     [rsp+488h+DirCount], rdi; int
0x180127acd  call    cs:__imp__wsplitpath_s
0x180127ad4  nop     dword ptr [rax+rax+00h]
0x180127ad9  test    eax, eax
0x180127adb  jz      short loc_180127B13
0x180127add  mov     edx, 83h; void *
0x180127ae2  mov     rcx, [rsp+488h]; this
0x180127aea  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180127af1  mov     r9d, eax; char *
0x180127af4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180127af9  mov     rcx, [rsp+488h+var_18]
0x180127b01  xor     rcx, rsp; StackCookie
0x180127b04  call    __security_check_cookie
0x180127b09  add     rsp, 480h
0x180127b10  pop     rdi
0x180127b11  retn
0x180127b13  lea     r8, [rsp+488h+Dir]
0x180127b1b  mov     rdx, rdi
0x180127b1e  lea     rcx, [rsp+488h+Drive]
0x180127b23  call    cs:__imp__o_wcscat_s
0x180127b2a  nop     dword ptr [rax+rax+00h]
0x180127b2f  test    eax, eax
0x180127b31  jz      short loc_180127B3A
0x180127b33  mov     edx, 86h
0x180127b38  jmp     short loc_180127AE2
0x180127b3a  mov     rdx, rdi; MaxCount
0x180127b3d  lea     rcx, [rsp+488h+Drive]; Source
0x180127b42  call    wcsnlen_s
0x180127b47  lea     rcx, [rax+1]
0x180127b4b  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180127b52  jnz     short loc_180127B7D
0x180127b54  mov     rcx, [rsp+488h]; this
0x180127b5c  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180127b63  mov     r9d, 80004005h; char *
0x180127b69  mov     edx, 8Bh; void *
0x180127b6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180127b73  mov     eax, 80004005h
0x180127b78  jmp     loc_180127AF9
0x180127b7d  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180127b85  cmp     rcx, 208h
0x180127b8c  jnb     short loc_180127BD7
0x180127b8e  xor     eax, eax
0x180127b90  lea     rdx, [rsp+488h+Drive]; pszPath
0x180127b95  mov     [rsp+rcx+488h+Drive], ax
0x180127b9a  xor     r8d, r8d; psa
0x180127b9d  xor     ecx, ecx; hwnd
0x180127b9f  call    cs:__imp_SHCreateDirectoryExW
0x180127ba6  nop     dword ptr [rax+rax+00h]
0x180127bab  test    eax, eax
0x180127bad  jz      short loc_180127BD0
0x180127baf  cmp     eax, 50h ; 'P'
0x180127bb2  jz      short loc_180127BD0
0x180127bb4  cmp     eax, 0B7h
0x180127bb9  jz      short loc_180127BD0
0x180127bbb  test    eax, eax
0x180127bbd  jle     loc_180127AF9
0x180127bc3  movzx   eax, ax
0x180127bc6  or      eax, 80070000h
0x180127bcb  jmp     loc_180127AF9
0x180127bd0  xor     eax, eax
0x180127bd2  jmp     loc_180127AF9
0x180127bd7  call    __report_rangecheckfailure
```
