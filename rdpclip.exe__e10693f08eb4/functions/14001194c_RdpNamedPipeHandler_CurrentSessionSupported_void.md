# RdpNamedPipeHandler::CurrentSessionSupported(void)

- ea: `0x14001194c`
- end: `0x140011cdb`
- name: `?CurrentSessionSupported@RdpNamedPipeHandler@@AEAA_NXZ`
- size: `911`
- prototype: `bool __fastcall(RdpNamedPipeHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140011fd0`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x14001194c`
- `0x1400121f8`
- `0x14006a120`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140011c49`
- `msvcrt!_wcsicmp` at `0x140011c49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400119bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400119bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011cb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011cb9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011b03`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011b03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011b3b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140011b3b`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x140011a39`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x140011a39`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400119b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1400119b3`
- `WTSAPI32!WTSFreeMemory` at `0x140011ca9`
- `WTSAPI32!WTSFreeMemory` at `0x140011ca9`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140011bf9`
- `WTSAPI32!WTSQuerySessionInformationW` at `0x140011bf9`

## string_xrefs

- `0x140011af5`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`

## pseudocode

```c
char __fastcall RdpNamedPipeHandler::CurrentSessionSupported(RdpNamedPipeHandler *this)
{
  char v1; // r14
  DWORD LastError; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v4; // rdx
  unsigned int v5; // eax
  int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwReturnedProductType; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pBytesReturned; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-C4h] BYREF
  LPWSTR ppBuffer; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v18; // [rsp+164h] [rbp+64h]
  unsigned __int16 v19; // [rsp+166h] [rbp+66h]

  ppBuffer = 0;
  pBytesReturned = 0;
  phkResult = 0;
  v1 = 0;
  pdwReturnedProductType = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 23;
LABEL_6:
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        &WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids,
        CurrentThreadActivityIdPrefix,
        LastError);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  if ( GetProductInfo(
         VersionInformation.dwMajorVersion,
         VersionInformation.dwMinorVersion,
         v18,
         v19,
         &pdwReturnedProductType) )
  {
    if ( pdwReturnedProductType == 175 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v5 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids, v5);
      }
      *(_DWORD *)Data = 1;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services",
             0,
             0x20019u,
             &phkResult)
        || (cbData = 4, !RegQueryValueExW(phkResult, L"EnableUiaRedirection", 0, 0, Data, &cbData)) )
      {
        v6 = *(_DWORD *)Data;
      }
      else
      {
        v6 = 1;
        *(_DWORD *)Data = 1;
      }
      if ( !v6 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_44;
        }
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 26;
        goto LABEL_43;
      }
    }
    else
    {
      if ( !(unsigned int)Containers::IsContainerModeEnabled() )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_44;
        }
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 29;
LABEL_43:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids, v7);
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids, v9);
      }
    }
    if ( WTSQuerySessionInformationW(0, 0xFFFFFFFF, WTSInitialProgram, &ppBuffer, &pBytesReturned) )
    {
      if ( pBytesReturned && !_wcsicmp(L"rdpinit.exe", ppBuffer) )
        v1 = 1;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v4 = 30;
        goto LABEL_6;
      }
    }
    goto LABEL_44;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v4 = 24;
    goto LABEL_6;
  }
LABEL_44:
  if ( ppBuffer )
    WTSFreeMemory(ppBuffer);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v1;
}

```

## disassembly

```asm
0x14001194c  push    rbp
0x14001194e  push    rbx
0x14001194f  push    rdi
0x140011950  push    r14
0x140011952  lea     rbp, [rsp-88h]
0x14001195a  sub     rsp, 188h
0x140011961  mov     rax, cs:__security_cookie
0x140011968  xor     rax, rsp
0x14001196b  mov     [rbp+0A0h+var_30], rax
0x14001196f  xor     edx, edx; Val
0x140011971  mov     [rsp+1A0h+ppBuffer], 0
0x14001197a  mov     r8d, 118h; Size
0x140011980  mov     [rsp+1A0h+pBytesReturned], 0
0x140011988  lea     rcx, [rsp+1A0h+VersionInformation.dwMajorVersion]; void *
0x14001198d  mov     [rsp+1A0h+phkResult], 0
0x140011996  xor     r14b, r14b
0x140011999  mov     [rsp+1A0h+var_16C], 0
0x1400119a1  call    memset_0
0x1400119a6  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x1400119ab  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1400119b3  call    cs:__imp_GetVersionExW
0x1400119b9  test    eax, eax
0x1400119bb  jnz     short loc_140011A1D
0x1400119bd  call    cs:__imp_GetLastError
0x1400119c3  mov     edi, eax
0x1400119c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400119cc  lea     rbx, WPP_GLOBAL_Control
0x1400119d3  cmp     rcx, rbx
0x1400119d6  jz      loc_140011C9F
0x1400119dc  test    byte ptr [rcx+1Ch], 8
0x1400119e0  jz      loc_140011C9F
0x1400119e6  cmp     byte ptr [rcx+19h], 2
0x1400119ea  jb      loc_140011C9F
0x1400119f0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400119f5  mov     edx, 17h
0x1400119fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a01  lea     r8, WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids
0x140011a08  mov     r9d, eax
0x140011a0b  mov     dword ptr [rsp+1A0h+pdwReturnedProductType], edi
0x140011a0f  mov     rcx, [rcx+10h]
0x140011a13  call    WPP_SF_Dd
0x140011a18  jmp     loc_140011C9F
0x140011a1d  movzx   r9d, [rbp+0A0h+var_3A]; dwSpMinorVersion
0x140011a22  lea     rax, [rsp+1A0h+var_16C]
0x140011a27  movzx   r8d, [rbp+0A0h+var_3C]; dwSpMajorVersion
0x140011a2c  mov     edx, [rsp+1A0h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x140011a30  mov     ecx, [rsp+1A0h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x140011a34  mov     [rsp+1A0h+pdwReturnedProductType], rax; pdwReturnedProductType
0x140011a39  call    cs:__imp_GetProductInfo
0x140011a3f  test    eax, eax
0x140011a41  jnz     short loc_140011A85
0x140011a43  call    cs:__imp_GetLastError
0x140011a49  mov     edi, eax
0x140011a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a52  lea     rbx, WPP_GLOBAL_Control
0x140011a59  cmp     rcx, rbx
0x140011a5c  jz      loc_140011C9F
0x140011a62  test    byte ptr [rcx+1Ch], 8
0x140011a66  jz      loc_140011C9F
0x140011a6c  cmp     byte ptr [rcx+19h], 2
0x140011a70  jb      loc_140011C9F
0x140011a76  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140011a7b  mov     edx, 18h
0x140011a80  jmp     loc_1400119FA
0x140011a85  cmp     [rsp+1A0h+var_16C], 0AFh
0x140011a8d  jnz     loc_140011B8E
0x140011a93  mov     rax, cs:WPP_GLOBAL_Control
0x140011a9a  lea     rbx, WPP_GLOBAL_Control
0x140011aa1  mov     edi, 1000h
0x140011aa6  cmp     rax, rbx
0x140011aa9  jz      short loc_140011ADA
0x140011aab  test    [rax+1Ch], edi
0x140011aae  jz      short loc_140011ADA
0x140011ab0  cmp     byte ptr [rax+19h], 5
0x140011ab4  jb      short loc_140011ADA
0x140011ab6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140011abb  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ac2  lea     r8, WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids
0x140011ac9  mov     edx, 19h
0x140011ace  mov     r9d, eax
0x140011ad1  mov     rcx, [rcx+10h]
0x140011ad5  call    WPP_SF_d
0x140011ada  lea     rax, [rsp+1A0h+phkResult]
0x140011adf  mov     dword ptr [rsp+1A0h+Data], 1
0x140011ae7  mov     r9d, 20019h; samDesired
0x140011aed  mov     [rsp+1A0h+pdwReturnedProductType], rax; phkResult
0x140011af2  xor     r8d, r8d; ulOptions
0x140011af5  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x140011afc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011b03  call    cs:__imp_RegOpenKeyExW
0x140011b09  test    eax, eax
0x140011b0b  jnz     short loc_140011B50
0x140011b0d  mov     rcx, [rsp+1A0h+phkResult]; hKey
0x140011b12  lea     rax, [rsp+1A0h+cbData]
0x140011b17  mov     [rsp+1A0h+lpcbData], rax; lpcbData
0x140011b1c  lea     rdx, aEnableuiaredir; "EnableUiaRedirection"
0x140011b23  lea     rax, [rsp+1A0h+Data]
0x140011b28  mov     [rsp+1A0h+cbData], 4
0x140011b30  xor     r9d, r9d; lpType
0x140011b33  mov     [rsp+1A0h+pdwReturnedProductType], rax; lpData
0x140011b38  xor     r8d, r8d; lpReserved
0x140011b3b  call    cs:__imp_RegQueryValueExW
0x140011b41  test    eax, eax
0x140011b43  jz      short loc_140011B50
0x140011b45  mov     eax, 1
0x140011b4a  mov     dword ptr [rsp+1A0h+Data], eax
0x140011b4e  jmp     short loc_140011B54
0x140011b50  mov     eax, dword ptr [rsp+1A0h+Data]
0x140011b54  test    eax, eax
0x140011b56  jnz     loc_140011BE2
0x140011b5c  mov     rax, cs:WPP_GLOBAL_Control
0x140011b63  cmp     rax, rbx
0x140011b66  jz      loc_140011C9F
0x140011b6c  test    [rax+1Ch], edi
0x140011b6f  jz      loc_140011C9F
0x140011b75  cmp     byte ptr [rax+19h], 4
0x140011b79  jb      loc_140011C9F
0x140011b7f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140011b84  mov     edx, 1Ah
0x140011b89  jmp     loc_140011C85
0x140011b8e  call    Containers__IsContainerModeEnabled
0x140011b93  test    eax, eax
0x140011b95  jz      loc_140011C58
0x140011b9b  mov     rax, cs:WPP_GLOBAL_Control
0x140011ba2  lea     rbx, WPP_GLOBAL_Control
0x140011ba9  cmp     rax, rbx
0x140011bac  jz      short loc_140011BE2
0x140011bae  mov     edi, 1000h
0x140011bb3  test    [rax+1Ch], edi
0x140011bb6  jz      short loc_140011BE2
0x140011bb8  cmp     byte ptr [rax+19h], 5
0x140011bbc  jb      short loc_140011BE2
0x140011bbe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140011bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140011bca  lea     r8, WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids
0x140011bd1  mov     edx, 1Ch
0x140011bd6  mov     r9d, eax
0x140011bd9  mov     rcx, [rcx+10h]
0x140011bdd  call    WPP_SF_d
0x140011be2  lea     rax, [rsp+1A0h+pBytesReturned]
0x140011be7  xor     r8d, r8d; WTSInfoClass
0x140011bea  lea     r9, [rsp+1A0h+ppBuffer]; ppBuffer
0x140011bef  mov     [rsp+1A0h+pdwReturnedProductType], rax; pBytesReturned
0x140011bf4  or      edx, 0FFFFFFFFh; SessionId
0x140011bf7  xor     ecx, ecx; hServer
0x140011bf9  call    cs:__imp_WTSQuerySessionInformationW
0x140011bff  test    eax, eax
0x140011c01  jnz     short loc_140011C36
0x140011c03  call    cs:__imp_GetLastError
0x140011c09  mov     edi, eax
0x140011c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c12  cmp     rcx, rbx
0x140011c15  jz      loc_140011C9F
0x140011c1b  test    byte ptr [rcx+1Ch], 8
0x140011c1f  jz      short loc_140011C9F
0x140011c21  cmp     byte ptr [rcx+19h], 2
0x140011c25  jb      short loc_140011C9F
0x140011c27  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140011c2c  mov     edx, 1Eh
0x140011c31  jmp     loc_1400119FA
0x140011c36  cmp     [rsp+1A0h+pBytesReturned], 0
0x140011c3b  jz      short loc_140011C9F
0x140011c3d  mov     rdx, [rsp+1A0h+ppBuffer]; String2
0x140011c42  lea     rcx, aRdpinitExe; "rdpinit.exe"
0x140011c49  call    cs:__imp__wcsicmp
0x140011c4f  test    eax, eax
0x140011c51  jnz     short loc_140011C9F
0x140011c53  mov     r14b, 1
0x140011c56  jmp     short loc_140011C9F
0x140011c58  mov     rax, cs:WPP_GLOBAL_Control
0x140011c5f  lea     rbx, WPP_GLOBAL_Control
0x140011c66  cmp     rax, rbx
0x140011c69  jz      short loc_140011C9F
0x140011c6b  mov     edi, 1000h
0x140011c70  test    [rax+1Ch], edi
0x140011c73  jz      short loc_140011C9F
0x140011c75  cmp     byte ptr [rax+19h], 4
0x140011c79  jb      short loc_140011C9F
0x140011c7b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140011c80  mov     edx, 1Dh
0x140011c85  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c8c  lea     r8, WPP_9a7fa01c864e3dc68f2a9283abe3b96f_Traceguids
0x140011c93  mov     r9d, eax
0x140011c96  mov     rcx, [rcx+10h]
0x140011c9a  call    WPP_SF_d
0x140011c9f  mov     rcx, [rsp+1A0h+ppBuffer]; pMemory
0x140011ca4  test    rcx, rcx
0x140011ca7  jz      short loc_140011CAF
0x140011ca9  call    cs:__imp_WTSFreeMemory
0x140011caf  mov     rcx, [rsp+1A0h+phkResult]; hKey
0x140011cb4  test    rcx, rcx
0x140011cb7  jz      short loc_140011CBF
0x140011cb9  call    cs:__imp_RegCloseKey
0x140011cbf  mov     al, r14b
0x140011cc2  mov     rcx, [rbp+0A0h+var_30]
0x140011cc6  xor     rcx, rsp; StackCookie
0x140011cc9  call    __security_check_cookie
0x140011cce  add     rsp, 188h
0x140011cd5  pop     r14
0x140011cd7  pop     rdi
0x140011cd8  pop     rbx
0x140011cd9  pop     rbp
0x140011cda  retn
```
