# CuipGetUserDesktopSnapshot(void)

- ea: `0x140006d00`
- end: `0x140006fc8`
- name: `?CuipGetUserDesktopSnapshot@@YAKXZ`
- size: `712`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001adb0`

## callees

- `0x140006d00`
- `0x140006fd0`
- `0x140007250`
- `0x14000fbec`
- `0x140013928`
- `0x14001bb44`
- `0x14001e050`

## import_xrefs

- `GDI32!SelectObject` at `0x140006dda`
- `GDI32!SelectObject` at `0x140006dda`
- `GDI32!DeleteObject` at `0x140006f8e`
- `GDI32!DeleteObject` at `0x14001e264`
- `GDI32!DeleteObject` at `0x140006f8e`
- `GDI32!DeleteObject` at `0x14001e264`
- `GDI32!SetDCBrushColor` at `0x140006ef1`
- `GDI32!SetDCBrushColor` at `0x140006ef1`
- `GDI32!CreateCompatibleDC` at `0x140006d57`
- `GDI32!CreateCompatibleDC` at `0x140006d57`
- `GDI32!GetLayout` at `0x140006e39`
- `GDI32!GetLayout` at `0x140006e6c`
- `GDI32!GetLayout` at `0x140006e39`
- `GDI32!GetLayout` at `0x140006e6c`
- `GDI32!GetStockObject` at `0x140006efc`
- `GDI32!GetStockObject` at `0x140006efc`
- `GDI32!CreateCompatibleBitmap` at `0x140006d89`
- `GDI32!CreateCompatibleBitmap` at `0x140006d89`
- `USER32!GetDC` at `0x140006d46`
- `USER32!GetDC` at `0x140006d46`
- `USER32!FillRect` at `0x140006f0d`
- `USER32!FillRect` at `0x140006f0d`
- `USER32!GetSystemMetrics` at `0x140006e8f`
- `USER32!GetSystemMetrics` at `0x140006e8f`
- `USER32!ReleaseDC` at `0x140006f80`
- `USER32!ReleaseDC` at `0x14001e254`
- `USER32!ReleaseDC` at `0x140006f80`
- `USER32!ReleaseDC` at `0x14001e254`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006de5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006de5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006f37`
- `ntdll!EtwEventWrite` at `0x140006d3d`
- `ntdll!EtwEventWrite` at `0x140006fa8`
- `ntdll!EtwEventWrite` at `0x140006d3d`
- `ntdll!EtwEventWrite` at `0x140006fa8`

## pseudocode

```c
__int64 CuipGetUserDesktopSnapshot(void)
{
  HBITMAP v0; // rsi
  HDC DC; // rdi
  HDC CompatibleDC; // r14
  HBITMAP CompatibleBitmap; // rax
  DWORD LastError; // eax
  DWORD v5; // r14d
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  DWORD Layout; // eax
  __int64 v10; // r8
  DWORD v11; // eax
  __int64 v12; // r8
  HBRUSH StockObject; // rax
  RECT rc; // [rsp+38h] [rbp-40h] BYREF

  v0 = 0;
  EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_GetUserDesktopSnapshot_Start, 0, 0);
  DC = GetDC(0);
  CompatibleDC = CreateCompatibleDC(DC);
  hdc = CompatibleDC;
  if ( CompatibleDC && DC )
  {
    CompatibleBitmap = CreateCompatibleBitmap(DC, nWidth, nHeight);
    v0 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      if ( SelectObject(CompatibleDC, CompatibleBitmap) )
      {
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          {
            Layout = GetLayout(DC);
            WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 32, v10, Layout);
            v8 = WPP_GLOBAL_Control;
          }
          if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_BYTE *)(v8 + 28) & 4) != 0 )
          {
            v11 = GetLayout(CompatibleDC);
            WPP_SF_l(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, v12, v11);
          }
        }
        if ( GetSystemMetrics(4096) )
        {
          rc = 0;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
          *(_QWORD *)&rc.left = 0;
          rc.right = nWidth;
          rc.bottom = nHeight;
          SetDCBrushColor(CompatibleDC, 0x7A5F1Du);
          StockObject = (HBRUSH)GetStockObject(18);
          FillRect(CompatibleDC, &rc, StockObject);
          v5 = 0;
        }
        else
        {
          CuipPaintDesktop(CompatibleDC);
          CuipAlphaBlend(CompatibleDC);
          v5 = 0;
        }
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          v7 = 31;
          goto LABEL_26;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v7 = 30;
LABEL_26:
        WPP_SF_D(*(_QWORD *)(v6 + 16), v7, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, LastError);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v7 = 29;
      goto LABEL_26;
    }
  }
  if ( DC )
    ReleaseDC(0, DC);
  if ( v0 )
    DeleteObject(v0);
  EtwEventWrite(g_ConsentPerfRegHandle, ConsentUI_GetUserDesktopSnapshot_Stop, 0, 0);
  return v5;
}

```

## disassembly

```asm
0x140006d00  push    rbx
0x140006d02  push    rsi
0x140006d03  push    rdi
0x140006d04  push    r14
0x140006d06  sub     rsp, 58h
0x140006d0a  mov     rax, cs:__security_cookie
0x140006d11  xor     rax, rsp
0x140006d14  mov     [rsp+78h+var_30], rax
0x140006d19  mov     [rsp+78h+var_50], 0
0x140006d22  xor     esi, esi
0x140006d24  mov     [rsp+78h+var_48], rsi
0x140006d29  xor     r9d, r9d
0x140006d2c  xor     r8d, r8d
0x140006d2f  lea     rdx, ConsentUI_GetUserDesktopSnapshot_Start
0x140006d36  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x140006d3d  call    cs:__imp_EtwEventWrite
0x140006d43  nop
0x140006d44  xor     ecx, ecx; hWnd
0x140006d46  call    cs:__imp_GetDC
0x140006d4c  mov     rdi, rax
0x140006d4f  mov     [rsp+78h+var_50], rax
0x140006d54  mov     rcx, rax; hdc
0x140006d57  call    cs:__imp_CreateCompatibleDC
0x140006d5d  mov     r14, rax
0x140006d60  mov     cs:hdc, rax
0x140006d67  test    rax, rax
0x140006d6a  jz      loc_140006F37
0x140006d70  test    rdi, rdi
0x140006d73  jz      loc_140006F37
0x140006d79  mov     r8d, cs:nHeight; cy
0x140006d80  mov     edx, cs:nWidth; cx
0x140006d86  mov     rcx, rdi; hdc
0x140006d89  call    cs:__imp_CreateCompatibleBitmap
0x140006d8f  mov     rsi, rax
0x140006d92  mov     [rsp+78h+var_48], rax
0x140006d97  test    rax, rax
0x140006d9a  jnz     short loc_140006DD4
0x140006d9c  call    cs:__imp_GetLastError
0x140006da2  mov     r14d, eax
0x140006da5  mov     [rsp+78h+var_58], eax
0x140006da9  lea     rbx, WPP_GLOBAL_Control
0x140006db0  mov     rcx, cs:WPP_GLOBAL_Control
0x140006db7  cmp     rcx, rbx
0x140006dba  jz      loc_140006F76
0x140006dc0  test    byte ptr [rcx+1Ch], 4
0x140006dc4  jz      loc_140006F76
0x140006dca  mov     edx, 1Eh
0x140006dcf  jmp     loc_140006F62
0x140006dd4  mov     rdx, rax; h
0x140006dd7  mov     rcx, r14; hdc
0x140006dda  call    cs:__imp_SelectObject
0x140006de0  test    rax, rax
0x140006de3  jnz     short loc_140006E1D
0x140006de5  call    cs:__imp_GetLastError
0x140006deb  mov     r14d, eax
0x140006dee  mov     [rsp+78h+var_58], eax
0x140006df2  lea     rbx, WPP_GLOBAL_Control
0x140006df9  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e00  cmp     rcx, rbx
0x140006e03  jz      loc_140006F76
0x140006e09  test    byte ptr [rcx+1Ch], 4
0x140006e0d  jz      loc_140006F76
0x140006e13  mov     edx, 1Fh
0x140006e18  jmp     loc_140006F62
0x140006e1d  lea     rbx, WPP_GLOBAL_Control
0x140006e24  mov     rax, cs:WPP_GLOBAL_Control
0x140006e2b  cmp     rax, rbx
0x140006e2e  jz      short loc_140006E8A
0x140006e30  test    byte ptr [rax+1Ch], 4
0x140006e34  jz      short loc_140006E5E
0x140006e36  mov     rcx, rdi; hdc
0x140006e39  call    cs:__imp_GetLayout
0x140006e3f  mov     edx, 20h ; ' '
0x140006e44  mov     r9d, eax
0x140006e47  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e4e  mov     rcx, [rcx+10h]
0x140006e52  call    WPP_SF_l
0x140006e57  mov     rax, cs:WPP_GLOBAL_Control
0x140006e5e  cmp     rax, rbx
0x140006e61  jz      short loc_140006E8A
0x140006e63  test    byte ptr [rax+1Ch], 4
0x140006e67  jz      short loc_140006E8A
0x140006e69  mov     rcx, r14; hdc
0x140006e6c  call    cs:__imp_GetLayout
0x140006e72  mov     edx, 21h ; '!'
0x140006e77  mov     r9d, eax
0x140006e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e81  mov     rcx, [rcx+10h]
0x140006e85  call    WPP_SF_l
0x140006e8a  mov     ecx, 1000h; nIndex
0x140006e8f  call    cs:__imp_GetSystemMetrics
0x140006e95  test    eax, eax
0x140006e97  jz      loc_140006F1D
0x140006e9d  xorps   xmm0, xmm0
0x140006ea0  movups  xmmword ptr [rsp+78h+rc.left], xmm0
0x140006ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x140006eac  cmp     rcx, rbx
0x140006eaf  jz      short loc_140006ECC
0x140006eb1  test    byte ptr [rcx+1Ch], 4
0x140006eb5  jz      short loc_140006ECC
0x140006eb7  mov     edx, 22h ; '"'
0x140006ebc  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140006ec3  mov     rcx, [rcx+10h]
0x140006ec7  call    WPP_SF_
0x140006ecc  mov     qword ptr [rsp+78h+rc.left], 0
0x140006ed5  mov     eax, cs:nWidth
0x140006edb  mov     [rsp+78h+rc.right], eax
0x140006edf  mov     eax, cs:nHeight
0x140006ee5  mov     [rsp+78h+rc.bottom], eax
0x140006ee9  mov     edx, 7A5F1Dh; color
0x140006eee  mov     rcx, r14; hdc
0x140006ef1  call    cs:__imp_SetDCBrushColor
0x140006ef7  mov     ecx, 12h; i
0x140006efc  call    cs:__imp_GetStockObject
0x140006f02  mov     r8, rax; hbr
0x140006f05  lea     rdx, [rsp+78h+rc]; lprc
0x140006f0a  mov     rcx, r14; hDC
0x140006f0d  call    cs:__imp_FillRect
0x140006f13  xor     r14d, r14d
0x140006f16  mov     [rsp+78h+var_58], r14d
0x140006f1b  jmp     short loc_140006F76
0x140006f1d  mov     rcx, r14; hdc
0x140006f20  call    ?CuipPaintDesktop@@YAXPEAUHDC__@@@Z; CuipPaintDesktop(HDC__ *)
0x140006f25  mov     rcx, r14; hdcDest
0x140006f28  call    ?CuipAlphaBlend@@YAXPEAUHDC__@@HKK@Z; CuipAlphaBlend(HDC__ *,int,ulong,ulong)
0x140006f2d  xor     r14d, r14d
0x140006f30  mov     [rsp+78h+var_58], r14d
0x140006f35  jmp     short loc_140006F76
0x140006f37  call    cs:__imp_GetLastError
0x140006f3d  mov     r14d, eax
0x140006f40  mov     [rsp+78h+var_58], eax
0x140006f44  lea     rbx, WPP_GLOBAL_Control
0x140006f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f52  cmp     rcx, rbx
0x140006f55  jz      short loc_140006F76
0x140006f57  test    byte ptr [rcx+1Ch], 4
0x140006f5b  jz      short loc_140006F76
0x140006f5d  mov     edx, 1Dh
0x140006f62  mov     r9d, eax
0x140006f65  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140006f6c  mov     rcx, [rcx+10h]
0x140006f70  call    WPP_SF_D
0x140006f75  nop
0x140006f76  test    rdi, rdi
0x140006f79  jz      short loc_140006F86
0x140006f7b  mov     rdx, rdi; hDC
0x140006f7e  xor     ecx, ecx; hWnd
0x140006f80  call    cs:__imp_ReleaseDC
0x140006f86  test    rsi, rsi
0x140006f89  jz      short loc_140006F94
0x140006f8b  mov     rcx, rsi; ho
0x140006f8e  call    cs:__imp_DeleteObject
0x140006f94  xor     r9d, r9d
0x140006f97  xor     r8d, r8d
0x140006f9a  lea     rdx, ConsentUI_GetUserDesktopSnapshot_Stop
0x140006fa1  mov     rcx, cs:?g_ConsentPerfRegHandle@@3_KA; unsigned __int64 g_ConsentPerfRegHandle
0x140006fa8  call    cs:__imp_EtwEventWrite
0x140006fae  mov     eax, r14d
0x140006fb1  mov     rcx, [rsp+78h+var_30]
0x140006fb6  xor     rcx, rsp; StackCookie
0x140006fb9  call    __security_check_cookie
0x140006fbe  add     rsp, 58h
0x140006fc2  pop     r14
0x140006fc4  pop     rdi
0x140006fc5  pop     rsi
0x140006fc6  pop     rbx
0x140006fc7  retn
0x14001e240  push    rbp
0x14001e242  sub     rsp, 20h
0x14001e246  mov     rbp, rdx
0x14001e249  mov     rdx, [rbp+28h]; hDC
0x14001e24d  test    rdx, rdx
0x14001e250  jz      short loc_14001E25B
0x14001e252  xor     ecx, ecx; hWnd
0x14001e254  call    cs:__imp_ReleaseDC
0x14001e25a  nop
0x14001e25b  mov     rcx, [rbp+30h]; ho
0x14001e25f  test    rcx, rcx
0x14001e262  jz      short loc_14001E26B
0x14001e264  call    cs:__imp_DeleteObject
0x14001e26a  nop
0x14001e26b  add     rsp, 20h
0x14001e26f  pop     rbp
0x14001e270  retn
```
