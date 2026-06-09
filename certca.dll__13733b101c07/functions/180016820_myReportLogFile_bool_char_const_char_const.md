# myReportLogFile(bool,char const *,char const *)

- ea: `0x180016820`
- end: `0x180016897`
- name: `?myReportLogFile@@YAX_NPEBD1@Z`
- size: `119`
- prototype: `void __fastcall(char, const char *, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a414`

## callees

- `0x180009190`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180016879`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180016879`

## string_xrefs

- `0x180016847`: `Opened`
- `0x180016840`: `Cannot open`
- `0x180016852`: `DbgOpenLogFile`

## pseudocode

```c
void __fastcall myReportLogFile(char a1, const char *a2, const char *a3)
{
  const char *v3; // rax
  CHAR OutputString[528]; // [rsp+30h] [rbp-228h] BYREF

  v3 = "Opened";
  if ( !a1 )
    v3 = "Cannot open";
  StringCchPrintfA(OutputString, 0x208u, "CertLib: %hs: %hs %hs\n", "DbgOpenLogFile", v3, a3);
  OutputDebugStringA(OutputString);
}

```

## disassembly

```asm
0x180016820  sub     rsp, 258h
0x180016827  mov     rax, cs:__security_cookie
0x18001682e  xor     rax, rsp
0x180016831  mov     [rsp+258h+var_18], rax
0x180016839  test    cl, cl
0x18001683b  mov     [rsp+258h+var_230], r8
0x180016840  lea     rdx, aCannotOpen; "Cannot open"
0x180016847  lea     rax, aOpened; "Opened"
0x18001684e  cmovz   rax, rdx
0x180016852  lea     r9, aDbgopenlogfile; "DbgOpenLogFile"
0x180016859  mov     edx, 208h; unsigned __int64
0x18001685e  mov     [rsp+258h+var_238], rax
0x180016863  lea     r8, aCertlibHsHsHs; "CertLib: %hs: %hs %hs\n"
0x18001686a  lea     rcx, [rsp+258h+OutputString]; char *
0x18001686f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180016874  lea     rcx, [rsp+258h+OutputString]; lpOutputString
0x180016879  call    cs:__imp_OutputDebugStringA
0x18001687f  mov     rcx, [rsp+258h+var_18]
0x180016887  xor     rcx, rsp; StackCookie
0x18001688a  call    __security_check_cookie
0x18001688f  add     rsp, 258h
0x180016896  retn
```
