# CopyOnWriteBitmap::CreateFromHICON(HICON__ *,CopyOnWriteBitmap * *)

- ea: `0x180003be8`
- end: `0x180003f1b`
- name: `?CreateFromHICON@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHICON__@@PEAPEAV1@@Z`
- size: `819`
- prototype: `__int64 __fastcall(HICON, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1801047ec`

## callees

- `0x180003be8`
- `0x180004460`
- `0x180008d84`
- `0x180011330`
- `0x1800116c8`
- `0x18001f950`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x180175010`

## import_xrefs

- `USER32!GetIconInfo` at `0x180003c2d`
- `USER32!GetIconInfo` at `0x180003c2d`
- `USER32!GetDC` at `0x180003dfa`
- `USER32!GetDC` at `0x180003dfa`
- `USER32!ReleaseDC` at `0x180003dd7`
- `USER32!ReleaseDC` at `0x180003dd7`
- `GDI32!GetStockObject` at `0x180003c57`
- `GDI32!GetStockObject` at `0x180003c57`
- `GDI32!GetDIBits` at `0x180003db6`
- `GDI32!GetDIBits` at `0x180003e4a`
- `GDI32!GetDIBits` at `0x180003db6`
- `GDI32!GetDIBits` at `0x180003e4a`
- `GDI32!DeleteObject` at `0x180003eef`
- `GDI32!DeleteObject` at `0x180003f00`
- `GDI32!DeleteObject` at `0x180003eef`
- `GDI32!DeleteObject` at `0x180003f00`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::CreateFromHICON(HICON a1, _QWORD *a2)
{
  HGDIOBJ StockObject; // rax
  unsigned int v4; // ebx
  __int64 v6; // rcx
  unsigned int v7; // r10d
  unsigned int v8; // ecx
  _DWORD *v9; // rdx
  unsigned int v10; // r9d
  _BYTE *v11; // r11
  __int64 v12; // r15
  _DWORD *v13; // rax
  unsigned int v14; // r8d
  __int64 v15; // rdi
  __int64 v16; // rcx
  int v17; // eax
  HDC DC; // r14
  LONG biHeight; // ecx
  LONG v20; // ecx
  unsigned __int64 v21; // rdx
  unsigned int v22; // eax
  unsigned __int64 v23; // rcx
  _BYTE *lpvBits; // rsi
  ICONINFO piconinfo; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+70h] [rbp-90h]
  struct tagBITMAPINFO bmi; // [rsp+80h] [rbp-80h] BYREF

  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( !GetIconInfo(a1, &piconinfo) )
    return 2;
  if ( piconinfo.fIcon && piconinfo.hbmColor )
  {
    StockObject = GetStockObject(15);
    v4 = CopyOnWriteBitmap::CreateFromHBITMAP(piconinfo.hbmColor, StockObject, a2);
    if ( !v4 )
    {
      if ( *a2 )
        CopyOnWriteBitmap::ConvertFormat(*a2, 2498570);
      if ( !piconinfo.hbmMask )
        goto LABEL_7;
      v4 = 7;
      DC = GetDC(0);
      if ( DC )
      {
        memset_0(&bmi.bmiHeader.biWidth, 0, 0x424u);
        bmi.bmiHeader.biSize = 40;
        if ( GetDIBits(DC, piconinfo.hbmMask, 0, 0, 0, &bmi, 0) )
        {
          biHeight = -bmi.bmiHeader.biHeight;
          bmi.bmiHeader.biSize = 40;
          if ( bmi.bmiHeader.biHeight > 0 )
            biHeight = bmi.bmiHeader.biHeight;
          v20 = -biHeight;
          v21 = 4LL * (unsigned int)bmi.bmiHeader.biWidth;
          bmi.bmiHeader.biHeight = v20;
          *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
          bmi.bmiHeader.biSizeImage = 0;
          *(_QWORD *)&bmi.bmiHeader.biClrUsed = 0;
          if ( v21 > 0xFFFFFFFF )
            goto LABEL_35;
          v22 = -v20;
          if ( v20 > 0 )
            v22 = v20;
          v23 = (unsigned int)v21 * (unsigned __int64)v22;
          if ( v23 <= 0xFFFFFFFF )
          {
            lpvBits = (_BYTE *)GpMallocEx((unsigned int)v23, 0);
            if ( lpvBits )
            {
              if ( GetDIBits(DC, piconinfo.hbmMask, 0, -bmi.bmiHeader.biHeight, lpvBits, &bmi, 0) )
              {
                v6 = *a2;
                v26 = 0;
                v27 = 0;
                v4 = CopyOnWriteBitmap::LockBits(v6, 0, 3, 2498570, &v26);
                if ( !v4 )
                {
                  v7 = 0;
                  v8 = DWORD1(v26);
                  v9 = (_DWORD *)v27;
                  if ( DWORD1(v26) )
                  {
                    v10 = v26;
                    v11 = lpvBits;
                    v12 = 4 * bmi.bmiHeader.biWidth;
                    do
                    {
                      v13 = v9;
                      v14 = 0;
                      if ( v10 )
                      {
                        do
                        {
                          if ( *(_DWORD *)((char *)v13 + v11 - (_BYTE *)v9) )
                          {
                            *v13 = 0;
                            v10 = v26;
                          }
                          ++v13;
                          ++v14;
                        }
                        while ( v14 < v10 );
                        v8 = DWORD1(v26);
                      }
                      v11 += v12;
                      v9 = (_DWORD *)((char *)v9 + SDWORD2(v26));
                      ++v7;
                    }
                    while ( v7 < v8 );
                  }
                  v15 = *a2;
                  v16 = *(_QWORD *)(v15 + 88);
                  if ( v16 )
                  {
                    v17 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v16 + 48LL))(v16, &v26);
                    --*(_DWORD *)(v15 + 60);
                    if ( v17 < 0 )
                      MapHRESULTToGpStatus((unsigned int)v17);
                  }
                }
              }
              GpFree(lpvBits);
            }
            else
            {
              v4 = 3;
            }
          }
          else
          {
LABEL_35:
            v4 = 11;
          }
        }
        ReleaseDC(0, DC);
      }
    }
  }
  else
  {
    v4 = 2;
  }
  if ( piconinfo.hbmMask )
    DeleteObject(piconinfo.hbmMask);
LABEL_7:
  if ( piconinfo.hbmColor )
    DeleteObject(piconinfo.hbmColor);
  return v4;
}

```

## disassembly

```asm
0x180003be8  mov     [rsp-8+arg_10], rbx
0x180003bed  push    rbp
0x180003bee  push    rsi
0x180003bef  push    rdi
0x180003bf0  push    r12
0x180003bf2  push    r13
0x180003bf4  push    r14
0x180003bf6  push    r15
0x180003bf8  lea     rbp, [rsp-3C0h]
0x180003c00  sub     rsp, 4C0h
0x180003c07  mov     rax, cs:__security_cookie
0x180003c0e  xor     rax, rsp
0x180003c11  mov     [rbp+3F0h+var_40], rax
0x180003c18  xorps   xmm0, xmm0
0x180003c1b  mov     rdi, rdx
0x180003c1e  lea     rdx, [rsp+4F0h+piconinfo]; piconinfo
0x180003c23  movups  xmmword ptr [rsp+4F0h+piconinfo.fIcon], xmm0
0x180003c28  movups  xmmword ptr [rsp+4F0h+piconinfo.hbmMask], xmm0
0x180003c2d  call    cs:__imp_GetIconInfo
0x180003c34  nop     dword ptr [rax+rax+00h]
0x180003c39  xor     r12d, r12d
0x180003c3c  test    eax, eax
0x180003c3e  jz      loc_180003F11
0x180003c44  cmp     [rsp+4F0h+piconinfo.fIcon], r12d
0x180003c49  jz      short loc_180003CC6
0x180003c4b  cmp     [rsp+4F0h+piconinfo.hbmColor], r12
0x180003c50  jz      short loc_180003CC6
0x180003c52  lea     ecx, [r12+0Fh]; i
0x180003c57  call    cs:__imp_GetStockObject
0x180003c5e  nop     dword ptr [rax+rax+00h]
0x180003c63  mov     rcx, [rsp+4F0h+piconinfo.hbmColor]
0x180003c68  mov     r8, rdi
0x180003c6b  mov     rdx, rax
0x180003c6e  call    ?CreateFromHBITMAP@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAUHPALETTE__@@PEAPEAV1@@Z; CopyOnWriteBitmap::CreateFromHBITMAP(HBITMAP__ *,HPALETTE__ *,CopyOnWriteBitmap * *)
0x180003c73  mov     ebx, eax
0x180003c75  test    eax, eax
0x180003c77  jz      loc_180003ED0
0x180003c7d  mov     rcx, [rsp+4F0h+piconinfo.hbmMask]; ho
0x180003c82  test    rcx, rcx
0x180003c85  jnz     loc_180003EEF
0x180003c8b  mov     rcx, [rsp+4F0h+piconinfo.hbmColor]; ho
0x180003c90  test    rcx, rcx
0x180003c93  jnz     loc_180003F00
0x180003c99  mov     eax, ebx
0x180003c9b  mov     rcx, [rbp+3F0h+var_40]
0x180003ca2  xor     rcx, rsp; StackCookie
0x180003ca5  call    __security_check_cookie
0x180003caa  mov     rbx, [rsp+4F0h+arg_10]
0x180003cb2  add     rsp, 4C0h
0x180003cb9  pop     r15
0x180003cbb  pop     r14
0x180003cbd  pop     r13
0x180003cbf  pop     r12
0x180003cc1  pop     rdi
0x180003cc2  pop     rsi
0x180003cc3  pop     rbp
0x180003cc4  retn
0x180003cc6  mov     ebx, 2
0x180003ccb  jmp     short loc_180003C7D
0x180003ccd  mov     rcx, [rdi]
0x180003cd0  lea     rax, [rsp+4F0h+var_490]
0x180003cd5  xorps   xmm0, xmm0
0x180003cd8  mov     [rsp+4F0h+lpvBits], rax
0x180003cdd  xor     edx, edx
0x180003cdf  mov     r9d, r15d
0x180003ce2  movups  [rsp+4F0h+var_490], xmm0
0x180003ce7  movups  [rsp+4F0h+var_480], xmm0
0x180003cec  lea     r8d, [rdx+3]
0x180003cf0  call    ?LockBits@CopyOnWriteBitmap@@AEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; CopyOnWriteBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x180003cf5  mov     ebx, eax
0x180003cf7  test    eax, eax
0x180003cf9  jnz     loc_180003DCA
0x180003cff  mov     eax, [rbp+3F0h+bmi.bmiHeader.biWidth]
0x180003d02  mov     r10d, r12d
0x180003d05  mov     ecx, dword ptr [rsp+4F0h+var_490+4]
0x180003d09  mov     rdx, qword ptr [rsp+4F0h+var_480]
0x180003d0e  shl     eax, 2
0x180003d11  test    ecx, ecx
0x180003d13  jz      short loc_180003D5A
0x180003d15  mov     r9d, dword ptr [rsp+4F0h+var_490]
0x180003d1a  mov     r11, rsi
0x180003d1d  movsxd  r15, eax
0x180003d20  mov     rax, rdx
0x180003d23  mov     r8d, r12d
0x180003d26  test    r9d, r9d
0x180003d29  jz      short loc_180003D47
0x180003d2b  mov     rcx, r11
0x180003d2e  sub     rcx, rdx
0x180003d31  cmp     [rcx+rax], r12d
0x180003d35  jnz     short loc_180003D87
0x180003d37  add     rax, 4
0x180003d3b  add     r8d, r13d
0x180003d3e  cmp     r8d, r9d
0x180003d41  jb      short loc_180003D31
0x180003d43  mov     ecx, dword ptr [rsp+4F0h+var_490+4]
0x180003d47  movsxd  rax, dword ptr [rsp+4F0h+var_490+8]
0x180003d4c  add     r11, r15
0x180003d4f  add     rdx, rax
0x180003d52  add     r10d, r13d
0x180003d55  cmp     r10d, ecx
0x180003d58  jb      short loc_180003D20
0x180003d5a  mov     rdi, [rdi]
0x180003d5d  mov     rcx, [rdi+58h]
0x180003d61  test    rcx, rcx
0x180003d64  jz      short loc_180003DCA
0x180003d66  mov     rax, [rcx]
0x180003d69  lea     rdx, [rsp+4F0h+var_490]
0x180003d6e  mov     rax, [rax+30h]
0x180003d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d77  dec     dword ptr [rdi+3Ch]
0x180003d7a  test    eax, eax
0x180003d7c  jns     short loc_180003DCA
0x180003d7e  mov     ecx, eax
0x180003d80  call    ?MapHRESULTToGpStatus@@YA?AW4Status@@J@Z; MapHRESULTToGpStatus(long)
0x180003d85  jmp     short loc_180003DCA
0x180003d87  mov     [rax], r12d
0x180003d8a  mov     r9d, dword ptr [rsp+4F0h+var_490]
0x180003d8f  jmp     short loc_180003D37
0x180003d91  mov     r9d, [rbp+3F0h+bmi.bmiHeader.biHeight]
0x180003d95  lea     rax, [rbp+3F0h+bmi]
0x180003d99  mov     rdx, [rsp+4F0h+piconinfo.hbmMask]; hbm
0x180003d9e  neg     r9d; cLines
0x180003da1  mov     [rsp+4F0h+usage], r12d; usage
0x180003da6  xor     r8d, r8d; start
0x180003da9  mov     [rsp+4F0h+lpbmi], rax; lpbmi
0x180003dae  mov     rcx, r14; hdc
0x180003db1  mov     [rsp+4F0h+lpvBits], rsi; lpvBits
0x180003db6  call    cs:__imp_GetDIBits
0x180003dbd  nop     dword ptr [rax+rax+00h]
0x180003dc2  test    eax, eax
0x180003dc4  jnz     loc_180003CCD
0x180003dca  mov     rcx, rsi
0x180003dcd  call    GpFree
0x180003dd2  mov     rdx, r14; hDC
0x180003dd5  xor     ecx, ecx; hWnd
0x180003dd7  call    cs:__imp_ReleaseDC
0x180003dde  nop     dword ptr [rax+rax+00h]
0x180003de3  jmp     loc_180003C7D
0x180003de8  cmp     [rsp+4F0h+piconinfo.hbmMask], r12
0x180003ded  jz      loc_180003C8B
0x180003df3  xor     ecx, ecx; hWnd
0x180003df5  mov     ebx, 7
0x180003dfa  call    cs:__imp_GetDC
0x180003e01  nop     dword ptr [rax+rax+00h]
0x180003e06  mov     r14, rax
0x180003e09  test    rax, rax
0x180003e0c  jz      loc_180003C7D
0x180003e12  xor     edx, edx; Val
0x180003e14  lea     rcx, [rbp+3F0h+bmi.bmiHeader.biWidth]; void *
0x180003e18  mov     r8d, 424h; Size
0x180003e1e  call    memset_0
0x180003e23  mov     rdx, [rsp+4F0h+piconinfo.hbmMask]; hbm
0x180003e28  lea     rax, [rbp+3F0h+bmi]
0x180003e2c  mov     [rsp+4F0h+usage], r12d; usage
0x180003e31  lea     esi, [rbx+21h]
0x180003e34  mov     [rsp+4F0h+lpbmi], rax; lpbmi
0x180003e39  xor     r9d, r9d; cLines
0x180003e3c  xor     r8d, r8d; start
0x180003e3f  mov     [rsp+4F0h+lpvBits], r12; lpvBits
0x180003e44  mov     rcx, r14; hdc
0x180003e47  mov     [rbp+3F0h+bmi.bmiHeader.biSize], esi
0x180003e4a  call    cs:__imp_GetDIBits
0x180003e51  nop     dword ptr [rax+rax+00h]
0x180003e56  test    eax, eax
0x180003e58  jz      loc_180003DD2
0x180003e5e  mov     ecx, [rbp+3F0h+bmi.bmiHeader.biHeight]
0x180003e61  lea     r13d, [rbx-6]
0x180003e65  mov     edx, [rbp+3F0h+bmi.bmiHeader.biWidth]
0x180003e68  neg     ecx
0x180003e6a  mov     r8d, 0FFFFFFFFh
0x180003e70  mov     [rbp+3F0h+bmi.bmiHeader.biSize], esi
0x180003e73  cmovs   ecx, [rbp+3F0h+bmi.bmiHeader.biHeight]
0x180003e77  neg     ecx
0x180003e79  shl     rdx, 2
0x180003e7d  mov     [rbp+3F0h+bmi.bmiHeader.biHeight], ecx
0x180003e80  mov     qword ptr [rbp+3F0h+bmi.bmiHeader.biPlanes], 200001h
0x180003e88  mov     [rbp+3F0h+bmi.bmiHeader.biSizeImage], r12d
0x180003e8c  mov     qword ptr [rbp+3F0h+bmi.bmiHeader.biClrUsed], r12
0x180003e90  cmp     rdx, r8
0x180003e93  ja      short loc_180003EA9
0x180003e95  mov     eax, ecx
0x180003e97  neg     eax
0x180003e99  cmovs   eax, ecx
0x180003e9c  mov     ecx, eax
0x180003e9e  mov     eax, edx
0x180003ea0  imul    rcx, rax
0x180003ea4  cmp     rcx, r8
0x180003ea7  jbe     short loc_180003EB3
0x180003ea9  mov     ebx, 0Bh
0x180003eae  jmp     loc_180003DD2
0x180003eb3  mov     ecx, ecx
0x180003eb5  xor     edx, edx
0x180003eb7  call    GpMallocEx
0x180003ebc  mov     rsi, rax
0x180003ebf  test    rax, rax
0x180003ec2  jnz     loc_180003D91
0x180003ec8  lea     ebx, [rax+3]
0x180003ecb  jmp     loc_180003DD2
0x180003ed0  mov     rcx, [rdi]
0x180003ed3  mov     r15d, 26200Ah
0x180003ed9  test    rcx, rcx
0x180003edc  jz      loc_180003DE8
0x180003ee2  mov     edx, r15d
0x180003ee5  call    ?ConvertFormat@CopyOnWriteBitmap@@AEAA?AW4Status@@H@Z; CopyOnWriteBitmap::ConvertFormat(int)
0x180003eea  jmp     loc_180003DE8
0x180003eef  call    cs:__imp_DeleteObject
0x180003ef6  nop     dword ptr [rax+rax+00h]
0x180003efb  jmp     loc_180003C8B
0x180003f00  call    cs:__imp_DeleteObject
0x180003f07  nop     dword ptr [rax+rax+00h]
0x180003f0c  jmp     loc_180003C99
0x180003f11  mov     ebx, 2
0x180003f16  jmp     loc_180003C99
```
