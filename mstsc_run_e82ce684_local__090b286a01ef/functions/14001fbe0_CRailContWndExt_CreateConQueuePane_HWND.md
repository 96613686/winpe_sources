# CRailContWndExt::CreateConQueuePane(HWND__ *)

- ea: `0x14001fbe0`
- end: `0x140020071`
- name: `?CreateConQueuePane@CRailContWndExt@@AEAAJPEAUHWND__@@@Z`
- size: `1169`
- prototype: `__int64 __fastcall(CRailContWndExt *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140022930`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14001e7ec`
- `0x14001fbe0`
- `0x1400205e8`
- `0x14002147c`
- `0x140021b04`
- `0x1400669a4`
- `0x1400fbf0c`
- `0x140113390`

## import_xrefs

- `USER32!EnableWindow` at `0x14001ffc7`
- `USER32!EnableWindow` at `0x14001ffc7`
- `USER32!GetWindowRect` at `0x14001fe04`
- `USER32!GetWindowRect` at `0x14001fe04`
- `USER32!SetWindowLongPtrW` at `0x14001fd20`
- `USER32!SetWindowLongPtrW` at `0x14001fd20`
- `USER32!GetDlgItem` at `0x14001fe2a`
- `USER32!GetDlgItem` at `0x14001fe2a`
- `USER32!SendMessageW` at `0x14001ff12`
- `USER32!SendMessageW` at `0x14001ff2a`
- `USER32!SendMessageW` at `0x14001ff42`
- `USER32!SendMessageW` at `0x14001ffaf`
- `USER32!SendMessageW` at `0x140020046`
- `USER32!SendMessageW` at `0x14001ff12`
- `USER32!SendMessageW` at `0x14001ff2a`
- `USER32!SendMessageW` at `0x14001ff42`
- `USER32!SendMessageW` at `0x14001ffaf`
- `USER32!SendMessageW` at `0x140020046`
- `KERNEL32!GetLastError` at `0x14001fcaa`
- `KERNEL32!GetLastError` at `0x14001fecb`
- `KERNEL32!GetLastError` at `0x14001fcaa`
- `KERNEL32!GetLastError` at `0x14001fecb`
- `COMCTL32!ImageList_Create` at `0x14001ffe2`
- `COMCTL32!ImageList_Create` at `0x14001ffe2`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14001fea9`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14001fea9`

## string_xrefs

- `0x14001fdef`: `CreateFonts failed!`

## pseudocode

```c
__int64 __fastcall CRailContWndExt::CreateConQueuePane(CRailContWndExt *this, HWND a2)
{
  bool v2; // zf
  unsigned int Dpi; // ebx
  int SystemMetrics; // r14d
  int SystemMetricsForDpi; // eax
  int v8; // ebp
  HWND v9; // rax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  HWND v15; // rcx
  HWND DlgItem; // rax
  unsigned int v17; // eax
  DWORD v18; // ebx
  unsigned int v19; // eax
  double v20; // xmm0_8
  HIMAGELIST v21; // rax
  unsigned int v22; // eax
  signed int v24; // [rsp+28h] [rbp-50h]
  struct tagRECT Rect; // [rsp+30h] [rbp-48h] BYREF

  v2 = *((_QWORD *)this + 260) == 0;
  Rect = 0;
  if ( v2 )
  {
    SystemMetrics = xGetSystemMetrics(11);
    SystemMetricsForDpi = xGetSystemMetrics(12);
  }
  else
  {
    Dpi = CRailContWndExt::GetDpi(this);
    SystemMetrics = Win32DpiApi::GetSystemMetricsForDpi(*((Win32DpiApi **)this + 260), 11, Dpi);
    SystemMetricsForDpi = Win32DpiApi::GetSystemMetricsForDpi(*((Win32DpiApi **)this + 260), 12, Dpi);
  }
  v8 = SystemMetricsForDpi;
  v9 = TSCreateDialogParamW(
         *((HINSTANCE *)this + 1),
         (const unsigned __int16 *)((*((_DWORD *)this + 517) & 0x100) != 0 ? 14029LL : 14023LL),
         a2,
         (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))CRailContWndExt::STATIC_ConQueuePaneWndProc,
         0);
  *((_QWORD *)this + 16) = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_054707ce312e306d358833de4c0f150b_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      return (unsigned int)-2147467259;
    return (unsigned int)LastError;
  }
  SetWindowLongPtrW(v9, -21, (LONG_PTR)this);
  if ( (*((_DWORD *)this + 517) & 0x100) != 0 )
  {
    LastError = CRailContWndExt::InitializeProgressCtrl(this, *((HWND *)this + 16));
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)LastError;
      }
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 28;
      v14 = "InitializeProgressCtrl failed!";
      goto LABEL_20;
    }
    LastError = CRailContWndExt::CreateFonts(this);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)LastError;
      }
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 29;
      v14 = "CreateFonts failed!";
LABEL_20:
      v24 = LastError;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)&WPP_054707ce312e306d358833de4c0f150b_Traceguids,
        v12,
        (__int64)v14,
        v24,
        *(_QWORD *)&Rect.left,
        *(_QWORD *)&Rect.right);
      return (unsigned int)LastError;
    }
  }
  GetWindowRect(*((HWND *)this + 16), &Rect);
  v15 = (HWND)*((_QWORD *)this + 16);
  *((_DWORD *)this + 10) += Rect.bottom - Rect.top;
  *((_DWORD *)this + 517) |= 0x40u;
  DlgItem = GetDlgItem(v15, 13200);
  *((_QWORD *)this + 17) = DlgItem;
  if ( DlgItem )
  {
    if ( (*((_DWORD *)this + 517) & 0x100) != 0
      && !SetWindowSubclass(DlgItem, CRailContWndExt::ConQueueListViewSubProc, 0x3390u, (DWORD_PTR)this)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v18 = GetLastError();
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v19, v18);
    }
    SendMessageW(*((HWND *)this + 17), 0x1001u, 0, 0xFFFFFFFFLL);
    SendMessageW(*((HWND *)this + 17), 0x1026u, 0, 0xFFFFFFFFLL);
    SendMessageW(*((HWND *)this + 17), 0x104Au, 0, 0);
    v20 = (double)SystemMetrics * 3.7;
    if ( v20 >= 9.223372036854776e18 )
      v20 = v20 - 9.223372036854776e18;
    SendMessageW(*((HWND *)this + 17), 0x1035u, 0, ((unsigned __int16)(5 * v8) << 16) | (unsigned __int16)(int)v20);
    if ( (*((_DWORD *)this + 517) & 0x100) == 0 )
      EnableWindow(*((HWND *)this + 17), 0);
    v21 = ImageList_Create(SystemMetrics, v8, 0x21u, 0, 32);
    *((_QWORD *)this + 18) = v21;
    if ( v21 )
    {
      SendMessageW(*((HWND *)this + 17), 0x1003u, 0, (LPARAM)v21);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v22);
      }
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_054707ce312e306d358833de4c0f150b_Traceguids, v17);
    }
    return (unsigned int)-2147418113;
  }
}

```

## disassembly

```asm
0x14001fbe0  mov     [rsp+arg_10], rbx
0x14001fbe5  push    rbp
0x14001fbe6  push    rsi
0x14001fbe7  push    rdi
0x14001fbe8  push    r14
0x14001fbea  push    r15
0x14001fbec  sub     rsp, 50h
0x14001fbf0  mov     rax, cs:__security_cookie
0x14001fbf7  xor     rax, rsp
0x14001fbfa  mov     [rsp+78h+var_38], rax
0x14001fbff  cmp     qword ptr [rcx+820h], 0
0x14001fc07  xorps   xmm0, xmm0
0x14001fc0a  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x14001fc0f  mov     rsi, rdx
0x14001fc12  mov     rdi, rcx
0x14001fc15  jz      short loc_14001FC4B
0x14001fc17  call    ?GetDpi@CRailContWndExt@@AEAAIXZ; CRailContWndExt::GetDpi(void)
0x14001fc1c  mov     rcx, [rdi+820h]; this
0x14001fc23  mov     r8d, eax; unsigned int
0x14001fc26  mov     edx, 0Bh; int
0x14001fc2b  mov     ebx, eax
0x14001fc2d  call    ?GetSystemMetricsForDpi@Win32DpiApi@@QEAAHHI@Z; Win32DpiApi::GetSystemMetricsForDpi(int,uint)
0x14001fc32  mov     rcx, [rdi+820h]; this
0x14001fc39  mov     r8d, ebx; unsigned int
0x14001fc3c  mov     edx, 0Ch; int
0x14001fc41  mov     r14d, eax
0x14001fc44  call    ?GetSystemMetricsForDpi@Win32DpiApi@@QEAAHHI@Z; Win32DpiApi::GetSystemMetricsForDpi(int,uint)
0x14001fc49  jmp     short loc_14001FC62
0x14001fc4b  mov     ecx, 0Bh; int
0x14001fc50  call    xGetSystemMetrics
0x14001fc55  mov     ecx, 0Ch; int
0x14001fc5a  mov     r14d, eax
0x14001fc5d  call    xGetSystemMetrics
0x14001fc62  mov     rcx, [rdi+8]; HINSTANCE
0x14001fc66  lea     r9, ?STATIC_ConQueuePaneWndProc@CRailContWndExt@@SA_JPEAUHWND__@@I_K_J@Z; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x14001fc6d  mov     ebp, eax
0x14001fc6f  mov     qword ptr [rsp+78h+cGrow], 0; __int64
0x14001fc78  mov     eax, [rdi+814h]
0x14001fc7e  mov     r15d, 100h
0x14001fc84  and     eax, r15d
0x14001fc87  mov     r8, rsi; HWND
0x14001fc8a  neg     eax
0x14001fc8c  sbb     rdx, rdx
0x14001fc8f  and     edx, 6
0x14001fc92  add     rdx, 36C7h; unsigned __int16 *
0x14001fc99  call    ?TSCreateDialogParamW@@YAPEAUHWND__@@PEAUHINSTANCE__@@PEBGPEAU1@P6A_J2I_K_J@Z4@Z; TSCreateDialogParamW(HINSTANCE__ *,ushort const *,HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),__int64)
0x14001fc9e  mov     [rdi+80h], rax
0x14001fca5  test    rax, rax
0x14001fca8  jnz     short loc_14001FD15
0x14001fcaa  call    cs:__imp_GetLastError
0x14001fcb0  mov     ebx, eax
0x14001fcb2  mov     rax, cs:WPP_GLOBAL_Control
0x14001fcb9  lea     rsi, WPP_GLOBAL_Control
0x14001fcc0  cmp     rax, rsi
0x14001fcc3  jz      short loc_14001FCF9
0x14001fcc5  test    byte ptr [rax+1Ch], 8
0x14001fcc9  jz      short loc_14001FCF9
0x14001fccb  cmp     byte ptr [rax+19h], 2
0x14001fccf  jb      short loc_14001FCF9
0x14001fcd1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001fcd6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fcdd  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001fce4  mov     edx, 1Bh
0x14001fce9  mov     [rsp+78h+cGrow], ebx
0x14001fced  mov     r9d, eax
0x14001fcf0  mov     rcx, [rcx+10h]
0x14001fcf4  call    WPP_SF_Dd
0x14001fcf9  test    ebx, ebx
0x14001fcfb  jle     short loc_14001FD06
0x14001fcfd  movzx   ebx, bx
0x14001fd00  or      ebx, 80070000h
0x14001fd06  test    ebx, ebx
0x14001fd08  mov     eax, 80004005h
0x14001fd0d  cmovns  ebx, eax
0x14001fd10  jmp     loc_14002004E
0x14001fd15  mov     r8, rdi; dwNewLong
0x14001fd18  mov     edx, 0FFFFFFEBh; nIndex
0x14001fd1d  mov     rcx, rax; hWnd
0x14001fd20  call    cs:__imp_SetWindowLongPtrW
0x14001fd26  test    [rdi+814h], r15d
0x14001fd2d  jz      loc_14001FDF8
0x14001fd33  mov     rdx, [rdi+80h]; HWND
0x14001fd3a  mov     rcx, rdi; this
0x14001fd3d  call    ?InitializeProgressCtrl@CRailContWndExt@@AEAAJPEAUHWND__@@@Z; CRailContWndExt::InitializeProgressCtrl(HWND__ *)
0x14001fd42  mov     ebx, eax
0x14001fd44  test    eax, eax
0x14001fd46  jns     short loc_14001FDAC
0x14001fd48  mov     rax, cs:WPP_GLOBAL_Control
0x14001fd4f  lea     rsi, WPP_GLOBAL_Control
0x14001fd56  cmp     rax, rsi
0x14001fd59  jz      loc_14002004E
0x14001fd5f  test    byte ptr [rax+1Ch], 8
0x14001fd63  jz      loc_14002004E
0x14001fd69  cmp     byte ptr [rax+19h], 2
0x14001fd6d  jb      loc_14002004E
0x14001fd73  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001fd78  mov     edx, 1Ch
0x14001fd7d  lea     rcx, aInitializeprog; "InitializeProgressCtrl failed!"
0x14001fd84  mov     [rsp+78h+var_50], ebx
0x14001fd88  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001fd8f  mov     qword ptr [rsp+78h+cGrow], rcx
0x14001fd94  mov     r9d, eax
0x14001fd97  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd9e  mov     rcx, [rcx+10h]
0x14001fda2  call    WPP_SF_DsD
0x14001fda7  jmp     loc_14002004E
0x14001fdac  mov     rcx, rdi; this
0x14001fdaf  call    ?CreateFonts@CRailContWndExt@@AEAAJXZ; CRailContWndExt::CreateFonts(void)
0x14001fdb4  mov     ebx, eax
0x14001fdb6  test    eax, eax
0x14001fdb8  jns     short loc_14001FDF8
0x14001fdba  mov     rax, cs:WPP_GLOBAL_Control
0x14001fdc1  lea     rsi, WPP_GLOBAL_Control
0x14001fdc8  cmp     rax, rsi
0x14001fdcb  jz      loc_14002004E
0x14001fdd1  test    byte ptr [rax+1Ch], 8
0x14001fdd5  jz      loc_14002004E
0x14001fddb  cmp     byte ptr [rax+19h], 2
0x14001fddf  jb      loc_14002004E
0x14001fde5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001fdea  mov     edx, 1Dh
0x14001fdef  lea     rcx, aCreatefontsFai; "CreateFonts failed!"
0x14001fdf6  jmp     short loc_14001FD84
0x14001fdf8  mov     rcx, [rdi+80h]; hWnd
0x14001fdff  lea     rdx, [rsp+78h+Rect]; lpRect
0x14001fe04  call    cs:__imp_GetWindowRect
0x14001fe0a  mov     eax, [rsp+78h+Rect.bottom]
0x14001fe0e  mov     ebx, 3390h
0x14001fe13  sub     eax, [rsp+78h+Rect.top]
0x14001fe17  mov     edx, ebx; nIDDlgItem
0x14001fe19  mov     rcx, [rdi+80h]; hDlg
0x14001fe20  add     [rdi+28h], eax
0x14001fe23  or      dword ptr [rdi+814h], 40h
0x14001fe2a  call    cs:__imp_GetDlgItem
0x14001fe30  mov     [rdi+88h], rax
0x14001fe37  test    rax, rax
0x14001fe3a  jnz     short loc_14001FE89
0x14001fe3c  mov     rax, cs:WPP_GLOBAL_Control
0x14001fe43  lea     rsi, WPP_GLOBAL_Control
0x14001fe4a  cmp     rax, rsi
0x14001fe4d  jz      short loc_14001FE7F
0x14001fe4f  test    byte ptr [rax+1Ch], 1
0x14001fe53  jz      short loc_14001FE7F
0x14001fe55  cmp     byte ptr [rax+19h], 2
0x14001fe59  jb      short loc_14001FE7F
0x14001fe5b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001fe60  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fe67  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001fe6e  mov     edx, 1Eh
0x14001fe73  mov     r9d, eax
0x14001fe76  mov     rcx, [rcx+10h]
0x14001fe7a  call    WPP_SF_d
0x14001fe7f  mov     ebx, 8000FFFFh
0x14001fe84  jmp     loc_14002004E
0x14001fe89  lea     rsi, WPP_GLOBAL_Control
0x14001fe90  test    [rdi+814h], r15d
0x14001fe97  jz      short loc_14001FEFB
0x14001fe99  mov     r9, rdi; dwRefData
0x14001fe9c  lea     rdx, ?ConQueueListViewSubProc@CRailContWndExt@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x14001fea3  mov     r8, rbx; uIdSubclass
0x14001fea6  mov     rcx, rax; hWnd
0x14001fea9  call    cs:__imp_SetWindowSubclass
0x14001feaf  test    eax, eax
0x14001feb1  jnz     short loc_14001FEFB
0x14001feb3  mov     rax, cs:WPP_GLOBAL_Control
0x14001feba  cmp     rax, rsi
0x14001febd  jz      short loc_14001FEFB
0x14001febf  test    byte ptr [rax+1Ch], 1
0x14001fec3  jz      short loc_14001FEFB
0x14001fec5  cmp     byte ptr [rax+19h], 2
0x14001fec9  jb      short loc_14001FEFB
0x14001fecb  call    cs:__imp_GetLastError
0x14001fed1  mov     ebx, eax
0x14001fed3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001fed8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fedf  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14001fee6  mov     edx, 1Fh
0x14001feeb  mov     [rsp+78h+cGrow], ebx
0x14001feef  mov     r9d, eax
0x14001fef2  mov     rcx, [rcx+10h]
0x14001fef6  call    WPP_SF_Dd
0x14001fefb  mov     rcx, [rdi+88h]; hWnd
0x14001ff02  mov     ebx, 0FFFFFFFFh
0x14001ff07  mov     r9d, ebx; lParam
0x14001ff0a  xor     r8d, r8d; wParam
0x14001ff0d  mov     edx, 1001h; Msg
0x14001ff12  call    cs:__imp_SendMessageW
0x14001ff18  mov     rcx, [rdi+88h]; hWnd
0x14001ff1f  mov     r9d, ebx; lParam
0x14001ff22  xor     r8d, r8d; wParam
0x14001ff25  mov     edx, 1026h; Msg
0x14001ff2a  call    cs:__imp_SendMessageW
0x14001ff30  mov     rcx, [rdi+88h]; hWnd
0x14001ff37  xor     r9d, r9d; lParam
0x14001ff3a  xor     r8d, r8d; wParam
0x14001ff3d  mov     edx, 104Ah; Msg
0x14001ff42  call    cs:__imp_SendMessageW
0x14001ff48  movsd   xmm1, cs:__real@43e0000000000000
0x14001ff50  xor     ecx, ecx
0x14001ff52  movd    xmm0, r14d
0x14001ff57  cvtdq2pd xmm0, xmm0
0x14001ff5b  mulsd   xmm0, cs:__real@400d99999999999a
0x14001ff63  comisd  xmm0, xmm1
0x14001ff67  jb      short loc_14001FF80
0x14001ff69  subsd   xmm0, xmm1
0x14001ff6d  comisd  xmm0, xmm1
0x14001ff71  jnb     short loc_14001FF80
0x14001ff73  mov     rax, 8000000000000000h
0x14001ff7d  mov     rcx, rax
0x14001ff80  cvttsd2si rax, xmm0
0x14001ff85  xor     r8d, r8d; wParam
0x14001ff88  add     rax, rcx
0x14001ff8b  movzx   ecx, bp
0x14001ff8e  shl     cx, 2
0x14001ff92  movzx   edx, ax
0x14001ff95  lea     eax, [rcx+rbp]
0x14001ff98  movzx   ecx, ax
0x14001ff9b  shl     ecx, 10h
0x14001ff9e  or      edx, ecx
0x14001ffa0  mov     rcx, [rdi+88h]; hWnd
0x14001ffa7  movsxd  r9, edx; lParam
0x14001ffaa  mov     edx, 1035h; Msg
0x14001ffaf  call    cs:__imp_SendMessageW
0x14001ffb5  test    [rdi+814h], r15d
0x14001ffbc  jnz     short loc_14001FFCD
0x14001ffbe  mov     rcx, [rdi+88h]; hWnd
0x14001ffc5  xor     edx, edx; bEnable
0x14001ffc7  call    cs:__imp_EnableWindow
0x14001ffcd  mov     ebx, 20h ; ' '
0x14001ffd2  xor     r9d, r9d; cInitial
0x14001ffd5  mov     edx, ebp; cy
0x14001ffd7  mov     [rsp+78h+cGrow], ebx; cGrow
0x14001ffdb  mov     ecx, r14d; cx
0x14001ffde  lea     r8d, [rbx+1]; flags
0x14001ffe2  call    cs:__imp_ImageList_Create
0x14001ffe8  mov     [rdi+90h], rax
0x14001ffef  test    rax, rax
0x14001fff2  jnz     short loc_140020034
0x14001fff4  mov     rax, cs:WPP_GLOBAL_Control
0x14001fffb  cmp     rax, rsi
0x14001fffe  jz      short loc_14002002D
0x140020000  test    byte ptr [rax+1Ch], 1
0x140020004  jz      short loc_14002002D
0x140020006  cmp     byte ptr [rax+19h], 2
0x14002000a  jb      short loc_14002002D
0x14002000c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140020011  mov     rcx, cs:WPP_GLOBAL_Control
0x140020018  lea     r8, WPP_054707ce312e306d358833de4c0f150b_Traceguids
0x14002001f  mov     edx, ebx
0x140020021  mov     r9d, eax
0x140020024  mov     rcx, [rcx+10h]
0x140020028  call    WPP_SF_d
0x14002002d  mov     ebx, 8007000Eh
0x140020032  jmp     short loc_14002004E
0x140020034  mov     rcx, [rdi+88h]; hWnd
0x14002003b  mov     r9, rax; lParam
0x14002003e  xor     r8d, r8d; wParam
0x140020041  mov     edx, 1003h; Msg
0x140020046  call    cs:__imp_SendMessageW
0x14002004c  xor     ebx, ebx
0x14002004e  mov     eax, ebx
0x140020050  mov     rcx, [rsp+78h+var_38]
0x140020055  xor     rcx, rsp; StackCookie
0x140020058  call    __security_check_cookie
0x14002005d  mov     rbx, [rsp+78h+arg_10]
0x140020065  add     rsp, 50h
0x140020069  pop     r15
0x14002006b  pop     r14
0x14002006d  pop     rdi
0x14002006e  pop     rsi
0x14002006f  pop     rbp
0x140020070  retn
```
