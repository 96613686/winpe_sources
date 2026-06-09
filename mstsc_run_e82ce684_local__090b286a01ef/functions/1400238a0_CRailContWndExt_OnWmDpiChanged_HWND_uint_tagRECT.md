# CRailContWndExt::OnWmDpiChanged(HWND__ *,uint,tagRECT *)

- ea: `0x1400238a0`
- end: `0x140023b8b`
- name: `?OnWmDpiChanged@CRailContWndExt@@UEAA_JPEAUHWND__@@IPEAUtagRECT@@@Z`
- size: `747`
- prototype: `__int64 __fastcall(CRailContWndExt *__hidden this, HWND, unsigned int, struct tagRECT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14001f9ac`
- `0x140021bc8`
- `0x1400238a0`
- `0x140025148`
- `0x1400669a4`
- `0x140097c30`

## import_xrefs

- `USER32!DestroyIcon` at `0x140023ac9`
- `USER32!DestroyIcon` at `0x140023ac9`
- `USER32!LoadImageW` at `0x140023aa9`
- `USER32!LoadImageW` at `0x140023aa9`
- `USER32!SetWindowPos` at `0x140023b6b`
- `USER32!SetWindowPos` at `0x140023b6b`
- `USER32!LoadIconW` at `0x1400239ef`
- `USER32!LoadIconW` at `0x1400239ef`
- `USER32!SendMessageW` at `0x140023973`
- `USER32!SendMessageW` at `0x14002398e`
- `USER32!SendMessageW` at `0x1400239a4`
- `USER32!SendMessageW` at `0x140023b1a`
- `USER32!SendMessageW` at `0x140023973`
- `USER32!SendMessageW` at `0x14002398e`
- `USER32!SendMessageW` at `0x1400239a4`
- `USER32!SendMessageW` at `0x140023b1a`
- `KERNEL32!MulDiv` at `0x1400238d5`
- `KERNEL32!MulDiv` at `0x1400238ea`
- `KERNEL32!MulDiv` at `0x1400238ff`
- `KERNEL32!MulDiv` at `0x140023917`
- `KERNEL32!MulDiv` at `0x140023b42`
- `KERNEL32!MulDiv` at `0x1400238d5`
- `KERNEL32!MulDiv` at `0x1400238ea`
- `KERNEL32!MulDiv` at `0x1400238ff`
- `KERNEL32!MulDiv` at `0x140023917`
- `KERNEL32!MulDiv` at `0x140023b42`
- `COMCTL32!ImageList_Destroy` at `0x140023934`
- `COMCTL32!ImageList_Destroy` at `0x140023afb`
- `COMCTL32!ImageList_Destroy` at `0x140023934`
- `COMCTL32!ImageList_Destroy` at `0x140023afb`
- `COMCTL32!ImageList_ReplaceIcon` at `0x140023ac0`
- `COMCTL32!ImageList_ReplaceIcon` at `0x140023ada`
- `COMCTL32!ImageList_ReplaceIcon` at `0x140023ac0`
- `COMCTL32!ImageList_ReplaceIcon` at `0x140023ada`
- `COMCTL32!ImageList_Create` at `0x140023a1e`
- `COMCTL32!ImageList_Create` at `0x140023a1e`
- `COMCTL32!ImageList_GetImageCount` at `0x1400239ff`
- `COMCTL32!ImageList_GetImageCount` at `0x1400239ff`

## pseudocode

```c
__int64 __fastcall CRailContWndExt::OnWmDpiChanged(CRailContWndExt *this, HWND a2, int a3, struct tagRECT *a4)
{
  unsigned int v4; // r12d
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // ecx
  struct _IMAGELIST *v12; // rcx
  struct _IMAGELIST *ImageList32BitColors; // rax
  int v14; // ecx
  LPARAM v15; // r9
  int SystemMetricsForDpi; // r13d
  int v17; // esi
  HICON IconW; // r15
  int v19; // r14d
  int ImageCount; // edi
  struct _IMAGELIST *v21; // rbp
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v23; // edi
  int v24; // r12d
  const WCHAR *v25; // rdx
  HICON ImageW; // rax
  HICON v27; // rsi
  struct _IMAGELIST *v28; // rcx
  HWND v29; // rcx
  int v30; // eax

  v4 = a3;
  v6 = MulDiv(*((_DWORD *)this + 522), a3, 96);
  v7 = *((_DWORD *)this + 523);
  *((_DWORD *)this + 10) = v6;
  v8 = MulDiv(v7, v4, 96);
  v9 = *((_DWORD *)this + 525);
  *((_DWORD *)this + 11) = v8;
  v10 = MulDiv(v9, v4, 96);
  v11 = *((_DWORD *)this + 526);
  *((_DWORD *)this + 106) = v10;
  *((_DWORD *)this + 107) = MulDiv(v11, v4, 96);
  CRailContWndExt::LoadExpandoAssetDetails(this);
  v12 = (struct _IMAGELIST *)*((_QWORD *)this + 13);
  if ( v12 )
  {
    ImageList_Destroy(v12);
    *((_QWORD *)this + 13) = 0;
  }
  ImageList32BitColors = LoadImageList32BitColors(
                           *((HINSTANCE *)this + 1),
                           (const unsigned __int16 *)*((unsigned __int16 *)this + 60),
                           *((_DWORD *)this + 28));
  v14 = *((unsigned __int16 *)this + 58) << 16;
  *((_QWORD *)this + 13) = ImageList32BitColors;
  SendMessageW(*((HWND *)this + 12), 0x420u, 0, *((unsigned __int16 *)this + 56) | v14);
  v15 = *((_QWORD *)this + 13);
  if ( v15 )
  {
    SendMessageW(*((HWND *)this + 12), 0x430u, 0, v15);
    SendMessageW(*((HWND *)this + 12), 0x436u, 0, *((_QWORD *)this + 13));
  }
  CRailContWndExt::SetExpandoButtonBitmap(this);
  SystemMetricsForDpi = Win32DpiApi::GetSystemMetricsForDpi(*((Win32DpiApi **)this + 260), 11, v4);
  v17 = Win32DpiApi::GetSystemMetricsForDpi(*((Win32DpiApi **)this + 260), 12, v4);
  IconW = LoadIconW(*(HINSTANCE *)(*((_QWORD *)this + 8) + 2664LL), (LPCWSTR)0x65);
  v19 = 32;
  ImageCount = ImageList_GetImageCount(*((HIMAGELIST *)this + 18));
  v21 = ImageList_Create(SystemMetricsForDpi, v17, 0x21u, 0, 32);
  if ( ImageCount <= 32 )
  {
    v19 = ImageCount;
    v23 = 0;
    if ( v19 <= 0 )
      goto LABEL_19;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
        CurrentThreadActivityIdPrefix,
        ImageCount);
    }
    v23 = 0;
  }
  v24 = v17;
  do
  {
    v25 = (const WCHAR *)*((_QWORD *)this + v23 + 19);
    if ( v25 && (ImageW = (HICON)LoadImageW(0, v25, 1u, SystemMetricsForDpi, v24, 0x2050u), (v27 = ImageW) != 0) )
    {
      ImageList_ReplaceIcon(v21, -1, ImageW);
      DestroyIcon(v27);
    }
    else
    {
      ImageList_ReplaceIcon(v21, -1, IconW);
    }
    ++v23;
  }
  while ( v23 < v19 );
  v4 = a3;
LABEL_19:
  v28 = (struct _IMAGELIST *)*((_QWORD *)this + 18);
  if ( v28 )
    ImageList_Destroy(v28);
  v29 = (HWND)*((_QWORD *)this + 17);
  *((_QWORD *)this + 18) = v21;
  SendMessageW(v29, 0x1003u, 0, (LPARAM)v21);
  CRailContWndExt::CreateBrandingBar(this, a2, 0);
  v30 = MulDiv(*((_DWORD *)this + 524), v4, 96);
  SetWindowPos(*((HWND *)this + 16), 0, 0, 0, 1, v30, 6u);
  return 0;
}

```

## disassembly

```asm
0x1400238a0  mov     [rsp+arg_18], rbx
0x1400238a5  mov     [rsp+arg_10], r8d
0x1400238aa  mov     [rsp+arg_8], rdx
0x1400238af  push    rbp
0x1400238b0  push    rsi
0x1400238b1  push    rdi
0x1400238b2  push    r12
0x1400238b4  push    r13
0x1400238b6  push    r14
0x1400238b8  push    r15
0x1400238ba  sub     rsp, 40h
0x1400238be  mov     r12d, r8d
0x1400238c1  mov     rbx, rcx
0x1400238c4  mov     ecx, [rcx+828h]; nNumber
0x1400238ca  mov     edi, 60h ; '`'
0x1400238cf  mov     r8d, edi; nDenominator
0x1400238d2  mov     edx, r12d; nNumerator
0x1400238d5  call    cs:__imp_MulDiv
0x1400238db  mov     ecx, [rbx+82Ch]; nNumber
0x1400238e1  mov     r8d, edi; nDenominator
0x1400238e4  mov     edx, r12d; nNumerator
0x1400238e7  mov     [rbx+28h], eax
0x1400238ea  call    cs:__imp_MulDiv
0x1400238f0  mov     ecx, [rbx+834h]; nNumber
0x1400238f6  mov     r8d, edi; nDenominator
0x1400238f9  mov     edx, r12d; nNumerator
0x1400238fc  mov     [rbx+2Ch], eax
0x1400238ff  call    cs:__imp_MulDiv
0x140023905  mov     ecx, [rbx+838h]; nNumber
0x14002390b  mov     r8d, edi; nDenominator
0x14002390e  mov     edx, r12d; nNumerator
0x140023911  mov     [rbx+1A8h], eax
0x140023917  call    cs:__imp_MulDiv
0x14002391d  mov     rcx, rbx; this
0x140023920  mov     [rbx+1ACh], eax
0x140023926  call    ?LoadExpandoAssetDetails@CRailContWndExt@@AEAAXXZ; CRailContWndExt::LoadExpandoAssetDetails(void)
0x14002392b  mov     rcx, [rbx+68h]; himl
0x14002392f  test    rcx, rcx
0x140023932  jz      short loc_140023942
0x140023934  call    cs:__imp_ImageList_Destroy
0x14002393a  mov     qword ptr [rbx+68h], 0
0x140023942  movzx   edx, word ptr [rbx+78h]; unsigned __int16 *
0x140023946  mov     r8d, [rbx+70h]; int
0x14002394a  mov     rcx, [rbx+8]; HINSTANCE
0x14002394e  call    ?LoadImageList32BitColors@@YAPEAU_IMAGELIST@@PEAUHINSTANCE__@@PEBGH@Z; LoadImageList32BitColors(HINSTANCE__ *,ushort const *,int)
0x140023953  movzx   ecx, word ptr [rbx+74h]
0x140023957  xor     r8d, r8d; wParam
0x14002395a  shl     ecx, 10h
0x14002395d  mov     edx, 420h; Msg
0x140023962  mov     [rbx+68h], rax
0x140023966  movzx   eax, word ptr [rbx+70h]
0x14002396a  or      ecx, eax
0x14002396c  movsxd  r9, ecx; lParam
0x14002396f  mov     rcx, [rbx+60h]; hWnd
0x140023973  call    cs:__imp_SendMessageW
0x140023979  mov     r9, [rbx+68h]; lParam
0x14002397d  test    r9, r9
0x140023980  jz      short loc_1400239AA
0x140023982  mov     rcx, [rbx+60h]; hWnd
0x140023986  xor     r8d, r8d; wParam
0x140023989  mov     edx, 430h; Msg
0x14002398e  call    cs:__imp_SendMessageW
0x140023994  mov     r9, [rbx+68h]; lParam
0x140023998  xor     r8d, r8d; wParam
0x14002399b  mov     rcx, [rbx+60h]; hWnd
0x14002399f  mov     edx, 436h; Msg
0x1400239a4  call    cs:__imp_SendMessageW
0x1400239aa  mov     rcx, rbx; this
0x1400239ad  call    ?SetExpandoButtonBitmap@CRailContWndExt@@AEAAXXZ; CRailContWndExt::SetExpandoButtonBitmap(void)
0x1400239b2  mov     rcx, [rbx+820h]; this
0x1400239b9  mov     r8d, r12d; unsigned int
0x1400239bc  mov     edx, 0Bh; int
0x1400239c1  call    ?GetSystemMetricsForDpi@Win32DpiApi@@QEAAHHI@Z; Win32DpiApi::GetSystemMetricsForDpi(int,uint)
0x1400239c6  mov     rcx, [rbx+820h]; this
0x1400239cd  mov     r8d, r12d; unsigned int
0x1400239d0  mov     edx, 0Ch; int
0x1400239d5  mov     r13d, eax
0x1400239d8  call    ?GetSystemMetricsForDpi@Win32DpiApi@@QEAAHHI@Z; Win32DpiApi::GetSystemMetricsForDpi(int,uint)
0x1400239dd  mov     rcx, [rbx+40h]
0x1400239e1  mov     edx, 65h ; 'e'; lpIconName
0x1400239e6  mov     esi, eax
0x1400239e8  mov     rcx, [rcx+0A68h]; hInstance
0x1400239ef  call    cs:__imp_LoadIconW
0x1400239f5  mov     rcx, [rbx+90h]; himl
0x1400239fc  mov     r15, rax
0x1400239ff  call    cs:__imp_ImageList_GetImageCount
0x140023a05  mov     r14d, 20h ; ' '
0x140023a0b  xor     r9d, r9d; cInitial
0x140023a0e  mov     edx, esi; cy
0x140023a10  mov     [rsp+78h+cGrow], r14d; cGrow
0x140023a15  mov     ecx, r13d; cx
0x140023a18  mov     edi, eax
0x140023a1a  lea     r8d, [r14+1]; flags
0x140023a1e  call    cs:__imp_ImageList_Create
0x140023a24  mov     rbp, rax
0x140023a27  cmp     edi, r14d
0x140023a2a  jle     short loc_140023A76
0x140023a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140023a33  lea     rax, WPP_GLOBAL_Control
0x140023a3a  cmp     rcx, rax
0x140023a3d  jz      short loc_140023A72
0x140023a3f  test    byte ptr [rcx+1Ch], 1
0x140023a43  jz      short loc_140023A72
0x140023a45  cmp     byte ptr [rcx+19h], 3
0x140023a49  jb      short loc_140023A72
0x140023a4b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140023a50  mov     rcx, cs:WPP_GLOBAL_Control
0x140023a57  lea     edx, [r14+25h]
0x140023a5b  mov     r9d, eax
0x140023a5e  mov     [rsp+78h+cGrow], edi
0x140023a62  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x140023a69  mov     rcx, [rcx+10h]
0x140023a6d  call    WPP_SF_Dd
0x140023a72  xor     edi, edi
0x140023a74  jmp     short loc_140023A80
0x140023a76  mov     r14d, edi
0x140023a79  xor     edi, edi
0x140023a7b  test    r14d, r14d
0x140023a7e  jle     short loc_140023AEF
0x140023a80  mov     r12d, esi
0x140023a83  movsxd  rax, edi
0x140023a86  mov     rdx, [rbx+rax*8+98h]; name
0x140023a8e  test    rdx, rdx
0x140023a91  jz      short loc_140023AD1
0x140023a93  xor     ecx, ecx; hInst
0x140023a95  mov     [rsp+78h+fuLoad], 2050h; fuLoad
0x140023a9d  mov     r9d, r13d; cx
0x140023aa0  mov     [rsp+78h+cGrow], r12d; cy
0x140023aa5  lea     r8d, [rcx+1]; type
0x140023aa9  call    cs:__imp_LoadImageW
0x140023aaf  mov     rsi, rax
0x140023ab2  test    rax, rax
0x140023ab5  jz      short loc_140023AD1
0x140023ab7  mov     r8, rax; hicon
0x140023aba  or      edx, 0FFFFFFFFh; i
0x140023abd  mov     rcx, rbp; himl
0x140023ac0  call    cs:__imp_ImageList_ReplaceIcon
0x140023ac6  mov     rcx, rsi; hIcon
0x140023ac9  call    cs:__imp_DestroyIcon
0x140023acf  jmp     short loc_140023AE0
0x140023ad1  mov     r8, r15; hicon
0x140023ad4  or      edx, 0FFFFFFFFh; i
0x140023ad7  mov     rcx, rbp; himl
0x140023ada  call    cs:__imp_ImageList_ReplaceIcon
0x140023ae0  inc     edi
0x140023ae2  cmp     edi, r14d
0x140023ae5  jl      short loc_140023A83
0x140023ae7  mov     r12d, [rsp+78h+arg_10]
0x140023aef  mov     rcx, [rbx+90h]; himl
0x140023af6  test    rcx, rcx
0x140023af9  jz      short loc_140023B01
0x140023afb  call    cs:__imp_ImageList_Destroy
0x140023b01  mov     rcx, [rbx+88h]; hWnd
0x140023b08  mov     r9, rbp; lParam
0x140023b0b  xor     r8d, r8d; wParam
0x140023b0e  mov     [rbx+90h], rbp
0x140023b15  mov     edx, 1003h; Msg
0x140023b1a  call    cs:__imp_SendMessageW
0x140023b20  mov     rdx, [rsp+78h+arg_8]; HWND
0x140023b28  xor     r8d, r8d; unsigned int *
0x140023b2b  mov     rcx, rbx; this
0x140023b2e  call    ?CreateBrandingBar@CRailContWndExt@@AEAAJPEAUHWND__@@PEAI@Z; CRailContWndExt::CreateBrandingBar(HWND__ *,uint *)
0x140023b33  mov     ecx, [rbx+830h]; nNumber
0x140023b39  mov     r8d, 60h ; '`'; nDenominator
0x140023b3f  mov     edx, r12d; nNumerator
0x140023b42  call    cs:__imp_MulDiv
0x140023b48  mov     rcx, [rbx+80h]; hWnd
0x140023b4f  xor     r9d, r9d; Y
0x140023b52  mov     [rsp+78h+uFlags], 6; uFlags
0x140023b5a  xor     r8d, r8d; X
0x140023b5d  mov     [rsp+78h+fuLoad], eax; cy
0x140023b61  xor     edx, edx; hWndInsertAfter
0x140023b63  mov     [rsp+78h+cGrow], 1; cx
0x140023b6b  call    cs:__imp_SetWindowPos
0x140023b71  mov     rbx, [rsp+78h+arg_18]
0x140023b79  xor     eax, eax
0x140023b7b  add     rsp, 40h
0x140023b7f  pop     r15
0x140023b81  pop     r14
0x140023b83  pop     r13
0x140023b85  pop     r12
0x140023b87  pop     rdi
0x140023b88  pop     rsi
0x140023b89  pop     rbp
0x140023b8a  retn
```
