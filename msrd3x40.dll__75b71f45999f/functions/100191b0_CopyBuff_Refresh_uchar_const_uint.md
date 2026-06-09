# CopyBuff::Refresh(uchar const *,uint)

- ea: `0x100191b0`
- end: `0x10019231`
- name: `?Refresh@CopyBuff@@QAEXPBEI@Z`
- size: `129`
- prototype: `void __thiscall(CopyBuff *__hidden this, const unsigned __int8 *Src, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1001a270`
- `0x1001aa40`
- `0x1001bfb0`
- `0x1004d040`

## callees

- `0x1000fc30`
- `0x100191b0`
- `0x1005e7e8`
- `0x1005f07c`

## pseudocode

```c
void __thiscall CopyBuff::Refresh(CopyBuff *this, const unsigned __int8 *Src, size_t Size)
{
  size_t v4; // eax
  int v5[3]; // [esp+8h] [ebp-14h] BYREF
  void *Block; // [esp+14h] [ebp-8h]
  void *v7; // [esp+18h] [ebp-4h]

  v5[0] = 1;
  Bitmap::Clear((CopyBuff *)((char *)this + 16), *((_DWORD *)this + 6), 8 * *((_DWORD *)this + 5), (struct Err *)v5);
  v4 = 2012;
  *((_DWORD *)this + 10) = 0;
  if ( Size < 0x7DC )
    v4 = Size;
  memcpy((char *)this + 76, Src, v4);
  *((_DWORD *)this + 1) = Size;
  if ( (v5[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v7 )
      operator delete[](v7);
  }
}

```

## disassembly

```asm
0x100191b0  mov     edi, edi
0x100191b2  push    ebp
0x100191b3  mov     ebp, esp
0x100191b5  sub     esp, 14h
0x100191b8  push    esi
0x100191b9  push    edi
0x100191ba  mov     edi, ecx
0x100191bc  mov     [ebp+var_14], 1
0x100191c3  mov     edx, [edi+18h]; unsigned int
0x100191c6  lea     ecx, [edi+10h]; this
0x100191c9  lea     eax, [ebp+var_14]
0x100191cc  push    eax; struct Err *
0x100191cd  mov     eax, [ecx+4]
0x100191d0  shl     eax, 3
0x100191d3  push    eax; unsigned int
0x100191d4  call    ?Clear@Bitmap@@QAIXKKAAVErr@@@Z; Bitmap::Clear(ulong,ulong,Err &)
0x100191d9  mov     esi, [ebp+Size]
0x100191dc  mov     eax, 7DCh
0x100191e1  cmp     esi, eax
0x100191e3  mov     dword ptr [edi+28h], 0
0x100191ea  cmovb   eax, esi
0x100191ed  push    eax; Size
0x100191ee  push    [ebp+Src]; Src
0x100191f1  lea     eax, [edi+4Ch]
0x100191f4  push    eax; void *
0x100191f5  call    _memcpy
0x100191fa  add     esp, 0Ch
0x100191fd  mov     [edi+4], esi
0x10019200  test    [ebp+var_14], 0FFFFFFFEh
0x10019207  pop     edi
0x10019208  pop     esi
0x10019209  jz      short loc_1001922B
0x1001920b  mov     eax, [ebp+Block]
0x1001920e  test    eax, eax
0x10019210  jz      short loc_1001921B
0x10019212  push    eax; Block
0x10019213  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10019218  add     esp, 4
0x1001921b  mov     eax, [ebp+var_4]
0x1001921e  test    eax, eax
0x10019220  jz      short loc_1001922B
0x10019222  push    eax; Block
0x10019223  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10019228  add     esp, 4
0x1001922b  mov     esp, ebp
0x1001922d  pop     ebp
0x1001922e  retn    8
```
