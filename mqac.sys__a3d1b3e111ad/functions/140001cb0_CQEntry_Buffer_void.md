# CQEntry::Buffer(void)

- ea: `0x140001cb0`
- end: `0x140001ccf`
- name: `?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ`
- size: `31`
- prototype: `struct CPacketBuffer *__fastcall(CQEntry *__hidden this)`
- caller_count: `48`
- callee_count: `2`
- tags: ``

## callers

- `0x140002290`
- `0x1400022d0`
- `0x140002650`
- `0x1400041ac`
- `0x140005f08`
- `0x1400060c0`
- `0x1400061fc`
- `0x140006334`
- `0x14000648c`
- `0x140006a74`
- `0x1400078f4`
- `0x140007a88`
- `0x140007e3c`
- `0x14000dc20`
- `0x14000df60`
- `0x140014980`
- `0x140014a58`
- `0x140014ef8`
- `0x140015084`
- `0x140015e04`
- `0x140017884`
- `0x140017b90`
- `0x140017ca4`
- `0x140017d9c`
- `0x140017ec4`
- `0x140018150`
- `0x14001821c`
- `0x1400184cc`
- `0x140018644`
- `0x140018dc8`
- `0x140019284`
- `0x14001a6c0`
- `0x14001c230`
- `0x14001cd90`
- `0x14001d390`
- `0x14001d69c`
- `0x14001dd80`
- `0x14001e0c0`
- `0x14001e4c8`
- `0x14001e634`
- `0x14001f1c4`
- `0x14001f3dc`
- `0x14001f56c`
- `0x14001f714`
- `0x14001f8d4`
- `0x14001fc14`
- `0x14001fcc8`
- `0x14001fe88`

## callees

- `0x140001cb0`
- `0x14000fe84`

## pseudocode

```c
struct CPacketBuffer *__fastcall CQEntry::Buffer(CQEntry *this)
{
  unsigned int v1; // edx

  v1 = *((_DWORD *)this + 4);
  if ( v1 == -1 )
    return 0;
  else
    return (struct CPacketBuffer *)CMMFAllocator::GetAccessibleBuffer(*((CMMFAllocator **)this + 3), v1);
}

```

## disassembly

```asm
0x140001cb0  sub     rsp, 28h
0x140001cb4  mov     edx, [rcx+10h]
0x140001cb7  cmp     edx, 0FFFFFFFFh
0x140001cba  jz      short loc_140001CC7
0x140001cbc  mov     rcx, [rcx+18h]
0x140001cc0  call    ?GetAccessibleBuffer@CMMFAllocator@@QEAAPEAVCAccessibleBlock@@VCAllocatorBlockOffset@@@Z; CMMFAllocator::GetAccessibleBuffer(CAllocatorBlockOffset)
0x140001cc5  jmp     short loc_140001CC9
0x140001cc7  xor     eax, eax
0x140001cc9  add     rsp, 28h
0x140001ccd  retn
```
