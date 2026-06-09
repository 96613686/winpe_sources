# CUspShapingDrawingSurface::VerticalFETextOut(HDC__ *,void * *,long,long,uint,tagRECT const *,ushort const *,long,long const *,long const *,tagGOFFSET const *)

- ea: `0x18009ac00`
- end: `0x18009b0ab`
- name: `?VerticalFETextOut@CUspShapingDrawingSurface@@AEAAJPEAUHDC__@@PEAPEAXJJIPEBUtagRECT@@PEBGJPEBJ4PEBUtagGOFFSET@@@Z`
- size: `1195`
- prototype: `int(CUspShapingDrawingSurface *__hidden this, HDC, void **, int, int, unsigned int, const struct tagRECT *, const unsigned __int16 *, int, const int *, const int *, const struct tagGOFFSET *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18000c740`

## callees

- `0x18000d620`
- `0x18000d650`
- `0x18000e5a0`
- `0x180010e60`
- `0x180014240`
- `0x180015700`
- `0x180015970`
- `0x180016900`
- `0x180025fb0`
- `0x18003ed14`
- `0x18007ac50`
- `0x18009ac00`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009ae87`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009aea2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009aef1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af06`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af23`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af38`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af89`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af9a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009afb3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009afcd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009b039`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009b053`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009ae87`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009aea2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009aef1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af06`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af23`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af38`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af89`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009af9a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009afb3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009afcd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009b039`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18009b053`
- `GDI32!ExtTextOutW` at `0x18009ada7`
- `GDI32!ExtTextOutW` at `0x18009af71`
- `GDI32!ExtTextOutW` at `0x18009ada7`
- `GDI32!ExtTextOutW` at `0x18009af71`
- `GDI32!MoveToEx` at `0x18009b068`
- `GDI32!MoveToEx` at `0x18009b068`
- `GDI32!SelectObject` at `0x18009ae36`
- `GDI32!SelectObject` at `0x18009afff`
- `GDI32!SelectObject` at `0x18009ae36`
- `GDI32!SelectObject` at `0x18009afff`
- `GDI32!SetBkMode` at `0x18009adbd`
- `GDI32!SetBkMode` at `0x18009b01f`
- `GDI32!SetBkMode` at `0x18009adbd`
- `GDI32!SetBkMode` at `0x18009b01f`
- `GDI32!SetTextAlign` at `0x18009acff`
- `GDI32!SetTextAlign` at `0x18009b075`
- `GDI32!SetTextAlign` at `0x18009acff`
- `GDI32!SetTextAlign` at `0x18009b075`
- `GDI32!DeleteObject` at `0x18009b00d`
- `GDI32!DeleteObject` at `0x18009b00d`

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
0x18009ac00  mov     [rsp-8+arg_0], rbx
0x18009ac05  push    rbp
0x18009ac06  push    rsi
0x18009ac07  push    rdi
0x18009ac08  push    r12
0x18009ac0a  push    r13
0x18009ac0c  push    r14
0x18009ac0e  push    r15
0x18009ac10  lea     rbp, [rsp-7]
0x18009ac15  sub     rsp, 0F0h
0x18009ac1c  mov     rax, cs:__security_cookie
0x18009ac23  xor     rax, rsp
0x18009ac26  mov     [rbp+37h+var_40], rax
0x18009ac2a  mov     rcx, [rbp+37h+arg_30]
0x18009ac2e  xor     ebx, ebx
0x18009ac30  mov     r15, [rbp+37h+arg_50]
0x18009ac37  mov     r14, rdx
0x18009ac3a  mov     rax, [rbp+37h+arg_48]
0x18009ac41  mov     [rbp+37h+var_A0], rcx
0x18009ac45  mov     rcx, [rbp+37h+arg_38]
0x18009ac49  mov     [rsp+120h+x], r9d
0x18009ac4e  mov     [rsp+120h+var_C0], r8
0x18009ac53  mov     [rbp+37h+var_90], rcx
0x18009ac57  test    rcx, rcx
0x18009ac5a  jz      loc_18009B07F
0x18009ac60  test    rax, rax
0x18009ac63  jz      loc_18009B07F
0x18009ac69  cmp     [rbp+37h+arg_58], rbx
0x18009ac70  jz      loc_18009B07F
0x18009ac76  mov     r12d, [rbp+37h+arg_40]
0x18009ac7d  test    r15, r15
0x18009ac80  mov     [rsp+120h+nNumber], ebx
0x18009ac84  cmovz   r15, rax
0x18009ac88  mov     qword ptr [rbp+37h+pt.x], rbx
0x18009ac8c  mov     [rbp+37h+var_98], r15
0x18009ac90  test    r12d, r12d
0x18009ac93  jnz     short loc_18009AC9C
0x18009ac95  xor     eax, eax
0x18009ac97  jmp     loc_18009B084
0x18009ac9c  lea     r8, [rsp+120h+nNumerator]; struct tagPOINT *
0x18009aca1  mov     qword ptr [rsp+120h+nNumerator], rbx
0x18009aca6  mov     rcx, r14; hdc
0x18009aca9  call    ?GetEscapementVector@@YAJPEAUHDC__@@HAEAUtagPOINT@@@Z; GetEscapementVector(HDC__ *,int,tagPOINT &)
0x18009acae  mov     [rbp+37h+var_B4], eax
0x18009acb1  test    eax, eax
0x18009acb3  js      loc_18009B084
0x18009acb9  mov     ebx, [rbp+37h+arg_28]
0x18009acbc  mov     rcx, r14; hdc
0x18009acbf  btr     ebx, 0Dh
0x18009acc3  or      ebx, 10h
0x18009acc6  call    GetTextAlign
0x18009accb  mov     edi, eax
0x18009accd  mov     [rsp+120h+align], eax
0x18009acd1  and     edi, 1
0x18009acd4  mov     r13d, eax
0x18009acd7  mov     [rbp+37h+var_B0], edi
0x18009acda  jz      short loc_18009AD07
0x18009acdc  lea     rdx, [rbp+37h+pt]; lppt
0x18009ace0  mov     rcx, r14; hdc
0x18009ace3  call    GetCurrentPositionEx
0x18009ace8  mov     eax, [rbp+37h+pt.x]
0x18009aceb  mov     edx, r13d
0x18009acee  mov     esi, [rbp+37h+pt.y]
0x18009acf1  and     edx, 0FFFFFFFEh; align
0x18009acf4  mov     rcx, r14; hdc
0x18009acf7  mov     [rsp+120h+x], eax
0x18009acfb  mov     [rsp+120h+var_D0], esi
0x18009acff  call    cs:__imp_SetTextAlign
0x18009ad05  jmp     short loc_18009AD0E
0x18009ad07  mov     esi, [rbp+37h+arg_20]
0x18009ad0a  mov     [rsp+120h+var_D0], esi
0x18009ad0e  mov     rcx, r14; hdc
0x18009ad11  call    GetBkMode
0x18009ad16  mov     r8d, ebx
0x18009ad19  mov     r13d, eax
0x18009ad1c  and     r8d, 2
0x18009ad20  jnz     short loc_18009AD2F
0x18009ad22  cmp     eax, 2
0x18009ad25  jz      short loc_18009AD2F
0x18009ad27  test    edi, edi
0x18009ad29  jz      loc_18009ADC6
0x18009ad2f  xor     ecx, ecx
0x18009ad31  test    r12d, r12d
0x18009ad34  jle     short loc_18009AD49
0x18009ad36  mov     edx, [rsp+120h+nNumber]
0x18009ad3a  add     edx, [r15+rcx*4]
0x18009ad3e  inc     ecx
0x18009ad40  cmp     ecx, r12d
0x18009ad43  jl      short loc_18009AD3A
0x18009ad45  mov     [rsp+120h+nNumber], edx
0x18009ad49  test    r8d, r8d
0x18009ad4c  jnz     short loc_18009AD54
0x18009ad4e  cmp     r13d, 2
0x18009ad52  jnz     short loc_18009ADC6
0x18009ad54  mov     rcx, r14; h
0x18009ad57  call    GetObjectType
0x18009ad5c  mov     edx, [rsp+120h+x]; x
0x18009ad60  add     eax, 0FFFFFFFCh
0x18009ad63  and     eax, 0FFFFFFF7h
0x18009ad66  mov     r9d, ebx
0x18009ad69  and     r9d, 0FFFFFFEFh
0x18009ad6d  mov     r8d, esi; y
0x18009ad70  neg     eax
0x18009ad72  lea     rax, [rsp+120h+nNumber]
0x18009ad77  mov     [rsp+120h+lpDx], rax; lpDx
0x18009ad7c  sbb     ecx, ecx
0x18009ad7e  and     ecx, 1000h
0x18009ad84  mov     [rsp+120h+c], 1; c
0x18009ad8c  lea     rax, String; " "
0x18009ad93  or      r9d, ecx; options
0x18009ad96  mov     [rsp+120h+lpString], rax; lpString
0x18009ad9b  mov     rcx, r14; hdc
0x18009ad9e  mov     rax, [rbp+37h+var_A0]
0x18009ada2  mov     [rsp+120h+lprect], rax; lprect
0x18009ada7  call    cs:__imp_ExtTextOutW
0x18009adad  and     ebx, 0FFFFFFFDh
0x18009adb0  cmp     r13d, 2
0x18009adb4  jnz     short loc_18009ADC6
0x18009adb6  lea     edx, [r13-1]; mode
0x18009adba  mov     rcx, r14; hdc
0x18009adbd  call    cs:__imp_SetBkMode
0x18009adc3  mov     r13d, eax
0x18009adc6  xorps   xmm0, xmm0
0x18009adc9  mov     edx, 6; type
0x18009adce  movups  [rbp+37h+var_60], xmm0
0x18009add2  mov     rcx, r14; hdc
0x18009add5  movups  [rbp+37h+var_60+0Ch], xmm0
0x18009add9  movups  [rbp+37h+pv], xmm0
0x18009addd  movups  [rbp+37h+var_70], xmm0
0x18009ade1  call    GetCurrentObject
0x18009ade6  test    rax, rax
0x18009ade9  jnz     short loc_18009ADF5
0x18009adeb  call    HRESULT_FROM_LAST_WIN32_ERROR
0x18009adf0  jmp     loc_18009B084
0x18009adf5  lea     r8, [rbp+37h+pv]; pv
0x18009adf9  mov     edx, 3Ch ; '<'; c
0x18009adfe  mov     rcx, rax; h
0x18009ae01  call    GetObjectA
0x18009ae06  test    eax, eax
0x18009ae08  jz      short loc_18009ADEB
0x18009ae0a  mov     eax, dword ptr [rbp+37h+pv+8]
0x18009ae0d  add     eax, 384h
0x18009ae12  mov     dword ptr [rbp+37h+pv+8], eax
0x18009ae15  cmp     eax, 0E10h
0x18009ae1a  jl      short loc_18009AE24
0x18009ae1c  add     eax, 0FFFFF1F0h
0x18009ae21  mov     dword ptr [rbp+37h+pv+8], eax
0x18009ae24  lea     rcx, [rbp+37h+pv]; lplf
0x18009ae28  mov     dword ptr [rbp+37h+pv+0Ch], eax
0x18009ae2b  call    CreateFontIndirectA
0x18009ae30  mov     rdx, rax; h
0x18009ae33  mov     rcx, r14; hdc
0x18009ae36  call    cs:__imp_SelectObject
0x18009ae3c  mov     edx, [rsp+120h+align]
0x18009ae40  mov     rdi, [rsp+120h+var_C0]
0x18009ae45  and     edx, 18h
0x18009ae48  mov     [rbp+37h+h], rax
0x18009ae4c  mov     rcx, [rdi]
0x18009ae4f  cmp     edx, 18h
0x18009ae52  jnz     short loc_18009AE61
0x18009ae54  mov     r12d, [rcx+30h]
0x18009ae58  mov     r15d, r12d
0x18009ae5b  sub     r15d, [rcx+10h]
0x18009ae5f  jmp     short loc_18009AE77
0x18009ae61  mov     r15d, [rcx+10h]
0x18009ae65  test    edx, edx
0x18009ae67  jnz     short loc_18009AE71
0x18009ae69  xor     r12d, r12d
0x18009ae6c  neg     r15d
0x18009ae6f  jmp     short loc_18009AE77
0x18009ae71  mov     r12d, r15d
0x18009ae74  xor     r15d, r15d
0x18009ae77  mov     r8d, [rcx+28h]; nDenominator
0x18009ae7b  cmp     r8d, [rcx+20h]
0x18009ae7f  jz      short loc_18009AE90
0x18009ae81  mov     ecx, [rcx+20h]; nNumber
0x18009ae84  mov     edx, r15d; nNumerator
0x18009ae87  call    cs:__imp_MulDiv
0x18009ae8d  mov     r15d, eax
0x18009ae90  mov     rax, [rdi]
0x18009ae93  mov     ecx, [rax+24h]; nNumber
0x18009ae96  mov     r8d, [rax+2Ch]; nDenominator
0x18009ae9a  cmp     r8d, ecx
0x18009ae9d  jz      short loc_18009AEAB
0x18009ae9f  mov     edx, r12d; nNumerator
0x18009aea2  call    cs:__imp_MulDiv
0x18009aea8  mov     r12d, eax
0x18009aeab  mov     rcx, r14; HDC
0x18009aeae  call    ?IsPrintingDC@@YAHPEAUHDC__@@@Z; IsPrintingDC(HDC__ *)
0x18009aeb3  mov     ecx, ebx
0x18009aeb5  bts     ecx, 10h
0x18009aeb9  test    eax, eax
0x18009aebb  cmovz   ecx, ebx
0x18009aebe  xor     eax, eax
0x18009aec0  mov     [rsp+120h+options], ecx
0x18009aec4  mov     [rsp+120h+var_CC], eax
0x18009aec8  cmp     eax, [rbp+37h+arg_40]
0x18009aece  jge     loc_18009AFED
0x18009aed4  mov     edx, [rsp+120h+nNumerator]; nNumerator
0x18009aed8  mov     r8d, 3E8h; nDenominator
0x18009aede  movsxd  rdi, eax
0x18009aee1  mov     ecx, r15d; nNumber
0x18009aee4  mov     rax, [rbp+37h+var_98]
0x18009aee8  lea     rax, [rax+rdi*4]
0x18009aeec  mov     [rsp+120h+var_C0], rax
0x18009aef1  call    cs:__imp_MulDiv
0x18009aef7  mov     edx, [rsp+120h+nNumerator+4]; nNumerator
0x18009aefb  mov     r8d, 3E8h; nDenominator
0x18009af01  mov     ecx, r12d; nNumber
0x18009af04  sub     esi, eax
0x18009af06  call    cs:__imp_MulDiv
0x18009af0c  mov     edx, [rsp+120h+nNumerator]; nNumerator
0x18009af10  mov     r8d, 3E8h; nDenominator
0x18009af16  add     esi, eax
0x18009af18  mov     ecx, r12d; nNumber
0x18009af1b  mov     rax, [rbp+37h+var_90]
0x18009af1f  lea     rdi, [rax+rdi*2]
0x18009af23  call    cs:__imp_MulDiv
0x18009af29  mov     edx, [rsp+120h+nNumerator+4]; nNumerator
0x18009af2d  mov     r8d, 3E8h; nDenominator
0x18009af33  mov     ecx, r15d; nNumber
0x18009af36  mov     ebx, eax
0x18009af38  call    cs:__imp_MulDiv
0x18009af3e  mov     edx, [rsp+120h+x]
0x18009af42  mov     r8d, esi; y
0x18009af45  mov     rcx, [rbp+37h+var_A0]
0x18009af49  add     edx, ebx
0x18009af4b  mov     rbx, [rsp+120h+var_C0]
0x18009af50  add     edx, eax; x
0x18009af52  mov     r9d, [rsp+120h+options]; options
0x18009af57  mov     [rsp+120h+lpDx], rbx; lpDx
0x18009af5c  mov     [rsp+120h+c], 1; c
0x18009af64  mov     [rsp+120h+lpString], rdi; lpString
0x18009af69  mov     [rsp+120h+lprect], rcx; lprect
0x18009af6e  mov     rcx, r14; hdc
0x18009af71  call    cs:__imp_ExtTextOutW
0x18009af77  test    eax, eax
0x18009af79  jz      short loc_18009AFE4
0x18009af7b  mov     edx, [rsp+120h+nNumerator]; nNumerator
0x18009af7f  mov     edi, 3E8h
0x18009af84  mov     ecx, [rbx]; nNumber
0x18009af86  mov     r8d, edi; nDenominator
0x18009af89  call    cs:__imp_MulDiv
0x18009af8f  mov     edx, [rsp+120h+nNumerator+4]; nNumerator
0x18009af93  mov     r8d, edi; nDenominator
0x18009af96  xor     ecx, ecx; nNumber
0x18009af98  mov     ebx, eax
0x18009af9a  call    cs:__imp_MulDiv
0x18009afa0  mov     edx, [rsp+120h+nNumerator]; nNumerator
0x18009afa4  mov     r8d, edi; nDenominator
0x18009afa7  add     eax, [rsp+120h+x]
0x18009afab  xor     ecx, ecx; nNumber
0x18009afad  add     eax, ebx
0x18009afaf  mov     [rsp+120h+x], eax
0x18009afb3  call    cs:__imp_MulDiv
0x18009afb9  mov     rcx, [rsp+120h+var_C0]
0x18009afbe  mov     r8d, edi; nDenominator
0x18009afc1  mov     esi, [rsp+120h+var_D0]
0x18009afc5  mov     edx, [rsp+120h+nNumerator+4]; nNumerator
0x18009afc9  sub     esi, eax
0x18009afcb  mov     ecx, [rcx]; nNumber
0x18009afcd  call    cs:__imp_MulDiv
0x18009afd3  add     esi, eax
0x18009afd5  mov     eax, [rsp+120h+var_CC]
0x18009afd9  inc     eax
0x18009afdb  mov     [rsp+120h+var_D0], esi
0x18009afdf  jmp     loc_18009AEC4
0x18009afe4  call    HRESULT_FROM_LAST_WIN32_ERROR
0x18009afe9  mov     edi, eax
0x18009afeb  jmp     short loc_18009AFF0
0x18009afed  mov     edi, [rbp+37h+var_B4]
0x18009aff0  mov     rax, [rbp+37h+h]
0x18009aff4  test    rax, rax
0x18009aff7  jz      short loc_18009B013
0x18009aff9  mov     rdx, rax; h
0x18009affc  mov     rcx, r14; hdc
0x18009afff  call    cs:__imp_SelectObject
0x18009b005  test    rax, rax
0x18009b008  jz      short loc_18009B013
0x18009b00a  mov     rcx, rax; ho
0x18009b00d  call    cs:__imp_DeleteObject
0x18009b013  cmp     r13d, 2
0x18009b017  jnz     short loc_18009B025
0x18009b019  mov     edx, r13d; mode
0x18009b01c  mov     rcx, r14; hdc
0x18009b01f  call    cs:__imp_SetBkMode
0x18009b025  cmp     [rbp+37h+var_B0], 0
0x18009b029  jz      short loc_18009B07B
0x18009b02b  mov     edx, [rsp+120h+nNumerator+4]; nNumerator
0x18009b02f  mov     r8d, 3E8h; nDenominator
0x18009b035  mov     ecx, [rsp+120h+nNumber]; nNumber
0x18009b039  call    cs:__imp_MulDiv
0x18009b03f  mov     ebx, [rsp+120h+var_D0]
0x18009b043  mov     r8d, 3E8h; nDenominator
0x18009b049  mov     edx, [rsp+120h+nNumerator]; nNumerator
0x18009b04d  add     ebx, eax
0x18009b04f  mov     ecx, [rsp+120h+nNumber]; nNumber
0x18009b053  call    cs:__imp_MulDiv
0x18009b059  add     eax, [rsp+120h+x]
0x18009b05d  xor     r9d, r9d; lppt
  ... truncated ...
```
