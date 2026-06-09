# AllocateCopyBufferNode

- ea: `0x10031f11`
- end: `0x10031f3e`
- name: `AllocateCopyBufferNode`
- size: `45`
- prototype: `int(void)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x10032050`
- `0x10032097`
- `0x100320e5`
- `0x100321bc`
- `0x10032274`

## callees

- `0x1002580a`
- `0x10031f11`
- `0x10035f40`

## pseudocode

```c
int AllocateCopyBufferNode()
{
  void *v0; // esi
  void *v2; // [esp-Ch] [ebp-10h]

  v0 = dword_1003AE78;
  if ( !dword_1003AE78 )
    return MemAllocate(56);
  v2 = dword_1003AE78;
  dword_1003AE78 = *(void **)dword_1003AE78;
  memset(v2, 0, 0x38u);
  return (int)v0;
}

```

## disassembly

```asm
0x10031f11  mov     edi, edi
0x10031f13  push    esi
0x10031f14  mov     esi, dword_1003AE78
0x10031f1a  push    38h ; '8'; Size
0x10031f1c  test    esi, esi
0x10031f1e  jnz     short loc_10031F27
0x10031f20  pop     ecx
0x10031f21  pop     esi
0x10031f22  jmp     _MemAllocate@4; MemAllocate(x)
0x10031f27  mov     ecx, [esi]
0x10031f29  push    0; Val
0x10031f2b  push    esi; void *
0x10031f2c  mov     dword_1003AE78, ecx
0x10031f32  call    _memset
0x10031f37  add     esp, 0Ch
0x10031f3a  mov     eax, esi
0x10031f3c  pop     esi
0x10031f3d  retn
```
