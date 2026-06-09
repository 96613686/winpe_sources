# File::`scalar deleting destructor'(uint)

- ea: `0x1001fdb0`
- end: `0x1001fe22`
- name: `??_GFile@@QAEPAXI@Z`
- size: `114`
- prototype: `void *__thiscall(File *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1001f910`
- `0x10022310`

## callees

- `0x1001fdb0`
- `0x1002e4e0`
- `0x1005e74d`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1001fe08`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1001fe08`

## pseudocode

```c
File *__thiscall File::`scalar deleting destructor'(File *this, unsigned int a2)
{
  int v4[3]; // [esp+4h] [ebp-14h] BYREF
  void *Block; // [esp+10h] [ebp-8h]
  void *v6; // [esp+14h] [ebp-4h]

  v4[0] = 1;
  File::Close(this, (struct Err *)v4);
  if ( *((_DWORD *)this + 1) )
    operator delete[](*((void **)this + 1));
  if ( (v4[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v6 )
      operator delete[](v6);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 20));
  operator delete(this, 0x2Cu);
  return this;
}

```

## disassembly

```asm
0x1001fdb0  mov     edi, edi
0x1001fdb2  push    ebp
0x1001fdb3  mov     ebp, esp
0x1001fdb5  sub     esp, 14h
0x1001fdb8  push    esi
0x1001fdb9  lea     eax, [ebp+var_14]
0x1001fdbc  mov     [ebp+var_14], 1
0x1001fdc3  push    eax; struct Err *
0x1001fdc4  mov     esi, ecx
0x1001fdc6  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x1001fdcb  mov     eax, [esi+4]
0x1001fdce  test    eax, eax
0x1001fdd0  jz      short loc_1001FDDB
0x1001fdd2  push    eax; Block
0x1001fdd3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fdd8  add     esp, 4
0x1001fddb  test    [ebp+var_14], 0FFFFFFFEh
0x1001fde2  jz      short loc_1001FE04
0x1001fde4  mov     eax, [ebp+Block]
0x1001fde7  test    eax, eax
0x1001fde9  jz      short loc_1001FDF4
0x1001fdeb  push    eax; Block
0x1001fdec  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fdf1  add     esp, 4
0x1001fdf4  mov     eax, [ebp+var_4]
0x1001fdf7  test    eax, eax
0x1001fdf9  jz      short loc_1001FE04
0x1001fdfb  push    eax; Block
0x1001fdfc  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001fe01  add     esp, 4
0x1001fe04  lea     eax, [esi+14h]
0x1001fe07  push    eax; lpCriticalSection
0x1001fe08  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1001fe0e  push    2Ch ; ','; unsigned int
0x1001fe10  push    esi; Block
0x1001fe11  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001fe16  add     esp, 8
0x1001fe19  mov     eax, esi
0x1001fe1b  pop     esi
0x1001fe1c  mov     esp, ebp
0x1001fe1e  pop     ebp
0x1001fe1f  retn    4
```
