# _dynamic_atexit_destructor_for__Sys__

- ea: `0x10062a00`
- end: `0x10062aaf`
- name: `_dynamic_atexit_destructor_for__Sys__`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1005cbf0`
- `0x1005e7e8`
- `0x10062a00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10062a45`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10062a45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10062a53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10062a70`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10062a53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x10062a70`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x10062a22`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x10062a35`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x10062a22`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x10062a35`

## pseudocode

```c
void __cdecl dynamic_atexit_destructor_for__Sys__()
{
  void *v0; // eax

  v0 = lpAddress;
  if ( lpAddress )
  {
    if ( dword_10066918 )
    {
      VirtualFree(lpAddress, dword_10066918 << dword_10066914, 0x4000u);
      v0 = lpAddress;
    }
    VirtualFree(v0, 0, 0x8000u);
  }
  if ( dword_10066928 )
    _free(dword_10066928);
  DeleteCriticalSection(&stru_10066950);
  if ( dword_10066944 )
    operator delete[](dword_10066944);
  DeleteCriticalSection(&stru_100668F8);
  Queue::~Queue(&stru_100668BC);
  if ( (Sys & 0xFFFFFFFE) != 0 )
  {
    if ( *(&Sys + 3) )
      operator delete[](*(&Sys + 3));
    if ( Block )
      operator delete[](Block);
  }
}

```

## disassembly

```asm
0x10062a00  mov     eax, lpAddress
0x10062a05  test    eax, eax
0x10062a07  jz      short loc_10062A3B
0x10062a09  mov     edx, dword_10066918
0x10062a0f  test    edx, edx
0x10062a11  jz      short loc_10062A2D
0x10062a13  mov     ecx, dword_10066914
0x10062a19  push    4000h; dwFreeType
0x10062a1e  shl     edx, cl
0x10062a20  push    edx; dwSize
0x10062a21  push    eax; lpAddress
0x10062a22  call    ds:__imp__VirtualFree@12; VirtualFree(x,x,x)
0x10062a28  mov     eax, lpAddress
0x10062a2d  push    8000h; dwFreeType
0x10062a32  push    0; dwSize
0x10062a34  push    eax; lpAddress
0x10062a35  call    ds:__imp__VirtualFree@12; VirtualFree(x,x,x)
0x10062a3b  mov     eax, dword_10066928
0x10062a40  test    eax, eax
0x10062a42  jz      short loc_10062A4E
0x10062a44  push    eax; Block
0x10062a45  call    ds:__imp__free
0x10062a4b  add     esp, 4
0x10062a4e  push    offset stru_10066950; lpCriticalSection
0x10062a53  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10062a59  mov     eax, dword_10066944
0x10062a5e  test    eax, eax
0x10062a60  jz      short loc_10062A6B
0x10062a62  push    eax; Block
0x10062a63  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10062a68  add     esp, 4
0x10062a6b  push    offset stru_100668F8; lpCriticalSection
0x10062a70  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10062a76  mov     ecx, offset stru_100668BC; lpCriticalSection
0x10062a7b  call    ??1Queue@@QAE@XZ; Queue::~Queue(void)
0x10062a80  test    dword ptr ?Sys@@3VSystem@@A, 0FFFFFFFEh; System Sys
0x10062a8a  jz      short locret_10062AAE
0x10062a8c  mov     eax, dword ptr ?Sys@@3VSystem@@A+0Ch; System Sys
0x10062a91  test    eax, eax
0x10062a93  jz      short loc_10062A9E
0x10062a95  push    eax; Block
0x10062a96  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10062a9b  add     esp, 4
0x10062a9e  mov     eax, Block
0x10062aa3  test    eax, eax
0x10062aa5  jz      short locret_10062AAE
0x10062aa7  push    eax; Block
0x10062aa8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10062aad  pop     ecx
0x10062aae  retn
```
