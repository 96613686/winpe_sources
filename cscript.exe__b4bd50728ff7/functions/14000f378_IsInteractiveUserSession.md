# IsInteractiveUserSession

- ea: `0x14000f378`
- end: `0x14000f418`
- name: `IsInteractiveUserSession`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000f464`

## callees

- `0x14000f378`
- `0x1400161d0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14000f39e`
- `KERNEL32!GetCurrentProcessId` at `0x14000f39e`
- `KERNEL32!ProcessIdToSessionId` at `0x14000f3ab`
- `KERNEL32!ProcessIdToSessionId` at `0x14000f3ab`
- `USER32!GetUserObjectInformationW` at `0x14000f3f2`
- `USER32!GetUserObjectInformationW` at `0x14000f3f2`
- `USER32!GetProcessWindowStation` at `0x14000f3bc`
- `USER32!GetProcessWindowStation` at `0x14000f3bc`
- `SHLWAPI!__imp_IsOS` at `0x14000f390`
- `SHLWAPI!__imp_IsOS` at `0x14000f390`

## pseudocode

```c
char IsInteractiveUserSession()
{
  DWORD CurrentProcessId; // eax
  HWINSTA ProcessWindowStation; // rax
  DWORD pSessionId; // [rsp+30h] [rbp-28h] BYREF
  DWORD nLengthNeeded; // [rsp+34h] [rbp-24h] BYREF
  __int64 pvInfo; // [rsp+38h] [rbp-20h] BYREF
  int v6; // [rsp+40h] [rbp-18h]

  if ( !IsOS(0x1Du)
    && (pSessionId = 0, CurrentProcessId = GetCurrentProcessId(), ProcessIdToSessionId(CurrentProcessId, &pSessionId))
    && pSessionId
    && (ProcessWindowStation = GetProcessWindowStation()) != 0
    && (pvInfo = 0,
        v6 = 0,
        nLengthNeeded = 0,
        GetUserObjectInformationW(ProcessWindowStation, 1, &pvInfo, 0xCu, &nLengthNeeded)) )
  {
    return v6 & 1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x14000f378  sub     rsp, 58h
0x14000f37c  mov     rax, cs:__security_cookie
0x14000f383  xor     rax, rsp
0x14000f386  mov     [rsp+58h+var_10], rax
0x14000f38b  mov     ecx, 1Dh; dwOS
0x14000f390  call    cs:__imp_IsOS
0x14000f396  test    eax, eax
0x14000f398  jnz     short loc_14000F404
0x14000f39a  mov     [rsp+58h+pSessionId], eax
0x14000f39e  call    cs:__imp_GetCurrentProcessId
0x14000f3a4  mov     ecx, eax; dwProcessId
0x14000f3a6  lea     rdx, [rsp+58h+pSessionId]; pSessionId
0x14000f3ab  call    cs:__imp_ProcessIdToSessionId
0x14000f3b1  test    eax, eax
0x14000f3b3  jz      short loc_14000F404
0x14000f3b5  cmp     [rsp+58h+pSessionId], 0
0x14000f3ba  jz      short loc_14000F404
0x14000f3bc  call    cs:__imp_GetProcessWindowStation
0x14000f3c2  test    rax, rax
0x14000f3c5  jz      short loc_14000F404
0x14000f3c7  xor     ecx, ecx
0x14000f3c9  lea     r8, [rsp+58h+pvInfo]; pvInfo
0x14000f3ce  mov     [rsp+58h+pvInfo], rcx
0x14000f3d3  mov     r9d, 0Ch; nLength
0x14000f3d9  mov     [rsp+58h+var_18], ecx
0x14000f3dd  mov     [rsp+58h+nLengthNeeded], ecx
0x14000f3e1  lea     rcx, [rsp+58h+nLengthNeeded]
0x14000f3e6  mov     [rsp+58h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x14000f3eb  mov     rcx, rax; hObj
0x14000f3ee  lea     edx, [r9-0Bh]; nIndex
0x14000f3f2  call    cs:__imp_GetUserObjectInformationW
0x14000f3f8  test    eax, eax
0x14000f3fa  jz      short loc_14000F404
0x14000f3fc  mov     eax, [rsp+58h+var_18]
0x14000f400  and     al, 1
0x14000f402  jmp     short loc_14000F406
0x14000f404  xor     al, al
0x14000f406  mov     rcx, [rsp+58h+var_10]
0x14000f40b  xor     rcx, rsp; StackCookie
0x14000f40e  call    __security_check_cookie
0x14000f413  add     rsp, 58h
0x14000f417  retn
```
