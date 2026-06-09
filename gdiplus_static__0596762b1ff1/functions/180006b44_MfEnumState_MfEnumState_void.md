# MfEnumState::~MfEnumState(void)

- ea: `0x180006b44`
- end: `0x180006be9`
- name: `??1MfEnumState@@UEAA@XZ`
- size: `165`
- prototype: `void __fastcall(MfEnumState *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a9c`
- `0x180006a64`
- `0x1800ecc90`
- `0x1801311f0`

## callees

- `0x180006b44`

## import_xrefs

- `GDI32!GetStockObject` at `0x180006b60`
- `GDI32!GetStockObject` at `0x180006b60`
- `GDI32!SelectObject` at `0x180006b73`
- `GDI32!SelectObject` at `0x180006b73`
- `GDI32!DeleteObject` at `0x180006b88`
- `GDI32!DeleteObject` at `0x180006bcd`
- `GDI32!DeleteObject` at `0x180006bdb`
- `GDI32!DeleteObject` at `0x180006b88`
- `GDI32!DeleteObject` at `0x180006bcd`
- `GDI32!DeleteObject` at `0x180006bdb`

## pseudocode

```c
void __fastcall MfEnumState::~MfEnumState(HDC *this)
{
  HGDIOBJ StockObject; // rax
  HDC v3; // rcx
  __int64 i; // rbx
  HDC v5; // rcx
  __int64 j; // rbx
  HDC v7; // rcx

  *this = (HDC)&MfEnumState::`vftable';
  StockObject = GetStockObject(13);
  SelectObject(this[2], StockObject);
  v3 = this[8];
  if ( v3 )
    DeleteObject(v3);
  for ( i = 0; i != 8; ++i )
  {
    v5 = this[i + 9];
    if ( v5 )
      DeleteObject(v5);
  }
  for ( j = 0; j != 7; ++j )
  {
    v7 = this[j + 289];
    if ( v7 )
      DeleteObject(v7);
  }
}

```

## disassembly

```asm
0x180006b44  mov     [rsp+arg_0], rbx
0x180006b49  push    rdi
0x180006b4a  sub     rsp, 20h
0x180006b4e  lea     rax, ??_7MfEnumState@@6B@; const MfEnumState::`vftable'
0x180006b55  mov     rdi, rcx
0x180006b58  mov     [rcx], rax
0x180006b5b  mov     ecx, 0Dh; i
0x180006b60  call    cs:__imp_GetStockObject
0x180006b67  nop     dword ptr [rax+rax+00h]
0x180006b6c  mov     rcx, [rdi+10h]; hdc
0x180006b70  mov     rdx, rax; h
0x180006b73  call    cs:__imp_SelectObject
0x180006b7a  nop     dword ptr [rax+rax+00h]
0x180006b7f  mov     rcx, [rdi+40h]; ho
0x180006b83  test    rcx, rcx
0x180006b86  jz      short loc_180006B94
0x180006b88  call    cs:__imp_DeleteObject
0x180006b8f  nop     dword ptr [rax+rax+00h]
0x180006b94  xor     ebx, ebx
0x180006b96  mov     rcx, [rdi+rbx*8+48h]; ho
0x180006b9b  test    rcx, rcx
0x180006b9e  jnz     short loc_180006BCD
0x180006ba0  inc     rbx
0x180006ba3  cmp     rbx, 8
0x180006ba7  jnz     short loc_180006B96
0x180006ba9  xor     ebx, ebx
0x180006bab  mov     rcx, [rdi+rbx*8+908h]; ho
0x180006bb3  test    rcx, rcx
0x180006bb6  jnz     short loc_180006BDB
0x180006bb8  inc     rbx
0x180006bbb  cmp     rbx, 7
0x180006bbf  jnz     short loc_180006BAB
0x180006bc1  mov     rbx, [rsp+28h+arg_0]
0x180006bc6  add     rsp, 20h
0x180006bca  pop     rdi
0x180006bcb  retn
0x180006bcd  call    cs:__imp_DeleteObject
0x180006bd4  nop     dword ptr [rax+rax+00h]
0x180006bd9  jmp     short loc_180006BA0
0x180006bdb  call    cs:__imp_DeleteObject
0x180006be2  nop     dword ptr [rax+rax+00h]
0x180006be7  jmp     short loc_180006BB8
```
