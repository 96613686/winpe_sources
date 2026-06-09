# CGdiGraphicContext::`vector deleting destructor'(uint)

- ea: `0x1800d9390`
- end: `0x1800d940b`
- name: `??_ECGdiGraphicContext@@UEAAPEAXI@Z`
- size: `123`
- prototype: `void *__fastcall(CGdiGraphicContext *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800d9390`
- `0x18013d250`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800d93fd`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800d93fd`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800d93ed`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800d93ed`

## pseudocode

```c
CGdiGraphicContext *__fastcall CGdiGraphicContext::`vector deleting destructor'(CGdiGraphicContext *this, char a2)
{
  HDC v4; // rcx

  *(_QWORD *)this = &CGdiGraphicContext::`vftable';
  v4 = (HDC)*((_QWORD *)this + 4);
  if ( v4 )
  {
    SelectObject(v4, *((HGDIOBJ *)this + 5));
    DeleteDC(*((HDC *)this + 4));
  }
  *(_QWORD *)this = &IGraphicContext::`vftable';
  *((_QWORD *)this + 1) = &IDpiAccessor::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x30u);
  return this;
}

```

## disassembly

```asm
0x1800d9390  mov     [rsp+arg_0], rbx
0x1800d9395  push    rdi
0x1800d9396  sub     rsp, 20h
0x1800d939a  lea     rax, ??_7CGdiGraphicContext@@6B@; const CGdiGraphicContext::`vftable'
0x1800d93a1  mov     rbx, rcx
0x1800d93a4  mov     [rcx], rax
0x1800d93a7  mov     edi, edx
0x1800d93a9  mov     rcx, [rcx+20h]; hdc
0x1800d93ad  test    rcx, rcx
0x1800d93b0  jnz     short loc_1800D93E9
0x1800d93b2  lea     rax, ??_7IGraphicContext@@6B@; const IGraphicContext::`vftable'
0x1800d93b9  mov     [rbx], rax
0x1800d93bc  lea     rax, ??_7IDpiAccessor@@6B@; const IDpiAccessor::`vftable'
0x1800d93c3  mov     [rbx+8], rax
0x1800d93c7  test    dil, 1
0x1800d93cb  jz      short loc_1800D93DA
0x1800d93cd  mov     edx, 30h ; '0'; unsigned __int64
0x1800d93d2  mov     rcx, rbx; void *
0x1800d93d5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d93da  mov     rax, rbx
0x1800d93dd  mov     rbx, [rsp+28h+arg_0]
0x1800d93e2  add     rsp, 20h
0x1800d93e6  pop     rdi
0x1800d93e7  retn
0x1800d93e9  mov     rdx, [rbx+28h]; h
0x1800d93ed  call    cs:__imp_SelectObject
0x1800d93f4  nop     dword ptr [rax+rax+00h]
0x1800d93f9  mov     rcx, [rbx+20h]; hdc
0x1800d93fd  call    cs:__imp_DeleteDC
0x1800d9404  nop     dword ptr [rax+rax+00h]
0x1800d9409  jmp     short loc_1800D93B2
```
