# ASN1BEREncOpenType

- ea: `0x180007ac0`
- end: `0x180007b05`
- name: `ASN1BEREncOpenType`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007ac0`
- `0x180007c70`
- `0x18000aadd`

## pseudocode

```c
__int64 __fastcall ASN1BEREncOpenType(__int64 a1, unsigned int *a2)
{
  if ( !(unsigned int)ASN1EncCheck(a1, *a2) )
    return 0;
  memcpy_0(*(void **)(a1 + 40), *((const void **)a2 + 1), *a2);
  *(_QWORD *)(a1 + 40) += *a2;
  return 1;
}

```

## disassembly

```asm
0x180007ac0  mov     [rsp+arg_0], rbx
0x180007ac5  push    rdi
0x180007ac6  sub     rsp, 20h
0x180007aca  mov     rbx, rdx
0x180007acd  mov     rdi, rcx
0x180007ad0  mov     edx, [rdx]
0x180007ad2  call    ASN1EncCheck
0x180007ad7  test    eax, eax
0x180007ad9  jz      short loc_180007B01
0x180007adb  mov     r8d, [rbx]; Size
0x180007ade  mov     rdx, [rbx+8]; Src
0x180007ae2  mov     rcx, [rdi+28h]; void *
0x180007ae6  call    memcpy_0
0x180007aeb  mov     eax, [rbx]
0x180007aed  add     [rdi+28h], rax
0x180007af1  mov     eax, 1
0x180007af6  mov     rbx, [rsp+28h+arg_0]
0x180007afb  add     rsp, 20h
0x180007aff  pop     rdi
0x180007b00  retn
0x180007b01  xor     eax, eax
0x180007b03  jmp     short loc_180007AF6
```
