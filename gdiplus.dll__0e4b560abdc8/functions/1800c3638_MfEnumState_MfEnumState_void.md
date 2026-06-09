# MfEnumState::~MfEnumState(void)

- ea: `0x1800c3638`
- end: `0x1800c36f1`
- name: `??1MfEnumState@@UEAA@XZ`
- size: `185`
- prototype: `void __fastcall(MfEnumState *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18005de8c`
- `0x1800d1a6c`
- `0x1800e6b80`
- `0x18011d750`

## callees

- `0x1800c3638`

## import_xrefs

- `GDI32!GetStockObject` at `0x1800c3659`
- `GDI32!GetStockObject` at `0x1800c3659`
- `GDI32!SelectObject` at `0x1800c366c`
- `GDI32!SelectObject` at `0x1800c366c`
- `GDI32!DeleteObject` at `0x1800c3681`
- `GDI32!DeleteObject` at `0x1800c36d5`
- `GDI32!DeleteObject` at `0x1800c36e3`
- `GDI32!DeleteObject` at `0x1800c3681`
- `GDI32!DeleteObject` at `0x1800c36d5`
- `GDI32!DeleteObject` at `0x1800c36e3`

## pseudocode

```c
void __fastcall MfEnumState::~MfEnumState(HDC *this)
{
  HGDIOBJ StockObject; // rax
  HDC v3; // rcx
  HGDIOBJ *v4; // rbx
  __int64 v5; // rsi
  HGDIOBJ *v6; // rbx
  __int64 v7; // rdi

  *this = (HDC)&MfEnumState::`vftable';
  StockObject = GetStockObject(13);
  SelectObject(this[2], StockObject);
  v3 = this[8];
  if ( v3 )
    DeleteObject(v3);
  v4 = (HGDIOBJ *)(this + 9);
  v5 = 8;
  do
  {
    if ( *v4 )
      DeleteObject(*v4);
    ++v4;
    --v5;
  }
  while ( v5 );
  v6 = (HGDIOBJ *)(this + 289);
  v7 = 7;
  do
  {
    if ( *v6 )
      DeleteObject(*v6);
    ++v6;
    --v7;
  }
  while ( v7 );
}

```

## disassembly

```asm
0x1800c3638  mov     [rsp+arg_0], rbx
0x1800c363d  mov     [rsp+arg_8], rsi
0x1800c3642  push    rdi
0x1800c3643  sub     rsp, 20h
0x1800c3647  lea     rax, ??_7MfEnumState@@6B@; const MfEnumState::`vftable'
0x1800c364e  mov     rdi, rcx
0x1800c3651  mov     [rcx], rax
0x1800c3654  mov     ecx, 0Dh; i
0x1800c3659  call    cs:__imp_GetStockObject
0x1800c3660  nop     dword ptr [rax+rax+00h]
0x1800c3665  mov     rcx, [rdi+10h]; hdc
0x1800c3669  mov     rdx, rax; h
0x1800c366c  call    cs:__imp_SelectObject
0x1800c3673  nop     dword ptr [rax+rax+00h]
0x1800c3678  mov     rcx, [rdi+40h]; ho
0x1800c367c  test    rcx, rcx
0x1800c367f  jz      short loc_1800C368D
0x1800c3681  call    cs:__imp_DeleteObject
0x1800c3688  nop     dword ptr [rax+rax+00h]
0x1800c368d  lea     rbx, [rdi+48h]
0x1800c3691  mov     esi, 8
0x1800c3696  mov     rcx, [rbx]; ho
0x1800c3699  test    rcx, rcx
0x1800c369c  jnz     short loc_1800C36D5
0x1800c369e  add     rbx, 8
0x1800c36a2  sub     rsi, 1
0x1800c36a6  jnz     short loc_1800C3696
0x1800c36a8  lea     rbx, [rdi+908h]
0x1800c36af  lea     edi, [rsi+7]
0x1800c36b2  mov     rcx, [rbx]; ho
0x1800c36b5  test    rcx, rcx
0x1800c36b8  jnz     short loc_1800C36E3
0x1800c36ba  add     rbx, 8
0x1800c36be  sub     rdi, 1
0x1800c36c2  jnz     short loc_1800C36B2
0x1800c36c4  mov     rbx, [rsp+28h+arg_0]
0x1800c36c9  mov     rsi, [rsp+28h+arg_8]
0x1800c36ce  add     rsp, 20h
0x1800c36d2  pop     rdi
0x1800c36d3  retn
0x1800c36d5  call    cs:__imp_DeleteObject
0x1800c36dc  nop     dword ptr [rax+rax+00h]
0x1800c36e1  jmp     short loc_1800C369E
0x1800c36e3  call    cs:__imp_DeleteObject
0x1800c36ea  nop     dword ptr [rax+rax+00h]
0x1800c36ef  jmp     short loc_1800C36BA
```
