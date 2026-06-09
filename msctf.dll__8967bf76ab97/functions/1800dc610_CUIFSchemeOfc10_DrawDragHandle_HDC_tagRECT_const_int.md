# CUIFSchemeOfc10::DrawDragHandle(HDC__ *,tagRECT const *,int)

- ea: `0x1800dc610`
- end: `0x1800dc6f5`
- name: `?DrawDragHandle@CUIFSchemeOfc10@@UEAAXPEAUHDC__@@PEBUtagRECT@@H@Z`
- size: `229`
- prototype: `void(CUIFSchemeOfc10 *__hidden this, HDC, const struct tagRECT *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800dae34`
- `0x1800dc610`
- `0x1800ddbec`
- `0x18010a010`

## import_xrefs

- `GDI32!MoveToEx` at `0x1800dc678`
- `GDI32!MoveToEx` at `0x1800dc6b2`
- `GDI32!MoveToEx` at `0x1800dc678`
- `GDI32!MoveToEx` at `0x1800dc6b2`
- `GDI32!LineTo` at `0x1800dc687`
- `GDI32!LineTo` at `0x1800dc6c0`
- `GDI32!LineTo` at `0x1800dc687`
- `GDI32!LineTo` at `0x1800dc6c0`
- `GDI32!SelectObject` at `0x1800dc654`
- `GDI32!SelectObject` at `0x1800dc6d8`
- `GDI32!SelectObject` at `0x1800dc654`
- `GDI32!SelectObject` at `0x1800dc6d8`

## pseudocode

```c
void __fastcall CUIFSchemeOfc10::DrawDragHandle(CUIFSchemeOfc10 *this, HDC a2, const struct tagRECT *a3, int a4)
{
  __int64 v4; // rax
  unsigned int v8; // eax
  HGDIOBJ v9; // r15
  LONG v10; // ebx
  LONG v11; // ebp
  LONG j; // r14d
  LONG left; // ebx
  LONG top; // ebp
  LONG i; // r14d
  HGDIOBJ h; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(_QWORD *)this;
  h = 0;
  v8 = (*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, __int64))(v4 + 8))(this, 21);
  CSolidPen::Init((CSolidPen *)&h, v8);
  v9 = SelectObject(a2, h);
  if ( a4 )
  {
    left = a3->left;
    top = a3->top;
    for ( i = a3->bottom; ; LineTo(a2, left, i) )
    {
      left += 2;
      if ( left >= a3->right - 1 )
        break;
      MoveToEx(a2, left, top + 2, 0);
    }
  }
  else
  {
    v10 = a3->top;
    v11 = a3->left;
    for ( j = a3->right; ; LineTo(a2, j, v10) )
    {
      v10 += 2;
      if ( v10 >= a3->bottom - 1 )
        break;
      MoveToEx(a2, v11 + 2, v10, 0);
    }
  }
  SelectObject(a2, v9);
  CSolidPen::~CSolidPen((CSolidPen *)&h);
}

```

## disassembly

```asm
0x1800dc610  push    rbx
0x1800dc612  push    rbp
0x1800dc613  push    rsi
0x1800dc614  push    rdi
0x1800dc615  push    r14
0x1800dc617  push    r15
0x1800dc619  sub     rsp, 28h
0x1800dc61d  mov     rax, [rcx]
0x1800dc620  mov     rsi, rdx
0x1800dc623  mov     edx, 15h
0x1800dc628  mov     [rsp+58h+h], 0
0x1800dc631  mov     ebx, r9d
0x1800dc634  mov     rdi, r8
0x1800dc637  mov     rax, [rax+8]
0x1800dc63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc640  mov     edx, eax; unsigned int
0x1800dc642  lea     rcx, [rsp+58h+h]; this
0x1800dc647  call    ?Init@CSolidPen@@QEAAHK@Z; CSolidPen::Init(ulong)
0x1800dc64c  mov     rdx, [rsp+58h+h]; h
0x1800dc651  mov     rcx, rsi; hdc
0x1800dc654  call    cs:__imp_SelectObject
0x1800dc65a  mov     r15, rax
0x1800dc65d  test    ebx, ebx
0x1800dc65f  jnz     short loc_1800DC69B
0x1800dc661  mov     ebx, [rdi+4]
0x1800dc664  mov     ebp, [rdi]
0x1800dc666  mov     r14d, [rdi+8]
0x1800dc66a  jmp     short loc_1800DC68D
0x1800dc66c  xor     r9d, r9d; lppt
0x1800dc66f  lea     edx, [rbp+2]; x
0x1800dc672  mov     r8d, ebx; y
0x1800dc675  mov     rcx, rsi; hdc
0x1800dc678  call    cs:__imp_MoveToEx
0x1800dc67e  mov     r8d, ebx; y
0x1800dc681  mov     edx, r14d; x
0x1800dc684  mov     rcx, rsi; hdc
0x1800dc687  call    cs:__imp_LineTo
0x1800dc68d  mov     eax, [rdi+0Ch]
0x1800dc690  add     ebx, 2
0x1800dc693  dec     eax
0x1800dc695  cmp     ebx, eax
0x1800dc697  jl      short loc_1800DC66C
0x1800dc699  jmp     short loc_1800DC6D2
0x1800dc69b  mov     ebx, [rdi]
0x1800dc69d  mov     ebp, [rdi+4]
0x1800dc6a0  mov     r14d, [rdi+0Ch]
0x1800dc6a4  jmp     short loc_1800DC6C6
0x1800dc6a6  xor     r9d, r9d; lppt
0x1800dc6a9  lea     r8d, [rbp+2]; y
0x1800dc6ad  mov     edx, ebx; x
0x1800dc6af  mov     rcx, rsi; hdc
0x1800dc6b2  call    cs:__imp_MoveToEx
0x1800dc6b8  mov     r8d, r14d; y
0x1800dc6bb  mov     edx, ebx; x
0x1800dc6bd  mov     rcx, rsi; hdc
0x1800dc6c0  call    cs:__imp_LineTo
0x1800dc6c6  mov     eax, [rdi+8]
0x1800dc6c9  add     ebx, 2
0x1800dc6cc  dec     eax
0x1800dc6ce  cmp     ebx, eax
0x1800dc6d0  jl      short loc_1800DC6A6
0x1800dc6d2  mov     rdx, r15; h
0x1800dc6d5  mov     rcx, rsi; hdc
0x1800dc6d8  call    cs:__imp_SelectObject
0x1800dc6de  lea     rcx, [rsp+58h+h]; this
0x1800dc6e3  call    ??1CSolidPen@@QEAA@XZ; CSolidPen::~CSolidPen(void)
0x1800dc6e8  add     rsp, 28h
0x1800dc6ec  pop     r15
0x1800dc6ee  pop     r14
0x1800dc6f0  pop     rdi
0x1800dc6f1  pop     rsi
0x1800dc6f2  pop     rbp
0x1800dc6f3  pop     rbx
0x1800dc6f4  retn
```
