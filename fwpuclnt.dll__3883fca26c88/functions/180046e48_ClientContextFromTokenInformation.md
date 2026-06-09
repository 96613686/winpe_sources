# ClientContextFromTokenInformation

- ea: `0x180046e48`
- end: `0x180046ec8`
- name: `ClientContextFromTokenInformation`
- size: `128`
- prototype: `__int64 __fastcall(PVOID DynamicGroupArgs, PAUTHZ_CLIENT_CONTEXT_HANDLE phAuthzClientContext)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180046dcc`
- `0x180046ed0`

## callees

- `0x1800034e0`
- `0x180007e38`
- `0x180046e48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046e8c`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180046e7c`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180046e7c`

## string_xrefs

- `0x180046eaf`: `ClientContextFromTokenInformation`
- `0x180046e9b`: `AuthzInitializeContextFromSid`

## pseudocode

```c
__int64 __fastcall ClientContextFromTokenInformation(
        PSID **DynamicGroupArgs,
        PAUTHZ_CLIENT_CONTEXT_HANDLE phAuthzClientContext)
{
  __int64 v2; // rbx
  DWORD LastError; // eax
  __int64 v4; // rcx
  __int64 v5; // rax

  v2 = 0;
  if ( !AuthzInitializeContextFromSid(
          2u,
          *DynamicGroupArgs[1],
          *((AUTHZ_RESOURCE_MANAGER_HANDLE *)gWfpGlobal + 98),
          0,
          0,
          DynamicGroupArgs,
          phAuthzClientContext) )
  {
    LastError = GetLastError();
    v5 = WfpReportSysErrorAsWinError(v4, "AuthzInitializeContextFromSid", LastError);
    v2 = v5;
    if ( v5 )
      WfpReportError(v5, "ClientContextFromTokenInformation");
  }
  return v2;
}

```

## disassembly

```asm
0x180046e48  push    rbx
0x180046e4a  sub     rsp, 40h
0x180046e4e  mov     r10, [rcx+8]
0x180046e52  xor     eax, eax
0x180046e54  mov     r8, cs:gWfpGlobal
0x180046e5b  xor     ebx, ebx
0x180046e5d  mov     [rsp+48h+phAuthzClientContext], rdx; phAuthzClientContext
0x180046e62  xor     r9d, r9d; pExpirationTime
0x180046e65  mov     [rsp+48h+DynamicGroupArgs], rcx; DynamicGroupArgs
0x180046e6a  mov     rdx, [r10]; UserSid
0x180046e6d  mov     r8, [r8+310h]; hAuthzResourceManager
0x180046e74  lea     ecx, [rbx+2]; Flags
0x180046e77  mov     qword ptr [rsp+48h+Identifier.LowPart], rax; Identifier
0x180046e7c  call    cs:__imp_AuthzInitializeContextFromSid
0x180046e83  nop     dword ptr [rax+rax+00h]
0x180046e88  test    eax, eax
0x180046e8a  jnz     short loc_180046EBE
0x180046e8c  call    cs:__imp_GetLastError
0x180046e93  nop     dword ptr [rax+rax+00h]
0x180046e98  mov     r8d, eax
0x180046e9b  lea     rdx, aAuthzinitializ_2; "AuthzInitializeContextFromSid"
0x180046ea2  call    WfpReportSysErrorAsWinError
0x180046ea7  mov     rbx, rax
0x180046eaa  test    rax, rax
0x180046ead  jz      short loc_180046EBE
0x180046eaf  lea     rdx, aClientcontextf_0; "ClientContextFromTokenInformation"
0x180046eb6  mov     rcx, rax
0x180046eb9  call    WfpReportError
0x180046ebe  mov     rax, rbx
0x180046ec1  add     rsp, 40h
0x180046ec5  pop     rbx
0x180046ec6  retn
```
