# CUIFSchemeOfc10::DrawSeparator(HDC__ *,tagRECT const *,int)

- ea: `0x1800dd3c0`
- end: `0x1800dd47c`
- name: `?DrawSeparator@CUIFSchemeOfc10@@UEAAXPEAUHDC__@@PEBUtagRECT@@H@Z`
- size: `188`
- prototype: `void(CUIFSchemeOfc10 *__hidden this, HDC, const struct tagRECT *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800dae34`
- `0x1800dd3c0`
- `0x1800ddbec`
- `0x18010a010`

## import_xrefs

- `GDI32!MoveToEx` at `0x1800dd428`
- `GDI32!MoveToEx` at `0x1800dd43b`
- `GDI32!MoveToEx` at `0x1800dd428`
- `GDI32!MoveToEx` at `0x1800dd43b`
- `GDI32!LineTo` at `0x1800dd450`
- `GDI32!LineTo` at `0x1800dd450`
- `GDI32!SelectObject` at `0x1800dd40a`
- `GDI32!SelectObject` at `0x1800dd45c`
- `GDI32!SelectObject` at `0x1800dd40a`
- `GDI32!SelectObject` at `0x1800dd45c`

## pseudocode

```c
void __fastcall CUIFSchemeOfc10::DrawSeparator(CUIFSchemeOfc10 *this, HDC a2, const struct tagRECT *a3, int a4)
{
  __int64 v4; // rax
  unsigned int v8; // eax
  HGDIOBJ v9; // rax
  int v10; // r8d
  int v11; // edx
  bool v12; // zf
  void *v13; // rsi
  int v14; // r8d
  int v15; // edx
  HGDIOBJ h; // [rsp+30h] [rbp+8h] BYREF

  v4 = *(_QWORD *)this;
  h = 0;
  v8 = (*(__int64 (__fastcall **)(CUIFSchemeOfc10 *, __int64))(v4 + 8))(this, 12);
  if ( CSolidPen::Init((CSolidPen *)&h, v8) )
  {
    v9 = SelectObject(a2, h);
    v10 = a3->top + 1;
    v11 = a3->left + 1;
    v12 = a4 == 0;
    v13 = v9;
    if ( v12 )
    {
      MoveToEx(a2, v11, v10, 0);
      v14 = a3->bottom - 1;
      v15 = a3->left + 1;
    }
    else
    {
      MoveToEx(a2, v11, v10, 0);
      v14 = a3->top + 1;
      v15 = a3->right - 1;
    }
    LineTo(a2, v15, v14);
    SelectObject(a2, v13);
  }
  CSolidPen::~CSolidPen((CSolidPen *)&h);
}

```

## disassembly

```asm
0x1800dd3c0  mov     [rsp+arg_8], rbx
0x1800dd3c5  mov     [rsp+arg_10], rsi
0x1800dd3ca  push    rdi
0x1800dd3cb  sub     rsp, 20h
0x1800dd3cf  mov     rax, [rcx]
0x1800dd3d2  mov     rbx, rdx
0x1800dd3d5  mov     edx, 0Ch
0x1800dd3da  mov     [rsp+28h+h], 0
0x1800dd3e3  mov     esi, r9d
0x1800dd3e6  mov     rdi, r8
0x1800dd3e9  mov     rax, [rax+8]
0x1800dd3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dd3f2  mov     edx, eax; unsigned int
0x1800dd3f4  lea     rcx, [rsp+28h+h]; this
0x1800dd3f9  call    ?Init@CSolidPen@@QEAAHK@Z; CSolidPen::Init(ulong)
0x1800dd3fe  test    eax, eax
0x1800dd400  jz      short loc_1800DD462
0x1800dd402  mov     rdx, [rsp+28h+h]; h
0x1800dd407  mov     rcx, rbx; hdc
0x1800dd40a  call    cs:__imp_SelectObject
0x1800dd410  mov     r8d, [rdi+4]
0x1800dd414  xor     r9d, r9d; lppt
0x1800dd417  mov     edx, [rdi]
0x1800dd419  inc     r8d; y
0x1800dd41c  inc     edx; x
0x1800dd41e  mov     rcx, rbx; hdc
0x1800dd421  test    esi, esi
0x1800dd423  mov     rsi, rax
0x1800dd426  jnz     short loc_1800DD43B
0x1800dd428  call    cs:__imp_MoveToEx
0x1800dd42e  mov     r8d, [rdi+0Ch]
0x1800dd432  mov     edx, [rdi]
0x1800dd434  dec     r8d
0x1800dd437  inc     edx
0x1800dd439  jmp     short loc_1800DD44D
0x1800dd43b  call    cs:__imp_MoveToEx
0x1800dd441  mov     r8d, [rdi+4]
0x1800dd445  mov     edx, [rdi+8]
0x1800dd448  inc     r8d; y
0x1800dd44b  dec     edx; x
0x1800dd44d  mov     rcx, rbx; hdc
0x1800dd450  call    cs:__imp_LineTo
0x1800dd456  mov     rdx, rsi; h
0x1800dd459  mov     rcx, rbx; hdc
0x1800dd45c  call    cs:__imp_SelectObject
0x1800dd462  lea     rcx, [rsp+28h+h]; this
0x1800dd467  call    ??1CSolidPen@@QEAA@XZ; CSolidPen::~CSolidPen(void)
0x1800dd46c  mov     rbx, [rsp+28h+arg_8]
0x1800dd471  mov     rsi, [rsp+28h+arg_10]
0x1800dd476  add     rsp, 20h
0x1800dd47a  pop     rdi
0x1800dd47b  retn
```
