# SBuffer::~SBuffer(void)

- ea: `0x1400010e8`
- end: `0x140001100`
- name: `??1SBuffer@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(void **this)`
- caller_count: `35`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140013f56`
- `0x140013f62`
- `0x140013f7a`
- `0x140013faa`
- `0x140013fe6`
- `0x1400140b2`
- `0x1400140ca`
- `0x1400140e2`
- `0x1400140fa`
- `0x140014112`
- `0x14001412a`
- `0x140014142`
- `0x14001415a`
- `0x140014172`
- `0x14001418a`
- `0x140014196`
- `0x1400141ae`
- `0x1400141f6`
- `0x140014343`
- `0x140014686`
- `0x1400148ad`
- `0x1400148b9`
- `0x1400148c5`
- `0x1400148d1`
- `0x140014901`
- `0x140014919`
- `0x14001493d`
- `0x140014991`
- `0x140014eb5`
- `0x140015033`
- `0x1400156f5`
- `0x140015701`
- `0x1400157c4`
- `0x1400157d0`
- `0x140015b72`

## callees

- `0x1400010e8`
- `0x14000a10c`

## pseudocode

```c
void __fastcall SBuffer::~SBuffer(void **this)
{
  if ( ((_BYTE)this[1] & 8) != 0 )
    operator delete(this[2]);
}

```

## disassembly

```asm
0x1400010e8  sub     rsp, 28h
0x1400010ec  test    byte ptr [rcx+8], 8
0x1400010f0  jz      short loc_1400010FB
0x1400010f2  mov     rcx, [rcx+10h]; lpMem
0x1400010f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400010fb  add     rsp, 28h
0x1400010ff  retn
```
