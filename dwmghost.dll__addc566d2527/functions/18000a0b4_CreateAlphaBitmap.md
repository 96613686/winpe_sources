# CreateAlphaBitmap

- ea: `0x18000a0b4`
- end: `0x18000a2bc`
- name: `CreateAlphaBitmap`
- size: `520`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006538`
- `0x1800067a8`

## callees

- `0x180001190`
- `0x18000a0b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a21a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a21a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a139`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a139`
- `USER32!GetDC` at `0x18000a0fa`
- `USER32!GetDC` at `0x18000a0fa`
- `USER32!ReleaseDC` at `0x18000a28c`
- `USER32!ReleaseDC` at `0x18000a28c`
- `GDI32!CreateDIBSection` at `0x18000a205`
- `GDI32!CreateDIBSection` at `0x18000a27e`
- `GDI32!CreateDIBSection` at `0x18000a205`
- `GDI32!CreateDIBSection` at `0x18000a27e`
- `GDI32!CreateCompatibleBitmap` at `0x18000a118`
- `GDI32!CreateCompatibleBitmap` at `0x18000a118`
- `GDI32!GetDIBits` at `0x18000a16c`
- `GDI32!GetDIBits` at `0x18000a19f`
- `GDI32!GetDIBits` at `0x18000a16c`
- `GDI32!GetDIBits` at `0x18000a19f`
- `GDI32!DeleteObject` at `0x18000a223`
- `GDI32!DeleteObject` at `0x18000a223`

## pseudocode

```c
HBITMAP __fastcall CreateAlphaBitmap(LONG a1, LONG a2)
{
  HBITMAP v4; // rsi
  HDC DC; // rdi
  HBITMAP CompatibleBitmap; // r12
  struct tagBITMAPINFO *lpbmi; // rax
  struct tagBITMAPINFO *v8; // rbx
  int v9; // eax
  void *ppvBits; // [rsp+40h] [rbp-40h] BYREF
  BITMAPINFO pbmi; // [rsp+48h] [rbp-38h] BYREF

  v4 = 0;
  if ( a1 > 0 && a2 > 0 )
  {
    DC = GetDC(0);
    if ( DC )
    {
      CompatibleBitmap = CreateCompatibleBitmap(DC, 1, 1);
      if ( !CompatibleBitmap )
        goto LABEL_18;
      lpbmi = (struct tagBITMAPINFO *)HeapAlloc(g_hProcessHeap, 0, 0x428u);
      v8 = lpbmi;
      if ( !lpbmi )
      {
LABEL_17:
        DeleteObject(CompatibleBitmap);
        if ( v4 )
        {
LABEL_19:
          ReleaseDC(0, DC);
          return v4;
        }
LABEL_18:
        pbmi.bmiHeader.biWidth = a1;
        pbmi.bmiHeader.biHeight = a2;
        *(_QWORD *)&pbmi.bmiHeader.biPlanes = 1572865;
        memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
        pbmi.bmiHeader.biSize = 40;
        ppvBits = 0;
        v4 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
        goto LABEL_19;
      }
      lpbmi->bmiHeader.biSize = 40;
      GetDIBits(DC, CompatibleBitmap, 0, 0, 0, lpbmi, 0);
      if ( v8->bmiHeader.biBitCount <= 8u )
      {
LABEL_16:
        HeapFree(g_hProcessHeap, 0, v8);
        goto LABEL_17;
      }
      if ( v8->bmiHeader.biCompression == 3 )
        GetDIBits(DC, CompatibleBitmap, 0, v8->bmiHeader.biHeight, 0, v8, 0);
      v8->bmiHeader.biWidth = a1;
      v8->bmiHeader.biHeight = a2;
      if ( v8->bmiHeader.biCompression )
      {
        if ( v8->bmiHeader.biBitCount == 16 )
        {
          v9 = 2 * a1 * a2;
LABEL_15:
          v8->bmiHeader.biSizeImage = v9;
          *(_QWORD *)&v8->bmiHeader.biClrUsed = 0;
          ppvBits = 0;
          v4 = CreateDIBSection(DC, v8, 0, &ppvBits, 0, 0);
          goto LABEL_16;
        }
        if ( v8->bmiHeader.biBitCount == 32 )
        {
          v9 = 4 * a1 * a2;
          goto LABEL_15;
        }
      }
      v9 = 0;
      goto LABEL_15;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000a0b4  mov     [rsp-38h+arg_10], rbx
0x18000a0b9  push    rbp
0x18000a0ba  push    rsi
0x18000a0bb  push    rdi
0x18000a0bc  push    r12
0x18000a0be  push    r13
0x18000a0c0  push    r14
0x18000a0c2  push    r15
0x18000a0c4  mov     rbp, rsp
0x18000a0c7  sub     rsp, 80h
0x18000a0ce  mov     rax, cs:__security_cookie
0x18000a0d5  xor     rax, rsp
0x18000a0d8  mov     [rbp+var_8], rax
0x18000a0dc  xor     r13d, r13d
0x18000a0df  mov     r14d, edx
0x18000a0e2  mov     r15d, ecx
0x18000a0e5  mov     esi, r13d
0x18000a0e8  test    ecx, ecx
0x18000a0ea  jle     loc_18000A292
0x18000a0f0  test    edx, edx
0x18000a0f2  jle     loc_18000A292
0x18000a0f8  xor     ecx, ecx; hWnd
0x18000a0fa  call    cs:__imp_GetDC
0x18000a100  mov     rdi, rax
0x18000a103  test    rax, rax
0x18000a106  jz      loc_18000A292
0x18000a10c  lea     eax, [r13+1]
0x18000a110  mov     rcx, rdi; hdc
0x18000a113  mov     r8d, eax; cy
0x18000a116  mov     edx, eax; cx
0x18000a118  call    cs:__imp_CreateCompatibleBitmap
0x18000a11e  mov     r12, rax
0x18000a121  test    rax, rax
0x18000a124  jz      loc_18000A22E
0x18000a12a  mov     rcx, cs:g_hProcessHeap; hHeap
0x18000a131  xor     edx, edx; dwFlags
0x18000a133  mov     r8d, 428h; dwBytes
0x18000a139  call    cs:__imp_HeapAlloc
0x18000a13f  mov     rbx, rax
0x18000a142  test    rax, rax
0x18000a145  jz      loc_18000A220
0x18000a14b  mov     [rsp+80h+usage], r13d; usage
0x18000a150  xor     r9d, r9d; cLines
0x18000a153  mov     [rsp+80h+lpbmi], rax; lpbmi
0x18000a158  xor     r8d, r8d; start
0x18000a15b  mov     rdx, r12; hbm
0x18000a15e  mov     [rsp+80h+lpvBits], r13; lpvBits
0x18000a163  mov     rcx, rdi; hdc
0x18000a166  mov     dword ptr [rax], 28h ; '('
0x18000a16c  call    cs:__imp_GetDIBits
0x18000a172  cmp     word ptr [rbx+0Eh], 8
0x18000a177  jbe     loc_18000A20E
0x18000a17d  cmp     dword ptr [rbx+10h], 3
0x18000a181  jnz     short loc_18000A1A5
0x18000a183  mov     r9d, [rbx+8]; cLines
0x18000a187  xor     r8d, r8d; start
0x18000a18a  mov     [rsp+80h+usage], r13d; usage
0x18000a18f  mov     rdx, r12; hbm
0x18000a192  mov     [rsp+80h+lpbmi], rbx; lpbmi
0x18000a197  mov     rcx, rdi; hdc
0x18000a19a  mov     [rsp+80h+lpvBits], r13; lpvBits
0x18000a19f  call    cs:__imp_GetDIBits
0x18000a1a5  mov     [rbx+4], r15d
0x18000a1a9  mov     [rbx+8], r14d
0x18000a1ad  cmp     [rbx+10h], r13d
0x18000a1b1  jz      short loc_18000A1E0
0x18000a1b3  mov     eax, 10h
0x18000a1b8  cmp     ax, [rbx+0Eh]
0x18000a1bc  jnz     short loc_18000A1C9
0x18000a1be  mov     eax, r14d
0x18000a1c1  imul    eax, r15d
0x18000a1c5  add     eax, eax
0x18000a1c7  jmp     short loc_18000A1E3
0x18000a1c9  mov     eax, 20h ; ' '
0x18000a1ce  cmp     ax, [rbx+0Eh]
0x18000a1d2  jnz     short loc_18000A1E0
0x18000a1d4  mov     eax, r14d
0x18000a1d7  imul    eax, r15d
0x18000a1db  shl     eax, 2
0x18000a1de  jmp     short loc_18000A1E3
0x18000a1e0  mov     eax, r13d
0x18000a1e3  mov     [rbx+14h], eax
0x18000a1e6  lea     r9, [rbp+ppvBits]; ppvBits
0x18000a1ea  mov     dword ptr [rsp+80h+lpbmi], r13d; offset
0x18000a1ef  xor     r8d, r8d; usage
0x18000a1f2  mov     rdx, rbx; pbmi
0x18000a1f5  mov     [rbx+20h], r13
0x18000a1f9  mov     rcx, rdi; hdc
0x18000a1fc  mov     [rbp+ppvBits], r13
0x18000a200  mov     [rsp+80h+lpvBits], r13; hSection
0x18000a205  call    cs:__imp_CreateDIBSection
0x18000a20b  mov     rsi, rax
0x18000a20e  mov     rcx, cs:g_hProcessHeap; hHeap
0x18000a215  mov     r8, rbx; lpMem
0x18000a218  xor     edx, edx; dwFlags
0x18000a21a  call    cs:__imp_HeapFree
0x18000a220  mov     rcx, r12; ho
0x18000a223  call    cs:__imp_DeleteObject
0x18000a229  test    rsi, rsi
0x18000a22c  jnz     short loc_18000A287
0x18000a22e  xorps   xmm0, xmm0
0x18000a231  mov     dword ptr [rsp+80h+lpbmi], r13d; offset
0x18000a236  movups  xmmword ptr [rbp+pbmi.bmiHeader.biWidth], xmm0
0x18000a23a  xor     eax, eax
0x18000a23c  lea     r9, [rbp+ppvBits]; ppvBits
0x18000a240  movups  xmmword ptr [rbp+pbmi.bmiHeader.biSizeImage], xmm0
0x18000a244  mov     qword ptr [rbp+pbmi.bmiHeader.biClrImportant], rax
0x18000a248  lea     rdx, [rbp+pbmi]; pbmi
0x18000a24c  xor     r8d, r8d; usage
0x18000a24f  mov     [rbp+pbmi.bmiHeader.biWidth], r15d
0x18000a253  mov     rcx, rdi; hdc
0x18000a256  mov     [rbp+pbmi.bmiHeader.biHeight], r14d
0x18000a25a  mov     qword ptr [rbp+pbmi.bmiHeader.biPlanes], 180001h
0x18000a262  mov     qword ptr [rbp+pbmi.bmiHeader.biSizeImage], r13
0x18000a266  mov     qword ptr [rbp+pbmi.bmiHeader.biYPelsPerMeter], r13
0x18000a26a  mov     [rbp+pbmi.bmiHeader.biClrImportant], r13d
0x18000a26e  mov     [rbp+pbmi.bmiHeader.biSize], 28h ; '('
0x18000a275  mov     [rbp+ppvBits], r13
0x18000a279  mov     [rsp+80h+lpvBits], r13; hSection
0x18000a27e  call    cs:__imp_CreateDIBSection
0x18000a284  mov     rsi, rax
0x18000a287  mov     rdx, rdi; hDC
0x18000a28a  xor     ecx, ecx; hWnd
0x18000a28c  call    cs:__imp_ReleaseDC
0x18000a292  mov     rax, rsi
0x18000a295  mov     rcx, [rbp+var_8]
0x18000a299  xor     rcx, rsp; StackCookie
0x18000a29c  call    __security_check_cookie
0x18000a2a1  mov     rbx, [rsp+80h+arg_10]
0x18000a2a9  add     rsp, 80h
0x18000a2b0  pop     r15
0x18000a2b2  pop     r14
0x18000a2b4  pop     r13
0x18000a2b6  pop     r12
0x18000a2b8  pop     rdi
0x18000a2b9  pop     rsi
0x18000a2ba  pop     rbp
0x18000a2bb  retn
```
