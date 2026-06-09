# CImage::CheckGdiBitmap(HDC__ *,tagRECT const *)

- ea: `0x1801e9924`
- end: `0x1801e9a69`
- name: `?CheckGdiBitmap@CImage@@AEAAJPEAUHDC__@@PEBUtagRECT@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(CImage *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1801e7e70`
- `0x1801fe230`

## callees

- `0x18013ce80`
- `0x1801e7bd4`
- `0x1801e9924`
- `0x1801e9ac0`
- `0x1801e9dc4`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!GetWorldTransform` at `0x1801e9984`
- `ext-ms-win-gdi-draw-l1-1-0!GetWorldTransform` at `0x1801e9984`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e99ca`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801e99ca`

## pseudocode

```c
__int64 __fastcall CImage::CheckGdiBitmap(CImage *this, HDC a2, const struct tagRECT *a3)
{
  int v6; // edi
  int v7; // ebx
  unsigned int DIBSectionFromBitmapSource; // edi
  void *v9; // rcx
  __int64 v10; // rax
  int v11; // ebx
  int v12; // eax
  int v13; // eax
  struct IWICBitmapSource *v14; // rbx
  struct IWICBitmapSource *v16; // [rsp+30h] [rbp-48h] BYREF
  struct _XFORM xf; // [rsp+38h] [rbp-40h] BYREF

  v6 = (*(__int64 (__fastcall **)(CImage *))(*(_QWORD *)this + 104LL))(this);
  v7 = (*(__int64 (__fastcall **)(CImage *))(*(_QWORD *)this + 112LL))(this);
  memset(&xf, 0, sizeof(xf));
  GetWorldTransform(a2, &xf);
  if ( CImage::CheckSize(this, a3, (const struct D2D_MATRIX_3X2_F *)&xf, v6, v7) )
  {
    v9 = (void *)*((_QWORD *)this + 16);
    if ( v9 )
    {
      DeleteObject(v9);
      *((_QWORD *)this + 16) = 0;
    }
  }
  else
  {
    DIBSectionFromBitmapSource = 0;
    if ( *((_QWORD *)this + 16) )
      return DIBSectionFromBitmapSource;
  }
  v10 = *(_QWORD *)this;
  v16 = 0;
  v11 = (*(__int64 (__fastcall **)(CImage *))(v10 + 112))(this);
  v12 = (*(__int64 (__fastcall **)(CImage *))(*(_QWORD *)this + 104LL))(this);
  v13 = CImage::CreateBitmapSource(this, &v16, v12, v11);
  v14 = v16;
  DIBSectionFromBitmapSource = v13;
  if ( v13 >= 0 )
    DIBSectionFromBitmapSource = CImage::CreateDIBSectionFromBitmapSource(this, a2, v16);
  if ( v14 )
    ((void (__fastcall *)(struct IWICBitmapSource *))v14->lpVtbl->Release)(v14);
  return DIBSectionFromBitmapSource;
}

```

## disassembly

```asm
0x1801e9924  mov     [rsp+arg_10], rbx
0x1801e9929  mov     [rsp+arg_18], rbp
0x1801e992e  push    rsi
0x1801e992f  push    rdi
0x1801e9930  push    r14
0x1801e9932  sub     rsp, 60h
0x1801e9936  mov     rax, cs:__security_cookie
0x1801e993d  xor     rax, rsp
0x1801e9940  mov     [rsp+78h+var_28], rax
0x1801e9945  mov     rax, [rcx]
0x1801e9948  mov     rsi, r8
0x1801e994b  mov     rbp, rdx
0x1801e994e  mov     r14, rcx
0x1801e9951  mov     rax, [rax+68h]
0x1801e9955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e995a  mov     rcx, [r14]
0x1801e995d  mov     edi, eax
0x1801e995f  mov     rax, [rcx+70h]
0x1801e9963  mov     rcx, r14
0x1801e9966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e996b  mov     ebx, eax
0x1801e996d  lea     rdx, [rsp+78h+xf]; lpxf
0x1801e9972  xor     eax, eax
0x1801e9974  xorps   xmm0, xmm0
0x1801e9977  mov     rcx, rbp; hdc
0x1801e997a  mov     qword ptr [rsp+78h+xf.eDx], rax
0x1801e997f  movups  xmmword ptr [rsp+78h+xf.eM11], xmm0
0x1801e9984  call    cs:__imp_GetWorldTransform
0x1801e998b  nop     dword ptr [rax+rax+00h]
0x1801e9990  mov     r9d, edi; int
0x1801e9993  mov     [rsp+78h+var_58], ebx; int
0x1801e9997  lea     r8, [rsp+78h+xf]; struct D2D_MATRIX_3X2_F *
0x1801e999c  mov     rdx, rsi; struct tagRECT *
0x1801e999f  mov     rcx, r14; this
0x1801e99a2  call    ?CheckSize@CImage@@AEAA_NPEBUtagRECT@@PEBUD2D_MATRIX_3X2_F@@JJ@Z; CImage::CheckSize(tagRECT const *,D2D_MATRIX_3X2_F const *,long,long)
0x1801e99a7  xor     esi, esi
0x1801e99a9  test    al, al
0x1801e99ab  jnz     short loc_1801E99BE
0x1801e99ad  mov     edi, esi
0x1801e99af  cmp     [r14+80h], rsi
0x1801e99b6  jnz     loc_1801E9A44
0x1801e99bc  jmp     short loc_1801E99DD
0x1801e99be  mov     rcx, [r14+80h]; ho
0x1801e99c5  test    rcx, rcx
0x1801e99c8  jz      short loc_1801E99DD
0x1801e99ca  call    cs:__imp_DeleteObject
0x1801e99d1  nop     dword ptr [rax+rax+00h]
0x1801e99d6  mov     [r14+80h], rsi
0x1801e99dd  mov     rax, [r14]
0x1801e99e0  mov     rcx, r14
0x1801e99e3  mov     [rsp+78h+var_48], rsi
0x1801e99e8  mov     rax, [rax+70h]
0x1801e99ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e99f1  mov     rcx, [r14]
0x1801e99f4  mov     ebx, eax
0x1801e99f6  mov     rax, [rcx+68h]
0x1801e99fa  mov     rcx, r14
0x1801e99fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9a02  mov     r9d, ebx; int
0x1801e9a05  lea     rdx, [rsp+78h+var_48]; struct IWICBitmapSource **
0x1801e9a0a  mov     r8d, eax; int
0x1801e9a0d  mov     rcx, r14; this
0x1801e9a10  call    ?CreateBitmapSource@CImage@@AEAAJPEAPEAUIWICBitmapSource@@JJ@Z; CImage::CreateBitmapSource(IWICBitmapSource * *,long,long)
0x1801e9a15  mov     rbx, [rsp+78h+var_48]
0x1801e9a1a  mov     edi, eax
0x1801e9a1c  test    eax, eax
0x1801e9a1e  js      short loc_1801E9A30
0x1801e9a20  mov     r8, rbx; struct IWICBitmapSource *
0x1801e9a23  mov     rdx, rbp; HDC
0x1801e9a26  mov     rcx, r14; this
0x1801e9a29  call    ?CreateDIBSectionFromBitmapSource@CImage@@AEAAJPEAUHDC__@@PEAUIWICBitmapSource@@@Z; CImage::CreateDIBSectionFromBitmapSource(HDC__ *,IWICBitmapSource *)
0x1801e9a2e  mov     edi, eax
0x1801e9a30  test    rbx, rbx
0x1801e9a33  jz      short loc_1801E9A44
0x1801e9a35  mov     rdx, [rbx]
0x1801e9a38  mov     rcx, rbx
0x1801e9a3b  mov     rax, [rdx+10h]
0x1801e9a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e9a44  mov     eax, edi
0x1801e9a46  mov     rcx, [rsp+78h+var_28]
0x1801e9a4b  xor     rcx, rsp; StackCookie
0x1801e9a4e  call    __security_check_cookie
0x1801e9a53  lea     r11, [rsp+78h+var_18]
0x1801e9a58  mov     rbx, [r11+30h]
0x1801e9a5c  mov     rbp, [r11+38h]
0x1801e9a60  mov     rsp, r11
0x1801e9a63  pop     r14
0x1801e9a65  pop     rdi
0x1801e9a66  pop     rsi
0x1801e9a67  retn
```
