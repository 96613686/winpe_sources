# MFP_InternalEndPage(HDC__ *,ulong)

- ea: `0x180099e04`
- end: `0x18009a38d`
- name: `?MFP_InternalEndPage@@YAHPEAUHDC__@@K@Z`
- size: `1417`
- prototype: `__int64 __fastcall(HDC hdc, unsigned int)`
- caller_count: `2`
- callee_count: `27`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180072008`
- `0x18009ace0`

## callees

- `0x180018720`
- `0x180018940`
- `0x180018a20`
- `0x180018c30`
- `0x180018df0`
- `0x180018f00`
- `0x180018fe0`
- `0x1800190c0`
- `0x180019310`
- `0x18002bea8`
- `0x180033420`
- `0x180047380`
- `0x180052060`
- `0x1800521b8`
- `0x180056bbc`
- `0x180057410`
- `0x18006e3c8`
- `0x18006f754`
- `0x180070a98`
- `0x18007dd58`
- `0x18007e4b4`
- `0x18007f800`
- `0x1800850c8`
- `0x180085150`
- `0x1800937e8`
- `0x180099e04`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099f1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099f7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099f1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099f7b`
- `GDI32!CreateRectRgn` at `0x18009a0ae`
- `GDI32!CreateRectRgn` at `0x18009a0ae`
- `GDI32!GetDeviceCaps` at `0x18009a011`
- `GDI32!GetDeviceCaps` at `0x18009a028`
- `GDI32!GetDeviceCaps` at `0x18009a011`
- `GDI32!GetDeviceCaps` at `0x18009a028`
- `GDI32!SelectClipRgn` at `0x18009a0e4`
- `GDI32!SelectClipRgn` at `0x18009a16f`
- `GDI32!SelectClipRgn` at `0x18009a0e4`
- `GDI32!SelectClipRgn` at `0x18009a16f`
- `GDI32!SetWorldTransform` at `0x18009a19c`
- `GDI32!SetWorldTransform` at `0x18009a19c`
- `GDI32!pldcGet` at `0x180099e48`
- `GDI32!pldcGet` at `0x180099e48`
- `GDI32!GdiSetLastError` at `0x18009a340`
- `GDI32!GdiSetLastError` at `0x18009a357`
- `GDI32!GdiSetLastError` at `0x18009a340`
- `GDI32!GdiSetLastError` at `0x18009a357`
- `GDI32!DeleteObject` at `0x18009a0cf`
- `GDI32!DeleteObject` at `0x18009a17e`
- `GDI32!DeleteObject` at `0x18009a0cf`
- `GDI32!DeleteObject` at `0x18009a17e`
- `ntdll!RtlDecodePointer` at `0x18009a316`
- `ntdll!RtlDecodePointer` at `0x18009a316`
- `win32u!NtGdiDoBanding` at `0x18009a04c`
- `win32u!NtGdiDoBanding` at `0x18009a04c`
- `win32u!NtGdiGetTransform` at `0x18009a097`
- `win32u!NtGdiGetTransform` at `0x18009a097`

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
0x180099e04  mov     [rsp-8+arg_10], rbx
0x180099e09  push    rbp
0x180099e0a  push    rsi
0x180099e0b  push    rdi
0x180099e0c  push    r12
0x180099e0e  push    r13
0x180099e10  push    r14
0x180099e12  push    r15
0x180099e14  lea     rbp, [rsp-27h]
0x180099e19  sub     rsp, 0A0h
0x180099e20  mov     rax, cs:__security_cookie
0x180099e27  xor     rax, rsp
0x180099e2a  mov     [rbp+57h+var_40], rax
0x180099e2e  mov     eax, ecx
0x180099e30  mov     r13d, edx
0x180099e33  and     eax, 7F0000h
0x180099e38  mov     r14, rcx
0x180099e3b  mov     ebx, eax
0x180099e3d  cmp     eax, 10000h
0x180099e42  jz      loc_18009A363
0x180099e48  call    cs:__imp_pldcGet
0x180099e4f  nop     dword ptr [rax+rax+00h]
0x180099e54  xor     edi, edi
0x180099e56  mov     rsi, rax
0x180099e59  test    rax, rax
0x180099e5c  jz      loc_18009A352
0x180099e62  cmp     ebx, 660000h
0x180099e68  jz      loc_18009A352
0x180099e6e  mov     edx, [rax+8]
0x180099e71  mov     ecx, edx
0x180099e73  and     ecx, 10080h
0x180099e79  cmp     ecx, 80h
0x180099e7f  jnz     loc_18009A33B
0x180099e85  bt      edx, 1Dh
0x180099e89  jb      short loc_180099E98
0x180099e8b  cmp     r13d, 1
0x180099e8f  mov     eax, edi
0x180099e91  setnz   al
0x180099e94  lea     r13d, [rax+0Ah]
0x180099e98  btr     edx, 1Dh
0x180099e9c  mov     [rsi+8], edx
0x180099e9f  test    dl, 20h
0x180099ea2  jz      short loc_180099EAC
0x180099ea4  mov     rcx, rsi
0x180099ea7  call    vSAPCallback
0x180099eac  btr     dword ptr [rsi+8], 7
0x180099eb1  test    dword ptr [rsi+8], 500000h
0x180099eb8  setnz   cl
0x180099ebb  bt      dword ptr [rsi+8], 0Eh
0x180099ec0  setb    al
0x180099ec3  test    al, cl
0x180099ec5  jz      loc_180099FBC
0x180099ecb  mov     [rbp+57h+hMem], rdi
0x180099ecf  mov     r12d, edi
0x180099ed2  mov     [rbp+57h+iMode], edi
0x180099ed5  mov     [rbp+57h+var_98.x], edi
0x180099ed8  cmp     r12d, 20h ; ' '
0x180099edc  jnb     loc_180099FBC
0x180099ee2  mov     rax, [rsi+68h]
0x180099ee6  mov     ecx, r12d
0x180099ee9  mov     r15, [rax+rcx*8]
0x180099eed  test    r15, r15
0x180099ef0  jz      loc_180099FB4
0x180099ef6  movzx   ebx, word ptr [r15+10h]
0x180099efb  mov     rcx, [r15+8]
0x180099eff  mov     qword ptr [rbp+57h+var_88.cx], rcx
0x180099f03  test    bl, 2
0x180099f06  jz      short loc_180099F2D
0x180099f08  cmp     [r15+28h], edi
0x180099f0c  jnz     short loc_180099F2D
0x180099f0e  mov     rcx, [r15+30h]; hMem
0x180099f12  test    rcx, rcx
0x180099f15  jz      loc_180099FAB
0x180099f1b  call    cs:__imp_LocalFree
0x180099f22  nop     dword ptr [rax+rax+00h]
0x180099f27  mov     [r15+30h], rdi
0x180099f2b  jmp     short loc_180099FAB
0x180099f2d  lea     r9, [rbp+57h+var_98]
0x180099f31  mov     rcx, r15
0x180099f34  lea     r8, [rbp+57h+iMode]
0x180099f38  lea     rdx, [rbp+57h+hMem]
0x180099f3c  call    bDoFontSubset
0x180099f41  test    eax, eax
0x180099f43  jz      short loc_180099F8D
0x180099f45  mov     eax, [rbp+57h+var_98.x]
0x180099f48  test    eax, eax
0x180099f4a  jz      short loc_180099F8D
0x180099f4c  mov     rdi, [rbp+57h+hMem]
0x180099f50  and     bl, 2
0x180099f53  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180099f57  neg     bl
0x180099f59  mov     r9d, 8
0x180099f5f  mov     [rsp+0D0h+var_B0], rdi
0x180099f64  sbb     edx, edx
0x180099f66  mov     r8, r15
0x180099f69  neg     edx
0x180099f6b  mov     rcx, rsi
0x180099f6e  add     edx, 7
0x180099f71  call    WriteFontDataAsEMFComment
0x180099f76  mov     rcx, rdi; hMem
0x180099f79  mov     ebx, eax
0x180099f7b  call    cs:__imp_LocalFree
0x180099f82  nop     dword ptr [rax+rax+00h]
0x180099f87  xor     edi, edi
0x180099f89  test    ebx, ebx
0x180099f8b  jnz     short loc_180099FAB
0x180099f8d  movzx   r9d, word ptr [r15+12h]
0x180099f92  mov     r8d, 1
0x180099f98  mov     rdx, r15
0x180099f9b  mov     rcx, r14
0x180099f9e  call    bAddUFIandWriteSpool
0x180099fa3  test    eax, eax
0x180099fa5  jz      loc_18009A34C
0x180099fab  mov     r15, qword ptr [rbp+57h+var_88.cx]
0x180099faf  jmp     loc_180099EED
0x180099fb4  inc     r12d
0x180099fb7  jmp     loc_180099ED8
0x180099fbc  mov     edx, 1; int
0x180099fc1  mov     rcx, r14; hdc
0x180099fc4  call    UnassociateEnhMetaFile
0x180099fc9  mov     r12, rax
0x180099fcc  test    rax, rax
0x180099fcf  jz      loc_18009A34C
0x180099fd5  test    dword ptr [rsi+8], 80000h
0x180099fdc  jz      loc_18009A204
0x180099fe2  xor     eax, eax
0x180099fe4  mov     qword ptr [rbp+57h+var_98.x], rdi
0x180099fe8  xorps   xmm0, xmm0
0x180099feb  mov     [rbp+57h+hMem], rdi
0x180099fef  mov     rcx, r14; hdc
0x180099ff2  mov     qword ptr [rbp+57h+point.x], rdi
0x180099ff6  mov     qword ptr [rbp+57h+size.cx], rdi
0x180099ffa  lea     edx, [rax+76h]; index
0x180099ffd  mov     qword ptr [rbp+57h+var_70.cx], rdi
0x18009a001  mov     qword ptr [rbp+57h+var_88.cx], rdi
0x18009a005  movups  xmmword ptr [rbp+57h+xf.eM11], xmm0
0x18009a009  mov     qword ptr [rbp+57h+xf.eDx], rax
0x18009a00d  mov     qword ptr [rbp+57h+var_68.left], rax
0x18009a011  call    cs:__imp_GetDeviceCaps
0x18009a018  nop     dword ptr [rax+rax+00h]
0x18009a01d  mov     edx, 75h ; 'u'; index
0x18009a022  mov     rcx, r14; hdc
0x18009a025  mov     [rbp+57h+var_68.right], eax
0x18009a028  call    cs:__imp_GetDeviceCaps
0x18009a02f  nop     dword ptr [rax+rax+00h]
0x18009a034  btr     dword ptr [rsi+8], 11h
0x18009a039  lea     r9, [rbp+57h+var_88]
0x18009a03d  lea     r8, [rbp+57h+var_98]
0x18009a041  mov     [rbp+57h+var_68.bottom], eax
0x18009a044  mov     edx, 1
0x18009a049  mov     rcx, r14
0x18009a04c  call    cs:__imp_NtGdiDoBanding
0x18009a053  nop     dword ptr [rax+rax+00h]
0x18009a058  lea     rdx, [rbp+57h+hMem]; lppoint
0x18009a05c  mov     rcx, r14; hdc
0x18009a05f  mov     r15d, eax
0x18009a062  call    GetViewportOrgEx
0x18009a067  lea     rdx, [rbp+57h+point]; lppoint
0x18009a06b  mov     rcx, r14; hdc
0x18009a06e  call    GetWindowOrgEx
0x18009a073  lea     rdx, [rbp+57h+size]; lpsize
0x18009a077  mov     rcx, r14; hdc
0x18009a07a  call    GetWindowExtEx
0x18009a07f  lea     rdx, [rbp+57h+var_70]; lpsize
0x18009a083  mov     rcx, r14; hdc
0x18009a086  call    GetViewportExtEx
0x18009a08b  lea     r8, [rbp+57h+xf]
0x18009a08f  mov     edx, 203h
0x18009a094  mov     rcx, r14
0x18009a097  call    cs:__imp_NtGdiGetTransform
0x18009a09e  nop     dword ptr [rax+rax+00h]
0x18009a0a3  xor     edx, edx; y1
0x18009a0a5  xor     ecx, ecx; x1
0x18009a0a7  lea     r9d, [rdx+1]; y2
0x18009a0ab  mov     r8d, r9d; x2
0x18009a0ae  call    cs:__imp_CreateRectRgn
0x18009a0b5  nop     dword ptr [rax+rax+00h]
0x18009a0ba  mov     rdx, rax; hrgn
0x18009a0bd  mov     rcx, r14; hdc
0x18009a0c0  mov     rdi, rax
0x18009a0c3  call    GetClipRgn
0x18009a0c8  test    eax, eax
0x18009a0ca  jnz     short loc_18009A0DF
0x18009a0cc  mov     rcx, rdi; ho
0x18009a0cf  call    cs:__imp_DeleteObject
0x18009a0d6  nop     dword ptr [rax+rax+00h]
0x18009a0db  xor     edi, edi
0x18009a0dd  jmp     short loc_18009A0F0
0x18009a0df  xor     edx, edx; hrgn
0x18009a0e1  mov     rcx, r14; hdc
0x18009a0e4  call    cs:__imp_SelectClipRgn
0x18009a0eb  nop     dword ptr [rax+rax+00h]
0x18009a0f0  mov     edx, 1; iMode
0x18009a0f5  mov     rcx, r14; hdc
0x18009a0f8  call    SetMapMode
0x18009a0fd  xor     r9d, r9d; lppt
0x18009a100  mov     [rbp+57h+iMode], eax
0x18009a103  xor     r8d, r8d; y
0x18009a106  xor     edx, edx; x
0x18009a108  mov     rcx, r14; hdc
0x18009a10b  call    SetWindowOrgEx
0x18009a110  xor     edx, edx; lpxf
0x18009a112  mov     rcx, r14; hdc
0x18009a115  lea     r8d, [rdx+1]; mode
0x18009a119  call    ModifyWorldTransform
0x18009a11e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009a122  test    r15d, r15d
0x18009a125  jz      short loc_18009A164
0x18009a127  lea     rax, [rbp+57h+var_88]
0x18009a12b  mov     [rsp+0D0h+var_A8], 0; struct tagRECT *
0x18009a134  lea     r9, [rbp+57h+var_68]; struct tagRECT *
0x18009a138  mov     [rsp+0D0h+var_B0], rax; struct tagSIZE *
0x18009a13d  lea     r8, [rbp+57h+var_98]; struct _POINTL *
0x18009a141  mov     rdx, r12; HENHMETAFILE
0x18009a144  mov     rcx, r14; hdc
0x18009a147  call    ?PrintBand@@YAXPEAUHDC__@@PEAUHENHMETAFILE__@@PEAU_POINTL@@PEAUtagRECT@@PEAUtagSIZE@@3@Z; PrintBand(HDC__ *,HENHMETAFILE__ *,_POINTL *,tagRECT *,tagSIZE *,tagRECT *)
0x18009a14c  lea     rdx, [rbp+57h+var_98]; struct _POINTL *
0x18009a150  mov     rcx, r14; HDC
0x18009a153  call    ?NextBand@@YAHPEAUHDC__@@PEAU_POINTL@@@Z; NextBand(HDC__ *,_POINTL *)
0x18009a158  mov     r15d, eax
0x18009a15b  cmp     [rbp+57h+var_98.x], ebx
0x18009a15e  jz      short loc_18009A164
0x18009a160  test    eax, eax
0x18009a162  jnz     short loc_18009A127
0x18009a164  test    rdi, rdi
0x18009a167  jz      short loc_18009A18A
0x18009a169  mov     rdx, rdi; hrgn
0x18009a16c  mov     rcx, r14; hdc
0x18009a16f  call    cs:__imp_SelectClipRgn
0x18009a176  nop     dword ptr [rax+rax+00h]
0x18009a17b  mov     rcx, rdi; ho
0x18009a17e  call    cs:__imp_DeleteObject
0x18009a185  nop     dword ptr [rax+rax+00h]
0x18009a18a  mov     edx, [rbp+57h+iMode]; iMode
0x18009a18d  mov     rcx, r14; hdc
0x18009a190  call    SetMapMode
0x18009a195  lea     rdx, [rbp+57h+xf]; lpxf
0x18009a199  mov     rcx, r14; hdc
0x18009a19c  call    cs:__imp_SetWorldTransform
0x18009a1a3  nop     dword ptr [rax+rax+00h]
0x18009a1a8  mov     r8d, [rbp+57h+point.y]; y
0x18009a1ac  xor     r9d, r9d; lppt
0x18009a1af  mov     edx, [rbp+57h+point.x]; x
0x18009a1b2  mov     rcx, r14; hdc
0x18009a1b5  call    SetWindowOrgEx
0x18009a1ba  mov     r8d, [rbp+57h+size.cy]; y
0x18009a1be  xor     r9d, r9d; lpsz
0x18009a1c1  mov     edx, [rbp+57h+size.cx]; x
0x18009a1c4  mov     rcx, r14; hdc
0x18009a1c7  call    SetWindowExtEx
0x18009a1cc  mov     r8d, [rbp+57h+var_70.cy]; y
0x18009a1d0  xor     r9d, r9d; lpsz
0x18009a1d3  mov     edx, [rbp+57h+var_70.cx]; x
0x18009a1d6  mov     rcx, r14; hdc
0x18009a1d9  call    SetViewportExtEx
0x18009a1de  mov     r8d, dword ptr [rbp+57h+hMem+4]; y
0x18009a1e2  xor     r9d, r9d; lppt
0x18009a1e5  mov     edx, dword ptr [rbp+57h+hMem]; x
0x18009a1e8  mov     rcx, r14; hdc
0x18009a1eb  call    SetViewportOrgEx
0x18009a1f0  bts     dword ptr [rsi+8], 11h
0x18009a1f5  neg     r15d
0x18009a1f8  sbb     r15d, r15d
0x18009a1fb  and     r15d, 2
0x18009a1ff  add     r15d, ebx
0x18009a202  jmp     short loc_18009A27F
0x18009a204  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18009a208  test    dword ptr [rsi+8], 200000h
0x18009a20f  jz      short loc_18009A279
0x18009a211  mov     rax, [rsi+70h]
0x18009a215  mov     r15d, ebx
0x18009a218  mov     qword ptr [rbp+57h+iMode], rdi
0x18009a21c  mov     [rbp+57h+iMode], 3
0x18009a223  test    rax, rax
0x18009a226  jz      short loc_18009A234
0x18009a228  movzx   ecx, word ptr [rax+46h]
0x18009a22c  movzx   eax, word ptr [rax+44h]
0x18009a230  add     ecx, eax
0x18009a232  jmp     short loc_18009A236
0x18009a234  mov     ecx, edi
0x18009a236  lea     eax, [rcx+3]
0x18009a239  mov     r8d, 8
0x18009a23f  and     eax, 0FFFFFFFCh
0x18009a242  lea     rdx, [rbp+57h+iMode]
0x18009a246  mov     rcx, rsi
0x18009a249  mov     [rbp+57h+iMode+4], eax
0x18009a24c  call    WriteEMFSpoolData
0x18009a251  test    eax, eax
0x18009a253  jz      short loc_18009A270
0x18009a255  mov     r8d, [rbp+57h+iMode+4]
0x18009a259  mov     rcx, rsi
0x18009a25c  mov     rdx, [rsi+70h]
0x18009a260  mov     edi, 1
0x18009a265  call    WriteEMFSpoolData
0x18009a26a  test    eax, eax
0x18009a26c  jnz     short loc_18009A270
0x18009a26e  xor     edi, edi
0x18009a270  btr     dword ptr [rsi+8], 15h
0x18009a275  test    edi, edi
0x18009a277  jz      short loc_18009A27F
  ... truncated ...
```
