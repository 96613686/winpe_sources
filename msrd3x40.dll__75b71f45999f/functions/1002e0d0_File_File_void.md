# File::~File(void)

- ea: `0x1002e0d0`
- end: `0x1002e133`
- name: `??1File@@QAE@XZ`
- size: `99`
- prototype: `void __thiscall(File *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1001f440`

## callees

- `0x1002e0d0`
- `0x1002e4e0`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1002e128`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1002e128`

## pseudocode

```c
void __thiscall File::~File(File *this)
{
  int v2[3]; // [esp+4h] [ebp-14h] BYREF
  void *Block; // [esp+10h] [ebp-8h]
  void *v4; // [esp+14h] [ebp-4h]

  v2[0] = 1;
  File::Close(this, (struct Err *)v2);
  if ( *((_DWORD *)this + 1) )
    operator delete[](*((void **)this + 1));
  if ( (v2[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v4 )
      operator delete[](v4);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 20));
}

```

## disassembly

```asm
0x1002e0d0  mov     edi, edi
0x1002e0d2  push    ebp
0x1002e0d3  mov     ebp, esp
0x1002e0d5  sub     esp, 14h
0x1002e0d8  push    esi
0x1002e0d9  lea     eax, [ebp+var_14]
0x1002e0dc  mov     [ebp+var_14], 1
0x1002e0e3  push    eax; struct Err *
0x1002e0e4  mov     esi, ecx
0x1002e0e6  call    ?Close@File@@QAEXAAVErr@@@Z; File::Close(Err &)
0x1002e0eb  mov     eax, [esi+4]
0x1002e0ee  test    eax, eax
0x1002e0f0  jz      short loc_1002E0FB
0x1002e0f2  push    eax; Block
0x1002e0f3  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e0f8  add     esp, 4
0x1002e0fb  test    [ebp+var_14], 0FFFFFFFEh
0x1002e102  jz      short loc_1002E124
0x1002e104  mov     eax, [ebp+Block]
0x1002e107  test    eax, eax
0x1002e109  jz      short loc_1002E114
0x1002e10b  push    eax; Block
0x1002e10c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e111  add     esp, 4
0x1002e114  mov     eax, [ebp+var_4]
0x1002e117  test    eax, eax
0x1002e119  jz      short loc_1002E124
0x1002e11b  push    eax; Block
0x1002e11c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002e121  add     esp, 4
0x1002e124  lea     eax, [esi+14h]
0x1002e127  push    eax; lpCriticalSection
0x1002e128  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1002e12e  pop     esi
0x1002e12f  mov     esp, ebp
0x1002e131  pop     ebp
0x1002e132  retn
```
