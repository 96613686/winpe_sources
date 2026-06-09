# WfpWin32ErrorPrint

- ea: `0x180010c94`
- end: `0x180010d44`
- name: `WfpWin32ErrorPrint`
- size: `176`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fda0`
- `0x180010088`
- `0x18001037c`

## callees

- `0x180010c94`
- `0x180011340`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180010d02`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180010d02`

## pseudocode

```c
DWORD __fastcall WfpWin32ErrorPrint(
        __int64 (*a1)(__int64, const wchar_t *, ...),
        __int64 a2,
        unsigned int a3,
        DWORD a4)
{
  wchar_t **v6; // rax
  wchar_t *v7; // rbx
  DWORD result; // eax
  WCHAR Buffer[1000]; // [rsp+40h] [rbp-7F8h] BYREF

  if ( a3 < 7 )
    v6 = (wchar_t **)((char *)&off_180014118 + 8 * a3);
  else
    v6 = off_180014148;
  v7 = *v6;
  result = FormatMessageW(0x1000u, 0, a4, 0, Buffer, 0x3E8u, 0);
  if ( result < 0x3E8 )
    return a1(a2, L"%s%s", v7, Buffer);
  return result;
}

```

## disassembly

```asm
0x180010c94  push    rbx
0x180010c96  push    rsi
0x180010c97  push    rdi
0x180010c98  sub     rsp, 820h
0x180010c9f  mov     rax, cs:__security_cookie
0x180010ca6  xor     rax, rsp
0x180010ca9  mov     [rsp+838h+var_28], rax
0x180010cb1  mov     r10d, r9d
0x180010cb4  mov     rsi, rdx
0x180010cb7  mov     rdi, rcx
0x180010cba  cmp     r8d, 7
0x180010cbe  jb      short loc_180010CC9
0x180010cc0  lea     rax, off_180014148; "            "
0x180010cc7  jmp     short loc_180010CD7
0x180010cc9  mov     eax, r8d
0x180010ccc  lea     rcx, off_180014118
0x180010cd3  lea     rax, [rcx+rax*8]
0x180010cd7  mov     rbx, [rax]
0x180010cda  xor     r9d, r9d; dwLanguageId
0x180010cdd  lea     rax, [rsp+838h+Buffer]
0x180010ce2  mov     [rsp+838h+Arguments], 0; Arguments
0x180010ceb  mov     [rsp+838h+nSize], 3E8h; nSize
0x180010cf3  mov     r8d, r10d; dwMessageId
0x180010cf6  xor     edx, edx; lpSource
0x180010cf8  mov     [rsp+838h+lpBuffer], rax; lpBuffer
0x180010cfd  mov     ecx, 1000h; dwFlags
0x180010d02  call    cs:__imp_FormatMessageW
0x180010d08  cmp     eax, 3E8h
0x180010d0d  jnb     short loc_180010D29
0x180010d0f  lea     r9, [rsp+838h+Buffer]
0x180010d14  mov     r8, rbx
0x180010d17  lea     rdx, aSS; "%s%s"
0x180010d1e  mov     rcx, rsi
0x180010d21  mov     rax, rdi
0x180010d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d29  mov     rcx, [rsp+838h+var_28]
0x180010d31  xor     rcx, rsp; StackCookie
0x180010d34  call    __security_check_cookie
0x180010d39  add     rsp, 820h
0x180010d40  pop     rdi
0x180010d41  pop     rsi
0x180010d42  pop     rbx
0x180010d43  retn
```
