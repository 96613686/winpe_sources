# CUspShapingDrawingSurface::VerticalFETextOut(HDC__ *,void * *,long,long,uint,tagRECT const *,ushort const *,long,long const *,long const *,tagGOFFSET const *)

- ea: `0x18009d9e4`
- end: `0x18009df18`
- name: `?VerticalFETextOut@CUspShapingDrawingSurface@@AEAAJPEAUHDC__@@PEAPEAXJJIPEBUtagRECT@@PEBGJPEBJ4PEBUtagGOFFSET@@@Z`
- size: `1332`
- prototype: `int(CUspShapingDrawingSurface *__hidden this, HDC, void **, int, int, unsigned int, const struct tagRECT *, const unsigned __int16 *, int, const int *, const int *, const struct tagGOFFSET *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1800059d0`

## callees

- `0x180004c00`
- `0x180006978`
- `0x1800069b0`
- `0x180019630`
- `0x1800209d0`
- `0x180021b90`
- `0x180021e50`
- `0x180022b20`
- `0x18002ef90`
- `0x18004a0cc`
- `0x18007f800`
- `0x18009d9e4`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dc83`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dca4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dcf9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dd14`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dd37`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dd52`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009ddb3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009ddca`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dde9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009de09`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009de8d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dead`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dc83`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dca4`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dcf9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dd14`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dd37`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dd52`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009ddb3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009ddca`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dde9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009de09`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009de8d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009dead`
- `GDI32!ExtTextOutW` at `0x18009db91`
- `GDI32!ExtTextOutW` at `0x18009dd91`
- `GDI32!ExtTextOutW` at `0x18009db91`
- `GDI32!ExtTextOutW` at `0x18009dd91`
- `GDI32!MoveToEx` at `0x18009dec8`
- `GDI32!MoveToEx` at `0x18009dec8`
- `GDI32!SelectObject` at `0x18009dc2c`
- `GDI32!SelectObject` at `0x18009de41`
- `GDI32!SelectObject` at `0x18009dc2c`
- `GDI32!SelectObject` at `0x18009de41`
- `GDI32!SetBkMode` at `0x18009dbad`
- `GDI32!SetBkMode` at `0x18009de6d`
- `GDI32!SetBkMode` at `0x18009dbad`
- `GDI32!SetBkMode` at `0x18009de6d`
- `GDI32!SetTextAlign` at `0x18009dae3`
- `GDI32!SetTextAlign` at `0x18009dedb`
- `GDI32!SetTextAlign` at `0x18009dae3`
- `GDI32!SetTextAlign` at `0x18009dedb`
- `GDI32!DeleteObject` at `0x18009de55`
- `GDI32!DeleteObject` at `0x18009de55`

## pseudocode

```c
__int64 __fastcall CUspShapingDrawingSurface::VerticalFETextOut(
        CUspShapingDrawingSurface *this,
        HDC a2,
        INT *a3,
        LONG a4,
        LONG a5,
        unsigned int a6,
        struct tagRECT *a7,
        const unsigned __int16 *a8,
        int a9,
        const int *a10,
        const int *a11,
        const struct tagGOFFSET *a12)
{
  const int *v12; // r15
  __int64 result; // rax
  unsigned int v15; // ebx
  UINT v16; // edi
  UINT v17; // r13d
  LONG y; // esi
  int BkMode; // eax
  int v20; // r13d
  __int64 v21; // rcx
  INT v22; // edx
  DWORD ObjectType; // eax
  HGDIOBJ CurrentObject; // rax
  LONG v25; // eax
  HFONT v26; // rax
  HGDIOBJ v27; // rax
  INT *v28; // rdi
  _DWORD *v29; // rcx
  int v30; // r12d
  int v31; // r15d
  int v32; // r8d
  int v33; // ecx
  int v34; // r8d
  int v35; // eax
  UINT v36; // ecx
  int v37; // eax
  __int64 v38; // rdi
  int v39; // esi
  int v40; // esi
  const WCHAR *lpString; // rdi
  int v42; // ebx
  int v43; // eax
  int v44; // edx
  int *v45; // rbx
  int v46; // ebx
  int v47; // esi
  unsigned int v48; // edi
  HGDIOBJ v49; // rax
  int v50; // ebx
  int v51; // eax
  INT nNumber; // [rsp+44h] [rbp-A5h] BYREF
  int nNumerator[2]; // [rsp+48h] [rbp-A1h] BYREF
  LONG v55; // [rsp+50h] [rbp-99h]
  int v56; // [rsp+54h] [rbp-95h]
  UINT align; // [rsp+58h] [rbp-91h]
  INT *lpDx; // [rsp+60h] [rbp-89h]
  UINT options; // [rsp+68h] [rbp-81h]
  unsigned int v60; // [rsp+6Ch] [rbp-7Dh]
  UINT v61; // [rsp+70h] [rbp-79h]
  struct tagPOINT pt; // [rsp+78h] [rbp-71h] BYREF
  RECT *lprect; // [rsp+80h] [rbp-69h]
  const int *v64; // [rsp+88h] [rbp-61h]
  const unsigned __int16 *v65; // [rsp+90h] [rbp-59h]
  HGDIOBJ h; // [rsp+98h] [rbp-51h]
  LOGFONTA pv; // [rsp+A0h] [rbp-49h] BYREF

  v12 = a11;
  lprect = a7;
  lpDx = a3;
  v65 = a8;
  if ( !a8 || !a10 || !a12 )
    return 2147942487LL;
  nNumber = 0;
  if ( !a11 )
    v12 = a10;
  pt = 0;
  v64 = v12;
  if ( !a9 )
    return 0;
  *(_QWORD *)nNumerator = 0;
  result = GetEscapementVector(a2, (__int64)a2, (struct tagPOINT *)nNumerator);
  v60 = result;
  if ( (int)result >= 0 )
  {
    v15 = a6 & 0xFFFFDFEF | 0x10;
    align = GetTextAlign(a2);
    v16 = align & 1;
    v17 = align;
    v61 = v16;
    if ( (align & 1) != 0 )
    {
      GetCurrentPositionEx(a2, &pt);
      y = pt.y;
      a4 = pt.x;
      v55 = pt.y;
      SetTextAlign(a2, v17 & 0xFFFFFFFE);
    }
    else
    {
      y = a5;
      v55 = a5;
    }
    BkMode = GetBkMode(a2);
    v20 = BkMode;
    if ( (a6 & 2) != 0 || BkMode == 2 || v16 )
    {
      v21 = 0;
      if ( a9 > 0 )
      {
        v22 = nNumber;
        do
        {
          v22 += v12[v21];
          v21 = (unsigned int)(v21 + 1);
        }
        while ( (int)v21 < a9 );
        nNumber = v22;
      }
      if ( (a6 & 2) != 0 || BkMode == 2 )
      {
        ObjectType = GetObjectType(a2);
        ExtTextOutW(
          a2,
          a4,
          y,
          (((ObjectType - 4) & 0xFFFFFFF7) != 0 ? 0x1000 : 0) | a6 & 0xFFFFDFEF,
          lprect,
          L" ",
          1u,
          &nNumber);
        v15 = a6 & 0xFFFFDFED | 0x10;
        if ( v20 == 2 )
          v20 = SetBkMode(a2, 1);
      }
    }
    memset(&pv, 0, sizeof(pv));
    CurrentObject = GetCurrentObject(a2, 6u);
    if ( CurrentObject && GetObjectA(CurrentObject, 60, &pv) )
    {
      v25 = pv.lfEscapement + 900;
      pv.lfEscapement = v25;
      if ( v25 >= 3600 )
      {
        v25 -= 3600;
        pv.lfEscapement = v25;
      }
      pv.lfOrientation = v25;
      v26 = CreateFontIndirectA(&pv);
      v27 = SelectObject(a2, v26);
      v28 = lpDx;
      h = v27;
      v29 = *(_DWORD **)lpDx;
      if ( (align & 0x18) == 0x18 )
      {
        v30 = v29[12];
        v31 = v30 - v29[4];
      }
      else if ( (align & 0x18) != 0 )
      {
        v30 = v29[4];
        v31 = 0;
      }
      else
      {
        v30 = 0;
        v31 = -v29[4];
      }
      v32 = v29[10];
      if ( v32 != v29[8] )
        v31 = MulDiv(v29[8], v31, v32);
      v33 = *(_DWORD *)(*(_QWORD *)v28 + 36LL);
      v34 = *(_DWORD *)(*(_QWORD *)v28 + 44LL);
      if ( v34 != v33 )
        v30 = MulDiv(v33, v30, v34);
      v35 = IsPrintingDC(a2);
      v36 = v15 | 0x10000;
      if ( !v35 )
        v36 = v15;
      v37 = 0;
      options = v36;
      while ( 1 )
      {
        v56 = v37;
        if ( v37 >= a9 )
          break;
        v38 = v37;
        lpDx = (INT *)&v64[v37];
        v39 = y - MulDiv(v31, nNumerator[0], 1000);
        v40 = MulDiv(v30, nNumerator[1], 1000) + v39;
        lpString = &v65[v38];
        v42 = MulDiv(v30, nNumerator[0], 1000);
        v43 = MulDiv(v31, nNumerator[1], 1000);
        v44 = v42 + a4;
        v45 = lpDx;
        if ( !ExtTextOutW(a2, v43 + v44, v40, options, lprect, lpString, 1u, lpDx) )
        {
          v48 = HRESULT_FROM_LAST_WIN32_ERROR();
          goto LABEL_45;
        }
        v46 = MulDiv(*v45, nNumerator[0], 1000);
        a4 += v46 + MulDiv(0, nNumerator[1], 1000);
        v47 = v55 - MulDiv(0, nNumerator[0], 1000);
        y = MulDiv(*lpDx, nNumerator[1], 1000) + v47;
        v37 = v56 + 1;
        v55 = y;
      }
      v48 = v60;
LABEL_45:
      if ( h )
      {
        v49 = SelectObject(a2, h);
        if ( v49 )
          DeleteObject(v49);
      }
      if ( v20 == 2 )
        SetBkMode(a2, 2);
      if ( v61 )
      {
        v50 = MulDiv(nNumber, nNumerator[1], 1000) + v55;
        v51 = MulDiv(nNumber, nNumerator[0], 1000);
        MoveToEx(a2, a4 + v51, v50, 0);
        SetTextAlign(a2, align);
      }
      return v48;
    }
    else
    {
      return HRESULT_FROM_LAST_WIN32_ERROR();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18009d9e4  mov     [rsp-8+arg_0], rbx
0x18009d9e9  push    rbp
0x18009d9ea  push    rsi
0x18009d9eb  push    rdi
0x18009d9ec  push    r12
0x18009d9ee  push    r13
0x18009d9f0  push    r14
0x18009d9f2  push    r15
0x18009d9f4  lea     rbp, [rsp-7]
0x18009d9f9  sub     rsp, 0F0h
0x18009da00  mov     rax, cs:__security_cookie
0x18009da07  xor     rax, rsp
0x18009da0a  mov     [rbp+37h+var_40], rax
0x18009da0e  mov     rcx, [rbp+37h+arg_30]
0x18009da12  xor     ebx, ebx
0x18009da14  mov     r15, [rbp+37h+arg_50]
0x18009da1b  mov     r14, rdx
0x18009da1e  mov     rax, [rbp+37h+arg_48]
0x18009da25  mov     [rbp+37h+var_A0], rcx
0x18009da29  mov     rcx, [rbp+37h+arg_38]
0x18009da2d  mov     [rsp+120h+x], r9d
0x18009da32  mov     [rsp+120h+var_C0], r8
0x18009da37  mov     [rbp+37h+var_90], rcx
0x18009da3b  test    rcx, rcx
0x18009da3e  jz      loc_18009DEEB
0x18009da44  test    rax, rax
0x18009da47  jz      loc_18009DEEB
0x18009da4d  cmp     [rbp+37h+arg_58], rbx
0x18009da54  jz      loc_18009DEEB
0x18009da5a  mov     r12d, [rbp+37h+arg_40]
0x18009da61  test    r15, r15
0x18009da64  mov     [rsp+120h+nNumber], ebx
0x18009da68  cmovz   r15, rax
0x18009da6c  mov     qword ptr [rbp+37h+pt.x], rbx
0x18009da70  mov     [rbp+37h+var_98], r15
0x18009da74  test    r12d, r12d
0x18009da77  jnz     short loc_18009DA80
0x18009da79  xor     eax, eax
0x18009da7b  jmp     loc_18009DEF0
0x18009da80  lea     r8, [rsp+120h+nNumerator]; struct tagPOINT *
0x18009da85  mov     qword ptr [rsp+120h+nNumerator], rbx
0x18009da8a  mov     rcx, r14; hdc
0x18009da8d  call    ?GetEscapementVector@@YAJPEAUHDC__@@HAEAUtagPOINT@@@Z; GetEscapementVector(HDC__ *,int,tagPOINT &)
0x18009da92  mov     [rbp+37h+var_B4], eax
0x18009da95  test    eax, eax
0x18009da97  js      loc_18009DEF0
0x18009da9d  mov     ebx, [rbp+37h+arg_28]
0x18009daa0  mov     rcx, r14; hdc
0x18009daa3  btr     ebx, 0Dh
0x18009daa7  or      ebx, 10h
0x18009daaa  call    GetTextAlign
0x18009daaf  mov     edi, eax
0x18009dab1  mov     [rsp+120h+align], eax
0x18009dab5  and     edi, 1
0x18009dab8  mov     r13d, eax
0x18009dabb  mov     [rbp+37h+var_B0], edi
0x18009dabe  jz      short loc_18009DAF1
0x18009dac0  lea     rdx, [rbp+37h+pt]; lppt
0x18009dac4  mov     rcx, r14; hdc
0x18009dac7  call    GetCurrentPositionEx
0x18009dacc  mov     eax, [rbp+37h+pt.x]
0x18009dacf  mov     edx, r13d
0x18009dad2  mov     esi, [rbp+37h+pt.y]
0x18009dad5  and     edx, 0FFFFFFFEh; align
0x18009dad8  mov     rcx, r14; hdc
0x18009dadb  mov     [rsp+120h+x], eax
0x18009dadf  mov     [rsp+120h+var_D0], esi
0x18009dae3  call    cs:__imp_SetTextAlign
0x18009daea  nop     dword ptr [rax+rax+00h]
0x18009daef  jmp     short loc_18009DAF8
0x18009daf1  mov     esi, [rbp+37h+arg_20]
0x18009daf4  mov     [rsp+120h+var_D0], esi
0x18009daf8  mov     rcx, r14; hdc
0x18009dafb  call    GetBkMode
0x18009db00  mov     r8d, ebx
0x18009db03  mov     r13d, eax
0x18009db06  and     r8d, 2
0x18009db0a  jnz     short loc_18009DB19
0x18009db0c  cmp     eax, 2
0x18009db0f  jz      short loc_18009DB19
0x18009db11  test    edi, edi
0x18009db13  jz      loc_18009DBBC
0x18009db19  xor     ecx, ecx
0x18009db1b  test    r12d, r12d
0x18009db1e  jle     short loc_18009DB33
0x18009db20  mov     edx, [rsp+120h+nNumber]
0x18009db24  add     edx, [r15+rcx*4]
0x18009db28  inc     ecx
0x18009db2a  cmp     ecx, r12d
0x18009db2d  jl      short loc_18009DB24
0x18009db2f  mov     [rsp+120h+nNumber], edx
0x18009db33  test    r8d, r8d
0x18009db36  jnz     short loc_18009DB3E
0x18009db38  cmp     r13d, 2
0x18009db3c  jnz     short loc_18009DBBC
0x18009db3e  mov     rcx, r14; h
0x18009db41  call    GetObjectType
0x18009db46  mov     edx, [rsp+120h+x]; x
0x18009db4a  add     eax, 0FFFFFFFCh
0x18009db4d  and     eax, 0FFFFFFF7h
0x18009db50  mov     r9d, ebx
0x18009db53  and     r9d, 0FFFFFFEFh
0x18009db57  mov     r8d, esi; y
0x18009db5a  neg     eax
0x18009db5c  lea     rax, [rsp+120h+nNumber]
0x18009db61  mov     [rsp+120h+lpDx], rax; lpDx
0x18009db66  sbb     ecx, ecx
0x18009db68  and     ecx, 1000h
0x18009db6e  mov     [rsp+120h+c], 1; c
0x18009db76  lea     rax, String; " "
0x18009db7d  or      r9d, ecx; options
0x18009db80  mov     [rsp+120h+lpString], rax; lpString
0x18009db85  mov     rcx, r14; hdc
0x18009db88  mov     rax, [rbp+37h+var_A0]
0x18009db8c  mov     [rsp+120h+lprect], rax; lprect
0x18009db91  call    cs:__imp_ExtTextOutW
0x18009db98  nop     dword ptr [rax+rax+00h]
0x18009db9d  and     ebx, 0FFFFFFFDh
0x18009dba0  cmp     r13d, 2
0x18009dba4  jnz     short loc_18009DBBC
0x18009dba6  lea     edx, [r13-1]; mode
0x18009dbaa  mov     rcx, r14; hdc
0x18009dbad  call    cs:__imp_SetBkMode
0x18009dbb4  nop     dword ptr [rax+rax+00h]
0x18009dbb9  mov     r13d, eax
0x18009dbbc  xorps   xmm0, xmm0
0x18009dbbf  mov     edx, 6; type
0x18009dbc4  movups  [rbp+37h+var_60], xmm0
0x18009dbc8  mov     rcx, r14; hdc
0x18009dbcb  movups  [rbp+37h+var_60+0Ch], xmm0
0x18009dbcf  movups  [rbp+37h+pv], xmm0
0x18009dbd3  movups  [rbp+37h+var_70], xmm0
0x18009dbd7  call    GetCurrentObject
0x18009dbdc  test    rax, rax
0x18009dbdf  jnz     short loc_18009DBEB
0x18009dbe1  call    HRESULT_FROM_LAST_WIN32_ERROR
0x18009dbe6  jmp     loc_18009DEF0
0x18009dbeb  lea     r8, [rbp+37h+pv]; pv
0x18009dbef  mov     edx, 3Ch ; '<'; c
0x18009dbf4  mov     rcx, rax; h
0x18009dbf7  call    GetObjectA
0x18009dbfc  test    eax, eax
0x18009dbfe  jz      short loc_18009DBE1
0x18009dc00  mov     eax, dword ptr [rbp+37h+pv+8]
0x18009dc03  add     eax, 384h
0x18009dc08  mov     dword ptr [rbp+37h+pv+8], eax
0x18009dc0b  cmp     eax, 0E10h
0x18009dc10  jl      short loc_18009DC1A
0x18009dc12  add     eax, 0FFFFF1F0h
0x18009dc17  mov     dword ptr [rbp+37h+pv+8], eax
0x18009dc1a  lea     rcx, [rbp+37h+pv]; lplf
0x18009dc1e  mov     dword ptr [rbp+37h+pv+0Ch], eax
0x18009dc21  call    CreateFontIndirectA
0x18009dc26  mov     rdx, rax; h
0x18009dc29  mov     rcx, r14; hdc
0x18009dc2c  call    cs:__imp_SelectObject
0x18009dc33  nop     dword ptr [rax+rax+00h]
0x18009dc38  mov     edx, [rsp+120h+align]
0x18009dc3c  mov     rdi, [rsp+120h+var_C0]
0x18009dc41  and     edx, 18h
0x18009dc44  mov     [rbp+37h+h], rax
0x18009dc48  mov     rcx, [rdi]
0x18009dc4b  cmp     edx, 18h
0x18009dc4e  jnz     short loc_18009DC5D
0x18009dc50  mov     r12d, [rcx+30h]
0x18009dc54  mov     r15d, r12d
0x18009dc57  sub     r15d, [rcx+10h]
0x18009dc5b  jmp     short loc_18009DC73
0x18009dc5d  mov     r15d, [rcx+10h]
0x18009dc61  test    edx, edx
0x18009dc63  jnz     short loc_18009DC6D
0x18009dc65  xor     r12d, r12d
0x18009dc68  neg     r15d
0x18009dc6b  jmp     short loc_18009DC73
0x18009dc6d  mov     r12d, r15d
0x18009dc70  xor     r15d, r15d
0x18009dc73  mov     r8d, [rcx+28h]; nDenominator
0x18009dc77  cmp     r8d, [rcx+20h]
0x18009dc7b  jz      short loc_18009DC92
0x18009dc7d  mov     ecx, [rcx+20h]; nNumber
0x18009dc80  mov     edx, r15d; nNumerator
0x18009dc83  call    cs:__imp_MulDiv
0x18009dc8a  nop     dword ptr [rax+rax+00h]
0x18009dc8f  mov     r15d, eax
0x18009dc92  mov     rax, [rdi]
0x18009dc95  mov     ecx, [rax+24h]; nNumber
0x18009dc98  mov     r8d, [rax+2Ch]; nDenominator
0x18009dc9c  cmp     r8d, ecx
0x18009dc9f  jz      short loc_18009DCB3
0x18009dca1  mov     edx, r12d; nNumerator
0x18009dca4  call    cs:__imp_MulDiv
0x18009dcab  nop     dword ptr [rax+rax+00h]
0x18009dcb0  mov     r12d, eax
0x18009dcb3  mov     rcx, r14; HDC
0x18009dcb6  call    ?IsPrintingDC@@YAHPEAUHDC__@@@Z; IsPrintingDC(HDC__ *)
0x18009dcbb  mov     ecx, ebx
0x18009dcbd  bts     ecx, 10h
0x18009dcc1  test    eax, eax
0x18009dcc3  cmovz   ecx, ebx
0x18009dcc6  xor     eax, eax
0x18009dcc8  mov     [rsp+120h+options], ecx
0x18009dccc  mov     [rsp+120h+var_CC], eax
0x18009dcd0  cmp     eax, [rbp+37h+arg_40]
0x18009dcd6  jge     loc_18009DE2F
0x18009dcdc  mov     edx, [rsp+120h+nNumerator]; nNumerator
0x18009dce0  mov     r8d, 3E8h; nDenominator
0x18009dce6  movsxd  rdi, eax
0x18009dce9  mov     ecx, r15d; nNumber
0x18009dcec  mov     rax, [rbp+37h+var_98]
0x18009dcf0  lea     rax, [rax+rdi*4]
0x18009dcf4  mov     [rsp+120h+var_C0], rax
0x18009dcf9  call    cs:__imp_MulDiv
0x18009dd00  nop     dword ptr [rax+rax+00h]
0x18009dd05  mov     edx, [rsp+120h+nNumerator+4]; nNumerator
0x18009dd09  mov     r8d, 3E8h; nDenominator
0x18009dd0f  mov     ecx, r12d; nNumber
0x18009dd12  sub     esi, eax
0x18009dd14  call    cs:__imp_MulDiv
0x18009dd1b  nop     dword ptr [rax+rax+00h]
0x18009dd20  mov     edx, [rsp+120h+nNumerator]; nNumerator
0x18009dd24  mov     r8d, 3E8h; nDenominator
0x18009dd2a  add     esi, eax
0x18009dd2c  mov     ecx, r12d; nNumber
0x18009dd2f  mov     rax, [rbp+37h+var_90]
0x18009dd33  lea     rdi, [rax+rdi*2]
0x18009dd37  call    cs:__imp_MulDiv
0x18009dd3e  nop     dword ptr [rax+rax+00h]
0x18009dd43  mov     edx, [rsp+120h+nNumerator+4]; nNumerator
0x18009dd47  mov     r8d, 3E8h; nDenominator
0x18009dd4d  mov     ecx, r15d; nNumber
0x18009dd50  mov     ebx, eax
0x18009dd52  call    cs:__imp_MulDiv
0x18009dd59  nop     dword ptr [rax+rax+00h]
0x18009dd5e  mov     edx, [rsp+120h+x]
0x18009dd62  mov     r8d, esi; y
0x18009dd65  mov     rcx, [rbp+37h+var_A0]
0x18009dd69  add     edx, ebx
0x18009dd6b  mov     rbx, [rsp+120h+var_C0]
0x18009dd70  add     edx, eax; x
0x18009dd72  mov     r9d, [rsp+120h+options]; options
0x18009dd77  mov     [rsp+120h+lpDx], rbx; lpDx
0x18009dd7c  mov     [rsp+120h+c], 1; c
0x18009dd84  mov     [rsp+120h+lpString], rdi; lpString
0x18009dd89  mov     [rsp+120h+lprect], rcx; lprect
0x18009dd8e  mov     rcx, r14; hdc
0x18009dd91  call    cs:__imp_ExtTextOutW
0x18009dd98  nop     dword ptr [rax+rax+00h]
0x18009dd9d  test    eax, eax
0x18009dd9f  jz      loc_18009DE26
0x18009dda5  mov     edx, [rsp+120h+nNumerator]; nNumerator
0x18009dda9  mov     edi, 3E8h
0x18009ddae  mov     ecx, [rbx]; nNumber
0x18009ddb0  mov     r8d, edi; nDenominator
0x18009ddb3  call    cs:__imp_MulDiv
0x18009ddba  nop     dword ptr [rax+rax+00h]
0x18009ddbf  mov     edx, [rsp+120h+nNumerator+4]; nNumerator
0x18009ddc3  mov     r8d, edi; nDenominator
0x18009ddc6  xor     ecx, ecx; nNumber
0x18009ddc8  mov     ebx, eax
0x18009ddca  call    cs:__imp_MulDiv
0x18009ddd1  nop     dword ptr [rax+rax+00h]
0x18009ddd6  mov     edx, [rsp+120h+nNumerator]; nNumerator
0x18009ddda  mov     r8d, edi; nDenominator
0x18009dddd  add     eax, [rsp+120h+x]
0x18009dde1  xor     ecx, ecx; nNumber
0x18009dde3  add     eax, ebx
0x18009dde5  mov     [rsp+120h+x], eax
0x18009dde9  call    cs:__imp_MulDiv
0x18009ddf0  nop     dword ptr [rax+rax+00h]
0x18009ddf5  mov     rcx, [rsp+120h+var_C0]
0x18009ddfa  mov     r8d, edi; nDenominator
0x18009ddfd  mov     esi, [rsp+120h+var_D0]
0x18009de01  mov     edx, [rsp+120h+nNumerator+4]; nNumerator
0x18009de05  sub     esi, eax
0x18009de07  mov     ecx, [rcx]; nNumber
0x18009de09  call    cs:__imp_MulDiv
0x18009de10  nop     dword ptr [rax+rax+00h]
0x18009de15  add     esi, eax
0x18009de17  mov     eax, [rsp+120h+var_CC]
0x18009de1b  inc     eax
0x18009de1d  mov     [rsp+120h+var_D0], esi
0x18009de21  jmp     loc_18009DCCC
0x18009de26  call    HRESULT_FROM_LAST_WIN32_ERROR
0x18009de2b  mov     edi, eax
0x18009de2d  jmp     short loc_18009DE32
0x18009de2f  mov     edi, [rbp+37h+var_B4]
0x18009de32  mov     rax, [rbp+37h+h]
0x18009de36  test    rax, rax
0x18009de39  jz      short loc_18009DE61
0x18009de3b  mov     rdx, rax; h
0x18009de3e  mov     rcx, r14; hdc
0x18009de41  call    cs:__imp_SelectObject
0x18009de48  nop     dword ptr [rax+rax+00h]
0x18009de4d  test    rax, rax
0x18009de50  jz      short loc_18009DE61
0x18009de52  mov     rcx, rax; ho
0x18009de55  call    cs:__imp_DeleteObject
0x18009de5c  nop     dword ptr [rax+rax+00h]
0x18009de61  cmp     r13d, 2
0x18009de65  jnz     short loc_18009DE79
  ... truncated ...
```
