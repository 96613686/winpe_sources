# std::_Uninitialized_move<ushort *,std::allocator<ushort>>(ushort * const,ushort * const,ushort *,std::allocator<ushort> &)

- ea: `0x18000a84c`
- end: `0x18000a883`
- name: `??$_Uninitialized_move@PEAGV?$allocator@G@std@@@std@@YAPEAGQEAG0PEAGAEAV?$allocator@G@0@@Z`
- size: `55`
- prototype: `char *__fastcall(void *, __int64, char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009c38`
- `0x18000a10c`
- `0x180014102`
- `0x180014176`

## callees

- `0x180009b60`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<unsigned short *>(void *a1, __int64 a2, char *a3)
{
  std::_Copy_memmove<unsigned short *,unsigned short *>(a1, a2, a3);
  return &a3[2 * ((a2 - (__int64)a1) >> 1)];
}

```

## disassembly

```asm
0x18000a84c  mov     [rsp+arg_0], rbx
0x18000a851  mov     [rsp+arg_8], rsi
0x18000a856  push    rdi
0x18000a857  sub     rsp, 20h
0x18000a85b  mov     rsi, r8
0x18000a85e  mov     rdi, rdx
0x18000a861  mov     rbx, rcx
0x18000a864  call    ??$_Copy_memmove@PEAGPEAG@std@@YAPEAGPEAG00@Z; std::_Copy_memmove<ushort *,ushort *>(ushort *,ushort *,ushort *)
0x18000a869  sub     rdi, rbx
0x18000a86c  mov     rbx, [rsp+28h+arg_0]
0x18000a871  sar     rdi, 1
0x18000a874  lea     rax, [rsi+rdi*2]
0x18000a878  mov     rsi, [rsp+28h+arg_8]
0x18000a87d  add     rsp, 20h
0x18000a881  pop     rdi
0x18000a882  retn
```
