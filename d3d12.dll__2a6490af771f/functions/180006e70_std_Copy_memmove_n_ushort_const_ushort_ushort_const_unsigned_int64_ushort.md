# std::_Copy_memmove_n<ushort const *,ushort *>(ushort const *,unsigned __int64,ushort *)

- ea: `0x180006e70`
- end: `0x180006e9e`
- name: `??$_Copy_memmove_n@PEBGPEAG@std@@YAPEAGPEBG_KPEAG@Z`
- size: `46`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800066d0`
- `0x180006cac`
- `0x18000a740`

## callees

- `0x18000c341`

## pseudocode

```c
__int64 __fastcall std::_Copy_memmove_n<unsigned short const *,unsigned short *>(void *Src, __int64 a2, void *a3)
{
  __int64 v4; // rbx

  v4 = 2 * a2;
  memmove_0(a3, Src, 2 * a2);
  return (__int64)a3 + v4;
}

```

## disassembly

```asm
0x180006e70  mov     [rsp+arg_0], rbx
0x180006e75  push    rdi
0x180006e76  sub     rsp, 20h
0x180006e7a  mov     rdi, r8
0x180006e7d  lea     rbx, [rdx+rdx]
0x180006e81  mov     rdx, rcx; Src
0x180006e84  mov     r8, rbx; Size
0x180006e87  mov     rcx, rdi; void *
0x180006e8a  call    memmove_0
0x180006e8f  lea     rax, [rbx+rdi]
0x180006e93  mov     rbx, [rsp+28h+arg_0]
0x180006e98  add     rsp, 20h
0x180006e9c  pop     rdi
0x180006e9d  retn
```
