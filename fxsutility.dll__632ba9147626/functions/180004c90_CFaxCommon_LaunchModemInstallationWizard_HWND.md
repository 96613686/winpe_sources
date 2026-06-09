# CFaxCommon::LaunchModemInstallationWizard(HWND__ *)

- ea: `0x180004c90`
- end: `0x180004e17`
- name: `?LaunchModemInstallationWizard@CFaxCommon@@UEAAJPEAUHWND__@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(CFaxCommon *this, HWND)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004c90`
- `0x180005eac`
- `0x180005ed4`
- `0x18000d6bc`
- `0x180017010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180004df7`
- `KERNEL32!FreeLibrary` at `0x180004df7`
- `KERNEL32!GetProcAddress` at `0x180004d38`
- `KERNEL32!GetProcAddress` at `0x180004d38`
- `KERNEL32!GetLastError` at `0x180004ce7`
- `KERNEL32!GetLastError` at `0x180004d6c`
- `KERNEL32!GetLastError` at `0x180004dbc`
- `KERNEL32!GetLastError` at `0x180004ce7`
- `KERNEL32!GetLastError` at `0x180004d6c`
- `KERNEL32!GetLastError` at `0x180004dbc`
- `KERNEL32!LoadLibraryW` at `0x180004cd9`
- `KERNEL32!LoadLibraryW` at `0x180004cd9`
- `USER32!EnableWindow` at `0x180004d4d`
- `USER32!EnableWindow` at `0x180004db4`
- `USER32!EnableWindow` at `0x180004d4d`
- `USER32!EnableWindow` at `0x180004db4`

## string_xrefs

- `0x180004d2e`: `InstallNewDevice`
- `0x180004d90`: `InstallNewDevice`

## pseudocode

```c
__int64 __fastcall CFaxCommon::LaunchModemInstallationWizard(CFaxCommon *this, HWND a2)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rdi
  DWORD v5; // eax
  int v6; // ebx
  FARPROC ProcAddress; // rbp
  DWORD LastError; // eax
  DWORD v9; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids);
  }
  LibraryW = LoadLibraryW(L"hdwwiz.cpl");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "InstallNewDevice");
    if ( ProcAddress )
    {
      v6 = 0;
      EnableWindow(a2, 0);
      if ( !((unsigned int (__fastcall *)(HWND, GUID *, _QWORD))ProcAddress)(a2, &GUID_DEVCLASS_MODEM, 0) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            (unsigned int)WPP_506210d4ee34309f98ba1c03a656d666_Traceguids,
            (unsigned int)L"InstallNewDevice",
            LastError);
        }
      }
      EnableWindow(a2, 1);
    }
    else
    {
      v9 = GetLastError();
      v6 = v9;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids, v9);
      }
    }
    FreeLibrary(v4);
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids, v5);
    }
  }
  if ( v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004c90  push    rbx
0x180004c92  push    rbp
0x180004c93  push    rsi
0x180004c94  push    rdi
0x180004c95  push    r15
0x180004c97  sub     rsp, 30h
0x180004c9b  mov     rsi, rdx
0x180004c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ca5  lea     r15, WPP_GLOBAL_Control
0x180004cac  cmp     rcx, r15
0x180004caf  jz      short loc_180004CD2
0x180004cb1  test    byte ptr [rcx+1Ch], 2
0x180004cb5  jz      short loc_180004CD2
0x180004cb7  cmp     byte ptr [rcx+19h], 5
0x180004cbb  jb      short loc_180004CD2
0x180004cbd  mov     rcx, [rcx+10h]
0x180004cc1  lea     r8, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x180004cc8  mov     edx, 16h
0x180004ccd  call    WPP_SF_
0x180004cd2  lea     rcx, aHdwwizCpl; "hdwwiz.cpl"
0x180004cd9  call    cs:__imp_LoadLibraryW
0x180004cdf  mov     rdi, rax
0x180004ce2  test    rax, rax
0x180004ce5  jnz     short loc_180004D2E
0x180004ce7  call    cs:__imp_GetLastError
0x180004ced  mov     ebx, eax
0x180004cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cf6  cmp     rcx, r15
0x180004cf9  jz      loc_180004DFD
0x180004cff  test    byte ptr [rcx+1Ch], 2
0x180004d03  jz      loc_180004DFD
0x180004d09  cmp     byte ptr [rcx+19h], 2
0x180004d0d  jb      loc_180004DFD
0x180004d13  mov     rcx, [rcx+10h]
0x180004d17  lea     edx, [rdi+17h]
0x180004d1a  mov     r9d, eax
0x180004d1d  lea     r8, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x180004d24  call    WPP_SF_d
0x180004d29  jmp     loc_180004DFD
0x180004d2e  lea     rdx, aInstallnewdevi_0; "InstallNewDevice"
0x180004d35  mov     rcx, rdi; hModule
0x180004d38  call    cs:__imp_GetProcAddress
0x180004d3e  mov     rbp, rax
0x180004d41  test    rax, rax
0x180004d44  jz      short loc_180004DBC
0x180004d46  xor     edx, edx; bEnable
0x180004d48  mov     rcx, rsi; hWnd
0x180004d4b  xor     ebx, ebx
0x180004d4d  call    cs:__imp_EnableWindow
0x180004d53  xor     r8d, r8d
0x180004d56  lea     rdx, GUID_DEVCLASS_MODEM
0x180004d5d  mov     rcx, rsi
0x180004d60  mov     rax, rbp
0x180004d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d68  test    eax, eax
0x180004d6a  jnz     short loc_180004DAC
0x180004d6c  call    cs:__imp_GetLastError
0x180004d72  mov     ebx, eax
0x180004d74  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d7b  cmp     rcx, r15
0x180004d7e  jz      short loc_180004DAC
0x180004d80  test    byte ptr [rcx+1Ch], 2
0x180004d84  jz      short loc_180004DAC
0x180004d86  cmp     byte ptr [rcx+19h], 2
0x180004d8a  jb      short loc_180004DAC
0x180004d8c  mov     rcx, [rcx+10h]
0x180004d90  lea     r9, aInstallnewdevi; "InstallNewDevice"
0x180004d97  mov     edx, 18h
0x180004d9c  mov     [rsp+58h+var_38], eax
0x180004da0  lea     r8, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x180004da7  call    WPP_SF_Sd
0x180004dac  mov     edx, 1; bEnable
0x180004db1  mov     rcx, rsi; hWnd
0x180004db4  call    cs:__imp_EnableWindow
0x180004dba  jmp     short loc_180004DF4
0x180004dbc  call    cs:__imp_GetLastError
0x180004dc2  mov     ebx, eax
0x180004dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dcb  cmp     rcx, r15
0x180004dce  jz      short loc_180004DF4
0x180004dd0  test    byte ptr [rcx+1Ch], 2
0x180004dd4  jz      short loc_180004DF4
0x180004dd6  cmp     byte ptr [rcx+19h], 2
0x180004dda  jb      short loc_180004DF4
0x180004ddc  mov     rcx, [rcx+10h]
0x180004de0  lea     r8, WPP_506210d4ee34309f98ba1c03a656d666_Traceguids
0x180004de7  mov     edx, 19h
0x180004dec  mov     r9d, eax
0x180004def  call    WPP_SF_d
0x180004df4  mov     rcx, rdi; hLibModule
0x180004df7  call    cs:__imp_FreeLibrary
0x180004dfd  test    ebx, ebx
0x180004dff  jle     short loc_180004E0A
0x180004e01  movzx   ebx, bx
0x180004e04  or      ebx, 80070000h
0x180004e0a  mov     eax, ebx
0x180004e0c  add     rsp, 30h
0x180004e10  pop     r15
0x180004e12  pop     rdi
0x180004e13  pop     rsi
0x180004e14  pop     rbp
0x180004e15  pop     rbx
0x180004e16  retn
```
