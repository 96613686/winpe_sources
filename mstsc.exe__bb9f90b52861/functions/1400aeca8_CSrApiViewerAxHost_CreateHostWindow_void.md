# CSrApiViewerAxHost::CreateHostWindow(void)

- ea: `0x1400aeca8`
- end: `0x1400af202`
- name: `?CreateHostWindow@CSrApiViewerAxHost@@AEAAJXZ`
- size: `1370`
- prototype: `__int64 __fastcall(CSrApiViewerAxHost *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400b2d10`

## callees

- `0x140003b2c`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400a5728`
- `0x1400aeca8`
- `0x1400b4ac8`
- `0x140114010`

## import_xrefs

- `USER32!LoadStringW` at `0x1400aef08`
- `USER32!LoadStringW` at `0x1400aef08`
- `USER32!GetMenuItemCount` at `0x1400aeea2`
- `USER32!GetMenuItemCount` at `0x1400aeea2`
- `USER32!InsertMenuItemW` at `0x1400aef95`
- `USER32!InsertMenuItemW` at `0x1400aef95`
- `USER32!GetSystemMenu` at `0x1400aee4c`
- `USER32!GetSystemMenu` at `0x1400aee4c`
- `USER32!LoadIconW` at `0x1400aefeb`
- `USER32!LoadIconW` at `0x1400aefeb`
- `USER32!CreateWindowExW` at `0x1400aedf0`
- `USER32!CreateWindowExW` at `0x1400aedf0`
- `USER32!SendMessageW` at `0x1400af04b`
- `USER32!SendMessageW` at `0x1400af04b`
- `KERNEL32!GetLastError` at `0x1400aee02`
- `KERNEL32!GetLastError` at `0x1400aee5a`
- `KERNEL32!GetLastError` at `0x1400aeeb0`
- `KERNEL32!GetLastError` at `0x1400aef12`
- `KERNEL32!GetLastError` at `0x1400aef9f`
- `KERNEL32!GetLastError` at `0x1400aeff6`
- `KERNEL32!GetLastError` at `0x1400af183`
- `KERNEL32!GetLastError` at `0x1400aee02`
- `KERNEL32!GetLastError` at `0x1400aee5a`
- `KERNEL32!GetLastError` at `0x1400aeeb0`
- `KERNEL32!GetLastError` at `0x1400aef12`
- `KERNEL32!GetLastError` at `0x1400aef9f`
- `KERNEL32!GetLastError` at `0x1400aeff6`
- `KERNEL32!GetLastError` at `0x1400af183`
- `ADVAPI32!RegGetValueW` at `0x1400aed1a`
- `ADVAPI32!RegGetValueW` at `0x1400aed1a`

## pseudocode

```c
__int64 __fastcall CSrApiViewerAxHost::CreateHostWindow(CSrApiViewerAxHost *this)
{
  int ValueW; // ebx
  unsigned int v3; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HWND Window; // rax
  unsigned int v6; // eax
  __int64 v7; // rdx
  HMENU SystemMenu; // rax
  HMENU v9; // rbx
  int MenuItemCount; // r14d
  bool v11; // zf
  UINT v12; // eax
  HICON IconW; // rax
  CDlgBase *v14; // rax
  CDlgBase *v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rax
  bool v19; // sf
  PVOID pvData; // [rsp+28h] [rbp-51h]
  MENUITEMINFOW mi; // [rsp+60h] [rbp-19h] BYREF
  int v23; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD pcbData; // [rsp+F0h] [rbp+77h] BYREF
  WCHAR *Buffer; // [rsp+F8h] [rbp+7Fh] BYREF

  v23 = 1;
  Buffer = 0;
  memset_0(&mi, 0, sizeof(mi));
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Terminal Server Client",
             L"ShadowSmartSizing",
             0x10u,
             0,
             &v23,
             &pcbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( ValueW > 0 )
        v3 = (unsigned __int16)ValueW | 0x80070000;
      else
        v3 = ValueW;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        CurrentThreadActivityIdPrefix,
        v3);
    }
    if ( ValueW > 0 )
      return (unsigned __int16)ValueW | 0x80070000;
    return (unsigned int)ValueW;
  }
  *((_DWORD *)this + 64) = v23 != 0;
  Window = CreateWindowExW(
             0,
             L"SrApiViewerAxContainerClass",
             &pszPassword,
             0xCF0000u,
             0,
             0,
             0,
             0,
             0,
             0,
             *((HINSTANCE *)this + 22),
             this);
  *((_QWORD *)this + 16) = Window;
  if ( !Window )
  {
    ValueW = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 69;
LABEL_62:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids, v6, ValueW);
LABEL_63:
    v19 = ValueW < 0;
    if ( ValueW > 0 )
    {
      ValueW = (unsigned __int16)ValueW | 0x80070000;
      v19 = ValueW < 0;
    }
    if ( !v19 )
      return (unsigned int)-2147467259;
    return (unsigned int)ValueW;
  }
  SystemMenu = GetSystemMenu(Window, 0);
  v9 = SystemMenu;
  if ( !SystemMenu )
  {
    ValueW = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 70;
    goto LABEL_62;
  }
  MenuItemCount = GetMenuItemCount(SystemMenu);
  if ( MenuItemCount < 1 )
  {
    ValueW = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 71;
    goto LABEL_62;
  }
  if ( !LoadStringW(*((HINSTANCE *)this + 23), 0xBC9u, (LPWSTR)&Buffer, 0) )
  {
    ValueW = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 72;
    goto LABEL_62;
  }
  v11 = *((_DWORD *)this + 64) == 0;
  mi.cbSize = 80;
  *(_QWORD *)&mi.fMask = 67;
  v12 = 0;
  mi.wID = 16;
  if ( !v11 )
    v12 = 8;
  mi.fState = v12;
  mi.dwTypeData = Buffer;
  if ( !InsertMenuItemW(v9, MenuItemCount - 1, 1, &mi) )
  {
    ValueW = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 73;
    goto LABEL_62;
  }
  IconW = LoadIconW(*((HINSTANCE *)this + 22), (LPCWSTR)0x65);
  if ( !IconW )
  {
    ValueW = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_63;
    }
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 74;
    goto LABEL_62;
  }
  SendMessageW(*((HWND *)this + 16), 0x80u, 1u, (LPARAM)IconW);
  v14 = (CDlgBase *)operator new(0x58u);
  v15 = v14;
  if ( v14 )
  {
    CDlgBase::CDlgBase(v14, 0, *((HINSTANCE *)this + 22), 410);
    *((_QWORD *)v15 + 9) = 0;
    *(_QWORD *)v15 = &CShadowConnectingDlg::`vftable';
    *((_QWORD *)v15 + 10) = 0;
  }
  else
  {
    v15 = 0;
  }
  *((_QWORD *)this + 11) = v15;
  if ( v15 )
  {
    ValueW = CShadowConnectingDlg::Initialize(v15, *((HWND *)this + 16), *((const unsigned __int16 **)this + 24));
    if ( ValueW >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 16LL))(*((_QWORD *)this + 11));
      *((_QWORD *)this + 12) = v18;
      if ( v18 )
        return (unsigned int)ValueW;
      ValueW = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_63;
      }
      v6 = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 77;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(pvData) = ValueW;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        (unsigned int)&WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v17,
        (__int64)"m_spViewer->Initialize failed",
        pvData);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        v16,
        -2147024882);
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1400aeca8  mov     [rsp-8+arg_0], rbx
0x1400aecad  push    rbp
0x1400aecae  push    rsi
0x1400aecaf  push    rdi
0x1400aecb0  push    r14
0x1400aecb2  push    r15
0x1400aecb4  lea     rbp, [rsp-37h]
0x1400aecb9  sub     rsp, 0B0h
0x1400aecc0  xor     r15d, r15d
0x1400aecc3  mov     [rbp+57h+arg_8], 1
0x1400aecca  mov     rsi, rcx
0x1400aeccd  mov     [rbp+57h+Buffer], r15
0x1400aecd1  xor     edx, edx; Val
0x1400aecd3  lea     rcx, [rbp+57h+mi]; void *
0x1400aecd7  lea     edi, [r15+50h]
0x1400aecdb  mov     r8d, edi; Size
0x1400aecde  call    memset_0
0x1400aece3  lea     rax, [rbp+57h+arg_10]
0x1400aece7  mov     [rbp+57h+arg_10], 4
0x1400aecee  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1400aecf3  lea     r9d, [r15+10h]; dwFlags
0x1400aecf7  lea     rax, [rbp+57h+arg_8]
0x1400aecfb  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1400aed02  mov     [rsp+0D0h+pvData], rax; pvData
0x1400aed07  lea     r8, ?s_kszSmartSizingRegValue@CSrApiViewerAxHost@@0QBGB; "ShadowSmartSizing"
0x1400aed0e  lea     rdx, ?s_kszShadowRegKeyPath@CSrApiViewerAxHost@@0QBGB; "Software\\Microsoft\\Terminal Server Cl"...
0x1400aed15  mov     [rsp+0D0h+pdwType], r15; pdwType
0x1400aed1a  call    cs:__imp_RegGetValueW
0x1400aed20  mov     ebx, eax
0x1400aed22  test    eax, 0FFFFFFFDh
0x1400aed27  jz      short loc_1400AED9B
0x1400aed29  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aed30  lea     rax, WPP_GLOBAL_Control
0x1400aed37  cmp     rcx, rax
0x1400aed3a  jz      short loc_1400AED85
0x1400aed3c  lea     edi, [r15+8]
0x1400aed40  test    [rcx+1Ch], dil
0x1400aed44  jz      short loc_1400AED85
0x1400aed46  cmp     byte ptr [rcx+19h], 2
0x1400aed4a  jb      short loc_1400AED85
0x1400aed4c  test    ebx, ebx
0x1400aed4e  jg      short loc_1400AED54
0x1400aed50  mov     edi, ebx
0x1400aed52  jmp     short loc_1400AED5D
0x1400aed54  movzx   edi, bx
0x1400aed57  or      edi, 80070000h
0x1400aed5d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aed62  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aed69  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400aed70  mov     edx, 44h ; 'D'
0x1400aed75  mov     dword ptr [rsp+0D0h+pdwType], edi
0x1400aed79  mov     r9d, eax
0x1400aed7c  mov     rcx, [rcx+10h]
0x1400aed80  call    WPP_SF_Dd
0x1400aed85  test    ebx, ebx
0x1400aed87  jle     loc_1400AF1E9
0x1400aed8d  movzx   ebx, bx
0x1400aed90  or      ebx, 80070000h
0x1400aed96  jmp     loc_1400AF1E9
0x1400aed9b  cmp     [rbp+57h+arg_8], r15d
0x1400aed9f  lea     r8, pszPassword; lpWindowName
0x1400aeda6  mov     [rsp+0D0h+lpParam], rsi; lpParam
0x1400aedab  lea     rdx, ?s_kszSrApiViewerAxContainerClass@CSrApiViewerAxHost@@0QBGB; "SrApiViewerAxContainerClass"
0x1400aedb2  mov     eax, r15d
0x1400aedb5  mov     r9d, 0CF0000h; dwStyle
0x1400aedbb  setnz   al
0x1400aedbe  xor     ecx, ecx; dwExStyle
0x1400aedc0  mov     [rsi+100h], eax
0x1400aedc6  mov     rax, [rsi+0B0h]
0x1400aedcd  mov     [rsp+0D0h+hInstance], rax; hInstance
0x1400aedd2  mov     [rsp+0D0h+hMenu], r15; hMenu
0x1400aedd7  mov     [rsp+0D0h+hWndParent], r15; hWndParent
0x1400aeddc  mov     [rsp+0D0h+nHeight], r15d; nHeight
0x1400aede1  mov     dword ptr [rsp+0D0h+pcbData], r15d; nWidth
0x1400aede6  mov     dword ptr [rsp+0D0h+pvData], r15d; Y
0x1400aedeb  mov     dword ptr [rsp+0D0h+pdwType], r15d; X
0x1400aedf0  call    cs:__imp_CreateWindowExW
0x1400aedf6  mov     [rsi+80h], rax
0x1400aedfd  test    rax, rax
0x1400aee00  jnz     short loc_1400AEE47
0x1400aee02  call    cs:__imp_GetLastError
0x1400aee08  mov     ebx, eax
0x1400aee0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aee11  lea     rax, WPP_GLOBAL_Control
0x1400aee18  cmp     rcx, rax
0x1400aee1b  jz      loc_1400AF1D2
0x1400aee21  mov     edi, 8
0x1400aee26  test    [rcx+1Ch], dil
0x1400aee2a  jz      loc_1400AF1D2
0x1400aee30  cmp     byte ptr [rcx+19h], 2
0x1400aee34  jb      loc_1400AF1D2
0x1400aee3a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aee3f  lea     edx, [rdi+3Dh]
0x1400aee42  jmp     loc_1400AF1B4
0x1400aee47  xor     edx, edx; bRevert
0x1400aee49  mov     rcx, rax; hWnd
0x1400aee4c  call    cs:__imp_GetSystemMenu
0x1400aee52  mov     rbx, rax
0x1400aee55  test    rax, rax
0x1400aee58  jnz     short loc_1400AEE9F
0x1400aee5a  call    cs:__imp_GetLastError
0x1400aee60  mov     ebx, eax
0x1400aee62  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aee69  lea     rax, WPP_GLOBAL_Control
0x1400aee70  cmp     rcx, rax
0x1400aee73  jz      loc_1400AF1D2
0x1400aee79  mov     edi, 8
0x1400aee7e  test    [rcx+1Ch], dil
0x1400aee82  jz      loc_1400AF1D2
0x1400aee88  cmp     byte ptr [rcx+19h], 2
0x1400aee8c  jb      loc_1400AF1D2
0x1400aee92  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aee97  lea     edx, [rdi+3Eh]
0x1400aee9a  jmp     loc_1400AF1B4
0x1400aee9f  mov     rcx, rbx; hMenu
0x1400aeea2  call    cs:__imp_GetMenuItemCount
0x1400aeea8  mov     r14d, eax
0x1400aeeab  cmp     eax, 1
0x1400aeeae  jge     short loc_1400AEEF5
0x1400aeeb0  call    cs:__imp_GetLastError
0x1400aeeb6  mov     ebx, eax
0x1400aeeb8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aeebf  lea     rax, WPP_GLOBAL_Control
0x1400aeec6  cmp     rcx, rax
0x1400aeec9  jz      loc_1400AF1D2
0x1400aeecf  mov     edi, 8
0x1400aeed4  test    [rcx+1Ch], dil
0x1400aeed8  jz      loc_1400AF1D2
0x1400aeede  cmp     byte ptr [rcx+19h], 2
0x1400aeee2  jb      loc_1400AF1D2
0x1400aeee8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aeeed  lea     edx, [rdi+3Fh]
0x1400aeef0  jmp     loc_1400AF1B4
0x1400aeef5  mov     rcx, [rsi+0B8h]; hInstance
0x1400aeefc  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1400aef00  xor     r9d, r9d; cchBufferMax
0x1400aef03  mov     edx, 0BC9h; uID
0x1400aef08  call    cs:__imp_LoadStringW
0x1400aef0e  test    eax, eax
0x1400aef10  jnz     short loc_1400AEF57
0x1400aef12  call    cs:__imp_GetLastError
0x1400aef18  mov     ebx, eax
0x1400aef1a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aef21  lea     rax, WPP_GLOBAL_Control
0x1400aef28  cmp     rcx, rax
0x1400aef2b  jz      loc_1400AF1D2
0x1400aef31  mov     edi, 8
0x1400aef36  test    [rcx+1Ch], dil
0x1400aef3a  jz      loc_1400AF1D2
0x1400aef40  cmp     byte ptr [rcx+19h], 2
0x1400aef44  jb      loc_1400AF1D2
0x1400aef4a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aef4f  lea     edx, [rdi+40h]
0x1400aef52  jmp     loc_1400AF1B4
0x1400aef57  cmp     [rsi+100h], r15d
0x1400aef5e  lea     edx, [r14-1]; item
0x1400aef62  mov     [rbp+57h+mi.cbSize], edi
0x1400aef65  lea     r9, [rbp+57h+mi]; lpmi
0x1400aef69  mov     edi, 8
0x1400aef6e  mov     qword ptr [rbp+57h+mi.fMask], 43h ; 'C'
0x1400aef76  mov     eax, r15d
0x1400aef79  mov     [rbp+57h+mi.wID], 10h
0x1400aef80  cmovnz  eax, edi
0x1400aef83  mov     rcx, rbx; hmenu
0x1400aef86  mov     [rbp+57h+mi.fState], eax
0x1400aef89  mov     rax, [rbp+57h+Buffer]
0x1400aef8d  lea     r8d, [rdi-7]; fByPosition
0x1400aef91  mov     [rbp+57h+mi.dwTypeData], rax
0x1400aef95  call    cs:__imp_InsertMenuItemW
0x1400aef9b  test    eax, eax
0x1400aef9d  jnz     short loc_1400AEFDF
0x1400aef9f  call    cs:__imp_GetLastError
0x1400aefa5  mov     ebx, eax
0x1400aefa7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aefae  lea     rax, WPP_GLOBAL_Control
0x1400aefb5  cmp     rcx, rax
0x1400aefb8  jz      loc_1400AF1D2
0x1400aefbe  test    [rcx+1Ch], dil
0x1400aefc2  jz      loc_1400AF1D2
0x1400aefc8  cmp     byte ptr [rcx+19h], 2
0x1400aefcc  jb      loc_1400AF1D2
0x1400aefd2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400aefd7  lea     edx, [rdi+41h]
0x1400aefda  jmp     loc_1400AF1B4
0x1400aefdf  mov     rcx, [rsi+0B0h]; hInstance
0x1400aefe6  mov     edx, 65h ; 'e'; lpIconName
0x1400aefeb  call    cs:__imp_LoadIconW
0x1400aeff1  test    rax, rax
0x1400aeff4  jnz     short loc_1400AF038
0x1400aeff6  call    cs:__imp_GetLastError
0x1400aeffc  mov     ebx, eax
0x1400aeffe  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af005  lea     rax, WPP_GLOBAL_Control
0x1400af00c  cmp     rcx, rax
0x1400af00f  jz      loc_1400AF1D2
0x1400af015  test    [rcx+1Ch], dil
0x1400af019  jz      loc_1400AF1D2
0x1400af01f  cmp     byte ptr [rcx+19h], 2
0x1400af023  jb      loc_1400AF1D2
0x1400af029  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af02e  mov     edx, 4Ah ; 'J'
0x1400af033  jmp     loc_1400AF1B4
0x1400af038  mov     rcx, [rsi+80h]; hWnd
0x1400af03f  mov     edx, 80h; Msg
0x1400af044  mov     r9, rax; lParam
0x1400af047  lea     r8d, [rdx-7Fh]; wParam
0x1400af04b  call    cs:__imp_SendMessageW
0x1400af051  mov     ecx, 58h ; 'X'; Size
0x1400af056  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400af05b  mov     rbx, rax
0x1400af05e  test    rax, rax
0x1400af061  jz      short loc_1400AF08E
0x1400af063  mov     r8, [rsi+0B0h]; HINSTANCE
0x1400af06a  mov     r9d, 19Ah; int
0x1400af070  xor     edx, edx; HWND
0x1400af072  mov     rcx, rax; this
0x1400af075  call    ??0CDlgBase@@QEAA@PEAUHWND__@@PEAUHINSTANCE__@@H@Z; CDlgBase::CDlgBase(HWND__ *,HINSTANCE__ *,int)
0x1400af07a  lea     rax, ??_7CShadowConnectingDlg@@6B@; const CShadowConnectingDlg::`vftable'
0x1400af081  mov     [rbx+48h], r15
0x1400af085  mov     [rbx], rax
0x1400af088  mov     [rbx+50h], r15
0x1400af08c  jmp     short loc_1400AF091
0x1400af08e  mov     rbx, r15
0x1400af091  mov     [rsi+58h], rbx
0x1400af095  test    rbx, rbx
0x1400af098  jnz     short loc_1400AF0ED
0x1400af09a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af0a1  lea     rax, WPP_GLOBAL_Control
0x1400af0a8  cmp     rcx, rax
0x1400af0ab  jz      short loc_1400AF0E3
0x1400af0ad  test    [rcx+1Ch], dil
0x1400af0b1  jz      short loc_1400AF0E3
0x1400af0b3  cmp     byte ptr [rcx+19h], 2
0x1400af0b7  jb      short loc_1400AF0E3
0x1400af0b9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af0be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af0c5  lea     edx, [rbx+4Bh]
0x1400af0c8  mov     r9d, eax
0x1400af0cb  mov     dword ptr [rsp+0D0h+pdwType], 8007000Eh
0x1400af0d3  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af0da  mov     rcx, [rcx+10h]
0x1400af0de  call    WPP_SF_Dd
0x1400af0e3  mov     ebx, 8007000Eh
0x1400af0e8  jmp     loc_1400AF1E9
0x1400af0ed  mov     r8, [rsi+0C0h]; unsigned __int16 *
0x1400af0f4  mov     rcx, rbx; this
0x1400af0f7  mov     rdx, [rsi+80h]; HWND
0x1400af0fe  call    ?Initialize@CShadowConnectingDlg@@QEAAJPEAUHWND__@@PEBG@Z; CShadowConnectingDlg::Initialize(HWND__ *,ushort const *)
0x1400af103  mov     ebx, eax
0x1400af105  test    eax, eax
0x1400af107  jns     short loc_1400AF16A
0x1400af109  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af110  lea     rax, WPP_GLOBAL_Control
0x1400af117  cmp     rcx, rax
0x1400af11a  jz      loc_1400AF1E9
0x1400af120  test    [rcx+1Ch], dil
0x1400af124  jz      loc_1400AF1E9
0x1400af12a  cmp     byte ptr [rcx+19h], 2
0x1400af12e  jb      loc_1400AF1E9
0x1400af134  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af139  lea     rcx, aMSpviewerIniti; "m_spViewer->Initialize failed"
0x1400af140  mov     dword ptr [rsp+0D0h+pvData], ebx
0x1400af144  mov     [rsp+0D0h+pdwType], rcx
0x1400af149  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af150  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af157  mov     edx, 4Ch ; 'L'
0x1400af15c  mov     r9d, eax
0x1400af15f  mov     rcx, [rcx+10h]
0x1400af163  call    WPP_SF_DsD
0x1400af168  jmp     short loc_1400AF1E9
0x1400af16a  mov     rcx, [rsi+58h]
0x1400af16e  mov     rax, [rcx]
0x1400af171  mov     rax, [rax+10h]
0x1400af175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400af17a  mov     [rsi+60h], rax
0x1400af17e  test    rax, rax
0x1400af181  jnz     short loc_1400AF1E9
0x1400af183  call    cs:__imp_GetLastError
0x1400af189  mov     ebx, eax
0x1400af18b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af192  lea     rax, WPP_GLOBAL_Control
0x1400af199  cmp     rcx, rax
0x1400af19c  jz      short loc_1400AF1D2
0x1400af19e  test    [rcx+1Ch], dil
0x1400af1a2  jz      short loc_1400AF1D2
0x1400af1a4  cmp     byte ptr [rcx+19h], 2
0x1400af1a8  jb      short loc_1400AF1D2
0x1400af1aa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af1af  mov     edx, 4Dh ; 'M'
0x1400af1b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af1bb  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af1c2  mov     r9d, eax
0x1400af1c5  mov     dword ptr [rsp+0D0h+pdwType], ebx
0x1400af1c9  mov     rcx, [rcx+10h]
0x1400af1cd  call    WPP_SF_Dd
0x1400af1d2  test    ebx, ebx
0x1400af1d4  jle     short loc_1400AF1E1
0x1400af1d6  movzx   ebx, bx
0x1400af1d9  or      ebx, 80070000h
0x1400af1df  test    ebx, ebx
  ... truncated ...
```
