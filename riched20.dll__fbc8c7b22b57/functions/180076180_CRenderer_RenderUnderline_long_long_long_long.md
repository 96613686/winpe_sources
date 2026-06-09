# CRenderer::RenderUnderline(long,long,long,long)

- ea: `0x180076180`
- end: `0x1800763d1`
- name: `?RenderUnderline@CRenderer@@QEAAXJJJJ@Z`
- size: `593`
- prototype: `void __usercall(CRenderer *__hidden this@<rcx>, int x@<edx>, int y@<r8d>, int@<r9d>, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180024580`
- `0x180072ad0`
- `0x180075e58`

## callees

- `0x180075860`
- `0x180076180`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!InvertRect` at `0x1800763a7`
- `USER32!InvertRect` at `0x1800763a7`
- `GDI32!LineTo` at `0x18007630a`
- `GDI32!LineTo` at `0x180076330`
- `GDI32!LineTo` at `0x18007630a`
- `GDI32!LineTo` at `0x180076330`
- `GDI32!MoveToEx` at `0x1800762df`
- `GDI32!MoveToEx` at `0x1800762df`
- `GDI32!CreatePen` at `0x18007629b`
- `GDI32!CreatePen` at `0x18007629b`
- `GDI32!DeleteObject` at `0x18007635a`
- `GDI32!DeleteObject` at `0x18007635a`
- `GDI32!SelectObject` at `0x1800762bd`
- `GDI32!SelectObject` at `0x18007634b`
- `GDI32!SelectObject` at `0x1800762bd`
- `GDI32!SelectObject` at `0x18007634b`

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
    Pen = CreatePen(*((char *)&qword_18009C7F0 + *((unsigned __int8 *)this + 312) - 4), 1, v12);
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
0x180076180  push    rbp
0x180076182  push    rbx
0x180076183  push    rsi
0x180076184  push    rdi
0x180076185  push    r12
0x180076187  push    r13
0x180076189  push    r14
0x18007618b  push    r15
0x18007618d  mov     rbp, rsp
0x180076190  sub     rsp, 48h
0x180076194  mov     rax, cs:__security_cookie
0x18007619b  xor     rax, rsp
0x18007619e  mov     [rbp+var_10], rax
0x1800761a2  mov     rdi, rcx
0x1800761a5  mov     r14d, edx
0x1800761a8  mov     rcx, [rcx+28h]
0x1800761ac  xorps   xmm0, xmm0
0x1800761af  mov     r12d, r9d
0x1800761b2  mov     ebx, r8d
0x1800761b5  movzx   edx, byte ptr [rdi+139h]
0x1800761bc  movzx   esi, byte ptr [rcx+0C6h]
0x1800761c3  mov     [rbp+var_28], 0
0x1800761ca  movups  xmmword ptr [rbp+rc.left], xmm0
0x1800761ce  test    dl, dl
0x1800761d0  jz      short loc_1800761FF
0x1800761d2  add     rcx, 10h
0x1800761d6  lea     r8, [rbp+var_28]
0x1800761da  mov     rax, [rcx]
0x1800761dd  mov     rax, [rax+0E0h]
0x1800761e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800761e9  test    eax, eax
0x1800761eb  jnz     short loc_1800761FF
0x1800761ed  mov     r8d, [rbp+var_28]
0x1800761f1  lea     eax, [r8+98967Fh]
0x1800761f8  test    eax, 0FFFFFFFDh
0x1800761fd  jnz     short loc_18007620A
0x1800761ff  mov     r8d, [rdi+0F4h]; unsigned int
0x180076206  mov     [rbp+var_28], r8d
0x18007620a  movzx   ecx, byte ptr [rdi+138h]
0x180076211  cmp     cl, 0FEh
0x180076214  jz      loc_180076368
0x18007621a  lea     eax, [rcx-4]
0x18007621d  mov     edx, ecx
0x18007621f  cmp     eax, 4
0x180076222  jbe     short loc_180076288
0x180076224  mov     eax, [rbp+arg_20]
0x180076227  mov     r9d, esi
0x18007622a  and     r9d, 1
0x18007622e  mov     [rbp+rc.top], ebx
0x180076231  cmp     cl, 9
0x180076234  jnz     short loc_18007623B
0x180076236  sub     ebx, eax
0x180076238  mov     [rbp+rc.top], ebx
0x18007623b  cmp     cl, 9
0x18007623e  lea     edx, [rax+rax]
0x180076241  cmovnz  edx, eax
0x180076244  test    r9d, r9d
0x180076247  jnz     short loc_180076266
0x180076249  mov     ecx, [rdi+134h]
0x18007624f  movsx   r9d, word ptr [rdi+5Ch]
0x180076254  lea     eax, [r9+rcx]
0x180076258  cmp     ebx, eax
0x18007625a  jl      short loc_180076266
0x18007625c  mov     ebx, r9d
0x18007625f  sub     ebx, edx
0x180076261  add     ebx, ecx
0x180076263  mov     [rbp+rc.top], ebx
0x180076266  lea     eax, [rdx+rbx]
0x180076269  mov     [rbp+rc.left], r14d
0x18007626d  mov     [rbp+rc.bottom], eax
0x180076270  lea     rdx, [rbp+rc]; struct tagRECT *
0x180076274  lea     eax, [r12+r14]
0x180076278  mov     rcx, rdi; this
0x18007627b  mov     [rbp+rc.right], eax
0x18007627e  call    ?FillRectWithColor@CRenderer@@QEAAXPEAUtagRECT@@K@Z; CRenderer::FillRectWithColor(tagRECT *,ulong)
0x180076283  jmp     loc_1800763B3
0x180076288  lea     rcx, qword_18009C7F0
0x18007628f  mov     esi, 1
0x180076294  movsx   ecx, byte ptr [rdx+rcx-4]; iStyle
0x180076299  mov     edx, esi; cWidth
0x18007629b  call    cs:__imp_CreatePen
0x1800762a2  nop     dword ptr [rax+rax+00h]
0x1800762a7  mov     r13, rax
0x1800762aa  test    rax, rax
0x1800762ad  jz      loc_1800763B3
0x1800762b3  mov     rcx, [rdi+118h]; hdc
0x1800762ba  mov     rdx, rax; h
0x1800762bd  call    cs:__imp_SelectObject
0x1800762c4  nop     dword ptr [rax+rax+00h]
0x1800762c9  mov     rcx, [rdi+118h]; hdc
0x1800762d0  xor     r9d, r9d; lppt
0x1800762d3  mov     r8d, ebx; y
0x1800762d6  mov     edx, r14d; x
0x1800762d9  mov     r15, rax
0x1800762dc  add     r12d, r14d
0x1800762df  call    cs:__imp_MoveToEx
0x1800762e6  nop     dword ptr [rax+rax+00h]
0x1800762eb  cmp     byte ptr [rdi+138h], 8
0x1800762f2  jnz     short loc_180076323
0x1800762f4  inc     r12d
0x1800762f7  inc     r14d
0x1800762fa  jmp     short loc_18007631C
0x1800762fc  mov     rcx, [rdi+118h]; hdc
0x180076303  lea     r8d, [rbx+rsi]; y
0x180076307  mov     edx, r14d; x
0x18007630a  call    cs:__imp_LineTo
0x180076311  nop     dword ptr [rax+rax+00h]
0x180076316  neg     esi
0x180076318  add     r14d, 2
0x18007631c  cmp     r14d, r12d
0x18007631f  jl      short loc_1800762FC
0x180076321  jmp     short loc_18007633C
0x180076323  mov     rcx, [rdi+118h]; hdc
0x18007632a  mov     r8d, ebx; y
0x18007632d  mov     edx, r12d; x
0x180076330  call    cs:__imp_LineTo
0x180076337  nop     dword ptr [rax+rax+00h]
0x18007633c  test    r15, r15
0x18007633f  jz      short loc_180076357
0x180076341  mov     rcx, [rdi+118h]; hdc
0x180076348  mov     rdx, r15; h
0x18007634b  call    cs:__imp_SelectObject
0x180076352  nop     dword ptr [rax+rax+00h]
0x180076357  mov     rcx, r13; ho
0x18007635a  call    cs:__imp_DeleteObject
0x180076361  nop     dword ptr [rax+rax+00h]
0x180076366  jmp     short loc_1800763B3
0x180076368  mov     rax, [rdi+88h]
0x18007636f  mov     r8d, [rdi+134h]
0x180076376  movsx   ecx, word ptr [rdi+5Ch]
0x18007637a  mov     [rbp+rc.top], r8d
0x18007637e  mov     [rbp+rc.left], r14d
0x180076382  movsx   edx, word ptr [rax+5Ch]
0x180076386  movsx   eax, word ptr [rdi+5Eh]
0x18007638a  sub     edx, eax
0x18007638c  lea     eax, [r8+rdx]
0x180076390  add     ecx, eax
0x180076392  lea     rdx, [rbp+rc]; lprc
0x180076396  mov     [rbp+rc.bottom], ecx
0x180076399  lea     eax, [r12+r14]
0x18007639d  mov     rcx, [rdi+118h]; hDC
0x1800763a4  mov     [rbp+rc.right], eax
0x1800763a7  call    cs:__imp_InvertRect
0x1800763ae  nop     dword ptr [rax+rax+00h]
0x1800763b3  mov     rcx, [rbp+var_10]
0x1800763b7  xor     rcx, rsp; StackCookie
0x1800763ba  call    __security_check_cookie
0x1800763bf  add     rsp, 48h
0x1800763c3  pop     r15
0x1800763c5  pop     r14
0x1800763c7  pop     r13
0x1800763c9  pop     r12
0x1800763cb  pop     rdi
0x1800763cc  pop     rsi
0x1800763cd  pop     rbx
0x1800763ce  pop     rbp
0x1800763cf  retn
```
