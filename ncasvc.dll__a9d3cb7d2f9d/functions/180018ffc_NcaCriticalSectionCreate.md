# NcaCriticalSectionCreate

- ea: `0x180018ffc`
- end: `0x180019098`
- name: `NcaCriticalSectionCreate`
- size: `156`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `21`
- callee_count: `4`
- tags: ``

## callers

- `0x1800026d0`
- `0x180006ec0`
- `0x18000b488`
- `0x18000d720`
- `0x18000f1b0`
- `0x1800100f0`
- `0x180010430`
- `0x180010820`
- `0x180010c70`
- `0x180011744`
- `0x180012950`
- `0x1800136e0`
- `0x180013c10`
- `0x180014330`
- `0x180014900`
- `0x180014b80`
- `0x180014f40`
- `0x1800156d0`
- `0x1800164e0`
- `0x1800169b0`
- `0x180018090`

## callees

- `0x1800033bc`
- `0x180004f04`
- `0x180018ffc`
- `0x1800199b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001903f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18001903f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001904f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001904f`

## string_xrefs

- `0x180019065`: `NcaCriticalSectionCreate`
- `0x180019077`: `NcaCriticalSectionCreate`

## pseudocode

```c
__int64 __fastcall NcaCriticalSectionCreate(LPCRITICAL_SECTION lpCriticalSection)
{
  DWORD LastError; // eax
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
  LODWORD(lpCriticalSection[1].DebugInfo) = 0;
  if ( InitializeCriticalSectionAndSpinCount(lpCriticalSection, 0) )
  {
    result = 0;
    LODWORD(lpCriticalSection[1].DebugInfo) = 1;
  }
  else
  {
    LastError = GetLastError();
    result = NcaReportErrorAsWinError("NcaCriticalSectionCreate", "InitializeCriticalSectionAndSpinCount", LastError);
    if ( (int)result < 0 )
      return NcaReportReturnError("NcaCriticalSectionCreate", (unsigned int)result);
  }
  return result;
}

```

## disassembly

```asm
0x180018ffc  push    rbx
0x180018ffe  sub     rsp, 20h
0x180019002  mov     rbx, rcx
0x180019005  mov     rcx, cs:WPP_GLOBAL_Control
0x18001900c  lea     rax, WPP_GLOBAL_Control
0x180019013  cmp     rcx, rax
0x180019016  jz      short loc_180019033
0x180019018  test    byte ptr [rcx+1Ch], 8
0x18001901c  jz      short loc_180019033
0x18001901e  mov     rcx, [rcx+10h]
0x180019022  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x180019029  mov     edx, 23h ; '#'
0x18001902e  call    WPP_SF_
0x180019033  xor     edx, edx; dwSpinCount
0x180019035  mov     dword ptr [rbx+28h], 0
0x18001903c  mov     rcx, rbx; lpCriticalSection
0x18001903f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180019046  nop     dword ptr [rax+rax+00h]
0x18001904b  test    eax, eax
0x18001904d  jnz     short loc_180019088
0x18001904f  call    cs:__imp_GetLastError
0x180019056  nop     dword ptr [rax+rax+00h]
0x18001905b  mov     r8d, eax
0x18001905e  lea     rdx, aInitializecrit; "InitializeCriticalSectionAndSpinCount"
0x180019065  lea     rcx, aNcacriticalsec; "NcaCriticalSectionCreate"
0x18001906c  call    NcaReportErrorAsWinError
0x180019071  test    eax, eax
0x180019073  jns     short loc_180019091
0x180019075  mov     edx, eax
0x180019077  lea     rcx, aNcacriticalsec; "NcaCriticalSectionCreate"
0x18001907e  add     rsp, 20h
0x180019082  pop     rbx
0x180019083  jmp     NcaReportReturnError
0x180019088  xor     eax, eax
0x18001908a  mov     dword ptr [rbx+28h], 1
0x180019091  add     rsp, 20h
0x180019095  pop     rbx
0x180019096  retn
```
