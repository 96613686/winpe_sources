# xdr_opaque_auth

- ea: `0x14000c5f4`
- end: `0x14000c64c`
- name: `xdr_opaque_auth`
- size: `88`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b2a0`
- `0x14000b394`
- `0x14000ba50`
- `0x14000c3ec`
- `0x14000d820`
- `0x14000e320`
- `0x14000f388`

## callees

- `0x14000b4d8`
- `0x14000c5f4`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall xdr_opaque_auth(__int64 a1, __int64 a2)
{
  unsigned int (*v4)(void); // rax

  if ( *(_DWORD *)a1 )
  {
    if ( *(_DWORD *)a1 != 1 )
    {
      if ( *(_DWORD *)a1 != 2 )
        return 0;
      return xdr_bytes(a1, a2 + 8, a2 + 16);
    }
    v4 = **(unsigned int (***)(void))(a1 + 8);
  }
  else
  {
    v4 = *(unsigned int (**)(void))(*(_QWORD *)(a1 + 8) + 8LL);
  }
  if ( !v4() )
    return 0;
  return xdr_bytes(a1, a2 + 8, a2 + 16);
}

```

## disassembly

```asm
0x14000c5f4  mov     [rsp+arg_0], rbx
0x14000c5f9  push    rdi
0x14000c5fa  sub     rsp, 20h
0x14000c5fe  cmp     dword ptr [rcx], 0
0x14000c601  mov     rdi, rdx
0x14000c604  mov     rbx, rcx
0x14000c607  jnz     short loc_14000C613
0x14000c609  mov     rax, [rcx+8]
0x14000c60d  mov     rax, [rax+8]
0x14000c611  jmp     short loc_14000C61F
0x14000c613  cmp     dword ptr [rcx], 1
0x14000c616  jnz     short loc_14000C635
0x14000c618  mov     rax, [rcx+8]
0x14000c61c  mov     rax, [rax]
0x14000c61f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c624  test    eax, eax
0x14000c626  jnz     short loc_14000C63A
0x14000c628  xor     eax, eax
0x14000c62a  mov     rbx, [rsp+28h+arg_0]
0x14000c62f  add     rsp, 20h
0x14000c633  pop     rdi
0x14000c634  retn
0x14000c635  cmp     dword ptr [rcx], 2
0x14000c638  jnz     short loc_14000C628
0x14000c63a  lea     r8, [rdi+10h]
0x14000c63e  mov     rcx, rbx
0x14000c641  lea     rdx, [rdi+8]
0x14000c645  call    xdr_bytes
0x14000c64a  jmp     short loc_14000C62A
```
