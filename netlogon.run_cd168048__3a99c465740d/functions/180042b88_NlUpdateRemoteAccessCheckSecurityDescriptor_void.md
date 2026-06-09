# NlUpdateRemoteAccessCheckSecurityDescriptor(void)

- ea: `0x180042b88`
- end: `0x180042ccd`
- name: `?NlUpdateRemoteAccessCheckSecurityDescriptor@@YAXXZ`
- size: `325`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800423a4`
- `0x18005179c`

## callees

- `0x180007518`
- `0x180042b88`
- `0x180078ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042bc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042bea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042bea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042cba`
- `ntdll!RtlAcquireResourceExclusive` at `0x180042c7b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180042c7b`
- `ntdll!RtlReleaseResource` at `0x180042ca6`
- `ntdll!RtlReleaseResource` at `0x180042ca6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042bb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042c23`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042bb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042c23`

## string_xrefs

- `0x180042bcc`: `The following error was encountered when processing RemoteAccessCheckDacl SDDL: %#x\n`
- `0x180042c3f`: `The following error was encountered when processing RemoteAccessCheckDacl SDDL: %#x\n`

## pseudocode

```c
void NlUpdateRemoteAccessCheckSecurityDescriptor(void)
{
  int v0; // ebx
  DWORD LastError; // eax
  DWORD v2; // eax
  HLOCAL v3; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  if ( !StringSecurityDescriptor )
    goto LABEL_15;
  v0 = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    NlPrintRoutine(
      0x100u,
      L"The following error was encountered when processing RemoteAccessCheckDacl SDDL: %#x\n",
      LastError);
    if ( SecurityDescriptor )
    {
      LocalFree(SecurityDescriptor);
      SecurityDescriptor = 0;
    }
    else
    {
      v0 = 1;
    }
  }
  if ( !StringSecurityDescriptor || v0 )
  {
LABEL_15:
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;GA;;;BA)(A;;GA;;;IU)(A;;GA;;;AA)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      v2 = GetLastError();
      NlPrintRoutine(
        0x100u,
        L"The following error was encountered when processing RemoteAccessCheckDacl SDDL: %#x\n",
        v2);
      if ( SecurityDescriptor )
      {
        LocalFree(SecurityDescriptor);
        SecurityDescriptor = 0;
      }
    }
  }
  RtlAcquireResourceExclusive(&NlGlobalRemoteAccessCheckSecurityDescriptorLock, 1u);
  v3 = NlGlobalRemoteAccessCheckSecurityDescriptor;
  NlGlobalRemoteAccessCheckSecurityDescriptor = SecurityDescriptor;
  NlStartOrRestartRemoteAccessCheck();
  RtlReleaseResource(&NlGlobalRemoteAccessCheckSecurityDescriptorLock);
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x180042b88  push    rbx
0x180042b8a  sub     rsp, 20h
0x180042b8e  mov     rcx, cs:StringSecurityDescriptor; StringSecurityDescriptor
0x180042b95  mov     [rsp+28h+SecurityDescriptor], 0
0x180042b9e  test    rcx, rcx
0x180042ba1  jz      short loc_180042C10
0x180042ba3  xor     ebx, ebx
0x180042ba5  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180042baa  xor     r9d, r9d; SecurityDescriptorSize
0x180042bad  lea     edx, [rbx+1]; StringSDRevision
0x180042bb0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180042bb7  nop     dword ptr [rax+rax+00h]
0x180042bbc  test    eax, eax
0x180042bbe  jnz     short loc_180042C02
0x180042bc0  call    cs:__imp_GetLastError
0x180042bc7  nop     dword ptr [rax+rax+00h]
0x180042bcc  lea     rdx, aTheFollowingEr; "The following error was encountered whe"...
0x180042bd3  mov     ecx, 100h; unsigned int
0x180042bd8  mov     r8d, eax
0x180042bdb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042be0  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x180042be5  test    rcx, rcx
0x180042be8  jz      short loc_180042BFD
0x180042bea  call    cs:__imp_LocalFree
0x180042bf1  nop     dword ptr [rax+rax+00h]
0x180042bf6  mov     [rsp+28h+SecurityDescriptor], rbx
0x180042bfb  jmp     short loc_180042C02
0x180042bfd  mov     ebx, 1
0x180042c02  cmp     cs:StringSecurityDescriptor, 0
0x180042c0a  jz      short loc_180042C10
0x180042c0c  test    ebx, ebx
0x180042c0e  jz      short loc_180042C72
0x180042c10  xor     r9d, r9d; SecurityDescriptorSize
0x180042c13  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180042c18  lea     rcx, aDAGaBaAGaIuAGa; "D:(A;;GA;;;BA)(A;;GA;;;IU)(A;;GA;;;AA)"
0x180042c1f  lea     edx, [r9+1]; StringSDRevision
0x180042c23  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180042c2a  nop     dword ptr [rax+rax+00h]
0x180042c2f  test    eax, eax
0x180042c31  jnz     short loc_180042C72
0x180042c33  call    cs:__imp_GetLastError
0x180042c3a  nop     dword ptr [rax+rax+00h]
0x180042c3f  lea     rdx, aTheFollowingEr; "The following error was encountered whe"...
0x180042c46  mov     ecx, 100h; unsigned int
0x180042c4b  mov     r8d, eax
0x180042c4e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042c53  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x180042c58  test    rcx, rcx
0x180042c5b  jz      short loc_180042C72
0x180042c5d  call    cs:__imp_LocalFree
0x180042c64  nop     dword ptr [rax+rax+00h]
0x180042c69  mov     [rsp+28h+SecurityDescriptor], 0
0x180042c72  mov     dl, 1; Wait
0x180042c74  lea     rcx, ?NlGlobalRemoteAccessCheckSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180042c7b  call    cs:__imp_RtlAcquireResourceExclusive
0x180042c82  nop     dword ptr [rax+rax+00h]
0x180042c87  mov     rax, [rsp+28h+SecurityDescriptor]
0x180042c8c  mov     rbx, cs:?NlGlobalRemoteAccessCheckSecurityDescriptor@@3PEAXEA; void * NlGlobalRemoteAccessCheckSecurityDescriptor
0x180042c93  mov     cs:?NlGlobalRemoteAccessCheckSecurityDescriptor@@3PEAXEA, rax; void * NlGlobalRemoteAccessCheckSecurityDescriptor
0x180042c9a  call    ?NlStartOrRestartRemoteAccessCheck@@YAKXZ; NlStartOrRestartRemoteAccessCheck(void)
0x180042c9f  lea     rcx, ?NlGlobalRemoteAccessCheckSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180042ca6  call    cs:__imp_RtlReleaseResource
0x180042cad  nop     dword ptr [rax+rax+00h]
0x180042cb2  test    rbx, rbx
0x180042cb5  jz      short loc_180042CC6
0x180042cb7  mov     rcx, rbx; hMem
0x180042cba  call    cs:__imp_LocalFree
0x180042cc1  nop     dword ptr [rax+rax+00h]
0x180042cc6  add     rsp, 20h
0x180042cca  pop     rbx
0x180042ccb  retn
```
