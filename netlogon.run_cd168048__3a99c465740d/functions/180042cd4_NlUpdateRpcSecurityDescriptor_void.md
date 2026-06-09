# NlUpdateRpcSecurityDescriptor(void)

- ea: `0x180042cd4`
- end: `0x180042e4b`
- name: `?NlUpdateRpcSecurityDescriptor@@YAXXZ`
- size: `375`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800423a4`
- `0x18005179c`

## callees

- `0x180007518`
- `0x180042cd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180042d71`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180042d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042d9c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042d22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042d22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042dc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042dc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042e2e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180042de0`
- `ntdll!RtlAcquireResourceExclusive` at `0x180042de0`
- `ntdll!RtlReleaseResource` at `0x180042e06`
- `ntdll!RtlReleaseResource` at `0x180042e06`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042d8c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180042d8c`

## string_xrefs

- `0x180042d36`: `Low resources when processing RpcDacl SDDL.  Using default SD.\n`
- `0x180042da8`: `The following error was encountered when processing RpcDacl SDDL: %#x\n`

## pseudocode

```c
void NlUpdateRpcSecurityDescriptor(void)
{
  WCHAR *v0; // rbx
  __int64 v1; // rax
  SIZE_T v2; // rdi
  WCHAR *v3; // rax
  DWORD LastError; // eax
  HLOCAL v5; // rdi
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  if ( !NlGlobalMemberWorkstation )
    return;
  v0 = 0;
  if ( qword_1800F82B8 )
  {
    v1 = -1;
    do
      ++v1;
    while ( *(_WORD *)(qword_1800F82B8 + 2 * v1) );
    v2 = (unsigned int)(2 * v1 + 18);
    v3 = (WCHAR *)LocalAlloc(0, v2);
    v0 = v3;
    if ( v3 )
    {
      *(_OWORD *)v3 = *(_OWORD *)L"O:SYG:SY";
      v3[8] = aOSygSy[8];
      _o_wcscat_s(v3, v2 >> 1, qword_1800F82B8);
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v0, 1u, &SecurityDescriptor, 0) )
        goto LABEL_11;
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"The following error was encountered when processing RpcDacl SDDL: %#x\n", LastError);
      if ( !SecurityDescriptor )
        goto LABEL_11;
      LocalFree(SecurityDescriptor);
    }
    else
    {
      NlPrintRoutine(0x100u, L"Low resources when processing RpcDacl SDDL.  Using default SD.\n");
    }
    SecurityDescriptor = 0;
  }
LABEL_11:
  RtlAcquireResourceExclusive(&NlGlobalRpcSecurityDescriptorLock, 1u);
  v5 = NlGlobalRpcSecurityDescriptor;
  NlGlobalRpcSecurityDescriptor = SecurityDescriptor;
  RtlReleaseResource(&NlGlobalRpcSecurityDescriptorLock);
  if ( v5 )
    LocalFree(v5);
  if ( v0 )
    LocalFree(v0);
}

```

## disassembly

```asm
0x180042cd4  mov     [rsp+arg_8], rbx
0x180042cd9  mov     [rsp+arg_10], rsi
0x180042cde  push    rdi
0x180042cdf  sub     rsp, 20h
0x180042ce3  xor     esi, esi
0x180042ce5  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x180042ceb  mov     [rsp+28h+SecurityDescriptor], rsi
0x180042cf0  jz      loc_180042E3A
0x180042cf6  mov     rcx, cs:qword_1800F82B8
0x180042cfd  mov     ebx, esi
0x180042cff  test    rcx, rcx
0x180042d02  jz      loc_180042DD7
0x180042d08  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042d0c  inc     rax
0x180042d0f  cmp     [rcx+rax*2], si
0x180042d13  jnz     short loc_180042D0C
0x180042d15  lea     eax, ds:12h[rax*2]
0x180042d1c  xor     ecx, ecx; uFlags
0x180042d1e  mov     edx, eax; uBytes
0x180042d20  mov     edi, eax
0x180042d22  call    cs:__imp_LocalAlloc
0x180042d29  nop     dword ptr [rax+rax+00h]
0x180042d2e  mov     rbx, rax
0x180042d31  test    rax, rax
0x180042d34  jnz     short loc_180042D4C
0x180042d36  lea     rdx, aLowResourcesWh; "Low resources when processing RpcDacl S"...
0x180042d3d  mov     ecx, 100h; unsigned int
0x180042d42  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042d47  jmp     loc_180042DD2
0x180042d4c  movups  xmm0, xmmword ptr cs:aOSygSy; "O:SYG:SY"
0x180042d53  shr     rdi, 1
0x180042d56  mov     rcx, rbx
0x180042d59  mov     rdx, rdi
0x180042d5c  movups  xmmword ptr [rax], xmm0
0x180042d5f  movzx   eax, word ptr cs:aOSygSy+10h; ""
0x180042d66  mov     [rbx+10h], ax
0x180042d6a  mov     r8, cs:qword_1800F82B8
0x180042d71  call    cs:__imp__o_wcscat_s
0x180042d78  nop     dword ptr [rax+rax+00h]
0x180042d7d  xor     r9d, r9d; SecurityDescriptorSize
0x180042d80  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x180042d85  mov     rcx, rbx; StringSecurityDescriptor
0x180042d88  lea     edx, [r9+1]; StringSDRevision
0x180042d8c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180042d93  nop     dword ptr [rax+rax+00h]
0x180042d98  test    eax, eax
0x180042d9a  jnz     short loc_180042DD7
0x180042d9c  call    cs:__imp_GetLastError
0x180042da3  nop     dword ptr [rax+rax+00h]
0x180042da8  lea     rdx, aTheFollowingEr_1; "The following error was encountered whe"...
0x180042daf  mov     ecx, 100h; unsigned int
0x180042db4  mov     r8d, eax
0x180042db7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180042dbc  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x180042dc1  test    rcx, rcx
0x180042dc4  jz      short loc_180042DD7
0x180042dc6  call    cs:__imp_LocalFree
0x180042dcd  nop     dword ptr [rax+rax+00h]
0x180042dd2  mov     [rsp+28h+SecurityDescriptor], rsi
0x180042dd7  mov     dl, 1; Wait
0x180042dd9  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180042de0  call    cs:__imp_RtlAcquireResourceExclusive
0x180042de7  nop     dword ptr [rax+rax+00h]
0x180042dec  mov     rax, [rsp+28h+SecurityDescriptor]
0x180042df1  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180042df8  mov     rdi, cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA; void * NlGlobalRpcSecurityDescriptor
0x180042dff  mov     cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA, rax; void * NlGlobalRpcSecurityDescriptor
0x180042e06  call    cs:__imp_RtlReleaseResource
0x180042e0d  nop     dword ptr [rax+rax+00h]
0x180042e12  test    rdi, rdi
0x180042e15  jz      short loc_180042E26
0x180042e17  mov     rcx, rdi; hMem
0x180042e1a  call    cs:__imp_LocalFree
0x180042e21  nop     dword ptr [rax+rax+00h]
0x180042e26  test    rbx, rbx
0x180042e29  jz      short loc_180042E3A
0x180042e2b  mov     rcx, rbx; hMem
0x180042e2e  call    cs:__imp_LocalFree
0x180042e35  nop     dword ptr [rax+rax+00h]
0x180042e3a  mov     rbx, [rsp+28h+arg_8]
0x180042e3f  mov     rsi, [rsp+28h+arg_10]
0x180042e44  add     rsp, 20h
0x180042e48  pop     rdi
0x180042e49  retn
```
