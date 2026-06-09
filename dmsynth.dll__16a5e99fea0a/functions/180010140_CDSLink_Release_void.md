# CDSLink::Release(void)

- ea: `0x180010140`
- end: `0x180010167`
- name: `?Release@CDSLink@@UEAAKXZ`
- size: `39`
- prototype: `unsigned int __fastcall(CDSLink *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010170`

## callees

- `0x18000e4d0`
- `0x180010140`

## pseudocode

```c
__int64 __fastcall CDSLink::Release(CDSLink *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 20);
  if ( !v1 && this )
    CDSLink::`scalar deleting destructor'(this);
  return v1;
}

```

## disassembly

```asm
0x180010140  push    rbx
0x180010142  sub     rsp, 20h
0x180010146  mov     ebx, 0FFFFFFFFh
0x18001014b  lock xadd [rcx+50h], ebx
0x180010150  sub     ebx, 1
0x180010153  jnz     short loc_18001015F
0x180010155  test    rcx, rcx
0x180010158  jz      short loc_18001015F
0x18001015a  call    ??_GCDSLink@@QEAAPEAXI@Z; CDSLink::`scalar deleting destructor'(uint)
0x18001015f  mov     eax, ebx
0x180010161  add     rsp, 20h
0x180010165  pop     rbx
0x180010166  retn
```
