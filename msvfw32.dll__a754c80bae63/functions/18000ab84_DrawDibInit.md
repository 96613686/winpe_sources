# DrawDibInit

- ea: `0x18000ab84`
- end: `0x18000ad3f`
- name: `DrawDibInit`
- size: `443`
- prototype: `BOOL __stdcall()`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008400`
- `0x180009bb0`
- `0x18000ad50`

## callees

- `0x1800014b0`
- `0x180002374`
- `0x18000ab84`
- `0x18000b3d8`
- `0x18000bcfc`
- `0x18000bd90`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x18000abb7`
- `GDI32!GetDeviceCaps` at `0x18000abc7`
- `GDI32!GetDeviceCaps` at `0x18000abfa`
- `GDI32!GetDeviceCaps` at `0x18000abb7`
- `GDI32!GetDeviceCaps` at `0x18000abc7`
- `GDI32!GetDeviceCaps` at `0x18000abfa`
- `USER32!GetDC` at `0x18000aba6`
- `USER32!GetDC` at `0x18000aba6`
- `USER32!ReleaseDC` at `0x18000ac08`
- `USER32!ReleaseDC` at `0x18000ac08`
- `USER32!GetSystemMetrics` at `0x18000abd8`
- `USER32!GetSystemMetrics` at `0x18000abe9`
- `USER32!GetSystemMetrics` at `0x18000abd8`
- `USER32!GetSystemMetrics` at `0x18000abe9`

## string_xrefs

- `0x18000ac9f`: `DecompressToScreen`
- `0x18000ac8a`: `DecompressToBitmap`

## pseudocode

```c
BOOL __stdcall DrawDibInit()
{
  HDC DC; // rdi
  __int16 DeviceCaps; // bx
  __int16 v2; // bx
  int SystemMetrics; // esi
  int v4; // r14d
  int v5; // r15d
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  WORD v10; // cx
  struct tagBITMAPINFOHEADER bi; // [rsp+20h] [rbp-30h] BYREF

  DC = GetDC(0);
  DeviceCaps = GetDeviceCaps(DC, 14);
  v2 = DeviceCaps * GetDeviceCaps(DC, 12);
  SystemMetrics = GetSystemMetrics(0);
  v4 = GetSystemMetrics(1);
  v5 = GetDeviceCaps(DC, 38);
  ReleaseDC(0, DC);
  if ( dword_180023D64 )
  {
    if ( gwScreenWidth == SystemMetrics && gwScreenHeight == v4 && gwScreenBitDepth == v2 )
      return 1;
    TermDCI();
    dword_180023D64 = 0;
  }
  gwScreenBitDepth = v2;
  gwScreenWidth = SystemMetrics;
  gwScreenHeight = v4;
  gwRasterCaps = v5;
  dword_180023D60 = mmGetProfileIntA(v6, szHalftone, 0);
  dword_180023D70 = mmGetProfileIntA(v7, szDrawToBitmap, 0xFFFFFFFFLL);
  dword_180023D58 = mmGetProfileIntA(v8, szDecompressToBitmap, 1);
  gfScreenX = mmGetProfileIntA(v9, szDecompressToScreen, 1);
  InitDCI();
  v10 = gwScreenBitDepth;
  if ( (unsigned __int16)gwScreenBitDepth > 0x20u )
  {
    v10 = 32;
    gwScreenBitDepth = 32;
  }
  if ( ((v10 - 16) & 0xFFEF) == 0 )
  {
    bi.biBitCount = v10;
    bi.biSize = 40;
    bi.biWidth = 1;
    bi.biHeight = 1;
    bi.biPlanes = 1;
    memset(&bi.biCompression, 0, 24);
    if ( !(unsigned int)DrawDibProfileDisplay(&bi) )
      gwScreenBitDepth = 24;
  }
  dword_180023D64 = 1;
  return 1;
}

```

## disassembly

```asm
0x18000ab84  push    rbp
0x18000ab86  push    rbx
0x18000ab87  push    rsi
0x18000ab88  push    rdi
0x18000ab89  push    r12
0x18000ab8b  push    r14
0x18000ab8d  push    r15
0x18000ab8f  mov     rbp, rsp
0x18000ab92  sub     rsp, 50h
0x18000ab96  mov     rax, cs:__security_cookie
0x18000ab9d  xor     rax, rsp
0x18000aba0  mov     [rbp+var_8], rax
0x18000aba4  xor     ecx, ecx; hWnd
0x18000aba6  call    cs:__imp_GetDC
0x18000abac  mov     rcx, rax; hdc
0x18000abaf  mov     edx, 0Eh; index
0x18000abb4  mov     rdi, rax
0x18000abb7  call    cs:__imp_GetDeviceCaps
0x18000abbd  mov     edx, 0Ch; index
0x18000abc2  mov     rcx, rdi; hdc
0x18000abc5  mov     ebx, eax
0x18000abc7  call    cs:__imp_GetDeviceCaps
0x18000abcd  movzx   ecx, bx
0x18000abd0  movzx   ebx, ax
0x18000abd3  imul    ebx, ecx
0x18000abd6  xor     ecx, ecx; nIndex
0x18000abd8  call    cs:__imp_GetSystemMetrics
0x18000abde  mov     r12d, 1
0x18000abe4  mov     esi, eax
0x18000abe6  mov     ecx, r12d; nIndex
0x18000abe9  call    cs:__imp_GetSystemMetrics
0x18000abef  lea     edx, [r12+25h]; index
0x18000abf4  mov     rcx, rdi; hdc
0x18000abf7  mov     r14d, eax
0x18000abfa  call    cs:__imp_GetDeviceCaps
0x18000ac00  mov     rdx, rdi; hDC
0x18000ac03  xor     ecx, ecx; hWnd
0x18000ac05  mov     r15d, eax
0x18000ac08  call    cs:__imp_ReleaseDC
0x18000ac0e  xor     edi, edi
0x18000ac10  cmp     cs:dword_180023D64, edi
0x18000ac16  jz      short loc_18000AC41
0x18000ac18  cmp     cs:gwScreenWidth, esi
0x18000ac1e  jnz     short loc_18000AC36
0x18000ac20  cmp     cs:gwScreenHeight, r14d
0x18000ac27  jnz     short loc_18000AC36
0x18000ac29  cmp     cs:gwScreenBitDepth, bx
0x18000ac30  jz      loc_18000AD21
0x18000ac36  call    TermDCI
0x18000ac3b  mov     cs:dword_180023D64, edi
0x18000ac41  xor     r8d, r8d
0x18000ac44  mov     cs:gwScreenBitDepth, bx
0x18000ac4b  lea     rdx, szHalftone; "Halftone"
0x18000ac52  mov     cs:gwScreenWidth, esi
0x18000ac58  mov     cs:gwScreenHeight, r14d
0x18000ac5f  mov     cs:gwRasterCaps, r15d
0x18000ac66  call    mmGetProfileIntA
0x18000ac6b  or      r8d, 0FFFFFFFFh
0x18000ac6f  mov     cs:dword_180023D60, eax
0x18000ac75  lea     rdx, szDrawToBitmap; "DrawToBitmap"
0x18000ac7c  call    mmGetProfileIntA
0x18000ac81  mov     r8d, r12d
0x18000ac84  mov     cs:dword_180023D70, eax
0x18000ac8a  lea     rdx, szDecompressToBitmap; "DecompressToBitmap"
0x18000ac91  call    mmGetProfileIntA
0x18000ac96  mov     r8d, r12d
0x18000ac99  mov     cs:dword_180023D58, eax
0x18000ac9f  lea     rdx, szDecompressToScreen; "DecompressToScreen"
0x18000aca6  call    mmGetProfileIntA
0x18000acab  mov     cs:gfScreenX, eax
0x18000acb1  call    InitDCI
0x18000acb6  movzx   ecx, cs:gwScreenBitDepth
0x18000acbd  mov     eax, 20h ; ' '
0x18000acc2  cmp     cx, ax
0x18000acc5  jbe     short loc_18000ACD0
0x18000acc7  mov     ecx, eax
0x18000acc9  mov     cs:gwScreenBitDepth, ax
0x18000acd0  lea     eax, [rcx-10h]
0x18000acd3  mov     edx, 0FFEFh
0x18000acd8  test    dx, ax
0x18000acdb  jnz     short loc_18000AD1A
0x18000acdd  mov     [rbp+bi.biBitCount], cx
0x18000ace1  lea     rcx, [rbp+bi]; lpbi
0x18000ace5  mov     [rbp+bi.biSize], 28h ; '('
0x18000acec  mov     [rbp+bi.biWidth], r12d
0x18000acf0  mov     [rbp+bi.biHeight], r12d
0x18000acf4  mov     [rbp+bi.biPlanes], r12w
0x18000acf9  mov     qword ptr [rbp+bi.biCompression], rdi
0x18000acfd  mov     qword ptr [rbp+bi.biXPelsPerMeter], rdi
0x18000ad01  mov     qword ptr [rbp+bi.biClrUsed], rdi
0x18000ad05  call    DrawDibProfileDisplay
0x18000ad0a  test    eax, eax
0x18000ad0c  jnz     short loc_18000AD1A
0x18000ad0e  mov     eax, 18h
0x18000ad13  mov     cs:gwScreenBitDepth, ax
0x18000ad1a  mov     cs:dword_180023D64, r12d
0x18000ad21  mov     eax, r12d
0x18000ad24  mov     rcx, [rbp+var_8]
0x18000ad28  xor     rcx, rsp; StackCookie
0x18000ad2b  call    __security_check_cookie
0x18000ad30  add     rsp, 50h
0x18000ad34  pop     r15
0x18000ad36  pop     r14
0x18000ad38  pop     r12
0x18000ad3a  pop     rdi
0x18000ad3b  pop     rsi
0x18000ad3c  pop     rbx
0x18000ad3d  pop     rbp
0x18000ad3e  retn
```
