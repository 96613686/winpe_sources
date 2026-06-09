# SIDKeyEnableLRpcInterface(void)

- ea: `0x18003b5a4`
- end: `0x18003b6f5`
- name: `?SIDKeyEnableLRpcInterface@@YAJXZ`
- size: `337`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800280a8`

## callees

- `0x18003b5a4`
- `0x18003baa0`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x18003b6db`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18003b6db`
- `RPCRT4!RpcServerRegisterIf3` at `0x18003b68a`
- `RPCRT4!RpcServerRegisterIf3` at `0x18003b68a`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18003b627`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x18003b627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b5d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b6ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b6ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003b5c7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003b5c7`

## string_xrefs

- `0x18003b614`: `SidKey Local End Point`

## pseudocode

```c
__int64 SIDKeyEnableLRpcInterface(void)
{
  int v0; // edi
  int LastError; // ebx
  const char *v2; // r8
  RPC_STATUS v3; // eax
  const char *v4; // r8
  unsigned int v5; // r9d
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;S-1-15-3-8)(A;;GR;;;S-1-15-3-3)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v3 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"SidKey Local End Point", SecurityDescriptor);
    if ( v3 )
    {
      v5 = 347;
    }
    else
    {
      v3 = RpcServerRegisterIf3(qword_1800404E0, 0, 0, 41, 1234, 0, &ProtectCallback, SecurityDescriptor);
      if ( !v3 || v3 == 1713 )
      {
        v0 = 1;
        LastError = 0;
        goto LABEL_11;
      }
      v5 = 376;
    }
    LastError = (unsigned __int16)v3 | 0x80010000;
    SidKeyDebugTraceError(LastError, "hr", v4, v5);
    goto LABEL_11;
  }
  LastError = GetLastError();
  SidKeyDebugTraceError(LastError, "dwStatus", v2, 0x146u);
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_11:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( LastError < 0 && v0 )
    RpcServerUnregisterIfEx(qword_1800404E0, 0, 1);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18003b5a4  mov     [rsp+arg_8], rbx
0x18003b5a9  push    rdi
0x18003b5aa  sub     rsp, 40h
0x18003b5ae  xor     edi, edi
0x18003b5b0  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x18003b5b5  xor     r9d, r9d; SecurityDescriptorSize
0x18003b5b8  mov     [rsp+48h+SecurityDescriptor], rdi
0x18003b5bd  lea     rcx, aDAGrgwgxWdAGrg_0; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x18003b5c4  lea     edx, [rdi+1]; StringSDRevision
0x18003b5c7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003b5ce  nop     dword ptr [rax+rax+00h]
0x18003b5d3  test    eax, eax
0x18003b5d5  jnz     short loc_18003B60F
0x18003b5d7  call    cs:__imp_GetLastError
0x18003b5de  nop     dword ptr [rax+rax+00h]
0x18003b5e3  mov     r9d, 146h; unsigned int
0x18003b5e9  lea     rdx, aDwstatus; "dwStatus"
0x18003b5f0  mov     ecx, eax; unsigned int
0x18003b5f2  mov     ebx, eax
0x18003b5f4  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18003b5f9  test    ebx, ebx
0x18003b5fb  jle     loc_18003B6B0
0x18003b601  movzx   ebx, bx
0x18003b604  or      ebx, 80070000h
0x18003b60a  jmp     loc_18003B6B0
0x18003b60f  mov     r9, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x18003b614  lea     r8, aSidkeyLocalEnd; "SidKey Local End Point"
0x18003b61b  mov     edx, 0Ah; MaxCalls
0x18003b620  lea     rcx, Protseq; "ncalrpc"
0x18003b627  call    cs:__imp_RpcServerUseProtseqEpW
0x18003b62e  nop     dword ptr [rax+rax+00h]
0x18003b633  test    eax, eax
0x18003b635  jz      short loc_18003B656
0x18003b637  mov     r9d, 15Bh; unsigned int
0x18003b63d  movzx   ebx, ax
0x18003b640  lea     rdx, aHr; "hr"
0x18003b647  or      ebx, 80010000h
0x18003b64d  mov     ecx, ebx; unsigned int
0x18003b64f  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18003b654  jmp     short loc_18003B6B0
0x18003b656  mov     rax, [rsp+48h+SecurityDescriptor]
0x18003b65b  lea     rcx, qword_1800404E0
0x18003b662  mov     [rsp+48h+var_10], rax
0x18003b667  mov     r9d, 29h ; ')'
0x18003b66d  lea     rax, _ProtectCallback
0x18003b674  xor     r8d, r8d
0x18003b677  mov     [rsp+48h+var_18], rax
0x18003b67c  xor     edx, edx
0x18003b67e  mov     [rsp+48h+var_20], edi
0x18003b682  mov     [rsp+48h+var_28], 4D2h
0x18003b68a  call    cs:__imp_RpcServerRegisterIf3
0x18003b691  nop     dword ptr [rax+rax+00h]
0x18003b696  test    eax, eax
0x18003b698  jz      short loc_18003B6A9
0x18003b69a  cmp     eax, 6B1h
0x18003b69f  jz      short loc_18003B6A9
0x18003b6a1  mov     r9d, 178h
0x18003b6a7  jmp     short loc_18003B63D
0x18003b6a9  mov     edi, 1
0x18003b6ae  xor     ebx, ebx
0x18003b6b0  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x18003b6b5  test    rcx, rcx
0x18003b6b8  jz      short loc_18003B6C6
0x18003b6ba  call    cs:__imp_LocalFree
0x18003b6c1  nop     dword ptr [rax+rax+00h]
0x18003b6c6  test    ebx, ebx
0x18003b6c8  jns     short loc_18003B6E7
0x18003b6ca  test    edi, edi
0x18003b6cc  jz      short loc_18003B6E7
0x18003b6ce  xor     edx, edx; MgrTypeUuid
0x18003b6d0  lea     rcx, qword_1800404E0; IfSpec
0x18003b6d7  lea     r8d, [rdx+1]; RundownContextHandles
0x18003b6db  call    cs:__imp_RpcServerUnregisterIfEx
0x18003b6e2  nop     dword ptr [rax+rax+00h]
0x18003b6e7  mov     eax, ebx
0x18003b6e9  mov     rbx, [rsp+48h+arg_8]
0x18003b6ee  add     rsp, 40h
0x18003b6f2  pop     rdi
0x18003b6f3  retn
```
