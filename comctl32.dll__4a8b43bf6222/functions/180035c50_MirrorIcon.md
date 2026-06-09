# MirrorIcon

- ea: `0x180035c50`
- end: `0x180035f79`
- name: `MirrorIcon`
- size: `809`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005058c`
- `0x180082850`

## callees

- `0x180035c50`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180035cbb`
- `GDI32!CreateCompatibleDC` at `0x180035ccf`
- `GDI32!CreateCompatibleDC` at `0x180035cbb`
- `GDI32!CreateCompatibleDC` at `0x180035ccf`
- `GDI32!CreateCompatibleBitmap` at `0x180035dd4`
- `GDI32!CreateCompatibleBitmap` at `0x180035dd4`
- `GDI32!SelectObject` at `0x180035e06`
- `GDI32!SelectObject` at `0x180035e19`
- `GDI32!SelectObject` at `0x180035eae`
- `GDI32!SelectObject` at `0x180035ebe`
- `GDI32!SelectObject` at `0x180035e06`
- `GDI32!SelectObject` at `0x180035e19`
- `GDI32!SelectObject` at `0x180035eae`
- `GDI32!SelectObject` at `0x180035ebe`
- `GDI32!DeleteObject` at `0x180035db2`
- `GDI32!DeleteObject` at `0x180035dbc`
- `GDI32!DeleteObject` at `0x180035ee1`
- `GDI32!DeleteObject` at `0x180035eea`
- `GDI32!DeleteObject` at `0x180035db2`
- `GDI32!DeleteObject` at `0x180035dbc`
- `GDI32!DeleteObject` at `0x180035ee1`
- `GDI32!DeleteObject` at `0x180035eea`
- `GDI32!GetObjectW` at `0x180035da0`
- `GDI32!GetObjectW` at `0x180035da0`
- `GDI32!SetLayout` at `0x180035ceb`
- `GDI32!SetLayout` at `0x180035cfb`
- `GDI32!SetLayout` at `0x180035ceb`
- `GDI32!SetLayout` at `0x180035cfb`
- `GDI32!DeleteDC` at `0x180035d03`
- `GDI32!DeleteDC` at `0x180035d03`
- `GDI32!CreateBitmap` at `0x180035df3`
- `GDI32!CreateBitmap` at `0x180035df3`
- `KERNEL32!EnterCriticalSection` at `0x180035c9f`
- `KERNEL32!EnterCriticalSection` at `0x180035c9f`
- `KERNEL32!LeaveCriticalSection` at `0x180035f21`
- `KERNEL32!LeaveCriticalSection` at `0x180035f21`
- `USER32!GetDC` at `0x180035d3a`
- `USER32!GetDC` at `0x180035d3a`
- `USER32!ReleaseDC` at `0x180035f14`
- `USER32!ReleaseDC` at `0x180035f14`
- `USER32!DestroyIcon` at `0x180035f3b`
- `USER32!DestroyIcon` at `0x180035f5a`
- `USER32!DestroyIcon` at `0x180035f3b`
- `USER32!DestroyIcon` at `0x180035f5a`
- `USER32!GetIconInfo` at `0x180035d85`
- `USER32!GetIconInfo` at `0x180035d85`
- `USER32!DrawIconEx` at `0x180035e5d`
- `USER32!DrawIconEx` at `0x180035e9e`
- `USER32!DrawIconEx` at `0x180035e5d`
- `USER32!DrawIconEx` at `0x180035e9e`
- `USER32!CreateIconIndirect` at `0x180035ed0`
- `USER32!CreateIconIndirect` at `0x180035ed0`

## pseudocode

```c
__int64 __fastcall MirrorIcon(HICON *a1, HICON *a2)
{
  HICON *v2; // rbx
  HICON *v3; // rdi
  HICON v4; // r12
  HICON v5; // r15
  HDC DC; // rax
  unsigned int v7; // r13d
  HDC v8; // r15
  HBITMAP CompatibleBitmap; // r14
  HBITMAP Bitmap; // rsi
  HGDIOBJ v11; // rdi
  HGDIOBJ v12; // rbx
  HICON hIcon[2]; // [rsp+50h] [rbp-49h]
  __int128 v15; // [rsp+60h] [rbp-39h]
  _OWORD pv[2]; // [rsp+70h] [rbp-29h] BYREF
  ICONINFO piconinfo; // [rsp+90h] [rbp-9h] BYREF
  HICON v20; // [rsp+110h] [rbp+77h]
  HDC v21; // [rsp+118h] [rbp+7Fh]

  v2 = a1;
  v3 = a2;
  memset(pv, 0, sizeof(pv));
  *(_OWORD *)hIcon = 0;
  v15 = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  EnterCriticalSection(&g_csDll);
  if ( !g_hdc && !g_hdcMask )
  {
    g_hdc = CreateCompatibleDC(0);
    if ( g_hdc )
    {
      g_hdcMask = CreateCompatibleDC(0);
      if ( g_hdcMask )
      {
        SetLayout(g_hdc, 1u);
        SetLayout(g_hdcMask, 1u);
      }
      else
      {
        DeleteDC(g_hdc);
        g_hdc = 0;
      }
    }
  }
  if ( v2 )
  {
    v4 = *v2;
    hIcon[0] = *v2;
  }
  else
  {
    v4 = hIcon[0];
  }
  if ( v3 )
  {
    v5 = *v3;
    hIcon[1] = *v3;
  }
  else
  {
    v5 = hIcon[1];
  }
  v20 = v5;
  DC = GetDC(0);
  v21 = DC;
  if ( g_hdc && g_hdcMask && DC )
  {
    v7 = 0;
    v8 = DC;
    do
    {
      if ( hIcon[v7] && GetIconInfo(hIcon[v7], &piconinfo) && GetObjectW(piconinfo.hbmColor, 32, pv) )
      {
        DeleteObject(piconinfo.hbmMask);
        DeleteObject(piconinfo.hbmColor);
        piconinfo.hbmColor = 0;
        piconinfo.hbmMask = 0;
        CompatibleBitmap = CreateCompatibleBitmap(v8, SDWORD1(pv[0]), SDWORD2(pv[0]));
        Bitmap = CreateBitmap(SDWORD1(pv[0]), SDWORD2(pv[0]), 1u, 1u, 0);
        v11 = SelectObject(g_hdc, CompatibleBitmap);
        v12 = SelectObject(g_hdcMask, Bitmap);
        DrawIconEx(g_hdc, 0, 0, hIcon[v7], SDWORD1(pv[0]), SDWORD2(pv[0]), 0, 0, 2u);
        DrawIconEx(g_hdcMask, 0, 0, hIcon[v7], SDWORD1(pv[0]), SDWORD2(pv[0]), 0, 0, 1u);
        SelectObject(g_hdc, v11);
        SelectObject(g_hdcMask, v12);
        piconinfo.hbmMask = Bitmap;
        piconinfo.hbmColor = CompatibleBitmap;
        *((_QWORD *)&pv[-1] + (int)v7) = CreateIconIndirect(&piconinfo);
        DeleteObject(CompatibleBitmap);
        DeleteObject(Bitmap);
      }
      ++v7;
    }
    while ( v7 < 2 );
    v5 = v20;
    v2 = a1;
    v3 = a2;
    DC = v21;
  }
  ReleaseDC(0, DC);
  LeaveCriticalSection(&g_csDll);
  if ( v4 && (_QWORD)v15 )
  {
    *v2 = (HICON)v15;
    DestroyIcon(v4);
  }
  if ( v5 )
  {
    if ( *((_QWORD *)&v15 + 1) )
    {
      *v3 = (HICON)*((_QWORD *)&v15 + 1);
      if ( v5 != v4 )
        DestroyIcon(v5);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180035c50  mov     [rsp-8+arg_8], rdx
0x180035c55  mov     [rsp-8+arg_0], rcx
0x180035c5a  push    rbp
0x180035c5b  push    rbx
0x180035c5c  push    rsi
0x180035c5d  push    rdi
0x180035c5e  push    r12
0x180035c60  push    r13
0x180035c62  push    r14
0x180035c64  push    r15
0x180035c66  lea     rbp, [rsp-1Fh]
0x180035c6b  sub     rsp, 0B8h
0x180035c72  xorps   xmm0, xmm0
0x180035c75  xorps   xmm1, xmm1
0x180035c78  mov     rbx, rcx
0x180035c7b  mov     rdi, rdx
0x180035c7e  lea     rcx, g_csDll; lpCriticalSection
0x180035c85  movups  [rbp+57h+pv], xmm0
0x180035c89  movups  [rbp+57h+var_70], xmm0
0x180035c8d  movdqu  xmmword ptr [rbp+57h+hIcon], xmm1
0x180035c92  movdqu  [rbp+57h+var_90], xmm0
0x180035c97  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm1
0x180035c9b  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm1
0x180035c9f  call    cs:__imp_EnterCriticalSection
0x180035ca5  xor     esi, esi
0x180035ca7  cmp     cs:g_hdc, rsi
0x180035cae  jnz     short loc_180035D10
0x180035cb0  cmp     cs:g_hdcMask, rsi
0x180035cb7  jnz     short loc_180035D10
0x180035cb9  xor     ecx, ecx; hdc
0x180035cbb  call    cs:__imp_CreateCompatibleDC
0x180035cc1  mov     cs:g_hdc, rax
0x180035cc8  test    rax, rax
0x180035ccb  jz      short loc_180035D10
0x180035ccd  xor     ecx, ecx; hdc
0x180035ccf  call    cs:__imp_CreateCompatibleDC
0x180035cd5  mov     rcx, cs:g_hdc; hdc
0x180035cdc  mov     cs:g_hdcMask, rax
0x180035ce3  test    rax, rax
0x180035ce6  jz      short loc_180035D03
0x180035ce8  lea     edx, [rsi+1]; l
0x180035ceb  call    cs:__imp_SetLayout
0x180035cf1  mov     rcx, cs:g_hdcMask; hdc
0x180035cf8  lea     edx, [rsi+1]; l
0x180035cfb  call    cs:__imp_SetLayout
0x180035d01  jmp     short loc_180035D10
0x180035d03  call    cs:__imp_DeleteDC
0x180035d09  mov     cs:g_hdc, rsi
0x180035d10  test    rbx, rbx
0x180035d13  jz      short loc_180035D1E
0x180035d15  mov     r12, [rbx]
0x180035d18  mov     [rbp+57h+hIcon], r12
0x180035d1c  jmp     short loc_180035D22
0x180035d1e  mov     r12, [rbp+57h+hIcon]
0x180035d22  test    rdi, rdi
0x180035d25  jz      short loc_180035D30
0x180035d27  mov     r15, [rdi]
0x180035d2a  mov     [rbp+57h+hIcon+8], r15
0x180035d2e  jmp     short loc_180035D34
0x180035d30  mov     r15, [rbp+57h+hIcon+8]
0x180035d34  xor     ecx, ecx; hWnd
0x180035d36  mov     [rbp+57h+arg_10], r15
0x180035d3a  call    cs:__imp_GetDC
0x180035d40  cmp     cs:g_hdc, rsi
0x180035d47  mov     [rbp+57h+arg_18], rax
0x180035d4b  jz      loc_180035F0F
0x180035d51  cmp     cs:g_hdcMask, rsi
0x180035d58  jz      loc_180035F0F
0x180035d5e  test    rax, rax
0x180035d61  jz      loc_180035F0F
0x180035d67  mov     r13d, esi
0x180035d6a  mov     r15, rax
0x180035d6d  movsxd  rax, r13d
0x180035d70  mov     rax, [rbp+rax*8+57h+hIcon]
0x180035d75  test    rax, rax
0x180035d78  jz      loc_180035EF2
0x180035d7e  lea     rdx, [rbp+57h+piconinfo]; piconinfo
0x180035d82  mov     rcx, rax; hIcon
0x180035d85  call    cs:__imp_GetIconInfo
0x180035d8b  test    eax, eax
0x180035d8d  jz      loc_180035EF2
0x180035d93  mov     rcx, [rbp+57h+piconinfo.hbmColor]; h
0x180035d97  lea     r8, [rbp+57h+pv]; pv
0x180035d9b  mov     edx, 20h ; ' '; c
0x180035da0  call    cs:__imp_GetObjectW
0x180035da6  test    eax, eax
0x180035da8  jz      loc_180035EF2
0x180035dae  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x180035db2  call    cs:__imp_DeleteObject
0x180035db8  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x180035dbc  call    cs:__imp_DeleteObject
0x180035dc2  mov     r8d, dword ptr [rbp+57h+pv+8]; cy
0x180035dc6  mov     rcx, r15; hdc
0x180035dc9  mov     edx, dword ptr [rbp+57h+pv+4]; cx
0x180035dcc  mov     [rbp+57h+piconinfo.hbmColor], rsi
0x180035dd0  mov     [rbp+57h+piconinfo.hbmMask], rsi
0x180035dd4  call    cs:__imp_CreateCompatibleBitmap
0x180035dda  mov     edx, dword ptr [rbp+57h+pv+8]; nHeight
0x180035ddd  mov     r14, rax
0x180035de0  mov     ecx, dword ptr [rbp+57h+pv+4]; nWidth
0x180035de3  mov     eax, 1
0x180035de8  mov     r9d, eax; nBitCount
0x180035deb  mov     [rsp+0F0h+lpBits], rsi; lpBits
0x180035df0  mov     r8d, eax; nPlanes
0x180035df3  call    cs:__imp_CreateBitmap
0x180035df9  mov     rcx, cs:g_hdc; hdc
0x180035e00  mov     rdx, r14; h
0x180035e03  mov     rsi, rax
0x180035e06  call    cs:__imp_SelectObject
0x180035e0c  mov     rcx, cs:g_hdcMask; hdc
0x180035e13  mov     rdx, rsi; h
0x180035e16  mov     rdi, rax
0x180035e19  call    cs:__imp_SelectObject
0x180035e1f  mov     [rsp+0F0h+diFlags], 2; diFlags
0x180035e27  xor     r8d, r8d; yTop
0x180035e2a  mov     rbx, rax
0x180035e2d  mov     [rsp+0F0h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x180035e36  mov     eax, dword ptr [rbp+57h+pv+8]
0x180035e39  xor     edx, edx; xLeft
0x180035e3b  movsxd  rcx, r13d
0x180035e3e  mov     [rsp+0F0h+istepIfAniCur], 0; istepIfAniCur
0x180035e46  mov     [rsp+0F0h+cyWidth], eax; cyWidth
0x180035e4a  mov     eax, dword ptr [rbp+57h+pv+4]
0x180035e4d  mov     r9, [rbp+rcx*8+57h+hIcon]; hIcon
0x180035e52  mov     rcx, cs:g_hdc; hdc
0x180035e59  mov     dword ptr [rsp+0F0h+lpBits], eax; cxWidth
0x180035e5d  call    cs:__imp_DrawIconEx
0x180035e63  mov     eax, dword ptr [rbp+57h+pv+8]
0x180035e66  xor     r8d, r8d; yTop
0x180035e69  mov     rcx, cs:g_hdcMask; hdc
0x180035e70  xor     edx, edx; xLeft
0x180035e72  mov     [rsp+0F0h+diFlags], 1; diFlags
0x180035e7a  mov     [rsp+0F0h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x180035e83  mov     [rsp+0F0h+istepIfAniCur], 0; istepIfAniCur
0x180035e8b  mov     [rsp+0F0h+cyWidth], eax; cyWidth
0x180035e8f  mov     eax, dword ptr [rbp+57h+pv+4]
0x180035e92  mov     dword ptr [rsp+0F0h+lpBits], eax; cxWidth
0x180035e96  movsxd  rax, r13d
0x180035e99  mov     r9, [rbp+rax*8+57h+hIcon]; hIcon
0x180035e9e  call    cs:__imp_DrawIconEx
0x180035ea4  mov     rcx, cs:g_hdc; hdc
0x180035eab  mov     rdx, rdi; h
0x180035eae  call    cs:__imp_SelectObject
0x180035eb4  mov     rcx, cs:g_hdcMask; hdc
0x180035ebb  mov     rdx, rbx; h
0x180035ebe  call    cs:__imp_SelectObject
0x180035ec4  lea     rcx, [rbp+57h+piconinfo]; piconinfo
0x180035ec8  mov     [rbp+57h+piconinfo.hbmMask], rsi
0x180035ecc  mov     [rbp+57h+piconinfo.hbmColor], r14
0x180035ed0  call    cs:__imp_CreateIconIndirect
0x180035ed6  movsxd  rcx, r13d
0x180035ed9  mov     qword ptr [rbp+rcx*8+57h+var_90], rax
0x180035ede  mov     rcx, r14; ho
0x180035ee1  call    cs:__imp_DeleteObject
0x180035ee7  mov     rcx, rsi; ho
0x180035eea  call    cs:__imp_DeleteObject
0x180035ef0  xor     esi, esi
0x180035ef2  inc     r13d
0x180035ef5  cmp     r13d, 2
0x180035ef9  jb      loc_180035D6D
0x180035eff  mov     r15, [rbp+57h+arg_10]
0x180035f03  mov     rbx, [rbp+57h+arg_0]
0x180035f07  mov     rdi, [rbp+57h+arg_8]
0x180035f0b  mov     rax, [rbp+57h+arg_18]
0x180035f0f  mov     rdx, rax; hDC
0x180035f12  xor     ecx, ecx; hWnd
0x180035f14  call    cs:__imp_ReleaseDC
0x180035f1a  lea     rcx, g_csDll; lpCriticalSection
0x180035f21  call    cs:__imp_LeaveCriticalSection
0x180035f27  test    r12, r12
0x180035f2a  jz      short loc_180035F41
0x180035f2c  mov     rax, qword ptr [rbp+57h+var_90]
0x180035f30  test    rax, rax
0x180035f33  jz      short loc_180035F41
0x180035f35  mov     rcx, r12; hIcon
0x180035f38  mov     [rbx], rax
0x180035f3b  call    cs:__imp_DestroyIcon
0x180035f41  test    r15, r15
0x180035f44  jz      short loc_180035F60
0x180035f46  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x180035f4a  test    rcx, rcx
0x180035f4d  jz      short loc_180035F60
0x180035f4f  mov     [rdi], rcx
0x180035f52  cmp     r15, r12
0x180035f55  jz      short loc_180035F60
0x180035f57  mov     rcx, r15; hIcon
0x180035f5a  call    cs:__imp_DestroyIcon
0x180035f60  mov     eax, 1
0x180035f65  add     rsp, 0B8h
0x180035f6c  pop     r15
0x180035f6e  pop     r14
0x180035f70  pop     r13
0x180035f72  pop     r12
0x180035f74  pop     rdi
0x180035f75  pop     rsi
0x180035f76  pop     rbx
0x180035f77  pop     rbp
0x180035f78  retn
```
