# CDropCaret::ShowCaret(void)

- ea: `0x18005b77c`
- end: `0x18005b838`
- name: `?ShowCaret@CDropCaret@@QEAAXXZ`
- size: `188`
- prototype: `void __fastcall(CDropCaret *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18005b090`
- `0x18005b840`

## callees

- `0x18005b77c`

## import_xrefs

- `GDI32!LineTo` at `0x18005b7f9`
- `GDI32!LineTo` at `0x18005b7f9`
- `GDI32!MoveToEx` at `0x18005b7de`
- `GDI32!MoveToEx` at `0x18005b7de`
- `GDI32!CreatePen` at `0x18005b7a1`
- `GDI32!CreatePen` at `0x18005b7a1`
- `GDI32!DeleteObject` at `0x18005b81b`
- `GDI32!DeleteObject` at `0x18005b81b`
- `GDI32!SelectObject` at `0x18005b7bc`
- `GDI32!SelectObject` at `0x18005b80c`
- `GDI32!SelectObject` at `0x18005b7bc`
- `GDI32!SelectObject` at `0x18005b80c`

## pseudocode

```c
void __fastcall CDropCaret::ShowCaret(CDropCaret *this)
{
  HPEN Pen; // rax
  HPEN v3; // rdi
  HGDIOBJ v4; // rsi

  if ( *((_DWORD *)this + 5) != -1 )
  {
    Pen = CreatePen(0, 1, 0);
    v3 = Pen;
    if ( Pen )
    {
      v4 = SelectObject(*((HDC *)this + 1), Pen);
      if ( v4 )
      {
        MoveToEx(*((HDC *)this + 1), *((_DWORD *)this + 7), *((_DWORD *)this + 8), 0);
        LineTo(*((HDC *)this + 1), *((_DWORD *)this + 7), *((_DWORD *)this + 5) + *((_DWORD *)this + 8));
        SelectObject(*((HDC *)this + 1), v4);
      }
      DeleteObject(v3);
    }
  }
}

```

## disassembly

```asm
0x18005b77c  mov     [rsp+arg_0], rbx
0x18005b781  mov     [rsp+arg_8], rsi
0x18005b786  push    rdi
0x18005b787  sub     rsp, 20h
0x18005b78b  cmp     dword ptr [rcx+14h], 0FFFFFFFFh
0x18005b78f  mov     rbx, rcx
0x18005b792  jz      loc_18005B827
0x18005b798  xor     r8d, r8d; color
0x18005b79b  xor     ecx, ecx; iStyle
0x18005b79d  lea     edx, [r8+1]; cWidth
0x18005b7a1  call    cs:__imp_CreatePen
0x18005b7a8  nop     dword ptr [rax+rax+00h]
0x18005b7ad  mov     rdi, rax
0x18005b7b0  test    rax, rax
0x18005b7b3  jz      short loc_18005B827
0x18005b7b5  mov     rcx, [rbx+8]; hdc
0x18005b7b9  mov     rdx, rax; h
0x18005b7bc  call    cs:__imp_SelectObject
0x18005b7c3  nop     dword ptr [rax+rax+00h]
0x18005b7c8  mov     rsi, rax
0x18005b7cb  test    rax, rax
0x18005b7ce  jz      short loc_18005B818
0x18005b7d0  mov     r8d, [rbx+20h]; y
0x18005b7d4  xor     r9d, r9d; lppt
0x18005b7d7  mov     edx, [rbx+1Ch]; x
0x18005b7da  mov     rcx, [rbx+8]; hdc
0x18005b7de  call    cs:__imp_MoveToEx
0x18005b7e5  nop     dword ptr [rax+rax+00h]
0x18005b7ea  mov     r8d, [rbx+20h]
0x18005b7ee  add     r8d, [rbx+14h]; y
0x18005b7f2  mov     edx, [rbx+1Ch]; x
0x18005b7f5  mov     rcx, [rbx+8]; hdc
0x18005b7f9  call    cs:__imp_LineTo
0x18005b800  nop     dword ptr [rax+rax+00h]
0x18005b805  mov     rcx, [rbx+8]; hdc
0x18005b809  mov     rdx, rsi; h
0x18005b80c  call    cs:__imp_SelectObject
0x18005b813  nop     dword ptr [rax+rax+00h]
0x18005b818  mov     rcx, rdi; ho
0x18005b81b  call    cs:__imp_DeleteObject
0x18005b822  nop     dword ptr [rax+rax+00h]
0x18005b827  mov     rbx, [rsp+28h+arg_0]
0x18005b82c  mov     rsi, [rsp+28h+arg_8]
0x18005b831  add     rsp, 20h
0x18005b835  pop     rdi
0x18005b836  retn
```
