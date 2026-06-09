# CreateBitmapFromIcon

- ea: `0x18002cf9c`
- end: `0x18002d1d8`
- name: `CreateBitmapFromIcon`
- size: `572`
- prototype: `__int64 __usercall@<rax>(HICON hicon@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002c794`

## callees

- `0x18002ced8`
- `0x18002cf9c`
- `0x180030c88`
- `0x180030cf8`
- `0x180030d60`
- `0x180030db0`
- `0x18003104a`
- `0x180031070`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_SHGetImageList` at `0x18002d0b0`
- `SHELL32!__imp_SHGetImageList` at `0x18002d0b0`
- `SHLWAPI!__imp_SHFillRectClr` at `0x18002d033`
- `SHLWAPI!__imp_SHFillRectClr` at `0x18002d033`
- `GDI32!DeleteObject` at `0x18002d1a6`
- `GDI32!DeleteObject` at `0x18002d1a6`
- `GDI32!CreateCompatibleDC` at `0x18002cff7`
- `GDI32!CreateCompatibleDC` at `0x18002cff7`
- `GDI32!DeleteDC` at `0x18002d198`
- `GDI32!DeleteDC` at `0x18002d198`
- `GDI32!SelectObject` at `0x18002d010`
- `GDI32!SelectObject` at `0x18002d17d`
- `GDI32!SelectObject` at `0x18002d010`
- `GDI32!SelectObject` at `0x18002d17d`

## pseudocode

```c
__int64 __fastcall CreateBitmapFromIcon(HICON hicon, __int64 a2, void **a3, const struct tagSIZE *a4, _QWORD *a5)
{
  HRESULT v7; // ebx
  HDC CompatibleDC; // rax
  HDC v9; // rsi
  HGDIOBJ v10; // rax
  void *v11; // r13
  struct _IMAGELIST *v12; // rax
  struct _IMAGELIST *v13; // r14
  int v14; // r12d
  void *v15; // rcx
  HGDIOBJ v16; // rax
  void *ppv; // [rsp+30h] [rbp-71h] BYREF
  HGDIOBJ h; // [rsp+38h] [rbp-69h] BYREF
  __int64 v20; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v21[8]; // [rsp+48h] [rbp-59h] BYREF
  int v22; // [rsp+50h] [rbp-51h]
  HDC v23; // [rsp+58h] [rbp-49h]
  LONG v24; // [rsp+68h] [rbp-39h]
  LONG v25; // [rsp+6Ch] [rbp-35h]
  int v26; // [rsp+78h] [rbp-29h]
  int v27; // [rsp+7Ch] [rbp-25h]
  int v28; // [rsp+80h] [rbp-21h]
  __int64 v29; // [rsp+A0h] [rbp-1h] BYREF
  LONG cx; // [rsp+A8h] [rbp+7h]
  LONG cy; // [rsp+ACh] [rbp+Bh]

  h = 0;
  *a5 = 0;
  v7 = Create32BitHBITMAP((HDC)hicon, a4, a3, (HBITMAP *)&h);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v7 = -2147467259;
  CompatibleDC = CreateCompatibleDC(0);
  v9 = CompatibleDC;
  if ( !CompatibleDC )
  {
LABEL_19:
    DeleteObject(h);
    *a5 = 0;
    return (unsigned int)v7;
  }
  v10 = SelectObject(CompatibleDC, h);
  cx = a4->cx;
  v11 = v10;
  cy = a4->cy;
  v29 = 0;
  SHFillRectClr(v9, &v29, 0xFFFFFFFFLL);
  ppv = 0;
  if ( hicon )
  {
    v7 = -2147024882;
    v12 = ImageList_Create(a4->cx, a4->cy, 0x21u, 1, 1);
    v13 = v12;
    if ( !v12 )
      goto LABEL_13;
    v14 = ImageList_ReplaceIcon(v12, -1, hicon);
    if ( v14 != -1 )
      v7 = HIMAGELIST_QueryInterface(v13, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppv);
    ImageList_Destroy(v13);
  }
  else
  {
    v7 = SHGetImageList(-1, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppv);
    if ( v7 < 0 )
      goto LABEL_13;
    v7 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 256LL))(
           ppv,
           (unsigned int)a4->cx,
           (unsigned int)a4->cy);
    if ( v7 < 0 )
      goto LABEL_13;
    v14 = 0;
    v7 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 296LL))(ppv, 0, 0);
  }
  if ( v7 >= 0 )
  {
    v20 = 88;
    memset_0(v21, 0, 0x50u);
    v24 = a4->cx;
    v25 = a4->cy;
    v26 = -16777216;
    v27 = -16777216;
    v22 = v14 & 0xFFFFFF;
    v23 = v9;
    v28 = 327681;
    v7 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppv + 64LL))(ppv, &v20);
  }
LABEL_13:
  v15 = ppv;
  ppv = 0;
  if ( v15 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
  v16 = SelectObject(v9, v11);
  *a5 = v16;
  if ( v7 >= 0 && !v16 )
    v7 = -2147467259;
  DeleteDC(v9);
  if ( v7 < 0 )
    goto LABEL_19;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002cf9c  mov     [rsp-8+arg_8], rbx
0x18002cfa1  push    rbp
0x18002cfa2  push    rsi
0x18002cfa3  push    rdi
0x18002cfa4  push    r12
0x18002cfa6  push    r13
0x18002cfa8  push    r14
0x18002cfaa  push    r15
0x18002cfac  lea     rbp, [rsp-1Fh]
0x18002cfb1  sub     rsp, 0C0h
0x18002cfb8  mov     rax, cs:__security_cookie
0x18002cfbf  xor     rax, rsp
0x18002cfc2  mov     [rbp+4Fh+var_40], rax
0x18002cfc6  mov     r15, [rbp+4Fh+arg_20]
0x18002cfca  mov     rdi, r9
0x18002cfcd  xor     r14d, r14d
0x18002cfd0  lea     r9, [rbp+4Fh+h]; HBITMAP *
0x18002cfd4  mov     rdx, rdi; struct tagSIZE *
0x18002cfd7  mov     [rbp+4Fh+h], r14
0x18002cfdb  mov     r12, rcx
0x18002cfde  mov     [r15], r14
0x18002cfe1  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x18002cfe6  mov     ebx, eax
0x18002cfe8  test    eax, eax
0x18002cfea  js      loc_18002D1AF
0x18002cff0  xor     ecx, ecx; hdc
0x18002cff2  mov     ebx, 80004005h
0x18002cff7  call    cs:__imp_CreateCompatibleDC
0x18002cffd  mov     rsi, rax
0x18002d000  test    rax, rax
0x18002d003  jz      loc_18002D1A2
0x18002d009  mov     rdx, [rbp+4Fh+h]; h
0x18002d00d  mov     rcx, rax; hdc
0x18002d010  call    cs:__imp_SelectObject
0x18002d016  mov     ecx, [rdi]
0x18002d018  lea     rdx, [rbp+4Fh+var_50]
0x18002d01c  mov     [rbp+4Fh+var_48], ecx
0x18002d01f  or      r8d, 0FFFFFFFFh
0x18002d023  mov     ecx, [rdi+4]
0x18002d026  mov     r13, rax
0x18002d029  mov     [rbp+4Fh+var_44], ecx
0x18002d02c  mov     rcx, rsi
0x18002d02f  mov     [rbp+4Fh+var_50], r14
0x18002d033  call    cs:__imp_SHFillRectClr
0x18002d039  mov     [rbp+4Fh+ppv], r14
0x18002d03d  test    r12, r12
0x18002d040  jz      short loc_18002D0A2
0x18002d042  mov     edx, [rdi+4]; cy
0x18002d045  lea     r9d, [r14+1]; cInitial
0x18002d049  mov     ecx, [rdi]; cx
0x18002d04b  lea     r8d, [r14+21h]; flags
0x18002d04f  mov     [rsp+0F0h+cGrow], r9d; cGrow
0x18002d054  mov     ebx, 8007000Eh
0x18002d059  call    ImageList_Create
0x18002d05e  mov     r14, rax
0x18002d061  test    rax, rax
0x18002d064  jz      loc_18002D15B
0x18002d06a  mov     r8, r12; hicon
0x18002d06d  or      edx, 0FFFFFFFFh; i
0x18002d070  mov     rcx, rax; himl
0x18002d073  call    ImageList_ReplaceIcon
0x18002d078  mov     r12d, eax
0x18002d07b  cmp     eax, 0FFFFFFFFh
0x18002d07e  jz      short loc_18002D095
0x18002d080  lea     r8, [rbp+4Fh+ppv]; ppv
0x18002d084  mov     rcx, r14; himl
0x18002d087  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x18002d08e  call    HIMAGELIST_QueryInterface
0x18002d093  mov     ebx, eax
0x18002d095  mov     rcx, r14; himl
0x18002d098  call    ImageList_Destroy
0x18002d09d  xor     r14d, r14d
0x18002d0a0  jmp     short loc_18002D0FC
0x18002d0a2  lea     r8, [rbp+4Fh+ppv]; ppvObj
0x18002d0a6  or      ecx, 0FFFFFFFFh; iImageList
0x18002d0a9  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x18002d0b0  call    cs:__imp_SHGetImageList
0x18002d0b6  mov     ebx, eax
0x18002d0b8  test    eax, eax
0x18002d0ba  js      loc_18002D15E
0x18002d0c0  mov     rcx, [rbp+4Fh+ppv]
0x18002d0c4  mov     r8d, [rdi+4]
0x18002d0c8  mov     edx, [rdi]
0x18002d0ca  mov     rax, [rcx]
0x18002d0cd  mov     rax, [rax+100h]
0x18002d0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0d9  mov     ebx, eax
0x18002d0db  test    eax, eax
0x18002d0dd  js      short loc_18002D15E
0x18002d0df  mov     rcx, [rbp+4Fh+ppv]
0x18002d0e3  xor     r8d, r8d
0x18002d0e6  xor     edx, edx
0x18002d0e8  mov     r12d, r14d
0x18002d0eb  mov     rax, [rcx]
0x18002d0ee  mov     rax, [rax+128h]
0x18002d0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0fa  mov     ebx, eax
0x18002d0fc  test    ebx, ebx
0x18002d0fe  js      short loc_18002D15E
0x18002d100  xor     edx, edx; Val
0x18002d102  mov     [rbp+4Fh+var_B0], 58h ; 'X'
0x18002d10a  lea     rcx, [rbp+4Fh+var_A8]; void *
0x18002d10e  lea     r8d, [rdx+50h]; Size
0x18002d112  call    memset_0
0x18002d117  mov     eax, [rdi]
0x18002d119  lea     rdx, [rbp+4Fh+var_B0]
0x18002d11d  mov     rcx, [rbp+4Fh+ppv]
0x18002d121  and     r12d, 0FFFFFFh
0x18002d128  mov     [rbp+4Fh+var_88], eax
0x18002d12b  mov     eax, [rdi+4]
0x18002d12e  mov     [rbp+4Fh+var_84], eax
0x18002d131  mov     eax, 0FF000000h
0x18002d136  mov     [rbp+4Fh+var_78], eax
0x18002d139  mov     [rbp+4Fh+var_74], eax
0x18002d13c  mov     [rbp+4Fh+var_A0], r12d
0x18002d140  mov     [rbp+4Fh+var_98], rsi
0x18002d144  mov     [rbp+4Fh+var_70], 50001h
0x18002d14b  mov     rax, [rcx]
0x18002d14e  mov     rax, [rax+40h]
0x18002d152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d157  mov     ebx, eax
0x18002d159  jmp     short loc_18002D15E
0x18002d15b  xor     r14d, r14d
0x18002d15e  mov     rcx, [rbp+4Fh+ppv]
0x18002d162  mov     [rbp+4Fh+ppv], r14
0x18002d166  test    rcx, rcx
0x18002d169  jz      short loc_18002D177
0x18002d16b  mov     rax, [rcx]
0x18002d16e  mov     rax, [rax+10h]
0x18002d172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d177  mov     rdx, r13; h
0x18002d17a  mov     rcx, rsi; hdc
0x18002d17d  call    cs:__imp_SelectObject
0x18002d183  mov     [r15], rax
0x18002d186  test    ebx, ebx
0x18002d188  js      short loc_18002D195
0x18002d18a  test    rax, rax
0x18002d18d  mov     eax, 80004005h
0x18002d192  cmovz   ebx, eax
0x18002d195  mov     rcx, rsi; hdc
0x18002d198  call    cs:__imp_DeleteDC
0x18002d19e  test    ebx, ebx
0x18002d1a0  jns     short loc_18002D1AF
0x18002d1a2  mov     rcx, [rbp+4Fh+h]; ho
0x18002d1a6  call    cs:__imp_DeleteObject
0x18002d1ac  mov     [r15], r14
0x18002d1af  mov     eax, ebx
0x18002d1b1  mov     rcx, [rbp+4Fh+var_40]
0x18002d1b5  xor     rcx, rsp; StackCookie
0x18002d1b8  call    __security_check_cookie
0x18002d1bd  mov     rbx, [rsp+0F0h+arg_8]
0x18002d1c5  add     rsp, 0C0h
0x18002d1cc  pop     r15
0x18002d1ce  pop     r14
0x18002d1d0  pop     r13
0x18002d1d2  pop     r12
0x18002d1d4  pop     rdi
0x18002d1d5  pop     rsi
0x18002d1d6  pop     rbp
0x18002d1d7  retn
```
