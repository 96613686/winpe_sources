# FwCriticalSectionCreate

- ea: `0x180005350`
- end: `0x1800053b1`
- name: `FwCriticalSectionCreate`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180005350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005365`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000537e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000537e`

## string_xrefs

- `0x18000538e`: `FwCriticalSectionCreate`
- `0x1800053a0`: `FwCriticalSectionCreate`

## pseudocode

```c
__int64 __fastcall FwCriticalSectionCreate(__int64 a1)
{
  __int64 result; // rax
  DWORD LastError; // eax

  *(_DWORD *)(a1 + 40) = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)a1, 0xFA0u) )
  {
    result = 0;
    *(_DWORD *)(a1 + 40) = 1;
  }
  else
  {
    LastError = GetLastError();
    result = FwReportErrorAsWinError("FwCriticalSectionCreate", "InitializeCriticalSectionAndSpinCount", LastError);
    if ( (int)result < 0 )
      return FwReportReturnError("FwCriticalSectionCreate", (unsigned int)result);
  }
  return result;
}

```

## disassembly

```asm
0x180005350  push    rbx
0x180005352  sub     rsp, 20h
0x180005356  mov     edx, 0FA0h; dwSpinCount
0x18000535b  mov     dword ptr [rcx+28h], 0
0x180005362  mov     rbx, rcx
0x180005365  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000536b  test    eax, eax
0x18000536d  jz      short loc_18000537E
0x18000536f  xor     eax, eax
0x180005371  mov     dword ptr [rbx+28h], 1
0x180005378  add     rsp, 20h
0x18000537c  pop     rbx
0x18000537d  retn
0x18000537e  call    cs:__imp_GetLastError
0x180005384  mov     r8d, eax
0x180005387  lea     rdx, aInitializecrit; "InitializeCriticalSectionAndSpinCount"
0x18000538e  lea     rcx, aFwcriticalsect_3; "FwCriticalSectionCreate"
0x180005395  call    FwReportErrorAsWinError
0x18000539a  test    eax, eax
0x18000539c  jns     short loc_180005378
0x18000539e  mov     edx, eax
0x1800053a0  lea     rcx, aFwcriticalsect_3; "FwCriticalSectionCreate"
0x1800053a7  add     rsp, 20h
0x1800053ab  pop     rbx
0x1800053ac  jmp     FwReportReturnError
```
