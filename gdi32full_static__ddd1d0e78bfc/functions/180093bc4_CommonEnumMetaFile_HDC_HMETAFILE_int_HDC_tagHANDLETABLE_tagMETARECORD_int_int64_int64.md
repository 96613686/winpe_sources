# CommonEnumMetaFile(HDC__ *,HMETAFILE__ *,int (*)(HDC__ *,tagHANDLETABLE *,tagMETARECORD *,int,__int64),__int64)

- ea: `0x180093bc4`
- end: `0x180094207`
- name: `?CommonEnumMetaFile@@YAHPEAUHDC__@@PEAUHMETAFILE__@@P6AH0PEAUtagHANDLETABLE@@PEAUtagMETARECORD@@H_J@Z4@Z`
- size: `1603`
- prototype: `__int64 __fastcall(HDC hdc, HMETAFILE, int (*)(HDC, struct tagHANDLETABLE *, struct tagMETARECORD *, int, __int64), __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18007e1d0`
- `0x180094640`

## callees

- `0x180006a28`
- `0x180018720`
- `0x180018940`
- `0x180018df0`
- `0x1800190c0`
- `0x180019310`
- `0x18001efe0`
- `0x18002ade0`
- `0x18002e040`
- `0x18002e130`
- `0x180032f20`
- `0x180047380`
- `0x1800479b0`
- `0x180055b20`
- `0x1800756cc`
- `0x180093bc4`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093d87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180093d87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800941f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800941f3`
- `GDI32!CreateRectRgn` at `0x180093e1d`
- `GDI32!CreateRectRgn` at `0x180093e1d`
- `GDI32!SelectClipRgn` at `0x180094131`
- `GDI32!SelectClipRgn` at `0x180094146`
- `GDI32!SelectClipRgn` at `0x180094131`
- `GDI32!SelectClipRgn` at `0x180094146`
- `GDI32!SelectObject` at `0x180093fef`
- `GDI32!SelectObject` at `0x18009400e`
- `GDI32!SelectObject` at `0x180094022`
- `GDI32!SelectObject` at `0x180094041`
- `GDI32!SelectObject` at `0x18009409c`
- `GDI32!SelectObject` at `0x1800940ec`
- `GDI32!SelectObject` at `0x1800941a4`
- `GDI32!SelectObject` at `0x180093fef`
- `GDI32!SelectObject` at `0x18009400e`
- `GDI32!SelectObject` at `0x180094022`
- `GDI32!SelectObject` at `0x180094041`
- `GDI32!SelectObject` at `0x18009409c`
- `GDI32!SelectObject` at `0x1800940ec`
- `GDI32!SelectObject` at `0x1800941a4`
- `GDI32!GdiGetEntry` at `0x180093c80`
- `GDI32!GdiGetEntry` at `0x180093c80`
- `GDI32!gW32PID` at `0x180093cc9`
- `GDI32!gCookie` at `0x180093ce1`
- `GDI32!gMaxGdiHandleCount` at `0x180093c52`
- `GDI32!pldcGet` at `0x180093d18`
- `GDI32!pldcGet` at `0x180093d18`
- `GDI32!GdiSetLastError` at `0x180093d49`
- `GDI32!GdiSetLastError` at `0x180093e8f`
- `GDI32!GdiSetLastError` at `0x180093d49`
- `GDI32!GdiSetLastError` at `0x180093e8f`
- `GDI32!DeleteObject` at `0x180093e5b`
- `GDI32!DeleteObject` at `0x180094171`
- `GDI32!DeleteObject` at `0x1800941e2`
- `GDI32!DeleteObject` at `0x180093e5b`
- `GDI32!DeleteObject` at `0x180094171`
- `GDI32!DeleteObject` at `0x1800941e2`

## pseudocode

```c
__int64 __fastcall CommonEnumMetaFile(
        HDC hdc,
        HMETAFILE a2,
        int (*a3)(HDC, struct tagHANDLETABLE *, struct tagMETARECORD *, int, __int64),
        __int64 a4)
{
  HDC v5; // rbx
  unsigned int v6; // r15d
  int v8; // r12d
  unsigned int v9; // eax
  __int64 v10; // rsi
  __int64 v11; // rdx
  int Entry; // eax
  __int64 v13; // rax
  __int64 v14; // r14
  int v15; // eax
  HRGN RectRgn; // rax
  HRGN v17; // r13
  int ClipRgn; // eax
  __int64 v19; // rcx
  __int64 Event; // rax
  unsigned int (__fastcall *v21)(HDC, _QWORD); // rax
  __int64 v22; // rax
  struct tagMETARECORD *v23; // r14
  HGDIOBJ StockObject; // rax
  HGDIOBJ v25; // rax
  HPALETTE v26; // rax
  unsigned int v27; // r14d
  HGDIOBJ v28; // rax
  __int64 v29; // r14
  HGDIOBJ v30; // rcx
  int v31; // eax
  int iMode; // [rsp+30h] [rbp-B8h]
  int v33; // [rsp+34h] [rbp-B4h]
  __int64 v34; // [rsp+38h] [rbp-B0h]
  struct tagHANDLETABLE *lpHandleTable; // [rsp+40h] [rbp-A8h]
  __int64 v36; // [rsp+48h] [rbp-A0h]
  struct tagSIZE size; // [rsp+50h] [rbp-98h] BYREF
  struct tagSIZE v38; // [rsp+58h] [rbp-90h] BYREF
  __int64 v39; // [rsp+60h] [rbp-88h]
  HGDIOBJ v40; // [rsp+68h] [rbp-80h]
  HGDIOBJ h; // [rsp+70h] [rbp-78h]
  HGDIOBJ DCObject; // [rsp+78h] [rbp-70h]
  HPALETTE hPal; // [rsp+80h] [rbp-68h]
  __int64 v44; // [rsp+88h] [rbp-60h]
  __int64 v45; // [rsp+90h] [rbp-58h]
  __int128 v46; // [rsp+98h] [rbp-50h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-40h]
  int v48; // [rsp+B0h] [rbp-38h]

  v5 = hdc;
  v6 = 0;
  size = 0;
  v38 = 0;
  if ( gbDisableMetaFiles )
    return 1;
  if ( ((unsigned int)hdc & 0x7F0000) == 0x660000 || !hdc && a3 )
  {
    v8 = 1;
  }
  else
  {
    v8 = 0;
    if ( ((((unsigned int)hdc & 0x7F0000) - 0x10000) & 0xFFDFFFFF) != 0 )
      return 0;
  }
  v9 = HANDLE_TO_INDEX();
  v10 = 0;
  v44 = 0;
  v11 = 0;
  if ( v9 < gMaxGdiHandleCount )
  {
    v46 = 0;
    v47 = 0;
    Entry = GdiGetEntry(v9, &v46);
    v11 = 0;
    if ( Entry >= 0 && BYTE14(v46) == 1 && WORD6(v46) == WORD1(v5) && (DWORD2(v46) & 0xFFFFFFFE) == gW32PID && v47 )
    {
      v10 = gCookie ^ __ROR8__(v47, 64 - (gCookie & 0x3Fu));
      v44 = v10;
      v11 = v10;
    }
  }
  if ( !v8 && !v11 )
    return 0;
  v45 = pldcGet(v5);
  v13 = pvClientObjGet(a2, 2490368);
  v14 = v13;
  v36 = v13;
  if ( !v13 )
  {
    GdiSetLastError(6);
    return 0;
  }
  v34 = *(unsigned __int16 *)(v13 + 14);
  lpHandleTable = (struct tagHANDLETABLE *)LocalAlloc(0x40u, 8 * v34 + 2);
  if ( !lpHandleTable )
    return 0;
  if ( v8 )
  {
    v40 = 0;
    hPal = 0;
    h = 0;
    v17 = 0;
    iMode = 0;
    v33 = 0;
    DCObject = 0;
    v39 = -1;
LABEL_29:
    v19 = v14;
    v6 = 1;
    if ( a3 )
    {
      while ( 1 )
      {
        Event = GetEvent(v19);
        if ( !Event )
          break;
        if ( Event == -1 || !v8 && (*(_DWORD *)(v10 + 152) & 0x800) == 0 )
          goto LABEL_47;
        v6 = ((__int64 (__fastcall *)(HDC, struct tagHANDLETABLE *, __int64, _QWORD, __int64))a3)(
               v5,
               lpHandleTable,
               Event,
               (unsigned __int16)v34,
               a4);
        if ( !v6 )
          break;
        v19 = v36;
      }
    }
    else
    {
      while ( 1 )
      {
        v22 = GetEvent(v19);
        v23 = (struct tagMETARECORD *)v22;
        if ( !v22 )
          break;
        if ( v22 == -1
          || !v8 && (*(_DWORD *)(v10 + 152) & 0x800) == 0
          || v45 && (v21 = *(unsigned int (__fastcall **)(HDC, _QWORD))(v45 + 32)) != 0 && !v21(v5, 0) )
        {
LABEL_47:
          v6 = 0;
          break;
        }
        PlayMetaFileRecord(v5, lpHandleTable, v23, (unsigned __int16)v34);
        v19 = v36;
      }
    }
    *(_DWORD *)(v36 + 48) = 0;
    if ( !v8 )
    {
      if ( iMode != 1 )
        SetGraphicsMode(v5, iMode);
      if ( !SelectObject(v5, h) )
      {
        StockObject = GetStockObject(7);
        SelectObject(v5, StockObject);
      }
      if ( !SelectObject(v5, DCObject) )
      {
        v25 = GetStockObject(4);
        SelectObject(v5, v25);
      }
      if ( !SelectPalette(v5, hPal, 0) )
      {
        v26 = (HPALETTE)GetStockObject(15);
        SelectPalette(v5, v26, 0);
      }
      if ( v40 != (HGDIOBJ)GetDCObject(v5, 655360) && !SelectObject(v5, v40) )
      {
        GetWindowExtEx(v5, &size);
        GetViewportExtEx(v5, &v38);
        v27 = SetMapMode(v5, 1);
        v39 = v27;
        v28 = GetStockObject(13);
        SelectObject(v5, v28);
        SetMapMode(v5, v27);
        SetWindowExtEx(v5, size.cx, size.cy, 0);
        SetViewportExtEx(v5, v38.cx, v38.cy, 0);
      }
      if ( !SelectClipRgn(v5, v17) )
        SelectClipRgn(v5, 0);
    }
    v29 = 0;
    if ( (_WORD)v34 )
    {
      do
      {
        v30 = lpHandleTable[v29].objectHandle[0];
        if ( v30 )
          DeleteObject(v30);
        v29 = (unsigned int)(v29 + 1);
      }
      while ( (unsigned int)v29 < (unsigned __int16)v34 );
      v5 = hdc;
      v10 = v44;
    }
    if ( (int)v39 > 0 )
      SelectObject(v5, v40);
    goto LABEL_69;
  }
  DCObject = (HGDIOBJ)GetDCObject(v5, 0x100000);
  v40 = (HGDIOBJ)GetDCObject(v5, 655360);
  hPal = (HPALETTE)GetDCObject(v5, 0x80000);
  h = (HGDIOBJ)GetDCObject(v5, 3145728);
  v15 = *(_DWORD *)(v10 + 152);
  v33 = v15 & 0x800;
  v48 = v33;
  *(_DWORD *)(v10 + 152) = v15 | 0x800;
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  v17 = RectRgn;
  if ( RectRgn )
  {
    ClipRgn = GetClipRgn(v5, RectRgn);
    v39 = -1;
    if ( ClipRgn != -1 )
    {
      if ( !ClipRgn )
      {
        DeleteObject(v17);
        v17 = 0;
      }
      iMode = GetGraphicsMode(v5);
      if ( iMode != 1 )
        SetGraphicsMode(v5, 1);
      goto LABEL_29;
    }
  }
LABEL_69:
  if ( v45 )
  {
    if ( !v8 )
    {
      v31 = *(_DWORD *)(v10 + 152);
      if ( (v31 & 0x800) == 0 )
        *(_DWORD *)(v10 + 152) = v33 | v31 & 0xFFFFF7FF;
    }
  }
  if ( v17 )
    DeleteObject(v17);
  LocalFree(lpHandleTable);
  return v6;
}

```

## disassembly

```asm
0x180093bc4  mov     rax, rsp
0x180093bc7  mov     [rax+10h], rbx
0x180093bcb  mov     [rax+20h], r9
0x180093bcf  mov     [rax+18h], r8
0x180093bd3  mov     [rax+8], rcx
0x180093bd7  push    rsi
0x180093bd8  push    r12
0x180093bda  push    r13
0x180093bdc  push    r14
0x180093bde  push    r15
0x180093be0  sub     rsp, 0C0h
0x180093be7  mov     r14, rdx
0x180093bea  mov     rbx, rcx
0x180093bed  xor     r15d, r15d
0x180093bf0  mov     qword ptr [rsp+0E8h+size.cx], r15
0x180093bf5  mov     qword ptr [rsp+0E8h+var_90.cx], r15
0x180093bfa  cmp     cs:gbDisableMetaFiles, r15d
0x180093c01  jz      short loc_180093C0C
0x180093c03  lea     eax, [r15+1]
0x180093c07  jmp     loc_180093D57
0x180093c0c  mov     eax, ebx
0x180093c0e  and     eax, 7F0000h
0x180093c13  cmp     eax, 660000h
0x180093c18  jz      short loc_180093C24
0x180093c1a  test    rbx, rbx
0x180093c1d  jnz     short loc_180093C2C
0x180093c1f  test    r8, r8
0x180093c22  jz      short loc_180093C2C
0x180093c24  mov     r12d, 1
0x180093c2a  jmp     short loc_180093C3F
0x180093c2c  mov     r12d, r15d
0x180093c2f  add     eax, 0FFFF0000h
0x180093c34  test    eax, 0FFDFFFFFh
0x180093c39  jnz     loc_180093D55
0x180093c3f  call    HANDLE_TO_INDEX
0x180093c44  mov     rsi, r15
0x180093c47  mov     [rsp+0E8h+var_60], r15
0x180093c4f  mov     rdx, r15
0x180093c52  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x180093c59  cmp     eax, [rcx]
0x180093c5b  jnb     loc_180093D0B
0x180093c61  xorps   xmm0, xmm0
0x180093c64  xor     ecx, ecx
0x180093c66  movups  [rsp+0E8h+var_50], xmm0
0x180093c6e  mov     [rsp+0E8h+var_40], rcx
0x180093c76  lea     rdx, [rsp+0E8h+var_50]
0x180093c7e  mov     ecx, eax
0x180093c80  call    cs:__imp_GdiGetEntry
0x180093c87  nop     dword ptr [rax+rax+00h]
0x180093c8c  mov     rdx, r15
0x180093c8f  test    eax, eax
0x180093c91  js      short loc_180093D0B
0x180093c93  cmp     byte ptr [rsp+0E8h+var_50+0Eh], 1
0x180093c9b  jnz     short loc_180093D0B
0x180093c9d  movzx   ecx, byte ptr [rsp+0E8h+var_50+0Dh]
0x180093ca5  shl     cx, 8
0x180093ca9  movzx   eax, byte ptr [rsp+0E8h+var_50+0Ch]
0x180093cb1  or      cx, ax
0x180093cb4  mov     eax, ebx
0x180093cb6  shr     eax, 10h
0x180093cb9  cmp     cx, ax
0x180093cbc  jnz     short loc_180093D0B
0x180093cbe  mov     rcx, qword ptr [rsp+0E8h+var_50+8]
0x180093cc6  and     ecx, 0FFFFFFFEh
0x180093cc9  mov     rax, cs:__imp_gW32PID
0x180093cd0  cmp     ecx, [rax]
0x180093cd2  jnz     short loc_180093D0B
0x180093cd4  mov     r8, [rsp+0E8h+var_40]
0x180093cdc  test    r8, r8
0x180093cdf  jz      short loc_180093D0B
0x180093ce1  mov     rax, cs:__imp_gCookie
0x180093ce8  mov     rdx, [rax]
0x180093ceb  mov     eax, edx
0x180093ced  and     eax, 3Fh
0x180093cf0  mov     ecx, 40h ; '@'
0x180093cf5  sub     ecx, eax
0x180093cf7  mov     rsi, r8
0x180093cfa  ror     rsi, cl
0x180093cfd  xor     rsi, rdx
0x180093d00  mov     [rsp+0E8h+var_60], rsi
0x180093d08  mov     rdx, rsi
0x180093d0b  test    r12d, r12d
0x180093d0e  jnz     short loc_180093D15
0x180093d10  test    rdx, rdx
0x180093d13  jz      short loc_180093D55
0x180093d15  mov     rcx, rbx
0x180093d18  call    cs:__imp_pldcGet
0x180093d1f  nop     dword ptr [rax+rax+00h]
0x180093d24  mov     [rsp+0E8h+var_58], rax
0x180093d2c  mov     edx, 260000h
0x180093d31  mov     rcx, r14
0x180093d34  call    pvClientObjGet
0x180093d39  mov     r14, rax
0x180093d3c  mov     [rsp+0E8h+var_A0], rax
0x180093d41  test    rax, rax
0x180093d44  jnz     short loc_180093D71
0x180093d46  lea     ecx, [rax+6]
0x180093d49  call    cs:__imp_GdiSetLastError
0x180093d50  nop     dword ptr [rax+rax+00h]
0x180093d55  xor     eax, eax
0x180093d57  mov     rbx, [rsp+0E8h+arg_8]
0x180093d5f  add     rsp, 0C0h
0x180093d66  pop     r15
0x180093d68  pop     r14
0x180093d6a  pop     r13
0x180093d6c  pop     r12
0x180093d6e  pop     rsi
0x180093d6f  retn
0x180093d71  movzx   eax, word ptr [rax+0Eh]
0x180093d75  mov     [rsp+0E8h+var_B0], rax
0x180093d7a  lea     rdx, ds:2[rax*8]; uBytes
0x180093d82  mov     ecx, 40h ; '@'; uFlags
0x180093d87  call    cs:__imp_LocalAlloc
0x180093d8e  nop     dword ptr [rax+rax+00h]
0x180093d93  mov     [rsp+0E8h+lpHandleTable], rax
0x180093d98  test    rax, rax
0x180093d9b  jz      short loc_180093D55
0x180093d9d  test    r12d, r12d
0x180093da0  jnz     loc_180093EA2
0x180093da6  mov     edx, 100000h
0x180093dab  mov     rcx, rbx
0x180093dae  call    GetDCObject
0x180093db3  mov     [rsp+0E8h+var_70], rax
0x180093db8  mov     edx, 0A0000h
0x180093dbd  mov     rcx, rbx
0x180093dc0  call    GetDCObject
0x180093dc5  mov     [rsp+0E8h+var_80], rax
0x180093dca  mov     edx, 80000h
0x180093dcf  mov     rcx, rbx
0x180093dd2  call    GetDCObject
0x180093dd7  mov     [rsp+0E8h+hPal], rax
0x180093ddf  mov     edx, 300000h
0x180093de4  mov     rcx, rbx
0x180093de7  call    GetDCObject
0x180093dec  mov     [rsp+0E8h+h], rax
0x180093df1  mov     eax, [rsi+98h]
0x180093df7  mov     edx, eax
0x180093df9  mov     ecx, 800h
0x180093dfe  and     edx, ecx
0x180093e00  mov     [rsp+0E8h+var_B4], edx
0x180093e04  mov     [rsp+0E8h+var_38], edx
0x180093e0b  or      eax, ecx
0x180093e0d  mov     [rsi+98h], eax
0x180093e13  xor     r9d, r9d; y2
0x180093e16  xor     r8d, r8d; x2
0x180093e19  xor     edx, edx; y1
0x180093e1b  xor     ecx, ecx; x1
0x180093e1d  call    cs:__imp_CreateRectRgn
0x180093e24  nop     dword ptr [rax+rax+00h]
0x180093e29  mov     r13, rax
0x180093e2c  test    rax, rax
0x180093e2f  jz      loc_1800941B0
0x180093e35  mov     rdx, rax; hrgn
0x180093e38  mov     rcx, rbx; hdc
0x180093e3b  call    GetClipRgn
0x180093e40  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180093e44  mov     [rsp+0E8h+var_88], rcx
0x180093e49  cmp     eax, ecx
0x180093e4b  jz      loc_1800941B0
0x180093e51  xor     r15d, r15d
0x180093e54  test    eax, eax
0x180093e56  jnz     short loc_180093E6A
0x180093e58  mov     rcx, r13; ho
0x180093e5b  call    cs:__imp_DeleteObject
0x180093e62  nop     dword ptr [rax+rax+00h]
0x180093e67  mov     r13d, r15d
0x180093e6a  mov     rcx, rbx; hdc
0x180093e6d  call    GetGraphicsMode
0x180093e72  mov     [rsp+0E8h+iMode], eax
0x180093e76  cmp     eax, 1
0x180093e79  jz      short loc_180093ECF
0x180093e7b  mov     edx, 1; iMode
0x180093e80  mov     rcx, rbx; hdc
0x180093e83  call    SetGraphicsMode
0x180093e88  jmp     short loc_180093ECF
0x180093e8a  mov     ecx, 57h ; 'W'
0x180093e8f  call    cs:__imp_GdiSetLastError
0x180093e96  nop     dword ptr [rax+rax+00h]
0x180093e9b  xor     eax, eax
0x180093e9d  jmp     loc_180093D57
0x180093ea2  mov     [rsp+0E8h+var_80], r15
0x180093ea7  mov     [rsp+0E8h+hPal], r15
0x180093eaf  mov     [rsp+0E8h+h], r15
0x180093eb4  mov     r13, r15
0x180093eb7  mov     [rsp+0E8h+iMode], r15d
0x180093ebc  mov     [rsp+0E8h+var_B4], r15d
0x180093ec1  mov     [rsp+0E8h+var_70], r15
0x180093ec6  mov     [rsp+0E8h+var_88], 0FFFFFFFFFFFFFFFFh
0x180093ecf  xor     edx, edx
0x180093ed1  mov     rcx, r14
0x180093ed4  cmp     [rsp+0E8h+arg_10], r15
0x180093edc  lea     r15d, [rdx+1]
0x180093ee0  jz      loc_180093FAD
0x180093ee6  jmp     short loc_180093F45
0x180093ee8  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180093eec  jz      loc_180093FBC
0x180093ef2  test    r12d, r12d
0x180093ef5  jnz     short loc_180093F07
0x180093ef7  test    dword ptr [rsi+98h], 800h
0x180093f01  jz      loc_180093FBC
0x180093f07  mov     rax, [rsp+0E8h+arg_18]
0x180093f0f  mov     [rsp+0E8h+var_C8], rax
0x180093f14  movzx   r9d, word ptr [rsp+0E8h+var_B0]
0x180093f1a  mov     r8, r14
0x180093f1d  mov     rdx, [rsp+0E8h+lpHandleTable]
0x180093f22  mov     rcx, rbx
0x180093f25  mov     rax, [rsp+0E8h+arg_10]
0x180093f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f32  mov     r15d, eax
0x180093f35  test    eax, eax
0x180093f37  jz      loc_180093FBF
0x180093f3d  mov     rdx, r14
0x180093f40  mov     rcx, [rsp+0E8h+var_A0]
0x180093f45  call    GetEvent
0x180093f4a  test    rax, rax
0x180093f4d  mov     r14, rax
0x180093f50  jnz     short loc_180093EE8
0x180093f52  jmp     short loc_180093FBF
0x180093f54  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180093f58  jz      short loc_180093FBC
0x180093f5a  test    r12d, r12d
0x180093f5d  jnz     short loc_180093F6B
0x180093f5f  test    dword ptr [rsi+98h], 800h
0x180093f69  jz      short loc_180093FBC
0x180093f6b  mov     rax, [rsp+0E8h+var_58]
0x180093f73  test    rax, rax
0x180093f76  jz      short loc_180093F8F
0x180093f78  mov     rax, [rax+20h]
0x180093f7c  test    rax, rax
0x180093f7f  jz      short loc_180093F8F
0x180093f81  xor     edx, edx
0x180093f83  mov     rcx, rbx
0x180093f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f8b  test    eax, eax
0x180093f8d  jz      short loc_180093FBC
0x180093f8f  movzx   r9d, word ptr [rsp+0E8h+var_B0]; noObjs
0x180093f95  mov     r8, r14; lpMR
0x180093f98  mov     rdx, [rsp+0E8h+lpHandleTable]; lpHandleTable
0x180093f9d  mov     rcx, rbx; hdc
0x180093fa0  call    PlayMetaFileRecord
0x180093fa5  mov     rdx, r14
0x180093fa8  mov     rcx, [rsp+0E8h+var_A0]
0x180093fad  call    GetEvent
0x180093fb2  test    rax, rax
0x180093fb5  mov     r14, rax
0x180093fb8  jnz     short loc_180093F54
0x180093fba  jmp     short loc_180093FBF
0x180093fbc  xor     r15d, r15d
0x180093fbf  mov     rax, [rsp+0E8h+var_A0]
0x180093fc4  mov     dword ptr [rax+30h], 0
0x180093fcb  test    r12d, r12d
0x180093fce  jnz     loc_180094152
0x180093fd4  mov     eax, [rsp+0E8h+iMode]
0x180093fd8  cmp     eax, 1
0x180093fdb  jz      short loc_180093FE7
0x180093fdd  mov     edx, eax; iMode
0x180093fdf  mov     rcx, rbx; hdc
0x180093fe2  call    SetGraphicsMode
0x180093fe7  mov     rdx, [rsp+0E8h+h]; h
0x180093fec  mov     rcx, rbx; hdc
0x180093fef  call    cs:__imp_SelectObject
0x180093ff6  nop     dword ptr [rax+rax+00h]
0x180093ffb  test    rax, rax
0x180093ffe  jnz     short loc_18009401A
0x180094000  lea     ecx, [rax+7]; i
0x180094003  call    GetStockObject
0x180094008  mov     rdx, rax; h
0x18009400b  mov     rcx, rbx; hdc
0x18009400e  call    cs:__imp_SelectObject
0x180094015  nop     dword ptr [rax+rax+00h]
0x18009401a  mov     rdx, [rsp+0E8h+var_70]; h
0x18009401f  mov     rcx, rbx; hdc
0x180094022  call    cs:__imp_SelectObject
0x180094029  nop     dword ptr [rax+rax+00h]
0x18009402e  test    rax, rax
0x180094031  jnz     short loc_18009404D
0x180094033  lea     ecx, [rax+4]; i
0x180094036  call    GetStockObject
0x18009403b  mov     rdx, rax; h
0x18009403e  mov     rcx, rbx; hdc
0x180094041  call    cs:__imp_SelectObject
0x180094048  nop     dword ptr [rax+rax+00h]
0x18009404d  xor     r8d, r8d; bForceBkgd
0x180094050  mov     rdx, [rsp+0E8h+hPal]; hPal
0x180094058  mov     rcx, rbx; hdc
0x18009405b  call    SelectPalette
0x180094060  test    rax, rax
0x180094063  jnz     short loc_18009407B
0x180094065  lea     ecx, [rax+0Fh]; i
0x180094068  call    GetStockObject
0x18009406d  mov     rdx, rax; hPal
0x180094070  xor     r8d, r8d; bForceBkgd
0x180094073  mov     rcx, rbx; hdc
0x180094076  call    SelectPalette
0x18009407b  mov     edx, 0A0000h
0x180094080  mov     rcx, rbx
0x180094083  call    GetDCObject
0x180094088  mov     rcx, [rsp+0E8h+var_80]
0x18009408d  cmp     rcx, rax
0x180094090  jz      loc_18009412B
  ... truncated ...
```
