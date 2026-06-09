# CopyOnWriteBitmap::CreateFromHICON(HICON__ *,CopyOnWriteBitmap * *)

- ea: `0x180064e44`
- end: `0x180065191`
- name: `?CreateFromHICON@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHICON__@@PEAPEAV1@@Z`
- size: `845`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800684e4`

## callees

- `0x180010bd0`
- `0x180017190`
- `0x180017a3c`
- `0x180064e44`
- `0x180065198`
- `0x18008ec3c`
- `0x180105d40`
- `0x18010673c`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064f4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064f4c`
- `USER32!GetIconInfo` at `0x180064e89`
- `USER32!GetIconInfo` at `0x180064e89`
- `USER32!GetDC` at `0x1800650cb`
- `USER32!GetDC` at `0x1800650cb`
- `USER32!ReleaseDC` at `0x18006506f`
- `USER32!ReleaseDC` at `0x18006506f`
- `GDI32!GetStockObject` at `0x180064eba`
- `GDI32!GetStockObject` at `0x180064eba`
- `GDI32!GetDIBits` at `0x180064f89`
- `GDI32!GetDIBits` at `0x18006511d`
- `GDI32!GetDIBits` at `0x180064f89`
- `GDI32!GetDIBits` at `0x18006511d`
- `GDI32!DeleteObject` at `0x180064eea`
- `GDI32!DeleteObject` at `0x180064f00`
- `GDI32!DeleteObject` at `0x180064eea`
- `GDI32!DeleteObject` at `0x180064f00`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::CreateFromHICON(HICON a1, CopyOnWriteBitmap **a2)
{
  HGDIOBJ StockObject; // rax
  unsigned int v4; // ebx
  _DWORD *lpvBits; // rsi
  CopyOnWriteBitmap *v7; // rcx
  unsigned int v8; // ecx
  int v9; // r12d
  _DWORD *v10; // r10
  unsigned int v11; // r15d
  unsigned int v12; // r9d
  _DWORD *v13; // r11
  _DWORD *v14; // rax
  _DWORD *v15; // rdx
  unsigned int v16; // r8d
  CopyOnWriteBitmap *v17; // rdi
  __int64 v18; // rcx
  int v19; // eax
  unsigned int v20; // eax
  HDC DC; // r14
  LONG biHeight; // ecx
  LONG v23; // ecx
  unsigned __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned __int64 v26; // rcx
  ICONINFO piconinfo; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h]
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
      {
        v20 = CopyOnWriteBitmap::ConvertFormat(*a2, 2498570, 1, 0, 0, 0);
        MapHRESULTToGpStatus(v20);
      }
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
          v23 = -biHeight;
          v24 = 4LL * (unsigned int)bmi.bmiHeader.biWidth;
          bmi.bmiHeader.biHeight = v23;
          *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
          bmi.bmiHeader.biSizeImage = 0;
          *(_QWORD *)&bmi.bmiHeader.biClrUsed = 0;
          if ( v24 > 0xFFFFFFFF )
            goto LABEL_39;
          v25 = -v23;
          if ( v23 > 0 )
            v25 = v23;
          v26 = (unsigned int)v24 * (unsigned __int64)v25;
          if ( v26 <= 0xFFFFFFFF )
          {
            lpvBits = HeapAlloc(GpRuntime::GpMemHeap, 0, (unsigned int)v26);
            if ( lpvBits )
            {
              if ( GetDIBits(DC, piconinfo.hbmMask, 0, -bmi.bmiHeader.biHeight, lpvBits, &bmi, 0) )
              {
                v7 = *a2;
                v28 = 0;
                v29 = 0;
                v4 = CopyOnWriteBitmap::LockBits(v7, 0, 3, 2498570, &v28);
                if ( !v4 )
                {
                  v8 = DWORD1(v28);
                  v9 = 4 * bmi.bmiHeader.biWidth;
                  if ( DWORD1(v28) )
                  {
                    v10 = (_DWORD *)v29;
                    v11 = 0;
                    v12 = v28;
                    v13 = lpvBits;
                    do
                    {
                      v14 = v10;
                      v15 = v13;
                      v16 = 0;
                      if ( v12 )
                      {
                        do
                        {
                          if ( *v15 )
                          {
                            *v14 = 0;
                            v12 = v28;
                          }
                          ++v14;
                          ++v15;
                          ++v16;
                        }
                        while ( v16 < v12 );
                        v8 = DWORD1(v28);
                      }
                      ++v11;
                      v10 = (_DWORD *)((char *)v10 + SDWORD2(v28));
                      v13 = (_DWORD *)((char *)v13 + v9);
                    }
                    while ( v11 < v8 );
                  }
                  v17 = *a2;
                  v18 = *((_QWORD *)v17 + 11);
                  if ( v18 )
                  {
                    v19 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v18 + 48LL))(v18, &v28);
                    --*((_DWORD *)v17 + 15);
                    if ( v19 < 0 )
                      MapHRESULTToGpStatus((unsigned int)v19);
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
LABEL_39:
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
0x180064e44  mov     [rsp-8+arg_10], rbx
0x180064e49  push    rbp
0x180064e4a  push    rsi
0x180064e4b  push    rdi
0x180064e4c  push    r12
0x180064e4e  push    r13
0x180064e50  push    r14
0x180064e52  push    r15
0x180064e54  lea     rbp, [rsp-3C0h]
0x180064e5c  sub     rsp, 4C0h
0x180064e63  mov     rax, cs:__security_cookie
0x180064e6a  xor     rax, rsp
0x180064e6d  mov     [rbp+3F0h+var_40], rax
0x180064e74  xorps   xmm0, xmm0
0x180064e77  mov     rdi, rdx
0x180064e7a  lea     rdx, [rsp+4F0h+piconinfo]; piconinfo
0x180064e7f  movups  xmmword ptr [rsp+4F0h+piconinfo.fIcon], xmm0
0x180064e84  movups  xmmword ptr [rsp+4F0h+piconinfo.hbmMask], xmm0
0x180064e89  call    cs:__imp_GetIconInfo
0x180064e90  nop     dword ptr [rax+rax+00h]
0x180064e95  xor     r13d, r13d
0x180064e98  test    eax, eax
0x180064e9a  jz      loc_180065187
0x180064ea0  cmp     [rsp+4F0h+piconinfo.fIcon], r13d
0x180064ea5  jz      loc_180064F39
0x180064eab  cmp     [rsp+4F0h+piconinfo.hbmColor], r13
0x180064eb0  jz      loc_180064F39
0x180064eb6  lea     ecx, [r13+0Fh]; i
0x180064eba  call    cs:__imp_GetStockObject
0x180064ec1  nop     dword ptr [rax+rax+00h]
0x180064ec6  mov     rcx, [rsp+4F0h+piconinfo.hbmColor]
0x180064ecb  mov     r8, rdi
0x180064ece  mov     rdx, rax
0x180064ed1  call    ?CreateFromHBITMAP@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAUHPALETTE__@@PEAPEAV1@@Z; CopyOnWriteBitmap::CreateFromHBITMAP(HBITMAP__ *,HPALETTE__ *,CopyOnWriteBitmap * *)
0x180064ed6  mov     ebx, eax
0x180064ed8  test    eax, eax
0x180064eda  jz      loc_180065087
0x180064ee0  mov     rcx, [rsp+4F0h+piconinfo.hbmMask]; ho
0x180064ee5  test    rcx, rcx
0x180064ee8  jz      short loc_180064EF6
0x180064eea  call    cs:__imp_DeleteObject
0x180064ef1  nop     dword ptr [rax+rax+00h]
0x180064ef6  mov     rcx, [rsp+4F0h+piconinfo.hbmColor]; ho
0x180064efb  test    rcx, rcx
0x180064efe  jz      short loc_180064F0C
0x180064f00  call    cs:__imp_DeleteObject
0x180064f07  nop     dword ptr [rax+rax+00h]
0x180064f0c  mov     eax, ebx
0x180064f0e  mov     rcx, [rbp+3F0h+var_40]
0x180064f15  xor     rcx, rsp; StackCookie
0x180064f18  call    __security_check_cookie
0x180064f1d  mov     rbx, [rsp+4F0h+arg_10]
0x180064f25  add     rsp, 4C0h
0x180064f2c  pop     r15
0x180064f2e  pop     r14
0x180064f30  pop     r13
0x180064f32  pop     r12
0x180064f34  pop     rdi
0x180064f35  pop     rsi
0x180064f36  pop     rbp
0x180064f37  retn
0x180064f39  mov     ebx, 2
0x180064f3e  jmp     short loc_180064EE0
0x180064f40  mov     r8d, ecx; dwBytes
0x180064f43  xor     edx, edx; dwFlags
0x180064f45  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x180064f4c  call    cs:__imp_HeapAlloc
0x180064f53  nop     dword ptr [rax+rax+00h]
0x180064f58  mov     rsi, rax
0x180064f5b  test    rax, rax
0x180064f5e  jz      loc_180065080
0x180064f64  mov     r9d, [rbp+3F0h+bmi.bmiHeader.biHeight]
0x180064f68  lea     rax, [rbp+3F0h+bmi]
0x180064f6c  mov     rdx, [rsp+4F0h+piconinfo.hbmMask]; hbm
0x180064f71  neg     r9d; cLines
0x180064f74  mov     [rsp+4F0h+usage], r13d; usage
0x180064f79  xor     r8d, r8d; start
0x180064f7c  mov     [rsp+4F0h+lpbmi], rax; lpbmi
0x180064f81  mov     rcx, r14; hdc
0x180064f84  mov     [rsp+4F0h+lpvBits], rsi; lpvBits
0x180064f89  call    cs:__imp_GetDIBits
0x180064f90  nop     dword ptr [rax+rax+00h]
0x180064f95  test    eax, eax
0x180064f97  jz      loc_180065062
0x180064f9d  mov     rcx, [rdi]
0x180064fa0  lea     rax, [rsp+4F0h+var_490]
0x180064fa5  xorps   xmm0, xmm0
0x180064fa8  mov     [rsp+4F0h+lpvBits], rax
0x180064fad  xor     edx, edx
0x180064faf  mov     r9d, r15d
0x180064fb2  movups  [rsp+4F0h+var_490], xmm0
0x180064fb7  movups  [rsp+4F0h+var_480], xmm0
0x180064fbc  lea     r8d, [rdx+3]
0x180064fc0  call    ?LockBits@CopyOnWriteBitmap@@AEBA?AW4Status@@PEBVGpRect@GpRuntime@@IHPEAVBitmapData@@@Z; CopyOnWriteBitmap::LockBits(GpRuntime::GpRect const *,uint,int,BitmapData *)
0x180064fc5  mov     ebx, eax
0x180064fc7  test    eax, eax
0x180064fc9  jnz     loc_180065062
0x180064fcf  mov     eax, [rbp+3F0h+bmi.bmiHeader.biWidth]
0x180064fd2  mov     ecx, dword ptr [rsp+4F0h+var_490+4]
0x180064fd6  lea     r12d, ds:0[rax*4]
0x180064fde  test    ecx, ecx
0x180064fe0  jz      short loc_180065037
0x180064fe2  mov     r10, qword ptr [rsp+4F0h+var_480]
0x180064fe7  mov     r15d, r13d
0x180064fea  mov     r9d, dword ptr [rsp+4F0h+var_490]
0x180064fef  mov     r11, rsi
0x180064ff2  mov     rax, r10
0x180064ff5  mov     rdx, r11
0x180064ff8  mov     r8d, r13d
0x180064ffb  test    r9d, r9d
0x180064ffe  jz      short loc_180065021
0x180065000  cmp     [rdx], r13d
0x180065003  jz      short loc_18006500D
0x180065005  mov     [rax], r13d
0x180065008  mov     r9d, dword ptr [rsp+4F0h+var_490]
0x18006500d  add     rax, 4
0x180065011  add     rdx, 4
0x180065015  inc     r8d
0x180065018  cmp     r8d, r9d
0x18006501b  jb      short loc_180065000
0x18006501d  mov     ecx, dword ptr [rsp+4F0h+var_490+4]
0x180065021  movsxd  rax, dword ptr [rsp+4F0h+var_490+8]
0x180065026  inc     r15d
0x180065029  add     r10, rax
0x18006502c  movsxd  rax, r12d
0x18006502f  add     r11, rax
0x180065032  cmp     r15d, ecx
0x180065035  jb      short loc_180064FF2
0x180065037  mov     rdi, [rdi]
0x18006503a  mov     rcx, [rdi+58h]
0x18006503e  test    rcx, rcx
0x180065041  jz      short loc_180065062
0x180065043  mov     rax, [rcx]
0x180065046  lea     rdx, [rsp+4F0h+var_490]
0x18006504b  mov     rax, [rax+30h]
0x18006504f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065054  dec     dword ptr [rdi+3Ch]
0x180065057  test    eax, eax
0x180065059  jns     short loc_180065062
0x18006505b  mov     ecx, eax
0x18006505d  call    ?MapHRESULTToGpStatus@@YA?AW4Status@@J@Z; MapHRESULTToGpStatus(long)
0x180065062  mov     rcx, rsi
0x180065065  call    GpFree
0x18006506a  mov     rdx, r14; hDC
0x18006506d  xor     ecx, ecx; hWnd
0x18006506f  call    cs:__imp_ReleaseDC
0x180065076  nop     dword ptr [rax+rax+00h]
0x18006507b  jmp     loc_180064EE0
0x180065080  mov     ebx, 3
0x180065085  jmp     short loc_18006506A
0x180065087  mov     rcx, [rdi]
0x18006508a  mov     esi, 1
0x18006508f  mov     r15d, 26200Ah
0x180065095  test    rcx, rcx
0x180065098  jz      short loc_1800650B9
0x18006509a  mov     byte ptr [rsp+4F0h+lpbmi], r13b
0x18006509f  xor     r9d, r9d
0x1800650a2  mov     r8d, esi
0x1800650a5  mov     [rsp+4F0h+lpvBits], r13
0x1800650aa  mov     edx, r15d
0x1800650ad  call    ?ConvertFormat@CopyOnWriteBitmap@@AEAA?AW4Status@@HW4DitherType@@W4PaletteType@@PEAUColorPalette@@E@Z; CopyOnWriteBitmap::ConvertFormat(int,DitherType,PaletteType,ColorPalette *,uchar)
0x1800650b2  mov     ecx, eax
0x1800650b4  call    ?MapHRESULTToGpStatus@@YA?AW4Status@@J@Z; MapHRESULTToGpStatus(long)
0x1800650b9  cmp     [rsp+4F0h+piconinfo.hbmMask], r13
0x1800650be  jz      loc_180064EF6
0x1800650c4  xor     ecx, ecx; hWnd
0x1800650c6  mov     ebx, 7
0x1800650cb  call    cs:__imp_GetDC
0x1800650d2  nop     dword ptr [rax+rax+00h]
0x1800650d7  mov     r14, rax
0x1800650da  test    rax, rax
0x1800650dd  jz      loc_180064EE0
0x1800650e3  xor     edx, edx; Val
0x1800650e5  lea     rcx, [rbp+3F0h+bmi.bmiHeader.biWidth]; void *
0x1800650e9  mov     r8d, 424h; Size
0x1800650ef  call    memset_0
0x1800650f4  mov     rdx, [rsp+4F0h+piconinfo.hbmMask]; hbm
0x1800650f9  lea     rax, [rbp+3F0h+bmi]
0x1800650fd  mov     [rsp+4F0h+usage], r13d; usage
0x180065102  lea     r12d, [rbx+21h]
0x180065106  mov     [rsp+4F0h+lpbmi], rax; lpbmi
0x18006510b  xor     r9d, r9d; cLines
0x18006510e  xor     r8d, r8d; start
0x180065111  mov     [rsp+4F0h+lpvBits], r13; lpvBits
0x180065116  mov     rcx, r14; hdc
0x180065119  mov     [rbp+3F0h+bmi.bmiHeader.biSize], r12d
0x18006511d  call    cs:__imp_GetDIBits
0x180065124  nop     dword ptr [rax+rax+00h]
0x180065129  test    eax, eax
0x18006512b  jz      loc_18006506A
0x180065131  mov     ecx, [rbp+3F0h+bmi.bmiHeader.biHeight]
0x180065134  mov     r8d, 0FFFFFFFFh
0x18006513a  mov     edx, [rbp+3F0h+bmi.bmiHeader.biWidth]
0x18006513d  neg     ecx
0x18006513f  mov     [rbp+3F0h+bmi.bmiHeader.biSize], r12d
0x180065143  cmovs   ecx, [rbp+3F0h+bmi.bmiHeader.biHeight]
0x180065147  neg     ecx
0x180065149  shl     rdx, 2
0x18006514d  mov     [rbp+3F0h+bmi.bmiHeader.biHeight], ecx
0x180065150  mov     qword ptr [rbp+3F0h+bmi.bmiHeader.biPlanes], 200001h
0x180065158  mov     [rbp+3F0h+bmi.bmiHeader.biSizeImage], r13d
0x18006515c  mov     qword ptr [rbp+3F0h+bmi.bmiHeader.biClrUsed], r13
0x180065160  cmp     rdx, r8
0x180065163  ja      short loc_18006517D
0x180065165  mov     eax, ecx
0x180065167  neg     eax
0x180065169  cmovs   eax, ecx
0x18006516c  mov     ecx, eax
0x18006516e  mov     eax, edx
0x180065170  imul    rcx, rax
0x180065174  cmp     rcx, r8
0x180065177  jbe     loc_180064F40
0x18006517d  mov     ebx, 0Bh
0x180065182  jmp     loc_18006506A
0x180065187  mov     ebx, 2
0x18006518c  jmp     loc_180064F0C
```
