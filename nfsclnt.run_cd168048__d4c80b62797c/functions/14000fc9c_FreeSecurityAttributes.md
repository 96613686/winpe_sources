# FreeSecurityAttributes

- ea: `0x14000fc9c`
- end: `0x14000fcdf`
- name: `FreeSecurityAttributes`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400030c0`

## callees

- `0x1400016ee`
- `0x14000fc9c`

## pseudocode

```c
void __fastcall FreeSecurityAttributes(void **a1)
{
  void *v2; // rcx

  if ( a1 && *a1 )
  {
    v2 = (void *)*((_QWORD *)*a1 + 1);
    if ( v2 )
    {
      free_0(v2);
      *((_QWORD *)*a1 + 1) = 0;
    }
    free_0(*a1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x14000fc9c  test    rcx, rcx
0x14000fc9f  jz      short locret_14000FCDE
0x14000fca1  push    rbx
0x14000fca2  sub     rsp, 20h
0x14000fca6  mov     rax, [rcx]
0x14000fca9  mov     rbx, rcx
0x14000fcac  test    rax, rax
0x14000fcaf  jz      short loc_14000FCD9
0x14000fcb1  mov     rcx, [rax+8]; Block
0x14000fcb5  test    rcx, rcx
0x14000fcb8  jz      short loc_14000FCCA
0x14000fcba  call    free_0
0x14000fcbf  mov     rax, [rbx]
0x14000fcc2  mov     qword ptr [rax+8], 0
0x14000fcca  mov     rcx, [rbx]; Block
0x14000fccd  call    free_0
0x14000fcd2  mov     qword ptr [rbx], 0
0x14000fcd9  add     rsp, 20h
0x14000fcdd  pop     rbx
0x14000fcde  retn
```
