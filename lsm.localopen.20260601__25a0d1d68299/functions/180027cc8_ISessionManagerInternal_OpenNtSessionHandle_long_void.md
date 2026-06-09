# ISessionManagerInternal::OpenNtSessionHandle(long,void * *)

- ea: `0x180027cc8`
- end: `0x180027dcc`
- name: `?OpenNtSessionHandle@ISessionManagerInternal@@SAJJPEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(int, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180010800`
- `0x180049c40`

## callees

- `0x1800077a0`
- `0x180027cc8`
- `0x180028254`
- `0x18004e850`

## import_xrefs

- `ntdll!NtOpenSession` at `0x180027d73`
- `ntdll!NtOpenSession` at `0x180027d73`
- `ntdll!RtlInitUnicodeString` at `0x180027d35`
- `ntdll!RtlInitUnicodeString` at `0x180027d35`

## string_xrefs

- `0x180027d97`: `ISessionManagerInternal::OpenNtSessionHandle`
- `0x180027d90`: `NtOpenSession failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall ISessionManagerInternal::OpenNtSessionHandle(unsigned int a1, void **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-79h] BYREF
  int v8; // [rsp+30h] [rbp-69h] BYREF
  __int64 v9; // [rsp+38h] [rbp-61h]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+40h] [rbp-59h]
  int v11; // [rsp+48h] [rbp-51h]
  __int128 v12; // [rsp+50h] [rbp-49h]
  WCHAR SourceString[64]; // [rsp+60h] [rbp-39h] BYREF

  v3 = StringCbPrintfW(SourceString, 0x80u, L"\\KernelObjects\\Session%d", a1, 0, 0, 0, 0, 0, 0, 0, 0);
  v4 = v3;
  if ( v3 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    v8 = 48;
    p_DestinationString = &DestinationString;
    v9 = 0;
    v11 = 0;
    v12 = 0;
    v5 = NtOpenSession(a2, 3221225472LL, &v8);
    if ( v5 < 0 )
    {
      v4 = v5 | 0x10000000;
      _DbgPrintMessage(
        8,
        "NtOpenSession failed: 0x%x in %s",
        v5 | 0x10000000u,
        "ISessionManagerInternal::OpenNtSessionHandle");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "StringCbPrintfW failed: 0x%x in %s",
      (unsigned int)v3,
      "ISessionManagerInternal::OpenNtSessionHandle");
  }
  return v4;
}

```

## disassembly

```asm
0x180027cc8  mov     [rsp-8+arg_10], rbx
0x180027ccd  mov     [rsp-8+arg_18], rdi
0x180027cd2  push    rbp
0x180027cd3  lea     rbp, [rsp-57h]
0x180027cd8  sub     rsp, 0F0h
0x180027cdf  mov     rax, cs:__security_cookie
0x180027ce6  xor     rax, rsp
0x180027ce9  mov     [rbp+57h+var_10], rax
0x180027ced  xorps   xmm0, xmm0
0x180027cf0  lea     r8, aKernelobjectsS; "\\KernelObjects\\Session%d"
0x180027cf7  mov     rdi, rdx
0x180027cfa  mov     r9d, ecx
0x180027cfd  mov     edx, 80h; unsigned __int64
0x180027d02  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 *
0x180027d06  movups  [rbp+57h+var_C0], xmm0
0x180027d0a  movups  [rbp+57h+var_B0], xmm0
0x180027d0e  movups  [rbp+57h+var_A0], xmm0
0x180027d12  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180027d16  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027d1b  mov     ebx, eax
0x180027d1d  test    eax, eax
0x180027d1f  jns     short loc_180027D2D
0x180027d21  mov     r8d, eax
0x180027d24  lea     rdx, aStringcbprintf; "StringCbPrintfW failed: 0x%x in %s"
0x180027d2b  jmp     short loc_180027D97
0x180027d2d  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180027d31  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180027d35  call    cs:__imp_RtlInitUnicodeString
0x180027d3c  nop     dword ptr [rax+rax+00h]
0x180027d41  lea     rax, [rbp+57h+DestinationString]
0x180027d45  mov     dword ptr [rbp+57h+var_C0], 30h ; '0'
0x180027d4c  xorps   xmm0, xmm0
0x180027d4f  mov     qword ptr [rbp+57h+var_B0], rax
0x180027d53  lea     r8, [rbp+57h+var_C0]
0x180027d57  mov     qword ptr [rbp+57h+var_C0+8], 0
0x180027d5f  mov     edx, 0C0000000h
0x180027d64  mov     dword ptr [rbp+57h+var_B0+8], 0
0x180027d6b  mov     rcx, rdi
0x180027d6e  movdqu  [rbp+57h+var_A0], xmm0
0x180027d73  call    cs:__imp_NtOpenSession
0x180027d7a  nop     dword ptr [rax+rax+00h]
0x180027d7f  test    eax, eax
0x180027d81  jns     short loc_180027DA8
0x180027d83  mov     ebx, eax
0x180027d85  or      ebx, 10000000h
0x180027d8b  jge     short loc_180027DA8
0x180027d8d  mov     r8d, ebx
0x180027d90  lea     rdx, aNtopensessionF; "NtOpenSession failed: 0x%x in %s"
0x180027d97  lea     r9, aIsessionmanage; "ISessionManagerInternal::OpenNtSessionH"...
0x180027d9e  mov     ecx, 8; int
0x180027da3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027da8  mov     eax, ebx
0x180027daa  mov     rcx, [rbp+57h+var_10]
0x180027dae  xor     rcx, rsp; StackCookie
0x180027db1  call    __security_check_cookie
0x180027db6  lea     r11, [rsp+0F0h+var_s0]
0x180027dbe  mov     rbx, [r11+20h]
0x180027dc2  mov     rdi, [r11+28h]
0x180027dc6  mov     rsp, r11
0x180027dc9  pop     rbp
0x180027dca  retn
```
