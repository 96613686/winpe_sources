# CInetLogInformation::ReturnStringInfo(char *,ulong *,char const *,ulong)

- ea: `0x180003604`
- end: `0x180003651`
- name: `?ReturnStringInfo@CInetLogInformation@@AEAAPEADPEADPEAKPEBDK@Z`
- size: `77`
- prototype: `char *__fastcall(CInetLogInformation *this, char *, unsigned int *, const char *, unsigned int Size)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032a0`
- `0x1800032d0`
- `0x1800033e0`

## callees

- `0x180003604`
- `0x180003796`

## pseudocode

```c
char *__fastcall CInetLogInformation::ReturnStringInfo(
        CInetLogInformation *this,
        char *a2,
        unsigned int *a3,
        const char *a4,
        unsigned int Size)
{
  const char *v5; // rbx

  v5 = a4;
  if ( a2 )
  {
    if ( *a3 < Size )
      v5 = 0;
    else
      memcpy_0(a2, a4, Size);
  }
  *a3 = Size;
  return (char *)v5;
}

```

## disassembly

```asm
0x180003604  mov     [rsp+arg_0], rbx
0x180003609  mov     [rsp+arg_8], rsi
0x18000360e  push    rdi
0x18000360f  sub     rsp, 20h
0x180003613  mov     edi, dword ptr [rsp+28h+Size]
0x180003617  mov     rbx, r9
0x18000361a  mov     rsi, r8
0x18000361d  mov     rax, rdx
0x180003620  test    rdx, rdx
0x180003623  jz      short loc_18000363C
0x180003625  cmp     [r8], edi
0x180003628  jb      short loc_18000363A
0x18000362a  mov     r8d, edi; Size
0x18000362d  mov     rdx, rbx; Src
0x180003630  mov     rcx, rax; void *
0x180003633  call    memcpy_0
0x180003638  jmp     short loc_18000363C
0x18000363a  xor     ebx, ebx
0x18000363c  mov     [rsi], edi
0x18000363e  mov     rax, rbx
0x180003641  mov     rbx, [rsp+28h+arg_0]
0x180003646  mov     rsi, [rsp+28h+arg_8]
0x18000364b  add     rsp, 20h
0x18000364f  pop     rdi
0x180003650  retn
```
