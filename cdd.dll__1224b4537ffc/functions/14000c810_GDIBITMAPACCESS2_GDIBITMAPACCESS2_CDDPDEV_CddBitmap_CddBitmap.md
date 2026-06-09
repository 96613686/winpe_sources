# GDIBITMAPACCESS2::GDIBITMAPACCESS2(CDDPDEV *,CddBitmap *,CddBitmap *)

- ea: `0x14000c810`
- end: `0x14000c889`
- name: `??0GDIBITMAPACCESS2@@QEAA@PEAUCDDPDEV@@PEAVCddBitmap@@1@Z`
- size: `121`
- prototype: `GDIBITMAPACCESS2 *__fastcall(GDIBITMAPACCESS2 *__hidden this, struct CDDPDEV *, struct CddBitmap *, struct CddBitmap *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002504`
- `0x140004904`
- `0x14000a254`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`

## callees

- `0x14000c810`

## pseudocode

```c
GDIBITMAPACCESS2 *__fastcall GDIBITMAPACCESS2::GDIBITMAPACCESS2(
        GDIBITMAPACCESS2 *this,
        struct CDDPDEV *a2,
        struct CddBitmap *a3,
        struct CddBitmap *a4)
{
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_OWORD *)this + 4) = 0;
  *((_OWORD *)this + 5) = 0;
  *((_OWORD *)this + 6) = 0;
  *((_OWORD *)this + 7) = 0;
  *((_QWORD *)this + 16) = a2;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_DWORD *)this + 44) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_BYTE *)this + 192) = a3 && a4;
  return this;
}

```

## disassembly

```asm
0x14000c810  xorps   xmm0, xmm0
0x14000c813  xor     eax, eax
0x14000c815  movups  xmmword ptr [rcx], xmm0
0x14000c818  movups  xmmword ptr [rcx+10h], xmm0
0x14000c81c  movups  xmmword ptr [rcx+20h], xmm0
0x14000c820  movups  xmmword ptr [rcx+30h], xmm0
0x14000c824  movups  xmmword ptr [rcx+40h], xmm0
0x14000c828  movups  xmmword ptr [rcx+50h], xmm0
0x14000c82c  movups  xmmword ptr [rcx+60h], xmm0
0x14000c830  movups  xmmword ptr [rcx+70h], xmm0
0x14000c834  mov     [rcx+80h], rdx
0x14000c83b  mov     [rcx+88h], rax
0x14000c842  mov     [rcx+90h], rax
0x14000c849  mov     [rcx+98h], rax
0x14000c850  mov     [rcx+0A8h], rax
0x14000c857  mov     [rcx+0B0h], eax
0x14000c85d  mov     [rcx+0B8h], rax
0x14000c864  mov     [rcx+0A0h], rax
0x14000c86b  test    r8, r8
0x14000c86e  jz      short loc_14000C875
0x14000c870  test    r9, r9
0x14000c873  jnz     short loc_14000C880
0x14000c875  mov     [rcx+0C0h], al
0x14000c87b  mov     rax, rcx
0x14000c87e  retn
0x14000c880  mov     byte ptr [rcx+0C0h], 1
0x14000c887  jmp     short loc_14000C87B
```
