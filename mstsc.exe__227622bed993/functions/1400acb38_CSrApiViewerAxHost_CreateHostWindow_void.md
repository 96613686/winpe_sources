# CSrApiViewerAxHost::CreateHostWindow(void)

- ea: `0x1400acb38`
- end: `0x1400ad092`
- name: `?CreateHostWindow@CSrApiViewerAxHost@@AEAAJXZ`
- size: `1370`
- prototype: `__int64 __fastcall(CSrApiViewerAxHost *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400b0ba0`

## callees

- `0x140003b2c`
- `0x140004703`
- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400a35b8`
- `0x1400acb38`
- `0x1400b2958`
- `0x140112010`

## import_xrefs

- `USER32!LoadStringW` at `0x1400acd98`
- `USER32!LoadStringW` at `0x1400acd98`
- `USER32!GetMenuItemCount` at `0x1400acd32`
- `USER32!GetMenuItemCount` at `0x1400acd32`
- `USER32!InsertMenuItemW` at `0x1400ace25`
- `USER32!InsertMenuItemW` at `0x1400ace25`
- `USER32!GetSystemMenu` at `0x1400accdc`
- `USER32!GetSystemMenu` at `0x1400accdc`
- `USER32!LoadIconW` at `0x1400ace7b`
- `USER32!LoadIconW` at `0x1400ace7b`
- `USER32!CreateWindowExW` at `0x1400acc80`
- `USER32!CreateWindowExW` at `0x1400acc80`
- `USER32!SendMessageW` at `0x1400acedb`
- `USER32!SendMessageW` at `0x1400acedb`
- `KERNEL32!GetLastError` at `0x1400acc92`
- `KERNEL32!GetLastError` at `0x1400accea`
- `KERNEL32!GetLastError` at `0x1400acd40`
- `KERNEL32!GetLastError` at `0x1400acda2`
- `KERNEL32!GetLastError` at `0x1400ace2f`
- `KERNEL32!GetLastError` at `0x1400ace86`
- `KERNEL32!GetLastError` at `0x1400ad013`
- `KERNEL32!GetLastError` at `0x1400acc92`
- `KERNEL32!GetLastError` at `0x1400accea`
- `KERNEL32!GetLastError` at `0x1400acd40`
- `KERNEL32!GetLastError` at `0x1400acda2`
- `KERNEL32!GetLastError` at `0x1400ace2f`
- `KERNEL32!GetLastError` at `0x1400ace86`
- `KERNEL32!GetLastError` at `0x1400ad013`
- `ADVAPI32!RegGetValueW` at `0x1400acbaa`
- `ADVAPI32!RegGetValueW` at `0x1400acbaa`

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
0x1400acb38  mov     [rsp-8+arg_0], rbx
0x1400acb3d  push    rbp
0x1400acb3e  push    rsi
0x1400acb3f  push    rdi
0x1400acb40  push    r14
0x1400acb42  push    r15
0x1400acb44  lea     rbp, [rsp-37h]
0x1400acb49  sub     rsp, 0B0h
0x1400acb50  xor     r15d, r15d
0x1400acb53  mov     [rbp+57h+arg_8], 1
0x1400acb5a  mov     rsi, rcx
0x1400acb5d  mov     [rbp+57h+Buffer], r15
0x1400acb61  xor     edx, edx; Val
0x1400acb63  lea     rcx, [rbp+57h+mi]; void *
0x1400acb67  lea     edi, [r15+50h]
0x1400acb6b  mov     r8d, edi; Size
0x1400acb6e  call    memset_0
0x1400acb73  lea     rax, [rbp+57h+arg_10]
0x1400acb77  mov     [rbp+57h+arg_10], 4
0x1400acb7e  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1400acb83  lea     r9d, [r15+10h]; dwFlags
0x1400acb87  lea     rax, [rbp+57h+arg_8]
0x1400acb8b  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1400acb92  mov     [rsp+0D0h+pvData], rax; pvData
0x1400acb97  lea     r8, ?s_kszSmartSizingRegValue@CSrApiViewerAxHost@@0QBGB; "ShadowSmartSizing"
0x1400acb9e  lea     rdx, ?s_kszShadowRegKeyPath@CSrApiViewerAxHost@@0QBGB; "Software\\Microsoft\\Terminal Server Cl"...
0x1400acba5  mov     [rsp+0D0h+pdwType], r15; pdwType
0x1400acbaa  call    cs:__imp_RegGetValueW
0x1400acbb0  mov     ebx, eax
0x1400acbb2  test    eax, 0FFFFFFFDh
0x1400acbb7  jz      short loc_1400ACC2B
0x1400acbb9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400acbc0  lea     rax, WPP_GLOBAL_Control
0x1400acbc7  cmp     rcx, rax
0x1400acbca  jz      short loc_1400ACC15
0x1400acbcc  lea     edi, [r15+8]
0x1400acbd0  test    [rcx+1Ch], dil
0x1400acbd4  jz      short loc_1400ACC15
0x1400acbd6  cmp     byte ptr [rcx+19h], 2
0x1400acbda  jb      short loc_1400ACC15
0x1400acbdc  test    ebx, ebx
0x1400acbde  jg      short loc_1400ACBE4
0x1400acbe0  mov     edi, ebx
0x1400acbe2  jmp     short loc_1400ACBED
0x1400acbe4  movzx   edi, bx
0x1400acbe7  or      edi, 80070000h
0x1400acbed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400acbf2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400acbf9  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400acc00  mov     edx, 44h ; 'D'
0x1400acc05  mov     dword ptr [rsp+0D0h+pdwType], edi
0x1400acc09  mov     r9d, eax
0x1400acc0c  mov     rcx, [rcx+10h]
0x1400acc10  call    WPP_SF_Dd
0x1400acc15  test    ebx, ebx
0x1400acc17  jle     loc_1400AD079
0x1400acc1d  movzx   ebx, bx
0x1400acc20  or      ebx, 80070000h
0x1400acc26  jmp     loc_1400AD079
0x1400acc2b  cmp     [rbp+57h+arg_8], r15d
0x1400acc2f  lea     r8, pszPassword; lpWindowName
0x1400acc36  mov     [rsp+0D0h+lpParam], rsi; lpParam
0x1400acc3b  lea     rdx, ?s_kszSrApiViewerAxContainerClass@CSrApiViewerAxHost@@0QBGB; "SrApiViewerAxContainerClass"
0x1400acc42  mov     eax, r15d
0x1400acc45  mov     r9d, 0CF0000h; dwStyle
0x1400acc4b  setnz   al
0x1400acc4e  xor     ecx, ecx; dwExStyle
0x1400acc50  mov     [rsi+100h], eax
0x1400acc56  mov     rax, [rsi+0B0h]
0x1400acc5d  mov     [rsp+0D0h+hInstance], rax; hInstance
0x1400acc62  mov     [rsp+0D0h+hMenu], r15; hMenu
0x1400acc67  mov     [rsp+0D0h+hWndParent], r15; hWndParent
0x1400acc6c  mov     [rsp+0D0h+nHeight], r15d; nHeight
0x1400acc71  mov     dword ptr [rsp+0D0h+pcbData], r15d; nWidth
0x1400acc76  mov     dword ptr [rsp+0D0h+pvData], r15d; Y
0x1400acc7b  mov     dword ptr [rsp+0D0h+pdwType], r15d; X
0x1400acc80  call    cs:__imp_CreateWindowExW
0x1400acc86  mov     [rsi+80h], rax
0x1400acc8d  test    rax, rax
0x1400acc90  jnz     short loc_1400ACCD7
0x1400acc92  call    cs:__imp_GetLastError
0x1400acc98  mov     ebx, eax
0x1400acc9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400acca1  lea     rax, WPP_GLOBAL_Control
0x1400acca8  cmp     rcx, rax
0x1400accab  jz      loc_1400AD062
0x1400accb1  mov     edi, 8
0x1400accb6  test    [rcx+1Ch], dil
0x1400accba  jz      loc_1400AD062
0x1400accc0  cmp     byte ptr [rcx+19h], 2
0x1400accc4  jb      loc_1400AD062
0x1400accca  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400acccf  lea     edx, [rdi+3Dh]
0x1400accd2  jmp     loc_1400AD044
0x1400accd7  xor     edx, edx; bRevert
0x1400accd9  mov     rcx, rax; hWnd
0x1400accdc  call    cs:__imp_GetSystemMenu
0x1400acce2  mov     rbx, rax
0x1400acce5  test    rax, rax
0x1400acce8  jnz     short loc_1400ACD2F
0x1400accea  call    cs:__imp_GetLastError
0x1400accf0  mov     ebx, eax
0x1400accf2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400accf9  lea     rax, WPP_GLOBAL_Control
0x1400acd00  cmp     rcx, rax
0x1400acd03  jz      loc_1400AD062
0x1400acd09  mov     edi, 8
0x1400acd0e  test    [rcx+1Ch], dil
0x1400acd12  jz      loc_1400AD062
0x1400acd18  cmp     byte ptr [rcx+19h], 2
0x1400acd1c  jb      loc_1400AD062
0x1400acd22  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400acd27  lea     edx, [rdi+3Eh]
0x1400acd2a  jmp     loc_1400AD044
0x1400acd2f  mov     rcx, rbx; hMenu
0x1400acd32  call    cs:__imp_GetMenuItemCount
0x1400acd38  mov     r14d, eax
0x1400acd3b  cmp     eax, 1
0x1400acd3e  jge     short loc_1400ACD85
0x1400acd40  call    cs:__imp_GetLastError
0x1400acd46  mov     ebx, eax
0x1400acd48  mov     rcx, cs:WPP_GLOBAL_Control
0x1400acd4f  lea     rax, WPP_GLOBAL_Control
0x1400acd56  cmp     rcx, rax
0x1400acd59  jz      loc_1400AD062
0x1400acd5f  mov     edi, 8
0x1400acd64  test    [rcx+1Ch], dil
0x1400acd68  jz      loc_1400AD062
0x1400acd6e  cmp     byte ptr [rcx+19h], 2
0x1400acd72  jb      loc_1400AD062
0x1400acd78  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400acd7d  lea     edx, [rdi+3Fh]
0x1400acd80  jmp     loc_1400AD044
0x1400acd85  mov     rcx, [rsi+0B8h]; hInstance
0x1400acd8c  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1400acd90  xor     r9d, r9d; cchBufferMax
0x1400acd93  mov     edx, 0BC9h; uID
0x1400acd98  call    cs:__imp_LoadStringW
0x1400acd9e  test    eax, eax
0x1400acda0  jnz     short loc_1400ACDE7
0x1400acda2  call    cs:__imp_GetLastError
0x1400acda8  mov     ebx, eax
0x1400acdaa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400acdb1  lea     rax, WPP_GLOBAL_Control
0x1400acdb8  cmp     rcx, rax
0x1400acdbb  jz      loc_1400AD062
0x1400acdc1  mov     edi, 8
0x1400acdc6  test    [rcx+1Ch], dil
0x1400acdca  jz      loc_1400AD062
0x1400acdd0  cmp     byte ptr [rcx+19h], 2
0x1400acdd4  jb      loc_1400AD062
0x1400acdda  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400acddf  lea     edx, [rdi+40h]
0x1400acde2  jmp     loc_1400AD044
0x1400acde7  cmp     [rsi+100h], r15d
0x1400acdee  lea     edx, [r14-1]; item
0x1400acdf2  mov     [rbp+57h+mi.cbSize], edi
0x1400acdf5  lea     r9, [rbp+57h+mi]; lpmi
0x1400acdf9  mov     edi, 8
0x1400acdfe  mov     qword ptr [rbp+57h+mi.fMask], 43h ; 'C'
0x1400ace06  mov     eax, r15d
0x1400ace09  mov     [rbp+57h+mi.wID], 10h
0x1400ace10  cmovnz  eax, edi
0x1400ace13  mov     rcx, rbx; hmenu
0x1400ace16  mov     [rbp+57h+mi.fState], eax
0x1400ace19  mov     rax, [rbp+57h+Buffer]
0x1400ace1d  lea     r8d, [rdi-7]; fByPosition
0x1400ace21  mov     [rbp+57h+mi.dwTypeData], rax
0x1400ace25  call    cs:__imp_InsertMenuItemW
0x1400ace2b  test    eax, eax
0x1400ace2d  jnz     short loc_1400ACE6F
0x1400ace2f  call    cs:__imp_GetLastError
0x1400ace35  mov     ebx, eax
0x1400ace37  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ace3e  lea     rax, WPP_GLOBAL_Control
0x1400ace45  cmp     rcx, rax
0x1400ace48  jz      loc_1400AD062
0x1400ace4e  test    [rcx+1Ch], dil
0x1400ace52  jz      loc_1400AD062
0x1400ace58  cmp     byte ptr [rcx+19h], 2
0x1400ace5c  jb      loc_1400AD062
0x1400ace62  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ace67  lea     edx, [rdi+41h]
0x1400ace6a  jmp     loc_1400AD044
0x1400ace6f  mov     rcx, [rsi+0B0h]; hInstance
0x1400ace76  mov     edx, 65h ; 'e'; lpIconName
0x1400ace7b  call    cs:__imp_LoadIconW
0x1400ace81  test    rax, rax
0x1400ace84  jnz     short loc_1400ACEC8
0x1400ace86  call    cs:__imp_GetLastError
0x1400ace8c  mov     ebx, eax
0x1400ace8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ace95  lea     rax, WPP_GLOBAL_Control
0x1400ace9c  cmp     rcx, rax
0x1400ace9f  jz      loc_1400AD062
0x1400acea5  test    [rcx+1Ch], dil
0x1400acea9  jz      loc_1400AD062
0x1400aceaf  cmp     byte ptr [rcx+19h], 2
0x1400aceb3  jb      loc_1400AD062
0x1400aceb9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400acebe  mov     edx, 4Ah ; 'J'
0x1400acec3  jmp     loc_1400AD044
0x1400acec8  mov     rcx, [rsi+80h]; hWnd
0x1400acecf  mov     edx, 80h; Msg
0x1400aced4  mov     r9, rax; lParam
0x1400aced7  lea     r8d, [rdx-7Fh]; wParam
0x1400acedb  call    cs:__imp_SendMessageW
0x1400acee1  mov     ecx, 58h ; 'X'; Size
0x1400acee6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400aceeb  mov     rbx, rax
0x1400aceee  test    rax, rax
0x1400acef1  jz      short loc_1400ACF1E
0x1400acef3  mov     r8, [rsi+0B0h]; HINSTANCE
0x1400acefa  mov     r9d, 19Ah; int
0x1400acf00  xor     edx, edx; HWND
0x1400acf02  mov     rcx, rax; this
0x1400acf05  call    ??0CDlgBase@@QEAA@PEAUHWND__@@PEAUHINSTANCE__@@H@Z; CDlgBase::CDlgBase(HWND__ *,HINSTANCE__ *,int)
0x1400acf0a  lea     rax, ??_7CShadowConnectingDlg@@6B@; const CShadowConnectingDlg::`vftable'
0x1400acf11  mov     [rbx+48h], r15
0x1400acf15  mov     [rbx], rax
0x1400acf18  mov     [rbx+50h], r15
0x1400acf1c  jmp     short loc_1400ACF21
0x1400acf1e  mov     rbx, r15
0x1400acf21  mov     [rsi+58h], rbx
0x1400acf25  test    rbx, rbx
0x1400acf28  jnz     short loc_1400ACF7D
0x1400acf2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400acf31  lea     rax, WPP_GLOBAL_Control
0x1400acf38  cmp     rcx, rax
0x1400acf3b  jz      short loc_1400ACF73
0x1400acf3d  test    [rcx+1Ch], dil
0x1400acf41  jz      short loc_1400ACF73
0x1400acf43  cmp     byte ptr [rcx+19h], 2
0x1400acf47  jb      short loc_1400ACF73
0x1400acf49  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400acf4e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400acf55  lea     edx, [rbx+4Bh]
0x1400acf58  mov     r9d, eax
0x1400acf5b  mov     dword ptr [rsp+0D0h+pdwType], 8007000Eh
0x1400acf63  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400acf6a  mov     rcx, [rcx+10h]
0x1400acf6e  call    WPP_SF_Dd
0x1400acf73  mov     ebx, 8007000Eh
0x1400acf78  jmp     loc_1400AD079
0x1400acf7d  mov     r8, [rsi+0C0h]; unsigned __int16 *
0x1400acf84  mov     rcx, rbx; this
0x1400acf87  mov     rdx, [rsi+80h]; HWND
0x1400acf8e  call    ?Initialize@CShadowConnectingDlg@@QEAAJPEAUHWND__@@PEBG@Z; CShadowConnectingDlg::Initialize(HWND__ *,ushort const *)
0x1400acf93  mov     ebx, eax
0x1400acf95  test    eax, eax
0x1400acf97  jns     short loc_1400ACFFA
0x1400acf99  mov     rcx, cs:WPP_GLOBAL_Control
0x1400acfa0  lea     rax, WPP_GLOBAL_Control
0x1400acfa7  cmp     rcx, rax
0x1400acfaa  jz      loc_1400AD079
0x1400acfb0  test    [rcx+1Ch], dil
0x1400acfb4  jz      loc_1400AD079
0x1400acfba  cmp     byte ptr [rcx+19h], 2
0x1400acfbe  jb      loc_1400AD079
0x1400acfc4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400acfc9  lea     rcx, aMSpviewerIniti; "m_spViewer->Initialize failed"
0x1400acfd0  mov     dword ptr [rsp+0D0h+pvData], ebx
0x1400acfd4  mov     [rsp+0D0h+pdwType], rcx
0x1400acfd9  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400acfe0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400acfe7  mov     edx, 4Ch ; 'L'
0x1400acfec  mov     r9d, eax
0x1400acfef  mov     rcx, [rcx+10h]
0x1400acff3  call    WPP_SF_DsD
0x1400acff8  jmp     short loc_1400AD079
0x1400acffa  mov     rcx, [rsi+58h]
0x1400acffe  mov     rax, [rcx]
0x1400ad001  mov     rax, [rax+10h]
0x1400ad005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400ad00a  mov     [rsi+60h], rax
0x1400ad00e  test    rax, rax
0x1400ad011  jnz     short loc_1400AD079
0x1400ad013  call    cs:__imp_GetLastError
0x1400ad019  mov     ebx, eax
0x1400ad01b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad022  lea     rax, WPP_GLOBAL_Control
0x1400ad029  cmp     rcx, rax
0x1400ad02c  jz      short loc_1400AD062
0x1400ad02e  test    [rcx+1Ch], dil
0x1400ad032  jz      short loc_1400AD062
0x1400ad034  cmp     byte ptr [rcx+19h], 2
0x1400ad038  jb      short loc_1400AD062
0x1400ad03a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400ad03f  mov     edx, 4Dh ; 'M'
0x1400ad044  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ad04b  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400ad052  mov     r9d, eax
0x1400ad055  mov     dword ptr [rsp+0D0h+pdwType], ebx
0x1400ad059  mov     rcx, [rcx+10h]
0x1400ad05d  call    WPP_SF_Dd
0x1400ad062  test    ebx, ebx
0x1400ad064  jle     short loc_1400AD071
0x1400ad066  movzx   ebx, bx
0x1400ad069  or      ebx, 80070000h
0x1400ad06f  test    ebx, ebx
  ... truncated ...
```
