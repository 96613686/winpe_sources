# CDither::DitherDeviceInit(tagBITMAPINFOHEADER *)

- ea: `0x18009bb84`
- end: `0x18009bec7`
- name: `?DitherDeviceInit@CDither@@AEAAHPEAUtagBITMAPINFOHEADER@@@Z`
- size: `835`
- prototype: `__int64 __fastcall(CDither *__hidden this, struct tagBITMAPINFOHEADER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009c0a0`

## callees

- `0x1800388a0`
- `0x18009bb84`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x18009bc77`
- `KERNEL32!GlobalUnlock` at `0x18009be95`
- `KERNEL32!GlobalUnlock` at `0x18009bc77`
- `KERNEL32!GlobalUnlock` at `0x18009be95`
- `KERNEL32!GlobalLock` at `0x18009bbda`
- `KERNEL32!GlobalLock` at `0x18009bbda`
- `KERNEL32!GlobalFree` at `0x18009bc95`
- `KERNEL32!GlobalFree` at `0x18009beb3`
- `KERNEL32!GlobalFree` at `0x18009bc95`
- `KERNEL32!GlobalFree` at `0x18009beb3`
- `KERNEL32!GlobalAlloc` at `0x18009bbcb`
- `KERNEL32!GlobalAlloc` at `0x18009bbcb`
- `KERNEL32!GlobalHandle` at `0x18009bc68`
- `KERNEL32!GlobalHandle` at `0x18009bc86`
- `KERNEL32!GlobalHandle` at `0x18009be86`
- `KERNEL32!GlobalHandle` at `0x18009bea4`
- `KERNEL32!GlobalHandle` at `0x18009bc68`
- `KERNEL32!GlobalHandle` at `0x18009bc86`
- `KERNEL32!GlobalHandle` at `0x18009be86`
- `KERNEL32!GlobalHandle` at `0x18009bea4`
- `GDI32!DeleteObject` at `0x18009bd81`
- `GDI32!DeleteObject` at `0x18009be2d`
- `GDI32!DeleteObject` at `0x18009bd81`
- `GDI32!DeleteObject` at `0x18009be2d`
- `GDI32!CreateSolidBrush` at `0x18009bd18`
- `GDI32!CreateSolidBrush` at `0x18009bd18`
- `GDI32!DeleteDC` at `0x18009bc48`
- `GDI32!DeleteDC` at `0x18009bdb8`
- `GDI32!DeleteDC` at `0x18009bc48`
- `GDI32!DeleteDC` at `0x18009bdb8`
- `GDI32!GetDIBits` at `0x18009be1e`
- `GDI32!GetDIBits` at `0x18009be1e`
- `GDI32!PatBlt` at `0x18009bd60`
- `GDI32!PatBlt` at `0x18009bd60`
- `GDI32!CreateCompatibleDC` at `0x18009bc0b`
- `GDI32!CreateCompatibleDC` at `0x18009bc0b`
- `GDI32!SelectObject` at `0x18009bcd1`
- `GDI32!SelectObject` at `0x18009bd2f`
- `GDI32!SelectObject` at `0x18009bd72`
- `GDI32!SelectObject` at `0x18009bda9`
- `GDI32!SelectObject` at `0x18009bcd1`
- `GDI32!SelectObject` at `0x18009bd2f`
- `GDI32!SelectObject` at `0x18009bd72`
- `GDI32!SelectObject` at `0x18009bda9`
- `GDI32!CreateCompatibleBitmap` at `0x18009bc2d`
- `GDI32!CreateCompatibleBitmap` at `0x18009bc2d`
- `USER32!ReleaseDC` at `0x18009bc59`
- `USER32!ReleaseDC` at `0x18009be3e`
- `USER32!ReleaseDC` at `0x18009bc59`
- `USER32!ReleaseDC` at `0x18009be3e`
- `USER32!GetDC` at `0x18009bbf4`
- `USER32!GetDC` at `0x18009bbf4`

## pseudocode

```c
__int64 __fastcall CDither::DitherDeviceInit(CDither *this, struct tagBITMAPINFOHEADER *a2)
{
  struct tagBITMAPINFOHEADER *v2; // rbx
  HGLOBAL v3; // rax
  void *v4; // rdi
  HDC DC; // rax
  HDC v6; // rsi
  HDC CompatibleDC; // r14
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v9; // r13
  HGLOBAL v10; // rax
  HGLOBAL v11; // rax
  HGDIOBJ v13; // rax
  int biClrUsed; // r12d
  int v15; // r15d
  HBRUSH SolidBrush; // rax
  HGDIOBJ v17; // rbx
  HGDIOBJ v18; // rax
  int i; // r8d
  unsigned __int8 v20; // dl
  __int64 v21; // rcx
  HGLOBAL v22; // rax
  HGLOBAL v23; // rax
  HGDIOBJ v25; // [rsp+48h] [rbp-B8h]
  tagBITMAPINFO bmi; // [rsp+60h] [rbp-A0h] BYREF

  v2 = a2;
  v3 = GlobalAlloc(0x42u, 0x2000u);
  v4 = GlobalLock(v3);
  if ( !v4 )
    return 0;
  DC = GetDC(0);
  v6 = DC;
  if ( !DC )
  {
LABEL_7:
    v10 = GlobalHandle(v4);
    GlobalUnlock(v10);
    v11 = GlobalHandle(v4);
    GlobalFree(v11);
    return 0;
  }
  CompatibleDC = CreateCompatibleDC(DC);
  if ( !CompatibleDC )
  {
LABEL_6:
    ReleaseDC(0, v6);
    goto LABEL_7;
  }
  CompatibleBitmap = CreateCompatibleBitmap(v6, 2048, 8);
  v9 = CompatibleBitmap;
  if ( !CompatibleBitmap )
  {
    DeleteDC(CompatibleDC);
    goto LABEL_6;
  }
  v13 = SelectObject(CompatibleDC, CompatibleBitmap);
  biClrUsed = v2->biClrUsed;
  v15 = 0;
  v25 = v13;
  if ( !biClrUsed )
  {
    biClrUsed = 256;
    do
    {
LABEL_12:
      SolidBrush = CreateSolidBrush(
                     *((unsigned __int8 *)&v2[1].biSize + 4 * v15 + 2)
                   | (*((unsigned __int8 *)&v2[1].biSize + 4 * v15) << 16)
                   | (*((unsigned __int8 *)&v2[1].biSize + 4 * v15 + 1) << 8));
      if ( SolidBrush )
      {
        v17 = SelectObject(CompatibleDC, SolidBrush);
        PatBlt(CompatibleDC, 8 * v15, 0, 8, 8, 0xF00021u);
        v18 = SelectObject(CompatibleDC, v17);
        DeleteObject(v18);
        v2 = a2;
      }
      ++v15;
    }
    while ( v15 < biClrUsed );
    v13 = v25;
    goto LABEL_16;
  }
  if ( biClrUsed > 0 )
    goto LABEL_12;
LABEL_16:
  SelectObject(CompatibleDC, v13);
  DeleteDC(CompatibleDC);
  bmi.bmiHeader.biSize = 40;
  *(_DWORD *)&bmi.bmiHeader.biPlanes = 262145;
  bmi.bmiHeader.biWidth = 2048;
  bmi.bmiHeader.biCompression = 0;
  *(_QWORD *)&bmi.bmiHeader.biSizeImage = 0x2000;
  bmi.bmiHeader.biHeight = 8;
  *(_QWORD *)&bmi.bmiHeader.biYPelsPerMeter = 0;
  bmi.bmiHeader.biClrImportant = 0;
  GetDIBits(v6, v9, 0, 8u, v4, &bmi, 0);
  DeleteObject(v9);
  ReleaseDC(0, v6);
  for ( i = 0; i < 0x2000; ++i )
  {
    v20 = *((_BYTE *)v4 + (unsigned int)i);
    v21 = 2 * i;
    *((_BYTE *)this + v21 + 232) = v20 >> 4;
    *((_BYTE *)this + v21 + 233) = v20 & 0xF;
  }
  v22 = GlobalHandle(v4);
  GlobalUnlock(v22);
  v23 = GlobalHandle(v4);
  GlobalFree(v23);
  return 1;
}

```

## disassembly

```asm
0x18009bb84  mov     [rsp-8+arg_10], rbx
0x18009bb89  push    rbp
0x18009bb8a  push    rsi
0x18009bb8b  push    rdi
0x18009bb8c  push    r12
0x18009bb8e  push    r13
0x18009bb90  push    r14
0x18009bb92  push    r15
0x18009bb94  lea     rbp, [rsp-3A0h]
0x18009bb9c  sub     rsp, 4A0h
0x18009bba3  mov     rax, cs:__security_cookie
0x18009bbaa  xor     rax, rsp
0x18009bbad  mov     [rbp+3D0h+var_40], rax
0x18009bbb4  mov     rbx, rdx
0x18009bbb7  mov     [rsp+4D0h+var_490], rdx
0x18009bbbc  mov     [rsp+4D0h+var_480], rcx
0x18009bbc1  mov     edx, 2000h; dwBytes
0x18009bbc6  mov     ecx, 42h ; 'B'; uFlags
0x18009bbcb  call    cs:__imp_GlobalAlloc
0x18009bbd2  nop     dword ptr [rax+rax+00h]
0x18009bbd7  mov     rcx, rax; hMem
0x18009bbda  call    cs:__imp_GlobalLock
0x18009bbe1  nop     dword ptr [rax+rax+00h]
0x18009bbe6  mov     rdi, rax
0x18009bbe9  test    rax, rax
0x18009bbec  jz      loc_18009BCA1
0x18009bbf2  xor     ecx, ecx; hWnd
0x18009bbf4  call    cs:__imp_GetDC
0x18009bbfb  nop     dword ptr [rax+rax+00h]
0x18009bc00  mov     rsi, rax
0x18009bc03  test    rax, rax
0x18009bc06  jz      short loc_18009BC65
0x18009bc08  mov     rcx, rax; hdc
0x18009bc0b  call    cs:__imp_CreateCompatibleDC
0x18009bc12  nop     dword ptr [rax+rax+00h]
0x18009bc17  mov     r14, rax
0x18009bc1a  test    rax, rax
0x18009bc1d  jz      short loc_18009BC54
0x18009bc1f  mov     edx, 800h; cx
0x18009bc24  mov     r8d, 8; cy
0x18009bc2a  mov     rcx, rsi; hdc
0x18009bc2d  call    cs:__imp_CreateCompatibleBitmap
0x18009bc34  nop     dword ptr [rax+rax+00h]
0x18009bc39  mov     r13, rax
0x18009bc3c  mov     rcx, r14; hdc
0x18009bc3f  test    rax, rax
0x18009bc42  jnz     loc_18009BCCE
0x18009bc48  call    cs:__imp_DeleteDC
0x18009bc4f  nop     dword ptr [rax+rax+00h]
0x18009bc54  mov     rdx, rsi; hDC
0x18009bc57  xor     ecx, ecx; hWnd
0x18009bc59  call    cs:__imp_ReleaseDC
0x18009bc60  nop     dword ptr [rax+rax+00h]
0x18009bc65  mov     rcx, rdi; pMem
0x18009bc68  call    cs:__imp_GlobalHandle
0x18009bc6f  nop     dword ptr [rax+rax+00h]
0x18009bc74  mov     rcx, rax; hMem
0x18009bc77  call    cs:__imp_GlobalUnlock
0x18009bc7e  nop     dword ptr [rax+rax+00h]
0x18009bc83  mov     rcx, rdi; pMem
0x18009bc86  call    cs:__imp_GlobalHandle
0x18009bc8d  nop     dword ptr [rax+rax+00h]
0x18009bc92  mov     rcx, rax; hMem
0x18009bc95  call    cs:__imp_GlobalFree
0x18009bc9c  nop     dword ptr [rax+rax+00h]
0x18009bca1  xor     eax, eax
0x18009bca3  mov     rcx, [rbp+3D0h+var_40]
0x18009bcaa  xor     rcx, rsp; StackCookie
0x18009bcad  call    __security_check_cookie
0x18009bcb2  mov     rbx, [rsp+4D0h+arg_10]
0x18009bcba  add     rsp, 4A0h
0x18009bcc1  pop     r15
0x18009bcc3  pop     r14
0x18009bcc5  pop     r13
0x18009bcc7  pop     r12
0x18009bcc9  pop     rdi
0x18009bcca  pop     rsi
0x18009bccb  pop     rbp
0x18009bccc  retn
0x18009bcce  mov     rdx, r13; h
0x18009bcd1  call    cs:__imp_SelectObject
0x18009bcd8  nop     dword ptr [rax+rax+00h]
0x18009bcdd  mov     r12d, [rbx+20h]
0x18009bce1  xor     r15d, r15d
0x18009bce4  mov     [rsp+4D0h+var_488], rax
0x18009bce9  test    r12d, r12d
0x18009bcec  jnz     short loc_18009BCF6
0x18009bcee  mov     r12d, 100h
0x18009bcf4  jmp     short loc_18009BCFC
0x18009bcf6  jle     loc_18009BDA3
0x18009bcfc  movsxd  rdx, r15d
0x18009bcff  movzx   ecx, byte ptr [rbx+rdx*4+29h]
0x18009bd04  movzx   eax, byte ptr [rbx+rdx*4+28h]
0x18009bd09  shl     ecx, 8
0x18009bd0c  shl     eax, 10h
0x18009bd0f  or      ecx, eax
0x18009bd11  movzx   eax, byte ptr [rbx+rdx*4+2Ah]
0x18009bd16  or      ecx, eax; color
0x18009bd18  call    cs:__imp_CreateSolidBrush
0x18009bd1f  nop     dword ptr [rax+rax+00h]
0x18009bd24  test    rax, rax
0x18009bd27  jz      short loc_18009BD92
0x18009bd29  mov     rdx, rax; h
0x18009bd2c  mov     rcx, r14; hdc
0x18009bd2f  call    cs:__imp_SelectObject
0x18009bd36  nop     dword ptr [rax+rax+00h]
0x18009bd3b  lea     edx, ds:0[r15*8]; x
0x18009bd43  mov     [rsp+4D0h+rop], 0F00021h; rop
0x18009bd4b  mov     rbx, rax
0x18009bd4e  xor     r8d, r8d; y
0x18009bd51  mov     eax, 8
0x18009bd56  mov     rcx, r14; hdc
0x18009bd59  mov     r9d, eax; w
0x18009bd5c  mov     [rsp+4D0h+h], eax; h
0x18009bd60  call    cs:__imp_PatBlt
0x18009bd67  nop     dword ptr [rax+rax+00h]
0x18009bd6c  mov     rdx, rbx; h
0x18009bd6f  mov     rcx, r14; hdc
0x18009bd72  call    cs:__imp_SelectObject
0x18009bd79  nop     dword ptr [rax+rax+00h]
0x18009bd7e  mov     rcx, rax; ho
0x18009bd81  call    cs:__imp_DeleteObject
0x18009bd88  nop     dword ptr [rax+rax+00h]
0x18009bd8d  mov     rbx, [rsp+4D0h+var_490]
0x18009bd92  inc     r15d
0x18009bd95  cmp     r15d, r12d
0x18009bd98  jl      loc_18009BCFC
0x18009bd9e  mov     rax, [rsp+4D0h+var_488]
0x18009bda3  mov     rdx, rax; h
0x18009bda6  mov     rcx, r14; hdc
0x18009bda9  call    cs:__imp_SelectObject
0x18009bdb0  nop     dword ptr [rax+rax+00h]
0x18009bdb5  mov     rcx, r14; hdc
0x18009bdb8  call    cs:__imp_DeleteDC
0x18009bdbf  nop     dword ptr [rax+rax+00h]
0x18009bdc4  xor     ebx, ebx
0x18009bdc6  mov     [rsp+4D0h+bmi.bmiHeader.biSize], 28h ; '('
0x18009bdce  lea     rax, [rsp+4D0h+bmi]
0x18009bdd3  mov     [rsp+4D0h+usage], ebx; usage
0x18009bdd7  mov     qword ptr [rsp+4D0h+rop], rax; lpbmi
0x18009bddc  mov     r14d, 1
0x18009bde2  xor     r8d, r8d; start
0x18009bde5  mov     dword ptr [rsp+4D0h+bmi.bmiHeader.biPlanes], 40001h
0x18009bded  mov     rdx, r13; hbm
0x18009bdf0  mov     [rsp+4D0h+bmi.bmiHeader.biWidth], 800h
0x18009bdf8  mov     rcx, rsi; hdc
0x18009bdfb  mov     [rsp+4D0h+bmi.bmiHeader.biCompression], ebx
0x18009bdff  lea     r9d, [r14+7]; cLines
0x18009be03  mov     qword ptr [rsp+4D0h+bmi.bmiHeader.biSizeImage], 2000h
0x18009be0c  mov     [rsp+4D0h+bmi.bmiHeader.biHeight], r9d
0x18009be11  mov     qword ptr [rsp+4D0h+bmi.bmiHeader.biYPelsPerMeter], rbx
0x18009be16  mov     [rbp+3D0h+bmi.bmiHeader.biClrImportant], ebx
0x18009be19  mov     qword ptr [rsp+4D0h+h], rdi; lpvBits
0x18009be1e  call    cs:__imp_GetDIBits
0x18009be25  nop     dword ptr [rax+rax+00h]
0x18009be2a  mov     rcx, r13; ho
0x18009be2d  call    cs:__imp_DeleteObject
0x18009be34  nop     dword ptr [rax+rax+00h]
0x18009be39  mov     rdx, rsi; hDC
0x18009be3c  xor     ecx, ecx; hWnd
0x18009be3e  call    cs:__imp_ReleaseDC
0x18009be45  nop     dword ptr [rax+rax+00h]
0x18009be4a  mov     r9, [rsp+4D0h+var_480]
0x18009be4f  mov     r8d, ebx
0x18009be52  mov     eax, r8d
0x18009be55  mov     dl, [rax+rdi]
0x18009be58  lea     eax, [r8+r8]
0x18009be5c  movsxd  rcx, eax
0x18009be5f  add     r8d, r14d
0x18009be62  mov     al, dl
0x18009be64  and     dl, 0Fh
0x18009be67  shr     al, 4
0x18009be6a  mov     [rcx+r9+0E8h], al
0x18009be72  mov     [rcx+r9+0E9h], dl
0x18009be7a  cmp     r8d, 2000h
0x18009be81  jl      short loc_18009BE52
0x18009be83  mov     rcx, rdi; pMem
0x18009be86  call    cs:__imp_GlobalHandle
0x18009be8d  nop     dword ptr [rax+rax+00h]
0x18009be92  mov     rcx, rax; hMem
0x18009be95  call    cs:__imp_GlobalUnlock
0x18009be9c  nop     dword ptr [rax+rax+00h]
0x18009bea1  mov     rcx, rdi; pMem
0x18009bea4  call    cs:__imp_GlobalHandle
0x18009beab  nop     dword ptr [rax+rax+00h]
0x18009beb0  mov     rcx, rax; hMem
0x18009beb3  call    cs:__imp_GlobalFree
0x18009beba  nop     dword ptr [rax+rax+00h]
0x18009bebf  mov     eax, r14d
0x18009bec2  jmp     loc_18009BCA3
```
