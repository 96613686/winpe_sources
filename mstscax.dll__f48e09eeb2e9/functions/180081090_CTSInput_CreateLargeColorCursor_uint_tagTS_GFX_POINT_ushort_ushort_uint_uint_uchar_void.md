# CTSInput::CreateLargeColorCursor(uint,tagTS_GFX_POINT,ushort,ushort,uint,uint,uchar *,void * *)

- ea: `0x180081090`
- end: `0x18008177a`
- name: `?CreateLargeColorCursor@CTSInput@@UEAAJIUtagTS_GFX_POINT@@GGIIPEAEPEAPEAX@Z`
- size: `1770`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180080f60`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x180081090`
- `0x180081780`
- `0x180081b74`
- `0x1800e9b1c`
- `0x1800f7748`
- `0x1801031a4`
- `0x18013db44`
- `0x180154c44`
- `0x180154ce8`
- `0x180688f26`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008127e`
- `KERNEL32!GetLastError` at `0x18008127e`
- `KERNEL32!LocalAlloc` at `0x1800814b9`
- `KERNEL32!LocalAlloc` at `0x180081542`
- `KERNEL32!LocalAlloc` at `0x1800814b9`
- `KERNEL32!LocalAlloc` at `0x180081542`
- `KERNEL32!LocalFree` at `0x180081408`
- `KERNEL32!LocalFree` at `0x180081408`
- `GDI32!DeleteObject` at `0x1800813db`
- `GDI32!DeleteObject` at `0x1800813ed`
- `GDI32!DeleteObject` at `0x1800813db`
- `GDI32!DeleteObject` at `0x1800813ed`
- `GDI32!DeleteDC` at `0x18008146d`
- `GDI32!DeleteDC` at `0x18008146d`
- `GDI32!CreateDIBitmap` at `0x18008165f`
- `GDI32!CreateDIBitmap` at `0x18008165f`
- `GDI32!CreateCompatibleDC` at `0x180081264`
- `GDI32!CreateCompatibleDC` at `0x180081264`
- `USER32!LoadCursorW` at `0x180081423`
- `USER32!LoadCursorW` at `0x180081423`

## pseudocode

```c
__int64 __fastcall CTSInput::CreateLargeColorCursor(
        CTSInput *a1,
        int a2,
        __int64 a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        DWORD a6,
        DWORD a7,
        unsigned __int8 *a8,
        __int64 *a9)
{
  unsigned __int8 *v10; // r8
  DWORD v12; // ecx
  unsigned int v13; // edi
  HDC v14; // r13
  HKEY v15; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v17; // rdx
  unsigned int v18; // r14d
  unsigned int v19; // eax
  unsigned int v20; // edi
  HCURSOR *v21; // r12
  unsigned __int8 *v22; // rsi
  signed int LastError; // ebx
  unsigned int v24; // eax
  unsigned int v25; // ecx
  unsigned __int8 *v26; // r13
  unsigned int v27; // r14d
  unsigned int v28; // r14d
  unsigned int v29; // eax
  HBITMAP v30; // r14
  unsigned int v31; // eax
  unsigned int v33; // r15d
  size_t v34; // rbx
  __int64 v35; // r14
  unsigned __int8 *v36; // rdi
  unsigned __int8 *v37; // rax
  unsigned int v38; // eax
  DWORD biSizeImage; // r14d
  unsigned int v40; // eax
  HBITMAP v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // r8
  unsigned int v45; // eax
  __int64 PlatformCursor; // rbx
  unsigned int v47; // eax
  __int64 v48; // rdx
  __int64 v49; // r8
  unsigned int v50; // eax
  UINT iUsage[2]; // [rsp+28h] [rbp-D8h]
  HBITMAP ho; // [rsp+68h] [rbp-98h]
  HDC hdc; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+80h] [rbp-80h]
  unsigned int v55; // [rsp+84h] [rbp-7Ch]
  HBITMAP v56; // [rsp+88h] [rbp-78h]
  DWORD v57; // [rsp+9Ch] [rbp-64h]
  __int64 v58; // [rsp+B0h] [rbp-50h]
  BITMAPINFOHEADER pbmih; // [rsp+C0h] [rbp-40h] BYREF
  char v60; // [rsp+E8h] [rbp-18h]
  int v61; // [rsp+E9h] [rbp-17h]
  __int16 v62; // [rsp+EDh] [rbp-13h]
  char v63; // [rsp+EFh] [rbp-11h]

  v10 = a8;
  v12 = a7;
  v13 = a4;
  *a9 = 0;
  v14 = 0;
  v58 = a3;
  v54 = a2;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DdDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      a7,
      CurrentThreadActivityIdPrefix,
      v54,
      a3,
      HIDWORD(a3),
      v13,
      a5,
      a7,
      a6);
    v15 = WPP_GLOBAL_Control;
    LOWORD(a2) = v54;
    v12 = a7;
    v10 = a8;
  }
  if ( (unsigned __int16)v13 > 0x180u || a5 > 0x180u )
  {
    if ( v15 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v15[7] & 1) != 0 && *((_BYTE *)v15 + 25) >= 2u )
    {
      v50 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DLD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids,
        v50,
        v13,
        a5);
    }
    v20 = -2147024809;
    goto LABEL_13;
  }
  pbmih.biBitCount = a2;
  v18 = v13;
  pbmih.biCompression = 0;
  pbmih.biSizeImage = v12;
  pbmih.biSize = 40;
  v55 = v13;
  pbmih.biWidth = v13;
  pbmih.biHeight = a5;
  pbmih.biPlanes = 1;
  *(_QWORD *)&pbmih.biXPelsPerMeter = 0;
  *(_QWORD *)&pbmih.biClrUsed = 0;
  ho = CTSInput::CreateXORBitmap(a1, (BITMAPINFO *)&pbmih, v13, a5, v10);
  if ( !ho )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      iUsage[0] = -2147467259;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids,
        v19,
        (__int64)"hbmXORBitmap",
        *(_QWORD *)iUsage);
    }
    v20 = -2147467259;
LABEL_13:
    v21 = (HCURSOR *)a9;
    goto LABEL_39;
  }
  v56 = 0;
  v22 = 0;
  hdc = CreateCompatibleDC(0);
  v14 = hdc;
  if ( !hdc )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids,
        v24,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    v20 = LastError;
    goto LABEL_33;
  }
  v20 = -2147467259;
  v25 = ((v18 + 31) >> 3) & 0x1FFFFFFC;
  pbmih.biClrUsed = 2;
  pbmih.biBitCount = 1;
  pbmih.biSizeImage = a6;
  v61 = -16777216;
  v60 = 0;
  v57 = a5 * v25;
  v62 = -1;
  v63 = 0;
  if ( a6 )
  {
    v26 = &a8[a7];
    v27 = (v18 + 15) >> 3;
    if ( (v27 & 0xFFFFFFFE) == v25 )
    {
      v22 = &a8[a7];
    }
    else
    {
      v28 = v27 & 0x1FFFFFFE;
      if ( v28 * a5 > a6 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v29 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DDDd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            &WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids,
            v29,
            v28,
            a5,
            a6);
        }
        goto LABEL_32;
      }
      v22 = (unsigned __int8 *)LocalAlloc(0x40u, a5 * ((v28 + 3) & 0xFFFFFFFC));
      if ( v22 )
      {
        pbmih.biSizeImage = a5 * ((v28 + 3) & 0xFFFFFFFC);
        if ( a5 )
        {
          v33 = 0;
          v34 = v28;
          v35 = (v28 + 3) & 0xFFFFFFFC;
          v36 = v22;
          do
          {
            memcpy_0(v36, v26, v34);
            v26 += v34;
            ++v33;
            v36 += v35;
          }
          while ( v33 < a5 );
          a3 = v58;
          v20 = -2147467259;
        }
      }
      else
      {
        v22 = &a8[a7];
      }
    }
  }
  else
  {
    pbmih.biSizeImage = a5 * (((v18 + 31) >> 3) & 0x1FFFFFFC);
    v37 = (unsigned __int8 *)LocalAlloc(0x40u, pbmih.biSizeImage);
    v22 = v37;
    if ( !v37 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v38 = RdpWppGetCurrentThreadActivityIdPrefix();
        iUsage[0] = -2147024882;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)&WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids,
          v38,
          (__int64)"maskData",
          *(_QWORD *)iUsage);
      }
      v20 = -2147024882;
      goto LABEL_33;
    }
    memset_0(v37, 0, pbmih.biSizeImage);
  }
  biSizeImage = pbmih.biSizeImage;
  if ( pbmih.biSizeImage < v57 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v40 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DDDDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids,
        v40,
        v55,
        a5,
        v54,
        biSizeImage,
        v57);
    }
LABEL_32:
    v14 = hdc;
    goto LABEL_33;
  }
  v14 = hdc;
  v41 = CreateDIBitmap(hdc, &pbmih, 4u, v22, (const BITMAPINFO *)&pbmih, 0);
  v56 = v41;
  if ( v41 )
  {
    v30 = ho;
    PlatformCursor = CTSInput::CreatePlatformCursor(v43, v42, v44, a3, ho, v41);
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v47 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DqDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v48, v49, v47, PlatformCursor, v55, a5);
    }
    v21 = (HCURSOR *)a9;
    v20 = 0;
    *a9 = PlatformCursor;
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v45 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids, v45);
  }
LABEL_33:
  v21 = (HCURSOR *)a9;
  v30 = ho;
LABEL_34:
  DeleteObject(v30);
  if ( v56 )
    DeleteObject(v56);
  if ( v22 && v22 != &a8[a7] )
    LocalFree(v22);
LABEL_39:
  if ( !*v21 )
  {
    *v21 = LoadCursorW(0, (LPCWSTR)0x7F00);
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids, v31);
    }
  }
  if ( v14 )
    DeleteDC(v14);
  return v20;
}

```

## disassembly

```asm
0x180081090  mov     [rsp-8+arg_8], rbx
0x180081095  push    rbp
0x180081096  push    rsi
0x180081097  push    rdi
0x180081098  push    r12
0x18008109a  push    r13
0x18008109c  push    r14
0x18008109e  push    r15
0x1800810a0  lea     rbp, [rsp-400h]
0x1800810a8  sub     rsp, 500h
0x1800810af  mov     rax, cs:__security_cookie
0x1800810b6  xor     rax, rsp
0x1800810b9  mov     [rbp+430h+var_40], rax
0x1800810c0  mov     rax, [rbp+430h+arg_40]
0x1800810c7  mov     rbx, r8
0x1800810ca  mov     r8, [rbp+430h+arg_38]
0x1800810d1  mov     r15, rcx
0x1800810d4  mov     ecx, [rbp+430h+arg_30]
0x1800810da  movzx   esi, [rbp+430h+arg_20]
0x1800810e1  movzx   edi, r9w
0x1800810e5  xor     r9d, r9d
0x1800810e8  mov     [rax], r9
0x1800810eb  mov     r13d, r9d
0x1800810ee  mov     [rbp+430h+var_480], rbx
0x1800810f2  mov     [rbp+430h+var_4B0], edx
0x1800810f5  mov     [rbp+430h+var_4A8], rbx
0x1800810f9  mov     [rsp+530h+var_4C0], ecx
0x1800810fd  mov     [rbp+430h+var_490], r8
0x180081101  mov     [rsp+530h+var_4D0], rax
0x180081106  mov     rax, cs:WPP_GLOBAL_Control
0x18008110d  lea     r14, WPP_GLOBAL_Control
0x180081114  lea     r11d, [r9+1]
0x180081118  cmp     rax, r14
0x18008111b  jz      short loc_18008118A
0x18008111d  test    [rax+1Ch], r11b
0x180081121  jz      short loc_18008118A
0x180081123  cmp     byte ptr [rax+19h], 4
0x180081127  jb      short loc_18008118A
0x180081129  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008112e  mov     r8d, [rbp+430h+arg_28]
0x180081135  mov     r9d, eax
0x180081138  mov     ecx, dword ptr [rbp+430h+var_4A8+4]
0x18008113b  mov     [rsp+530h+var_4E0], r8d
0x180081140  mov     r8d, [rsp+530h+var_4C0]
0x180081145  mov     [rsp+530h+var_4E8], r8d
0x18008114a  mov     [rsp+530h+var_4F0], esi
0x18008114e  mov     [rsp+530h+var_4F8], edi
0x180081152  mov     [rsp+530h+var_500], ecx
0x180081156  mov     ecx, [rbp+430h+var_4B0]
0x180081159  mov     [rsp+530h+iUsage], ebx
0x18008115d  mov     dword ptr [rsp+530h+pbmi], ecx
0x180081161  mov     rcx, cs:WPP_GLOBAL_Control
0x180081168  mov     rcx, [rcx+10h]
0x18008116c  call    WPP_SF_DdDDDDDD
0x180081171  mov     rax, cs:WPP_GLOBAL_Control
0x180081178  lea     r11d, [r13+1]
0x18008117c  mov     edx, [rbp+430h+var_4B0]
0x18008117f  xor     r9d, r9d
0x180081182  mov     ecx, [rsp+530h+var_4C0]
0x180081186  mov     r8, [rbp+430h+var_490]
0x18008118a  mov     r10d, 180h
0x180081190  cmp     di, r10w
0x180081194  ja      loc_180081730
0x18008119a  cmp     si, r10w
0x18008119e  ja      loc_180081730
0x1800811a4  mov     [rbp+430h+pbmih.biBitCount], dx
0x1800811a8  mov     r14d, edi
0x1800811ab  mov     [rbp+430h+pbmih.biCompression], r9d
0x1800811af  lea     rdx, [rbp+430h+pbmih]; pbmi
0x1800811b3  mov     [rbp+430h+pbmih.biSizeImage], ecx
0x1800811b6  mov     r9d, esi; unsigned int
0x1800811b9  mov     [rsp+530h+pbmi], r8; unsigned __int8 *
0x1800811be  mov     rcx, r15; this
0x1800811c1  mov     r8d, edi; unsigned int
0x1800811c4  mov     [rbp+430h+pbmih.biSize], 28h ; '('
0x1800811cb  mov     [rbp+430h+var_4AC], edi
0x1800811ce  mov     r12d, esi
0x1800811d1  mov     [rbp+430h+pbmih.biWidth], edi
0x1800811d4  mov     [rbp+430h+pbmih.biHeight], esi
0x1800811d7  mov     [rbp+430h+pbmih.biPlanes], r11w
0x1800811dc  mov     qword ptr [rbp+430h+pbmih.biXPelsPerMeter], r13
0x1800811e0  mov     qword ptr [rbp+430h+pbmih.biClrUsed], r13
0x1800811e4  call    ?CreateXORBitmap@CTSInput@@AEAAPEAUHBITMAP__@@PEAUtagBITMAPINFO@@IIPEAE@Z; CTSInput::CreateXORBitmap(tagBITMAPINFO *,uint,uint,uchar *)
0x1800811e9  mov     [rsp+530h+ho], rax
0x1800811ee  test    rax, rax
0x1800811f1  jnz     short loc_18008125C
0x1800811f3  mov     rax, cs:WPP_GLOBAL_Control
0x1800811fa  lea     r14, WPP_GLOBAL_Control
0x180081201  lea     r15, WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids
0x180081208  cmp     rax, r14
0x18008120b  jz      short loc_18008124D
0x18008120d  test    byte ptr [rax+1Ch], 8
0x180081211  jz      short loc_18008124D
0x180081213  cmp     byte ptr [rax+19h], 2
0x180081217  jb      short loc_18008124D
0x180081219  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008121e  lea     rcx, aHbmxorbitmap; "hbmXORBitmap"
0x180081225  mov     [rsp+530h+iUsage], 80004005h
0x18008122d  mov     [rsp+530h+pbmi], rcx
0x180081232  mov     edx, 0Eh
0x180081237  mov     rcx, cs:WPP_GLOBAL_Control
0x18008123e  mov     r9d, eax
0x180081241  mov     r8, r15
0x180081244  mov     rcx, [rcx+10h]
0x180081248  call    WPP_SF_DsD
0x18008124d  mov     edi, 80004005h
0x180081252  mov     r12, [rsp+530h+var_4D0]
0x180081257  jmp     loc_180081415
0x18008125c  xor     ecx, ecx; hdc
0x18008125e  mov     [rbp+430h+var_4A8], r13
0x180081262  xor     esi, esi
0x180081264  call    cs:__imp_CreateCompatibleDC
0x18008126a  mov     [rsp+530h+hdc], rax
0x18008126f  mov     r13, rax
0x180081272  lea     r15, WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids
0x180081279  test    rax, rax
0x18008127c  jnz     short loc_1800812E5
0x18008127e  call    cs:__imp_GetLastError
0x180081284  mov     ebx, eax
0x180081286  mov     rax, cs:WPP_GLOBAL_Control
0x18008128d  lea     rdx, WPP_GLOBAL_Control
0x180081294  cmp     rax, rdx
0x180081297  jz      short loc_1800812C7
0x180081299  test    byte ptr [rax+1Ch], 8
0x18008129d  jz      short loc_1800812C7
0x18008129f  cmp     byte ptr [rax+19h], 2
0x1800812a3  jb      short loc_1800812C7
0x1800812a5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800812aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800812b1  lea     edx, [rsi+0Fh]
0x1800812b4  mov     r9d, eax
0x1800812b7  mov     dword ptr [rsp+530h+pbmi], ebx
0x1800812bb  mov     r8, r15
0x1800812be  mov     rcx, [rcx+10h]
0x1800812c2  call    WPP_SF_Dd
0x1800812c7  test    ebx, ebx
0x1800812c9  jle     short loc_1800812D4
0x1800812cb  movzx   ebx, bx
0x1800812ce  or      ebx, 80070000h
0x1800812d4  mov     edi, 80004005h
0x1800812d9  test    ebx, ebx
0x1800812db  cmovns  ebx, edi
0x1800812de  mov     edi, ebx
0x1800812e0  jmp     loc_1800813CE
0x1800812e5  mov     edx, [rbp+430h+arg_28]
0x1800812eb  lea     ecx, [r14+1Fh]
0x1800812ef  shr     ecx, 3
0x1800812f2  mov     edi, 80004005h
0x1800812f7  and     ecx, 1FFFFFFCh
0x1800812fd  mov     [rbp+430h+var_498], edi
0x180081300  mov     eax, ecx
0x180081302  mov     [rbp+430h+pbmih.biClrUsed], 2
0x180081309  imul    eax, r12d
0x18008130d  mov     r9d, 1
0x180081313  mov     [rbp+430h+pbmih.biBitCount], r9w
0x180081318  mov     [rbp+430h+pbmih.biSizeImage], edx
0x18008131b  mov     [rbp+430h+var_447], 0FF000000h
0x180081322  mov     [rbp+430h+var_448], sil
0x180081326  mov     [rbp+430h+var_494], eax
0x180081329  mov     [rbp+430h+var_443], 0FFFFh
0x18008132f  mov     [rbp+430h+var_441], sil
0x180081333  test    edx, edx
0x180081335  jz      loc_180081538
0x18008133b  mov     r13d, [rsp+530h+var_4C0]
0x180081340  add     r14d, 0Fh
0x180081344  add     r13, [rbp+430h+var_490]
0x180081348  shr     r14d, 3
0x18008134c  mov     eax, r14d
0x18008134f  and     eax, 0FFFFFFFEh
0x180081352  cmp     eax, ecx
0x180081354  jnz     short loc_18008135E
0x180081356  mov     rsi, r13
0x180081359  jmp     loc_1800815BF
0x18008135e  and     r14d, 1FFFFFFEh
0x180081365  mov     eax, r12d
0x180081368  imul    eax, r14d
0x18008136c  cmp     eax, edx
0x18008136e  jbe     loc_18008149F
0x180081374  mov     rax, cs:WPP_GLOBAL_Control
0x18008137b  lea     rdx, WPP_GLOBAL_Control
0x180081382  cmp     rax, rdx
0x180081385  jz      short loc_1800813C9
0x180081387  test    [rax+1Ch], r9b
0x18008138b  jz      short loc_1800813C9
0x18008138d  cmp     byte ptr [rax+19h], 2
0x180081391  jb      short loc_1800813C9
0x180081393  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180081398  mov     rcx, cs:WPP_GLOBAL_Control
0x18008139f  mov     edx, 10h
0x1800813a4  mov     r8d, [rbp+430h+arg_28]
0x1800813ab  mov     r9d, eax
0x1800813ae  mov     [rsp+530h+var_500], r8d
0x1800813b3  mov     r8, r15
0x1800813b6  mov     [rsp+530h+iUsage], r12d
0x1800813bb  mov     rcx, [rcx+10h]
0x1800813bf  mov     dword ptr [rsp+530h+pbmi], r14d
0x1800813c4  call    WPP_SF_DDDd
0x1800813c9  mov     r13, [rsp+530h+hdc]
0x1800813ce  mov     r12, [rsp+530h+var_4D0]
0x1800813d3  mov     r14, [rsp+530h+ho]
0x1800813d8  mov     rcx, r14; ho
0x1800813db  call    cs:__imp_DeleteObject
0x1800813e1  mov     rax, [rbp+430h+var_4A8]
0x1800813e5  test    rax, rax
0x1800813e8  jz      short loc_1800813F3
0x1800813ea  mov     rcx, rax; ho
0x1800813ed  call    cs:__imp_DeleteObject
0x1800813f3  test    rsi, rsi
0x1800813f6  jz      short loc_18008140E
0x1800813f8  mov     eax, [rsp+530h+var_4C0]
0x1800813fc  add     rax, [rbp+430h+var_490]
0x180081400  cmp     rsi, rax
0x180081403  jz      short loc_18008140E
0x180081405  mov     rcx, rsi; hMem
0x180081408  call    cs:__imp_LocalFree
0x18008140e  lea     r14, WPP_GLOBAL_Control
0x180081415  cmp     qword ptr [r12], 0
0x18008141a  jnz     short loc_180081465
0x18008141c  mov     edx, 7F00h; lpCursorName
0x180081421  xor     ecx, ecx; hInstance
0x180081423  call    cs:__imp_LoadCursorW
0x180081429  mov     [r12], rax
0x18008142d  mov     rax, cs:WPP_GLOBAL_Control
0x180081434  cmp     rax, r14
0x180081437  jz      short loc_180081465
0x180081439  test    byte ptr [rax+1Ch], 1
0x18008143d  jz      short loc_180081465
0x18008143f  cmp     byte ptr [rax+19h], 2
0x180081443  jb      short loc_180081465
0x180081445  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008144a  mov     rcx, cs:WPP_GLOBAL_Control
0x180081451  mov     edx, 15h
0x180081456  mov     r9d, eax
0x180081459  mov     r8, r15
0x18008145c  mov     rcx, [rcx+10h]
0x180081460  call    WPP_SF_d
0x180081465  test    r13, r13
0x180081468  jz      short loc_180081473
0x18008146a  mov     rcx, r13; hdc
0x18008146d  call    cs:__imp_DeleteDC
0x180081473  mov     eax, edi
0x180081475  mov     rcx, [rbp+430h+var_40]
0x18008147c  xor     rcx, rsp; StackCookie
0x18008147f  call    __security_check_cookie
0x180081484  mov     rbx, [rsp+530h+arg_8]
0x18008148c  add     rsp, 500h
0x180081493  pop     r15
0x180081495  pop     r14
0x180081497  pop     r13
0x180081499  pop     r12
0x18008149b  pop     rdi
0x18008149c  pop     rsi
0x18008149d  pop     rbp
0x18008149e  retn
0x18008149f  lea     eax, [r14+3]
0x1800814a3  mov     ecx, 0FFFFFFFCh
0x1800814a8  and     eax, ecx
0x1800814aa  mov     ecx, 40h ; '@'; uFlags
0x1800814af  imul    eax, r12d
0x1800814b3  mov     edx, eax; uBytes
0x1800814b5  mov     [rbp+430h+var_4A0], rax
0x1800814b9  call    cs:__imp_LocalAlloc
0x1800814bf  mov     rsi, rax
0x1800814c2  test    rax, rax
0x1800814c5  jz      short loc_180081530
0x1800814c7  mov     rdx, [rbp+430h+var_4A0]
0x1800814cb  lea     ecx, [r14+3]
0x1800814cf  mov     [rbp+430h+pbmih.biSizeImage], edx
0x1800814d2  mov     dword ptr [rbp+430h+var_4A0], 0
0x1800814d9  test    r12d, r12d
0x1800814dc  jz      loc_1800815B9
0x1800814e2  mov     r15d, dword ptr [rbp+430h+var_4A0]
0x1800814e6  mov     eax, 0FFFFFFFCh
0x1800814eb  and     rcx, rax
0x1800814ee  mov     ebx, r14d
0x1800814f1  mov     [rbp+430h+var_488], rcx
0x1800814f5  mov     r14, rcx
0x1800814f8  mov     rdi, rsi
0x1800814fb  mov     r8, rbx; Size
0x1800814fe  mov     rdx, r13; Src
0x180081501  mov     rcx, rdi; void *
0x180081504  call    memcpy_0
0x180081509  mov     r9d, 1
0x18008150f  add     r13, rbx
0x180081512  add     r15d, r9d
0x180081515  add     rdi, r14
0x180081518  cmp     r15d, r12d
0x18008151b  jb      short loc_1800814FB
0x18008151d  mov     rbx, [rbp+430h+var_480]
0x180081521  lea     r15, WPP_22d072ea4da537dbe476a9155f2b3394_Traceguids
0x180081528  mov     edi, [rbp+430h+var_498]
0x18008152b  jmp     loc_1800815BF
0x180081530  mov     rsi, r13
0x180081533  jmp     loc_1800815B9
0x180081538  mov     edx, eax; uBytes
0x18008153a  mov     ecx, 40h ; '@'; uFlags
0x18008153f  mov     [rbp+430h+pbmih.biSizeImage], eax
0x180081542  call    cs:__imp_LocalAlloc
0x180081548  mov     rsi, rax
0x18008154b  test    rax, rax
  ... truncated ...
```
