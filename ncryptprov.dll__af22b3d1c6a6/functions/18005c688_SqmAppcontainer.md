# SqmAppcontainer

- ea: `0x18005c688`
- end: `0x18005c7ac`
- name: `SqmAppcontainer`
- size: `292`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014558`

## callees

- `0x18000d3d0`
- `0x18000def0`
- `0x18005c688`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18005c6f3`
- `ntdll!NtQueryInformationToken` at `0x18005c735`
- `ntdll!NtQueryInformationToken` at `0x18005c6f3`
- `ntdll!NtQueryInformationToken` at `0x18005c735`
- `ntdll!WinSqmSetString` at `0x18005c767`
- `ntdll!WinSqmSetString` at `0x18005c767`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c6c8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005c6c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c6ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005c6ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c794`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c794`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c784`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005c784`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005c74c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005c74c`

## pseudocode

```c
HLOCAL SqmAppcontainer()
{
  HANDLE CurrentThread; // rax
  PSID *v1; // rbx
  ULONG TokenInformationLength; // [rsp+40h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+50h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  StringSid = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    if ( NtQueryInformationToken(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) == -1073741789 )
    {
      if ( TokenInformationLength )
      {
        v1 = (PSID *)SafeAllocaAllocateFromHeap(TokenInformationLength);
        if ( v1 )
        {
          if ( !NtQueryInformationToken(
                  TokenHandle,
                  TokenAppContainerSid,
                  v1,
                  TokenInformationLength,
                  &TokenInformationLength)
            && ConvertSidToStringSidW(*v1, &StringSid) )
          {
            WinSqmSetString(0, 12417, StringSid);
          }
          MSCryptFree(v1);
        }
      }
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LocalFree(StringSid);
}

```

## disassembly

```asm
0x18005c688  mov     [rsp-8+arg_18], rbx
0x18005c68d  push    rbp
0x18005c68e  mov     rbp, rsp
0x18005c691  sub     rsp, 30h
0x18005c695  mov     [rbp+TokenInformationLength], 0
0x18005c69c  mov     [rbp+TokenHandle], 0
0x18005c6a4  mov     [rbp+StringSid], 0
0x18005c6ac  call    cs:__imp_GetCurrentThread
0x18005c6b3  nop     dword ptr [rax+rax+00h]
0x18005c6b8  mov     edx, 0Ch; DesiredAccess
0x18005c6bd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18005c6c1  mov     rcx, rax; ThreadHandle
0x18005c6c4  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18005c6c8  call    cs:__imp_OpenThreadToken
0x18005c6cf  nop     dword ptr [rax+rax+00h]
0x18005c6d4  test    eax, eax
0x18005c6d6  jz      loc_18005C77B
0x18005c6dc  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005c6e0  lea     rax, [rbp+TokenInformationLength]
0x18005c6e4  xor     r9d, r9d; TokenInformationLength
0x18005c6e7  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18005c6ec  xor     r8d, r8d; TokenInformation
0x18005c6ef  lea     edx, [r9+1Fh]; TokenInformationClass
0x18005c6f3  call    cs:__imp_NtQueryInformationToken
0x18005c6fa  nop     dword ptr [rax+rax+00h]
0x18005c6ff  cmp     eax, 0C0000023h
0x18005c704  jnz     short loc_18005C77B
0x18005c706  mov     eax, [rbp+TokenInformationLength]
0x18005c709  test    eax, eax
0x18005c70b  jz      short loc_18005C77B
0x18005c70d  mov     ecx, eax
0x18005c70f  call    SafeAllocaAllocateFromHeap
0x18005c714  mov     rbx, rax
0x18005c717  test    rax, rax
0x18005c71a  jz      short loc_18005C77B
0x18005c71c  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18005c720  lea     rax, [rbp+TokenInformationLength]
0x18005c724  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18005c728  mov     r8, rbx; TokenInformation
0x18005c72b  mov     edx, 1Fh; TokenInformationClass
0x18005c730  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18005c735  call    cs:__imp_NtQueryInformationToken
0x18005c73c  nop     dword ptr [rax+rax+00h]
0x18005c741  test    eax, eax
0x18005c743  jnz     short loc_18005C773
0x18005c745  mov     rcx, [rbx]; Sid
0x18005c748  lea     rdx, [rbp+StringSid]; StringSid
0x18005c74c  call    cs:__imp_ConvertSidToStringSidW
0x18005c753  nop     dword ptr [rax+rax+00h]
0x18005c758  test    eax, eax
0x18005c75a  jz      short loc_18005C773
0x18005c75c  mov     r8, [rbp+StringSid]
0x18005c760  mov     edx, 3081h
0x18005c765  xor     ecx, ecx
0x18005c767  call    cs:__imp_WinSqmSetString
0x18005c76e  nop     dword ptr [rax+rax+00h]
0x18005c773  mov     rcx, rbx
0x18005c776  call    MSCryptFree
0x18005c77b  mov     rcx, [rbp+TokenHandle]; hObject
0x18005c77f  test    rcx, rcx
0x18005c782  jz      short loc_18005C790
0x18005c784  call    cs:__imp_CloseHandle
0x18005c78b  nop     dword ptr [rax+rax+00h]
0x18005c790  mov     rcx, [rbp+StringSid]; hMem
0x18005c794  call    cs:__imp_LocalFree
0x18005c79b  nop     dword ptr [rax+rax+00h]
0x18005c7a0  mov     rbx, [rsp+30h+arg_18]
0x18005c7a5  add     rsp, 30h
0x18005c7a9  pop     rbp
0x18005c7aa  retn
```
