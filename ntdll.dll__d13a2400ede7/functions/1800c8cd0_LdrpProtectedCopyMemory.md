# LdrpProtectedCopyMemory

- ea: `0x1800c8cd0`
- end: `0x1800c8d2a`
- name: `LdrpProtectedCopyMemory`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800c8cd0`
- `0x18015b7c8`
- `0x180164280`

## string_xrefs

- `0x180168124`: `LdrpProtectedCopyMemory`

## pseudocode

```c
__int64 __fastcall LdrpProtectedCopyMemory(__int64 a1, const void *a2, void *a3, size_t a4, size_t *a5)
{
  memmove(a3, a2, a4);
  *a5 = a4;
  return 0;
}

```

## disassembly

```asm
0x1800c8cd0  mov     [rsp+arg_0], rbx
0x1800c8cd5  mov     [rsp+arg_10], rsi
0x1800c8cda  mov     [rsp+arg_18], r9
0x1800c8cdf  mov     [rsp+arg_8], rdx
0x1800c8ce4  push    rdi
0x1800c8ce5  sub     rsp, 40h
0x1800c8ce9  mov     rdi, r9
0x1800c8cec  mov     rax, r8
0x1800c8cef  xor     ebx, ebx
0x1800c8cf1  mov     esi, ebx
0x1800c8cf3  mov     r8, r9; Size
0x1800c8cf6  mov     rcx, rax; void *
0x1800c8cf9  call    memmove
0x1800c8cfe  jmp     short loc_1800C8D09
0x1800c8d00  mov     esi, eax
0x1800c8d02  xor     ebx, ebx
0x1800c8d04  mov     rdi, [rsp+48h+arg_18]
0x1800c8d09  test    esi, esi
0x1800c8d0b  cmovns  rbx, rdi
0x1800c8d0f  mov     rcx, [rsp+48h+arg_20]
0x1800c8d14  mov     [rcx], rbx
0x1800c8d17  mov     eax, esi
0x1800c8d19  mov     rbx, [rsp+48h+arg_0]
0x1800c8d1e  mov     rsi, [rsp+48h+arg_10]
0x1800c8d23  add     rsp, 40h
0x1800c8d27  pop     rdi
0x1800c8d28  retn
0x1801680c0  push    rbp
0x1801680c2  sub     rsp, 20h
0x1801680c6  mov     rbp, rdx
0x1801680c9  mov     rax, [rcx]
0x1801680cc  mov     edx, [rax]
0x1801680ce  mov     [rbp+38h], rcx
0x1801680d2  mov     [rbp+20h], edx
0x1801680d5  mov     rax, [rbp+38h]
0x1801680d9  mov     rcx, [rax]
0x1801680dc  mov     [rbp+30h], rcx
0x1801680e0  mov     eax, [rbp+20h]
0x1801680e3  cmp     eax, 0C0000006h
0x1801680e8  jz      short loc_1801680F4
0x1801680ea  mov     eax, [rbp+20h]
0x1801680ed  cmp     eax, 0C0000005h
0x1801680f2  jnz     short loc_180168124
0x1801680f4  mov     rax, [rbp+30h]
0x1801680f8  cmp     qword ptr [rax+20h], 0
0x1801680fd  jnz     short loc_180168124
0x1801680ff  mov     rax, [rbp+30h]
0x180168103  mov     rcx, [rbp+58h]
0x180168107  cmp     [rax+28h], rcx
0x18016810b  jb      short loc_180168124
0x18016810d  mov     rdx, [rbp+30h]
0x180168111  add     rcx, [rbp+68h]
0x180168115  cmp     [rdx+28h], rcx
0x180168119  jnb     short loc_180168124
0x18016811b  mov     dword ptr [rbp+28h], 1
0x180168122  jmp     short loc_180168137
0x180168124  lea     rdx, aLdrpprotectedc; "LdrpProtectedCopyMemory"
0x18016812b  mov     rcx, [rbp+38h]
0x18016812f  call    LdrpGenericExceptionFilter
0x180168134  mov     [rbp+28h], eax
0x180168137  mov     eax, [rbp+28h]
0x18016813a  add     rsp, 20h
0x18016813e  pop     rbp
0x18016813f  retn
```
