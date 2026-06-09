# NullCompress

- ea: `0x1800177b0`
- end: `0x1800177df`
- name: `NullCompress`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800177b0`
- `0x18001b625`

## pseudocode

```c
__int64 __fastcall NullCompress(__int64 a1, const void *a2, size_t a3, void *a4, size_t a5, size_t *a6)
{
  __int64 result; // rax

  if ( a5 >= a3 )
  {
    memcpy_0(a4, a2, a3);
    result = 0;
  }
  else
  {
    result = 122;
  }
  *a6 = a3;
  return result;
}

```

## disassembly

```asm
0x1800177b0  push    rbx
0x1800177b2  sub     rsp, 20h
0x1800177b6  mov     rbx, r8
0x1800177b9  cmp     [rsp+28h+arg_20], r8
0x1800177be  jnb     short loc_1800177C7
0x1800177c0  mov     eax, 7Ah ; 'z'
0x1800177c5  jmp     short loc_1800177D1
0x1800177c7  mov     rcx, r9; void *
0x1800177ca  call    memcpy_0
0x1800177cf  xor     eax, eax
0x1800177d1  mov     rcx, [rsp+28h+arg_28]
0x1800177d6  mov     [rcx], rbx
0x1800177d9  add     rsp, 20h
0x1800177dd  pop     rbx
0x1800177de  retn
```
