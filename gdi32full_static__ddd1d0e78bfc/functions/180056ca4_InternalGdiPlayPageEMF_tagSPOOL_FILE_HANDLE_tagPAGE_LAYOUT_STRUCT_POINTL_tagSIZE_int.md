# InternalGdiPlayPageEMF(tagSPOOL_FILE_HANDLE *,tagPAGE_LAYOUT_STRUCT *,_POINTL *,tagSIZE *,int)

- ea: `0x180056ca4`
- end: `0x180057131`
- name: `?InternalGdiPlayPageEMF@@YAHPEAUtagSPOOL_FILE_HANDLE@@PEAUtagPAGE_LAYOUT_STRUCT@@PEAU_POINTL@@PEAUtagSIZE@@H@Z`
- size: `1165`
- prototype: `__int64 __fastcall(struct tagSPOOL_FILE_HANDLE *, struct tagPAGE_LAYOUT_STRUCT *, struct _POINTL *, struct tagSIZE *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800569d0`

## callees

- `0x180018c30`
- `0x180056ca4`
- `0x180057410`
- `0x180057670`
- `0x180057710`
- `0x18006e3c8`
- `0x18006e760`
- `0x18007f800`
- `0x180080604`
- `0x180085ad4`
- `0x180085bf0`
- `0x180099ca8`

## import_xrefs

- `GDI32!CreateRectRgn` at `0x180056e27`
- `GDI32!CreateRectRgn` at `0x180056fa9`
- `GDI32!CreateRectRgn` at `0x180056e27`
- `GDI32!CreateRectRgn` at `0x180056fa9`
- `GDI32!LineTo` at `0x180056e70`
- `GDI32!LineTo` at `0x180056e9f`
- `GDI32!LineTo` at `0x180056ece`
- `GDI32!LineTo` at `0x180056efd`
- `GDI32!LineTo` at `0x180056e70`
- `GDI32!LineTo` at `0x180056e9f`
- `GDI32!LineTo` at `0x180056ece`
- `GDI32!LineTo` at `0x180056efd`
- `GDI32!MoveToEx` at `0x180056e5a`
- `GDI32!MoveToEx` at `0x180056e89`
- `GDI32!MoveToEx` at `0x180056eb8`
- `GDI32!MoveToEx` at `0x180056ee7`
- `GDI32!MoveToEx` at `0x180056e5a`
- `GDI32!MoveToEx` at `0x180056e89`
- `GDI32!MoveToEx` at `0x180056eb8`
- `GDI32!MoveToEx` at `0x180056ee7`
- `GDI32!RestoreDC` at `0x1800570d4`
- `GDI32!RestoreDC` at `0x1800570d4`
- `GDI32!SaveDC` at `0x180056fbb`
- `GDI32!SaveDC` at `0x180056fbb`
- `GDI32!SelectClipRgn` at `0x180056e41`
- `GDI32!SelectClipRgn` at `0x180056f13`
- `GDI32!SelectClipRgn` at `0x180056fe1`
- `GDI32!SelectClipRgn` at `0x180056e41`
- `GDI32!SelectClipRgn` at `0x180056f13`
- `GDI32!SelectClipRgn` at `0x180056fe1`
- `GDI32!SetWorldTransform` at `0x180056f5f`
- `GDI32!SetWorldTransform` at `0x1800570e7`
- `GDI32!SetWorldTransform` at `0x180056f5f`
- `GDI32!SetWorldTransform` at `0x1800570e7`
- `GDI32!DeleteObject` at `0x180056f22`
- `GDI32!DeleteObject` at `0x180057102`
- `GDI32!DeleteObject` at `0x180056f22`
- `GDI32!DeleteObject` at `0x180057102`
- `win32u!NtGdiGetPerBandInfo` at `0x180056dfc`
- `win32u!NtGdiGetPerBandInfo` at `0x180056dfc`
- `win32u!NtGdiGetTransform` at `0x180056f3a`
- `win32u!NtGdiGetTransform` at `0x180056f3a`

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
0x180056ca4  push    rbp
0x180056ca6  push    rbx
0x180056ca7  push    rsi
0x180056ca8  push    rdi
0x180056ca9  push    r12
0x180056cab  push    r13
0x180056cad  push    r14
0x180056caf  push    r15
0x180056cb1  lea     rbp, [rsp-8]
0x180056cb6  sub     rsp, 108h
0x180056cbd  mov     rax, cs:__security_cookie
0x180056cc4  xor     rax, rsp
0x180056cc7  mov     [rbp+40h+var_50], rax
0x180056ccb  xor     eax, eax
0x180056ccd  mov     [rsp+140h+var_F0], rcx
0x180056cd2  mov     r13, r8
0x180056cd5  mov     qword ptr [rbp+40h+xf.eDx], rax
0x180056cd9  mov     rbx, rdx
0x180056cdc  mov     qword ptr [rsp+140h+var_100.x], rax
0x180056ce1  mov     rsi, rcx
0x180056ce4  mov     qword ptr [rsp+140h+var_108.cx], rax
0x180056ce9  xorps   xmm0, xmm0
0x180056cec  lea     r8d, [rax+60h]; Size
0x180056cf0  xor     edx, edx; Val
0x180056cf2  lea     rcx, [rsp+140h+var_E0]; void *
0x180056cf7  mov     r15, r9
0x180056cfa  movups  xmmword ptr [rbp+40h+xf.eM11], xmm0
0x180056cfe  call    memset_0
0x180056d03  mov     r14d, [rbp+40h+arg_20]
0x180056d07  mov     rdi, [rsi+8]
0x180056d0b  test    r14d, r14d
0x180056d0e  jz      short loc_180056D56
0x180056d10  mov     r12d, [r13+0]
0x180056d14  xor     r9d, r9d; lppt
0x180056d17  mov     esi, [r15]
0x180056d1a  mov     edx, r12d
0x180056d1d  mov     r13d, [r13+4]
0x180056d21  neg     edx; x
0x180056d23  mov     r8d, r13d
0x180056d26  mov     dword ptr [rsp+140h+var_F8], esi
0x180056d2a  mov     [rsp+140h+var_108.cx], esi
0x180056d2e  neg     r8d; y
0x180056d31  mov     esi, [r15+4]
0x180056d35  mov     rcx, rdi; hdc
0x180056d38  mov     [rsp+140h+var_100.x], r12d
0x180056d3d  mov     [rsp+140h+var_100.y], r13d
0x180056d42  mov     [rsp+140h+var_110], esi
0x180056d46  mov     [rsp+140h+var_108.cy], esi
0x180056d4a  call    SetViewportOrgEx
0x180056d4f  mov     rsi, [rsp+140h+var_F0]
0x180056d54  jmp     short loc_180056D70
0x180056d56  mov     eax, [rsp+140h+var_108.cy]
0x180056d5a  mov     r13d, [rsp+140h+var_100.y]
0x180056d5f  mov     r12d, [rsp+140h+var_100.x]
0x180056d64  mov     [rsp+140h+var_110], eax
0x180056d68  mov     eax, [rsp+140h+var_108.cx]
0x180056d6c  mov     dword ptr [rsp+140h+var_F8], eax
0x180056d70  mov     edx, [rbx+8]; unsigned int
0x180056d73  test    edx, edx
0x180056d75  jz      short loc_180056D7F
0x180056d77  mov     rcx, rsi; struct tagSPOOL_FILE_HANDLE *
0x180056d7a  call    ?InternalProcessEMFRecord@@YAHPEAUtagSPOOL_FILE_HANDLE@@K@Z; InternalProcessEMFRecord(tagSPOOL_FILE_HANDLE *,ulong)
0x180056d7f  cmp     dword ptr [rbx+48h], 0FFFFFFFFh
0x180056d83  jnz     short loc_180056D9B
0x180056d85  cmp     dword ptr [rbx+50h], 0FFFFFFFFh
0x180056d89  jnz     short loc_180056D9B
0x180056d8b  cmp     dword ptr [rbx+4Ch], 0FFFFFFFFh
0x180056d8f  jnz     short loc_180056D9B
0x180056d91  cmp     dword ptr [rbx+44h], 0FFFFFFFFh
0x180056d95  jz      loc_180056F2E
0x180056d9b  xor     edx, edx; lpxf
0x180056d9d  mov     rcx, rdi; hdc
0x180056da0  lea     r8d, [rdx+1]; mode
0x180056da4  call    ModifyWorldTransform
0x180056da9  test    eax, eax
0x180056dab  jz      loc_180056F2E
0x180056db1  xor     esi, esi
0x180056db3  test    r14d, r14d
0x180056db6  jz      loc_180056E4D
0x180056dbc  mov     rcx, [rbx]
0x180056dbf  call    IsMetafileWithGl
0x180056dc4  test    eax, eax
0x180056dc6  jnz     loc_180056E4D
0x180056dcc  mov     eax, dword ptr [rsp+140h+var_F8]
0x180056dd0  lea     rdx, [rbp+40h+var_80]
0x180056dd4  mov     r14d, [rbx+3Ch]
0x180056dd8  mov     rcx, rdi
0x180056ddb  mov     r15d, [rbx+40h]
0x180056ddf  sub     r14d, [rbx+34h]
0x180056de3  sub     r15d, [rbx+38h]
0x180056de7  mov     [rbp+40h+x2], eax
0x180056dea  mov     eax, [rsp+140h+var_110]
0x180056dee  mov     [rbp+40h+var_74], r14d
0x180056df2  mov     [rbp+40h+var_70], r15d
0x180056df6  mov     [rbp+40h+var_80], esi
0x180056df9  mov     [rbp+40h+y2], eax
0x180056dfc  call    cs:__imp_NtGdiGetPerBandInfo
0x180056e03  nop     dword ptr [rax+rax+00h]
0x180056e08  dec     eax
0x180056e0a  cmp     eax, 0FFFFFFFDh
0x180056e0d  ja      short loc_180056E4D
0x180056e0f  cmp     [rbp+40h+var_74], r14d
0x180056e13  jnz     short loc_180056E4D
0x180056e15  cmp     [rbp+40h+var_70], r15d
0x180056e19  jnz     short loc_180056E4D
0x180056e1b  mov     r9d, [rbp+40h+y2]; y2
0x180056e1f  xor     edx, edx; y1
0x180056e21  mov     r8d, [rbp+40h+x2]; x2
0x180056e25  xor     ecx, ecx; x1
0x180056e27  call    cs:__imp_CreateRectRgn
0x180056e2e  nop     dword ptr [rax+rax+00h]
0x180056e33  mov     rsi, rax
0x180056e36  test    rax, rax
0x180056e39  jz      short loc_180056E4D
0x180056e3b  mov     rdx, rax; hrgn
0x180056e3e  mov     rcx, rdi; hdc
0x180056e41  call    cs:__imp_SelectClipRgn
0x180056e48  nop     dword ptr [rax+rax+00h]
0x180056e4d  mov     r8d, [rbx+48h]; y
0x180056e51  xor     r9d, r9d; lppt
0x180056e54  mov     edx, [rbx+44h]; x
0x180056e57  mov     rcx, rdi; hdc
0x180056e5a  call    cs:__imp_MoveToEx
0x180056e61  nop     dword ptr [rax+rax+00h]
0x180056e66  mov     r8d, [rbx+48h]; y
0x180056e6a  mov     rcx, rdi; hdc
0x180056e6d  mov     edx, [rbx+4Ch]; x
0x180056e70  call    cs:__imp_LineTo
0x180056e77  nop     dword ptr [rax+rax+00h]
0x180056e7c  mov     r8d, [rbx+48h]; y
0x180056e80  xor     r9d, r9d; lppt
0x180056e83  mov     edx, [rbx+4Ch]; x
0x180056e86  mov     rcx, rdi; hdc
0x180056e89  call    cs:__imp_MoveToEx
0x180056e90  nop     dword ptr [rax+rax+00h]
0x180056e95  mov     r8d, [rbx+50h]; y
0x180056e99  mov     rcx, rdi; hdc
0x180056e9c  mov     edx, [rbx+4Ch]; x
0x180056e9f  call    cs:__imp_LineTo
0x180056ea6  nop     dword ptr [rax+rax+00h]
0x180056eab  mov     r8d, [rbx+50h]; y
0x180056eaf  xor     r9d, r9d; lppt
0x180056eb2  mov     edx, [rbx+4Ch]; x
0x180056eb5  mov     rcx, rdi; hdc
0x180056eb8  call    cs:__imp_MoveToEx
0x180056ebf  nop     dword ptr [rax+rax+00h]
0x180056ec4  mov     r8d, [rbx+50h]; y
0x180056ec8  mov     rcx, rdi; hdc
0x180056ecb  mov     edx, [rbx+44h]; x
0x180056ece  call    cs:__imp_LineTo
0x180056ed5  nop     dword ptr [rax+rax+00h]
0x180056eda  mov     r8d, [rbx+50h]; y
0x180056ede  xor     r9d, r9d; lppt
0x180056ee1  mov     edx, [rbx+44h]; x
0x180056ee4  mov     rcx, rdi; hdc
0x180056ee7  call    cs:__imp_MoveToEx
0x180056eee  nop     dword ptr [rax+rax+00h]
0x180056ef3  mov     r8d, [rbx+48h]; y
0x180056ef7  mov     rcx, rdi; hdc
0x180056efa  mov     edx, [rbx+44h]; x
0x180056efd  call    cs:__imp_LineTo
0x180056f04  nop     dword ptr [rax+rax+00h]
0x180056f09  test    rsi, rsi
0x180056f0c  jz      short loc_180056F2E
0x180056f0e  xor     edx, edx; hrgn
0x180056f10  mov     rcx, rdi; hdc
0x180056f13  call    cs:__imp_SelectClipRgn
0x180056f1a  nop     dword ptr [rax+rax+00h]
0x180056f1f  mov     rcx, rsi; ho
0x180056f22  call    cs:__imp_DeleteObject
0x180056f29  nop     dword ptr [rax+rax+00h]
0x180056f2e  lea     r8, [rbp+40h+xf]
0x180056f32  mov     edx, 203h
0x180056f37  mov     rcx, rdi
0x180056f3a  call    cs:__imp_NtGdiGetTransform
0x180056f41  nop     dword ptr [rax+rax+00h]
0x180056f46  test    eax, eax
0x180056f48  jz      loc_180057110
0x180056f4e  xor     r15d, r15d
0x180056f51  lea     rdx, [rbx+0Ch]; lpxf
0x180056f55  mov     rcx, rdi; hdc
0x180056f58  mov     [rsp+140h+var_110], r15d
0x180056f5d  xor     esi, esi
0x180056f5f  call    cs:__imp_SetWorldTransform
0x180056f66  nop     dword ptr [rax+rax+00h]
0x180056f6b  test    eax, eax
0x180056f6d  jz      loc_1800570E0
0x180056f73  lea     rcx, [rbx+24h]
0x180056f77  xor     r14d, r14d
0x180056f7a  mov     edx, [rcx+4]; y1
0x180056f7d  cmp     edx, 0FFFFFFFFh
0x180056f80  jnz     short loc_180056F95
0x180056f82  cmp     [rcx+0Ch], edx
0x180056f85  jnz     short loc_180056F95
0x180056f87  cmp     [rcx+8], edx
0x180056f8a  jnz     short loc_180056F95
0x180056f8c  mov     [rsp+140h+var_F8], rsi
0x180056f91  cmp     [rcx], edx
0x180056f93  jz      short loc_180056FF5
0x180056f95  mov     [rsp+140h+var_F8], rcx
0x180056f9a  cmp     [rbp+40h+arg_20], esi
0x180056f9d  jnz     short loc_180056FF5
0x180056f9f  mov     r9d, [rcx+0Ch]; y2
0x180056fa3  mov     r8d, [rcx+8]; x2
0x180056fa7  mov     ecx, [rcx]; x1
0x180056fa9  call    cs:__imp_CreateRectRgn
0x180056fb0  nop     dword ptr [rax+rax+00h]
0x180056fb5  mov     rcx, rdi; hdc
0x180056fb8  mov     rsi, rax
0x180056fbb  call    cs:__imp_SaveDC
0x180056fc2  nop     dword ptr [rax+rax+00h]
0x180056fc7  mov     r14d, eax
0x180056fca  test    rsi, rsi
0x180056fcd  jz      loc_1800570C9
0x180056fd3  test    eax, eax
0x180056fd5  jz      loc_1800570E0
0x180056fdb  mov     rdx, rsi; hrgn
0x180056fde  mov     rcx, rdi; hdc
0x180056fe1  call    cs:__imp_SelectClipRgn
0x180056fe8  nop     dword ptr [rax+rax+00h]
0x180056fed  test    eax, eax
0x180056fef  jz      loc_1800570CE
0x180056ff5  mov     rcx, [rbx]
0x180056ff8  call    IsMetafileWithGl
0x180056ffd  mov     r15d, eax
0x180057000  test    eax, eax
0x180057002  jz      short loc_18005702E
0x180057004  mov     r9, [rsp+140h+var_F0]
0x180057009  lea     rax, [rsp+140h+var_E0]
0x18005700e  mov     rcx, [rbx]; hemf
0x180057011  lea     r8, [rbx+34h]
0x180057015  mov     rdx, rdi; hdc
0x180057018  mov     [rsp+140h+var_120], rax; __int64
0x18005701d  mov     r9, [r9+20h]
0x180057021  call    InitGlPrinting
0x180057026  test    eax, eax
0x180057028  jz      loc_1800570C4
0x18005702e  cmp     [rbp+40h+arg_20], 0
0x180057032  jz      short loc_180057086
0x180057034  mov     rcx, rdi; hdc
0x180057037  test    r15d, r15d
0x18005703a  jz      short loc_18005705F
0x18005703c  neg     r13d
0x18005703f  neg     r12d
0x180057042  mov     r8d, r13d; y
0x180057045  mov     edx, r12d; x
0x180057048  xor     r9d, r9d; lppt
0x18005704b  call    SetViewportOrgEx
0x180057050  mov     rcx, [rbx]
0x180057053  lea     r9, [rsp+140h+var_108]
0x180057058  lea     r8, [rsp+140h+var_100]
0x18005705d  jmp     short loc_180057097
0x18005705f  mov     rax, [rsp+140h+var_F8]
0x180057064  lea     r9, [rbx+34h]; struct tagRECT *
0x180057068  mov     rdx, [rbx]; HENHMETAFILE
0x18005706b  lea     r8, [rsp+140h+var_100]; struct _POINTL *
0x180057070  mov     [rsp+140h+var_118], rax; struct tagRECT *
0x180057075  lea     rax, [rsp+140h+var_108]
0x18005707a  mov     [rsp+140h+var_120], rax; struct tagSIZE *
0x18005707f  call    ?PrintBand@@YAXPEAUHDC__@@PEAUHENHMETAFILE__@@PEAU_POINTL@@PEAUtagRECT@@PEAUtagSIZE@@3@Z; PrintBand(HDC__ *,HENHMETAFILE__ *,_POINTL *,tagRECT *,tagSIZE *,tagRECT *)
0x180057084  jmp     short loc_1800570BC
0x180057086  mov     rax, [rbx]
0x180057089  test    r15d, r15d
0x18005708c  jz      short loc_1800570AD
0x18005708e  xor     r9d, r9d
0x180057091  mov     rcx, rax
0x180057094  xor     r8d, r8d
0x180057097  lea     rdx, [rsp+140h+var_E0]
0x18005709c  call    PrintMfWithGl
0x1800570a1  lea     rcx, [rsp+140h+var_E0]
0x1800570a6  call    EndGlPrinting
0x1800570ab  jmp     short loc_1800570BC
0x1800570ad  lea     r8, [rbx+34h]; lprect
0x1800570b1  mov     rdx, rax; hmf
0x1800570b4  mov     rcx, rdi; hdc
0x1800570b7  call    PlayEnhMetaFile
0x1800570bc  mov     r15d, 1
0x1800570c2  jmp     short loc_1800570C9
0x1800570c4  mov     r15d, [rsp+140h+var_110]
0x1800570c9  test    r14d, r14d
0x1800570cc  jz      short loc_1800570E0
0x1800570ce  mov     edx, r14d; nSavedDC
0x1800570d1  mov     rcx, rdi; hdc
0x1800570d4  call    cs:__imp_RestoreDC
0x1800570db  nop     dword ptr [rax+rax+00h]
0x1800570e0  lea     rdx, [rbp+40h+xf]; lpxf
0x1800570e4  mov     rcx, rdi; hdc
0x1800570e7  call    cs:__imp_SetWorldTransform
0x1800570ee  nop     dword ptr [rax+rax+00h]
0x1800570f3  neg     eax
0x1800570f5  sbb     ebx, ebx
0x1800570f7  and     ebx, r15d
0x1800570fa  test    rsi, rsi
0x1800570fd  jz      short loc_18005710E
0x1800570ff  mov     rcx, rsi; ho
0x180057102  call    cs:__imp_DeleteObject
0x180057109  nop     dword ptr [rax+rax+00h]
0x18005710e  mov     eax, ebx
0x180057110  mov     rcx, [rbp+40h+var_50]
0x180057114  xor     rcx, rsp; StackCookie
  ... truncated ...
```
