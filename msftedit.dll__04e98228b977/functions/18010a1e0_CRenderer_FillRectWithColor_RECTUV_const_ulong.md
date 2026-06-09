# CRenderer::FillRectWithColor(RECTUV const *,ulong)

- ea: `0x18010a1e0`
- end: `0x18010a328`
- name: `?FillRectWithColor@CRenderer@@QEAAXPEBURECTUV@@K@Z`
- size: `328`
- prototype: `void(CRenderer *__hidden this, const struct RECTUV *, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800b32b4`
- `0x18014f0bc`
- `0x18014f290`
- `0x180194230`
- `0x1801cf0e0`

## callees

- `0x18004e140`
- `0x18010a1e0`
- `0x18013ce80`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010a283`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010a2c9`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010a283`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010a2c9`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18010a252`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18010a252`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010a2d8`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010a2d8`

## pseudocode

```c
void __fastcall CRenderer::FillRectWithColor(CRenderer *this, const struct RECTUV *a2, COLORREF a3)
{
  CDisplay *v5; // rcx
  HBRUSH SolidBrush; // rbp
  HDC v7; // rax
  HGDIOBJ v8; // rbx
  HDC v9; // rax
  __int64 v10; // rcx
  COLORREF v11; // [rsp+30h] [rbp-38h] BYREF
  struct tagRECT v12; // [rsp+38h] [rbp-30h] BYREF

  if ( (*((_BYTE *)this + 500) & 1) != 0 )
    a3 = *((_DWORD *)this + 109);
  v5 = (CDisplay *)*((_QWORD *)this + 19);
  v12 = 0;
  CDisplay::RectFromRectuv(v5, &v12, a2, 1, 0);
  if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42)) )
  {
    SolidBrush = CreateSolidBrush(a3);
    if ( SolidBrush )
    {
      v7 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
      v8 = SelectObject(v7, SolidBrush);
      (*(void (__fastcall **)(_QWORD, struct tagRECT *, _QWORD))(**((_QWORD **)this + 42) + 248LL))(
        *((_QWORD *)this + 42),
        &v12,
        a3);
      v9 = (HDC)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
      SelectObject(v9, v8);
      DeleteObject(SolidBrush);
    }
  }
  else
  {
    v10 = *((_QWORD *)this + 42);
    v11 = a3;
    (*(void (__fastcall **)(__int64, struct tagRECT *, COLORREF *))(*(_QWORD *)v10 + 256LL))(v10, &v12, &v11);
  }
}

```

## disassembly

```asm
0x18010a1e0  mov     [rsp+arg_18], rbx
0x18010a1e5  push    rbp
0x18010a1e6  push    rsi
0x18010a1e7  push    rdi
0x18010a1e8  sub     rsp, 50h
0x18010a1ec  mov     rax, cs:__security_cookie
0x18010a1f3  xor     rax, rsp
0x18010a1f6  mov     [rsp+68h+var_20], rax
0x18010a1fb  mov     r9b, 1; bool
0x18010a1fe  mov     esi, r8d
0x18010a201  mov     rdi, rcx
0x18010a204  test    [rcx+1F4h], r9b
0x18010a20b  jz      short loc_18010A213
0x18010a20d  mov     esi, [rcx+1B4h]
0x18010a213  mov     rcx, [rcx+98h]; this
0x18010a21a  xorps   xmm0, xmm0
0x18010a21d  mov     r8, rdx; struct RECTUV *
0x18010a220  mov     [rsp+68h+var_48], 0; bool
0x18010a225  lea     rdx, [rsp+68h+var_30]; struct tagRECT *
0x18010a22a  movups  xmmword ptr [rsp+68h+var_30.left], xmm0
0x18010a22f  call    ?RectFromRectuv@CDisplay@@QEBAXAEAUtagRECT@@AEBURECTUV@@_N2@Z; CDisplay::RectFromRectuv(tagRECT &,RECTUV const &,bool,bool)
0x18010a234  mov     rcx, [rdi+150h]
0x18010a23b  mov     rax, [rcx]
0x18010a23e  mov     rax, [rax+30h]
0x18010a242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a247  test    rax, rax
0x18010a24a  jz      loc_18010A2E6
0x18010a250  mov     ecx, esi; color
0x18010a252  call    cs:__imp_CreateSolidBrush
0x18010a259  nop     dword ptr [rax+rax+00h]
0x18010a25e  mov     rbp, rax
0x18010a261  test    rax, rax
0x18010a264  jz      loc_18010A30A
0x18010a26a  mov     rcx, [rdi+150h]
0x18010a271  mov     rdx, [rcx]
0x18010a274  mov     rax, [rdx+30h]
0x18010a278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a27d  mov     rdx, rbp; h
0x18010a280  mov     rcx, rax; hdc
0x18010a283  call    cs:__imp_SelectObject
0x18010a28a  nop     dword ptr [rax+rax+00h]
0x18010a28f  mov     rcx, [rdi+150h]
0x18010a296  mov     r8d, esi
0x18010a299  mov     rbx, rax
0x18010a29c  mov     rdx, [rcx]
0x18010a29f  mov     rax, [rdx+0F8h]
0x18010a2a6  lea     rdx, [rsp+68h+var_30]
0x18010a2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a2b0  mov     rcx, [rdi+150h]
0x18010a2b7  mov     rdx, [rcx]
0x18010a2ba  mov     rax, [rdx+30h]
0x18010a2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a2c3  mov     rdx, rbx; h
0x18010a2c6  mov     rcx, rax; hdc
0x18010a2c9  call    cs:__imp_SelectObject
0x18010a2d0  nop     dword ptr [rax+rax+00h]
0x18010a2d5  mov     rcx, rbp; ho
0x18010a2d8  call    cs:__imp_DeleteObject
0x18010a2df  nop     dword ptr [rax+rax+00h]
0x18010a2e4  jmp     short loc_18010A30A
0x18010a2e6  mov     rcx, [rdi+150h]
0x18010a2ed  lea     r8, [rsp+68h+var_38]
0x18010a2f2  mov     [rsp+68h+var_38], esi
0x18010a2f6  lea     rdx, [rsp+68h+var_30]
0x18010a2fb  mov     rax, [rcx]
0x18010a2fe  mov     rax, [rax+100h]
0x18010a305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010a30a  mov     rcx, [rsp+68h+var_20]
0x18010a30f  xor     rcx, rsp; StackCookie
0x18010a312  call    __security_check_cookie
0x18010a317  mov     rbx, [rsp+68h+arg_18]
0x18010a31f  add     rsp, 50h
0x18010a323  pop     rdi
0x18010a324  pop     rsi
0x18010a325  pop     rbp
0x18010a326  retn
```
