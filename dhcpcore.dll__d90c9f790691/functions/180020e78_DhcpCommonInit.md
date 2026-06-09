# DhcpCommonInit

- ea: `0x180020e78`
- end: `0x180020f47`
- name: `DhcpCommonInit`
- size: `207`
- prototype: `__int64()`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180025350`
- `0x18003c064`
- `0x18003c554`
- `0x18003c9d8`

## callees

- `0x180007294`
- `0x180020e78`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020edf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020f18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020f18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020e98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020e98`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180020ec0`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180020ec0`

## pseudocode

```c
__int64 DhcpCommonInit()
{
  DWORD LastError; // eax
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF

  nSize = 0;
  if ( !DhcpCommonInitialized )
  {
    EnterCriticalSection(&DhcpGlobalApiCritSect);
    if ( !DhcpCommonInitialized )
    {
      nSize = 64;
      if ( GetComputerNameExW(ComputerNameDnsHostname, &DhcpGlobalHostNameW, &nSize) )
      {
        DhcpUnicodeToOem(&DhcpGlobalHostNameW);
      }
      else
      {
        LastError = GetLastError();
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_D(1025, 167, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, LastError);
      }
      DhcpCommonInitialized = 1;
    }
    LeaveCriticalSection(&DhcpGlobalApiCritSect);
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 168, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180020e78  sub     rsp, 28h
0x180020e7c  cmp     cs:DhcpCommonInitialized, 0
0x180020e83  mov     [rsp+28h+nSize], 0
0x180020e8b  jnz     loc_180020F1E
0x180020e91  lea     rcx, DhcpGlobalApiCritSect; lpCriticalSection
0x180020e98  call    cs:__imp_EnterCriticalSection
0x180020e9e  cmp     cs:DhcpCommonInitialized, 0
0x180020ea5  jnz     short loc_180020F11
0x180020ea7  lea     r8, [rsp+28h+nSize]; nSize
0x180020eac  mov     [rsp+28h+nSize], 40h ; '@'
0x180020eb4  lea     rdx, DhcpGlobalHostNameW; lpBuffer
0x180020ebb  mov     ecx, 1; NameType
0x180020ec0  call    cs:__imp_GetComputerNameExW
0x180020ec6  test    eax, eax
0x180020ec8  jz      short loc_180020EDF
0x180020eca  lea     rdx, DhcpGlobalHostName
0x180020ed1  lea     rcx, DhcpGlobalHostNameW; SourceString
0x180020ed8  call    DhcpUnicodeToOem
0x180020edd  jmp     short loc_180020F07
0x180020edf  call    cs:__imp_GetLastError
0x180020ee5  test    byte ptr cs:xmmword_1800616A0, 2
0x180020eec  jz      short loc_180020F07
0x180020eee  mov     edx, 0A7h
0x180020ef3  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180020efa  mov     ecx, 401h
0x180020eff  mov     r9d, eax
0x180020f02  call    WPP_SF_D
0x180020f07  mov     cs:DhcpCommonInitialized, 1
0x180020f11  lea     rcx, DhcpGlobalApiCritSect; lpCriticalSection
0x180020f18  call    cs:__imp_LeaveCriticalSection
0x180020f1e  test    byte ptr cs:xmmword_1800616A0, 10h
0x180020f25  jz      short loc_180020F40
0x180020f27  mov     edx, 0A8h
0x180020f2c  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180020f33  mov     ecx, 404h
0x180020f38  xor     r9d, r9d
0x180020f3b  call    WPP_SF_D
0x180020f40  xor     eax, eax
0x180020f42  add     rsp, 28h
0x180020f46  retn
```
