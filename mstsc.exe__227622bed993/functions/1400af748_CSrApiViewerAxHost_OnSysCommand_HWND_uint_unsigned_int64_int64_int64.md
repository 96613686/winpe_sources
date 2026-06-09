# CSrApiViewerAxHost::OnSysCommand(HWND__ *,uint,unsigned __int64,__int64,__int64 *)

- ea: `0x1400af748`
- end: `0x1400afa70`
- name: `?OnSysCommand@CSrApiViewerAxHost@@AEAAJPEAUHWND__@@I_K_JPEA_J@Z`
- size: `808`
- prototype: `__int64 __fastcall(CSrApiViewerAxHost *__hidden this, HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400ac5b4`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400abea8`
- `0x1400af748`
- `0x140112010`

## import_xrefs

- `USER32!CheckMenuItem` at `0x1400af829`
- `USER32!CheckMenuItem` at `0x1400af829`
- `USER32!GetSystemMenu` at `0x1400af79c`
- `USER32!GetSystemMenu` at `0x1400af79c`
- `USER32!DefWindowProcW` at `0x1400afa41`
- `USER32!DefWindowProcW` at `0x1400afa41`
- `KERNEL32!GetLastError` at `0x1400af7aa`
- `KERNEL32!GetLastError` at `0x1400af7aa`
- `ADVAPI32!RegCreateKeyExW` at `0x1400af941`
- `ADVAPI32!RegCreateKeyExW` at `0x1400af941`
- `ADVAPI32!RegSetValueExW` at `0x1400af9e2`
- `ADVAPI32!RegSetValueExW` at `0x1400af9e2`
- `ADVAPI32!RegCloseKey` at `0x1400afa54`
- `ADVAPI32!RegCloseKey` at `0x1400afa54`

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
0x1400af748  mov     rax, rsp
0x1400af74b  push    rbx
0x1400af74c  push    rbp
0x1400af74d  push    rsi
0x1400af74e  push    rdi
0x1400af74f  sub     rsp, 68h
0x1400af753  mov     dword ptr [rax+20h], 0
0x1400af75a  mov     r10, r9
0x1400af75d  mov     qword ptr [rax-38h], 0
0x1400af765  mov     r11d, r8d
0x1400af768  mov     rax, r9
0x1400af76b  mov     rsi, rdx
0x1400af76e  and     eax, 0FFF0h
0x1400af773  mov     rdi, rcx
0x1400af776  cmp     rax, 10h
0x1400af77a  jnz     loc_1400AFA2E
0x1400af780  xor     eax, eax
0x1400af782  xor     ebp, ebp
0x1400af784  cmp     [rcx+100h], eax
0x1400af78a  setz    al
0x1400af78d  xor     edx, edx; bRevert
0x1400af78f  mov     [rcx+100h], eax
0x1400af795  mov     rcx, [rcx+80h]; hWnd
0x1400af79c  call    cs:__imp_GetSystemMenu
0x1400af7a2  mov     rcx, rax; hMenu
0x1400af7a5  test    rax, rax
0x1400af7a8  jnz     short loc_1400AF815
0x1400af7aa  call    cs:__imp_GetLastError
0x1400af7b0  mov     ebx, eax
0x1400af7b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af7b9  lea     rax, WPP_GLOBAL_Control
0x1400af7c0  cmp     rcx, rax
0x1400af7c3  jz      short loc_1400AF7F9
0x1400af7c5  test    byte ptr [rcx+1Ch], 8
0x1400af7c9  jz      short loc_1400AF7F9
0x1400af7cb  cmp     byte ptr [rcx+19h], 2
0x1400af7cf  jb      short loc_1400AF7F9
0x1400af7d1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af7d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af7dd  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af7e4  mov     edx, 0A6h
0x1400af7e9  mov     [rsp+88h+dwOptions], ebx
0x1400af7ed  mov     r9d, eax
0x1400af7f0  mov     rcx, [rcx+10h]
0x1400af7f4  call    WPP_SF_Dd
0x1400af7f9  test    ebx, ebx
0x1400af7fb  jle     short loc_1400AF806
0x1400af7fd  movzx   ebx, bx
0x1400af800  or      ebx, 80070000h
0x1400af806  test    ebx, ebx
0x1400af808  mov     eax, 80004005h
0x1400af80d  cmovns  ebx, eax
0x1400af810  jmp     loc_1400AFA4A
0x1400af815  mov     eax, [rdi+100h]
0x1400af81b  mov     edx, 10h; uIDCheckItem
0x1400af820  neg     eax
0x1400af822  sbb     r8d, r8d
0x1400af825  and     r8d, 8; uCheck
0x1400af829  call    cs:__imp_CheckMenuItem
0x1400af82f  mov     eax, [rdi+100h]
0x1400af835  mov     rcx, [rdi+48h]
0x1400af839  neg     eax
0x1400af83b  sbb     dx, dx
0x1400af83e  mov     r8, [rcx]
0x1400af841  mov     rax, [r8+68h]
0x1400af845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400af84a  mov     ebx, eax
0x1400af84c  test    eax, eax
0x1400af84e  jns     short loc_1400AF8B4
0x1400af850  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af857  lea     rax, WPP_GLOBAL_Control
0x1400af85e  cmp     rcx, rax
0x1400af861  jz      loc_1400AFA4A
0x1400af867  test    byte ptr [rcx+1Ch], 8
0x1400af86b  jz      loc_1400AFA4A
0x1400af871  cmp     byte ptr [rcx+19h], 2
0x1400af875  jb      loc_1400AFA4A
0x1400af87b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af880  mov     edx, 0A7h
0x1400af885  lea     rcx, aPutSmartsizing_0; "put_SmartSizing failed"
0x1400af88c  mov     [rsp+88h+samDesired], ebx
0x1400af890  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af897  mov     qword ptr [rsp+88h+dwOptions], rcx
0x1400af89c  mov     r9d, eax
0x1400af89f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af8a6  mov     rcx, [rcx+10h]
0x1400af8aa  call    WPP_SF_DsD
0x1400af8af  jmp     loc_1400AFA4A
0x1400af8b4  mov     rcx, rdi; this
0x1400af8b7  call    ?AdjustControlSize@CSrApiViewerAxHost@@AEAAJXZ; CSrApiViewerAxHost::AdjustControlSize(void)
0x1400af8bc  mov     ebx, eax
0x1400af8be  test    eax, eax
0x1400af8c0  jns     short loc_1400AF900
0x1400af8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af8c9  lea     rax, WPP_GLOBAL_Control
0x1400af8d0  cmp     rcx, rax
0x1400af8d3  jz      loc_1400AFA4A
0x1400af8d9  test    byte ptr [rcx+1Ch], 8
0x1400af8dd  jz      loc_1400AFA4A
0x1400af8e3  cmp     byte ptr [rcx+19h], 2
0x1400af8e7  jb      loc_1400AFA4A
0x1400af8ed  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af8f2  mov     edx, 0A8h
0x1400af8f7  lea     rcx, aAdjustcontrols; "AdjustControlSize failed"
0x1400af8fe  jmp     short loc_1400AF88C
0x1400af900  mov     eax, [rdi+100h]
0x1400af906  lea     rdx, ?s_kszShadowRegKeyPath@CSrApiViewerAxHost@@0QBGB; "Software\\Microsoft\\Terminal Server Cl"...
0x1400af90d  mov     [rsp+88h+lpdwDisposition], rbp; lpdwDisposition
0x1400af912  xor     r9d, r9d; lpClass
0x1400af915  mov     [rsp+88h+Data], eax
0x1400af91c  xor     r8d, r8d; Reserved
0x1400af91f  lea     rax, [rsp+88h+hKey]
0x1400af924  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1400af92b  mov     [rsp+88h+phkResult], rax; phkResult
0x1400af930  mov     [rsp+88h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x1400af935  mov     [rsp+88h+samDesired], 20006h; samDesired
0x1400af93d  mov     [rsp+88h+dwOptions], ebp; dwOptions
0x1400af941  call    cs:__imp_RegCreateKeyExW
0x1400af947  mov     edi, eax
0x1400af949  test    eax, eax
0x1400af94b  jz      short loc_1400AF9BB
0x1400af94d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af954  lea     rax, WPP_GLOBAL_Control
0x1400af95b  mov     esi, 80070000h
0x1400af960  cmp     rcx, rax
0x1400af963  jz      short loc_1400AF9A6
0x1400af965  test    byte ptr [rcx+1Ch], 8
0x1400af969  jz      short loc_1400AF9A6
0x1400af96b  cmp     byte ptr [rcx+19h], 2
0x1400af96f  jb      short loc_1400AF9A6
0x1400af971  test    edi, edi
0x1400af973  jg      short loc_1400AF979
0x1400af975  mov     ebx, edi
0x1400af977  jmp     short loc_1400AF97E
0x1400af979  movzx   ebx, di
0x1400af97c  or      ebx, esi
0x1400af97e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400af983  mov     edx, 0A9h
0x1400af988  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af98f  lea     r8, WPP_65f74ffed3c832d7acdcacb7c7303db9_Traceguids
0x1400af996  mov     r9d, eax
0x1400af999  mov     [rsp+88h+dwOptions], ebx
0x1400af99d  mov     rcx, [rcx+10h]
0x1400af9a1  call    WPP_SF_Dd
0x1400af9a6  test    edi, edi
0x1400af9a8  jg      short loc_1400AF9B1
0x1400af9aa  mov     ebx, edi
0x1400af9ac  jmp     loc_1400AFA4A
0x1400af9b1  movzx   ebx, di
0x1400af9b4  or      ebx, esi
0x1400af9b6  jmp     loc_1400AFA4A
0x1400af9bb  mov     rcx, [rsp+88h+hKey]; hKey
0x1400af9c0  lea     rax, [rsp+88h+Data]
0x1400af9c8  mov     r9d, 4; dwType
0x1400af9ce  lea     rdx, ?s_kszSmartSizingRegValue@CSrApiViewerAxHost@@0QBGB; "ShadowSmartSizing"
0x1400af9d5  mov     [rsp+88h+samDesired], r9d; cbData
0x1400af9da  xor     r8d, r8d; Reserved
0x1400af9dd  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x1400af9e2  call    cs:__imp_RegSetValueExW
0x1400af9e8  mov     edi, eax
0x1400af9ea  test    eax, eax
0x1400af9ec  jz      short loc_1400AFA4A
0x1400af9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af9f5  lea     rax, WPP_GLOBAL_Control
0x1400af9fc  mov     esi, 80070000h
0x1400afa01  cmp     rcx, rax
0x1400afa04  jz      short loc_1400AF9A6
0x1400afa06  test    byte ptr [rcx+1Ch], 8
0x1400afa0a  jz      short loc_1400AF9A6
0x1400afa0c  cmp     byte ptr [rcx+19h], 2
0x1400afa10  jb      short loc_1400AF9A6
0x1400afa12  test    edi, edi
0x1400afa14  jg      short loc_1400AFA1A
0x1400afa16  mov     ebx, edi
0x1400afa18  jmp     short loc_1400AFA1F
0x1400afa1a  movzx   ebx, di
0x1400afa1d  or      ebx, esi
0x1400afa1f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400afa24  mov     edx, 0AAh
0x1400afa29  jmp     loc_1400AF988
0x1400afa2e  mov     r9, [rsp+88h+lParam]; lParam
0x1400afa36  xor     ebx, ebx
0x1400afa38  mov     r8, r10; wParam
0x1400afa3b  mov     edx, r11d; Msg
0x1400afa3e  mov     rcx, rsi; hWnd
0x1400afa41  call    cs:__imp_DefWindowProcW
0x1400afa47  mov     rbp, rax
0x1400afa4a  mov     rcx, [rsp+88h+hKey]; hKey
0x1400afa4f  test    rcx, rcx
0x1400afa52  jz      short loc_1400AFA5A
0x1400afa54  call    cs:__imp_RegCloseKey
0x1400afa5a  mov     rcx, [rsp+88h+arg_28]
0x1400afa62  mov     eax, ebx
0x1400afa64  mov     [rcx], rbp
0x1400afa67  add     rsp, 68h
0x1400afa6b  pop     rdi
0x1400afa6c  pop     rsi
0x1400afa6d  pop     rbp
0x1400afa6e  pop     rbx
0x1400afa6f  retn
```
