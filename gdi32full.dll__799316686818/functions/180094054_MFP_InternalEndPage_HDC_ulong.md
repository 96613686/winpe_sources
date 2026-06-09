# MFP_InternalEndPage(HDC__ *,ulong)

- ea: `0x180094054`
- end: `0x18009457c`
- name: `?MFP_InternalEndPage@@YAHPEAUHDC__@@K@Z`
- size: `1320`
- prototype: `__int64 __fastcall(HDC hdc, unsigned int)`
- caller_count: `2`
- callee_count: `27`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006d2ac`
- `0x180094e5c`

## callees

- `0x180010000`
- `0x180010210`
- `0x1800102f0`
- `0x1800104e0`
- `0x180010690`
- `0x180010790`
- `0x180010870`
- `0x180010950`
- `0x180010b70`
- `0x180022f88`
- `0x180029c30`
- `0x1800317c8`
- `0x18003ba90`
- `0x18004c018`
- `0x18004c138`
- `0x180051124`
- `0x1800518e0`
- `0x18006aeac`
- `0x18006c074`
- `0x1800791c8`
- `0x180079930`
- `0x18007ac50`
- `0x18008025c`
- `0x1800802e0`
- `0x18008decc`
- `0x180094054`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800941bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800941bf`
- `GDI32!CreateRectRgn` at `0x1800942d4`
- `GDI32!CreateRectRgn` at `0x1800942d4`
- `GDI32!GetDeviceCaps` at `0x18009424f`
- `GDI32!GetDeviceCaps` at `0x180094260`
- `GDI32!GetDeviceCaps` at `0x18009424f`
- `GDI32!GetDeviceCaps` at `0x180094260`
- `GDI32!SelectClipRgn` at `0x1800942fe`
- `GDI32!SelectClipRgn` at `0x180094383`
- `GDI32!SelectClipRgn` at `0x1800942fe`
- `GDI32!SelectClipRgn` at `0x180094383`
- `GDI32!SetWorldTransform` at `0x1800943a4`
- `GDI32!SetWorldTransform` at `0x1800943a4`
- `GDI32!pldcGet` at `0x180094098`
- `GDI32!pldcGet` at `0x180094098`
- `GDI32!GdiSetLastError` at `0x18009453c`
- `GDI32!GdiSetLastError` at `0x18009454d`
- `GDI32!GdiSetLastError` at `0x18009453c`
- `GDI32!GdiSetLastError` at `0x18009454d`
- `GDI32!DeleteObject` at `0x1800942ef`
- `GDI32!DeleteObject` at `0x18009438c`
- `GDI32!DeleteObject` at `0x1800942ef`
- `GDI32!DeleteObject` at `0x18009438c`
- `ntdll!RtlDecodePointer` at `0x180094518`
- `ntdll!RtlDecodePointer` at `0x180094518`
- `win32u!NtGdiDoBanding` at `0x18009427e`
- `win32u!NtGdiDoBanding` at `0x18009427e`
- `win32u!NtGdiGetTransform` at `0x1800942c3`
- `win32u!NtGdiGetTransform` at `0x1800942c3`

## pseudocode

```c
__int64 __fastcall MFP_InternalEndPage(HDC hdc, unsigned int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  BOOL v6; // edi
  __int64 v7; // rsi
  int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // r12d
  struct tagSIZE i; // r15
  __int16 v12; // bx
  void *v13; // rcx
  HLOCAL v14; // rdi
  int v15; // ebx
  HENHMETAFILE v16; // r12
  LONG DeviceCaps; // eax
  int v18; // r15d
  HRGN RectRgn; // rdi
  int v20; // eax
  unsigned int v21; // r15d
  __int64 v22; // rax
  int v23; // ecx
  __int64 v24; // rdi
  unsigned int (__fastcall *v25)(_QWORD); // rax
  int iMode[2]; // [rsp+30h] [rbp-49h] BYREF
  struct _POINTL v28; // [rsp+38h] [rbp-41h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-39h] BYREF
  struct tagSIZE v30; // [rsp+48h] [rbp-31h] BYREF
  struct tagPOINT point; // [rsp+50h] [rbp-29h] BYREF
  struct tagSIZE size; // [rsp+58h] [rbp-21h] BYREF
  struct tagSIZE v33; // [rsp+60h] [rbp-19h] BYREF
  struct tagRECT v34; // [rsp+68h] [rbp-11h] BYREF
  XFORM xf; // [rsp+78h] [rbp-1h] BYREF

  v4 = (unsigned int)hdc & 0x7F0000;
  if ( ((unsigned int)hdc & 0x7F0000) == 0x10000 )
    return 0;
  v5 = pldcGet(hdc);
  v6 = 0;
  v7 = v5;
  if ( !v5 || v4 == 6684672 )
  {
    GdiSetLastError(6);
    return 0;
  }
  v8 = *(_DWORD *)(v5 + 8);
  if ( (v8 & 0x10080) != 0x80 )
  {
    GdiSetLastError(87);
    return -1;
  }
  if ( (v8 & 0x20000000) == 0 )
    a2 = (a2 != 1) + 10;
  v9 = v8 & 0xDFFFFFFF;
  *(_DWORD *)(v5 + 8) = v9;
  if ( (v9 & 0x20) != 0 )
    vSAPCallback(v5);
  *(_DWORD *)(v7 + 8) &= ~0x80u;
  if ( (((*(_DWORD *)(v7 + 8) & 0x500000) != 0) & _bittest((const signed __int32 *)(v7 + 8), 0xEu)) != 0 )
  {
    hMem = 0;
    v10 = 0;
    iMode[0] = 0;
    v28.x = 0;
    while ( v10 < 0x20 )
    {
      for ( i = *(struct tagSIZE *)(*(_QWORD *)(v7 + 104) + 8LL * v10); i; i = v30 )
      {
        v12 = *(_WORD *)(*(_QWORD *)&i + 16LL);
        v30 = *(struct tagSIZE *)(*(_QWORD *)&i + 8LL);
        if ( (v12 & 2) == 0 || *(_DWORD *)(*(_QWORD *)&i + 40LL) )
        {
          if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))bDoFontSubset)(
                                i,
                                &hMem,
                                iMode,
                                &v28)
            || !v28.x
            || (v14 = hMem,
                v15 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WriteFontDataAsEMFComment)(
                        v7,
                        (unsigned int)((v12 & 2) != 0) + 7,
                        i,
                        8,
                        hMem,
                        v28.x,
                        iMode[0]),
                LocalFree(v14),
                v6 = 0,
                !v15) )
          {
            if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))bAddUFIandWriteSpool)(
                                  hdc,
                                  i,
                                  1,
                                  *(unsigned __int16 *)(*(_QWORD *)&i + 18LL)) )
              return -1;
          }
        }
        else
        {
          v13 = *(void **)(*(_QWORD *)&i + 48LL);
          if ( v13 )
          {
            LocalFree(v13);
            *(_QWORD *)(*(_QWORD *)&i + 48LL) = 0;
          }
        }
      }
      ++v10;
    }
  }
  v16 = (HENHMETAFILE)UnassociateEnhMetaFile(hdc, 1);
  if ( !v16 )
    return -1;
  if ( (*(_DWORD *)(v7 + 8) & 0x80000) != 0 )
  {
    v28 = 0;
    hMem = 0;
    point = 0;
    size = 0;
    v33 = 0;
    v30 = 0;
    memset(&xf, 0, sizeof(xf));
    *(_QWORD *)&v34.left = 0;
    v34.right = GetDeviceCaps(hdc, 118);
    DeviceCaps = GetDeviceCaps(hdc, 117);
    *(_DWORD *)(v7 + 8) &= ~0x20000u;
    v34.bottom = DeviceCaps;
    v18 = NtGdiDoBanding(hdc, 1, &v28, &v30);
    GetViewportOrgEx(hdc, (LPPOINT)&hMem);
    GetWindowOrgEx(hdc, &point);
    GetWindowExtEx(hdc, &size);
    GetViewportExtEx(hdc, &v33);
    NtGdiGetTransform(hdc, 515, &xf);
    RectRgn = CreateRectRgn(0, 0, 1, 1);
    if ( GetClipRgn(hdc, RectRgn) )
    {
      SelectClipRgn(hdc, 0);
    }
    else
    {
      DeleteObject(RectRgn);
      RectRgn = 0;
    }
    iMode[0] = SetMapMode(hdc, 1);
    SetWindowOrgEx(hdc, 0, 0, 0);
    ModifyWorldTransform(hdc, 0, 1u);
    if ( v18 )
    {
      do
      {
        PrintBand(hdc, v16, &v28, &v34, &v30, 0);
        v20 = NextBand(hdc, &v28);
        v18 = v20;
      }
      while ( v28.x != -1 && v20 );
    }
    if ( RectRgn )
    {
      SelectClipRgn(hdc, RectRgn);
      DeleteObject(RectRgn);
    }
    SetMapMode(hdc, iMode[0]);
    SetWorldTransform(hdc, &xf);
    SetWindowOrgEx(hdc, point.x, point.y, 0);
    SetWindowExtEx(hdc, size.cx, size.cy, 0);
    SetViewportExtEx(hdc, v33.cx, v33.cy, 0);
    SetViewportOrgEx(hdc, (int)hMem, SHIDWORD(hMem), 0);
    *(_DWORD *)(v7 + 8) |= 0x20000u;
    v21 = v18 != 0 ? 1 : -1;
  }
  else
  {
    if ( (*(_DWORD *)(v7 + 8) & 0x200000) == 0 )
      goto LABEL_42;
    v22 = *(_QWORD *)(v7 + 112);
    v21 = -1;
    iMode[1] = 0;
    iMode[0] = 3;
    if ( v22 )
      v23 = *(unsigned __int16 *)(v22 + 68) + *(unsigned __int16 *)(v22 + 70);
    else
      v23 = 0;
    iMode[1] = (v23 + 3) & 0xFFFFFFFC;
    if ( (unsigned int)WriteEMFSpoolData(v7, iMode, 8) )
      v6 = WriteEMFSpoolData(v7, *(_QWORD *)(v7 + 112), (unsigned int)iMode[1]) != 0;
    *(_DWORD *)(v7 + 8) &= ~0x200000u;
    if ( v6 )
LABEL_42:
      v21 = 1;
  }
  if ( pfnDeleteEnhMetaFile )
    pfnDeleteEnhMetaFile(v16);
  else
    DeleteEnhMetaFile(v16);
  v24 = *(_QWORD *)(v7 + 128);
  if ( !v24 || !*(_DWORD *)(v24 + 40) )
    goto LABEL_54;
  EMFSpoolData::FreeTempBuffers(*(EMFSpoolData **)(v7 + 128), 0);
  if ( !*(_QWORD *)(v24 + 72) )
  {
    if ( *(_DWORD *)(v24 + 64) )
    {
      EMFSpoolData::UnmapFile((EMFSpoolData *)v24, 0);
    }
    else if ( !(unsigned int)EMFSpoolData::FlushPage((EMFSpoolData *)v24, a2) )
    {
      goto LABEL_54;
    }
    if ( (unsigned int)AssociateEnhMetaFile(hdc) )
      goto LABEL_55;
    goto LABEL_54;
  }
  *(_QWORD *)(v24 + 72) = 0;
  *(_QWORD *)(v24 + 32) = -1;
LABEL_54:
  v21 = -1;
LABEL_55:
  LODWORD(NtCurrentTeb()->Win32ClientInfo[1]) = 0;
  if ( (*(_DWORD *)(v7 + 8) & 0x80000) == 0 )
  {
    v25 = (unsigned int (__fastcall *)(_QWORD))RtlDecodePointer(fpEndPagePrinter);
    if ( !v25(*(_QWORD *)(v7 + 48)) )
      v21 = -1;
  }
  *(_DWORD *)(v7 + 8) |= 0x100u;
  return v21;
}

```

## disassembly

```asm
0x180094054  mov     [rsp-8+arg_10], rbx
0x180094059  push    rbp
0x18009405a  push    rsi
0x18009405b  push    rdi
0x18009405c  push    r12
0x18009405e  push    r13
0x180094060  push    r14
0x180094062  push    r15
0x180094064  lea     rbp, [rsp-27h]
0x180094069  sub     rsp, 0A0h
0x180094070  mov     rax, cs:__security_cookie
0x180094077  xor     rax, rsp
0x18009407a  mov     [rbp+57h+var_40], rax
0x18009407e  mov     eax, ecx
0x180094080  mov     r13d, edx
0x180094083  and     eax, 7F0000h
0x180094088  mov     r14, rcx
0x18009408b  mov     ebx, eax
0x18009408d  cmp     eax, 10000h
0x180094092  jz      loc_180094553
0x180094098  call    cs:__imp_pldcGet
0x18009409e  xor     edi, edi
0x1800940a0  mov     rsi, rax
0x1800940a3  test    rax, rax
0x1800940a6  jz      loc_180094548
0x1800940ac  cmp     ebx, 660000h
0x1800940b2  jz      loc_180094548
0x1800940b8  mov     edx, [rax+8]
0x1800940bb  mov     ecx, edx
0x1800940bd  and     ecx, 10080h
0x1800940c3  cmp     ecx, 80h
0x1800940c9  jnz     loc_180094537
0x1800940cf  bt      edx, 1Dh
0x1800940d3  jb      short loc_1800940E2
0x1800940d5  cmp     r13d, 1
0x1800940d9  mov     eax, edi
0x1800940db  setnz   al
0x1800940de  lea     r13d, [rax+0Ah]
0x1800940e2  btr     edx, 1Dh
0x1800940e6  mov     [rsi+8], edx
0x1800940e9  test    dl, 20h
0x1800940ec  jz      short loc_1800940F6
0x1800940ee  mov     rcx, rsi
0x1800940f1  call    vSAPCallback
0x1800940f6  btr     dword ptr [rsi+8], 7
0x1800940fb  test    dword ptr [rsi+8], 500000h
0x180094102  setnz   cl
0x180094105  bt      dword ptr [rsi+8], 0Eh
0x18009410a  setb    al
0x18009410d  test    al, cl
0x18009410f  jz      loc_1800941FA
0x180094115  mov     [rbp+57h+hMem], rdi
0x180094119  mov     r12d, edi
0x18009411c  mov     [rbp+57h+iMode], edi
0x18009411f  mov     [rbp+57h+var_98.x], edi
0x180094122  cmp     r12d, 20h ; ' '
0x180094126  jnb     loc_1800941FA
0x18009412c  mov     rax, [rsi+68h]
0x180094130  mov     ecx, r12d
0x180094133  mov     r15, [rax+rcx*8]
0x180094137  test    r15, r15
0x18009413a  jz      loc_1800941F2
0x180094140  movzx   ebx, word ptr [r15+10h]
0x180094145  mov     rcx, [r15+8]
0x180094149  mov     qword ptr [rbp+57h+var_88.cx], rcx
0x18009414d  test    bl, 2
0x180094150  jz      short loc_180094171
0x180094152  cmp     [r15+28h], edi
0x180094156  jnz     short loc_180094171
0x180094158  mov     rcx, [r15+30h]; hMem
0x18009415c  test    rcx, rcx
0x18009415f  jz      loc_1800941E9
0x180094165  call    cs:__imp_LocalFree
0x18009416b  mov     [r15+30h], rdi
0x18009416f  jmp     short loc_1800941E9
0x180094171  lea     r9, [rbp+57h+var_98]
0x180094175  mov     rcx, r15
0x180094178  lea     r8, [rbp+57h+iMode]
0x18009417c  lea     rdx, [rbp+57h+hMem]
0x180094180  call    bDoFontSubset
0x180094185  test    eax, eax
0x180094187  jz      short loc_1800941CB
0x180094189  mov     eax, [rbp+57h+var_98.x]
0x18009418c  test    eax, eax
0x18009418e  jz      short loc_1800941CB
0x180094190  mov     rdi, [rbp+57h+hMem]
0x180094194  and     bl, 2
0x180094197  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18009419b  neg     bl
0x18009419d  mov     r9d, 8
0x1800941a3  mov     [rsp+0D0h+var_B0], rdi
0x1800941a8  sbb     edx, edx
0x1800941aa  mov     r8, r15
0x1800941ad  neg     edx
0x1800941af  mov     rcx, rsi
0x1800941b2  add     edx, 7
0x1800941b5  call    WriteFontDataAsEMFComment
0x1800941ba  mov     rcx, rdi; hMem
0x1800941bd  mov     ebx, eax
0x1800941bf  call    cs:__imp_LocalFree
0x1800941c5  xor     edi, edi
0x1800941c7  test    ebx, ebx
0x1800941c9  jnz     short loc_1800941E9
0x1800941cb  movzx   r9d, word ptr [r15+12h]
0x1800941d0  mov     r8d, 1
0x1800941d6  mov     rdx, r15
0x1800941d9  mov     rcx, r14
0x1800941dc  call    bAddUFIandWriteSpool
0x1800941e1  test    eax, eax
0x1800941e3  jz      loc_180094542
0x1800941e9  mov     r15, qword ptr [rbp+57h+var_88.cx]
0x1800941ed  jmp     loc_180094137
0x1800941f2  inc     r12d
0x1800941f5  jmp     loc_180094122
0x1800941fa  mov     edx, 1; int
0x1800941ff  mov     rcx, r14; hdc
0x180094202  call    UnassociateEnhMetaFile
0x180094207  mov     r12, rax
0x18009420a  test    rax, rax
0x18009420d  jz      loc_180094542
0x180094213  test    dword ptr [rsi+8], 80000h
0x18009421a  jz      loc_180094406
0x180094220  xor     eax, eax
0x180094222  mov     qword ptr [rbp+57h+var_98.x], rdi
0x180094226  xorps   xmm0, xmm0
0x180094229  mov     [rbp+57h+hMem], rdi
0x18009422d  mov     rcx, r14; hdc
0x180094230  mov     qword ptr [rbp+57h+point.x], rdi
0x180094234  mov     qword ptr [rbp+57h+size.cx], rdi
0x180094238  lea     edx, [rax+76h]; index
0x18009423b  mov     qword ptr [rbp+57h+var_70.cx], rdi
0x18009423f  mov     qword ptr [rbp+57h+var_88.cx], rdi
0x180094243  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x180094247  mov     qword ptr [rbp+57h+xf.eDx], rax
0x18009424b  mov     qword ptr [rbp+57h+var_68.left], rax
0x18009424f  call    cs:__imp_GetDeviceCaps
0x180094255  mov     edx, 75h ; 'u'; index
0x18009425a  mov     rcx, r14; hdc
0x18009425d  mov     [rbp+57h+var_68.right], eax
0x180094260  call    cs:__imp_GetDeviceCaps
0x180094266  btr     dword ptr [rsi+8], 11h
0x18009426b  lea     r9, [rbp+57h+var_88]
0x18009426f  lea     r8, [rbp+57h+var_98]
0x180094273  mov     [rbp+57h+var_68.bottom], eax
0x180094276  mov     edx, 1
0x18009427b  mov     rcx, r14
0x18009427e  call    cs:__imp_NtGdiDoBanding
0x180094284  lea     rdx, [rbp+57h+hMem]; lppoint
0x180094288  mov     rcx, r14; hdc
0x18009428b  mov     r15d, eax
0x18009428e  call    GetViewportOrgEx
0x180094293  lea     rdx, [rbp+57h+point]; lppoint
0x180094297  mov     rcx, r14; hdc
0x18009429a  call    GetWindowOrgEx
0x18009429f  lea     rdx, [rbp+57h+size]; lpsize
0x1800942a3  mov     rcx, r14; hdc
0x1800942a6  call    GetWindowExtEx
0x1800942ab  lea     rdx, [rbp+57h+var_70]; lpsize
0x1800942af  mov     rcx, r14; hdc
0x1800942b2  call    GetViewportExtEx
0x1800942b7  lea     r8, [rbp+57h+xf]
0x1800942bb  mov     edx, 203h
0x1800942c0  mov     rcx, r14
0x1800942c3  call    cs:__imp_NtGdiGetTransform
0x1800942c9  xor     edx, edx; y1
0x1800942cb  xor     ecx, ecx; x1
0x1800942cd  lea     r9d, [rdx+1]; y2
0x1800942d1  mov     r8d, r9d; x2
0x1800942d4  call    cs:__imp_CreateRectRgn
0x1800942da  mov     rdx, rax; hrgn
0x1800942dd  mov     rcx, r14; hdc
0x1800942e0  mov     rdi, rax
0x1800942e3  call    GetClipRgn
0x1800942e8  test    eax, eax
0x1800942ea  jnz     short loc_1800942F9
0x1800942ec  mov     rcx, rdi; ho
0x1800942ef  call    cs:__imp_DeleteObject
0x1800942f5  xor     edi, edi
0x1800942f7  jmp     short loc_180094304
0x1800942f9  xor     edx, edx; hrgn
0x1800942fb  mov     rcx, r14; hdc
0x1800942fe  call    cs:__imp_SelectClipRgn
0x180094304  mov     edx, 1; iMode
0x180094309  mov     rcx, r14; hdc
0x18009430c  call    SetMapMode
0x180094311  xor     r9d, r9d; lppt
0x180094314  mov     [rbp+57h+iMode], eax
0x180094317  xor     r8d, r8d; y
0x18009431a  xor     edx, edx; x
0x18009431c  mov     rcx, r14; hdc
0x18009431f  call    SetWindowOrgEx
0x180094324  xor     edx, edx; lpxf
0x180094326  mov     rcx, r14; hdc
0x180094329  lea     r8d, [rdx+1]; mode
0x18009432d  call    ModifyWorldTransform
0x180094332  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180094336  test    r15d, r15d
0x180094339  jz      short loc_180094378
0x18009433b  lea     rax, [rbp+57h+var_88]
0x18009433f  mov     [rsp+0D0h+var_A8], 0; struct tagRECT *
0x180094348  lea     r9, [rbp+57h+var_68]; struct tagRECT *
0x18009434c  mov     [rsp+0D0h+var_B0], rax; struct tagSIZE *
0x180094351  lea     r8, [rbp+57h+var_98]; struct _POINTL *
0x180094355  mov     rdx, r12; HENHMETAFILE
0x180094358  mov     rcx, r14; hdc
0x18009435b  call    ?PrintBand@@YAXPEAUHDC__@@PEAUHENHMETAFILE__@@PEAU_POINTL@@PEAUtagRECT@@PEAUtagSIZE@@3@Z; PrintBand(HDC__ *,HENHMETAFILE__ *,_POINTL *,tagRECT *,tagSIZE *,tagRECT *)
0x180094360  lea     rdx, [rbp+57h+var_98]; struct _POINTL *
0x180094364  mov     rcx, r14; HDC
0x180094367  call    ?NextBand@@YAHPEAUHDC__@@PEAU_POINTL@@@Z; NextBand(HDC__ *,_POINTL *)
0x18009436c  mov     r15d, eax
0x18009436f  cmp     [rbp+57h+var_98.x], ebx
0x180094372  jz      short loc_180094378
0x180094374  test    eax, eax
0x180094376  jnz     short loc_18009433B
0x180094378  test    rdi, rdi
0x18009437b  jz      short loc_180094392
0x18009437d  mov     rdx, rdi; hrgn
0x180094380  mov     rcx, r14; hdc
0x180094383  call    cs:__imp_SelectClipRgn
0x180094389  mov     rcx, rdi; ho
0x18009438c  call    cs:__imp_DeleteObject
0x180094392  mov     edx, [rbp+57h+iMode]; iMode
0x180094395  mov     rcx, r14; hdc
0x180094398  call    SetMapMode
0x18009439d  lea     rdx, [rbp+57h+xf]; lpxf
0x1800943a1  mov     rcx, r14; hdc
0x1800943a4  call    cs:__imp_SetWorldTransform
0x1800943aa  mov     r8d, [rbp+57h+point.y]; y
0x1800943ae  xor     r9d, r9d; lppt
0x1800943b1  mov     edx, [rbp+57h+point.x]; x
0x1800943b4  mov     rcx, r14; hdc
0x1800943b7  call    SetWindowOrgEx
0x1800943bc  mov     r8d, [rbp+57h+size.cy]; y
0x1800943c0  xor     r9d, r9d; lpsz
0x1800943c3  mov     edx, [rbp+57h+size.cx]; x
0x1800943c6  mov     rcx, r14; hdc
0x1800943c9  call    SetWindowExtEx
0x1800943ce  mov     r8d, [rbp+57h+var_70.cy]; y
0x1800943d2  xor     r9d, r9d; lpsz
0x1800943d5  mov     edx, [rbp+57h+var_70.cx]; x
0x1800943d8  mov     rcx, r14; hdc
0x1800943db  call    SetViewportExtEx
0x1800943e0  mov     r8d, dword ptr [rbp+57h+hMem+4]; y
0x1800943e4  xor     r9d, r9d; lppt
0x1800943e7  mov     edx, dword ptr [rbp+57h+hMem]; x
0x1800943ea  mov     rcx, r14; hdc
0x1800943ed  call    SetViewportOrgEx
0x1800943f2  bts     dword ptr [rsi+8], 11h
0x1800943f7  neg     r15d
0x1800943fa  sbb     r15d, r15d
0x1800943fd  and     r15d, 2
0x180094401  add     r15d, ebx
0x180094404  jmp     short loc_180094481
0x180094406  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009440a  test    dword ptr [rsi+8], 200000h
0x180094411  jz      short loc_18009447B
0x180094413  mov     rax, [rsi+70h]
0x180094417  mov     r15d, ebx
0x18009441a  mov     qword ptr [rbp+57h+iMode], rdi
0x18009441e  mov     [rbp+57h+iMode], 3
0x180094425  test    rax, rax
0x180094428  jz      short loc_180094436
0x18009442a  movzx   ecx, word ptr [rax+46h]
0x18009442e  movzx   eax, word ptr [rax+44h]
0x180094432  add     ecx, eax
0x180094434  jmp     short loc_180094438
0x180094436  mov     ecx, edi
0x180094438  lea     eax, [rcx+3]
0x18009443b  mov     r8d, 8
0x180094441  and     eax, 0FFFFFFFCh
0x180094444  lea     rdx, [rbp+57h+iMode]
0x180094448  mov     rcx, rsi
0x18009444b  mov     [rbp+57h+iMode+4], eax
0x18009444e  call    WriteEMFSpoolData
0x180094453  test    eax, eax
0x180094455  jz      short loc_180094472
0x180094457  mov     r8d, [rbp+57h+iMode+4]
0x18009445b  mov     rcx, rsi
0x18009445e  mov     rdx, [rsi+70h]
0x180094462  mov     edi, 1
0x180094467  call    WriteEMFSpoolData
0x18009446c  test    eax, eax
0x18009446e  jnz     short loc_180094472
0x180094470  xor     edi, edi
0x180094472  btr     dword ptr [rsi+8], 15h
0x180094477  test    edi, edi
0x180094479  jz      short loc_180094481
0x18009447b  mov     r15d, 1
0x180094481  mov     rax, cs:pfnDeleteEnhMetaFile
0x180094488  mov     rcx, r12; hmf
0x18009448b  test    rax, rax
0x18009448e  jz      short loc_180094497
0x180094490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094495  jmp     short loc_18009449C
0x180094497  call    DeleteEnhMetaFile
0x18009449c  mov     rdi, [rsi+80h]
0x1800944a3  xor     r12d, r12d
0x1800944a6  test    rdi, rdi
0x1800944a9  jz      short loc_1800944F5
0x1800944ab  cmp     [rdi+28h], r12d
  ... truncated ...
```
