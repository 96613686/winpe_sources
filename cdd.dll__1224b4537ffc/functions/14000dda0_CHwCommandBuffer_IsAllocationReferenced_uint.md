# CHwCommandBuffer::IsAllocationReferenced(uint)

- ea: `0x14000dda0`
- end: `0x14000ddc2`
- name: `?IsAllocationReferenced@CHwCommandBuffer@@QEAAHI@Z`
- size: `34`
- prototype: `__int64 __fastcall(CHwCommandBuffer *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000cf80`
- `0x14002ee20`

## callees

- `0x14000dda0`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::IsAllocationReferenced(CHwCommandBuffer *this, int a2)
{
  __int64 i; // rax

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)this + 524) )
      return 0;
    if ( a2 == *((_DWORD *)this + 2 * i + 12) )
      break;
  }
  return 1;
}

```

## disassembly

```asm
0x14000dda0  mov     r9d, [rcx+830h]
0x14000dda7  xor     eax, eax
0x14000dda9  cmp     eax, r9d
0x14000ddac  jnb     short loc_14000DDB8
0x14000ddae  cmp     edx, [rcx+rax*8+30h]
0x14000ddb2  jz      short loc_14000DDBC
0x14000ddb4  inc     eax
0x14000ddb6  jmp     short loc_14000DDA9
0x14000ddb8  xor     eax, eax
0x14000ddba  retn
0x14000ddbc  mov     eax, 1
0x14000ddc1  retn
```
