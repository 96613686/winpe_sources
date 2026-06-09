# Common_GetIcon

- ea: `0x180044100`
- end: `0x18004461e`
- name: `Common_GetIcon`
- size: `1310`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180044040`
- `0x180044080`
- `0x1800440c0`
- `0x180146540`

## callees

- `0x180044100`
- `0x18007b714`
- `0x180114520`
- `0x1801d1010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18004449c`
- `GDI32!DeleteObject` at `0x1800444e9`
- `GDI32!DeleteObject` at `0x18004449c`
- `GDI32!DeleteObject` at `0x1800444e9`
- `GDI32!PatBlt` at `0x1800442d1`
- `GDI32!PatBlt` at `0x180044372`
- `GDI32!PatBlt` at `0x1800442d1`
- `GDI32!PatBlt` at `0x180044372`
- `GDI32!SelectObject` at `0x1800442ae`
- `GDI32!SelectObject` at `0x18004434f`
- `GDI32!SelectObject` at `0x1800443f4`
- `GDI32!SelectObject` at `0x1800442ae`
- `GDI32!SelectObject` at `0x18004434f`
- `GDI32!SelectObject` at `0x1800443f4`
- `GDI32!DeleteDC` at `0x180044493`
- `GDI32!DeleteDC` at `0x180044493`
- `GDI32!CreateCompatibleDC` at `0x180044296`
- `GDI32!CreateCompatibleDC` at `0x180044296`
- `GDI32!CreateCompatibleBitmap` at `0x18004424f`
- `GDI32!CreateCompatibleBitmap` at `0x18004424f`
- `GDI32!CreateBitmap` at `0x180044282`
- `GDI32!CreateBitmap` at `0x180044282`
- `GDI32!CreateDIBSection` at `0x1800445ba`
- `GDI32!CreateDIBSection` at `0x1800445ba`
- `GDI32!GetDeviceCaps` at `0x180044226`
- `GDI32!GetDeviceCaps` at `0x180044226`
- `USER32!CreateIconIndirect` at `0x180044482`
- `USER32!CreateIconIndirect` at `0x180044482`
- `USER32!GetDC` at `0x180044215`
- `USER32!GetDC` at `0x180044593`
- `USER32!GetDC` at `0x180044215`
- `USER32!GetDC` at `0x180044593`
- `USER32!GetSystemMetrics` at `0x180044237`
- `USER32!GetSystemMetrics` at `0x18004452f`
- `USER32!GetSystemMetrics` at `0x180044237`
- `USER32!GetSystemMetrics` at `0x18004452f`
- `USER32!ReleaseDC` at `0x18004425d`
- `USER32!ReleaseDC` at `0x1800445c8`
- `USER32!ReleaseDC` at `0x18004425d`
- `USER32!ReleaseDC` at `0x1800445c8`

## pseudocode

```c
__int64 __fastcall Common_GetIcon(
        int (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        __int64 a2,
        unsigned int a3,
        int a4,
        HICON *a5)
{
  int (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rax
  __int64 result; // rax
  HICON v9; // rdi
  int (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rax
  int v11; // r14d
  unsigned int v12; // r13d
  unsigned int v13; // r15d
  unsigned int v14; // r12d
  HDC v15; // rsi
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v17; // r15
  HBITMAP Bitmap; // r12
  HDC CompatibleDC; // rax
  HDC v20; // rsi
  int (__fastcall **v21)(_QWORD, _QWORD, _QWORD); // rax
  int (__fastcall **v22)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v23; // r9
  int v24; // r10d
  _BYTE *i; // r11
  unsigned int v26; // eax
  WORD v27; // ax
  HDC DC; // rsi
  int v29; // edx
  int v30; // edx
  __int64 v31; // rcx
  int v32; // ecx
  int v33; // [rsp+30h] [rbp-D0h]
  int cy; // [rsp+48h] [rbp-B8h] BYREF
  int nWidth; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  int (__fastcall ***v40)(_QWORD, _QWORD, _QWORD); // [rsp+68h] [rbp-98h]
  __int64 v41; // [rsp+70h] [rbp-90h]
  HDC v42; // [rsp+78h] [rbp-88h]
  __int128 v43; // [rsp+80h] [rbp-80h]
  __int64 v44; // [rsp+90h] [rbp-70h]
  unsigned __int64 v45; // [rsp+98h] [rbp-68h]
  __int128 v46; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+B0h] [rbp-50h]
  void *ppvBits; // [rsp+C0h] [rbp-40h] BYREF
  ICONINFO piconinfo; // [rsp+C8h] [rbp-38h] BYREF
  int v50; // [rsp+E8h] [rbp-18h] BYREF
  int v51; // [rsp+ECh] [rbp-14h] BYREF
  BITMAPINFO pbmi; // [rsp+F0h] [rbp-10h] BYREF

  v33 = a4;
  v7 = (*a1)[30];
  nWidth = 0;
  cy = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  ppvBits = 0;
  v50 = 0;
  result = ((__int64 (__fastcall *)(_QWORD, _QWORD, int *))v7)(a1, a3, &v50);
  if ( (int)result >= 0 )
  {
    v9 = 0;
    v10 = **a1;
    v11 = v50 & 1;
    v38 = 0;
    v51 = 0;
    if ( v10(a1, &GUID_e94cc23b_0916_4ba6_93f4_aa52b5355ee8, &v38) >= 0 )
    {
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v38 + 32LL))(v38, &v51);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    (*a1)[16](a1, (GUID *)&nWidth, (__int64 *)&cy);
    v12 = -2147024882;
    if ( (v51 & 0xFE) == 0x20 )
    {
      pbmi.bmiHeader.biSize = 40;
      v17 = 0;
      pbmi.bmiHeader.biWidth = nWidth;
      pbmi.bmiHeader.biHeight = cy;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 1;
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      if ( v11 )
        v27 = 32;
      else
        v27 = 24;
      pbmi.bmiHeader.biBitCount = v27;
      pbmi.bmiHeader.biCompression = 0;
      DC = GetDC(0);
      if ( DC )
      {
        v17 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
        ReleaseDC(0, DC);
      }
      v29 = a4 | 0x1000;
      if ( (a4 & 0x10000) != 0 )
        v29 = a4;
      v33 = v29;
    }
    else
    {
      v13 = cy;
      v14 = nWidth;
      v11 = 0;
      v15 = GetDC(0);
      if ( (GetDeviceCaps(v15, 38) & 0x100) != 0 || GetSystemMetrics(80) <= 1 || GetSystemMetrics(81) )
        CompatibleBitmap = CreateCompatibleBitmap(v15, v14, v13);
      else
        CompatibleBitmap = (HBITMAP)CreateDIB(v15, v14, v13, 0);
      v17 = CompatibleBitmap;
      ReleaseDC(0, v15);
    }
    if ( v17 )
    {
      Bitmap = CreateBitmap(nWidth, cy, 1u, 1u, 0);
      if ( Bitmap )
      {
        CompatibleDC = CreateCompatibleDC(0);
        v20 = CompatibleDC;
        if ( CompatibleDC )
        {
          SelectObject(CompatibleDC, Bitmap);
          PatBlt(v20, 0, 0, nWidth, cy, 0xFF0062u);
          v47 = 0;
          v41 = a3;
          v46 = 0;
          v42 = v20;
          v39 = 88;
          v44 = 0;
          v40 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
          v43 = 0u;
          v45 = 0xFF000000FF000000uLL;
          LODWORD(v46) = v33 | 0x10;
          v21 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*a1;
          DWORD1(v46) = 13369376;
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v21[8])(a1, &v39);
          SelectObject(v20, v17);
          PatBlt(v20, 0, 0, nWidth, cy, 0x42u);
          v47 = 0;
          v41 = a3;
          v46 = 0;
          v42 = v20;
          v39 = 88;
          v44 = 0;
          v40 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))a1;
          v43 = 0u;
          v45 = 0xFF000000FF000000uLL;
          LODWORD(v46) = v33 | 1;
          v22 = (int (__fastcall **)(_QWORD, _QWORD, _QWORD))*a1;
          DWORD1(v46) = 13369376;
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))v22[8])(a1, &v39);
          SelectObject(v20, g_hbmDcDeselect);
          if ( v11 )
          {
            v23 = 0;
            v24 = nWidth * cy;
            for ( i = ppvBits; (int)v23 < v24; v23 = (unsigned int)(v23 + 1) )
            {
              v26 = (unsigned __int8)i[4 * v23 + 3];
              if ( (_BYTE)v26 )
              {
                i[4 * v23 + 2] = 255 * (unsigned int)(unsigned __int8)i[4 * v23 + 2] / v26;
                i[4 * v23 + 1] = 255 * (unsigned int)(unsigned __int8)i[4 * v23 + 1] / v26;
                i[4 * v23] = 255 * (unsigned int)(unsigned __int8)i[4 * v23] / v26;
              }
            }
          }
          *(_QWORD *)&piconinfo.fIcon = 1;
          piconinfo.yHotspot = 0;
          piconinfo.hbmColor = v17;
          piconinfo.hbmMask = Bitmap;
          v9 = CreateIconIndirect(&piconinfo);
          if ( v9 )
          {
            DeleteObject(Bitmap);
            if ( !v33 )
            {
              v30 = *(_DWORD *)(a2 + 64);
              v31 = 2LL * v30;
              *(_DWORD *)(a2 + 8 * v31 + 8) = a3;
              *(_QWORD *)(a2 + 8 * v31) = v9;
              v32 = 0;
              if ( v30 != 3 )
                v32 = v30 + 1;
              *(_DWORD *)(a2 + 64) = v32;
            }
            v12 = 0;
          }
          DeleteDC(v20);
        }
      }
      DeleteObject(v17);
    }
    *a5 = v9;
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180044100  push    rbp
0x180044102  push    rbx
0x180044103  push    rsi
0x180044104  push    r12
0x180044106  lea     rbp, [rsp-58h]
0x18004410b  sub     rsp, 158h
0x180044112  mov     rax, cs:__security_cookie
0x180044119  xor     rax, rsp
0x18004411c  mov     [rbp+70h+var_50], rax
0x180044120  mov     rax, [rbp+70h+arg_20]
0x180044127  xor     esi, esi
0x180044129  mov     [rsp+170h+var_130], rax
0x18004412e  xorps   xmm0, xmm0
0x180044131  mov     rax, [rcx]
0x180044134  mov     r12d, r9d
0x180044137  mov     [rsp+170h+var_140], r9d
0x18004413c  mov     rbx, rcx
0x18004413f  mov     r9d, r8d
0x180044142  mov     [rsp+170h+var_13C], r8d
0x180044147  mov     [rsp+170h+var_138], rdx
0x18004414c  lea     r8, [rbp+70h+var_88]
0x180044150  mov     rax, [rax+0F0h]
0x180044157  mov     edx, r9d
0x18004415a  mov     [rsp+170h+nWidth], esi
0x18004415e  mov     [rsp+170h+cy], esi
0x180044162  movups  xmmword ptr [rbp+70h+piconinfo.fIcon], xmm0
0x180044166  mov     [rbp+70h+ppvBits], rsi
0x18004416a  movups  xmmword ptr [rbp+70h+piconinfo.hbmMask], xmm0
0x18004416e  mov     [rbp+70h+var_88], esi
0x180044171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044176  test    eax, eax
0x180044178  js      loc_1800444CD
0x18004417e  mov     rax, [rbx]
0x180044181  lea     r8, [rsp+170h+var_120]
0x180044186  mov     [rsp+170h+var_20], rdi
0x18004418e  lea     rdx, _GUID_e94cc23b_0916_4ba6_93f4_aa52b5355ee8
0x180044195  mov     [rsp+170h+var_28], r13
0x18004419d  mov     rcx, rbx
0x1800441a0  mov     [rsp+170h+var_30], r14
0x1800441a8  mov     edi, esi
0x1800441aa  mov     r14d, [rbp+70h+var_88]
0x1800441ae  mov     rax, [rax]
0x1800441b1  and     r14d, 1
0x1800441b5  mov     [rsp+170h+var_38], r15
0x1800441bd  mov     [rsp+170h+var_120], rsi
0x1800441c2  mov     [rbp+70h+var_84], esi
0x1800441c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441ca  test    eax, eax
0x1800441cc  jns     loc_1800444FF
0x1800441d2  mov     rax, [rbx]
0x1800441d5  lea     r8, [rsp+170h+cy]
0x1800441da  lea     rdx, [rsp+170h+nWidth]
0x1800441df  mov     rcx, rbx
0x1800441e2  mov     rax, [rax+80h]
0x1800441e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441ee  mov     eax, [rbp+70h+var_84]
0x1800441f1  mov     r13d, 8007000Eh
0x1800441f7  and     al, 0FEh
0x1800441f9  mov     ecx, 1
0x1800441fe  cmp     al, 20h ; ' '
0x180044200  jz      loc_180044553
0x180044206  mov     r15d, [rsp+170h+cy]
0x18004420b  xor     ecx, ecx; hWnd
0x18004420d  mov     r12d, [rsp+170h+nWidth]
0x180044212  mov     r14d, esi
0x180044215  call    cs:__imp_GetDC
0x18004421b  mov     rcx, rax; hdc
0x18004421e  mov     edx, 26h ; '&'; index
0x180044223  mov     rsi, rax
0x180044226  call    cs:__imp_GetDeviceCaps
0x18004422c  bt      eax, 8
0x180044230  jb      short loc_180044246
0x180044232  mov     ecx, 50h ; 'P'; nIndex
0x180044237  call    cs:__imp_GetSystemMetrics
0x18004423d  cmp     eax, 1
0x180044240  jg      loc_18004452A
0x180044246  mov     r8d, r15d; cy
0x180044249  mov     edx, r12d; cx
0x18004424c  mov     rcx, rsi; hdc
0x18004424f  call    cs:__imp_CreateCompatibleBitmap
0x180044255  mov     rdx, rsi; hDC
0x180044258  xor     ecx, ecx; hWnd
0x18004425a  mov     r15, rax
0x18004425d  call    cs:__imp_ReleaseDC
0x180044263  test    r15, r15
0x180044266  jz      loc_1800444A2
0x18004426c  mov     edx, [rsp+170h+cy]; nHeight
0x180044270  mov     r9d, 1; nBitCount
0x180044276  mov     ecx, [rsp+170h+nWidth]; nWidth
0x18004427a  mov     r8d, r9d; nPlanes
0x18004427d  mov     [rsp+170h+lpBits], rdi; lpBits
0x180044282  call    cs:__imp_CreateBitmap
0x180044288  mov     r12, rax
0x18004428b  test    rax, rax
0x18004428e  jz      loc_180044499
0x180044294  xor     ecx, ecx; hdc
0x180044296  call    cs:__imp_CreateCompatibleDC
0x18004429c  mov     rsi, rax
0x18004429f  test    rax, rax
0x1800442a2  jz      loc_180044499
0x1800442a8  mov     rdx, r12; h
0x1800442ab  mov     rcx, rax; hdc
0x1800442ae  call    cs:__imp_SelectObject
0x1800442b4  mov     ecx, [rsp+170h+cy]
0x1800442b8  xor     r8d, r8d; y
0x1800442bb  mov     r9d, [rsp+170h+nWidth]; w
0x1800442c0  xor     edx, edx; x
0x1800442c2  mov     [rsp+170h+rop], 0FF0062h; rop
0x1800442ca  mov     dword ptr [rsp+170h+lpBits], ecx; h
0x1800442ce  mov     rcx, rsi; hdc
0x1800442d1  call    cs:__imp_PatBlt
0x1800442d7  xor     eax, eax
0x1800442d9  lea     rdx, [rsp+170h+var_110]
0x1800442de  mov     [rbp+70h+var_C0], rax
0x1800442e2  xorps   xmm0, xmm0
0x1800442e5  mov     eax, [rsp+170h+var_13C]
0x1800442e9  mov     rcx, rbx
0x1800442ec  movups  [rsp+170h+var_100], xmm0
0x1800442f1  mov     dword ptr [rsp+170h+var_100], eax
0x1800442f5  xor     eax, eax
0x1800442f7  movups  [rbp+70h+var_D0], xmm0
0x1800442fb  mov     qword ptr [rsp+170h+var_100+8], rsi
0x180044300  movups  [rsp+170h+var_110], xmm0
0x180044305  mov     dword ptr [rsp+170h+var_110], 58h ; 'X'
0x18004430d  movups  [rbp+70h+var_E0], xmm0
0x180044311  mov     qword ptr [rsp+170h+var_110+8], rbx
0x180044316  movups  [rbp+70h+var_F0], xmm0
0x18004431a  mov     qword ptr [rbp+70h+var_F0], rax
0x18004431e  mov     eax, [rsp+170h+var_140]
0x180044322  or      eax, 10h
0x180044325  mov     dword ptr [rbp+70h+var_E0+8], 0FF000000h
0x18004432c  mov     dword ptr [rbp+70h+var_D0], eax
0x18004432f  mov     rax, [rbx]
0x180044332  mov     dword ptr [rbp+70h+var_E0+0Ch], 0FF000000h
0x180044339  mov     dword ptr [rbp+70h+var_D0+4], 0CC0020h
0x180044340  mov     rax, [rax+40h]
0x180044344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044349  mov     rdx, r15; h
0x18004434c  mov     rcx, rsi; hdc
0x18004434f  call    cs:__imp_SelectObject
0x180044355  mov     eax, [rsp+170h+cy]
0x180044359  xor     r8d, r8d; y
0x18004435c  mov     r9d, [rsp+170h+nWidth]; w
0x180044361  xor     edx, edx; x
0x180044363  mov     rcx, rsi; hdc
0x180044366  mov     [rsp+170h+rop], 42h ; 'B'; rop
0x18004436e  mov     dword ptr [rsp+170h+lpBits], eax; h
0x180044372  call    cs:__imp_PatBlt
0x180044378  xor     eax, eax
0x18004437a  lea     rdx, [rsp+170h+var_110]
0x18004437f  mov     [rbp+70h+var_C0], rax
0x180044383  xorps   xmm0, xmm0
0x180044386  mov     eax, [rsp+170h+var_13C]
0x18004438a  mov     rcx, rbx
0x18004438d  movups  [rsp+170h+var_100], xmm0
0x180044392  mov     dword ptr [rsp+170h+var_100], eax
0x180044396  xor     eax, eax
0x180044398  movups  [rbp+70h+var_D0], xmm0
0x18004439c  mov     qword ptr [rsp+170h+var_100+8], rsi
0x1800443a1  movups  [rsp+170h+var_110], xmm0
0x1800443a6  mov     dword ptr [rsp+170h+var_110], 58h ; 'X'
0x1800443ae  movups  [rbp+70h+var_E0], xmm0
0x1800443b2  mov     qword ptr [rsp+170h+var_110+8], rbx
0x1800443b7  movups  [rbp+70h+var_F0], xmm0
0x1800443bb  mov     qword ptr [rbp+70h+var_F0], rax
0x1800443bf  mov     eax, [rsp+170h+var_140]
0x1800443c3  or      eax, 1
0x1800443c6  mov     dword ptr [rbp+70h+var_E0+8], 0FF000000h
0x1800443cd  mov     dword ptr [rbp+70h+var_D0], eax
0x1800443d0  mov     rax, [rbx]
0x1800443d3  mov     dword ptr [rbp+70h+var_E0+0Ch], 0FF000000h
0x1800443da  mov     dword ptr [rbp+70h+var_D0+4], 0CC0020h
0x1800443e1  mov     rax, [rax+40h]
0x1800443e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443ea  mov     rdx, cs:?g_hbmDcDeselect@@3PEAUHBITMAP__@@EA; h
0x1800443f1  mov     rcx, rsi; hdc
0x1800443f4  call    cs:__imp_SelectObject
0x1800443fa  test    r14d, r14d
0x1800443fd  jz      short loc_18004446B
0x1800443ff  mov     r10d, [rsp+170h+cy]
0x180044404  xor     r9d, r9d
0x180044407  imul    r10d, [rsp+170h+nWidth]
0x18004440d  mov     r11, [rbp+70h+ppvBits]
0x180044411  test    r10d, r10d
0x180044414  jle     short loc_18004446B
0x180044416  movzx   eax, byte ptr [r11+r9*4+3]
0x18004441c  test    al, al
0x18004441e  jz      short loc_180044463
0x180044420  mov     r8d, eax
0x180044423  xor     edx, edx
0x180044425  movzx   eax, byte ptr [r11+r9*4+2]
0x18004442b  imul    eax, 0FFh
0x180044431  div     r8d
0x180044434  xor     edx, edx
0x180044436  mov     [r11+r9*4+2], al
0x18004443b  movzx   eax, byte ptr [r11+r9*4+1]
0x180044441  imul    eax, 0FFh
0x180044447  div     r8d
0x18004444a  xor     edx, edx
0x18004444c  mov     [r11+r9*4+1], al
0x180044451  movzx   eax, byte ptr [r11+r9*4]
0x180044456  imul    eax, 0FFh
0x18004445c  div     r8d
0x18004445f  mov     [r11+r9*4], al
0x180044463  inc     r9d
0x180044466  cmp     r9d, r10d
0x180044469  jl      short loc_180044416
0x18004446b  lea     rcx, [rbp+70h+piconinfo]; piconinfo
0x18004446f  mov     qword ptr [rbp+70h+piconinfo.fIcon], 1
0x180044477  mov     [rbp+70h+piconinfo.yHotspot], edi
0x18004447a  mov     [rbp+70h+piconinfo.hbmColor], r15
0x18004447e  mov     [rbp+70h+piconinfo.hbmMask], r12
0x180044482  call    cs:__imp_CreateIconIndirect
0x180044488  mov     rdi, rax
0x18004448b  test    rax, rax
0x18004448e  jnz     short loc_1800444E6
0x180044490  mov     rcx, rsi; hdc
0x180044493  call    cs:__imp_DeleteDC
0x180044499  mov     rcx, r15; ho
0x18004449c  call    cs:__imp_DeleteObject
0x1800444a2  mov     rax, [rsp+170h+var_130]
0x1800444a7  mov     r15, [rsp+170h+var_38]
0x1800444af  mov     r14, [rsp+170h+var_30]
0x1800444b7  mov     [rax], rdi
0x1800444ba  mov     eax, r13d
0x1800444bd  mov     r13, [rsp+170h+var_28]
0x1800444c5  mov     rdi, [rsp+170h+var_20]
0x1800444cd  mov     rcx, [rbp+70h+var_50]
0x1800444d1  xor     rcx, rsp; StackCookie
0x1800444d4  call    __security_check_cookie
0x1800444d9  add     rsp, 158h
0x1800444e0  pop     r12
0x1800444e2  pop     rsi
0x1800444e3  pop     rbx
0x1800444e4  pop     rbp
0x1800444e5  retn
0x1800444e6  mov     rcx, r12; ho
0x1800444e9  call    cs:__imp_DeleteObject
0x1800444ef  cmp     [rsp+170h+var_140], 0
0x1800444f4  jz      loc_1800445EE
0x1800444fa  xor     r13d, r13d
0x1800444fd  jmp     short loc_180044490
0x1800444ff  mov     rcx, [rsp+170h+var_120]
0x180044504  lea     rdx, [rbp+70h+var_84]
0x180044508  mov     rax, [rcx]
0x18004450b  mov     rax, [rax+20h]
0x18004450f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044514  mov     rcx, [rsp+170h+var_120]
0x180044519  mov     rax, [rcx]
0x18004451c  mov     rax, [rax+10h]
0x180044520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044525  jmp     loc_1800441D2
0x18004452a  mov     ecx, 51h ; 'Q'; nIndex
0x18004452f  call    cs:__imp_GetSystemMetrics
0x180044535  test    eax, eax
0x180044537  jnz     loc_180044246
0x18004453d  xor     r9d, r9d
0x180044540  mov     r8d, r15d
0x180044543  mov     edx, r12d
0x180044546  mov     rcx, rsi
0x180044549  call    CreateDIB
0x18004454e  jmp     loc_180044255
0x180044553  xor     eax, eax
0x180044555  mov     [rbp+70h+pbmi.bmiHeader.biSize], 28h ; '('
0x18004455c  mov     qword ptr [rbp+70h+pbmi.bmiHeader.biClrImportant], rax
0x180044560  xorps   xmm0, xmm0
0x180044563  mov     eax, [rsp+170h+nWidth]
0x180044567  mov     r15, rsi
0x18004456a  movups  xmmword ptr [rbp+70h+pbmi.bmiHeader.biWidth], xmm0
0x18004456e  mov     [rbp+70h+pbmi.bmiHeader.biWidth], eax
0x180044571  mov     eax, [rsp+170h+cy]
0x180044575  mov     [rbp+70h+pbmi.bmiHeader.biHeight], eax
0x180044578  mov     [rbp+70h+pbmi.bmiHeader.biPlanes], cx
0x18004457c  movups  xmmword ptr [rbp+70h+pbmi.bmiHeader.biSizeImage], xmm0
0x180044580  test    r14d, r14d
0x180044583  jz      short loc_1800445E7
0x180044585  mov     eax, 20h ; ' '
0x18004458a  xor     ecx, ecx; hWnd
0x18004458c  mov     [rbp+70h+pbmi.bmiHeader.biBitCount], ax
0x180044590  mov     [rbp+70h+pbmi.bmiHeader.biCompression], esi
0x180044593  call    cs:__imp_GetDC
0x180044599  mov     rsi, rax
0x18004459c  test    rax, rax
0x18004459f  jz      short loc_1800445CE
0x1800445a1  xor     eax, eax
0x1800445a3  lea     r9, [rbp+70h+ppvBits]; ppvBits
0x1800445a7  mov     [rsp+170h+rop], eax; offset
0x1800445ab  lea     rdx, [rbp+70h+pbmi]; pbmi
0x1800445af  xor     r8d, r8d; usage
0x1800445b2  mov     [rsp+170h+lpBits], rax; hSection
0x1800445b7  mov     rcx, rsi; hdc
0x1800445ba  call    cs:__imp_CreateDIBSection
0x1800445c0  mov     rdx, rsi; hDC
0x1800445c3  xor     ecx, ecx; hWnd
0x1800445c5  mov     r15, rax
0x1800445c8  call    cs:__imp_ReleaseDC
0x1800445ce  mov     edx, r12d
0x1800445d1  bts     edx, 0Ch
0x1800445d5  bt      r12d, 10h
0x1800445da  cmovb   edx, r12d
  ... truncated ...
```
