# DibFromBitmap

- ea: `0x18000fb08`
- end: `0x18000fcbf`
- name: `DibFromBitmap`
- size: `439`
- prototype: `__int64 __fastcall(HBITMAP hbm, HPALETTE hPal)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010578`

## callees

- `0x18000fb08`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000fc08`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000fc08`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000fbf0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000fbf0`
- `GDI32!GetObjectW` at `0x18000fb4b`
- `GDI32!GetObjectW` at `0x18000fb4b`
- `GDI32!SelectPalette` at `0x18000fc43`
- `GDI32!SelectPalette` at `0x18000fc95`
- `GDI32!SelectPalette` at `0x18000fc43`
- `GDI32!SelectPalette` at `0x18000fc95`
- `GDI32!DeleteDC` at `0x18000fc9e`
- `GDI32!DeleteDC` at `0x18000fc9e`
- `GDI32!RealizePalette` at `0x18000fc4f`
- `GDI32!RealizePalette` at `0x18000fc4f`
- `GDI32!CreateCompatibleDC` at `0x18000fc2c`
- `GDI32!CreateCompatibleDC` at `0x18000fc2c`
- `GDI32!GetDIBits` at `0x18000fc81`
- `GDI32!GetDIBits` at `0x18000fc81`

## pseudocode

```c
HGLOBAL __fastcall DibFromBitmap(HBITMAP hbm, HPALETTE hPal)
{
  UINT v4; // r13d
  unsigned __int16 v5; // dx
  int v6; // eax
  unsigned int v7; // r8d
  unsigned int v8; // ecx
  unsigned int v9; // edx
  HGLOBAL v10; // rax
  HGLOBAL v11; // rsi
  HPALETTE v12; // r12
  int *lpbmi; // rdi
  __int128 v14; // xmm1
  __int64 v15; // xmm0_8
  HDC CompatibleDC; // rax
  HDC v17; // rbx
  __int128 pv; // [rsp+40h] [rbp-39h] BYREF
  __int128 v20; // [rsp+50h] [rbp-29h]
  __int128 v21; // [rsp+60h] [rbp-19h]
  __int128 v22; // [rsp+70h] [rbp-9h]
  __int64 v23; // [rsp+80h] [rbp+7h]

  DWORD2(v21) = 0;
  HIWORD(v21) = 0;
  pv = 0;
  v20 = 0;
  if ( !hbm )
    return 0;
  GetObjectW(hbm, 32, &pv);
  v4 = DWORD2(pv);
  WORD6(v21) = 1;
  LODWORD(v21) = 40;
  *(_QWORD *)((char *)&v21 + 4) = *(_QWORD *)((char *)&pv + 4);
  if ( (unsigned __int16)v20 * WORD1(v20) <= 8 )
    v5 = 8;
  else
    v5 = 24;
  v6 = 0;
  HIWORD(v21) = v5;
  LODWORD(v22) = 0;
  *((_QWORD *)&v22 + 1) = 0;
  HIDWORD(v23) = 0;
  v7 = DWORD2(pv) * (((DWORD1(pv) * (unsigned int)v5 + 31) >> 3) & 0x1FFFFFFC);
  if ( v5 == 8 )
    v6 = 256;
  v8 = 1024;
  if ( v5 != 8 )
    v8 = 0;
  LODWORD(v23) = v6;
  DWORD1(v22) = DWORD2(pv) * (((DWORD1(pv) * (unsigned int)v5 + 31) >> 3) & 0x1FFFFFFC);
  v9 = v8 + 40;
  if ( v8 + 40 < v8 )
    return 0;
  if ( v9 + v7 < v9 )
    return 0;
  v10 = GlobalAlloc(0x2042u, v9 + v7);
  v11 = v10;
  if ( !v10 )
    return 0;
  v12 = 0;
  lpbmi = (int *)GlobalLock(v10);
  v14 = v22;
  *(_OWORD *)lpbmi = v21;
  v15 = v23;
  *((_OWORD *)lpbmi + 1) = v14;
  *((_QWORD *)lpbmi + 4) = v15;
  CompatibleDC = CreateCompatibleDC(0);
  v17 = CompatibleDC;
  if ( hPal )
  {
    v12 = SelectPalette(CompatibleDC, hPal, 0);
    RealizePalette(v17);
  }
  GetDIBits(v17, hbm, 0, v4, (char *)&lpbmi[lpbmi[8]] + *lpbmi, (LPBITMAPINFO)lpbmi, 0);
  if ( hPal )
    SelectPalette(v17, v12, 0);
  DeleteDC(v17);
  return v11;
}

```

## disassembly

```asm
0x18000fb08  push    rbp
0x18000fb0a  push    rbx
0x18000fb0b  push    rsi
0x18000fb0c  push    rdi
0x18000fb0d  push    r12
0x18000fb0f  push    r13
0x18000fb11  push    r14
0x18000fb13  push    r15
0x18000fb15  lea     rbp, [rsp-1Fh]
0x18000fb1a  sub     rsp, 98h
0x18000fb21  xor     ebx, ebx
0x18000fb23  xorps   xmm0, xmm0
0x18000fb26  mov     dword ptr [rbp+57h+var_70+8], ebx
0x18000fb29  mov     r15, rdx
0x18000fb2c  mov     word ptr [rbp+57h+var_70+0Eh], bx
0x18000fb30  mov     r14, rcx
0x18000fb33  movups  [rbp+57h+pv], xmm0
0x18000fb37  movups  [rbp+57h+var_80], xmm0
0x18000fb3b  test    rcx, rcx
0x18000fb3e  jz      loc_18000FCA9
0x18000fb44  lea     r8, [rbp+57h+pv]; pv
0x18000fb48  lea     edx, [rbx+20h]; c
0x18000fb4b  call    cs:__imp_GetObjectW
0x18000fb51  movzx   ecx, word ptr [rbp+57h+var_80+2]
0x18000fb55  lea     eax, [rbx+1]
0x18000fb58  mov     r9d, dword ptr [rbp+57h+pv+4]
0x18000fb5c  lea     r10d, [rbx+8]
0x18000fb60  mov     r13d, dword ptr [rbp+57h+pv+8]
0x18000fb64  mov     word ptr [rbp+57h+var_70+0Ch], ax
0x18000fb68  movzx   eax, word ptr [rbp+57h+var_80]
0x18000fb6c  imul    ecx, eax
0x18000fb6f  mov     dword ptr [rbp+57h+var_70], 28h ; '('
0x18000fb76  mov     dword ptr [rbp+57h+var_70+4], r9d
0x18000fb7a  mov     dword ptr [rbp+57h+var_70+8], r13d
0x18000fb7e  cmp     ecx, r10d
0x18000fb81  jle     short loc_18000FB88
0x18000fb83  lea     edx, [rbx+18h]
0x18000fb86  jmp     short loc_18000FB8C
0x18000fb88  movzx   edx, r10w
0x18000fb8c  movzx   r8d, dx
0x18000fb90  mov     ecx, 100h
0x18000fb95  imul    r8d, r9d
0x18000fb99  mov     eax, ebx
0x18000fb9b  mov     word ptr [rbp+57h+var_70+0Eh], dx
0x18000fb9f  mov     dword ptr [rbp+57h+var_60], ebx
0x18000fba2  mov     qword ptr [rbp+57h+var_60+8], rbx
0x18000fba6  mov     dword ptr [rbp+57h+var_50+4], ebx
0x18000fba9  add     r8d, 1Fh
0x18000fbad  shr     r8d, 3
0x18000fbb1  and     r8d, 1FFFFFFCh
0x18000fbb8  imul    r8d, r13d
0x18000fbbc  cmp     dx, r10w
0x18000fbc0  cmovz   eax, ecx
0x18000fbc3  mov     ecx, 400h
0x18000fbc8  cmovnz  ecx, ebx
0x18000fbcb  mov     dword ptr [rbp+57h+var_50], eax
0x18000fbce  mov     dword ptr [rbp+57h+var_60+4], r8d
0x18000fbd2  lea     edx, [rcx+28h]
0x18000fbd5  cmp     edx, ecx
0x18000fbd7  jb      loc_18000FCA9
0x18000fbdd  lea     eax, [rdx+r8]
0x18000fbe1  cmp     eax, edx
0x18000fbe3  jb      loc_18000FCA9
0x18000fbe9  mov     edx, eax; dwBytes
0x18000fbeb  mov     ecx, 2042h; uFlags
0x18000fbf0  call    cs:__imp_GlobalAlloc
0x18000fbf6  mov     rsi, rax
0x18000fbf9  test    rax, rax
0x18000fbfc  jz      loc_18000FCA9
0x18000fc02  mov     rcx, rax; hMem
0x18000fc05  mov     r12, rbx
0x18000fc08  call    cs:__imp_GlobalLock
0x18000fc0e  movups  xmm0, [rbp+57h+var_70]
0x18000fc12  xor     ecx, ecx; hdc
0x18000fc14  mov     rdi, rax
0x18000fc17  movups  xmm1, [rbp+57h+var_60]
0x18000fc1b  movups  xmmword ptr [rax], xmm0
0x18000fc1e  movsd   xmm0, [rbp+57h+var_50]
0x18000fc23  movups  xmmword ptr [rax+10h], xmm1
0x18000fc27  movsd   qword ptr [rax+20h], xmm0
0x18000fc2c  call    cs:__imp_CreateCompatibleDC
0x18000fc32  mov     rbx, rax
0x18000fc35  test    r15, r15
0x18000fc38  jz      short loc_18000FC55
0x18000fc3a  xor     r8d, r8d; bForceBkgd
0x18000fc3d  mov     rdx, r15; hPal
0x18000fc40  mov     rcx, rax; hdc
0x18000fc43  call    cs:__imp_SelectPalette
0x18000fc49  mov     rcx, rbx; hdc
0x18000fc4c  mov     r12, rax
0x18000fc4f  call    cs:__imp_RealizePalette
0x18000fc55  movsxd  r8, dword ptr [rdi+20h]
0x18000fc59  mov     r9d, r13d; cLines
0x18000fc5c  movsxd  rdx, dword ptr [rdi]
0x18000fc5f  add     rdx, rdi
0x18000fc62  mov     [rsp+0D0h+usage], 0; usage
0x18000fc6a  mov     [rsp+0D0h+lpbmi], rdi; lpbmi
0x18000fc6f  lea     rcx, [rdx+r8*4]
0x18000fc73  xor     r8d, r8d; start
0x18000fc76  mov     [rsp+0D0h+lpvBits], rcx; lpvBits
0x18000fc7b  mov     rdx, r14; hbm
0x18000fc7e  mov     rcx, rbx; hdc
0x18000fc81  call    cs:__imp_GetDIBits
0x18000fc87  test    r15, r15
0x18000fc8a  jz      short loc_18000FC9B
0x18000fc8c  xor     r8d, r8d; bForceBkgd
0x18000fc8f  mov     rdx, r12; hPal
0x18000fc92  mov     rcx, rbx; hdc
0x18000fc95  call    cs:__imp_SelectPalette
0x18000fc9b  mov     rcx, rbx; hdc
0x18000fc9e  call    cs:__imp_DeleteDC
0x18000fca4  mov     rax, rsi
0x18000fca7  jmp     short loc_18000FCAB
0x18000fca9  xor     eax, eax
0x18000fcab  add     rsp, 98h
0x18000fcb2  pop     r15
0x18000fcb4  pop     r14
0x18000fcb6  pop     r13
0x18000fcb8  pop     r12
0x18000fcba  pop     rdi
0x18000fcbb  pop     rsi
0x18000fcbc  pop     rbx
0x18000fcbd  pop     rbp
0x18000fcbe  retn
```
