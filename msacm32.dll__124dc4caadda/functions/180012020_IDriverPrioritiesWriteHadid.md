# IDriverPrioritiesWriteHadid

- ea: `0x180012020`
- end: `0x1800120a0`
- name: `IDriverPrioritiesWriteHadid`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001570`

## callees

- `0x180001c40`
- `0x180008810`
- `0x180009270`

## pseudocode

```c
LSTATUS __fastcall IDriverPrioritiesWriteHadid(HKEY a1, const WCHAR *a2, __int64 a3)
{
  wchar_t pszDest[176]; // [rsp+30h] [rbp-178h] BYREF

  StringCchPrintfW(pszDest, 0xB0u, L"%u, %s", *(_DWORD *)(a3 + 56) >= 0, a3 + 120);
  return IRegWriteString(a1, a2, (const BYTE *)pszDest);
}

```

## disassembly

```asm
0x180012020  mov     [rsp+arg_18], rbx
0x180012025  push    rdi
0x180012026  sub     rsp, 1A0h
0x18001202d  mov     rax, cs:__security_cookie
0x180012034  xor     rax, rsp
0x180012037  mov     [rsp+1A8h+var_18], rax
0x18001203f  mov     r9d, [r8+38h]
0x180012043  lea     rax, [r8+78h]
0x180012047  not     r9d
0x18001204a  mov     [rsp+1A8h+var_188], rax
0x18001204f  mov     rdi, rdx
0x180012052  shr     r9d, 1Fh
0x180012056  mov     rbx, rcx
0x180012059  lea     r8, gszPriorityFormat; "%u, %s"
0x180012060  mov     edx, 0B0h; cchDest
0x180012065  lea     rcx, [rsp+1A8h+pszDest]; pszDest
0x18001206a  call    StringCchPrintfW
0x18001206f  lea     r8, [rsp+1A8h+pszDest]
0x180012074  mov     rdx, rdi
0x180012077  mov     rcx, rbx
0x18001207a  call    IRegWriteString
0x18001207f  mov     rcx, [rsp+1A8h+var_18]
0x180012087  xor     rcx, rsp; StackCookie
0x18001208a  call    __security_check_cookie
0x18001208f  mov     rbx, [rsp+1A8h+arg_18]
0x180012097  add     rsp, 1A0h
0x18001209e  pop     rdi
0x18001209f  retn
```
