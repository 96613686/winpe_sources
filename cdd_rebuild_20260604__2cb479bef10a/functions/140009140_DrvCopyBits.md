# DrvCopyBits

- ea: `0x140009140`
- end: `0x140009195`
- name: `DrvCopyBits`
- size: `85`
- prototype: `FN_DrvCopyBits`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000919c`

## import_xrefs

- `WIN32K!EngBitBlt` at `0x140009147`

## pseudocode

```c
BOOL __stdcall DrvCopyBits(
        SURFOBJ *psoDest,
        SURFOBJ *psoSrc,
        CLIPOBJ *pco,
        XLATEOBJ *pxlo,
        RECTL *prclDest,
        POINTL *pptlSrc)
{
  struct CDDPDEV *v7; // [rsp+50h] [rbp-18h]

  LODWORD(v7) = 52428;
  return DrvBitBltInternal(psoDest, psoSrc, 0, pco, pxlo, prclDest, pptlSrc, 0, 0, 0, v7, EngBitBlt);
}

```

## disassembly

```asm
0x140009140  mov     r11, rsp
0x140009143  sub     rsp, 68h
0x140009147  mov     rax, cs:__imp_EngBitBlt
0x14000914e  mov     [r11-10h], rax
0x140009152  xor     eax, eax
0x140009154  mov     dword ptr [rsp+68h+var_18], 0CCCCh; struct CDDPDEV *
0x14000915c  mov     [r11-20h], rax
0x140009160  mov     [r11-28h], rax
0x140009164  mov     [r11-30h], rax
0x140009168  mov     rax, [rsp+68h+pptlSrc]
0x140009170  mov     [r11-38h], rax
0x140009174  mov     rax, [rsp+68h+prclDest]
0x14000917c  mov     [r11-40h], rax
0x140009180  mov     [r11-48h], r9
0x140009184  mov     r9, r8; struct _CLIPOBJ *
0x140009187  xor     r8d, r8d; struct _SURFOBJ *
0x14000918a  call    ?DrvBitBltInternal@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@4PEAU_BRUSHOBJ@@4KP6AH0001234454K@Z@Z; DrvBitBltInternal(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))
0x14000918f  add     rsp, 68h
0x140009193  retn
```
