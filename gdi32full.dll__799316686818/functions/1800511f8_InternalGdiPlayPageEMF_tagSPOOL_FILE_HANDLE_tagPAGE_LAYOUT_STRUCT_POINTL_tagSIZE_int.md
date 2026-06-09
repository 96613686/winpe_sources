# InternalGdiPlayPageEMF(tagSPOOL_FILE_HANDLE *,tagPAGE_LAYOUT_STRUCT *,_POINTL *,tagSIZE *,int)

- ea: `0x1800511f8`
- end: `0x1800515fe`
- name: `?InternalGdiPlayPageEMF@@YAHPEAUtagSPOOL_FILE_HANDLE@@PEAUtagPAGE_LAYOUT_STRUCT@@PEAU_POINTL@@PEAUtagSIZE@@H@Z`
- size: `1030`
- prototype: `__int64 __fastcall(struct tagSPOOL_FILE_HANDLE *, struct tagPAGE_LAYOUT_STRUCT *, struct _POINTL *, struct tagSIZE *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180050f50`

## callees

- `0x1800104e0`
- `0x1800317c8`
- `0x180031b30`
- `0x1800511f8`
- `0x1800518e0`
- `0x180051b0c`
- `0x180051bac`
- `0x18007ac50`
- `0x18007ba24`
- `0x180080b98`
- `0x180080ca4`
- `0x180093f18`

## import_xrefs

- `GDI32!CreateRectRgn` at `0x18005136d`
- `GDI32!CreateRectRgn` at `0x18005149b`
- `GDI32!CreateRectRgn` at `0x18005136d`
- `GDI32!CreateRectRgn` at `0x18005149b`
- `GDI32!LineTo` at `0x1800513a4`
- `GDI32!LineTo` at `0x1800513c7`
- `GDI32!LineTo` at `0x1800513ea`
- `GDI32!LineTo` at `0x18005140d`
- `GDI32!LineTo` at `0x1800513a4`
- `GDI32!LineTo` at `0x1800513c7`
- `GDI32!LineTo` at `0x1800513ea`
- `GDI32!LineTo` at `0x18005140d`
- `GDI32!MoveToEx` at `0x180051394`
- `GDI32!MoveToEx` at `0x1800513b7`
- `GDI32!MoveToEx` at `0x1800513da`
- `GDI32!MoveToEx` at `0x1800513fd`
- `GDI32!MoveToEx` at `0x180051394`
- `GDI32!MoveToEx` at `0x1800513b7`
- `GDI32!MoveToEx` at `0x1800513da`
- `GDI32!MoveToEx` at `0x1800513fd`
- `GDI32!RestoreDC` at `0x1800515b4`
- `GDI32!RestoreDC` at `0x1800515b4`
- `GDI32!SaveDC` at `0x1800514a7`
- `GDI32!SaveDC` at `0x1800514a7`
- `GDI32!SelectClipRgn` at `0x180051381`
- `GDI32!SelectClipRgn` at `0x18005141d`
- `GDI32!SelectClipRgn` at `0x1800514c7`
- `GDI32!SelectClipRgn` at `0x180051381`
- `GDI32!SelectClipRgn` at `0x18005141d`
- `GDI32!SelectClipRgn` at `0x1800514c7`
- `GDI32!SetWorldTransform` at `0x180051457`
- `GDI32!SetWorldTransform` at `0x1800515c1`
- `GDI32!SetWorldTransform` at `0x180051457`
- `GDI32!SetWorldTransform` at `0x1800515c1`
- `GDI32!DeleteObject` at `0x180051426`
- `GDI32!DeleteObject` at `0x1800515d6`
- `GDI32!DeleteObject` at `0x180051426`
- `GDI32!DeleteObject` at `0x1800515d6`
- `win32u!NtGdiGetPerBandInfo` at `0x180051348`
- `win32u!NtGdiGetPerBandInfo` at `0x180051348`
- `win32u!NtGdiGetTransform` at `0x180051438`
- `win32u!NtGdiGetTransform` at `0x180051438`

## pseudocode

```c
__int64 __fastcall InternalGdiPlayPageEMF(
        struct tagSPOOL_FILE_HANDLE *a1,
        struct tagPAGE_LAYOUT_STRUCT *a2,
        struct _POINTL *a3,
        struct tagSIZE *a4,
        int a5)
{
  struct tagSPOOL_FILE_HANDLE *v7; // rsi
  HDC v9; // rdi
  LONG x; // r12d
  LONG v11; // edx
  LONG y; // r13d
  LONG cy; // esi
  unsigned int v14; // edx
  HRGN v15; // rsi
  int v16; // r14d
  int v17; // r15d
  HRGN RectRgn; // rax
  __int64 result; // rax
  int v20; // r15d
  HRGN v21; // rsi
  int *v22; // rcx
  int v23; // r14d
  int v24; // edx
  int v25; // eax
  int v26; // r15d
  __int64 v27; // rcx
  struct tagSIZE *v28; // r9
  struct _POINTL *v29; // r8
  unsigned int v30; // ebx
  LONG v31; // [rsp+30h] [rbp-D0h]
  struct tagSIZE v32; // [rsp+38h] [rbp-C8h] BYREF
  struct _POINTL v33; // [rsp+40h] [rbp-C0h] BYREF
  struct tagRECT *v34; // [rsp+48h] [rbp-B8h]
  struct tagSPOOL_FILE_HANDLE *v35; // [rsp+50h] [rbp-B0h]
  __int64 v36[12]; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+C0h] [rbp-40h] BYREF
  int x2; // [rsp+C4h] [rbp-3Ch]
  int y2; // [rsp+C8h] [rbp-38h]
  int v40; // [rsp+CCh] [rbp-34h]
  int v41; // [rsp+D0h] [rbp-30h]
  XFORM xf; // [rsp+D8h] [rbp-28h] BYREF

  v35 = a1;
  v33 = 0;
  v7 = a1;
  v32 = 0;
  memset(&xf, 0, sizeof(xf));
  memset_0(v36, 0, sizeof(v36));
  v9 = (HDC)*((_QWORD *)v7 + 1);
  if ( a5 )
  {
    x = a3->x;
    v11 = a3->x;
    y = a3->y;
    LODWORD(v34) = a4->cx;
    v32.cx = (int)v34;
    cy = a4->cy;
    v33.x = x;
    v33.y = y;
    v31 = cy;
    v32.cy = cy;
    SetViewportOrgEx(v9, -v11, -y, 0);
    v7 = v35;
  }
  else
  {
    y = v33.y;
    x = v33.x;
    v31 = v32.cy;
    LODWORD(v34) = v32.cx;
  }
  v14 = *((_DWORD *)a2 + 2);
  if ( v14 )
    InternalProcessEMFRecord(v7, v14);
  if ( (*((_DWORD *)a2 + 18) != -1
     || *((_DWORD *)a2 + 20) != -1
     || *((_DWORD *)a2 + 19) != -1
     || *((_DWORD *)a2 + 17) != -1)
    && ModifyWorldTransform(v9, 0, 1u) )
  {
    v15 = 0;
    if ( a5 )
    {
      if ( !(unsigned int)IsMetafileWithGl(*(_QWORD *)a2) )
      {
        v16 = *((_DWORD *)a2 + 15) - *((_DWORD *)a2 + 13);
        v17 = *((_DWORD *)a2 + 16) - *((_DWORD *)a2 + 14);
        x2 = (int)v34;
        v40 = v16;
        v41 = v17;
        v37 = 0;
        y2 = v31;
        if ( (unsigned int)NtGdiGetPerBandInfo(v9, &v37) - 1 <= 0xFFFFFFFD && v40 == v16 && v41 == v17 )
        {
          RectRgn = CreateRectRgn(0, 0, x2, y2);
          v15 = RectRgn;
          if ( RectRgn )
            SelectClipRgn(v9, RectRgn);
        }
      }
    }
    MoveToEx(v9, *((_DWORD *)a2 + 17), *((_DWORD *)a2 + 18), 0);
    LineTo(v9, *((_DWORD *)a2 + 19), *((_DWORD *)a2 + 18));
    MoveToEx(v9, *((_DWORD *)a2 + 19), *((_DWORD *)a2 + 18), 0);
    LineTo(v9, *((_DWORD *)a2 + 19), *((_DWORD *)a2 + 20));
    MoveToEx(v9, *((_DWORD *)a2 + 19), *((_DWORD *)a2 + 20), 0);
    LineTo(v9, *((_DWORD *)a2 + 17), *((_DWORD *)a2 + 20));
    MoveToEx(v9, *((_DWORD *)a2 + 17), *((_DWORD *)a2 + 20), 0);
    LineTo(v9, *((_DWORD *)a2 + 17), *((_DWORD *)a2 + 18));
    if ( v15 )
    {
      SelectClipRgn(v9, 0);
      DeleteObject(v15);
    }
  }
  result = NtGdiGetTransform(v9, 515, &xf);
  if ( (_DWORD)result )
  {
    v20 = 0;
    v21 = 0;
    if ( !SetWorldTransform(v9, (const XFORM *)((char *)a2 + 12)) )
      goto LABEL_44;
    v22 = (int *)((char *)a2 + 36);
    v23 = 0;
    v24 = *((_DWORD *)a2 + 10);
    if ( v24 != -1 || *((_DWORD *)a2 + 12) != -1 || *((_DWORD *)a2 + 11) != -1 || (v34 = 0, *v22 != -1) )
    {
      v34 = (struct tagRECT *)((char *)a2 + 36);
      if ( !a5 )
      {
        v21 = CreateRectRgn(*v22, v24, *((_DWORD *)a2 + 11), *((_DWORD *)a2 + 12));
        v25 = SaveDC(v9);
        v23 = v25;
        if ( !v21 )
          goto LABEL_42;
        if ( !v25 )
          goto LABEL_44;
        if ( !SelectClipRgn(v9, v21) )
        {
LABEL_43:
          RestoreDC(v9, v23);
          goto LABEL_44;
        }
      }
    }
    v26 = IsMetafileWithGl(*(_QWORD *)a2);
    if ( v26 && !(unsigned int)InitGlPrinting(*(HENHMETAFILE *)a2, v9, (__int64)v36) )
    {
      v20 = 0;
LABEL_42:
      if ( v23 )
        goto LABEL_43;
LABEL_44:
      v30 = SetWorldTransform(v9, &xf) ? v20 : 0;
      if ( v21 )
        DeleteObject(v21);
      return v30;
    }
    if ( a5 )
    {
      if ( !v26 )
      {
        PrintBand(v9, *(HENHMETAFILE *)a2, &v33, (struct tagRECT *)((char *)a2 + 52), &v32, v34);
LABEL_40:
        v20 = 1;
        goto LABEL_42;
      }
      SetViewportOrgEx(v9, -x, -y, 0);
      v27 = *(_QWORD *)a2;
      v28 = &v32;
      v29 = &v33;
    }
    else
    {
      if ( !v26 )
      {
        PlayEnhMetaFile(v9, *(HENHMETAFILE *)a2, (const RECT *)((char *)a2 + 52));
        goto LABEL_40;
      }
      v28 = 0;
      v27 = *(_QWORD *)a2;
      v29 = 0;
    }
    PrintMfWithGl(v27, v36, v29, v28);
    EndGlPrinting(v36);
    goto LABEL_40;
  }
  return result;
}

```

## disassembly

```asm
0x1800511f8  push    rbp
0x1800511fa  push    rbx
0x1800511fb  push    rsi
0x1800511fc  push    rdi
0x1800511fd  push    r12
0x1800511ff  push    r13
0x180051201  push    r14
0x180051203  push    r15
0x180051205  lea     rbp, [rsp-8]
0x18005120a  sub     rsp, 108h
0x180051211  mov     rax, cs:__security_cookie
0x180051218  xor     rax, rsp
0x18005121b  mov     [rbp+40h+var_50], rax
0x18005121f  xor     eax, eax
0x180051221  mov     [rsp+140h+var_F0], rcx
0x180051226  mov     r13, r8
0x180051229  mov     qword ptr [rbp+40h+xf.eDx], rax
0x18005122d  mov     rbx, rdx
0x180051230  mov     qword ptr [rsp+140h+var_100.x], rax
0x180051235  mov     rsi, rcx
0x180051238  mov     qword ptr [rsp+140h+var_108.cx], rax
0x18005123d  xorps   xmm0, xmm0
0x180051240  lea     r8d, [rax+60h]; Size
0x180051244  xor     edx, edx; Val
0x180051246  lea     rcx, [rsp+140h+var_E0]; void *
0x18005124b  mov     r15, r9
0x18005124e  movups  xmmword ptr [rbp+40h+xf.eM11], xmm0
0x180051252  call    memset_0
0x180051257  mov     r14d, [rbp+40h+arg_20]
0x18005125b  mov     rdi, [rsi+8]
0x18005125f  test    r14d, r14d
0x180051262  jz      short loc_1800512AA
0x180051264  mov     r12d, [r13+0]
0x180051268  xor     r9d, r9d; lppt
0x18005126b  mov     esi, [r15]
0x18005126e  mov     edx, r12d
0x180051271  mov     r13d, [r13+4]
0x180051275  neg     edx; x
0x180051277  mov     r8d, r13d
0x18005127a  mov     dword ptr [rsp+140h+var_F8], esi
0x18005127e  mov     [rsp+140h+var_108.cx], esi
0x180051282  neg     r8d; y
0x180051285  mov     esi, [r15+4]
0x180051289  mov     rcx, rdi; hdc
0x18005128c  mov     [rsp+140h+var_100.x], r12d
0x180051291  mov     [rsp+140h+var_100.y], r13d
0x180051296  mov     [rsp+140h+var_110], esi
0x18005129a  mov     [rsp+140h+var_108.cy], esi
0x18005129e  call    SetViewportOrgEx
0x1800512a3  mov     rsi, [rsp+140h+var_F0]
0x1800512a8  jmp     short loc_1800512C4
0x1800512aa  mov     eax, [rsp+140h+var_108.cy]
0x1800512ae  mov     r13d, [rsp+140h+var_100.y]
0x1800512b3  mov     r12d, [rsp+140h+var_100.x]
0x1800512b8  mov     [rsp+140h+var_110], eax
0x1800512bc  mov     eax, [rsp+140h+var_108.cx]
0x1800512c0  mov     dword ptr [rsp+140h+var_F8], eax
0x1800512c4  mov     edx, [rbx+8]; unsigned int
0x1800512c7  test    edx, edx
0x1800512c9  jz      short loc_1800512D3
0x1800512cb  mov     rcx, rsi; struct tagSPOOL_FILE_HANDLE *
0x1800512ce  call    ?InternalProcessEMFRecord@@YAHPEAUtagSPOOL_FILE_HANDLE@@K@Z; InternalProcessEMFRecord(tagSPOOL_FILE_HANDLE *,ulong)
0x1800512d3  cmp     dword ptr [rbx+48h], 0FFFFFFFFh
0x1800512d7  jnz     short loc_1800512EF
0x1800512d9  cmp     dword ptr [rbx+50h], 0FFFFFFFFh
0x1800512dd  jnz     short loc_1800512EF
0x1800512df  cmp     dword ptr [rbx+4Ch], 0FFFFFFFFh
0x1800512e3  jnz     short loc_1800512EF
0x1800512e5  cmp     dword ptr [rbx+44h], 0FFFFFFFFh
0x1800512e9  jz      loc_18005142C
0x1800512ef  xor     edx, edx; lpxf
0x1800512f1  mov     rcx, rdi; hdc
0x1800512f4  lea     r8d, [rdx+1]; mode
0x1800512f8  call    ModifyWorldTransform
0x1800512fd  test    eax, eax
0x1800512ff  jz      loc_18005142C
0x180051305  xor     esi, esi
0x180051307  test    r14d, r14d
0x18005130a  jz      short loc_180051387
0x18005130c  mov     rcx, [rbx]
0x18005130f  call    IsMetafileWithGl
0x180051314  test    eax, eax
0x180051316  jnz     short loc_180051387
0x180051318  mov     eax, dword ptr [rsp+140h+var_F8]
0x18005131c  lea     rdx, [rbp+40h+var_80]
0x180051320  mov     r14d, [rbx+3Ch]
0x180051324  mov     rcx, rdi
0x180051327  mov     r15d, [rbx+40h]
0x18005132b  sub     r14d, [rbx+34h]
0x18005132f  sub     r15d, [rbx+38h]
0x180051333  mov     [rbp+40h+x2], eax
0x180051336  mov     eax, [rsp+140h+var_110]
0x18005133a  mov     [rbp+40h+var_74], r14d
0x18005133e  mov     [rbp+40h+var_70], r15d
0x180051342  mov     [rbp+40h+var_80], esi
0x180051345  mov     [rbp+40h+y2], eax
0x180051348  call    cs:__imp_NtGdiGetPerBandInfo
0x18005134e  dec     eax
0x180051350  cmp     eax, 0FFFFFFFDh
0x180051353  ja      short loc_180051387
0x180051355  cmp     [rbp+40h+var_74], r14d
0x180051359  jnz     short loc_180051387
0x18005135b  cmp     [rbp+40h+var_70], r15d
0x18005135f  jnz     short loc_180051387
0x180051361  mov     r9d, [rbp+40h+y2]; y2
0x180051365  xor     edx, edx; y1
0x180051367  mov     r8d, [rbp+40h+x2]; x2
0x18005136b  xor     ecx, ecx; x1
0x18005136d  call    cs:__imp_CreateRectRgn
0x180051373  mov     rsi, rax
0x180051376  test    rax, rax
0x180051379  jz      short loc_180051387
0x18005137b  mov     rdx, rax; hrgn
0x18005137e  mov     rcx, rdi; hdc
0x180051381  call    cs:__imp_SelectClipRgn
0x180051387  mov     r8d, [rbx+48h]; y
0x18005138b  xor     r9d, r9d; lppt
0x18005138e  mov     edx, [rbx+44h]; x
0x180051391  mov     rcx, rdi; hdc
0x180051394  call    cs:__imp_MoveToEx
0x18005139a  mov     r8d, [rbx+48h]; y
0x18005139e  mov     rcx, rdi; hdc
0x1800513a1  mov     edx, [rbx+4Ch]; x
0x1800513a4  call    cs:__imp_LineTo
0x1800513aa  mov     r8d, [rbx+48h]; y
0x1800513ae  xor     r9d, r9d; lppt
0x1800513b1  mov     edx, [rbx+4Ch]; x
0x1800513b4  mov     rcx, rdi; hdc
0x1800513b7  call    cs:__imp_MoveToEx
0x1800513bd  mov     r8d, [rbx+50h]; y
0x1800513c1  mov     rcx, rdi; hdc
0x1800513c4  mov     edx, [rbx+4Ch]; x
0x1800513c7  call    cs:__imp_LineTo
0x1800513cd  mov     r8d, [rbx+50h]; y
0x1800513d1  xor     r9d, r9d; lppt
0x1800513d4  mov     edx, [rbx+4Ch]; x
0x1800513d7  mov     rcx, rdi; hdc
0x1800513da  call    cs:__imp_MoveToEx
0x1800513e0  mov     r8d, [rbx+50h]; y
0x1800513e4  mov     rcx, rdi; hdc
0x1800513e7  mov     edx, [rbx+44h]; x
0x1800513ea  call    cs:__imp_LineTo
0x1800513f0  mov     r8d, [rbx+50h]; y
0x1800513f4  xor     r9d, r9d; lppt
0x1800513f7  mov     edx, [rbx+44h]; x
0x1800513fa  mov     rcx, rdi; hdc
0x1800513fd  call    cs:__imp_MoveToEx
0x180051403  mov     r8d, [rbx+48h]; y
0x180051407  mov     rcx, rdi; hdc
0x18005140a  mov     edx, [rbx+44h]; x
0x18005140d  call    cs:__imp_LineTo
0x180051413  test    rsi, rsi
0x180051416  jz      short loc_18005142C
0x180051418  xor     edx, edx; hrgn
0x18005141a  mov     rcx, rdi; hdc
0x18005141d  call    cs:__imp_SelectClipRgn
0x180051423  mov     rcx, rsi; ho
0x180051426  call    cs:__imp_DeleteObject
0x18005142c  lea     r8, [rbp+40h+xf]
0x180051430  mov     edx, 203h
0x180051435  mov     rcx, rdi
0x180051438  call    cs:__imp_NtGdiGetTransform
0x18005143e  test    eax, eax
0x180051440  jz      loc_1800515DE
0x180051446  xor     r15d, r15d
0x180051449  lea     rdx, [rbx+0Ch]; lpxf
0x18005144d  mov     rcx, rdi; hdc
0x180051450  mov     [rsp+140h+var_110], r15d
0x180051455  xor     esi, esi
0x180051457  call    cs:__imp_SetWorldTransform
0x18005145d  test    eax, eax
0x18005145f  jz      loc_1800515BA
0x180051465  lea     rcx, [rbx+24h]
0x180051469  xor     r14d, r14d
0x18005146c  mov     edx, [rcx+4]; y1
0x18005146f  cmp     edx, 0FFFFFFFFh
0x180051472  jnz     short loc_180051487
0x180051474  cmp     [rcx+0Ch], edx
0x180051477  jnz     short loc_180051487
0x180051479  cmp     [rcx+8], edx
0x18005147c  jnz     short loc_180051487
0x18005147e  mov     [rsp+140h+var_F8], rsi
0x180051483  cmp     [rcx], edx
0x180051485  jz      short loc_1800514D5
0x180051487  mov     [rsp+140h+var_F8], rcx
0x18005148c  cmp     [rbp+40h+arg_20], esi
0x18005148f  jnz     short loc_1800514D5
0x180051491  mov     r9d, [rcx+0Ch]; y2
0x180051495  mov     r8d, [rcx+8]; x2
0x180051499  mov     ecx, [rcx]; x1
0x18005149b  call    cs:__imp_CreateRectRgn
0x1800514a1  mov     rcx, rdi; hdc
0x1800514a4  mov     rsi, rax
0x1800514a7  call    cs:__imp_SaveDC
0x1800514ad  mov     r14d, eax
0x1800514b0  test    rsi, rsi
0x1800514b3  jz      loc_1800515A9
0x1800514b9  test    eax, eax
0x1800514bb  jz      loc_1800515BA
0x1800514c1  mov     rdx, rsi; hrgn
0x1800514c4  mov     rcx, rdi; hdc
0x1800514c7  call    cs:__imp_SelectClipRgn
0x1800514cd  test    eax, eax
0x1800514cf  jz      loc_1800515AE
0x1800514d5  mov     rcx, [rbx]
0x1800514d8  call    IsMetafileWithGl
0x1800514dd  mov     r15d, eax
0x1800514e0  test    eax, eax
0x1800514e2  jz      short loc_18005150E
0x1800514e4  mov     r9, [rsp+140h+var_F0]
0x1800514e9  lea     rax, [rsp+140h+var_E0]
0x1800514ee  mov     rcx, [rbx]; hemf
0x1800514f1  lea     r8, [rbx+34h]
0x1800514f5  mov     rdx, rdi; hdc
0x1800514f8  mov     [rsp+140h+var_120], rax; __int64
0x1800514fd  mov     r9, [r9+20h]
0x180051501  call    InitGlPrinting
0x180051506  test    eax, eax
0x180051508  jz      loc_1800515A4
0x18005150e  cmp     [rbp+40h+arg_20], 0
0x180051512  jz      short loc_180051566
0x180051514  mov     rcx, rdi; hdc
0x180051517  test    r15d, r15d
0x18005151a  jz      short loc_18005153F
0x18005151c  neg     r13d
0x18005151f  neg     r12d
0x180051522  mov     r8d, r13d; y
0x180051525  mov     edx, r12d; x
0x180051528  xor     r9d, r9d; lppt
0x18005152b  call    SetViewportOrgEx
0x180051530  mov     rcx, [rbx]
0x180051533  lea     r9, [rsp+140h+var_108]
0x180051538  lea     r8, [rsp+140h+var_100]
0x18005153d  jmp     short loc_180051577
0x18005153f  mov     rax, [rsp+140h+var_F8]
0x180051544  lea     r9, [rbx+34h]; struct tagRECT *
0x180051548  mov     rdx, [rbx]; HENHMETAFILE
0x18005154b  lea     r8, [rsp+140h+var_100]; struct _POINTL *
0x180051550  mov     [rsp+140h+var_118], rax; struct tagRECT *
0x180051555  lea     rax, [rsp+140h+var_108]
0x18005155a  mov     [rsp+140h+var_120], rax; struct tagSIZE *
0x18005155f  call    ?PrintBand@@YAXPEAUHDC__@@PEAUHENHMETAFILE__@@PEAU_POINTL@@PEAUtagRECT@@PEAUtagSIZE@@3@Z; PrintBand(HDC__ *,HENHMETAFILE__ *,_POINTL *,tagRECT *,tagSIZE *,tagRECT *)
0x180051564  jmp     short loc_18005159C
0x180051566  mov     rax, [rbx]
0x180051569  test    r15d, r15d
0x18005156c  jz      short loc_18005158D
0x18005156e  xor     r9d, r9d
0x180051571  mov     rcx, rax
0x180051574  xor     r8d, r8d
0x180051577  lea     rdx, [rsp+140h+var_E0]
0x18005157c  call    PrintMfWithGl
0x180051581  lea     rcx, [rsp+140h+var_E0]
0x180051586  call    EndGlPrinting
0x18005158b  jmp     short loc_18005159C
0x18005158d  lea     r8, [rbx+34h]; lprect
0x180051591  mov     rdx, rax; hmf
0x180051594  mov     rcx, rdi; hdc
0x180051597  call    PlayEnhMetaFile
0x18005159c  mov     r15d, 1
0x1800515a2  jmp     short loc_1800515A9
0x1800515a4  mov     r15d, [rsp+140h+var_110]
0x1800515a9  test    r14d, r14d
0x1800515ac  jz      short loc_1800515BA
0x1800515ae  mov     edx, r14d; nSavedDC
0x1800515b1  mov     rcx, rdi; hdc
0x1800515b4  call    cs:__imp_RestoreDC
0x1800515ba  lea     rdx, [rbp+40h+xf]; lpxf
0x1800515be  mov     rcx, rdi; hdc
0x1800515c1  call    cs:__imp_SetWorldTransform
0x1800515c7  neg     eax
0x1800515c9  sbb     ebx, ebx
0x1800515cb  and     ebx, r15d
0x1800515ce  test    rsi, rsi
0x1800515d1  jz      short loc_1800515DC
0x1800515d3  mov     rcx, rsi; ho
0x1800515d6  call    cs:__imp_DeleteObject
0x1800515dc  mov     eax, ebx
0x1800515de  mov     rcx, [rbp+40h+var_50]
0x1800515e2  xor     rcx, rsp; StackCookie
0x1800515e5  call    __security_check_cookie
0x1800515ea  add     rsp, 108h
0x1800515f1  pop     r15
0x1800515f3  pop     r14
0x1800515f5  pop     r13
0x1800515f7  pop     r12
0x1800515f9  pop     rdi
0x1800515fa  pop     rsi
0x1800515fb  pop     rbx
0x1800515fc  pop     rbp
0x1800515fd  retn
```
