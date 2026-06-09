# CSrApiViewerAxHost::OnSysCommand(HWND__ *,uint,unsigned __int64,__int64,__int64 *)

- ea: `0x1400b18b8`
- end: `0x1400b1be0`
- name: `?OnSysCommand@CSrApiViewerAxHost@@AEAAJPEAUHWND__@@I_K_JPEA_J@Z`
- size: `808`
- prototype: `__int64 __fastcall(CSrApiViewerAxHost *__hidden this, HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400ae724`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400ae018`
- `0x1400b18b8`
- `0x140114010`

## import_xrefs

- `USER32!CheckMenuItem` at `0x1400b1999`
- `USER32!CheckMenuItem` at `0x1400b1999`
- `USER32!GetSystemMenu` at `0x1400b190c`
- `USER32!GetSystemMenu` at `0x1400b190c`
- `USER32!DefWindowProcW` at `0x1400b1bb1`
- `USER32!DefWindowProcW` at `0x1400b1bb1`
- `KERNEL32!GetLastError` at `0x1400b191a`
- `KERNEL32!GetLastError` at `0x1400b191a`
- `ADVAPI32!RegCreateKeyExW` at `0x1400b1ab1`
- `ADVAPI32!RegCreateKeyExW` at `0x1400b1ab1`
- `ADVAPI32!RegSetValueExW` at `0x1400b1b52`
- `ADVAPI32!RegSetValueExW` at `0x1400b1b52`
- `ADVAPI32!RegCloseKey` at `0x1400b1bc4`
- `ADVAPI32!RegCloseKey` at `0x1400b1bc4`

## pseudocode

```c
__int64 __fastcall CSrApiViewerAxHost::OnSysCommand(
        CSrApiViewerAxHost *this,
        HWND hWnd,
        UINT Msg,
        WPARAM wParam,
        LPARAM lParam,
        __int64 *a6)
{
  LRESULT v7; // rbp
  HMENU SystemMenu; // rcx
  signed int LastError; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v13; // edx
  const char *v14; // rcx
  LSTATUS v15; // edi
  unsigned int v16; // ebx
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 result; // rax
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  int Data; // [rsp+A8h] [rbp+20h] BYREF

  Data = 0;
  hKey = 0;
  if ( (wParam & 0xFFF0) != 0x10 )
  {
    LastError = 0;
    v7 = DefWindowProcW(hWnd, Msg, wParam, lParam);
    goto LABEL_44;
  }
  v7 = 0;
  *((_DWORD *)this + 64) = *((_DWORD *)this + 64) == 0;
  SystemMenu = GetSystemMenu(*((HWND *)this + 16), 0);
  if ( SystemMenu )
  {
    CheckMenuItem(SystemMenu, 0x10u, *((_DWORD *)this + 64) != 0 ? 8 : 0);
    LOWORD(v11) = -(*((_DWORD *)this + 64) != 0);
    LastError = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 9) + 104LL))(
                  *((_QWORD *)this + 9),
                  v11);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 167;
      v14 = "put_SmartSizing failed";
      goto LABEL_17;
    }
    LastError = CSrApiViewerAxHost::AdjustControlSize(this);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_44;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 168;
      v14 = "AdjustControlSize failed";
LABEL_17:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)&WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v14,
        LastError);
      goto LABEL_44;
    }
    Data = *((_DWORD *)this + 64);
    v15 = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Terminal Server Client",
            0,
            0,
            0,
            0x20006u,
            0,
            &hKey,
            0);
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      else
        v16 = v15;
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v18 = 169;
    }
    else
    {
      v15 = RegSetValueExW(hKey, L"ShadowSmartSizing", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !v15 )
        goto LABEL_44;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      else
        v16 = v15;
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v18 = 170;
    }
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids, v17, v16);
LABEL_32:
    if ( v15 > 0 )
      LastError = (unsigned __int16)v15 | 0x80070000;
    else
      LastError = v15;
    goto LABEL_44;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      166,
      &WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids,
      v10,
      LastError);
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    LastError = -2147467259;
LABEL_44:
  if ( hKey )
    RegCloseKey(hKey);
  result = (unsigned int)LastError;
  *a6 = v7;
  return result;
}

```

## disassembly

```asm
0x1400b18b8  mov     rax, rsp
0x1400b18bb  push    rbx
0x1400b18bc  push    rbp
0x1400b18bd  push    rsi
0x1400b18be  push    rdi
0x1400b18bf  sub     rsp, 68h
0x1400b18c3  mov     dword ptr [rax+20h], 0
0x1400b18ca  mov     r10, r9
0x1400b18cd  mov     qword ptr [rax-38h], 0
0x1400b18d5  mov     r11d, r8d
0x1400b18d8  mov     rax, r9
0x1400b18db  mov     rsi, rdx
0x1400b18de  and     eax, 0FFF0h
0x1400b18e3  mov     rdi, rcx
0x1400b18e6  cmp     rax, 10h
0x1400b18ea  jnz     loc_1400B1B9E
0x1400b18f0  xor     eax, eax
0x1400b18f2  xor     ebp, ebp
0x1400b18f4  cmp     [rcx+100h], eax
0x1400b18fa  setz    al
0x1400b18fd  xor     edx, edx; bRevert
0x1400b18ff  mov     [rcx+100h], eax
0x1400b1905  mov     rcx, [rcx+80h]; hWnd
0x1400b190c  call    cs:__imp_GetSystemMenu
0x1400b1912  mov     rcx, rax; hMenu
0x1400b1915  test    rax, rax
0x1400b1918  jnz     short loc_1400B1985
0x1400b191a  call    cs:__imp_GetLastError
0x1400b1920  mov     ebx, eax
0x1400b1922  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1929  lea     rax, WPP_GLOBAL_Control
0x1400b1930  cmp     rcx, rax
0x1400b1933  jz      short loc_1400B1969
0x1400b1935  test    byte ptr [rcx+1Ch], 8
0x1400b1939  jz      short loc_1400B1969
0x1400b193b  cmp     byte ptr [rcx+19h], 2
0x1400b193f  jb      short loc_1400B1969
0x1400b1941  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b1946  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b194d  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b1954  mov     edx, 0A6h
0x1400b1959  mov     [rsp+88h+dwOptions], ebx
0x1400b195d  mov     r9d, eax
0x1400b1960  mov     rcx, [rcx+10h]
0x1400b1964  call    WPP_SF_Dd
0x1400b1969  test    ebx, ebx
0x1400b196b  jle     short loc_1400B1976
0x1400b196d  movzx   ebx, bx
0x1400b1970  or      ebx, 80070000h
0x1400b1976  test    ebx, ebx
0x1400b1978  mov     eax, 80004005h
0x1400b197d  cmovns  ebx, eax
0x1400b1980  jmp     loc_1400B1BBA
0x1400b1985  mov     eax, [rdi+100h]
0x1400b198b  mov     edx, 10h; uIDCheckItem
0x1400b1990  neg     eax
0x1400b1992  sbb     r8d, r8d
0x1400b1995  and     r8d, 8; uCheck
0x1400b1999  call    cs:__imp_CheckMenuItem
0x1400b199f  mov     eax, [rdi+100h]
0x1400b19a5  mov     rcx, [rdi+48h]
0x1400b19a9  neg     eax
0x1400b19ab  sbb     dx, dx
0x1400b19ae  mov     r8, [rcx]
0x1400b19b1  mov     rax, [r8+68h]
0x1400b19b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400b19ba  mov     ebx, eax
0x1400b19bc  test    eax, eax
0x1400b19be  jns     short loc_1400B1A24
0x1400b19c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b19c7  lea     rax, WPP_GLOBAL_Control
0x1400b19ce  cmp     rcx, rax
0x1400b19d1  jz      loc_1400B1BBA
0x1400b19d7  test    byte ptr [rcx+1Ch], 8
0x1400b19db  jz      loc_1400B1BBA
0x1400b19e1  cmp     byte ptr [rcx+19h], 2
0x1400b19e5  jb      loc_1400B1BBA
0x1400b19eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b19f0  mov     edx, 0A7h
0x1400b19f5  lea     rcx, aPutSmartsizing_0; "put_SmartSizing failed"
0x1400b19fc  mov     [rsp+88h+samDesired], ebx
0x1400b1a00  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b1a07  mov     qword ptr [rsp+88h+dwOptions], rcx
0x1400b1a0c  mov     r9d, eax
0x1400b1a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1a16  mov     rcx, [rcx+10h]
0x1400b1a1a  call    WPP_SF_DsD
0x1400b1a1f  jmp     loc_1400B1BBA
0x1400b1a24  mov     rcx, rdi; this
0x1400b1a27  call    ?AdjustControlSize@CSrApiViewerAxHost@@AEAAJXZ; CSrApiViewerAxHost::AdjustControlSize(void)
0x1400b1a2c  mov     ebx, eax
0x1400b1a2e  test    eax, eax
0x1400b1a30  jns     short loc_1400B1A70
0x1400b1a32  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1a39  lea     rax, WPP_GLOBAL_Control
0x1400b1a40  cmp     rcx, rax
0x1400b1a43  jz      loc_1400B1BBA
0x1400b1a49  test    byte ptr [rcx+1Ch], 8
0x1400b1a4d  jz      loc_1400B1BBA
0x1400b1a53  cmp     byte ptr [rcx+19h], 2
0x1400b1a57  jb      loc_1400B1BBA
0x1400b1a5d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b1a62  mov     edx, 0A8h
0x1400b1a67  lea     rcx, aAdjustcontrols; "AdjustControlSize failed"
0x1400b1a6e  jmp     short loc_1400B19FC
0x1400b1a70  mov     eax, [rdi+100h]
0x1400b1a76  lea     rdx, ?s_kszShadowRegKeyPath@CSrApiViewerAxHost@@0QBGB; "Software\\Microsoft\\Terminal Server Cl"...
0x1400b1a7d  mov     [rsp+88h+lpdwDisposition], rbp; lpdwDisposition
0x1400b1a82  xor     r9d, r9d; lpClass
0x1400b1a85  mov     [rsp+88h+Data], eax
0x1400b1a8c  xor     r8d, r8d; Reserved
0x1400b1a8f  lea     rax, [rsp+88h+hKey]
0x1400b1a94  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400b1a9b  mov     [rsp+88h+phkResult], rax; phkResult
0x1400b1aa0  mov     [rsp+88h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1400b1aa5  mov     [rsp+88h+samDesired], 20006h; samDesired
0x1400b1aad  mov     [rsp+88h+dwOptions], ebp; dwOptions
0x1400b1ab1  call    cs:__imp_RegCreateKeyExW
0x1400b1ab7  mov     edi, eax
0x1400b1ab9  test    eax, eax
0x1400b1abb  jz      short loc_1400B1B2B
0x1400b1abd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1ac4  lea     rax, WPP_GLOBAL_Control
0x1400b1acb  mov     esi, 80070000h
0x1400b1ad0  cmp     rcx, rax
0x1400b1ad3  jz      short loc_1400B1B16
0x1400b1ad5  test    byte ptr [rcx+1Ch], 8
0x1400b1ad9  jz      short loc_1400B1B16
0x1400b1adb  cmp     byte ptr [rcx+19h], 2
0x1400b1adf  jb      short loc_1400B1B16
0x1400b1ae1  test    edi, edi
0x1400b1ae3  jg      short loc_1400B1AE9
0x1400b1ae5  mov     ebx, edi
0x1400b1ae7  jmp     short loc_1400B1AEE
0x1400b1ae9  movzx   ebx, di
0x1400b1aec  or      ebx, esi
0x1400b1aee  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b1af3  mov     edx, 0A9h
0x1400b1af8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1aff  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400b1b06  mov     r9d, eax
0x1400b1b09  mov     [rsp+88h+dwOptions], ebx
0x1400b1b0d  mov     rcx, [rcx+10h]
0x1400b1b11  call    WPP_SF_Dd
0x1400b1b16  test    edi, edi
0x1400b1b18  jg      short loc_1400B1B21
0x1400b1b1a  mov     ebx, edi
0x1400b1b1c  jmp     loc_1400B1BBA
0x1400b1b21  movzx   ebx, di
0x1400b1b24  or      ebx, esi
0x1400b1b26  jmp     loc_1400B1BBA
0x1400b1b2b  mov     rcx, [rsp+88h+hKey]; hKey
0x1400b1b30  lea     rax, [rsp+88h+Data]
0x1400b1b38  mov     r9d, 4; dwType
0x1400b1b3e  lea     rdx, ?s_kszSmartSizingRegValue@CSrApiViewerAxHost@@0QBGB; "ShadowSmartSizing"
0x1400b1b45  mov     [rsp+88h+samDesired], r9d; cbData
0x1400b1b4a  xor     r8d, r8d; Reserved
0x1400b1b4d  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x1400b1b52  call    cs:__imp_RegSetValueExW
0x1400b1b58  mov     edi, eax
0x1400b1b5a  test    eax, eax
0x1400b1b5c  jz      short loc_1400B1BBA
0x1400b1b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1b65  lea     rax, WPP_GLOBAL_Control
0x1400b1b6c  mov     esi, 80070000h
0x1400b1b71  cmp     rcx, rax
0x1400b1b74  jz      short loc_1400B1B16
0x1400b1b76  test    byte ptr [rcx+1Ch], 8
0x1400b1b7a  jz      short loc_1400B1B16
0x1400b1b7c  cmp     byte ptr [rcx+19h], 2
0x1400b1b80  jb      short loc_1400B1B16
0x1400b1b82  test    edi, edi
0x1400b1b84  jg      short loc_1400B1B8A
0x1400b1b86  mov     ebx, edi
0x1400b1b88  jmp     short loc_1400B1B8F
0x1400b1b8a  movzx   ebx, di
0x1400b1b8d  or      ebx, esi
0x1400b1b8f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400b1b94  mov     edx, 0AAh
0x1400b1b99  jmp     loc_1400B1AF8
0x1400b1b9e  mov     r9, [rsp+88h+lParam]; lParam
0x1400b1ba6  xor     ebx, ebx
0x1400b1ba8  mov     r8, r10; wParam
0x1400b1bab  mov     edx, r11d; Msg
0x1400b1bae  mov     rcx, rsi; hWnd
0x1400b1bb1  call    cs:__imp_DefWindowProcW
0x1400b1bb7  mov     rbp, rax
0x1400b1bba  mov     rcx, [rsp+88h+hKey]; hKey
0x1400b1bbf  test    rcx, rcx
0x1400b1bc2  jz      short loc_1400B1BCA
0x1400b1bc4  call    cs:__imp_RegCloseKey
0x1400b1bca  mov     rcx, [rsp+88h+arg_28]
0x1400b1bd2  mov     eax, ebx
0x1400b1bd4  mov     [rcx], rbp
0x1400b1bd7  add     rsp, 68h
0x1400b1bdb  pop     rdi
0x1400b1bdc  pop     rsi
0x1400b1bdd  pop     rbp
0x1400b1bde  pop     rbx
0x1400b1bdf  retn
```
