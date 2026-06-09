# AfxLoadSysColorBitmap(HINSTANCE__ *,HRSRC__ *,int)

- ea: `0x1801e3d40`
- end: `0x1801e3f44`
- name: `?AfxLoadSysColorBitmap@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@PEAUHRSRC__@@H@Z`
- size: `516`
- prototype: `HBITMAP__ *__fastcall(HINSTANCE__ *hInst, HRSRC__ *hRsrc, int bMono)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1801e4690`
- `0x1801e61d0`

## callees

- `0x1801e3d40`

## import_xrefs

- `KERNEL32!LockResource` at `0x1801e3d6e`
- `KERNEL32!LockResource` at `0x1801e3d6e`
- `KERNEL32!LoadResource` at `0x1801e3d5c`
- `KERNEL32!LoadResource` at `0x1801e3d5c`
- `VCRUNTIME140!memcpy` at `0x1801e3db4`
- `VCRUNTIME140!memcpy` at `0x1801e3db4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801e3f1f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801e3f1f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801e3d94`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1801e3d94`
- `USER32!GetSysColor` at `0x1801e3e01`
- `USER32!GetSysColor` at `0x1801e3e15`
- `USER32!GetSysColor` at `0x1801e3e2f`
- `USER32!GetSysColor` at `0x1801e3e01`
- `USER32!GetSysColor` at `0x1801e3e15`
- `USER32!GetSysColor` at `0x1801e3e2f`
- `USER32!GetDC` at `0x1801e3e6c`
- `USER32!GetDC` at `0x1801e3e6c`
- `USER32!ReleaseDC` at `0x1801e3f16`
- `USER32!ReleaseDC` at `0x1801e3f16`
- `GDI32!StretchDIBits` at `0x1801e3ef6`
- `GDI32!StretchDIBits` at `0x1801e3ef6`
- `GDI32!DeleteDC` at `0x1801e3f0b`
- `GDI32!DeleteDC` at `0x1801e3f0b`
- `GDI32!CreateCompatibleBitmap` at `0x1801e3e7e`
- `GDI32!CreateCompatibleBitmap` at `0x1801e3e7e`
- `GDI32!SelectObject` at `0x1801e3ea2`
- `GDI32!SelectObject` at `0x1801e3f02`
- `GDI32!SelectObject` at `0x1801e3ea2`
- `GDI32!SelectObject` at `0x1801e3f02`
- `GDI32!CreateCompatibleDC` at `0x1801e3e93`
- `GDI32!CreateCompatibleDC` at `0x1801e3e93`

## pseudocode

```c
HBITMAP __fastcall AfxLoadSysColorBitmap(HMODULE hInst, HRSRC hRsrc, int bMono)
{
  int v3; // edi
  HGLOBAL Resource; // rax
  char *v5; // rax
  char *v6; // r14
  size_t v7; // rbx
  unsigned int *v8; // rax
  unsigned int *lpbmi; // rsi
  char *v10; // r15
  __int64 i; // rbp
  unsigned int v12; // eax
  __int64 v13; // r12
  int iSysColorTo; // ecx
  DWORD v15; // edi
  int v16; // ebx
  int v17; // ebx
  int SrcWidth; // r12d
  HDC DC; // rbp
  HBITMAP CompatibleBitmap; // r15
  HDC CompatibleDC; // rdi
  HGDIOBJ v22; // rbx
  int DestHeight; // [rsp+C8h] [rbp+20h]

  v3 = bMono;
  Resource = LoadResource(hInst, hRsrc);
  if ( !Resource )
    return 0;
  v5 = (char *)LockResource(Resource);
  v6 = v5;
  if ( !v5 )
    return 0;
  if ( *((_WORD *)v5 + 7) > 8u )
    return 0;
  v7 = (unsigned int)(*(_DWORD *)v5 + 64);
  v8 = (unsigned int *)malloc(v7);
  lpbmi = v8;
  if ( !v8 )
    return 0;
  if ( v7 )
    memcpy(v8, v6, (unsigned int)v7);
  v10 = (char *)lpbmi + *lpbmi;
  for ( i = 0; i < 16; ++i )
  {
    v12 = 0;
    v13 = 0;
    while ( *(_DWORD *)&v10[4 * i] != _afxSysColorMap[v13].rgbqFrom )
    {
      ++v12;
      ++v13;
      if ( v12 >= 4 )
        goto LABEL_16;
    }
    iSysColorTo = _afxSysColorMap[v13].iSysColorTo;
    if ( v3 )
    {
      if ( iSysColorTo != 18 )
        *(_DWORD *)&v10[4 * i] = 0xFFFFFF;
    }
    else
    {
      v15 = GetSysColor(iSysColorTo) & 0xFF00;
      v16 = v15 | (unsigned __int8)(GetSysColor(_afxSysColorMap[v13].iSysColorTo) >> 16);
      v3 = bMono;
      *(_DWORD *)&v10[4 * i] = v16 | ((unsigned __int8)GetSysColor(_afxSysColorMap[v13].iSysColorTo) << 16);
    }
LABEL_16:
    ;
  }
  v17 = lpbmi[2];
  SrcWidth = lpbmi[1];
  DestHeight = v17;
  DC = GetDC(0);
  CompatibleBitmap = CreateCompatibleBitmap(DC, SrcWidth, v17);
  if ( CompatibleBitmap )
  {
    CompatibleDC = CreateCompatibleDC(DC);
    v22 = SelectObject(CompatibleDC, CompatibleBitmap);
    StretchDIBits(
      CompatibleDC,
      0,
      0,
      SrcWidth,
      DestHeight,
      0,
      0,
      SrcWidth,
      DestHeight,
      &v6[4 * (1LL << *((_BYTE *)lpbmi + 14)) + 40],
      (const BITMAPINFO *)lpbmi,
      0,
      0xCC0020u);
    SelectObject(CompatibleDC, v22);
    DeleteDC(CompatibleDC);
  }
  ReleaseDC(0, DC);
  free(lpbmi);
  return CompatibleBitmap;
}

```

## disassembly

```asm
0x1801e3d40  mov     [rsp+arg_0], rbx
0x1801e3d45  mov     [rsp+arg_10], bMono
0x1801e3d4a  push    rbp
0x1801e3d4b  push    rsi
0x1801e3d4c  push    rdi
0x1801e3d4d  push    r12
0x1801e3d4f  push    r13
0x1801e3d51  push    r14
0x1801e3d53  push    r15
0x1801e3d55  sub     rsp, 70h
0x1801e3d59  mov     edi, bMono
0x1801e3d5c  call    cs:__imp_LoadResource
0x1801e3d62  test    rax, rax
0x1801e3d65  jz      loc_1801E3F2A
0x1801e3d6b  mov     hInst, rax; hResData
0x1801e3d6e  call    cs:__imp_LockResource
0x1801e3d74  mov     r14, rax
0x1801e3d77  test    rax, rax
0x1801e3d7a  jz      loc_1801E3F2A
0x1801e3d80  cmp     word ptr [rax+0Eh], 8
0x1801e3d85  ja      loc_1801E3F2A
0x1801e3d8b  mov     eax, [rax]
0x1801e3d8d  add     eax, 40h ; '@'
0x1801e3d90  mov     ecx, eax; Size
0x1801e3d92  mov     ebx, eax
0x1801e3d94  call    cs:__imp_malloc
0x1801e3d9a  mov     rsi, rax
0x1801e3d9d  test    rax, rax
0x1801e3da0  jz      loc_1801E3F2A
0x1801e3da6  test    rbx, rbx
0x1801e3da9  jz      short loc_1801E3DBA
0x1801e3dab  mov     bMono, ebx; Size
0x1801e3dae  mov     hRsrc, r14; Src
0x1801e3db1  mov     hInst, rax; void *
0x1801e3db4  call    cs:__imp_memcpy
0x1801e3dba  mov     r15d, [rsi]
0x1801e3dbd  lea     rbx, ?_afxSysColorMap@@3QBUAFX_COLORMAP@@B; AFX_COLORMAP const near * const _afxSysColorMap
0x1801e3dc4  add     r15, rsi
0x1801e3dc7  xor     ebp, ebp
0x1801e3dc9  lea     r13d, [rbp+1]
0x1801e3dcd  mov     ecx, [r15+rbp*4]
0x1801e3dd1  xor     eax, eax
0x1801e3dd3  xor     r12d, r12d
0x1801e3dd6  cmp     ecx, [rbx+r12*8]
0x1801e3dda  jz      short loc_1801E3DE9
0x1801e3ddc  add     eax, r13d
0x1801e3ddf  add     r12, r13
0x1801e3de2  cmp     eax, 4
0x1801e3de5  jb      short loc_1801E3DD6
0x1801e3de7  jmp     short loc_1801E3E4F
0x1801e3de9  mov     ecx, [rbx+r12*8+4]; nIndex
0x1801e3dee  test    edi, edi
0x1801e3df0  jz      short loc_1801E3E01
0x1801e3df2  cmp     ecx, 12h
0x1801e3df5  jz      short loc_1801E3E4F
0x1801e3df7  mov     dword ptr [r15+rbp*4], 0FFFFFFh
0x1801e3dff  jmp     short loc_1801E3E4F
0x1801e3e01  call    cs:__imp_GetSysColor
0x1801e3e07  mov     ecx, [rbx+r12*8+4]; nIndex
0x1801e3e0c  movzx   edi, ax
0x1801e3e0f  and     edi, 0FFFFFF00h
0x1801e3e15  call    cs:__imp_GetSysColor
0x1801e3e1b  shr     eax, 10h
0x1801e3e1e  lea     hInst, ?_afxSysColorMap@@3QBUAFX_COLORMAP@@B; AFX_COLORMAP const near * const _afxSysColorMap
0x1801e3e25  mov     ecx, [hInst+r12*8+4]; nIndex
0x1801e3e2a  movzx   ebx, al
0x1801e3e2d  or      ebx, edi
0x1801e3e2f  call    cs:__imp_GetSysColor
0x1801e3e35  mov     edi, [rsp+0A8h+arg_10]
0x1801e3e3c  movzx   ecx, al
0x1801e3e3f  shl     ecx, 10h
0x1801e3e42  or      ecx, ebx
0x1801e3e44  lea     rbx, ?_afxSysColorMap@@3QBUAFX_COLORMAP@@B; AFX_COLORMAP const near * const _afxSysColorMap
0x1801e3e4b  mov     [r15+rbp*4], ecx
0x1801e3e4f  add     rbp, r13
0x1801e3e52  cmp     rbp, 10h
0x1801e3e56  jl      loc_1801E3DCD
0x1801e3e5c  mov     ebx, [rsi+8]
0x1801e3e5f  xor     ecx, ecx; hWnd
0x1801e3e61  mov     r12d, [rsi+4]
0x1801e3e65  mov     [rsp+0A8h+arg_18], ebx
0x1801e3e6c  call    cs:__imp_GetDC
0x1801e3e72  mov     bMono, ebx; cy
0x1801e3e75  mov     edx, r12d; cx
0x1801e3e78  mov     hInst, rax; hdc
0x1801e3e7b  mov     rbp, rax
0x1801e3e7e  call    cs:__imp_CreateCompatibleBitmap
0x1801e3e84  mov     r15, rax
0x1801e3e87  test    rax, rax
0x1801e3e8a  jz      loc_1801E3F11
0x1801e3e90  mov     hInst, rbp; hdc
0x1801e3e93  call    cs:__imp_CreateCompatibleDC
0x1801e3e99  mov     hInst, rax; hdc
0x1801e3e9c  mov     hRsrc, r15; h
0x1801e3e9f  mov     rdi, rax
0x1801e3ea2  call    cs:__imp_SelectObject
0x1801e3ea8  mov     cl, [rsi+0Eh]
0x1801e3eab  xor     edx, edx; xDest
0x1801e3ead  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x1801e3eb5  mov     rbx, rax
0x1801e3eb8  mov     eax, [rsp+0A8h+arg_18]
0x1801e3ebf  mov     r9d, r12d; DestWidth
0x1801e3ec2  mov     [rsp+0A8h+iUsage], edx; iUsage
0x1801e3ec6  xor     bMono, bMono; yDest
0x1801e3ec9  mov     [rsp+0A8h+lpbmi], rsi; lpbmi
0x1801e3ece  shl     r13, cl
0x1801e3ed1  lea     hInst, [r13+0Ah]
0x1801e3ed5  lea     hInst, [r14+hInst*4]
0x1801e3ed9  mov     [rsp+0A8h+lpBits], hInst; lpBits
0x1801e3ede  mov     hInst, rdi; hdc
0x1801e3ee1  mov     [rsp+0A8h+SrcHeight], eax; SrcHeight
0x1801e3ee5  mov     [rsp+0A8h+SrcWidth], r12d; SrcWidth
0x1801e3eea  mov     [rsp+0A8h+ySrc], edx; ySrc
0x1801e3eee  mov     [rsp+0A8h+xSrc], edx; xSrc
0x1801e3ef2  mov     [rsp+0A8h+DestHeight], eax; DestHeight
0x1801e3ef6  call    cs:__imp_StretchDIBits
0x1801e3efc  mov     hRsrc, rbx; h
0x1801e3eff  mov     hInst, rdi; hdc
0x1801e3f02  call    cs:__imp_SelectObject
0x1801e3f08  mov     hInst, rdi; hdc
0x1801e3f0b  call    cs:__imp_DeleteDC
0x1801e3f11  mov     hRsrc, rbp; hDC
0x1801e3f14  xor     ecx, ecx; hWnd
0x1801e3f16  call    cs:__imp_ReleaseDC
0x1801e3f1c  mov     hInst, rsi; Block
0x1801e3f1f  call    cs:__imp_free
0x1801e3f25  mov     rax, r15
0x1801e3f28  jmp     short loc_1801E3F2C
0x1801e3f2a  xor     eax, eax
0x1801e3f2c  mov     rbx, [rsp+0A8h+arg_0]
0x1801e3f34  add     rsp, 70h
0x1801e3f38  pop     r15
0x1801e3f3a  pop     r14
0x1801e3f3c  pop     r13
0x1801e3f3e  pop     r12
0x1801e3f40  pop     rdi
0x1801e3f41  pop     rsi
0x1801e3f42  pop     rbp
0x1801e3f43  retn
```
