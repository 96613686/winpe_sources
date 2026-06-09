# COemActivationDataBaseT<CEmptyType>::Initialize(void)

- ea: `0x180172c90`
- end: `0x180172ee1`
- name: `?Initialize@?$COemActivationDataBaseT@VCEmptyType@@@@UEAAJXZ`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180173564`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x1800d989c`
- `0x180171c98`
- `0x180172c90`
- `0x180172ee8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180172d88`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180172dd6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180172d88`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180172dd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180172de7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180172e72`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180172e98`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180172de7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180172e72`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180172e98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180172da0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180172e23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180172da0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180172e23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180172ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180172ea3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180172eb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180172eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172df2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180172e31`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180172ce2`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180172ce2`

## string_xrefs

- `0x180172db7`: `kernel32.dll`
- `0x180172d58`: `kernelBase.dll`

## pseudocode

```c
__int64 __fastcall COemActivationDataBaseT<CEmptyType>::Initialize(__int64 a1)
{
  HMODULE v2; // rbx
  BOOL v3; // r14d
  signed int LastError; // eax
  unsigned int v5; // edi
  int v6; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // r15
  HMODULE v9; // r14
  signed int v10; // eax
  signed int v11; // eax
  HMODULE v12; // rcx
  HMODULE v13; // r14
  HMODULE v14; // r12
  HMODULE v15; // rax
  _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-D0h] BYREF

  v2 = 0;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( GetVersionExW(&VersionInformation) )
  {
    v5 = 0;
    v3 = VersionInformation.dwPlatformId == 2 && VersionInformation.dwMajorVersion >= 6;
  }
  else
  {
    v3 = 0;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_40;
  }
  if ( v3 )
  {
    v6 = CMiscHelpersT<CEmptyType>::AppendToSystemPath(L"kernelBase.dll");
    v5 = v6;
    if ( v6 < 0 )
    {
LABEL_15:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
      goto LABEL_40;
    }
    Library = LoadLibraryExW(0, 0, 0);
    v2 = Library;
    if ( !Library || (ProcAddress = GetProcAddress(Library, "GetSystemFirmwareTable")) == 0 )
    {
      v6 = CMiscHelpersT<CEmptyType>::AppendToSystemPath((void *)L"kernel32.dll");
      v5 = v6;
      if ( v6 < 0 )
        goto LABEL_15;
      v9 = LoadLibraryExW(0, 0, 0);
      if ( v2 )
        FreeLibrary(v2);
      if ( !v9 )
      {
        v10 = GetLastError();
        v5 = v10;
        if ( v10 )
        {
          if ( v10 > 0 )
            v5 = (unsigned __int16)v10 | 0x80070000;
        }
        else
        {
          v5 = -2147467259;
        }
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
        v2 = 0;
        goto LABEL_40;
      }
      ProcAddress = GetProcAddress(v9, "GetSystemFirmwareTable");
      if ( !ProcAddress )
      {
        v11 = GetLastError();
        v5 = v11;
        if ( v11 )
        {
          if ( v11 > 0 )
            v5 = (unsigned __int16)v11 | 0x80070000;
        }
        else
        {
          v5 = -2147467259;
        }
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
        v2 = v9;
        goto LABEL_40;
      }
      v2 = v9;
    }
  }
  else
  {
    ProcAddress = 0;
  }
  v12 = *(HMODULE *)(a1 + 8);
  v13 = v2;
  v14 = v2;
  v2 = 0;
  if ( v12 )
    FreeLibrary(v12);
  v15 = 0;
  if ( v13 )
    v15 = v14;
  *(_QWORD *)(a1 + 8) = v15;
  *(_QWORD *)(a1 + 16) = ProcAddress;
LABEL_40:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v2 )
    FreeLibrary(v2);
  return v5;
}

```

## disassembly

```asm
0x180172c90  push    rbp
0x180172c92  push    rbx
0x180172c93  push    rsi
0x180172c94  push    rdi
0x180172c95  push    r12
0x180172c97  push    r13
0x180172c99  push    r14
0x180172c9b  push    r15
0x180172c9d  lea     rbp, [rsp-68h]
0x180172ca2  sub     rsp, 168h
0x180172ca9  mov     rax, cs:__security_cookie
0x180172cb0  xor     rax, rsp
0x180172cb3  mov     [rbp+0A0h+var_50], rax
0x180172cb7  mov     r13, rcx
0x180172cba  xor     esi, esi
0x180172cbc  lea     rcx, [rsp+1A0h+VersionInformation.dwMajorVersion]; void *
0x180172cc1  mov     [rsp+1A0h+lpLibFileName], rsi
0x180172cc6  xor     edx, edx; Val
0x180172cc8  mov     r8d, 110h; Size
0x180172cce  xor     ebx, ebx
0x180172cd0  call    memset_0
0x180172cd5  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x180172cda  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 114h
0x180172ce2  call    cs:__imp_GetVersionExW
0x180172ce8  mov     r12d, 80004005h
0x180172cee  test    eax, eax
0x180172cf0  jnz     short loc_180172D1A
0x180172cf2  xor     r14d, r14d
0x180172cf5  call    cs:__imp_GetLastError
0x180172cfb  mov     edi, eax
0x180172cfd  test    eax, eax
0x180172cff  jnz     short loc_180172D06
0x180172d01  mov     edi, r12d
0x180172d04  jmp     short loc_180172D11
0x180172d06  jle     short loc_180172D11
0x180172d08  movzx   edi, ax
0x180172d0b  or      edi, 80070000h
0x180172d11  mov     ecx, edi
0x180172d13  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180172d18  jmp     short loc_180172D33
0x180172d1a  xor     edi, edi
0x180172d1c  cmp     [rsp+1A0h+VersionInformation.dwPlatformId], 2
0x180172d21  jnz     short loc_180172D30
0x180172d23  cmp     [rsp+1A0h+VersionInformation.dwMajorVersion], 6
0x180172d28  jb      short loc_180172D30
0x180172d2a  lea     r14d, [rdi+1]
0x180172d2e  jmp     short loc_180172D33
0x180172d30  xor     r14d, r14d
0x180172d33  mov     ecx, edi
0x180172d35  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180172d3a  test    edi, edi
0x180172d3c  jns     short loc_180172D4A
0x180172d3e  mov     ecx, edi
0x180172d40  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180172d45  jmp     loc_180172E89
0x180172d4a  test    r14d, r14d
0x180172d4d  jz      loc_180172E5E
0x180172d53  lea     rdx, [rsp+1A0h+lpLibFileName]
0x180172d58  lea     rcx, aKernelbaseDll_0; "kernelBase.dll"
0x180172d5f  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x180172d64  mov     edi, eax
0x180172d66  test    eax, eax
0x180172d68  jns     short loc_180172D7B
0x180172d6a  mov     ecx, eax
0x180172d6c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180172d71  mov     rsi, [rsp+1A0h+lpLibFileName]
0x180172d76  jmp     loc_180172E89
0x180172d7b  mov     rsi, [rsp+1A0h+lpLibFileName]
0x180172d80  xor     r8d, r8d; dwFlags
0x180172d83  mov     rcx, rsi; lpLibFileName
0x180172d86  xor     edx, edx; hFile
0x180172d88  call    cs:__imp_LoadLibraryExW
0x180172d8e  mov     rbx, rax
0x180172d91  test    rax, rax
0x180172d94  jz      short loc_180172DB2
0x180172d96  mov     rcx, rax; hModule
0x180172d99  lea     rdx, aGetsystemfirmw; "GetSystemFirmwareTable"
0x180172da0  call    cs:__imp_GetProcAddress
0x180172da6  mov     r15, rax
0x180172da9  test    rax, rax
0x180172dac  jnz     loc_180172E61
0x180172db2  lea     rdx, [rsp+1A0h+lpLibFileName]
0x180172db7  lea     rcx, SourceString; "kernel32.dll"
0x180172dbe  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x180172dc3  mov     edi, eax
0x180172dc5  test    eax, eax
0x180172dc7  js      short loc_180172D6A
0x180172dc9  mov     rsi, [rsp+1A0h+lpLibFileName]
0x180172dce  xor     r8d, r8d; dwFlags
0x180172dd1  mov     rcx, rsi; lpLibFileName
0x180172dd4  xor     edx, edx; hFile
0x180172dd6  call    cs:__imp_LoadLibraryExW
0x180172ddc  mov     r14, rax
0x180172ddf  test    rbx, rbx
0x180172de2  jz      short loc_180172DED
0x180172de4  mov     rcx, rbx; hLibModule
0x180172de7  call    cs:__imp_FreeLibrary
0x180172ded  test    r14, r14
0x180172df0  jnz     short loc_180172E19
0x180172df2  call    cs:__imp_GetLastError
0x180172df8  mov     edi, eax
0x180172dfa  test    eax, eax
0x180172dfc  jnz     short loc_180172E03
0x180172dfe  mov     edi, r12d
0x180172e01  jmp     short loc_180172E0E
0x180172e03  jle     short loc_180172E0E
0x180172e05  movzx   edi, ax
0x180172e08  or      edi, 80070000h
0x180172e0e  mov     ecx, edi
0x180172e10  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180172e15  xor     ebx, ebx
0x180172e17  jmp     short loc_180172E89
0x180172e19  mov     rcx, r14; hModule
0x180172e1c  lea     rdx, aGetsystemfirmw; "GetSystemFirmwareTable"
0x180172e23  call    cs:__imp_GetProcAddress
0x180172e29  mov     r15, rax
0x180172e2c  test    rax, rax
0x180172e2f  jnz     short loc_180172E59
0x180172e31  call    cs:__imp_GetLastError
0x180172e37  mov     edi, eax
0x180172e39  test    eax, eax
0x180172e3b  jnz     short loc_180172E42
0x180172e3d  mov     edi, r12d
0x180172e40  jmp     short loc_180172E4D
0x180172e42  jle     short loc_180172E4D
0x180172e44  movzx   edi, ax
0x180172e47  or      edi, 80070000h
0x180172e4d  mov     ecx, edi
0x180172e4f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180172e54  mov     rbx, r14
0x180172e57  jmp     short loc_180172E89
0x180172e59  mov     rbx, r14
0x180172e5c  jmp     short loc_180172E61
0x180172e5e  xor     r15d, r15d
0x180172e61  mov     rcx, [r13+8]; hLibModule
0x180172e65  mov     r14, rbx
0x180172e68  mov     r12, rbx
0x180172e6b  xor     ebx, ebx
0x180172e6d  test    rcx, rcx
0x180172e70  jz      short loc_180172E78
0x180172e72  call    cs:__imp_FreeLibrary
0x180172e78  xor     eax, eax
0x180172e7a  test    r14, r14
0x180172e7d  cmovnz  rax, r12
0x180172e81  mov     [r13+8], rax
0x180172e85  mov     [r13+10h], r15
0x180172e89  mov     ecx, edi
0x180172e8b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180172e90  test    rbx, rbx
0x180172e93  jz      short loc_180172E9E
0x180172e95  mov     rcx, rbx; hLibModule
0x180172e98  call    cs:__imp_FreeLibrary
0x180172e9e  test    rsi, rsi
0x180172ea1  jz      short loc_180172EBF
0x180172ea3  call    cs:__imp_GetProcessHeap
0x180172ea9  lea     r8, [rsi-4]; lpMem
0x180172ead  xor     edx, edx; dwFlags
0x180172eaf  mov     rcx, rax; hHeap
0x180172eb2  call    cs:__imp_HeapFree
0x180172eb8  xor     ecx, ecx
0x180172eba  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180172ebf  mov     eax, edi
0x180172ec1  mov     rcx, [rbp+0A0h+var_50]
0x180172ec5  xor     rcx, rsp; StackCookie
0x180172ec8  call    __security_check_cookie
0x180172ecd  add     rsp, 168h
0x180172ed4  pop     r15
0x180172ed6  pop     r14
0x180172ed8  pop     r13
0x180172eda  pop     r12
0x180172edc  pop     rdi
0x180172edd  pop     rsi
0x180172ede  pop     rbx
0x180172edf  pop     rbp
0x180172ee0  retn
```
