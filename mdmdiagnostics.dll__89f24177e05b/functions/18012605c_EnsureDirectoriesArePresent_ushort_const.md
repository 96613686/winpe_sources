# EnsureDirectoriesArePresent(ushort const *)

- ea: `0x18012605c`
- end: `0x1801261af`
- name: `?EnsureDirectoriesArePresent@@YAJPEBG@Z`
- size: `339`
- prototype: `signed int __fastcall(const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800faae0`
- `0x1800fad60`
- `0x18010b6d4`
- `0x18010fd74`
- `0x180125c24`

## callees

- `0x180019000`
- `0x180019850`
- `0x1800ece5c`
- `0x180104108`
- `0x18012605c`
- `0x180126438`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801260b5`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801260b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180126104`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180126104`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180126177`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x180126177`

## string_xrefs

- `0x1801260cc`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`
- `0x180126137`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\reportfromstreams\registrydiagnosticreportfromstream.cpp`

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
0x18012605c  push    rdi
0x18012605e  sub     rsp, 480h
0x180126065  mov     rax, cs:__security_cookie
0x18012606c  xor     rax, rsp
0x18012606f  mov     [rsp+488h+var_18], rax
0x180126077  mov     [rsp+488h+ExtCount], 0; ExtCount
0x180126080  lea     r9, [rsp+488h+Dir]; Dir
0x180126088  mov     [rsp+488h+Ext], 0; Ext
0x180126091  lea     rdx, [rsp+488h+Drive]; Drive
0x180126096  mov     edi, 104h
0x18012609b  mov     [rsp+488h+FilenameCount], 0; FilenameCount
0x1801260a4  mov     [rsp+488h+Filename], 0; Filename
0x1801260ad  mov     r8d, edi; DriveCount
0x1801260b0  mov     [rsp+488h+DirCount], rdi; int
0x1801260b5  call    cs:__imp__wsplitpath_s
0x1801260bb  test    eax, eax
0x1801260bd  jz      short loc_1801260F4
0x1801260bf  mov     edx, 83h; void *
0x1801260c4  mov     rcx, [rsp+488h]; this
0x1801260cc  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801260d3  mov     r9d, eax; char *
0x1801260d6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801260db  mov     rcx, [rsp+488h+var_18]
0x1801260e3  xor     rcx, rsp; StackCookie
0x1801260e6  call    __security_check_cookie
0x1801260eb  add     rsp, 480h
0x1801260f2  pop     rdi
0x1801260f3  retn
0x1801260f4  lea     r8, [rsp+488h+Dir]
0x1801260fc  mov     rdx, rdi
0x1801260ff  lea     rcx, [rsp+488h+Drive]
0x180126104  call    cs:__imp__o_wcscat_s
0x18012610a  test    eax, eax
0x18012610c  jz      short loc_180126115
0x18012610e  mov     edx, 86h
0x180126113  jmp     short loc_1801260C4
0x180126115  mov     rdx, rdi; MaxCount
0x180126118  lea     rcx, [rsp+488h+Drive]; Source
0x18012611d  call    wcsnlen_s
0x180126122  lea     rcx, [rax+1]
0x180126126  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18012612d  jnz     short loc_180126155
0x18012612f  mov     rcx, [rsp+488h]; this
0x180126137  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012613e  mov     r9d, 80004005h; char *
0x180126144  mov     edx, 8Bh; void *
0x180126149  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012614e  mov     eax, 80004005h
0x180126153  jmp     short loc_1801260DB
0x180126155  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18012615d  cmp     rcx, 208h
0x180126164  jnb     short loc_1801261A9
0x180126166  xor     eax, eax
0x180126168  lea     rdx, [rsp+488h+Drive]; pszPath
0x18012616d  mov     [rsp+rcx+488h+Drive], ax
0x180126172  xor     r8d, r8d; psa
0x180126175  xor     ecx, ecx; hwnd
0x180126177  call    cs:__imp_SHCreateDirectoryExW
0x18012617d  test    eax, eax
0x18012617f  jz      short loc_1801261A2
0x180126181  cmp     eax, 50h ; 'P'
0x180126184  jz      short loc_1801261A2
0x180126186  cmp     eax, 0B7h
0x18012618b  jz      short loc_1801261A2
0x18012618d  test    eax, eax
0x18012618f  jle     loc_1801260DB
0x180126195  movzx   eax, ax
0x180126198  or      eax, 80070000h
0x18012619d  jmp     loc_1801260DB
0x1801261a2  xor     eax, eax
0x1801261a4  jmp     loc_1801260DB
0x1801261a9  call    __report_rangecheckfailure
```
