# TBGenerateDragImage

- ea: `0x180026cc4`
- end: `0x180026ef8`
- name: `TBGenerateDragImage`
- size: `564`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002aab0`

## callees

- `0x1800115f0`
- `0x1800243a4`
- `0x180026cc4`
- `0x1800293b4`
- `0x180029ac4`
- `0x180036e24`
- `0x180042570`
- `0x18008ea60`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180026d18`
- `GDI32!CreateCompatibleDC` at `0x180026d18`
- `GDI32!SelectObject` at `0x180026dee`
- `GDI32!SelectObject` at `0x180026eb8`
- `GDI32!SelectObject` at `0x180026dee`
- `GDI32!SelectObject` at `0x180026eb8`
- `GDI32!GetDeviceCaps` at `0x180026d94`
- `GDI32!GetDeviceCaps` at `0x180026da4`
- `GDI32!GetDeviceCaps` at `0x180026d94`
- `GDI32!GetDeviceCaps` at `0x180026da4`
- `GDI32!SetLayout` at `0x180026d3c`
- `GDI32!SetLayout` at `0x180026d3c`
- `GDI32!DeleteDC` at `0x180026ec1`
- `GDI32!DeleteDC` at `0x180026ec1`
- `GDI32!CreateBitmap` at `0x180026dbd`
- `GDI32!CreateBitmap` at `0x180026dbd`
- `USER32!PtInRect` at `0x180026e7d`
- `USER32!PtInRect` at `0x180026e7d`

## pseudocode

```c
__int64 __fastcall TBGenerateDragImage(__int64 a1, __int64 a2)
{
  HDC CompatibleDC; // rax
  HDC v5; // r15
  int v6; // eax
  int v7; // edi
  int v8; // esi
  UINT DeviceCaps; // ebx
  UINT v10; // eax
  HBITMAP Bitmap; // rax
  HGDIOBJ v12; // rax
  void *v13; // rdi
  int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  _QWORD v19[20]; // [rsp+30h] [rbp-89h] BYREF
  RECT rc; // [rsp+D0h] [rbp+17h] BYREF

  memset(v19, 0, 0x98u);
  if ( *(_DWORD *)(a1 + 284) == -1 )
    return 0;
  CompatibleDC = CreateCompatibleDC(0);
  v5 = CompatibleDC;
  if ( !CompatibleDC )
    return 0;
  if ( (*(_DWORD *)(a1 + 32) & 0x400000) != 0 )
    SetLayout(CompatibleDC, 1u);
  v19[4] = v5;
  *(_DWORD *)(a1 + 20) = CICustomDrawNotify(a1, 1, v19);
  v6 = TBWidthOfButton(a1, *(_QWORD *)(a1 + 80) + 40LL * *(int *)(a1 + 284), v5);
  *(_DWORD *)a2 = v6;
  v7 = *(_DWORD *)(a1 + 184);
  *(_DWORD *)(a2 + 4) = v7;
  v8 = v6;
  DeviceCaps = GetDeviceCaps(v5, 12);
  v10 = GetDeviceCaps(v5, 14);
  Bitmap = CreateBitmap(v8, v7, v10, DeviceCaps, 0);
  *(_QWORD *)(a2 + 16) = Bitmap;
  if ( !Bitmap )
    return 0;
  rc.right = *(_DWORD *)a2;
  rc.bottom = *(_DWORD *)(a2 + 4);
  *(_QWORD *)&rc.left = 0;
  v12 = SelectObject(v5, Bitmap);
  *(_DWORD *)(a2 + 24) = 5570815;
  v13 = v12;
  FillRectClr(v5, &rc, 0x5500FFu);
  v14 = *(_DWORD *)(a1 + 16);
  v15 = *(_QWORD *)(a1 + 80);
  *(_DWORD *)(a1 + 316) &= ~0x20000u;
  *(_DWORD *)(a1 + 16) = v14 | 0x8000;
  DrawButton(v5, 0, 0, a1, v15 + 40LL * *(int *)(a1 + 284), 1);
  v16 = *(unsigned int *)(a1 + 284);
  *(_DWORD *)(a1 + 316) |= 0x20000u;
  *(_DWORD *)(a1 + 16) = v14;
  TB_GetItemRect(a1, v16, &rc);
  if ( PtInRect(&rc, *(POINT *)(a1 + 96)) )
  {
    if ( (*(_DWORD *)(a1 + 32) & 0x400000) != 0 )
      v17 = rc.right - *(_DWORD *)(a1 + 96);
    else
      v17 = *(_DWORD *)(a1 + 96) - rc.left;
    *(_DWORD *)(a2 + 8) = v17;
    *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 100) - rc.top;
  }
  SelectObject(v5, v13);
  DeleteDC(v5);
  return 1;
}

```

## disassembly

```asm
0x180026cc4  mov     [rsp-8+arg_10], rbx
0x180026cc9  mov     [rsp-8+arg_18], rsi
0x180026cce  push    rbp
0x180026ccf  push    rdi
0x180026cd0  push    r12
0x180026cd2  push    r14
0x180026cd4  push    r15
0x180026cd6  lea     rbp, [rsp-37h]
0x180026cdb  sub     rsp, 0F0h
0x180026ce2  mov     rax, cs:__security_cookie
0x180026ce9  xor     rax, rsp
0x180026cec  mov     [rbp+57h+var_30], rax
0x180026cf0  mov     r12, rdx
0x180026cf3  mov     r14, rcx
0x180026cf6  xor     edx, edx; Val
0x180026cf8  lea     rcx, [rsp+110h+var_E0]; void *
0x180026cfd  mov     r8d, 98h; Size
0x180026d03  call    memset
0x180026d08  cmp     dword ptr [r14+11Ch], 0FFFFFFFFh
0x180026d10  jz      loc_180026ECE
0x180026d16  xor     ecx, ecx; hdc
0x180026d18  call    cs:__imp_CreateCompatibleDC
0x180026d1e  mov     r15, rax
0x180026d21  test    rax, rax
0x180026d24  jz      loc_180026ECE
0x180026d2a  test    dword ptr [r14+20h], 400000h
0x180026d32  jz      short loc_180026D42
0x180026d34  mov     edx, 1; l
0x180026d39  mov     rcx, rax; hdc
0x180026d3c  call    cs:__imp_SetLayout
0x180026d42  lea     r8, [rsp+110h+var_E0]
0x180026d47  mov     [rbp+57h+var_C0], r15
0x180026d4b  mov     edx, 1
0x180026d50  mov     rcx, r14
0x180026d53  call    CICustomDrawNotify
0x180026d58  mov     [r14+14h], eax
0x180026d5c  mov     r8, r15
0x180026d5f  movsxd  rax, dword ptr [r14+11Ch]
0x180026d66  lea     rcx, [rax+rax*4]
0x180026d6a  mov     rax, [r14+50h]
0x180026d6e  lea     rdx, [rax+rcx*8]
0x180026d72  mov     rcx, r14
0x180026d75  call    TBWidthOfButton
0x180026d7a  mov     [r12], eax
0x180026d7e  mov     edx, 0Ch; index
0x180026d83  mov     edi, [r14+0B8h]
0x180026d8a  mov     rcx, r15; hdc
0x180026d8d  mov     [r12+4], edi
0x180026d92  mov     esi, eax
0x180026d94  call    cs:__imp_GetDeviceCaps
0x180026d9a  mov     edx, 0Eh; index
0x180026d9f  mov     rcx, r15; hdc
0x180026da2  mov     ebx, eax
0x180026da4  call    cs:__imp_GetDeviceCaps
0x180026daa  mov     r9d, ebx; nBitCount
0x180026dad  mov     [rsp+110h+lpBits], 0; lpBits
0x180026db6  mov     r8d, eax; nPlanes
0x180026db9  mov     edx, edi; nHeight
0x180026dbb  mov     ecx, esi; nWidth
0x180026dbd  call    cs:__imp_CreateBitmap
0x180026dc3  mov     [r12+10h], rax
0x180026dc8  test    rax, rax
0x180026dcb  jz      loc_180026ECE
0x180026dd1  mov     ecx, [r12]
0x180026dd5  mov     rdx, rax; h
0x180026dd8  mov     [rbp+57h+rc.right], ecx
0x180026ddb  mov     ecx, [r12+4]
0x180026de0  mov     [rbp+57h+rc.bottom], ecx
0x180026de3  mov     rcx, r15; hdc
0x180026de6  mov     qword ptr [rbp+57h+rc.left], 0
0x180026dee  call    cs:__imp_SelectObject
0x180026df4  mov     r8d, 5500FFh; color
0x180026dfa  lea     rdx, [rbp+57h+rc]; lprect
0x180026dfe  mov     rcx, r15; hdc
0x180026e01  mov     [r12+18h], r8d
0x180026e06  mov     rdi, rax
0x180026e09  call    FillRectClr
0x180026e0e  mov     ebx, [r14+10h]
0x180026e12  mov     r9, r14
0x180026e15  mov     rax, [r14+50h]
0x180026e19  mov     ecx, ebx
0x180026e1b  btr     dword ptr [r14+13Ch], 11h
0x180026e24  bts     ecx, 0Fh
0x180026e28  mov     [r14+10h], ecx
0x180026e2c  xor     r8d, r8d
0x180026e2f  movsxd  rcx, dword ptr [r14+11Ch]
0x180026e36  mov     [rsp+110h+var_E8], 1; int
0x180026e3e  lea     rdx, [rcx+rcx*4]
0x180026e42  lea     rcx, [rax+rdx*8]
0x180026e46  xor     edx, edx
0x180026e48  mov     [rsp+110h+lpBits], rcx; int
0x180026e4d  mov     rcx, r15; hdc
0x180026e50  call    DrawButton
0x180026e55  mov     edx, [r14+11Ch]
0x180026e5c  lea     r8, [rbp+57h+rc]
0x180026e60  bts     dword ptr [r14+13Ch], 11h
0x180026e69  mov     rcx, r14
0x180026e6c  mov     [r14+10h], ebx
0x180026e70  call    TB_GetItemRect
0x180026e75  mov     rdx, [r14+60h]; pt
0x180026e79  lea     rcx, [rbp+57h+rc]; lprc
0x180026e7d  call    cs:__imp_PtInRect
0x180026e83  test    eax, eax
0x180026e85  jz      short loc_180026EB2
0x180026e87  test    dword ptr [r14+20h], 400000h
0x180026e8f  jz      short loc_180026E9A
0x180026e91  mov     eax, [rbp+57h+rc.right]
0x180026e94  sub     eax, [r14+60h]
0x180026e98  jmp     short loc_180026EA1
0x180026e9a  mov     eax, [r14+60h]
0x180026e9e  sub     eax, [rbp+57h+rc.left]
0x180026ea1  mov     [r12+8], eax
0x180026ea6  mov     ecx, [r14+64h]
0x180026eaa  sub     ecx, [rbp+57h+rc.top]
0x180026ead  mov     [r12+0Ch], ecx
0x180026eb2  mov     rdx, rdi; h
0x180026eb5  mov     rcx, r15; hdc
0x180026eb8  call    cs:__imp_SelectObject
0x180026ebe  mov     rcx, r15; hdc
0x180026ec1  call    cs:__imp_DeleteDC
0x180026ec7  mov     eax, 1
0x180026ecc  jmp     short loc_180026ED0
0x180026ece  xor     eax, eax
0x180026ed0  mov     rcx, [rbp+57h+var_30]
0x180026ed4  xor     rcx, rsp; StackCookie
0x180026ed7  call    __security_check_cookie
0x180026edc  lea     r11, [rsp+110h+var_20]
0x180026ee4  mov     rbx, [r11+40h]
0x180026ee8  mov     rsi, [r11+48h]
0x180026eec  mov     rsp, r11
0x180026eef  pop     r15
0x180026ef1  pop     r14
0x180026ef3  pop     r12
0x180026ef5  pop     rdi
0x180026ef6  pop     rbp
0x180026ef7  retn
```
