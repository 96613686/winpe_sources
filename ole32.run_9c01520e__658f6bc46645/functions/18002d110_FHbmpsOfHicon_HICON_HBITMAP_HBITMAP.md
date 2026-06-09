# _FHbmpsOfHicon(HICON__ *,HBITMAP__ * *,HBITMAP__ * *)

- ea: `0x18002d110`
- end: `0x18002d49e`
- name: `?_FHbmpsOfHicon@@YAJPEAUHICON__@@PEAPEAUHBITMAP__@@1@Z`
- size: `910`
- prototype: `HRESULT __fastcall(HICON__ *hicon, HBITMAP__ **phbmpAND, HBITMAP__ **phbmpXOR)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002c9d0`

## callees

- `0x18002d110`

## import_xrefs

- `GDI32!BitBlt` at `0x18002d3bc`
- `GDI32!BitBlt` at `0x18002d3bc`
- `GDI32!PatBlt` at `0x18002d2fa`
- `GDI32!PatBlt` at `0x18002d361`
- `GDI32!PatBlt` at `0x18002d2fa`
- `GDI32!PatBlt` at `0x18002d361`
- `GDI32!CreateCompatibleBitmap` at `0x18002d279`
- `GDI32!CreateCompatibleBitmap` at `0x18002d279`
- `GDI32!DeleteDC` at `0x18002d3f5`
- `GDI32!DeleteDC` at `0x18002d404`
- `GDI32!DeleteDC` at `0x18002d43c`
- `GDI32!DeleteDC` at `0x18002d450`
- `GDI32!DeleteDC` at `0x18002d3f5`
- `GDI32!DeleteDC` at `0x18002d404`
- `GDI32!DeleteDC` at `0x18002d43c`
- `GDI32!DeleteDC` at `0x18002d450`
- `GDI32!CreateCompatibleDC` at `0x18002d23e`
- `GDI32!CreateCompatibleDC` at `0x18002d259`
- `GDI32!CreateCompatibleDC` at `0x18002d23e`
- `GDI32!CreateCompatibleDC` at `0x18002d259`
- `GDI32!DeleteObject` at `0x18002d1bf`
- `GDI32!DeleteObject` at `0x18002d1d4`
- `GDI32!DeleteObject` at `0x18002d464`
- `GDI32!DeleteObject` at `0x18002d478`
- `GDI32!DeleteObject` at `0x18002d1bf`
- `GDI32!DeleteObject` at `0x18002d1d4`
- `GDI32!DeleteObject` at `0x18002d464`
- `GDI32!DeleteObject` at `0x18002d478`
- `GDI32!CreateBitmap` at `0x18002d2b4`
- `GDI32!CreateBitmap` at `0x18002d2b4`
- `GDI32!GetObjectW` at `0x18002d19a`
- `GDI32!GetObjectW` at `0x18002d19a`
- `GDI32!SelectObject` at `0x18002d2d2`
- `GDI32!SelectObject` at `0x18002d334`
- `GDI32!SelectObject` at `0x18002d3d3`
- `GDI32!SelectObject` at `0x18002d3e6`
- `GDI32!SelectObject` at `0x18002d2d2`
- `GDI32!SelectObject` at `0x18002d334`
- `GDI32!SelectObject` at `0x18002d3d3`
- `GDI32!SelectObject` at `0x18002d3e6`
- `USER32!DrawIcon` at `0x18002d31a`
- `USER32!DrawIcon` at `0x18002d381`
- `USER32!DrawIcon` at `0x18002d31a`
- `USER32!DrawIcon` at `0x18002d381`
- `USER32!GetIconInfo` at `0x18002d153`
- `USER32!GetIconInfo` at `0x18002d153`
- `USER32!ReleaseDC` at `0x18002d296`
- `USER32!ReleaseDC` at `0x18002d428`
- `USER32!ReleaseDC` at `0x18002d296`
- `USER32!ReleaseDC` at `0x18002d428`
- `USER32!GetDC` at `0x18002d223`
- `USER32!GetDC` at `0x18002d223`
- `USER32!GetSystemMetrics` at `0x18002d1ee`
- `USER32!GetSystemMetrics` at `0x18002d201`
- `USER32!GetSystemMetrics` at `0x18002d1ee`
- `USER32!GetSystemMetrics` at `0x18002d201`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall _FHbmpsOfHicon(HICON hicon, HBITMAP__ **phbmpAND, HBITMAP__ **phbmpXOR)
{
  int SystemMetrics; // esi
  int h; // r14d
  HBITMAP__ *v8; // rax
  HDC v10; // rbx
  HBITMAP CompatibleBitmap; // r15
  HBITMAP Bitmap; // r12
  HDC DC; // rax
  HDC v14; // r13
  HDC CompatibleDC; // rdi
  _BYTE iconinfo_8[64]; // [rsp+58h] [rbp-29h] OVERLAPPED BYREF
  HGDIOBJ v20; // [rsp+100h] [rbp+7Fh]

  memset(iconinfo_8, 0, 32);
  SystemMetrics = 0;
  h = 0;
  if ( !GetIconInfo(hicon, (PICONINFO)iconinfo_8) )
    goto LABEL_13;
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
      h = *(_DWORD *)&iconinfo_8[40] / 2;
    }
    DeleteObject(*(HGDIOBJ *)&iconinfo_8[16]);
  }
  if ( *(_QWORD *)&iconinfo_8[24] )
    DeleteObject(*(HGDIOBJ *)&iconinfo_8[24]);
  if ( !SystemMetrics || !h )
  {
LABEL_13:
    SystemMetrics = GetSystemMetrics(11);
    h = GetSystemMetrics(12);
  }
  v10 = 0;
  CompatibleBitmap = 0;
  Bitmap = 0;
  if ( hicon )
  {
    DC = GetDC(0);
    v14 = DC;
    if ( !DC )
      return 0;
    CompatibleDC = CreateCompatibleDC(DC);
    if ( CompatibleDC )
    {
      v10 = CreateCompatibleDC(v14);
      if ( v10 )
      {
        CompatibleBitmap = CreateCompatibleBitmap(v14, SystemMetrics, h);
        if ( CompatibleBitmap )
        {
          ReleaseDC(0, v14);
          Bitmap = CreateBitmap(SystemMetrics, h, 1u, 1u, 0);
          if ( Bitmap )
          {
            v20 = SelectObject(CompatibleDC, CompatibleBitmap);
            if ( PatBlt(CompatibleDC, 0, 0, SystemMetrics, h, 0x42u) )
            {
              if ( DrawIcon(CompatibleDC, 0, 0, hicon)
                && SelectObject(v10, Bitmap)
                && PatBlt(v10, 0, 0, SystemMetrics, h, 0xFF0062u)
                && DrawIcon(v10, 0, 0, hicon)
                && BitBlt(v10, 0, 0, SystemMetrics, h, CompatibleDC, 0, 0, 0x660046u) )
              {
                SelectObject(CompatibleDC, v20);
                SelectObject(v10, v20);
                DeleteDC(CompatibleDC);
                DeleteDC(v10);
                *phbmpXOR = CompatibleBitmap;
                *phbmpAND = Bitmap;
                return 0;
              }
            }
          }
        }
      }
    }
    ReleaseDC(0, v14);
    if ( CompatibleDC )
      DeleteDC(CompatibleDC);
    if ( v10 )
      DeleteDC(v10);
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
0x18002d110  mov     rax, rsp
0x18002d113  mov     [rax+18h], phbmpXOR
0x18002d117  mov     [rax+10h], phbmpAND
0x18002d11b  mov     [rax+8], hicon
0x18002d11f  push    rbp
0x18002d120  push    rbx
0x18002d121  push    rsi
0x18002d122  push    rdi
0x18002d123  push    r12
0x18002d125  push    r13
0x18002d127  push    r14
0x18002d129  push    r15
0x18002d12b  lea     rbp, [rax-5Fh]
0x18002d12f  sub     rsp, 98h
0x18002d136  xorps   xmm0, xmm0
0x18002d139  mov     r15, phbmpAND
0x18002d13c  lea     phbmpAND, [rbp+57h+iconinfo.yHotspot]; piconinfo
0x18002d140  mov     rbx, phbmpXOR
0x18002d143  movups  xmmword ptr [rbp+57h+iconinfo.yHotspot], xmm0
0x18002d147  mov     rdi, hicon
0x18002d14a  xor     esi, esi
0x18002d14c  movups  xmmword ptr [rbp+57h+iconinfo.hbmColor], xmm0
0x18002d150  xor     r14d, r14d
0x18002d153  call    cs:__imp_GetIconInfo
0x18002d15a  nop     dword ptr [rax+rax+00h]
0x18002d15f  test    eax, eax
0x18002d161  jz      loc_18002D1E9
0x18002d167  mov     hicon, [rbp+57h+iconinfo.hbmColor]; h
0x18002d16b  test    hicon, hicon
0x18002d16e  jz      short loc_18002D1CB
0x18002d170  mov     rax, qword ptr [rbp+57h+bitmap.bmType]
0x18002d174  test    rax, rax
0x18002d177  jz      short loc_18002D186
0x18002d179  mov     [r15], hicon
0x18002d17c  mov     [rbx], rax
0x18002d17f  xor     eax, eax
0x18002d181  jmp     loc_18002D489
0x18002d186  xorps   xmm0, xmm0
0x18002d189  lea     phbmpXOR, [rbp+57h+bitmap.bmHeight]; pv
0x18002d18d  mov     edx, 20h ; ' '; c
0x18002d192  movups  xmmword ptr [rbp+57h+bitmap.bmHeight], xmm0
0x18002d196  movups  xmmword ptr [rbp+57h+bitmap.bmBits], xmm0
0x18002d19a  call    cs:__imp_GetObjectW
0x18002d1a1  nop     dword ptr [rax+rax+00h]
0x18002d1a6  test    eax, eax
0x18002d1a8  jz      short loc_18002D1BB
0x18002d1aa  mov     eax, dword ptr [rbp+57h+bitmap.bmPlanes]
0x18002d1ad  mov     ecx, 2
0x18002d1b2  mov     esi, [rbp+57h+bitmap.bmWidthBytes]
0x18002d1b5  cdq
0x18002d1b6  idiv    ecx
0x18002d1b8  mov     r14d, eax
0x18002d1bb  mov     hicon, [rbp+57h+iconinfo.hbmColor]; ho
0x18002d1bf  call    cs:__imp_DeleteObject
0x18002d1c6  nop     dword ptr [rax+rax+00h]
0x18002d1cb  mov     hicon, qword ptr [rbp+57h+bitmap.bmType]; ho
0x18002d1cf  test    hicon, hicon
0x18002d1d2  jz      short loc_18002D1E0
0x18002d1d4  call    cs:__imp_DeleteObject
0x18002d1db  nop     dword ptr [rax+rax+00h]
0x18002d1e0  test    esi, esi
0x18002d1e2  jz      short loc_18002D1E9
0x18002d1e4  test    r14d, r14d
0x18002d1e7  jnz     short loc_18002D210
0x18002d1e9  mov     ecx, 0Bh; nIndex
0x18002d1ee  call    cs:__imp_GetSystemMetrics
0x18002d1f5  nop     dword ptr [rax+rax+00h]
0x18002d1fa  mov     ecx, 0Ch; nIndex
0x18002d1ff  mov     esi, eax
0x18002d201  call    cs:__imp_GetSystemMetrics
0x18002d208  nop     dword ptr [rax+rax+00h]
0x18002d20d  mov     r14d, eax
0x18002d210  xor     ebx, ebx
0x18002d212  xor     r15d, r15d
0x18002d215  xor     r12d, r12d
0x18002d218  test    rdi, rdi
0x18002d21b  jz      loc_18002D484
0x18002d221  xor     ecx, ecx; hWnd
0x18002d223  call    cs:__imp_GetDC
0x18002d22a  nop     dword ptr [rax+rax+00h]
0x18002d22f  mov     r13, rax
0x18002d232  test    rax, rax
0x18002d235  jz      loc_18002D17F
0x18002d23b  mov     hicon, rax; hdc
0x18002d23e  call    cs:__imp_CreateCompatibleDC
0x18002d245  nop     dword ptr [rax+rax+00h]
0x18002d24a  mov     rdi, rax
0x18002d24d  test    rax, rax
0x18002d250  jz      $ExitFalse
0x18002d256  mov     hicon, r13; hdc
0x18002d259  call    cs:__imp_CreateCompatibleDC
0x18002d260  nop     dword ptr [rax+rax+00h]
0x18002d265  mov     rbx, rax
0x18002d268  test    rax, rax
0x18002d26b  jz      $ExitFalse
0x18002d271  mov     r8d, r14d; cy
0x18002d274  mov     edx, esi; cx
0x18002d276  mov     hicon, r13; hdc
0x18002d279  call    cs:__imp_CreateCompatibleBitmap
0x18002d280  nop     dword ptr [rax+rax+00h]
0x18002d285  mov     r15, rax
0x18002d288  test    rax, rax
0x18002d28b  jz      $ExitFalse
0x18002d291  mov     phbmpAND, r13; hDC
0x18002d294  xor     ecx, ecx; hWnd
0x18002d296  call    cs:__imp_ReleaseDC
0x18002d29d  nop     dword ptr [rax+rax+00h]
0x18002d2a2  and     qword ptr [rsp+0D0h+h], r12
0x18002d2a7  lea     r8d, [r12+1]; nPlanes
0x18002d2ac  mov     r9d, r8d; nBitCount
0x18002d2af  mov     edx, r14d; nHeight
0x18002d2b2  mov     ecx, esi; nWidth
0x18002d2b4  call    cs:__imp_CreateBitmap
0x18002d2bb  nop     dword ptr [rax+rax+00h]
0x18002d2c0  mov     r12, rax
0x18002d2c3  test    rax, rax
0x18002d2c6  jz      $ExitFalse
0x18002d2cc  mov     phbmpAND, r15; h
0x18002d2cf  mov     hicon, rdi; hdc
0x18002d2d2  call    cs:__imp_SelectObject
0x18002d2d9  nop     dword ptr [rax+rax+00h]
0x18002d2de  mov     r9d, esi; w
0x18002d2e1  mov     [rsp+0D0h+rop], 42h ; 'B'; rop
0x18002d2e9  xor     r8d, r8d; y
0x18002d2ec  mov     [rbp+57h+arg_18], rax
0x18002d2f0  xor     edx, edx; x
0x18002d2f2  mov     [rsp+0D0h+h], r14d; h
0x18002d2f7  mov     hicon, rdi; hdc
0x18002d2fa  call    cs:__imp_PatBlt
0x18002d301  nop     dword ptr [rax+rax+00h]
0x18002d306  test    eax, eax
0x18002d308  jz      $ExitFalse
0x18002d30e  mov     r9, [rbp+57h+arg_0]; hIcon
0x18002d312  xor     r8d, r8d; Y
0x18002d315  xor     edx, edx; X
0x18002d317  mov     hicon, rdi; hDC
0x18002d31a  call    cs:__imp_DrawIcon
0x18002d321  nop     dword ptr [rax+rax+00h]
0x18002d326  test    eax, eax
0x18002d328  jz      $ExitFalse
0x18002d32e  mov     phbmpAND, r12; h
0x18002d331  mov     hicon, rbx; hdc
0x18002d334  call    cs:__imp_SelectObject
0x18002d33b  nop     dword ptr [rax+rax+00h]
0x18002d340  test    rax, rax
0x18002d343  jz      $ExitFalse
0x18002d349  mov     [rsp+0D0h+rop], 0FF0062h; rop
0x18002d351  mov     r9d, esi; w
0x18002d354  xor     r8d, r8d; y
0x18002d357  mov     [rsp+0D0h+h], r14d; h
0x18002d35c  xor     edx, edx; x
0x18002d35e  mov     hicon, rbx; hdc
0x18002d361  call    cs:__imp_PatBlt
0x18002d368  nop     dword ptr [rax+rax+00h]
0x18002d36d  test    eax, eax
0x18002d36f  jz      $ExitFalse
0x18002d375  mov     r9, [rbp+57h+arg_0]; hIcon
0x18002d379  xor     r8d, r8d; Y
0x18002d37c  xor     edx, edx; X
0x18002d37e  mov     hicon, rbx; hDC
0x18002d381  call    cs:__imp_DrawIcon
0x18002d388  nop     dword ptr [rax+rax+00h]
0x18002d38d  test    eax, eax
0x18002d38f  jz      $ExitFalse
0x18002d395  mov     dword ptr [rsp+40h], 660046h; rop
0x18002d39d  mov     r9d, esi; cx
0x18002d3a0  and     [rsp+0D0h+var_98], 0
0x18002d3a5  xor     r8d, r8d; y
0x18002d3a8  and     [rsp+0D0h+var_A0], 0
0x18002d3ad  xor     edx, edx; x
0x18002d3af  mov     qword ptr [rsp+0D0h+rop], rdi; hdcSrc
0x18002d3b4  mov     hicon, rbx; hdc
0x18002d3b7  mov     [rsp+0D0h+h], r14d; cy
0x18002d3bc  call    cs:__imp_BitBlt
0x18002d3c3  nop     dword ptr [rax+rax+00h]
0x18002d3c8  test    eax, eax
0x18002d3ca  jz      short $ExitFalse
0x18002d3cc  mov     phbmpAND, [rbp+57h+arg_18]; h
0x18002d3d0  mov     hicon, rdi; hdc
0x18002d3d3  call    cs:__imp_SelectObject
0x18002d3da  nop     dword ptr [rax+rax+00h]
0x18002d3df  mov     phbmpAND, [rbp+57h+arg_18]; h
0x18002d3e3  mov     hicon, rbx; hdc
0x18002d3e6  call    cs:__imp_SelectObject
0x18002d3ed  nop     dword ptr [rax+rax+00h]
0x18002d3f2  mov     hicon, rdi; hdc
0x18002d3f5  call    cs:__imp_DeleteDC
0x18002d3fc  nop     dword ptr [rax+rax+00h]
0x18002d401  mov     hicon, rbx; hdc
0x18002d404  call    cs:__imp_DeleteDC
0x18002d40b  nop     dword ptr [rax+rax+00h]
0x18002d410  mov     rax, [rbp+57h+arg_10]
0x18002d414  mov     [rax], r15
0x18002d417  mov     rax, [rbp+57h+arg_8]
0x18002d41b  mov     [rax], r12
0x18002d41e  jmp     loc_18002D17F
0x18002d423  mov     phbmpAND, r13; hDC
0x18002d426  xor     ecx, ecx; hWnd
0x18002d428  call    cs:__imp_ReleaseDC
0x18002d42f  nop     dword ptr [rax+rax+00h]
0x18002d434  test    rdi, rdi
0x18002d437  jz      short loc_18002D448
0x18002d439  mov     hicon, rdi; hdc
0x18002d43c  call    cs:__imp_DeleteDC
0x18002d443  nop     dword ptr [rax+rax+00h]
0x18002d448  test    rbx, rbx
0x18002d44b  jz      short loc_18002D45C
0x18002d44d  mov     hicon, rbx; hdc
0x18002d450  call    cs:__imp_DeleteDC
0x18002d457  nop     dword ptr [rax+rax+00h]
0x18002d45c  test    r15, r15
0x18002d45f  jz      short loc_18002D470
0x18002d461  mov     hicon, r15; ho
0x18002d464  call    cs:__imp_DeleteObject
0x18002d46b  nop     dword ptr [rax+rax+00h]
0x18002d470  test    r12, r12
0x18002d473  jz      short loc_18002D484
0x18002d475  mov     hicon, r12; ho
0x18002d478  call    cs:__imp_DeleteObject
0x18002d47f  nop     dword ptr [rax+rax+00h]
0x18002d484  mov     eax, 80004005h
0x18002d489  add     rsp, 98h
0x18002d490  pop     r15
0x18002d492  pop     r14
0x18002d494  pop     r13
0x18002d496  pop     r12
0x18002d498  pop     rdi
0x18002d499  pop     rsi
0x18002d49a  pop     rbx
0x18002d49b  pop     rbp
0x18002d49c  retn
```
