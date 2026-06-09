# NsippCopyMemory

- ea: `0x140004ca0`
- end: `0x140004d0a`
- name: `NsippCopyMemory`
- size: `106`
- prototype: `void *__fastcall(void *Src, void **, char, unsigned int, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400043d0`

## callees

- `0x140004ca0`
- `0x1400056e8`
- `0x140006560`

## pseudocode

```c
void *__fastcall NsippCopyMemory(void *Src, void **a2, char a3, unsigned int a4, char a5)
{
  __int64 v5; // rbx
  void *result; // rax
  void *v8; // rax

  v5 = a4;
  if ( !Src || !a4 )
    return 0;
  if ( a3 == 1 )
  {
    v8 = *a2;
    if ( a5 )
      RtlCopyFromUser(v8, Src, a4);
    else
      RtlCopyVolatileMemory(v8, Src, a4);
  }
  result = *a2;
  *a2 = (char *)*a2 + ((v5 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
  return result;
}

```

## disassembly

```asm
0x140004ca0  mov     [rsp+arg_0], rbx
0x140004ca5  push    rdi
0x140004ca6  sub     rsp, 20h
0x140004caa  mov     ebx, r9d
0x140004cad  mov     rdi, rdx
0x140004cb0  test    rcx, rcx
0x140004cb3  jnz     short loc_140004CC3
0x140004cb5  xor     eax, eax
0x140004cb7  mov     rbx, [rsp+28h+arg_0]
0x140004cbc  add     rsp, 20h
0x140004cc0  pop     rdi
0x140004cc1  retn
0x140004cc3  test    r9d, r9d
0x140004cc6  jz      short loc_140004CB5
0x140004cc8  cmp     r8b, 1
0x140004ccc  jnz     short loc_140004CE6
0x140004cce  cmp     [rsp+28h+arg_20], 0
0x140004cd3  mov     r8, rbx; Size
0x140004cd6  mov     rax, [rdx]
0x140004cd9  mov     rdx, rcx; Src
0x140004cdc  mov     rcx, rax; void *
0x140004cdf  jnz     short loc_140004D03
0x140004ce1  call    RtlCopyVolatileMemory
0x140004ce6  mov     rax, [rdi]
0x140004ce9  lea     rcx, [rbx+7]
0x140004ced  mov     rbx, [rsp+28h+arg_0]
0x140004cf2  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140004cf6  add     rcx, rax
0x140004cf9  mov     [rdi], rcx
0x140004cfc  add     rsp, 20h
0x140004d00  pop     rdi
0x140004d01  retn
0x140004d03  call    RtlCopyFromUser
0x140004d08  jmp     short loc_140004CE6
```
