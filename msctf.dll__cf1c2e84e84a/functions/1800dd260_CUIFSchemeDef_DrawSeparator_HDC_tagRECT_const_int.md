# CUIFSchemeDef::DrawSeparator(HDC__ *,tagRECT const *,int)

- ea: `0x1800dd260`
- end: `0x1800dd3b3`
- name: `?DrawSeparator@CUIFSchemeDef@@UEAAXPEAUHDC__@@PEBUtagRECT@@H@Z`
- size: `339`
- prototype: `void(CUIFSchemeDef *__hidden this, HDC, const struct tagRECT *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800dae34`
- `0x1800dd260`
- `0x1800ddbec`

## import_xrefs

- `USER32!GetSysColor` at `0x1800dd28e`
- `USER32!GetSysColor` at `0x1800dd2ad`
- `USER32!GetSysColor` at `0x1800dd28e`
- `USER32!GetSysColor` at `0x1800dd2ad`
- `GDI32!MoveToEx` at `0x1800dd2ea`
- `GDI32!MoveToEx` at `0x1800dd31e`
- `GDI32!MoveToEx` at `0x1800dd332`
- `GDI32!MoveToEx` at `0x1800dd369`
- `GDI32!MoveToEx` at `0x1800dd2ea`
- `GDI32!MoveToEx` at `0x1800dd31e`
- `GDI32!MoveToEx` at `0x1800dd332`
- `GDI32!MoveToEx` at `0x1800dd369`
- `GDI32!LineTo` at `0x1800dd2fb`
- `GDI32!LineTo` at `0x1800dd345`
- `GDI32!LineTo` at `0x1800dd37d`
- `GDI32!LineTo` at `0x1800dd2fb`
- `GDI32!LineTo` at `0x1800dd345`
- `GDI32!LineTo` at `0x1800dd37d`
- `GDI32!SelectObject` at `0x1800dd2cf`
- `GDI32!SelectObject` at `0x1800dd309`
- `GDI32!SelectObject` at `0x1800dd353`
- `GDI32!SelectObject` at `0x1800dd389`
- `GDI32!SelectObject` at `0x1800dd2cf`
- `GDI32!SelectObject` at `0x1800dd309`
- `GDI32!SelectObject` at `0x1800dd353`
- `GDI32!SelectObject` at `0x1800dd389`

## pseudocode

```c
void __fastcall CUIFSchemeDef::DrawSeparator(CUIFSchemeDef *this, HDC a2, const struct tagRECT *a3, int a4)
{
  DWORD SysColor; // eax
  DWORD v8; // eax
  HGDIOBJ v9; // rax
  LONG left; // edx
  LONG top; // r8d
  bool v12; // zf
  void *v13; // rsi
  LONG bottom; // r8d
  LONG right; // edx
  HGDIOBJ h; // [rsp+20h] [rbp-18h] BYREF
  HGDIOBJ v17[2]; // [rsp+28h] [rbp-10h] BYREF

  v17[0] = 0;
  h = 0;
  SysColor = GetSysColor(20);
  if ( CSolidPen::Init((CSolidPen *)v17, SysColor) )
  {
    v8 = GetSysColor(16);
    if ( CSolidPen::Init((CSolidPen *)&h, v8) )
    {
      v9 = SelectObject(a2, h);
      left = a3->left;
      top = a3->top;
      v12 = a4 == 0;
      v13 = v9;
      if ( v12 )
      {
        MoveToEx(a2, left + 1, top, 0);
        LineTo(a2, a3->left + 1, a3->bottom);
        SelectObject(a2, v17[0]);
        MoveToEx(a2, a3->left + 2, a3->top, 0);
        bottom = a3->bottom;
        right = a3->left + 2;
      }
      else
      {
        MoveToEx(a2, left, top + 1, 0);
        LineTo(a2, a3->right, a3->top + 1);
        SelectObject(a2, v17[0]);
        MoveToEx(a2, a3->left, a3->top + 2, 0);
        right = a3->right;
        bottom = a3->top + 2;
      }
      LineTo(a2, right, bottom);
      SelectObject(a2, v13);
    }
  }
  CSolidPen::~CSolidPen((CSolidPen *)&h);
  CSolidPen::~CSolidPen((CSolidPen *)v17);
}

```

## disassembly

```asm
0x1800dd260  mov     rax, rsp
0x1800dd263  mov     [rax+8], rbx
0x1800dd267  mov     [rax+10h], rsi
0x1800dd26b  push    rdi
0x1800dd26c  sub     rsp, 30h
0x1800dd270  mov     ecx, 14h; nIndex
0x1800dd275  mov     qword ptr [rax-10h], 0
0x1800dd27d  mov     esi, r9d
0x1800dd280  mov     qword ptr [rax-18h], 0
0x1800dd288  mov     rdi, r8
0x1800dd28b  mov     rbx, rdx
0x1800dd28e  call    cs:__imp_GetSysColor
0x1800dd294  mov     edx, eax; unsigned int
0x1800dd296  lea     rcx, [rsp+38h+var_10]; this
0x1800dd29b  call    ?Init@CSolidPen@@QEAAHK@Z; CSolidPen::Init(ulong)
0x1800dd2a0  test    eax, eax
0x1800dd2a2  jz      loc_1800DD38F
0x1800dd2a8  mov     ecx, 10h; nIndex
0x1800dd2ad  call    cs:__imp_GetSysColor
0x1800dd2b3  mov     edx, eax; unsigned int
0x1800dd2b5  lea     rcx, [rsp+38h+h]; this
0x1800dd2ba  call    ?Init@CSolidPen@@QEAAHK@Z; CSolidPen::Init(ulong)
0x1800dd2bf  test    eax, eax
0x1800dd2c1  jz      loc_1800DD38F
0x1800dd2c7  mov     rdx, [rsp+38h+h]; h
0x1800dd2cc  mov     rcx, rbx; hdc
0x1800dd2cf  call    cs:__imp_SelectObject
0x1800dd2d5  mov     edx, [rdi]; x
0x1800dd2d7  xor     r9d, r9d; lppt
0x1800dd2da  mov     r8d, [rdi+4]; y
0x1800dd2de  test    esi, esi
0x1800dd2e0  mov     rsi, rax
0x1800dd2e3  mov     rcx, rbx; hdc
0x1800dd2e6  jnz     short loc_1800DD32F
0x1800dd2e8  inc     edx; x
0x1800dd2ea  call    cs:__imp_MoveToEx
0x1800dd2f0  mov     edx, [rdi]
0x1800dd2f2  mov     rcx, rbx; hdc
0x1800dd2f5  mov     r8d, [rdi+0Ch]; y
0x1800dd2f9  inc     edx; x
0x1800dd2fb  call    cs:__imp_LineTo
0x1800dd301  mov     rdx, [rsp+38h+var_10]; h
0x1800dd306  mov     rcx, rbx; hdc
0x1800dd309  call    cs:__imp_SelectObject
0x1800dd30f  mov     edx, [rdi]
0x1800dd311  xor     r9d, r9d; lppt
0x1800dd314  mov     r8d, [rdi+4]; y
0x1800dd318  add     edx, 2; x
0x1800dd31b  mov     rcx, rbx; hdc
0x1800dd31e  call    cs:__imp_MoveToEx
0x1800dd324  mov     edx, [rdi]
0x1800dd326  mov     r8d, [rdi+0Ch]
0x1800dd32a  add     edx, 2
0x1800dd32d  jmp     short loc_1800DD37A
0x1800dd32f  inc     r8d; y
0x1800dd332  call    cs:__imp_MoveToEx
0x1800dd338  mov     r8d, [rdi+4]
0x1800dd33c  mov     rcx, rbx; hdc
0x1800dd33f  mov     edx, [rdi+8]; x
0x1800dd342  inc     r8d; y
0x1800dd345  call    cs:__imp_LineTo
0x1800dd34b  mov     rdx, [rsp+38h+var_10]; h
0x1800dd350  mov     rcx, rbx; hdc
0x1800dd353  call    cs:__imp_SelectObject
0x1800dd359  mov     r8d, [rdi+4]
0x1800dd35d  xor     r9d, r9d; lppt
0x1800dd360  mov     edx, [rdi]; x
0x1800dd362  add     r8d, 2; y
0x1800dd366  mov     rcx, rbx; hdc
0x1800dd369  call    cs:__imp_MoveToEx
0x1800dd36f  mov     r8d, [rdi+4]
0x1800dd373  mov     edx, [rdi+8]; x
0x1800dd376  add     r8d, 2; y
0x1800dd37a  mov     rcx, rbx; hdc
0x1800dd37d  call    cs:__imp_LineTo
0x1800dd383  mov     rdx, rsi; h
0x1800dd386  mov     rcx, rbx; hdc
0x1800dd389  call    cs:__imp_SelectObject
0x1800dd38f  lea     rcx, [rsp+38h+h]; this
0x1800dd394  call    ??1CSolidPen@@QEAA@XZ; CSolidPen::~CSolidPen(void)
0x1800dd399  lea     rcx, [rsp+38h+var_10]; this
0x1800dd39e  call    ??1CSolidPen@@QEAA@XZ; CSolidPen::~CSolidPen(void)
0x1800dd3a3  mov     rbx, [rsp+38h+arg_0]
0x1800dd3a8  mov     rsi, [rsp+38h+arg_8]
0x1800dd3ad  add     rsp, 30h
0x1800dd3b1  pop     rdi
0x1800dd3b2  retn
```
