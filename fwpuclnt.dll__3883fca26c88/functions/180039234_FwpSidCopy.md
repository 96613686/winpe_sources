# FwpSidCopy

- ea: `0x180039234`
- end: `0x1800392e1`
- name: `FwpSidCopy`
- size: `173`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003901c`
- `0x18003966c`

## callees

- `0x1800034e0`
- `0x18000438c`
- `0x180005fc8`
- `0x180007e38`
- `0x180039234`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039293`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180039283`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180039283`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039252`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039252`

## string_xrefs

- `0x1800392a2`: `CopySid`
- `0x1800392c0`: `FwpSidCopy`

## pseudocode

```c
__int64 __fastcall FwpSidCopy(PSID pSourceSid, _QWORD *a2)
{
  __int64 v2; // rbx
  DWORD LengthSid; // ebp
  PSID v6; // r8
  PSID v7; // rsi
  DWORD LastError; // eax
  __int64 v9; // rcx
  PSID pDestinationSid; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  pDestinationSid = 0;
  *a2 = 0;
  if ( pSourceSid )
  {
    LengthSid = GetLengthSid(pSourceSid);
    v2 = WfpMemAlloc(LengthSid, 0);
    if ( v2 )
      goto LABEL_5;
    v6 = pSourceSid;
    v7 = pDestinationSid;
    if ( CopySid(LengthSid, pDestinationSid, v6) )
    {
      *a2 = v7;
      return v2;
    }
    LastError = GetLastError();
    v2 = WfpReportSysErrorAsWinError(v9, "CopySid", LastError);
    if ( v2 )
    {
LABEL_5:
      WfpMemFree(&pDestinationSid);
      WfpReportError(v2, "FwpSidCopy");
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180039234  push    rbx
0x180039236  push    rbp
0x180039237  push    rsi
0x180039238  push    rdi
0x180039239  sub     rsp, 28h
0x18003923d  xor     ebx, ebx
0x18003923f  mov     rdi, rdx
0x180039242  mov     [rsp+48h+pDestinationSid], rbx
0x180039247  mov     rsi, rcx
0x18003924a  mov     [rdx], rbx
0x18003924d  test    rcx, rcx
0x180039250  jz      short loc_1800392CF
0x180039252  call    cs:__imp_GetLengthSid
0x180039259  nop     dword ptr [rax+rax+00h]
0x18003925e  mov     ecx, eax; dwBytes
0x180039260  lea     r8, [rsp+48h+pDestinationSid]
0x180039265  xor     edx, edx; dwFlags
0x180039267  mov     ebp, eax
0x180039269  call    WfpMemAlloc
0x18003926e  mov     rbx, rax
0x180039271  test    rax, rax
0x180039274  jnz     short loc_1800392B6
0x180039276  mov     r8, rsi; pSourceSid
0x180039279  mov     ecx, ebp; nDestinationSidLength
0x18003927b  mov     rsi, [rsp+48h+pDestinationSid]
0x180039280  mov     rdx, rsi; pDestinationSid
0x180039283  call    cs:__imp_CopySid
0x18003928a  nop     dword ptr [rax+rax+00h]
0x18003928f  test    eax, eax
0x180039291  jnz     short loc_1800392DC
0x180039293  call    cs:__imp_GetLastError
0x18003929a  nop     dword ptr [rax+rax+00h]
0x18003929f  mov     r8d, eax
0x1800392a2  lea     rdx, aCopysid; "CopySid"
0x1800392a9  call    WfpReportSysErrorAsWinError
0x1800392ae  mov     rbx, rax
0x1800392b1  test    rax, rax
0x1800392b4  jz      short loc_1800392CF
0x1800392b6  lea     rcx, [rsp+48h+pDestinationSid]
0x1800392bb  call    WfpMemFree
0x1800392c0  lea     rdx, aFwpsidcopy; "FwpSidCopy"
0x1800392c7  mov     rcx, rbx
0x1800392ca  call    WfpReportError
0x1800392cf  mov     rax, rbx
0x1800392d2  add     rsp, 28h
0x1800392d6  pop     rdi
0x1800392d7  pop     rsi
0x1800392d8  pop     rbp
0x1800392d9  pop     rbx
0x1800392da  retn
0x1800392dc  mov     [rdi], rsi
0x1800392df  jmp     short loc_1800392CF
```
