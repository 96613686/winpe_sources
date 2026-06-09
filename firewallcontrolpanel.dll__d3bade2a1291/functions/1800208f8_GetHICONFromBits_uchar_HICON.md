# GetHICONFromBits(uchar *,HICON__ * *)

- ea: `0x1800208f8`
- end: `0x180020ae4`
- name: `?GetHICONFromBits@@YAJPEAEPEAPEAUHICON__@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(unsigned __int8 *, HICON *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020aec`

## callees

- `0x1800208f8`
- `0x180030ea0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a88`
- `USER32!GetActiveWindow` at `0x18002095c`
- `USER32!GetActiveWindow` at `0x18002095c`
- `USER32!CreateIconIndirect` at `0x180020a5f`
- `USER32!CreateIconIndirect` at `0x180020a5f`
- `USER32!GetDC` at `0x180020968`
- `USER32!GetDC` at `0x180020968`
- `USER32!ReleaseDC` at `0x180020a80`
- `USER32!ReleaseDC` at `0x180020a80`
- `GDI32!CreateBitmapIndirect` at `0x180020a3b`
- `GDI32!CreateBitmapIndirect` at `0x180020a3b`
- `GDI32!SetDIBits` at `0x1800209f7`
- `GDI32!SetDIBits` at `0x1800209f7`
- `GDI32!DeleteObject` at `0x180020a99`
- `GDI32!DeleteObject` at `0x180020aa8`
- `GDI32!DeleteObject` at `0x180020a99`
- `GDI32!DeleteObject` at `0x180020aa8`
- `GDI32!CreateCompatibleBitmap` at `0x180020984`
- `GDI32!CreateCompatibleBitmap` at `0x180020984`

## pseudocode

```c
__int64 __fastcall GetHICONFromBits(unsigned __int8 *a1, HICON *a2)
{
  int v4; // r14d
  int v5; // r12d
  int v6; // r13d
  HWND ActiveWindow; // r15
  HDC DC; // rax
  HDC v9; // rdi
  UINT v10; // r9d
  DWORD v11; // r14d
  HICON v12; // rax
  signed int LastError; // ebx
  BITMAP pbm; // [rsp+40h] [rbp-59h] BYREF
  ICONINFO piconinfo; // [rsp+60h] [rbp-39h] BYREF
  BITMAPINFO bmi; // [rsp+80h] [rbp-19h] BYREF

  *a2 = 0;
  v4 = *((unsigned __int16 *)a1 + 14);
  v5 = *((_DWORD *)a1 + 6);
  v6 = *((_DWORD *)a1 + 5);
  memset(&pbm, 0, sizeof(pbm));
  memset(&bmi, 0, sizeof(bmi));
  memset(&piconinfo, 0, sizeof(piconinfo));
  ActiveWindow = GetActiveWindow();
  DC = GetDC(ActiveWindow);
  v9 = DC;
  if ( DC )
  {
    piconinfo.hbmColor = CreateCompatibleBitmap(DC, *((_DWORD *)a1 + 4), *((_DWORD *)a1 + 5));
    if ( !piconinfo.hbmColor )
      goto LABEL_7;
    v10 = *((_DWORD *)a1 + 5);
    bmi.bmiHeader.biWidth = *((_DWORD *)a1 + 4);
    bmi.bmiHeader.biPlanes = *((_WORD *)a1 + 14);
    bmi.bmiHeader.biBitCount = *((_WORD *)a1 + 15);
    bmi.bmiHeader.biSize = 40;
    v11 = v6 * v5 * v4;
    bmi.bmiHeader.biHeight = v10;
    bmi.bmiHeader.biCompression = 0;
    *(_QWORD *)&bmi.bmiHeader.biXPelsPerMeter = 0;
    *(_QWORD *)&bmi.bmiHeader.biClrUsed = 0;
    bmi.bmiHeader.biSizeImage = v11;
    if ( !SetDIBits(v9, piconinfo.hbmColor, 0, v10, a1 + 52, &bmi, 0) )
      goto LABEL_7;
    pbm.bmType = *((_DWORD *)a1 + 8);
    pbm.bmWidth = *((_DWORD *)a1 + 9);
    pbm.bmHeight = *((_DWORD *)a1 + 10);
    pbm.bmBitsPixel = *((_WORD *)a1 + 25);
    pbm.bmWidthBytes = *((_DWORD *)a1 + 11);
    pbm.bmPlanes = *((_WORD *)a1 + 24);
    pbm.bmBits = &a1[v11 + 52];
    piconinfo.hbmMask = CreateBitmapIndirect(&pbm);
    if ( !piconinfo.hbmMask )
      goto LABEL_7;
    piconinfo.fIcon = *(_DWORD *)a1;
    piconinfo.xHotspot = *((_DWORD *)a1 + 1);
    piconinfo.yHotspot = *((_DWORD *)a1 + 2);
    v12 = CreateIconIndirect(&piconinfo);
    if ( v12 )
    {
      *a2 = v12;
      LastError = 0;
    }
    else
    {
LABEL_7:
      LastError = GetLastError();
    }
    ReleaseDC(ActiveWindow, v9);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( piconinfo.hbmColor )
    DeleteObject(piconinfo.hbmColor);
  if ( piconinfo.hbmMask )
    DeleteObject(piconinfo.hbmMask);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800208f8  mov     [rsp-8+arg_10], rbx
0x1800208fd  push    rbp
0x1800208fe  push    rsi
0x1800208ff  push    rdi
0x180020900  push    r12
0x180020902  push    r13
0x180020904  push    r14
0x180020906  push    r15
0x180020908  lea     rbp, [rsp-27h]
0x18002090d  sub     rsp, 0C0h
0x180020914  mov     rax, cs:__security_cookie
0x18002091b  xor     rax, rsp
0x18002091e  mov     [rbp+57h+var_40], rax
0x180020922  xorps   xmm0, xmm0
0x180020925  xorps   xmm1, xmm1
0x180020928  xor     eax, eax
0x18002092a  mov     rsi, rdx
0x18002092d  mov     [rdx], rax
0x180020930  mov     rbx, rcx
0x180020933  movzx   r14d, word ptr [rcx+1Ch]
0x180020938  mov     r12d, [rcx+18h]
0x18002093c  mov     r13d, [rcx+14h]
0x180020940  movups  xmmword ptr [rbp+57h+bmi.bmiHeader.biCompression], xmm1
0x180020944  movups  xmmword ptr [rbp+57h+bmi.bmiHeader.biYPelsPerMeter], xmm1
0x180020948  movups  xmmword ptr [rbp+57h+pbm.bmType], xmm0
0x18002094c  movups  xmmword ptr [rbp+57h+pbm.bmPlanes], xmm0
0x180020950  movups  xmmword ptr [rbp+57h+bmi.bmiHeader.biSize], xmm1
0x180020954  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x180020958  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x18002095c  call    cs:__imp_GetActiveWindow
0x180020962  mov     rcx, rax; hWnd
0x180020965  mov     r15, rax
0x180020968  call    cs:__imp_GetDC
0x18002096e  mov     rdi, rax
0x180020971  test    rax, rax
0x180020974  jz      loc_180020A88
0x18002097a  mov     r8d, [rbx+14h]; cy
0x18002097e  mov     rcx, rax; hdc
0x180020981  mov     edx, [rbx+10h]; cx
0x180020984  call    cs:__imp_CreateCompatibleBitmap
0x18002098a  mov     [rbp+57h+piconinfo.hbmColor], rax
0x18002098e  mov     rdx, rax; hbm
0x180020991  test    rax, rax
0x180020994  jz      loc_180020A72
0x18002099a  mov     eax, [rbx+10h]
0x18002099d  lea     rcx, [rbp+57h+bmi]
0x1800209a1  mov     r9d, [rbx+14h]; cLines
0x1800209a5  xor     r8d, r8d; start
0x1800209a8  mov     [rbp+57h+bmi.bmiHeader.biWidth], eax
0x1800209ab  movzx   eax, word ptr [rbx+1Ch]
0x1800209af  mov     [rbp+57h+bmi.bmiHeader.biPlanes], ax
0x1800209b3  movzx   eax, word ptr [rbx+1Eh]
0x1800209b7  imul    r14d, r12d
0x1800209bb  xor     r12d, r12d
0x1800209be  mov     [rbp+57h+bmi.bmiHeader.biBitCount], ax
0x1800209c2  lea     rax, [rbx+34h]
0x1800209c6  mov     [rsp+0F0h+ColorUse], r12d; ColorUse
0x1800209cb  mov     [rsp+0F0h+lpbmi], rcx; lpbmi
0x1800209d0  mov     rcx, rdi; hdc
0x1800209d3  mov     [rbp+57h+bmi.bmiHeader.biSize], 28h ; '('
0x1800209da  imul    r14d, r13d
0x1800209de  mov     [rbp+57h+bmi.bmiHeader.biHeight], r9d
0x1800209e2  mov     [rbp+57h+bmi.bmiHeader.biCompression], r12d
0x1800209e6  mov     qword ptr [rbp+57h+bmi.bmiHeader.biXPelsPerMeter], r12
0x1800209ea  mov     qword ptr [rbp+57h+bmi.bmiHeader.biClrUsed], r12
0x1800209ee  mov     [rbp+57h+bmi.bmiHeader.biSizeImage], r14d
0x1800209f2  mov     [rsp+0F0h+lpBits], rax; lpBits
0x1800209f7  call    cs:__imp_SetDIBits
0x1800209fd  test    eax, eax
0x1800209ff  jz      short loc_180020A72
0x180020a01  mov     eax, [rbx+20h]
0x180020a04  mov     [rbp+57h+pbm.bmType], eax
0x180020a07  mov     eax, [rbx+24h]
0x180020a0a  mov     [rbp+57h+pbm.bmWidth], eax
0x180020a0d  mov     eax, [rbx+28h]
0x180020a10  mov     [rbp+57h+pbm.bmHeight], eax
0x180020a13  movzx   eax, word ptr [rbx+32h]
0x180020a17  mov     [rbp+57h+pbm.bmBitsPixel], ax
0x180020a1b  mov     eax, [rbx+2Ch]
0x180020a1e  mov     [rbp+57h+pbm.bmWidthBytes], eax
0x180020a21  movzx   eax, word ptr [rbx+30h]
0x180020a25  mov     ecx, r14d
0x180020a28  add     rcx, 34h ; '4'
0x180020a2c  mov     [rbp+57h+pbm.bmPlanes], ax
0x180020a30  add     rcx, rbx
0x180020a33  mov     [rbp+57h+pbm.bmBits], rcx
0x180020a37  lea     rcx, [rbp+57h+pbm]; pbm
0x180020a3b  call    cs:__imp_CreateBitmapIndirect
0x180020a41  mov     [rbp+57h+piconinfo.hbmMask], rax
0x180020a45  test    rax, rax
0x180020a48  jz      short loc_180020A72
0x180020a4a  mov     eax, [rbx]
0x180020a4c  lea     rcx, [rbp+57h+piconinfo]; piconinfo
0x180020a50  mov     [rbp+57h+piconinfo.fIcon], eax
0x180020a53  mov     eax, [rbx+4]
0x180020a56  mov     [rbp+57h+piconinfo.xHotspot], eax
0x180020a59  mov     eax, [rbx+8]
0x180020a5c  mov     [rbp+57h+piconinfo.yHotspot], eax
0x180020a5f  call    cs:__imp_CreateIconIndirect
0x180020a65  test    rax, rax
0x180020a68  jz      short loc_180020A72
0x180020a6a  mov     [rsi], rax
0x180020a6d  mov     ebx, r12d
0x180020a70  jmp     short loc_180020A7A
0x180020a72  call    cs:__imp_GetLastError
0x180020a78  mov     ebx, eax
0x180020a7a  mov     rdx, rdi; hDC
0x180020a7d  mov     rcx, r15; hWnd
0x180020a80  call    cs:__imp_ReleaseDC
0x180020a86  jmp     short loc_180020A90
0x180020a88  call    cs:__imp_GetLastError
0x180020a8e  mov     ebx, eax
0x180020a90  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x180020a94  test    rcx, rcx
0x180020a97  jz      short loc_180020A9F
0x180020a99  call    cs:__imp_DeleteObject
0x180020a9f  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x180020aa3  test    rcx, rcx
0x180020aa6  jz      short loc_180020AAE
0x180020aa8  call    cs:__imp_DeleteObject
0x180020aae  test    ebx, ebx
0x180020ab0  jle     short loc_180020ABB
0x180020ab2  movzx   ebx, bx
0x180020ab5  or      ebx, 80070000h
0x180020abb  mov     eax, ebx
0x180020abd  mov     rcx, [rbp+57h+var_40]
0x180020ac1  xor     rcx, rsp; StackCookie
0x180020ac4  call    __security_check_cookie
0x180020ac9  mov     rbx, [rsp+0F0h+arg_10]
0x180020ad1  add     rsp, 0C0h
0x180020ad8  pop     r15
0x180020ada  pop     r14
0x180020adc  pop     r13
0x180020ade  pop     r12
0x180020ae0  pop     rdi
0x180020ae1  pop     rsi
0x180020ae2  pop     rbp
0x180020ae3  retn
```
