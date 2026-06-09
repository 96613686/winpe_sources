# LongBinaryILockBytes::DeleteSelf(void)

- ea: `0x1001c890`
- end: `0x1001c8ab`
- name: `?DeleteSelf@LongBinaryILockBytes@@UAEXXZ`
- size: `27`
- prototype: `void __thiscall(LongBinaryILockBytes *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1001c890`
- `0x1004cea1`

## pseudocode

```c
void __thiscall LongBinaryILockBytes::DeleteSelf(LongBinaryILockBytes *this)
{
  if ( this != (LongBinaryILockBytes *)4 )
  {
    *((_DWORD *)this - 1) = &LongBinaryILockBytes::`vftable'{for `ILockBytes'};
    *(_DWORD *)this = &LongBinaryILockBytes::`vftable'{for `CStorageObject'};
    operator delete((char *)this - 4);
  }
}

```

## disassembly

```asm
0x1001c890  lea     eax, [ecx-4]
0x1001c893  test    eax, eax
0x1001c895  jz      short locret_1001C8AA
0x1001c897  push    eax; Block
0x1001c898  mov     dword ptr [eax], offset ??_7LongBinaryILockBytes@@6BILockBytes@@@; const LongBinaryILockBytes::`vftable'{for `ILockBytes'}
0x1001c89e  mov     dword ptr [ecx], offset ??_7LongBinaryILockBytes@@6BCStorageObject@@@; const LongBinaryILockBytes::`vftable'{for `CStorageObject'}
0x1001c8a4  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001c8a9  pop     ecx
0x1001c8aa  retn
```
