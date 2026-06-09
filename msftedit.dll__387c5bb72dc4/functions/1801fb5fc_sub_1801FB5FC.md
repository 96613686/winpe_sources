# sub_1801FB5FC

- ea: `0x1801fb5fc`
- end: `0x1801fb69e`
- name: `sub_1801FB5FC`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1801fea58`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fb627`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fb684`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fb627`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fb684`
- `ext-ms-win-gdi-draw-l1-1-1!CreatePen` at `0x1801fb618`
- `ext-ms-win-gdi-draw-l1-1-1!CreatePen` at `0x1801fb618`
- `ext-ms-win-gdi-draw-l1-1-0!MoveToEx` at `0x1801fb66a`
- `ext-ms-win-gdi-draw-l1-1-0!MoveToEx` at `0x1801fb66a`
- `ext-ms-win-gdi-draw-l1-1-0!LineTo` at `0x1801fb678`
- `ext-ms-win-gdi-draw-l1-1-0!LineTo` at `0x1801fb678`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801fb697`

## pseudocode

```c
BOOL __fastcall sub_1801FB5FC(__int64 a1, HDC a2, COLORREF a3, int a4, int a5, int a6)
{
  int v8; // edx
  HPEN Pen; // rbp
  HGDIOBJ v10; // rax
  char v11; // r9
  int v12; // edi
  void *v13; // rsi
  int v14; // ebx
  int v15; // edx

  v8 = -a4;
  if ( a4 > 0 )
    v8 = a4;
  Pen = CreatePen(0, v8, a3);
  v10 = SelectObject(a2, Pen);
  v11 = *(_BYTE *)(a1 + 112);
  v12 = a5;
  v13 = v10;
  v14 = a6;
  v15 = a5 - a6;
  if ( v11 )
  {
    v14 = a5 / 2;
  }
  else
  {
    v15 = a5 / 2;
    v12 = a5 / 2;
  }
  MoveToEx(a2, v15, v11 != 0 ? a5 / 2 : 0, 0);
  LineTo(a2, v12, v14);
  SelectObject(a2, v13);
  return DeleteObject(Pen);
}

```

## disassembly

```asm
0x1801fb5fc  push    rbx
0x1801fb5fe  push    rbp
0x1801fb5ff  push    rsi
0x1801fb600  push    rdi
0x1801fb601  push    r14
0x1801fb603  sub     rsp, 20h
0x1801fb607  mov     r14, rdx
0x1801fb60a  mov     rbx, rcx
0x1801fb60d  mov     edx, r9d
0x1801fb610  neg     edx
0x1801fb612  cmovs   edx, r9d; cWidth
0x1801fb616  xor     ecx, ecx; iStyle
0x1801fb618  call    cs:CreatePen
0x1801fb61e  mov     rdx, rax; h
0x1801fb621  mov     rcx, r14; hdc
0x1801fb624  mov     rbp, rax
0x1801fb627  call    cs:SelectObject
0x1801fb62d  mov     r9b, [rbx+70h]
0x1801fb631  mov     ecx, 2
0x1801fb636  mov     edi, [rsp+48h+arg_20]
0x1801fb63a  mov     rsi, rax
0x1801fb63d  mov     ebx, [rsp+48h+arg_28]
0x1801fb641  mov     eax, edi
0x1801fb643  cdq
0x1801fb644  idiv    ecx
0x1801fb646  mov     cl, r9b
0x1801fb649  mov     edx, edi
0x1801fb64b  sub     edx, ebx
0x1801fb64d  test    r9b, r9b
0x1801fb650  cmovz   edx, eax; x
0x1801fb653  neg     cl
0x1801fb655  mov     rcx, r14; hdc
0x1801fb658  sbb     r8d, r8d
0x1801fb65b  and     r8d, eax; y
0x1801fb65e  test    r9b, r9b
0x1801fb661  cmovz   edi, eax
0x1801fb664  cmovnz  ebx, eax
0x1801fb667  xor     r9d, r9d; lppt
0x1801fb66a  call    cs:MoveToEx
0x1801fb670  mov     r8d, ebx; y
0x1801fb673  mov     edx, edi; x
0x1801fb675  mov     rcx, r14; hdc
0x1801fb678  call    cs:LineTo
0x1801fb67e  mov     rdx, rsi; h
0x1801fb681  mov     rcx, r14; hdc
0x1801fb684  call    cs:SelectObject
0x1801fb68a  mov     rcx, rbp
0x1801fb68d  add     rsp, 20h
0x1801fb691  pop     r14
0x1801fb693  pop     rdi
0x1801fb694  pop     rsi
0x1801fb695  pop     rbp
0x1801fb696  pop     rbx
0x1801fb697  jmp     cs:DeleteObject
```
