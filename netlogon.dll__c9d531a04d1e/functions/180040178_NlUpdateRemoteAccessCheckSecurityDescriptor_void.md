# NlUpdateRemoteAccessCheckSecurityDescriptor(void)

- ea: `0x180040178`
- end: `0x180040286`
- name: `?NlUpdateRemoteAccessCheckSecurityDescriptor@@YAXXZ`
- size: `270`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003fa34`
- `0x18004e118`

## callees

- `0x180007278`
- `0x180040178`
- `0x1800737cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800401aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004020b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800401aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004020b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800401ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004022f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004027a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800401ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004022f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004027a`
- `ntdll!RtlAcquireResourceExclusive` at `0x180040247`
- `ntdll!RtlAcquireResourceExclusive` at `0x180040247`
- `ntdll!RtlReleaseResource` at `0x18004026c`
- `ntdll!RtlReleaseResource` at `0x18004026c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800401a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180040201`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800401a0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180040201`

## string_xrefs

- `0x1800401b0`: `The following error was encountered when processing RemoteAccessCheckDacl SDDL: %#x\n`
- `0x180040211`: `The following error was encountered when processing RemoteAccessCheckDacl SDDL: %#x\n`

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
0x180040178  push    rbx
0x18004017a  sub     rsp, 20h
0x18004017e  mov     rcx, cs:StringSecurityDescriptor; StringSecurityDescriptor
0x180040185  mov     [rsp+28h+SecurityDescriptor], 0
0x18004018e  test    rcx, rcx
0x180040191  jz      short loc_1800401EE
0x180040193  xor     ebx, ebx
0x180040195  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x18004019a  xor     r9d, r9d; SecurityDescriptorSize
0x18004019d  lea     edx, [rbx+1]; StringSDRevision
0x1800401a0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800401a6  test    eax, eax
0x1800401a8  jnz     short loc_1800401E0
0x1800401aa  call    cs:__imp_GetLastError
0x1800401b0  lea     rdx, aTheFollowingEr; "The following error was encountered whe"...
0x1800401b7  mov     ecx, 100h; unsigned int
0x1800401bc  mov     r8d, eax
0x1800401bf  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800401c4  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x1800401c9  test    rcx, rcx
0x1800401cc  jz      short loc_1800401DB
0x1800401ce  call    cs:__imp_LocalFree
0x1800401d4  mov     [rsp+28h+SecurityDescriptor], rbx
0x1800401d9  jmp     short loc_1800401E0
0x1800401db  mov     ebx, 1
0x1800401e0  cmp     cs:StringSecurityDescriptor, 0
0x1800401e8  jz      short loc_1800401EE
0x1800401ea  test    ebx, ebx
0x1800401ec  jz      short loc_18004023E
0x1800401ee  xor     r9d, r9d; SecurityDescriptorSize
0x1800401f1  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x1800401f6  lea     rcx, aDAGaBaAGaIuAGa; "D:(A;;GA;;;BA)(A;;GA;;;IU)(A;;GA;;;AA)"
0x1800401fd  lea     edx, [r9+1]; StringSDRevision
0x180040201  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180040207  test    eax, eax
0x180040209  jnz     short loc_18004023E
0x18004020b  call    cs:__imp_GetLastError
0x180040211  lea     rdx, aTheFollowingEr; "The following error was encountered whe"...
0x180040218  mov     ecx, 100h; unsigned int
0x18004021d  mov     r8d, eax
0x180040220  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040225  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x18004022a  test    rcx, rcx
0x18004022d  jz      short loc_18004023E
0x18004022f  call    cs:__imp_LocalFree
0x180040235  mov     [rsp+28h+SecurityDescriptor], 0
0x18004023e  mov     dl, 1; Wait
0x180040240  lea     rcx, ?NlGlobalRemoteAccessCheckSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180040247  call    cs:__imp_RtlAcquireResourceExclusive
0x18004024d  mov     rax, [rsp+28h+SecurityDescriptor]
0x180040252  mov     rbx, cs:?NlGlobalRemoteAccessCheckSecurityDescriptor@@3PEAXEA; void * NlGlobalRemoteAccessCheckSecurityDescriptor
0x180040259  mov     cs:?NlGlobalRemoteAccessCheckSecurityDescriptor@@3PEAXEA, rax; void * NlGlobalRemoteAccessCheckSecurityDescriptor
0x180040260  call    ?NlStartOrRestartRemoteAccessCheck@@YAKXZ; NlStartOrRestartRemoteAccessCheck(void)
0x180040265  lea     rcx, ?NlGlobalRemoteAccessCheckSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x18004026c  call    cs:__imp_RtlReleaseResource
0x180040272  test    rbx, rbx
0x180040275  jz      short loc_180040280
0x180040277  mov     rcx, rbx; hMem
0x18004027a  call    cs:__imp_LocalFree
0x180040280  add     rsp, 20h
0x180040284  pop     rbx
0x180040285  retn
```
