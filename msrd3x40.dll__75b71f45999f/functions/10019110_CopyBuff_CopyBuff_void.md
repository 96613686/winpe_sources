# CopyBuff::CopyBuff(void)

- ea: `0x10019110`
- end: `0x100191a7`
- name: `??0CopyBuff@@QAE@XZ`
- size: `151`
- prototype: `CopyBuff *__thiscall(CopyBuff *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1001a270`
- `0x1001aa40`
- `0x1004d040`

## callees

- `0x1000fc30`
- `0x10019110`
- `0x1005e7e8`

## pseudocode

```c
CopyBuff *__thiscall CopyBuff::CopyBuff(CopyBuff *this)
{
  Bitmap *v2; // ecx
  bool v3; // zf
  int v5[3]; // [esp+8h] [ebp-14h] BYREF
  void *Block; // [esp+14h] [ebp-8h]
  void *v7; // [esp+18h] [ebp-4h]

  v5[0] = 1;
  v2 = (CopyBuff *)((char *)this + 16);
  *((_DWORD *)v2 + 2) = 0;
  *((_DWORD *)v2 + 1) = 32;
  *((_DWORD *)this + 1) = 0;
  *(_DWORD *)this = (char *)this + 76;
  *((_DWORD *)this + 2) = 2012;
  *(_DWORD *)v2 = (char *)this + 44;
  *((_DWORD *)this + 9) = 0;
  *((_DWORD *)this + 7) = (char *)this + 40;
  *((_DWORD *)this + 8) = 4;
  Bitmap::Clear(v2, 0, 0x100u, (struct Err *)v5);
  v3 = (v5[0] & 0xFFFFFFFE) == 0;
  *((_DWORD *)this + 10) = 0;
  if ( !v3 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v7 )
      operator delete[](v7);
  }
  return this;
}

```

## disassembly

```asm
0x10019110  mov     edi, edi
0x10019112  push    ebp
0x10019113  mov     ebp, esp
0x10019115  sub     esp, 14h
0x10019118  push    esi
0x10019119  push    edi
0x1001911a  mov     edi, ecx
0x1001911c  mov     [ebp+var_14], 1
0x10019123  lea     ecx, [edi+10h]; this
0x10019126  xor     edx, edx; unsigned int
0x10019128  mov     dword ptr [ecx+8], 0
0x1001912f  mov     dword ptr [ecx+4], 20h ; ' '
0x10019136  lea     eax, [edi+4Ch]
0x10019139  mov     dword ptr [edi+4], 0
0x10019140  mov     [edi], eax
0x10019142  lea     esi, [edi+28h]
0x10019145  lea     eax, [edi+2Ch]
0x10019148  mov     dword ptr [edi+8], 7DCh
0x1001914f  mov     [ecx], eax
0x10019151  lea     eax, [ebp+var_14]
0x10019154  push    eax; struct Err *
0x10019155  push    100h; unsigned int
0x1001915a  mov     dword ptr [edi+24h], 0
0x10019161  mov     [edi+1Ch], esi
0x10019164  mov     dword ptr [edi+20h], 4
0x1001916b  call    ?Clear@Bitmap@@QAIXKKAAVErr@@@Z; Bitmap::Clear(ulong,ulong,Err &)
0x10019170  test    [ebp+var_14], 0FFFFFFFEh
0x10019177  mov     dword ptr [esi], 0
0x1001917d  jz      short loc_1001919F
0x1001917f  mov     eax, [ebp+Block]
0x10019182  test    eax, eax
0x10019184  jz      short loc_1001918F
0x10019186  push    eax; Block
0x10019187  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001918c  add     esp, 4
0x1001918f  mov     eax, [ebp+var_4]
0x10019192  test    eax, eax
0x10019194  jz      short loc_1001919F
0x10019196  push    eax; Block
0x10019197  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001919c  add     esp, 4
0x1001919f  mov     eax, edi
0x100191a1  pop     edi
0x100191a2  pop     esi
0x100191a3  mov     esp, ebp
0x100191a5  pop     ebp
0x100191a6  retn
```
