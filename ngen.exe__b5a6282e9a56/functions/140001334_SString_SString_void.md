# SString::~SString(void)

- ea: `0x140001334`
- end: `0x140001352`
- name: `??1SString@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(void **this)`
- caller_count: `41`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140013f6e`
- `0x140013f86`
- `0x140013f9e`
- `0x140013fda`
- `0x140014076`
- `0x1400140a6`
- `0x1400140be`
- `0x1400140d6`
- `0x1400140ee`
- `0x140014106`
- `0x14001411e`
- `0x140014136`
- `0x14001414e`
- `0x140014166`
- `0x14001417e`
- `0x1400141a2`
- `0x1400141ea`
- `0x140014337`
- `0x14001467a`
- `0x14001486d`
- `0x14001487d`
- `0x14001488d`
- `0x14001489d`
- `0x1400148f5`
- `0x14001490d`
- `0x140014925`
- `0x140014985`
- `0x140014dd3`
- `0x140014deb`
- `0x140014df7`
- `0x140014ea9`
- `0x140015027`
- `0x1400156e5`
- `0x1400157ac`
- `0x1400157b8`
- `0x140015976`
- `0x140015b0e`
- `0x140015b1e`
- `0x140015b2e`
- `0x140015b3e`
- `0x140015b5a`

## callees

- `0x140001334`
- `0x14000a10c`

## pseudocode

```c
void __fastcall SString::~SString(void **this)
{
  if ( ((_BYTE)this[1] & 8) != 0 )
    operator delete(this[2]);
}

```

## disassembly

```asm
0x140001334  mov     [rsp+arg_0], rcx
0x140001339  sub     rsp, 28h
0x14000133d  test    byte ptr [rcx+8], 8
0x140001341  jz      short loc_14000134D
0x140001343  mov     rcx, [rcx+10h]; lpMem
0x140001347  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000134c  nop
0x14000134d  add     rsp, 28h
0x140001351  retn
```
