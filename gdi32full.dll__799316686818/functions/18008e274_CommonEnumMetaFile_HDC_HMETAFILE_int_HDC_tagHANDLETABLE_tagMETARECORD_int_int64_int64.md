# CommonEnumMetaFile(HDC__ *,HMETAFILE__ *,int (*)(HDC__ *,tagHANDLETABLE *,tagMETARECORD *,int,__int64),__int64)

- ea: `0x18008e274`
- end: `0x18008e844`
- name: `?CommonEnumMetaFile@@YAHPEAUHDC__@@PEAUHMETAFILE__@@P6AH0PEAUtagHANDLETABLE@@PEAUtagMETARECORD@@H_J@Z4@Z`
- size: `1488`
- prototype: `__int64 __fastcall(HDC hdc, HMETAFILE, int (*)(HDC, struct tagHANDLETABLE *, struct tagMETARECORD *, int, __int64), __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800795e0`
- `0x18008ec60`

## callees

- `0x18000d6c0`
- `0x180010000`
- `0x180010210`
- `0x180010690`
- `0x180010950`
- `0x180010b70`
- `0x18001f270`
- `0x180021fe0`
- `0x180024fb8`
- `0x180025090`
- `0x180029790`
- `0x18003ba90`
- `0x18003bd30`
- `0x18004fc88`
- `0x1800710c4`
- `0x18008e274`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008e424`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008e424`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008e836`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008e836`
- `GDI32!CreateRectRgn` at `0x18008e4b4`
- `GDI32!CreateRectRgn` at `0x18008e4b4`
- `GDI32!SelectClipRgn` at `0x18008e792`
- `GDI32!SelectClipRgn` at `0x18008e7a1`
- `GDI32!SelectClipRgn` at `0x18008e792`
- `GDI32!SelectClipRgn` at `0x18008e7a1`
- `GDI32!SelectObject` at `0x18008e674`
- `GDI32!SelectObject` at `0x18008e68d`
- `GDI32!SelectObject` at `0x18008e69b`
- `GDI32!SelectObject` at `0x18008e6b4`
- `GDI32!SelectObject` at `0x18008e709`
- `GDI32!SelectObject` at `0x18008e753`
- `GDI32!SelectObject` at `0x18008e7f3`
- `GDI32!SelectObject` at `0x18008e674`
- `GDI32!SelectObject` at `0x18008e68d`
- `GDI32!SelectObject` at `0x18008e69b`
- `GDI32!SelectObject` at `0x18008e6b4`
- `GDI32!SelectObject` at `0x18008e709`
- `GDI32!SelectObject` at `0x18008e753`
- `GDI32!SelectObject` at `0x18008e7f3`
- `GDI32!GdiGetEntry` at `0x18008e330`
- `GDI32!GdiGetEntry` at `0x18008e330`
- `GDI32!gW32PID` at `0x18008e373`
- `GDI32!gCookie` at `0x18008e38b`
- `GDI32!gMaxGdiHandleCount` at `0x18008e302`
- `GDI32!pldcGet` at `0x18008e3c2`
- `GDI32!pldcGet` at `0x18008e3c2`
- `GDI32!GdiSetLastError` at `0x18008e3ed`
- `GDI32!GdiSetLastError` at `0x18008e51a`
- `GDI32!GdiSetLastError` at `0x18008e3ed`
- `GDI32!GdiSetLastError` at `0x18008e51a`
- `GDI32!DeleteObject` at `0x18008e4ec`
- `GDI32!DeleteObject` at `0x18008e7c6`
- `GDI32!DeleteObject` at `0x18008e82b`
- `GDI32!DeleteObject` at `0x18008e4ec`
- `GDI32!DeleteObject` at `0x18008e7c6`
- `GDI32!DeleteObject` at `0x18008e82b`

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
0x18008e274  mov     rax, rsp
0x18008e277  mov     [rax+10h], rbx
0x18008e27b  mov     [rax+20h], r9
0x18008e27f  mov     [rax+18h], r8
0x18008e283  mov     [rax+8], rcx
0x18008e287  push    rsi
0x18008e288  push    r12
0x18008e28a  push    r13
0x18008e28c  push    r14
0x18008e28e  push    r15
0x18008e290  sub     rsp, 0C0h
0x18008e297  mov     r14, rdx
0x18008e29a  mov     rbx, rcx
0x18008e29d  xor     r15d, r15d
0x18008e2a0  mov     qword ptr [rsp+0E8h+size.cx], r15
0x18008e2a5  mov     qword ptr [rsp+0E8h+var_90.cx], r15
0x18008e2aa  cmp     cs:gbDisableMetaFiles, r15d
0x18008e2b1  jz      short loc_18008E2BC
0x18008e2b3  lea     eax, [r15+1]
0x18008e2b7  jmp     loc_18008E3F5
0x18008e2bc  mov     eax, ebx
0x18008e2be  and     eax, 7F0000h
0x18008e2c3  cmp     eax, 660000h
0x18008e2c8  jz      short loc_18008E2D4
0x18008e2ca  test    rbx, rbx
0x18008e2cd  jnz     short loc_18008E2DC
0x18008e2cf  test    r8, r8
0x18008e2d2  jz      short loc_18008E2DC
0x18008e2d4  mov     r12d, 1
0x18008e2da  jmp     short loc_18008E2EF
0x18008e2dc  mov     r12d, r15d
0x18008e2df  add     eax, 0FFFF0000h
0x18008e2e4  test    eax, 0FFDFFFFFh
0x18008e2e9  jnz     loc_18008E3F3
0x18008e2ef  call    HANDLE_TO_INDEX
0x18008e2f4  mov     rsi, r15
0x18008e2f7  mov     [rsp+0E8h+var_60], r15
0x18008e2ff  mov     rdx, r15
0x18008e302  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18008e309  cmp     eax, [rcx]
0x18008e30b  jnb     loc_18008E3B5
0x18008e311  xorps   xmm0, xmm0
0x18008e314  xor     ecx, ecx
0x18008e316  movups  [rsp+0E8h+var_50], xmm0
0x18008e31e  mov     [rsp+0E8h+var_40], rcx
0x18008e326  lea     rdx, [rsp+0E8h+var_50]
0x18008e32e  mov     ecx, eax
0x18008e330  call    cs:__imp_GdiGetEntry
0x18008e336  mov     rdx, r15
0x18008e339  test    eax, eax
0x18008e33b  js      short loc_18008E3B5
0x18008e33d  cmp     byte ptr [rsp+0E8h+var_50+0Eh], 1
0x18008e345  jnz     short loc_18008E3B5
0x18008e347  movzx   ecx, byte ptr [rsp+0E8h+var_50+0Dh]
0x18008e34f  shl     cx, 8
0x18008e353  movzx   eax, byte ptr [rsp+0E8h+var_50+0Ch]
0x18008e35b  or      cx, ax
0x18008e35e  mov     eax, ebx
0x18008e360  shr     eax, 10h
0x18008e363  cmp     cx, ax
0x18008e366  jnz     short loc_18008E3B5
0x18008e368  mov     rcx, qword ptr [rsp+0E8h+var_50+8]
0x18008e370  and     ecx, 0FFFFFFFEh
0x18008e373  mov     rax, cs:__imp_gW32PID
0x18008e37a  cmp     ecx, [rax]
0x18008e37c  jnz     short loc_18008E3B5
0x18008e37e  mov     r8, [rsp+0E8h+var_40]
0x18008e386  test    r8, r8
0x18008e389  jz      short loc_18008E3B5
0x18008e38b  mov     rax, cs:__imp_gCookie
0x18008e392  mov     rdx, [rax]
0x18008e395  mov     eax, edx
0x18008e397  and     eax, 3Fh
0x18008e39a  mov     ecx, 40h ; '@'
0x18008e39f  sub     ecx, eax
0x18008e3a1  mov     rsi, r8
0x18008e3a4  ror     rsi, cl
0x18008e3a7  xor     rsi, rdx
0x18008e3aa  mov     [rsp+0E8h+var_60], rsi
0x18008e3b2  mov     rdx, rsi
0x18008e3b5  test    r12d, r12d
0x18008e3b8  jnz     short loc_18008E3BF
0x18008e3ba  test    rdx, rdx
0x18008e3bd  jz      short loc_18008E3F3
0x18008e3bf  mov     rcx, rbx
0x18008e3c2  call    cs:__imp_pldcGet
0x18008e3c8  mov     [rsp+0E8h+var_58], rax
0x18008e3d0  mov     edx, 260000h
0x18008e3d5  mov     rcx, r14
0x18008e3d8  call    pvClientObjGet
0x18008e3dd  mov     r14, rax
0x18008e3e0  mov     [rsp+0E8h+var_A0], rax
0x18008e3e5  test    rax, rax
0x18008e3e8  jnz     short loc_18008E40E
0x18008e3ea  lea     ecx, [rax+6]
0x18008e3ed  call    cs:__imp_GdiSetLastError
0x18008e3f3  xor     eax, eax
0x18008e3f5  mov     rbx, [rsp+0E8h+arg_8]
0x18008e3fd  add     rsp, 0C0h
0x18008e404  pop     r15
0x18008e406  pop     r14
0x18008e408  pop     r13
0x18008e40a  pop     r12
0x18008e40c  pop     rsi
0x18008e40d  retn
0x18008e40e  movzx   eax, word ptr [rax+0Eh]
0x18008e412  mov     [rsp+0E8h+var_B0], rax
0x18008e417  lea     rdx, ds:2[rax*8]; uBytes
0x18008e41f  mov     ecx, 40h ; '@'; uFlags
0x18008e424  call    cs:__imp_LocalAlloc
0x18008e42a  mov     [rsp+0E8h+lpHandleTable], rax
0x18008e42f  test    rax, rax
0x18008e432  jz      short loc_18008E3F3
0x18008e434  test    r12d, r12d
0x18008e437  jnz     loc_18008E527
0x18008e43d  mov     edx, 100000h
0x18008e442  mov     rcx, rbx
0x18008e445  call    GetDCObject
0x18008e44a  mov     [rsp+0E8h+var_70], rax
0x18008e44f  mov     edx, 0A0000h
0x18008e454  mov     rcx, rbx
0x18008e457  call    GetDCObject
0x18008e45c  mov     [rsp+0E8h+var_80], rax
0x18008e461  mov     edx, 80000h
0x18008e466  mov     rcx, rbx
0x18008e469  call    GetDCObject
0x18008e46e  mov     [rsp+0E8h+hPal], rax
0x18008e476  mov     edx, 300000h
0x18008e47b  mov     rcx, rbx
0x18008e47e  call    GetDCObject
0x18008e483  mov     [rsp+0E8h+h], rax
0x18008e488  mov     eax, [rsi+98h]
0x18008e48e  mov     edx, eax
0x18008e490  mov     ecx, 800h
0x18008e495  and     edx, ecx
0x18008e497  mov     [rsp+0E8h+var_B4], edx
0x18008e49b  mov     [rsp+0E8h+var_38], edx
0x18008e4a2  or      eax, ecx
0x18008e4a4  mov     [rsi+98h], eax
0x18008e4aa  xor     r9d, r9d; y2
0x18008e4ad  xor     r8d, r8d; x2
0x18008e4b0  xor     edx, edx; y1
0x18008e4b2  xor     ecx, ecx; x1
0x18008e4b4  call    cs:__imp_CreateRectRgn
0x18008e4ba  mov     r13, rax
0x18008e4bd  test    rax, rax
0x18008e4c0  jz      loc_18008E7F9
0x18008e4c6  mov     rdx, rax; hrgn
0x18008e4c9  mov     rcx, rbx; hdc
0x18008e4cc  call    GetClipRgn
0x18008e4d1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008e4d5  mov     [rsp+0E8h+var_88], rcx
0x18008e4da  cmp     eax, ecx
0x18008e4dc  jz      loc_18008E7F9
0x18008e4e2  xor     r15d, r15d
0x18008e4e5  test    eax, eax
0x18008e4e7  jnz     short loc_18008E4F5
0x18008e4e9  mov     rcx, r13; ho
0x18008e4ec  call    cs:__imp_DeleteObject
0x18008e4f2  mov     r13d, r15d
0x18008e4f5  mov     rcx, rbx; hdc
0x18008e4f8  call    GetGraphicsMode
0x18008e4fd  mov     [rsp+0E8h+iMode], eax
0x18008e501  cmp     eax, 1
0x18008e504  jz      short loc_18008E554
0x18008e506  mov     edx, 1; iMode
0x18008e50b  mov     rcx, rbx; hdc
0x18008e50e  call    SetGraphicsMode
0x18008e513  jmp     short loc_18008E554
0x18008e515  mov     ecx, 57h ; 'W'
0x18008e51a  call    cs:__imp_GdiSetLastError
0x18008e520  xor     eax, eax
0x18008e522  jmp     loc_18008E3F5
0x18008e527  mov     [rsp+0E8h+var_80], r15
0x18008e52c  mov     [rsp+0E8h+hPal], r15
0x18008e534  mov     [rsp+0E8h+h], r15
0x18008e539  mov     r13, r15
0x18008e53c  mov     [rsp+0E8h+iMode], r15d
0x18008e541  mov     [rsp+0E8h+var_B4], r15d
0x18008e546  mov     [rsp+0E8h+var_70], r15
0x18008e54b  mov     [rsp+0E8h+var_88], 0FFFFFFFFFFFFFFFFh
0x18008e554  xor     edx, edx
0x18008e556  mov     rcx, r14
0x18008e559  cmp     [rsp+0E8h+arg_10], r15
0x18008e561  lea     r15d, [rdx+1]
0x18008e565  jz      loc_18008E632
0x18008e56b  jmp     short loc_18008E5CA
0x18008e56d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18008e571  jz      loc_18008E641
0x18008e577  test    r12d, r12d
0x18008e57a  jnz     short loc_18008E58C
0x18008e57c  test    dword ptr [rsi+98h], 800h
0x18008e586  jz      loc_18008E641
0x18008e58c  mov     rax, [rsp+0E8h+arg_18]
0x18008e594  mov     [rsp+0E8h+var_C8], rax
0x18008e599  movzx   r9d, word ptr [rsp+0E8h+var_B0]
0x18008e59f  mov     r8, r14
0x18008e5a2  mov     rdx, [rsp+0E8h+lpHandleTable]
0x18008e5a7  mov     rcx, rbx
0x18008e5aa  mov     rax, [rsp+0E8h+arg_10]
0x18008e5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e5b7  mov     r15d, eax
0x18008e5ba  test    eax, eax
0x18008e5bc  jz      loc_18008E644
0x18008e5c2  mov     rdx, r14
0x18008e5c5  mov     rcx, [rsp+0E8h+var_A0]
0x18008e5ca  call    GetEvent
0x18008e5cf  test    rax, rax
0x18008e5d2  mov     r14, rax
0x18008e5d5  jnz     short loc_18008E56D
0x18008e5d7  jmp     short loc_18008E644
0x18008e5d9  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18008e5dd  jz      short loc_18008E641
0x18008e5df  test    r12d, r12d
0x18008e5e2  jnz     short loc_18008E5F0
0x18008e5e4  test    dword ptr [rsi+98h], 800h
0x18008e5ee  jz      short loc_18008E641
0x18008e5f0  mov     rax, [rsp+0E8h+var_58]
0x18008e5f8  test    rax, rax
0x18008e5fb  jz      short loc_18008E614
0x18008e5fd  mov     rax, [rax+20h]
0x18008e601  test    rax, rax
0x18008e604  jz      short loc_18008E614
0x18008e606  xor     edx, edx
0x18008e608  mov     rcx, rbx
0x18008e60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e610  test    eax, eax
0x18008e612  jz      short loc_18008E641
0x18008e614  movzx   r9d, word ptr [rsp+0E8h+var_B0]; noObjs
0x18008e61a  mov     r8, r14; lpMR
0x18008e61d  mov     rdx, [rsp+0E8h+lpHandleTable]; lpHandleTable
0x18008e622  mov     rcx, rbx; hdc
0x18008e625  call    PlayMetaFileRecord
0x18008e62a  mov     rdx, r14
0x18008e62d  mov     rcx, [rsp+0E8h+var_A0]
0x18008e632  call    GetEvent
0x18008e637  test    rax, rax
0x18008e63a  mov     r14, rax
0x18008e63d  jnz     short loc_18008E5D9
0x18008e63f  jmp     short loc_18008E644
0x18008e641  xor     r15d, r15d
0x18008e644  mov     rax, [rsp+0E8h+var_A0]
0x18008e649  mov     dword ptr [rax+30h], 0
0x18008e650  test    r12d, r12d
0x18008e653  jnz     loc_18008E7A7
0x18008e659  mov     eax, [rsp+0E8h+iMode]
0x18008e65d  cmp     eax, 1
0x18008e660  jz      short loc_18008E66C
0x18008e662  mov     edx, eax; iMode
0x18008e664  mov     rcx, rbx; hdc
0x18008e667  call    SetGraphicsMode
0x18008e66c  mov     rdx, [rsp+0E8h+h]; h
0x18008e671  mov     rcx, rbx; hdc
0x18008e674  call    cs:__imp_SelectObject
0x18008e67a  test    rax, rax
0x18008e67d  jnz     short loc_18008E693
0x18008e67f  lea     ecx, [rax+7]; i
0x18008e682  call    GetStockObject
0x18008e687  mov     rdx, rax; h
0x18008e68a  mov     rcx, rbx; hdc
0x18008e68d  call    cs:__imp_SelectObject
0x18008e693  mov     rdx, [rsp+0E8h+var_70]; h
0x18008e698  mov     rcx, rbx; hdc
0x18008e69b  call    cs:__imp_SelectObject
0x18008e6a1  test    rax, rax
0x18008e6a4  jnz     short loc_18008E6BA
0x18008e6a6  lea     ecx, [rax+4]; i
0x18008e6a9  call    GetStockObject
0x18008e6ae  mov     rdx, rax; h
0x18008e6b1  mov     rcx, rbx; hdc
0x18008e6b4  call    cs:__imp_SelectObject
0x18008e6ba  xor     r8d, r8d; bForceBkgd
0x18008e6bd  mov     rdx, [rsp+0E8h+hPal]; hPal
0x18008e6c5  mov     rcx, rbx; hdc
0x18008e6c8  call    SelectPalette
0x18008e6cd  test    rax, rax
0x18008e6d0  jnz     short loc_18008E6E8
0x18008e6d2  lea     ecx, [rax+0Fh]; i
0x18008e6d5  call    GetStockObject
0x18008e6da  mov     rdx, rax; hPal
0x18008e6dd  xor     r8d, r8d; bForceBkgd
0x18008e6e0  mov     rcx, rbx; hdc
0x18008e6e3  call    SelectPalette
0x18008e6e8  mov     edx, 0A0000h
0x18008e6ed  mov     rcx, rbx
0x18008e6f0  call    GetDCObject
0x18008e6f5  mov     rcx, [rsp+0E8h+var_80]
0x18008e6fa  cmp     rcx, rax
0x18008e6fd  jz      loc_18008E78C
0x18008e703  mov     rdx, rcx; h
0x18008e706  mov     rcx, rbx; hdc
0x18008e709  call    cs:__imp_SelectObject
0x18008e70f  test    rax, rax
0x18008e712  jnz     short loc_18008E78C
0x18008e714  lea     rdx, [rsp+0E8h+size]; lpsize
0x18008e719  mov     rcx, rbx; hdc
0x18008e71c  call    GetWindowExtEx
0x18008e721  lea     rdx, [rsp+0E8h+var_90]; lpsize
0x18008e726  mov     rcx, rbx; hdc
0x18008e729  call    GetViewportExtEx
  ... truncated ...
```
