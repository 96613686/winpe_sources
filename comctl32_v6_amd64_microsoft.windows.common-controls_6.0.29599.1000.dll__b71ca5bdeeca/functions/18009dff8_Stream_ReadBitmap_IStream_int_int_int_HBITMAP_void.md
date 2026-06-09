# Stream_ReadBitmap(IStream *,int,int,int,HBITMAP__ * *,void * *)

- ea: `0x18009dff8`
- end: `0x18009e3e1`
- name: `?Stream_ReadBitmap@@YAJPEAUIStream@@HHHPEAPEAUHBITMAP__@@PEAPEAX@Z`
- size: `1001`
- prototype: `__int64 __fastcall(struct IStream *, int, int, int, HBITMAP *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18009d868`
- `0x18009d950`

## callees

- `0x180027a2c`
- `0x18009dff8`
- `0x180114520`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e115`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e212`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e299`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e39b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e115`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e212`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e299`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009e39b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e127`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e2af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e127`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e2af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e220`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e3a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e220`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e3a9`
- `GDI32!DeleteObject` at `0x18009e3c0`
- `GDI32!DeleteObject` at `0x18009e3c0`
- `GDI32!CreateBitmap` at `0x18009e282`
- `GDI32!CreateBitmap` at `0x18009e282`
- `GDI32!CreateDIBSection` at `0x18009e1b9`
- `GDI32!CreateDIBSection` at `0x18009e1b9`
- `GDI32!SetDIBits` at `0x18009e33d`
- `GDI32!SetDIBits` at `0x18009e33d`
- `USER32!GetDC` at `0x18009e180`
- `USER32!GetDC` at `0x18009e180`
- `USER32!ReleaseDC` at `0x18009e20c`
- `USER32!ReleaseDC` at `0x18009e20c`

## pseudocode

```c
__int64 __fastcall Stream_ReadBitmap(struct IStream *a1, int a2, int a3, int a4, HBITMAP *a5, void **a6)
{
  HBITMAP v9; // rdi
  __int64 v11; // rax
  __int64 (__fastcall *v12)(struct IStream *, __int64 *, __int64, _QWORD); // rax
  int v13; // ebx
  int v14; // r12d
  int v15; // esi
  __int64 v16; // r14
  HANDLE ProcessHeap; // rax
  BITMAPINFO *v18; // rax
  BITMAPINFO *v19; // r15
  int v20; // ebx
  void *v21; // r13
  HDC DC; // rax
  HDC v23; // r14
  HANDLE v24; // rax
  HBITMAP Bitmap; // rax
  HANDLE v27; // rax
  int v28; // r9d
  signed int v29; // esi
  int v30; // edx
  UINT v31; // ecx
  HANDLE v32; // rax
  int nWidth; // [rsp+40h] [rbp-69h]
  UINT nWidtha; // [rsp+40h] [rbp-69h]
  int v35; // [rsp+44h] [rbp-65h]
  void *ppvBits; // [rsp+60h] [rbp-49h] BYREF
  __int64 v38; // [rsp+68h] [rbp-41h] BYREF
  int v39; // [rsp+70h] [rbp-39h]
  __int16 v40; // [rsp+74h] [rbp-35h]
  int nHeight[4]; // [rsp+78h] [rbp-31h] BYREF
  __int128 v42; // [rsp+88h] [rbp-21h]
  __int64 v43; // [rsp+98h] [rbp-11h]

  LODWORD(ppvBits) = a4;
  v38 = 0;
  v39 = 0;
  v9 = 0;
  v40 = 0;
  v43 = 0;
  v11 = *(_QWORD *)a1;
  *(_OWORD *)nHeight = 0;
  v12 = *(__int64 (__fastcall **)(struct IStream *, __int64 *, __int64, _QWORD))(v11 + 24);
  v42 = 0;
  v13 = v12(a1, &v38, 14, 0);
  if ( v13 >= 0 )
  {
    if ( (_WORD)v38 != 19778 )
    {
      v13 = -2147024883;
      goto LABEL_27;
    }
    v13 = (*(__int64 (__fastcall **)(struct IStream *, int *, __int64, _QWORD))(*(_QWORD *)a1 + 24LL))(
            a1,
            nHeight,
            40,
            0);
    if ( v13 >= 0 )
    {
      v13 = -2147024883;
      if ( nHeight[0] == 40 )
      {
        nWidth = nHeight[1];
        if ( nHeight[1] == a2 )
        {
          v14 = nHeight[2];
          if ( nHeight[2] <= a3 )
          {
            v15 = HIWORD(nHeight[3]) * LOWORD(nHeight[3]);
            if ( (v15 == a4 || a4 == 254) && v15 >= 0 )
            {
              if ( v15 <= 8 )
                v16 = 4 * (unsigned int)(1LL << v15);
              else
                v16 = 0;
              ProcessHeap = GetProcessHeap();
              v18 = (BITMAPINFO *)HeapAlloc(ProcessHeap, 8u, v16 + 40);
              v19 = v18;
              if ( !v18 )
              {
                v13 = -2147024882;
                goto LABEL_27;
              }
              v20 = nWidth;
              v21 = 0;
              *(_OWORD *)&v18->bmiHeader.biSize = *(_OWORD *)nHeight;
              *(_OWORD *)&v18->bmiHeader.biCompression = v42;
              *(_QWORD *)&v18->bmiHeader.biClrUsed = v43;
              v35 = (nWidth * v15 + 31) / 32;
              v18->bmiHeader.biSizeImage = 4 * v14 * v35;
              if ( (_DWORD)v16 )
              {
                v13 = (*(__int64 (__fastcall **)(struct IStream *, RGBQUAD *, _QWORD, _QWORD))(*(_QWORD *)a1 + 24LL))(
                        a1,
                        v18->bmiColors,
                        (unsigned int)v16,
                        0);
                if ( v13 < 0 )
                {
LABEL_24:
                  v24 = GetProcessHeap();
                  HeapFree(v24, 0, v19);
                  if ( v21 )
                  {
                    v32 = GetProcessHeap();
                    HeapFree(v32, 0, v21);
                  }
                  if ( v13 < 0 && v9 )
                  {
                    DeleteObject(v9);
                    v9 = 0;
                  }
                  goto LABEL_27;
                }
                v20 = nWidth;
              }
              DC = GetDC(0);
              v23 = DC;
              if ( v15 <= 1 )
              {
                Bitmap = CreateBitmap(v20, v14, 1u, 1u, 0);
              }
              else
              {
                if ( (_DWORD)ppvBits != 254 )
                {
                  ppvBits = 0;
                  v9 = CreateDIBSection(DC, v19, 0, &ppvBits, 0, 0);
                  if ( v9 )
                  {
                    v13 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, _QWORD))(*(_QWORD *)a1 + 24LL))(
                            a1,
                            ppvBits,
                            v19->bmiHeader.biSizeImage,
                            0);
                    if ( v13 < 0 )
                      goto LABEL_22;
                    if ( a6 )
                      *a6 = ppvBits;
                    ppvBits = 0;
                    goto LABEL_21;
                  }
                  goto LABEL_43;
                }
                Bitmap = (HBITMAP)CreateColorBitmap(v20, v14);
              }
              v9 = Bitmap;
              if ( Bitmap )
              {
                v13 = -2147024882;
                v27 = GetProcessHeap();
                v21 = HeapAlloc(v27, 8u, 0x1000u);
                if ( v21 )
                {
                  v28 = (nWidth * v15 + 31) / 32;
                  v29 = 0;
                  v30 = 4096 / (4 * v35);
                  while ( v29 < v14 )
                  {
                    v31 = v14 - v29;
                    if ( v30 <= v14 - v29 )
                      v31 = v30;
                    nWidtha = v31;
                    v13 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, _QWORD))(*(_QWORD *)a1 + 24LL))(
                            a1,
                            v21,
                            4 * v28 * v31,
                            0);
                    if ( v13 < 0 )
                      goto LABEL_22;
                    v13 = -2147024882;
                    if ( !SetDIBits(v23, v9, v29, nWidtha, v21, v19, 0) )
                      goto LABEL_22;
                    v30 = nWidtha;
                    v29 += nWidtha;
                    v28 = v35;
                  }
LABEL_21:
                  v13 = 0;
                }
LABEL_22:
                if ( v23 )
                  ReleaseDC(0, v23);
                goto LABEL_24;
              }
LABEL_43:
              v13 = -2147024882;
              goto LABEL_22;
            }
          }
        }
      }
    }
  }
LABEL_27:
  *a5 = v9;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18009dff8  push    rbp
0x18009dffa  push    rbx
0x18009dffb  push    rsi
0x18009dffc  push    rdi
0x18009dffd  push    r12
0x18009dfff  push    r13
0x18009e001  push    r14
0x18009e003  push    r15
0x18009e005  lea     rbp, [rsp-0Fh]
0x18009e00a  sub     rsp, 0B8h
0x18009e011  mov     rax, cs:__security_cookie
0x18009e018  xor     rax, rsp
0x18009e01b  mov     [rbp+47h+var_50], rax
0x18009e01f  mov     rax, [rbp+47h+arg_20]
0x18009e023  xorps   xmm0, xmm0
0x18009e026  mov     [rbp+47h+var_98], rax
0x18009e02a  mov     r14d, r9d
0x18009e02d  mov     rax, [rbp+47h+arg_28]
0x18009e031  mov     r13d, r8d
0x18009e034  mov     [rbp+47h+var_A0], rax
0x18009e038  mov     r15d, edx
0x18009e03b  xor     eax, eax
0x18009e03d  mov     dword ptr [rbp+47h+ppvBits], r9d
0x18009e041  mov     [rbp+47h+var_88], rax
0x18009e045  lea     rdx, [rbp+47h+var_88]
0x18009e049  mov     [rbp+47h+var_80], eax
0x18009e04c  xor     edi, edi
0x18009e04e  mov     [rbp+47h+var_7C], ax
0x18009e052  xor     r9d, r9d
0x18009e055  mov     [rbp+47h+var_58], rax
0x18009e059  mov     rsi, rcx
0x18009e05c  mov     rax, [rcx]
0x18009e05f  lea     r8d, [rdi+0Eh]
0x18009e063  mov     [rbp+47h+var_A8], rcx
0x18009e067  movups  xmmword ptr [rbp+47h+nHeight], xmm0
0x18009e06b  mov     rax, [rax+18h]
0x18009e06f  movups  [rbp+47h+var_68], xmm0
0x18009e073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e078  mov     ebx, eax
0x18009e07a  test    eax, eax
0x18009e07c  js      loc_18009E237
0x18009e082  mov     eax, 4D42h
0x18009e087  cmp     word ptr [rbp+47h+var_88], ax
0x18009e08b  jnz     loc_18009E3D7
0x18009e091  mov     rax, [rsi]
0x18009e094  lea     r8d, [rdi+28h]
0x18009e098  xor     r9d, r9d
0x18009e09b  lea     rdx, [rbp+47h+nHeight]
0x18009e09f  mov     rcx, rsi
0x18009e0a2  mov     rax, [rax+18h]
0x18009e0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e0ab  mov     ebx, eax
0x18009e0ad  test    eax, eax
0x18009e0af  js      loc_18009E237
0x18009e0b5  cmp     [rbp+47h+nHeight], 28h ; '('
0x18009e0b9  mov     ebx, 8007000Dh
0x18009e0be  jnz     loc_18009E237
0x18009e0c4  mov     eax, [rbp+47h+nHeight+4]
0x18009e0c7  mov     [rbp+47h+nWidth], eax
0x18009e0ca  cmp     eax, r15d
0x18009e0cd  jnz     loc_18009E237
0x18009e0d3  mov     r12d, [rbp+47h+nHeight+8]
0x18009e0d7  cmp     r12d, r13d
0x18009e0da  jg      loc_18009E237
0x18009e0e0  movzx   esi, word ptr [rbp+47h+nHeight+0Ch]
0x18009e0e4  movzx   eax, word ptr [rbp+47h+nHeight+0Eh]
0x18009e0e8  imul    esi, eax
0x18009e0eb  cmp     esi, r14d
0x18009e0ee  jnz     loc_18009E260
0x18009e0f4  test    esi, esi
0x18009e0f6  js      loc_18009E237
0x18009e0fc  cmp     esi, 8
0x18009e0ff  jle     short loc_18009E106
0x18009e101  xor     r14d, r14d
0x18009e104  jmp     short loc_18009E115
0x18009e106  mov     ecx, esi
0x18009e108  mov     r14d, 1
0x18009e10e  shl     r14, cl
0x18009e111  shl     r14d, 2
0x18009e115  call    cs:__imp_GetProcessHeap
0x18009e11b  lea     r8, [r14+28h]; dwBytes
0x18009e11f  mov     edx, 8; dwFlags
0x18009e124  mov     rcx, rax; hHeap
0x18009e127  call    cs:__imp_HeapAlloc
0x18009e12d  mov     r15, rax
0x18009e130  test    rax, rax
0x18009e133  jz      loc_18009E3CD
0x18009e139  movups  xmm0, xmmword ptr [rbp+47h+nHeight]
0x18009e13d  mov     ebx, [rbp+47h+nWidth]
0x18009e140  xor     r13d, r13d
0x18009e143  movups  xmmword ptr [rax], xmm0
0x18009e146  movups  xmm1, [rbp+47h+var_68]
0x18009e14a  lea     ecx, [r13+20h]
0x18009e14e  movups  xmmword ptr [rax+10h], xmm1
0x18009e152  movsd   xmm0, [rbp+47h+var_58]
0x18009e157  movsd   qword ptr [rax+20h], xmm0
0x18009e15c  mov     eax, esi
0x18009e15e  imul    eax, ebx
0x18009e161  add     eax, 1Fh
0x18009e164  cdq
0x18009e165  idiv    ecx
0x18009e167  mov     [rbp+47h+var_AC], eax
0x18009e16a  imul    eax, r12d
0x18009e16e  shl     eax, 2
0x18009e171  mov     [r15+14h], eax
0x18009e175  test    r14d, r14d
0x18009e178  jnz     loc_18009E356
0x18009e17e  xor     ecx, ecx; hWnd
0x18009e180  call    cs:__imp_GetDC
0x18009e186  mov     r14, rax
0x18009e189  cmp     esi, 1
0x18009e18c  jle     loc_18009E26F
0x18009e192  cmp     dword ptr [rbp+47h+ppvBits], 0FEh
0x18009e199  jz      loc_18009E382
0x18009e19f  mov     [rsp+0F0h+offset], edi; offset
0x18009e1a3  lea     r9, [rbp+47h+ppvBits]; ppvBits
0x18009e1a7  xor     r8d, r8d; usage
0x18009e1aa  mov     [rsp+0F0h+hSection], rdi; hSection
0x18009e1af  mov     rdx, r15; pbmi
0x18009e1b2  mov     [rbp+47h+ppvBits], rdi
0x18009e1b6  mov     rcx, rax; hdc
0x18009e1b9  call    cs:__imp_CreateDIBSection
0x18009e1bf  mov     rdi, rax
0x18009e1c2  test    rax, rax
0x18009e1c5  jz      loc_18009E391
0x18009e1cb  mov     rcx, [rbp+47h+var_A8]
0x18009e1cf  xor     r9d, r9d
0x18009e1d2  mov     r8d, [r15+14h]
0x18009e1d6  mov     rdx, [rcx]
0x18009e1d9  mov     rax, [rdx+18h]
0x18009e1dd  mov     rdx, [rbp+47h+ppvBits]
0x18009e1e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e1e6  mov     ebx, eax
0x18009e1e8  test    eax, eax
0x18009e1ea  js      short loc_18009E202
0x18009e1ec  mov     rcx, [rbp+47h+var_A0]
0x18009e1f0  test    rcx, rcx
0x18009e1f3  jz      short loc_18009E1FC
0x18009e1f5  mov     rax, [rbp+47h+ppvBits]
0x18009e1f9  mov     [rcx], rax
0x18009e1fc  mov     [rbp+47h+ppvBits], r13
0x18009e200  xor     ebx, ebx
0x18009e202  test    r14, r14
0x18009e205  jz      short loc_18009E212
0x18009e207  mov     rdx, r14; hDC
0x18009e20a  xor     ecx, ecx; hWnd
0x18009e20c  call    cs:__imp_ReleaseDC
0x18009e212  call    cs:__imp_GetProcessHeap
0x18009e218  mov     r8, r15; lpMem
0x18009e21b  xor     edx, edx; dwFlags
0x18009e21d  mov     rcx, rax; hHeap
0x18009e220  call    cs:__imp_HeapFree
0x18009e226  test    r13, r13
0x18009e229  jnz     loc_18009E39B
0x18009e22f  test    ebx, ebx
0x18009e231  js      loc_18009E3B4
0x18009e237  mov     rax, [rbp+47h+var_98]
0x18009e23b  mov     [rax], rdi
0x18009e23e  mov     eax, ebx
0x18009e240  mov     rcx, [rbp+47h+var_50]
0x18009e244  xor     rcx, rsp; StackCookie
0x18009e247  call    __security_check_cookie
0x18009e24c  add     rsp, 0B8h
0x18009e253  pop     r15
0x18009e255  pop     r14
0x18009e257  pop     r13
0x18009e259  pop     r12
0x18009e25b  pop     rdi
0x18009e25c  pop     rsi
0x18009e25d  pop     rbx
0x18009e25e  pop     rbp
0x18009e25f  retn
0x18009e260  cmp     r14d, 0FEh
0x18009e267  jz      loc_18009E0F4
0x18009e26d  jmp     short loc_18009E237
0x18009e26f  mov     r9d, 1; nBitCount
0x18009e275  mov     [rsp+0F0h+hSection], rdi; lpBits
0x18009e27a  mov     r8d, r9d; nPlanes
0x18009e27d  mov     edx, r12d; nHeight
0x18009e280  mov     ecx, ebx; nWidth
0x18009e282  call    cs:__imp_CreateBitmap
0x18009e288  mov     rdi, rax
0x18009e28b  test    rax, rax
0x18009e28e  jz      loc_18009E391
0x18009e294  mov     ebx, 8007000Eh
0x18009e299  call    cs:__imp_GetProcessHeap
0x18009e29f  mov     esi, 1000h
0x18009e2a4  mov     edx, 8; dwFlags
0x18009e2a9  mov     rcx, rax; hHeap
0x18009e2ac  mov     r8d, esi; dwBytes
0x18009e2af  call    cs:__imp_HeapAlloc
0x18009e2b5  mov     r13, rax
0x18009e2b8  test    rax, rax
0x18009e2bb  jz      loc_18009E202
0x18009e2c1  mov     r9d, [rbp+47h+var_AC]
0x18009e2c5  mov     eax, esi
0x18009e2c7  cdq
0x18009e2c8  lea     ecx, ds:0[r9*4]
0x18009e2d0  idiv    ecx
0x18009e2d2  xor     esi, esi
0x18009e2d4  mov     edx, eax
0x18009e2d6  cmp     esi, r12d
0x18009e2d9  jge     loc_18009E200
0x18009e2df  mov     ecx, r12d
0x18009e2e2  sub     ecx, esi
0x18009e2e4  cmp     edx, ecx
0x18009e2e6  cmovle  ecx, edx
0x18009e2e9  mov     edx, ecx
0x18009e2eb  mov     [rbp+47h+nWidth], ecx
0x18009e2ee  mov     rcx, [rbp+47h+var_A8]
0x18009e2f2  mov     r8d, edx
0x18009e2f5  imul    r8d, r9d
0x18009e2f9  mov     rdx, r13
0x18009e2fc  xor     r9d, r9d
0x18009e2ff  mov     rax, [rcx]
0x18009e302  shl     r8d, 2
0x18009e306  mov     rax, [rax+18h]
0x18009e30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e30f  mov     ebx, eax
0x18009e311  test    eax, eax
0x18009e313  js      loc_18009E202
0x18009e319  mov     r9d, [rbp+47h+nWidth]; cLines
0x18009e31d  mov     r8d, esi; start
0x18009e320  mov     [rsp+0F0h+ColorUse], 0; ColorUse
0x18009e328  mov     rdx, rdi; hbm
0x18009e32b  mov     qword ptr [rsp+0F0h+offset], r15; lpbmi
0x18009e330  mov     rcx, r14; hdc
0x18009e333  mov     [rsp+0F0h+hSection], r13; lpBits
0x18009e338  mov     ebx, 8007000Eh
0x18009e33d  call    cs:__imp_SetDIBits
0x18009e343  test    eax, eax
0x18009e345  jz      loc_18009E202
0x18009e34b  mov     edx, [rbp+47h+nWidth]
0x18009e34e  add     esi, edx
0x18009e350  mov     r9d, [rbp+47h+var_AC]
0x18009e354  jmp     short loc_18009E2D6
0x18009e356  mov     rcx, [rbp+47h+var_A8]
0x18009e35a  lea     rdx, [r15+28h]
0x18009e35e  xor     r9d, r9d
0x18009e361  mov     r8d, r14d
0x18009e364  mov     rax, [rcx]
0x18009e367  mov     rax, [rax+18h]
0x18009e36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e370  mov     ebx, eax
0x18009e372  test    eax, eax
0x18009e374  js      loc_18009E212
0x18009e37a  mov     ebx, [rbp+47h+nWidth]
0x18009e37d  jmp     loc_18009E17E
0x18009e382  mov     edx, r12d; cy
0x18009e385  mov     ecx, ebx; cx
0x18009e387  call    CreateColorBitmap
0x18009e38c  jmp     loc_18009E288
0x18009e391  mov     ebx, 8007000Eh
0x18009e396  jmp     loc_18009E202
0x18009e39b  call    cs:__imp_GetProcessHeap
0x18009e3a1  mov     r8, r13; lpMem
0x18009e3a4  xor     edx, edx; dwFlags
0x18009e3a6  mov     rcx, rax; hHeap
0x18009e3a9  call    cs:__imp_HeapFree
0x18009e3af  jmp     loc_18009E22F
0x18009e3b4  test    rdi, rdi
0x18009e3b7  jz      loc_18009E237
0x18009e3bd  mov     rcx, rdi; ho
0x18009e3c0  call    cs:__imp_DeleteObject
0x18009e3c6  xor     edi, edi
0x18009e3c8  jmp     loc_18009E237
0x18009e3cd  mov     ebx, 8007000Eh
0x18009e3d2  jmp     loc_18009E237
0x18009e3d7  mov     ebx, 8007000Dh
0x18009e3dc  jmp     loc_18009E237
```
