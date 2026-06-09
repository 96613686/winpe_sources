# _FHbmpsOfHicon(HICON__ *,HBITMAP__ * *,HBITMAP__ * *)

- ea: `0x180028eb4`
- end: `0x180029196`
- name: `?_FHbmpsOfHicon@@YAJPEAUHICON__@@PEAPEAUHBITMAP__@@1@Z`
- size: `738`
- prototype: `HRESULT __fastcall(HICON__ *hicon, HBITMAP__ **phbmpAND, HBITMAP__ **phbmpXOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800271c0`

## callees

- `0x180028eb4`

## import_xrefs

- `GDI32!PatBlt` at `0x18002904b`
- `GDI32!PatBlt` at `0x1800290a0`
- `GDI32!PatBlt` at `0x18002904b`
- `GDI32!PatBlt` at `0x1800290a0`
- `GDI32!BitBlt` at `0x1800290f1`
- `GDI32!BitBlt` at `0x1800290f1`
- `GDI32!CreateCompatibleBitmap` at `0x180028fe3`
- `GDI32!CreateCompatibleBitmap` at `0x180028fe3`
- `GDI32!DeleteDC` at `0x180029118`
- `GDI32!DeleteDC` at `0x180029121`
- `GDI32!DeleteDC` at `0x18002914d`
- `GDI32!DeleteDC` at `0x18002915b`
- `GDI32!DeleteDC` at `0x180029118`
- `GDI32!DeleteDC` at `0x180029121`
- `GDI32!DeleteDC` at `0x18002914d`
- `GDI32!DeleteDC` at `0x18002915b`
- `GDI32!CreateCompatibleDC` at `0x180028fb4`
- `GDI32!CreateCompatibleDC` at `0x180028fc9`
- `GDI32!CreateCompatibleDC` at `0x180028fb4`
- `GDI32!CreateCompatibleDC` at `0x180028fc9`
- `GDI32!DeleteObject` at `0x180028f53`
- `GDI32!DeleteObject` at `0x180028f62`
- `GDI32!DeleteObject` at `0x180029169`
- `GDI32!DeleteObject` at `0x180029177`
- `GDI32!DeleteObject` at `0x180028f53`
- `GDI32!DeleteObject` at `0x180028f62`
- `GDI32!DeleteObject` at `0x180029169`
- `GDI32!DeleteObject` at `0x180029177`
- `GDI32!CreateBitmap` at `0x180029011`
- `GDI32!CreateBitmap` at `0x180029011`
- `GDI32!GetObjectW` at `0x180028f34`
- `GDI32!GetObjectW` at `0x180028f34`
- `GDI32!SelectObject` at `0x180029029`
- `GDI32!SelectObject` at `0x180029079`
- `GDI32!SelectObject` at `0x180029102`
- `GDI32!SelectObject` at `0x18002910f`
- `GDI32!SelectObject` at `0x180029029`
- `GDI32!SelectObject` at `0x180029079`
- `GDI32!SelectObject` at `0x180029102`
- `GDI32!SelectObject` at `0x18002910f`
- `USER32!ReleaseDC` at `0x180028ffa`
- `USER32!ReleaseDC` at `0x18002913f`
- `USER32!ReleaseDC` at `0x180028ffa`
- `USER32!ReleaseDC` at `0x18002913f`
- `USER32!GetDC` at `0x180028f97`
- `USER32!GetDC` at `0x180028f97`
- `USER32!GetSystemMetrics` at `0x180028f76`
- `USER32!GetSystemMetrics` at `0x180028f83`
- `USER32!GetSystemMetrics` at `0x180028f76`
- `USER32!GetSystemMetrics` at `0x180028f83`
- `USER32!DrawIcon` at `0x180029065`
- `USER32!DrawIcon` at `0x1800290ba`
- `USER32!DrawIcon` at `0x180029065`
- `USER32!DrawIcon` at `0x1800290ba`
- `USER32!GetIconInfo` at `0x180028ef2`
- `USER32!GetIconInfo` at `0x180028ef2`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall _FHbmpsOfHicon(HICON hicon, HBITMAP__ **phbmpAND, HBITMAP__ **phbmpXOR)
{
  int SystemMetrics; // esi
  int v7; // r14d
  HBITMAP__ *v8; // rax
  HDC DC; // rax
  HDC v11; // r15
  HDC v12; // rbx
  HBITMAP CompatibleBitmap; // r12
  HBITMAP Bitmap; // r13
  HDC CompatibleDC; // rdi
  _BYTE iconinfo_8[64]; // [rsp+58h] [rbp-29h] OVERLAPPED BYREF
  HGDIOBJ h; // [rsp+100h] [rbp+7Fh]

  memset(iconinfo_8, 0, 32);
  if ( !GetIconInfo(hicon, (PICONINFO)iconinfo_8) )
    goto LABEL_13;
  SystemMetrics = 0;
  v7 = 0;
  if ( *(_QWORD *)&iconinfo_8[16] )
  {
    v8 = *(HBITMAP__ **)&iconinfo_8[24];
    if ( *(_QWORD *)&iconinfo_8[24] )
    {
      *phbmpAND = *(HBITMAP__ **)&iconinfo_8[16];
      *phbmpXOR = v8;
      return 0;
    }
    memset(&iconinfo_8[32], 0, 32);
    if ( GetObjectW(*(HANDLE *)&iconinfo_8[16], 32, &iconinfo_8[32]) )
    {
      SystemMetrics = *(_DWORD *)&iconinfo_8[36];
      v7 = *(_DWORD *)&iconinfo_8[40] / 2;
    }
    DeleteObject(*(HGDIOBJ *)&iconinfo_8[16]);
  }
  if ( *(_QWORD *)&iconinfo_8[24] )
    DeleteObject(*(HGDIOBJ *)&iconinfo_8[24]);
  if ( !SystemMetrics || !v7 )
  {
LABEL_13:
    SystemMetrics = GetSystemMetrics(11);
    v7 = GetSystemMetrics(12);
  }
  if ( hicon )
  {
    DC = GetDC(0);
    v11 = DC;
    if ( !DC )
      return 0;
    v12 = 0;
    CompatibleBitmap = 0;
    Bitmap = 0;
    CompatibleDC = CreateCompatibleDC(DC);
    if ( CompatibleDC )
    {
      v12 = CreateCompatibleDC(v11);
      if ( v12 )
      {
        CompatibleBitmap = CreateCompatibleBitmap(v11, SystemMetrics, v7);
        if ( CompatibleBitmap )
        {
          ReleaseDC(0, v11);
          Bitmap = CreateBitmap(SystemMetrics, v7, 1u, 1u, 0);
          if ( Bitmap )
          {
            h = SelectObject(CompatibleDC, CompatibleBitmap);
            if ( PatBlt(CompatibleDC, 0, 0, SystemMetrics, v7, 0x42u) )
            {
              if ( DrawIcon(CompatibleDC, 0, 0, hicon)
                && SelectObject(v12, Bitmap)
                && PatBlt(v12, 0, 0, SystemMetrics, v7, 0xFF0062u)
                && DrawIcon(v12, 0, 0, hicon)
                && BitBlt(v12, 0, 0, SystemMetrics, v7, CompatibleDC, 0, 0, 0x660046u) )
              {
                SelectObject(CompatibleDC, h);
                SelectObject(v12, h);
                DeleteDC(CompatibleDC);
                DeleteDC(v12);
                *phbmpXOR = CompatibleBitmap;
                *phbmpAND = Bitmap;
                return 0;
              }
            }
          }
        }
      }
    }
    ReleaseDC(0, v11);
    if ( CompatibleDC )
      DeleteDC(CompatibleDC);
    if ( v12 )
      DeleteDC(v12);
    if ( CompatibleBitmap )
      DeleteObject(CompatibleBitmap);
    if ( Bitmap )
      DeleteObject(Bitmap);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180028eb4  mov     rax, rsp
0x180028eb7  mov     [rax+18h], phbmpXOR
0x180028ebb  mov     [rax+10h], phbmpAND
0x180028ebf  mov     [rax+8], hicon
0x180028ec3  push    rbp
0x180028ec4  push    rbx
0x180028ec5  push    rsi
0x180028ec6  push    rdi
0x180028ec7  push    r12
0x180028ec9  push    r13
0x180028ecb  push    r14
0x180028ecd  push    r15
0x180028ecf  lea     rbp, [rax-5Fh]
0x180028ed3  sub     rsp, 98h
0x180028eda  xorps   xmm0, xmm0
0x180028edd  mov     r15, phbmpAND
0x180028ee0  lea     phbmpAND, [rbp+57h+iconinfo.yHotspot]; piconinfo
0x180028ee4  mov     rdi, phbmpXOR
0x180028ee7  movups  xmmword ptr [rbp+57h+iconinfo.yHotspot], xmm0
0x180028eeb  mov     rbx, hicon
0x180028eee  movups  xmmword ptr [rbp+57h+iconinfo.hbmColor], xmm0
0x180028ef2  call    cs:__imp_GetIconInfo
0x180028ef8  test    eax, eax
0x180028efa  jz      short loc_180028F71
0x180028efc  mov     hicon, [rbp+57h+iconinfo.hbmColor]; h
0x180028f00  xor     esi, esi
0x180028f02  xor     r14d, r14d
0x180028f05  test    hicon, hicon
0x180028f08  jz      short loc_180028F59
0x180028f0a  mov     rax, qword ptr [rbp+57h+bitmap.bmType]
0x180028f0e  test    rax, rax
0x180028f11  jz      short loc_180028F20
0x180028f13  mov     [r15], hicon
0x180028f16  mov     [rdi], rax
0x180028f19  xor     eax, eax
0x180028f1b  jmp     loc_180029182
0x180028f20  xorps   xmm0, xmm0
0x180028f23  lea     phbmpXOR, [rbp+57h+bitmap.bmHeight]; pv
0x180028f27  mov     edx, 20h ; ' '; c
0x180028f2c  movups  xmmword ptr [rbp+57h+bitmap.bmHeight], xmm0
0x180028f30  movups  xmmword ptr [rbp+57h+bitmap.bmBits], xmm0
0x180028f34  call    cs:__imp_GetObjectW
0x180028f3a  test    eax, eax
0x180028f3c  jz      short loc_180028F4F
0x180028f3e  mov     eax, dword ptr [rbp+57h+bitmap.bmPlanes]
0x180028f41  mov     ecx, 2
0x180028f46  mov     esi, [rbp+57h+bitmap.bmWidthBytes]
0x180028f49  cdq
0x180028f4a  idiv    ecx
0x180028f4c  mov     r14d, eax
0x180028f4f  mov     hicon, [rbp+57h+iconinfo.hbmColor]; ho
0x180028f53  call    cs:__imp_DeleteObject
0x180028f59  mov     hicon, qword ptr [rbp+57h+bitmap.bmType]; ho
0x180028f5d  test    hicon, hicon
0x180028f60  jz      short loc_180028F68
0x180028f62  call    cs:__imp_DeleteObject
0x180028f68  test    esi, esi
0x180028f6a  jz      short loc_180028F71
0x180028f6c  test    r14d, r14d
0x180028f6f  jnz     short loc_180028F8C
0x180028f71  mov     ecx, 0Bh; nIndex
0x180028f76  call    cs:__imp_GetSystemMetrics
0x180028f7c  mov     ecx, 0Ch; nIndex
0x180028f81  mov     esi, eax
0x180028f83  call    cs:__imp_GetSystemMetrics
0x180028f89  mov     r14d, eax
0x180028f8c  test    rbx, rbx
0x180028f8f  jz      loc_18002917D
0x180028f95  xor     ecx, ecx; hWnd
0x180028f97  call    cs:__imp_GetDC
0x180028f9d  mov     r15, rax
0x180028fa0  test    rax, rax
0x180028fa3  jz      loc_180028F19
0x180028fa9  mov     hicon, rax; hdc
0x180028fac  xor     ebx, ebx
0x180028fae  xor     r12d, r12d
0x180028fb1  xor     r13d, r13d
0x180028fb4  call    cs:__imp_CreateCompatibleDC
0x180028fba  mov     rdi, rax
0x180028fbd  test    rax, rax
0x180028fc0  jz      $ExitFalse
0x180028fc6  mov     hicon, r15; hdc
0x180028fc9  call    cs:__imp_CreateCompatibleDC
0x180028fcf  mov     rbx, rax
0x180028fd2  test    rax, rax
0x180028fd5  jz      $ExitFalse
0x180028fdb  mov     r8d, r14d; cy
0x180028fde  mov     edx, esi; cx
0x180028fe0  mov     hicon, r15; hdc
0x180028fe3  call    cs:__imp_CreateCompatibleBitmap
0x180028fe9  mov     r12, rax
0x180028fec  test    rax, rax
0x180028fef  jz      $ExitFalse
0x180028ff5  mov     phbmpAND, r15; hDC
0x180028ff8  xor     ecx, ecx; hWnd
0x180028ffa  call    cs:__imp_ReleaseDC
0x180029000  lea     r8d, [r13+1]; nPlanes
0x180029004  mov     [rsp+0D0h+lpBits], r13; lpBits
0x180029009  mov     r9d, r8d; nBitCount
0x18002900c  mov     edx, r14d; nHeight
0x18002900f  mov     ecx, esi; nWidth
0x180029011  call    cs:__imp_CreateBitmap
0x180029017  mov     r13, rax
0x18002901a  test    rax, rax
0x18002901d  jz      $ExitFalse
0x180029023  mov     phbmpAND, r12; h
0x180029026  mov     hicon, rdi; hdc
0x180029029  call    cs:__imp_SelectObject
0x18002902f  mov     r9d, esi; w
0x180029032  mov     [rsp+0D0h+rop], 42h ; 'B'; rop
0x18002903a  xor     r8d, r8d; y
0x18002903d  mov     [rbp+57h+h], rax
0x180029041  xor     edx, edx; x
0x180029043  mov     dword ptr [rsp+0D0h+lpBits], r14d; h
0x180029048  mov     hicon, rdi; hdc
0x18002904b  call    cs:__imp_PatBlt
0x180029051  test    eax, eax
0x180029053  jz      $ExitFalse
0x180029059  mov     r9, [rbp+57h+arg_0]; hIcon
0x18002905d  xor     r8d, r8d; Y
0x180029060  xor     edx, edx; X
0x180029062  mov     hicon, rdi; hDC
0x180029065  call    cs:__imp_DrawIcon
0x18002906b  test    eax, eax
0x18002906d  jz      $ExitFalse
0x180029073  mov     phbmpAND, r13; h
0x180029076  mov     hicon, rbx; hdc
0x180029079  call    cs:__imp_SelectObject
0x18002907f  test    rax, rax
0x180029082  jz      $ExitFalse
0x180029088  mov     [rsp+0D0h+rop], 0FF0062h; rop
0x180029090  mov     r9d, esi; w
0x180029093  xor     r8d, r8d; y
0x180029096  mov     dword ptr [rsp+0D0h+lpBits], r14d; h
0x18002909b  xor     edx, edx; x
0x18002909d  mov     hicon, rbx; hdc
0x1800290a0  call    cs:__imp_PatBlt
0x1800290a6  test    eax, eax
0x1800290a8  jz      $ExitFalse
0x1800290ae  mov     r9, [rbp+57h+arg_0]; hIcon
0x1800290b2  xor     r8d, r8d; Y
0x1800290b5  xor     edx, edx; X
0x1800290b7  mov     hicon, rbx; hDC
0x1800290ba  call    cs:__imp_DrawIcon
0x1800290c0  test    eax, eax
0x1800290c2  jz      short $ExitFalse
0x1800290c4  mov     dword ptr [rsp+40h], 660046h; rop
0x1800290cc  mov     r9d, esi; cx
0x1800290cf  mov     [rsp+0D0h+y1], 0; y1
0x1800290d7  xor     r8d, r8d; y
0x1800290da  mov     [rsp+0D0h+x1], 0; x1
0x1800290e2  xor     edx, edx; x
0x1800290e4  mov     qword ptr [rsp+0D0h+rop], rdi; hdcSrc
0x1800290e9  mov     hicon, rbx; hdc
0x1800290ec  mov     dword ptr [rsp+0D0h+lpBits], r14d; cy
0x1800290f1  call    cs:__imp_BitBlt
0x1800290f7  test    eax, eax
0x1800290f9  jz      short $ExitFalse
0x1800290fb  mov     phbmpAND, [rbp+57h+h]; h
0x1800290ff  mov     hicon, rdi; hdc
0x180029102  call    cs:__imp_SelectObject
0x180029108  mov     phbmpAND, [rbp+57h+h]; h
0x18002910c  mov     hicon, rbx; hdc
0x18002910f  call    cs:__imp_SelectObject
0x180029115  mov     hicon, rdi; hdc
0x180029118  call    cs:__imp_DeleteDC
0x18002911e  mov     hicon, rbx; hdc
0x180029121  call    cs:__imp_DeleteDC
0x180029127  mov     rax, [rbp+57h+arg_10]
0x18002912b  mov     [rax], r12
0x18002912e  mov     rax, [rbp+57h+arg_8]
0x180029132  mov     [rax], r13
0x180029135  jmp     loc_180028F19
0x18002913a  mov     phbmpAND, r15; hDC
0x18002913d  xor     ecx, ecx; hWnd
0x18002913f  call    cs:__imp_ReleaseDC
0x180029145  test    rdi, rdi
0x180029148  jz      short loc_180029153
0x18002914a  mov     hicon, rdi; hdc
0x18002914d  call    cs:__imp_DeleteDC
0x180029153  test    rbx, rbx
0x180029156  jz      short loc_180029161
0x180029158  mov     hicon, rbx; hdc
0x18002915b  call    cs:__imp_DeleteDC
0x180029161  test    r12, r12
0x180029164  jz      short loc_18002916F
0x180029166  mov     hicon, r12; ho
0x180029169  call    cs:__imp_DeleteObject
0x18002916f  test    r13, r13
0x180029172  jz      short loc_18002917D
0x180029174  mov     hicon, r13; ho
0x180029177  call    cs:__imp_DeleteObject
0x18002917d  mov     eax, 80004005h
0x180029182  add     rsp, 98h
0x180029189  pop     r15
0x18002918b  pop     r14
0x18002918d  pop     r13
0x18002918f  pop     r12
0x180029191  pop     rdi
0x180029192  pop     rsi
0x180029193  pop     rbx
0x180029194  pop     rbp
0x180029195  retn
```
