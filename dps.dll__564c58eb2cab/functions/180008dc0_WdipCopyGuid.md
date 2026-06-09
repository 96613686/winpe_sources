# WdipCopyGuid

- ea: `0x180008dc0`
- end: `0x180008dd1`
- name: `WdipCopyGuid`
- size: `17`
- prototype: `void __fastcall(_OWORD *, _OWORD *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180001830`
- `0x180002510`
- `0x180003020`
- `0x18000b7ec`
- `0x18000bdf4`
- `0x18000c21c`
- `0x180011580`
- `0x180011714`
- `0x1800118f0`
- `0x180011c6c`
- `0x180011eec`
- `0x180011fd4`
- `0x180012934`
- `0x180012e2c`

## callees

- `0x180008dc0`

## pseudocode

```c
void __fastcall WdipCopyGuid(_OWORD *a1, _OWORD *a2)
{
  if ( a1 )
  {
    if ( a2 )
      *a1 = *a2;
  }
}

```

## disassembly

```asm
0x180008dc0  test    rcx, rcx
0x180008dc3  jz      short locret_180008DD0
0x180008dc5  test    rdx, rdx
0x180008dc8  jz      short locret_180008DD0
0x180008dca  movups  xmm0, xmmword ptr [rdx]
0x180008dcd  movups  xmmword ptr [rcx], xmm0
0x180008dd0  retn
```
