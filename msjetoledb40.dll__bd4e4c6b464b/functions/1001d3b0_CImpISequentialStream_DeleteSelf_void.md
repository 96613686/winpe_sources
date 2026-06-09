# CImpISequentialStream::DeleteSelf(void)

- ea: `0x1001d3b0`
- end: `0x1001d3cb`
- name: `?DeleteSelf@CImpISequentialStream@@UAEXXZ`
- size: `27`
- prototype: `void __thiscall(CImpISequentialStream *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1001d3b0`
- `0x1004cea1`

## pseudocode

```c
void __thiscall CImpISequentialStream::DeleteSelf(CImpISequentialStream *this)
{
  if ( this != (CImpISequentialStream *)4 )
  {
    *((_DWORD *)this - 1) = &CImpISequentialStream::`vftable'{for `ISequentialStream'};
    *(_DWORD *)this = &CImpISequentialStream::`vftable'{for `CStorageObject'};
    operator delete((char *)this - 4);
  }
}

```

## disassembly

```asm
0x1001d3b0  lea     eax, [ecx-4]
0x1001d3b3  test    eax, eax
0x1001d3b5  jz      short locret_1001D3CA
0x1001d3b7  push    eax; Block
0x1001d3b8  mov     dword ptr [eax], offset ??_7CImpISequentialStream@@6BISequentialStream@@@; const CImpISequentialStream::`vftable'{for `ISequentialStream'}
0x1001d3be  mov     dword ptr [ecx], offset ??_7CImpISequentialStream@@6BCStorageObject@@@; const CImpISequentialStream::`vftable'{for `CStorageObject'}
0x1001d3c4  call    ??3@YAXPAX@Z; operator delete(void *)
0x1001d3c9  pop     ecx
0x1001d3ca  retn
```
