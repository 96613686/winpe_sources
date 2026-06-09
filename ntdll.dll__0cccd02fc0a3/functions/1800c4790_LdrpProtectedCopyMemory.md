# LdrpProtectedCopyMemory

- ea: `0x1800c4790`
- end: `0x1800c47ea`
- name: `LdrpProtectedCopyMemory`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800c4790`
- `0x18015ae38`
- `0x180163a80`

## string_xrefs

- `0x180167844`: `LdrpProtectedCopyMemory`

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
0x1800c4790  mov     [rsp+arg_0], rbx
0x1800c4795  mov     [rsp+arg_10], rsi
0x1800c479a  mov     [rsp+arg_18], r9
0x1800c479f  mov     [rsp+arg_8], rdx
0x1800c47a4  push    rdi
0x1800c47a5  sub     rsp, 40h
0x1800c47a9  mov     rdi, r9
0x1800c47ac  mov     rax, r8
0x1800c47af  xor     ebx, ebx
0x1800c47b1  mov     esi, ebx
0x1800c47b3  mov     r8, r9; Size
0x1800c47b6  mov     rcx, rax; void *
0x1800c47b9  call    memmove
0x1800c47be  jmp     short loc_1800C47C9
0x1800c47c0  mov     esi, eax
0x1800c47c2  xor     ebx, ebx
0x1800c47c4  mov     rdi, [rsp+48h+arg_18]
0x1800c47c9  test    esi, esi
0x1800c47cb  cmovns  rbx, rdi
0x1800c47cf  mov     rcx, [rsp+48h+arg_20]
0x1800c47d4  mov     [rcx], rbx
0x1800c47d7  mov     eax, esi
0x1800c47d9  mov     rbx, [rsp+48h+arg_0]
0x1800c47de  mov     rsi, [rsp+48h+arg_10]
0x1800c47e3  add     rsp, 40h
0x1800c47e7  pop     rdi
0x1800c47e8  retn
0x1801677e0  push    rbp
0x1801677e2  sub     rsp, 20h
0x1801677e6  mov     rbp, rdx
0x1801677e9  mov     rax, [rcx]
0x1801677ec  mov     edx, [rax]
0x1801677ee  mov     [rbp+38h], rcx
0x1801677f2  mov     [rbp+20h], edx
0x1801677f5  mov     rax, [rbp+38h]
0x1801677f9  mov     rcx, [rax]
0x1801677fc  mov     [rbp+30h], rcx
0x180167800  mov     eax, [rbp+20h]
0x180167803  cmp     eax, 0C0000006h
0x180167808  jz      short loc_180167814
0x18016780a  mov     eax, [rbp+20h]
0x18016780d  cmp     eax, 0C0000005h
0x180167812  jnz     short loc_180167844
0x180167814  mov     rax, [rbp+30h]
0x180167818  cmp     qword ptr [rax+20h], 0
0x18016781d  jnz     short loc_180167844
0x18016781f  mov     rax, [rbp+30h]
0x180167823  mov     rcx, [rbp+58h]
0x180167827  cmp     [rax+28h], rcx
0x18016782b  jb      short loc_180167844
0x18016782d  mov     rdx, [rbp+30h]
0x180167831  add     rcx, [rbp+68h]
0x180167835  cmp     [rdx+28h], rcx
0x180167839  jnb     short loc_180167844
0x18016783b  mov     dword ptr [rbp+28h], 1
0x180167842  jmp     short loc_180167857
0x180167844  lea     rdx, aLdrpprotectedc; "LdrpProtectedCopyMemory"
0x18016784b  mov     rcx, [rbp+38h]
0x18016784f  call    LdrpGenericExceptionFilter
0x180167854  mov     [rbp+28h], eax
0x180167857  mov     eax, [rbp+28h]
0x18016785a  add     rsp, 20h
0x18016785e  pop     rbp
0x18016785f  retn
```
