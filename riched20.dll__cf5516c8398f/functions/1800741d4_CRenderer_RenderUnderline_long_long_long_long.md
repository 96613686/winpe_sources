# CRenderer::RenderUnderline(long,long,long,long)

- ea: `0x1800741d4`
- end: `0x1800743f4`
- name: `?RenderUnderline@CRenderer@@QEAAXJJJJ@Z`
- size: `544`
- prototype: `void __usercall(CRenderer *__hidden this@<rcx>, int x@<edx>, int y@<r8d>, int@<r9d>, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180021160`
- `0x180070c20`
- `0x180073ec4`

## callees

- `0x180073910`
- `0x1800741d4`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!InvertRect` at `0x1800743d1`
- `USER32!InvertRect` at `0x1800743d1`
- `GDI32!LineTo` at `0x18007434c`
- `GDI32!LineTo` at `0x18007436c`
- `GDI32!LineTo` at `0x18007434c`
- `GDI32!LineTo` at `0x18007436c`
- `GDI32!MoveToEx` at `0x180074327`
- `GDI32!MoveToEx` at `0x180074327`
- `GDI32!CreatePen` at `0x1800742ef`
- `GDI32!CreatePen` at `0x1800742ef`
- `GDI32!DeleteObject` at `0x18007438a`
- `GDI32!DeleteObject` at `0x18007438a`
- `GDI32!SelectObject` at `0x18007430b`
- `GDI32!SelectObject` at `0x180074381`
- `GDI32!SelectObject` at `0x18007430b`
- `GDI32!SelectObject` at `0x180074381`

## pseudocode

```c
void __fastcall CRenderer::RenderUnderline(CRenderer *this, LONG x, int y, int a4, int a5)
{
  __int64 v7; // rcx
  __int64 v10; // rdx
  char v11; // si
  COLORREF v12; // r8d
  int v13; // ecx
  int v14; // edx
  int v15; // ecx
  int v16; // r9d
  int v17; // esi
  HPEN Pen; // rax
  HPEN v19; // r13
  HGDIOBJ v20; // r15
  int v21; // r12d
  int v22; // r12d
  int i; // r14d
  __int64 v24; // rax
  int v25; // ecx
  HDC v26; // rcx
  COLORREF v27; // [rsp+20h] [rbp-28h] BYREF
  RECT rc; // [rsp+28h] [rbp-20h] BYREF

  v7 = *((_QWORD *)this + 5);
  v10 = *((unsigned __int8 *)this + 313);
  v11 = *(_BYTE *)(v7 + 198);
  v27 = 0;
  rc = 0;
  if ( !(_BYTE)v10
    || (*(unsigned int (__fastcall **)(__int64, __int64, COLORREF *))(*(_QWORD *)(v7 + 16) + 224LL))(v7 + 16, v10, &v27)
    || (v12 = v27, ((v27 + 9999999) & 0xFFFFFFFD) == 0) )
  {
    v12 = *((_DWORD *)this + 61);
    v27 = v12;
  }
  v13 = *((unsigned __int8 *)this + 312);
  if ( (_BYTE)v13 == 0xFE )
  {
    v24 = *((_QWORD *)this + 17);
    v25 = *((__int16 *)this + 46);
    rc.top = *((_DWORD *)this + 77);
    rc.left = x;
    rc.bottom = rc.top + *(__int16 *)(v24 + 92) - *((__int16 *)this + 47) + v25;
    v26 = (HDC)*((_QWORD *)this + 35);
    rc.right = a4 + x;
    InvertRect(v26, &rc);
  }
  else if ( (unsigned int)(v13 - 4) <= 4 )
  {
    v17 = 1;
    Pen = CreatePen(*((char *)&qword_180099808 + *((unsigned __int8 *)this + 312) - 4), 1, v12);
    v19 = Pen;
    if ( Pen )
    {
      v20 = SelectObject(*((HDC *)this + 35), Pen);
      v21 = x + a4;
      MoveToEx(*((HDC *)this + 35), x, y, 0);
      if ( *((_BYTE *)this + 312) == 8 )
      {
        v22 = v21 + 1;
        for ( i = x + 1; i < v22; i += 2 )
        {
          LineTo(*((HDC *)this + 35), i, y + v17);
          v17 = -v17;
        }
      }
      else
      {
        LineTo(*((HDC *)this + 35), v21, y);
      }
      if ( v20 )
        SelectObject(*((HDC *)this + 35), v20);
      DeleteObject(v19);
    }
  }
  else
  {
    rc.top = y;
    if ( (_BYTE)v13 == 9 )
    {
      y -= a5;
      rc.top = y;
    }
    v14 = 2 * a5;
    if ( (_BYTE)v13 != 9 )
      v14 = a5;
    if ( (v11 & 1) == 0 )
    {
      v15 = *((_DWORD *)this + 77);
      v16 = *((__int16 *)this + 46);
      if ( y >= v16 + v15 )
      {
        y = v15 + v16 - v14;
        rc.top = y;
      }
    }
    rc.left = x;
    rc.bottom = v14 + y;
    rc.right = a4 + x;
    CRenderer::FillRectWithColor(this, &rc, v12);
  }
}

```

## disassembly

```asm
0x1800741d4  push    rbp
0x1800741d6  push    rbx
0x1800741d7  push    rsi
0x1800741d8  push    rdi
0x1800741d9  push    r12
0x1800741db  push    r13
0x1800741dd  push    r14
0x1800741df  push    r15
0x1800741e1  mov     rbp, rsp
0x1800741e4  sub     rsp, 48h
0x1800741e8  mov     rax, cs:__security_cookie
0x1800741ef  xor     rax, rsp
0x1800741f2  mov     [rbp+var_10], rax
0x1800741f6  mov     rdi, rcx
0x1800741f9  mov     r14d, edx
0x1800741fc  mov     rcx, [rcx+28h]
0x180074200  xorps   xmm0, xmm0
0x180074203  mov     r12d, r9d
0x180074206  mov     ebx, r8d
0x180074209  movzx   edx, byte ptr [rdi+139h]
0x180074210  movzx   esi, byte ptr [rcx+0C6h]
0x180074217  mov     [rbp+var_28], 0
0x18007421e  movups  xmmword ptr [rbp+rc.left], xmm0
0x180074222  test    dl, dl
0x180074224  jz      short loc_180074253
0x180074226  add     rcx, 10h
0x18007422a  lea     r8, [rbp+var_28]
0x18007422e  mov     rax, [rcx]
0x180074231  mov     rax, [rax+0E0h]
0x180074238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007423d  test    eax, eax
0x18007423f  jnz     short loc_180074253
0x180074241  mov     r8d, [rbp+var_28]
0x180074245  lea     eax, [r8+98967Fh]
0x18007424c  test    eax, 0FFFFFFFDh
0x180074251  jnz     short loc_18007425E
0x180074253  mov     r8d, [rdi+0F4h]; unsigned int
0x18007425a  mov     [rbp+var_28], r8d
0x18007425e  movzx   ecx, byte ptr [rdi+138h]
0x180074265  cmp     cl, 0FEh
0x180074268  jz      loc_180074392
0x18007426e  lea     eax, [rcx-4]
0x180074271  mov     edx, ecx
0x180074273  cmp     eax, 4
0x180074276  jbe     short loc_1800742DC
0x180074278  mov     eax, [rbp+arg_20]
0x18007427b  mov     r9d, esi
0x18007427e  and     r9d, 1
0x180074282  mov     [rbp+rc.top], ebx
0x180074285  cmp     cl, 9
0x180074288  jnz     short loc_18007428F
0x18007428a  sub     ebx, eax
0x18007428c  mov     [rbp+rc.top], ebx
0x18007428f  cmp     cl, 9
0x180074292  lea     edx, [rax+rax]
0x180074295  cmovnz  edx, eax
0x180074298  test    r9d, r9d
0x18007429b  jnz     short loc_1800742BA
0x18007429d  mov     ecx, [rdi+134h]
0x1800742a3  movsx   r9d, word ptr [rdi+5Ch]
0x1800742a8  lea     eax, [r9+rcx]
0x1800742ac  cmp     ebx, eax
0x1800742ae  jl      short loc_1800742BA
0x1800742b0  mov     ebx, r9d
0x1800742b3  sub     ebx, edx
0x1800742b5  add     ebx, ecx
0x1800742b7  mov     [rbp+rc.top], ebx
0x1800742ba  lea     eax, [rdx+rbx]
0x1800742bd  mov     [rbp+rc.left], r14d
0x1800742c1  mov     [rbp+rc.bottom], eax
0x1800742c4  lea     rdx, [rbp+rc]; struct tagRECT *
0x1800742c8  lea     eax, [r12+r14]
0x1800742cc  mov     rcx, rdi; this
0x1800742cf  mov     [rbp+rc.right], eax
0x1800742d2  call    ?FillRectWithColor@CRenderer@@QEAAXPEAUtagRECT@@K@Z; CRenderer::FillRectWithColor(tagRECT *,ulong)
0x1800742d7  jmp     loc_1800743D7
0x1800742dc  lea     rcx, qword_180099808
0x1800742e3  mov     esi, 1
0x1800742e8  movsx   ecx, byte ptr [rdx+rcx-4]; iStyle
0x1800742ed  mov     edx, esi; cWidth
0x1800742ef  call    cs:__imp_CreatePen
0x1800742f5  mov     r13, rax
0x1800742f8  test    rax, rax
0x1800742fb  jz      loc_1800743D7
0x180074301  mov     rcx, [rdi+118h]; hdc
0x180074308  mov     rdx, rax; h
0x18007430b  call    cs:__imp_SelectObject
0x180074311  mov     rcx, [rdi+118h]; hdc
0x180074318  xor     r9d, r9d; lppt
0x18007431b  mov     r8d, ebx; y
0x18007431e  mov     edx, r14d; x
0x180074321  mov     r15, rax
0x180074324  add     r12d, r14d
0x180074327  call    cs:__imp_MoveToEx
0x18007432d  cmp     byte ptr [rdi+138h], 8
0x180074334  jnz     short loc_18007435F
0x180074336  inc     r12d
0x180074339  inc     r14d
0x18007433c  jmp     short loc_180074358
0x18007433e  mov     rcx, [rdi+118h]; hdc
0x180074345  lea     r8d, [rbx+rsi]; y
0x180074349  mov     edx, r14d; x
0x18007434c  call    cs:__imp_LineTo
0x180074352  neg     esi
0x180074354  add     r14d, 2
0x180074358  cmp     r14d, r12d
0x18007435b  jl      short loc_18007433E
0x18007435d  jmp     short loc_180074372
0x18007435f  mov     rcx, [rdi+118h]; hdc
0x180074366  mov     r8d, ebx; y
0x180074369  mov     edx, r12d; x
0x18007436c  call    cs:__imp_LineTo
0x180074372  test    r15, r15
0x180074375  jz      short loc_180074387
0x180074377  mov     rcx, [rdi+118h]; hdc
0x18007437e  mov     rdx, r15; h
0x180074381  call    cs:__imp_SelectObject
0x180074387  mov     rcx, r13; ho
0x18007438a  call    cs:__imp_DeleteObject
0x180074390  jmp     short loc_1800743D7
0x180074392  mov     rax, [rdi+88h]
0x180074399  mov     r8d, [rdi+134h]
0x1800743a0  movsx   ecx, word ptr [rdi+5Ch]
0x1800743a4  mov     [rbp+rc.top], r8d
0x1800743a8  mov     [rbp+rc.left], r14d
0x1800743ac  movsx   edx, word ptr [rax+5Ch]
0x1800743b0  movsx   eax, word ptr [rdi+5Eh]
0x1800743b4  sub     edx, eax
0x1800743b6  lea     eax, [r8+rdx]
0x1800743ba  add     ecx, eax
0x1800743bc  lea     rdx, [rbp+rc]; lprc
0x1800743c0  mov     [rbp+rc.bottom], ecx
0x1800743c3  lea     eax, [r12+r14]
0x1800743c7  mov     rcx, [rdi+118h]; hDC
0x1800743ce  mov     [rbp+rc.right], eax
0x1800743d1  call    cs:__imp_InvertRect
0x1800743d7  mov     rcx, [rbp+var_10]
0x1800743db  xor     rcx, rsp; StackCookie
0x1800743de  call    __security_check_cookie
0x1800743e3  add     rsp, 48h
0x1800743e7  pop     r15
0x1800743e9  pop     r14
0x1800743eb  pop     r13
0x1800743ed  pop     r12
0x1800743ef  pop     rdi
0x1800743f0  pop     rsi
0x1800743f1  pop     rbx
0x1800743f2  pop     rbp
0x1800743f3  retn
```
