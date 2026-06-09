# MI_ReportErrorDetails_FromFOpen

- ea: `0x180007dc0`
- end: `0x180007e8e`
- name: `MI_ReportErrorDetails_FromFOpen`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180028948`
- `0x1800290f4`

## callees

- `0x180006e64`
- `0x180007c80`
- `0x180044842`
- `0x180044880`

## import_xrefs

- `msvcrt!_wcserror_s` at `0x180007e04`
- `msvcrt!_wcserror_s` at `0x180007e04`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180007e19`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180007e19`

## string_xrefs

- `0x180007e0d`: `mpunits.dll`
- `0x180007e43`: `FAILED-TO-OPEN-FILE`

## pseudocode

```c
__int64 __fastcall MI_ReportErrorDetails_FromFOpen(__int64 a1, int a2, __int64 a3)
{
  HMODULE ModuleHandleA; // rax
  wchar_t Buffer[1024]; // [rsp+40h] [rbp-828h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  _wcserror_s(Buffer, 0x400u, a2);
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  Intlstr_FormatString_FormatMessage(ModuleHandleA, 2008, a1);
  return MI_ReportErrorDetails_ForCustomError(a2, (int)L"ERRNO", a3, (__int64)L"FAILED-TO-OPEN-FILE");
}

```

## disassembly

```asm
0x180007dc0  push    rbx
0x180007dc2  push    rsi
0x180007dc3  push    rdi
0x180007dc4  sub     rsp, 850h
0x180007dcb  mov     rax, cs:__security_cookie
0x180007dd2  xor     rax, rsp
0x180007dd5  mov     [rsp+868h+var_28], rax
0x180007ddd  mov     rdi, r8
0x180007de0  mov     esi, edx
0x180007de2  mov     rbx, rcx
0x180007de5  xor     edx, edx; Val
0x180007de7  mov     r8d, 800h; Size
0x180007ded  lea     rcx, [rsp+868h+Buffer]; void *
0x180007df2  call    memset_0
0x180007df7  mov     r8d, esi; ErrorNumber
0x180007dfa  lea     rcx, [rsp+868h+Buffer]; Buffer
0x180007dff  mov     edx, 400h; SizeInWords
0x180007e04  call    cs:__imp__wcserror_s
0x180007e0a  xorps   xmm0, xmm0
0x180007e0d  lea     rcx, ModuleName; "mpunits.dll"
0x180007e14  movups  [rsp+868h+var_838], xmm0
0x180007e19  call    cs:__imp_GetModuleHandleA
0x180007e1f  lea     r9, [rsp+868h+Buffer]
0x180007e24  mov     r8, rbx
0x180007e27  mov     rcx, rax
0x180007e2a  mov     edx, 7D8h
0x180007e2f  call    _Intlstr_FormatString_FormatMessage
0x180007e34  mov     qword ptr [rsp+868h+var_838], rax
0x180007e39  lea     r9, [rsp+868h+var_838]
0x180007e3e  mov     byte ptr [rsp+868h+var_838+8], 1
0x180007e43  lea     rax, aFailedToOpenFi; "FAILED-TO-OPEN-FILE"
0x180007e4a  movaps  xmm0, [rsp+868h+var_838]
0x180007e4f  lea     rdx, aErrno; "ERRNO"
0x180007e56  mov     [rsp+868h+var_840], rax; __int64
0x180007e5b  mov     r8d, 1
0x180007e61  mov     ecx, esi; int
0x180007e63  mov     [rsp+868h+var_848], rdi; __int64
0x180007e68  movdqa  [rsp+868h+var_838], xmm0
0x180007e6e  call    MI_ReportErrorDetails_ForCustomError
0x180007e73  mov     rcx, [rsp+868h+var_28]
0x180007e7b  xor     rcx, rsp; StackCookie
0x180007e7e  call    __security_check_cookie
0x180007e83  add     rsp, 850h
0x180007e8a  pop     rdi
0x180007e8b  pop     rsi
0x180007e8c  pop     rbx
0x180007e8d  retn
```
