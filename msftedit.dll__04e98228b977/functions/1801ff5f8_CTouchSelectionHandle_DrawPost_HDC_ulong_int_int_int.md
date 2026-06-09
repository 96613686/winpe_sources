# CTouchSelectionHandle::DrawPost(HDC__ *,ulong,int,int,int)

- ea: `0x1801ff5f8`
- end: `0x1801ff6bd`
- name: `?DrawPost@CTouchSelectionHandle@@IEBAXPEAUHDC__@@KHHH@Z`
- size: `197`
- prototype: `void(CTouchSelectionHandle *__hidden this, HDC, unsigned int, int, int, int)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180202ba4`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ff629`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ff698`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ff629`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801ff698`
- `ext-ms-win-gdi-draw-l1-1-1!CreatePen` at `0x1801ff614`
- `ext-ms-win-gdi-draw-l1-1-1!CreatePen` at `0x1801ff614`
- `ext-ms-win-gdi-draw-l1-1-0!MoveToEx` at `0x1801ff672`
- `ext-ms-win-gdi-draw-l1-1-0!MoveToEx` at `0x1801ff672`
- `ext-ms-win-gdi-draw-l1-1-0!LineTo` at `0x1801ff686`
- `ext-ms-win-gdi-draw-l1-1-0!LineTo` at `0x1801ff686`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801ff6b1`

## pseudocode

```c
void __fastcall CTouchSelectionHandle::DrawPost(
        CTouchSelectionHandle *this,
        HDC a2,
        COLORREF a3,
        int a4,
        int a5,
        int a6)
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
  v11 = *((_BYTE *)this + 112);
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
  DeleteObject(Pen);
}

```

## disassembly

```asm
0x1801ff5f8  push    rbx
0x1801ff5fa  push    rbp
0x1801ff5fb  push    rsi
0x1801ff5fc  push    rdi
0x1801ff5fd  push    r14
0x1801ff5ff  sub     rsp, 20h
0x1801ff603  mov     r14, rdx
0x1801ff606  mov     rbx, rcx
0x1801ff609  mov     edx, r9d
0x1801ff60c  neg     edx
0x1801ff60e  cmovs   edx, r9d; cWidth
0x1801ff612  xor     ecx, ecx; iStyle
0x1801ff614  call    cs:__imp_CreatePen
0x1801ff61b  nop     dword ptr [rax+rax+00h]
0x1801ff620  mov     rdx, rax; h
0x1801ff623  mov     rcx, r14; hdc
0x1801ff626  mov     rbp, rax
0x1801ff629  call    cs:__imp_SelectObject
0x1801ff630  nop     dword ptr [rax+rax+00h]
0x1801ff635  mov     r9b, [rbx+70h]
0x1801ff639  mov     ecx, 2
0x1801ff63e  mov     edi, [rsp+48h+arg_20]
0x1801ff642  mov     rsi, rax
0x1801ff645  mov     ebx, [rsp+48h+arg_28]
0x1801ff649  mov     eax, edi
0x1801ff64b  cdq
0x1801ff64c  idiv    ecx
0x1801ff64e  mov     cl, r9b
0x1801ff651  mov     edx, edi
0x1801ff653  sub     edx, ebx
0x1801ff655  test    r9b, r9b
0x1801ff658  cmovz   edx, eax; x
0x1801ff65b  neg     cl
0x1801ff65d  mov     rcx, r14; hdc
0x1801ff660  sbb     r8d, r8d
0x1801ff663  and     r8d, eax; y
0x1801ff666  test    r9b, r9b
0x1801ff669  cmovz   edi, eax
0x1801ff66c  cmovnz  ebx, eax
0x1801ff66f  xor     r9d, r9d; lppt
0x1801ff672  call    cs:__imp_MoveToEx
0x1801ff679  nop     dword ptr [rax+rax+00h]
0x1801ff67e  mov     r8d, ebx; y
0x1801ff681  mov     edx, edi; x
0x1801ff683  mov     rcx, r14; hdc
0x1801ff686  call    cs:__imp_LineTo
0x1801ff68d  nop     dword ptr [rax+rax+00h]
0x1801ff692  mov     rdx, rsi; h
0x1801ff695  mov     rcx, r14; hdc
0x1801ff698  call    cs:__imp_SelectObject
0x1801ff69f  nop     dword ptr [rax+rax+00h]
0x1801ff6a4  mov     rcx, rbp
0x1801ff6a7  add     rsp, 20h
0x1801ff6ab  pop     r14
0x1801ff6ad  pop     rdi
0x1801ff6ae  pop     rsi
0x1801ff6af  pop     rbp
0x1801ff6b0  pop     rbx
0x1801ff6b1  jmp     cs:__imp_DeleteObject
```
