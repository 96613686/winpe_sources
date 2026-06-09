# CGhostWindow::CGhostWindow(HWND__ *,CGhostProcess *)

- ea: `0x180005f24`
- end: `0x180005fe1`
- name: `??0CGhostWindow@@QEAA@PEAUHWND__@@PEAVCGhostProcess@@@Z`
- size: `189`
- prototype: `CGhostWindow *__fastcall(CGhostWindow *__hidden this, HWND, struct CGhostProcess *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800057b8`
- `0x180007e64`
- `0x180009f80`

## callees

- `0x1800032d8`
- `0x180003850`

## pseudocode

```c
CGhostWindow *__fastcall CGhostWindow::CGhostWindow(CGhostWindow *this, HWND a2, struct CGhostProcess *a3)
{
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rdx
  CCountedObject *v6; // rcx
  CGhostWindow *v7; // r9

  CCountedObject::CCountedObject(this);
  *(_QWORD *)(v4 + 16) = v3;
  *(_DWORD *)(v4 + 32) = 0;
  *(_QWORD *)v4 = &CGhostWindow::`vftable';
  *(_QWORD *)(v4 + 48) = 0;
  *(_DWORD *)(v4 + 56) = 0;
  *(_QWORD *)(v4 + 64) = 0;
  *(_QWORD *)(v4 + 136) = 0;
  *(_QWORD *)(v4 + 144) = 0;
  *(_DWORD *)(v4 + 152) = 0;
  *(_QWORD *)(v4 + 160) = 0;
  *(_QWORD *)(v4 + 172) = 0;
  *(_QWORD *)(v4 + 184) = 0;
  *(_QWORD *)(v4 + 192) = 0;
  *(_QWORD *)(v4 + 200) = 0;
  *(_QWORD *)(v4 + 208) = 0;
  *(_QWORD *)(v4 + 216) = 0;
  *(_QWORD *)(v4 + 224) = 0;
  *(_QWORD *)(v4 + 24) = 1;
  *(_QWORD *)(v4 + 40) = v5;
  *(_BYTE *)(v4 + 168) = -1;
  *(_OWORD *)(v4 + 72) = 0;
  *(_OWORD *)(v4 + 88) = 0;
  *(_OWORD *)(v4 + 104) = 0;
  *(_OWORD *)(v4 + 116) = 0;
  v6 = *(CCountedObject **)(v4 + 16);
  *(_DWORD *)(v4 + 72) = 60;
  CCountedObject::AddRef(v6);
  return v7;
}

```

## disassembly

```asm
0x180005f24  sub     rsp, 28h
0x180005f28  mov     r9, rcx
0x180005f2b  call    ??0CCountedObject@@IEAA@XZ; CCountedObject::CCountedObject(void)
0x180005f30  xor     eax, eax
0x180005f32  mov     [r9+10h], r8
0x180005f36  mov     [r9+20h], eax
0x180005f3a  lea     rcx, ??_7CGhostWindow@@6B@; const CGhostWindow::`vftable'
0x180005f41  mov     [r9], rcx
0x180005f44  xorps   xmm0, xmm0
0x180005f47  mov     [r9+30h], rax
0x180005f4b  mov     [r9+38h], eax
0x180005f4f  mov     [r9+40h], rax
0x180005f53  mov     [r9+88h], rax
0x180005f5a  mov     [r9+90h], rax
0x180005f61  mov     [r9+98h], eax
0x180005f68  mov     [r9+0A0h], rax
0x180005f6f  mov     [r9+0ACh], rax
0x180005f76  mov     [r9+0B8h], rax
0x180005f7d  mov     [r9+0C0h], rax
0x180005f84  mov     [r9+0C8h], rax
0x180005f8b  mov     [r9+0D0h], rax
0x180005f92  mov     [r9+0D8h], rax
0x180005f99  mov     [r9+0E0h], rax
0x180005fa0  mov     qword ptr [r9+18h], 1
0x180005fa8  mov     [r9+28h], rdx
0x180005fac  mov     byte ptr [r9+0A8h], 0FFh
0x180005fb4  movups  xmmword ptr [r9+48h], xmm0
0x180005fb9  movups  xmmword ptr [r9+58h], xmm0
0x180005fbe  movups  xmmword ptr [r9+68h], xmm0
0x180005fc3  movups  xmmword ptr [r9+74h], xmm0
0x180005fc8  mov     rcx, [r9+10h]; this
0x180005fcc  mov     dword ptr [r9+48h], 3Ch ; '<'
0x180005fd4  call    ?AddRef@CCountedObject@@QEAAXXZ; CCountedObject::AddRef(void)
0x180005fd9  mov     rax, r9
0x180005fdc  add     rsp, 28h
0x180005fe0  retn
```
