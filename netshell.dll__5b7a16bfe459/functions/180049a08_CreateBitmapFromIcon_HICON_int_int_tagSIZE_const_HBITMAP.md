# CreateBitmapFromIcon(HICON__ *,int,int,tagSIZE const *,HBITMAP__ * *)

- ea: `0x180049a08`
- end: `0x180049c35`
- name: `?CreateBitmapFromIcon@@YAJPEAUHICON__@@HHPEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z`
- size: `557`
- prototype: `__int64 __usercall@<rax>(HICON hicon@<rcx>, int@<edx>, int@<r8d>, const struct tagSIZE *@<r9>, HBITMAP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180043bb0`

## callees

- `0x18001e1e0`
- `0x18001eb7c`
- `0x180049940`
- `0x180049a08`
- `0x180060818`
- `0x1800608f8`
- `0x180060960`
- `0x180060a68`
- `0x180065010`

## import_xrefs

- `SHLWAPI!__imp_SHFillRectClr` at `0x180049aa9`
- `SHLWAPI!__imp_SHFillRectClr` at `0x180049aa9`
- `SHELL32!__imp_SHGetImageList` at `0x180049b2b`
- `SHELL32!__imp_SHGetImageList` at `0x180049b2b`
- `GDI32!DeleteDC` at `0x180049bf5`
- `GDI32!DeleteDC` at `0x180049bf5`
- `GDI32!DeleteObject` at `0x180049c06`
- `GDI32!DeleteObject` at `0x180049c06`
- `GDI32!CreateCompatibleDC` at `0x180049a69`
- `GDI32!CreateCompatibleDC` at `0x180049a69`
- `GDI32!SelectObject` at `0x180049a82`
- `GDI32!SelectObject` at `0x180049be6`
- `GDI32!SelectObject` at `0x180049a82`
- `GDI32!SelectObject` at `0x180049be6`

## pseudocode

```c
__int64 __fastcall CreateBitmapFromIcon(HICON hicon, __int64 a2, void **a3, const struct tagSIZE *a4, HBITMAP *a5)
{
  int v7; // edi
  HDC CompatibleDC; // rax
  HDC v9; // rsi
  HGDIOBJ v10; // rax
  void *v11; // r13
  struct _IMAGELIST *v12; // rax
  struct _IMAGELIST *v13; // rdi
  HRESULT v14; // r14d
  int v15; // r15d
  void *ppv; // [rsp+30h] [rbp-71h] BYREF
  HGDIOBJ h; // [rsp+38h] [rbp-69h] BYREF
  __int64 v19; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v20[8]; // [rsp+48h] [rbp-59h] BYREF
  int v21; // [rsp+50h] [rbp-51h]
  HDC v22; // [rsp+58h] [rbp-49h]
  LONG v23; // [rsp+68h] [rbp-39h]
  LONG v24; // [rsp+6Ch] [rbp-35h]
  int v25; // [rsp+78h] [rbp-29h]
  int v26; // [rsp+7Ch] [rbp-25h]
  int v27; // [rsp+80h] [rbp-21h]
  __int64 v28; // [rsp+A0h] [rbp-1h] BYREF
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
  if ( CompatibleDC )
  {
    v10 = SelectObject(CompatibleDC, h);
    cx = a4->cx;
    v11 = v10;
    cy = a4->cy;
    v28 = 0;
    SHFillRectClr(v9, &v28, 0xFFFFFFFFLL);
    ppv = 0;
    if ( hicon )
    {
      v12 = ImageList_Create(a4->cx, a4->cy, 0x21u, 1, 1);
      v13 = v12;
      if ( v12 )
      {
        v14 = -2147024882;
        v15 = ImageList_ReplaceIcon(v12, -1, hicon);
        if ( v15 != -1 )
          v14 = HIMAGELIST_QueryInterface(v13, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppv);
        ImageList_Destroy(v13);
        goto LABEL_11;
      }
    }
    else if ( SHGetImageList(-1, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppv) >= 0
           && (*(int (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 256LL))(
                ppv,
                (unsigned int)a4->cx,
                (unsigned int)a4->cy) >= 0 )
    {
      v15 = 0;
      v14 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 296LL))(ppv, 0, 0);
LABEL_11:
      if ( v14 >= 0 )
      {
        v19 = 88;
        memset_0(v20, 0, 0x50u);
        v23 = a4->cx;
        v24 = a4->cy;
        v25 = -16777216;
        v26 = -16777216;
        v21 = v15 & 0xFFFFFF;
        v22 = v9;
        v27 = 327681;
        (*(void (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppv + 64LL))(ppv, &v19);
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    v7 = 0;
    *a5 = (HBITMAP)SelectObject(v9, v11);
    DeleteDC(v9);
  }
  if ( !*a5 )
    DeleteObject(h);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180049a08  mov     [rsp-8+arg_8], rbx
0x180049a0d  push    rbp
0x180049a0e  push    rsi
0x180049a0f  push    rdi
0x180049a10  push    r12
0x180049a12  push    r13
0x180049a14  push    r14
0x180049a16  push    r15
0x180049a18  lea     rbp, [rsp-1Fh]
0x180049a1d  sub     rsp, 0C0h
0x180049a24  mov     rax, cs:__security_cookie
0x180049a2b  xor     rax, rsp
0x180049a2e  mov     [rbp+4Fh+var_40], rax
0x180049a32  mov     r12, [rbp+4Fh+arg_20]
0x180049a36  mov     rbx, r9
0x180049a39  lea     r9, [rbp+4Fh+h]; HBITMAP *
0x180049a3d  mov     [rbp+4Fh+h], 0
0x180049a45  mov     rdx, rbx; struct tagSIZE *
0x180049a48  mov     r15, rcx
0x180049a4b  mov     qword ptr [r12], 0
0x180049a53  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x180049a58  mov     edi, eax
0x180049a5a  test    eax, eax
0x180049a5c  js      loc_180049C0C
0x180049a62  xor     ecx, ecx; hdc
0x180049a64  mov     edi, 80004005h
0x180049a69  call    cs:__imp_CreateCompatibleDC
0x180049a6f  mov     rsi, rax
0x180049a72  test    rax, rax
0x180049a75  jz      loc_180049BFB
0x180049a7b  mov     rdx, [rbp+4Fh+h]; h
0x180049a7f  mov     rcx, rax; hdc
0x180049a82  call    cs:__imp_SelectObject
0x180049a88  mov     ecx, [rbx]
0x180049a8a  lea     rdx, [rbp+4Fh+var_50]
0x180049a8e  mov     [rbp+4Fh+var_48], ecx
0x180049a91  or      r8d, 0FFFFFFFFh
0x180049a95  mov     ecx, [rbx+4]
0x180049a98  mov     r13, rax
0x180049a9b  mov     [rbp+4Fh+var_44], ecx
0x180049a9e  mov     rcx, rsi
0x180049aa1  mov     [rbp+4Fh+var_50], 0
0x180049aa9  call    cs:__imp_SHFillRectClr
0x180049aaf  mov     [rbp+4Fh+ppv], 0
0x180049ab7  test    r15, r15
0x180049aba  jz      short loc_180049B1D
0x180049abc  mov     edx, [rbx+4]; cy
0x180049abf  mov     r9d, 1; cInitial
0x180049ac5  mov     ecx, [rbx]; cx
0x180049ac7  mov     [rsp+0F0h+cGrow], r9d; cGrow
0x180049acc  lea     r8d, [r9+20h]; flags
0x180049ad0  call    ImageList_Create
0x180049ad5  mov     rdi, rax
0x180049ad8  test    rax, rax
0x180049adb  jz      loc_180049BD0
0x180049ae1  mov     r8, r15; hicon
0x180049ae4  or      edx, 0FFFFFFFFh; i
0x180049ae7  mov     rcx, rax; himl
0x180049aea  mov     r14d, 8007000Eh
0x180049af0  call    ImageList_ReplaceIcon
0x180049af5  mov     r15d, eax
0x180049af8  cmp     eax, 0FFFFFFFFh
0x180049afb  jz      short loc_180049B13
0x180049afd  lea     r8, [rbp+4Fh+ppv]; ppv
0x180049b01  mov     rcx, rdi; himl
0x180049b04  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x180049b0b  call    HIMAGELIST_QueryInterface
0x180049b10  mov     r14d, eax
0x180049b13  mov     rcx, rdi; himl
0x180049b16  call    ImageList_Destroy
0x180049b1b  jmp     short loc_180049B74
0x180049b1d  lea     r8, [rbp+4Fh+ppv]; ppvObj
0x180049b21  or      ecx, 0FFFFFFFFh; iImageList
0x180049b24  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x180049b2b  call    cs:__imp_SHGetImageList
0x180049b31  test    eax, eax
0x180049b33  js      loc_180049BD0
0x180049b39  mov     rcx, [rbp+4Fh+ppv]
0x180049b3d  mov     r8d, [rbx+4]
0x180049b41  mov     edx, [rbx]
0x180049b43  mov     rax, [rcx]
0x180049b46  mov     rax, [rax+100h]
0x180049b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b52  test    eax, eax
0x180049b54  js      short loc_180049BD0
0x180049b56  mov     rcx, [rbp+4Fh+ppv]
0x180049b5a  xor     r15d, r15d
0x180049b5d  xor     r8d, r8d
0x180049b60  xor     edx, edx
0x180049b62  mov     rax, [rcx]
0x180049b65  mov     rax, [rax+128h]
0x180049b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b71  mov     r14d, eax
0x180049b74  test    r14d, r14d
0x180049b77  js      short loc_180049BD0
0x180049b79  xor     edx, edx; Val
0x180049b7b  mov     [rbp+4Fh+var_B0], 58h ; 'X'
0x180049b83  lea     rcx, [rbp+4Fh+var_A8]; void *
0x180049b87  lea     r8d, [rdx+50h]; Size
0x180049b8b  call    memset_0
0x180049b90  mov     eax, [rbx]
0x180049b92  lea     rdx, [rbp+4Fh+var_B0]
0x180049b96  mov     rcx, [rbp+4Fh+ppv]
0x180049b9a  and     r15d, 0FFFFFFh
0x180049ba1  mov     [rbp+4Fh+var_88], eax
0x180049ba4  mov     eax, [rbx+4]
0x180049ba7  mov     [rbp+4Fh+var_84], eax
0x180049baa  mov     eax, 0FF000000h
0x180049baf  mov     [rbp+4Fh+var_78], eax
0x180049bb2  mov     [rbp+4Fh+var_74], eax
0x180049bb5  mov     [rbp+4Fh+var_A0], r15d
0x180049bb9  mov     [rbp+4Fh+var_98], rsi
0x180049bbd  mov     [rbp+4Fh+var_70], 50001h
0x180049bc4  mov     rax, [rcx]
0x180049bc7  mov     rax, [rax+40h]
0x180049bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bd0  mov     rcx, [rbp+4Fh+ppv]
0x180049bd4  mov     rax, [rcx]
0x180049bd7  mov     rax, [rax+10h]
0x180049bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049be0  mov     rdx, r13; h
0x180049be3  mov     rcx, rsi; hdc
0x180049be6  call    cs:__imp_SelectObject
0x180049bec  mov     rcx, rsi; hdc
0x180049bef  xor     edi, edi
0x180049bf1  mov     [r12], rax
0x180049bf5  call    cs:__imp_DeleteDC
0x180049bfb  cmp     qword ptr [r12], 0
0x180049c00  jnz     short loc_180049C0C
0x180049c02  mov     rcx, [rbp+4Fh+h]; ho
0x180049c06  call    cs:__imp_DeleteObject
0x180049c0c  mov     eax, edi
0x180049c0e  mov     rcx, [rbp+4Fh+var_40]
0x180049c12  xor     rcx, rsp; StackCookie
0x180049c15  call    __security_check_cookie
0x180049c1a  mov     rbx, [rsp+0F0h+arg_8]
0x180049c22  add     rsp, 0C0h
0x180049c29  pop     r15
0x180049c2b  pop     r14
0x180049c2d  pop     r13
0x180049c2f  pop     r12
0x180049c31  pop     rdi
0x180049c32  pop     rsi
0x180049c33  pop     rbp
0x180049c34  retn
```
