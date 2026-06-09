# NlUpdateRpcSecurityDescriptor(void)

- ea: `0x18004028c`
- end: `0x1800403c9`
- name: `?NlUpdateRpcSecurityDescriptor@@YAXXZ`
- size: `317`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003fa34`
- `0x18004e118`

## callees

- `0x180007278`
- `0x18004028c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180040320`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180040320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004033f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004033f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800402da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800402da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040363`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800403a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800403b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040363`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800403a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800403b3`
- `ntdll!RtlAcquireResourceExclusive` at `0x180040377`
- `ntdll!RtlAcquireResourceExclusive` at `0x180040377`
- `ntdll!RtlReleaseResource` at `0x180040397`
- `ntdll!RtlReleaseResource` at `0x180040397`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180040335`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180040335`

## string_xrefs

- `0x1800402e8`: `Low resources when processing RpcDacl SDDL.  Using default SD.\n`
- `0x180040345`: `The following error was encountered when processing RpcDacl SDDL: %#x\n`

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
  if ( qword_1800F12B8 )
  {
    v1 = -1;
    do
      ++v1;
    while ( *(_WORD *)(qword_1800F12B8 + 2 * v1) );
    v2 = (unsigned int)(2 * v1 + 18);
    v3 = (WCHAR *)LocalAlloc(0, v2);
    v0 = v3;
    if ( v3 )
    {
      *(_OWORD *)v3 = *(_OWORD *)L"O:SYG:SY";
      v3[8] = aOSygSy[8];
      _o_wcscat_s(v3, v2 >> 1, qword_1800F12B8);
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
0x18004028c  mov     [rsp+arg_8], rbx
0x180040291  mov     [rsp+arg_10], rsi
0x180040296  push    rdi
0x180040297  sub     rsp, 20h
0x18004029b  xor     esi, esi
0x18004029d  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x1800402a3  mov     [rsp+28h+SecurityDescriptor], rsi
0x1800402a8  jz      loc_1800403B9
0x1800402ae  mov     rcx, cs:qword_1800F12B8
0x1800402b5  mov     ebx, esi
0x1800402b7  test    rcx, rcx
0x1800402ba  jz      loc_18004036E
0x1800402c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800402c4  inc     rax
0x1800402c7  cmp     [rcx+rax*2], si
0x1800402cb  jnz     short loc_1800402C4
0x1800402cd  lea     eax, ds:12h[rax*2]
0x1800402d4  xor     ecx, ecx; uFlags
0x1800402d6  mov     edx, eax; uBytes
0x1800402d8  mov     edi, eax
0x1800402da  call    cs:__imp_LocalAlloc
0x1800402e0  mov     rbx, rax
0x1800402e3  test    rax, rax
0x1800402e6  jnz     short loc_1800402FB
0x1800402e8  lea     rdx, aLowResourcesWh; "Low resources when processing RpcDacl S"...
0x1800402ef  mov     ecx, 100h; unsigned int
0x1800402f4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800402f9  jmp     short loc_180040369
0x1800402fb  movups  xmm0, xmmword ptr cs:aOSygSy; "O:SYG:SY"
0x180040302  shr     rdi, 1
0x180040305  mov     rcx, rbx
0x180040308  mov     rdx, rdi
0x18004030b  movups  xmmword ptr [rax], xmm0
0x18004030e  movzx   eax, word ptr cs:aOSygSy+10h; ""
0x180040315  mov     [rbx+10h], ax
0x180040319  mov     r8, cs:qword_1800F12B8
0x180040320  call    cs:__imp__o_wcscat_s
0x180040326  xor     r9d, r9d; SecurityDescriptorSize
0x180040329  lea     r8, [rsp+28h+SecurityDescriptor]; SecurityDescriptor
0x18004032e  mov     rcx, rbx; StringSecurityDescriptor
0x180040331  lea     edx, [r9+1]; StringSDRevision
0x180040335  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004033b  test    eax, eax
0x18004033d  jnz     short loc_18004036E
0x18004033f  call    cs:__imp_GetLastError
0x180040345  lea     rdx, aTheFollowingEr_1; "The following error was encountered whe"...
0x18004034c  mov     ecx, 100h; unsigned int
0x180040351  mov     r8d, eax
0x180040354  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040359  mov     rcx, [rsp+28h+SecurityDescriptor]; hMem
0x18004035e  test    rcx, rcx
0x180040361  jz      short loc_18004036E
0x180040363  call    cs:__imp_LocalFree
0x180040369  mov     [rsp+28h+SecurityDescriptor], rsi
0x18004036e  mov     dl, 1; Wait
0x180040370  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180040377  call    cs:__imp_RtlAcquireResourceExclusive
0x18004037d  mov     rax, [rsp+28h+SecurityDescriptor]
0x180040382  lea     rcx, ?NlGlobalRpcSecurityDescriptorLock@@3U_RTL_RESOURCE@@A; Resource
0x180040389  mov     rdi, cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA; void * NlGlobalRpcSecurityDescriptor
0x180040390  mov     cs:?NlGlobalRpcSecurityDescriptor@@3PEAXEA, rax; void * NlGlobalRpcSecurityDescriptor
0x180040397  call    cs:__imp_RtlReleaseResource
0x18004039d  test    rdi, rdi
0x1800403a0  jz      short loc_1800403AB
0x1800403a2  mov     rcx, rdi; hMem
0x1800403a5  call    cs:__imp_LocalFree
0x1800403ab  test    rbx, rbx
0x1800403ae  jz      short loc_1800403B9
0x1800403b0  mov     rcx, rbx; hMem
0x1800403b3  call    cs:__imp_LocalFree
0x1800403b9  mov     rbx, [rsp+28h+arg_8]
0x1800403be  mov     rsi, [rsp+28h+arg_10]
0x1800403c3  add     rsp, 20h
0x1800403c7  pop     rdi
0x1800403c8  retn
```
