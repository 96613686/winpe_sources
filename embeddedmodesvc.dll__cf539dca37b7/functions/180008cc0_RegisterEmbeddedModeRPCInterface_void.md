# RegisterEmbeddedModeRPCInterface(void)

- ea: `0x180008cc0`
- end: `0x180008dd9`
- name: `?RegisterEmbeddedModeRPCInterface@@YAJXZ`
- size: `281`
- prototype: `signed int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008018`

## callees

- `0x180008cc0`
- `0x18000902c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cec`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008ce2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008ce2`
- `RPCRT4!RpcServerInqBindings` at `0x180008d38`
- `RPCRT4!RpcServerInqBindings` at `0x180008d38`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180008dc6`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180008dc6`
- `RPCRT4!RpcBindingVectorFree` at `0x180008d88`
- `RPCRT4!RpcBindingVectorFree` at `0x180008daf`
- `RPCRT4!RpcBindingVectorFree` at `0x180008d88`
- `RPCRT4!RpcBindingVectorFree` at `0x180008daf`
- `RPCRT4!RpcEpRegisterW` at `0x180008da2`
- `RPCRT4!RpcEpRegisterW` at `0x180008da2`
- `RPCRT4!RpcServerUseProtseqW` at `0x180008d19`
- `RPCRT4!RpcServerUseProtseqW` at `0x180008d19`
- `RPCRT4!RpcServerRegisterIf3` at `0x180008d77`
- `RPCRT4!RpcServerRegisterIf3` at `0x180008d77`

## pseudocode

```c
signed int RegisterEmbeddedModeRPCInterface(void)
{
  signed int result; // eax
  RPC_STATUS v1; // eax
  int v2; // ecx
  RPC_STATUS v3; // ebx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+50h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+10h] BYREF

  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AU)(A;;GR;;;AC)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v1 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
    if ( v1 || (BindingVector = 0, (v1 = RpcServerInqBindings(&BindingVector)) != 0) )
    {
      v2 = v1;
    }
    else
    {
      v3 = RpcServerRegisterIf3(qword_18001C860, 0, 0, 41, 1234, 0, 0, SecurityDescriptor);
      if ( v3 )
      {
        RpcBindingVectorFree(&BindingVector);
      }
      else
      {
        v3 = RpcEpRegisterW(qword_18001C860, BindingVector, 0, 0);
        RpcBindingVectorFree(&BindingVector);
        if ( v3 )
          RpcServerUnregisterIfEx(qword_18001C860, 0, 1);
      }
      v2 = v3;
    }
    return RpcStatusToHresult(v2);
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180008cc0  push    rbx
0x180008cc2  sub     rsp, 40h
0x180008cc6  xor     r9d, r9d; SecurityDescriptorSize
0x180008cc9  mov     [rsp+48h+SecurityDescriptor], 0
0x180008cd2  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180008cd7  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AU)("...
0x180008cde  lea     edx, [r9+1]; StringSDRevision
0x180008ce2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180008ce8  test    eax, eax
0x180008cea  jnz     short loc_180008D08
0x180008cec  call    cs:__imp_GetLastError
0x180008cf2  test    eax, eax
0x180008cf4  jle     loc_180008DD3
0x180008cfa  movzx   eax, ax
0x180008cfd  or      eax, 80070000h
0x180008d02  add     rsp, 40h
0x180008d06  pop     rbx
0x180008d07  retn
0x180008d08  mov     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180008d0d  lea     rcx, Protseq; "ncalrpc"
0x180008d14  mov     edx, 0Ah; MaxCalls
0x180008d19  call    cs:__imp_RpcServerUseProtseqW
0x180008d1f  test    eax, eax
0x180008d21  jz      short loc_180008D2A
0x180008d23  mov     ecx, eax
0x180008d25  jmp     loc_180008DCE
0x180008d2a  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x180008d2f  mov     [rsp+48h+BindingVector], 0
0x180008d38  call    cs:__imp_RpcServerInqBindings
0x180008d3e  test    eax, eax
0x180008d40  jnz     short loc_180008D23
0x180008d42  mov     rax, [rsp+48h+SecurityDescriptor]
0x180008d47  lea     rcx, qword_18001C860
0x180008d4e  mov     [rsp+48h+var_10], rax
0x180008d53  mov     r9d, 29h ; ')'
0x180008d59  mov     [rsp+48h+var_18], 0
0x180008d62  xor     r8d, r8d
0x180008d65  mov     [rsp+48h+var_20], 0
0x180008d6d  xor     edx, edx
0x180008d6f  mov     [rsp+48h+var_28], 4D2h
0x180008d77  call    cs:__imp_RpcServerRegisterIf3
0x180008d7d  mov     ebx, eax
0x180008d7f  test    eax, eax
0x180008d81  jz      short loc_180008D90
0x180008d83  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x180008d88  call    cs:__imp_RpcBindingVectorFree
0x180008d8e  jmp     short loc_180008DCC
0x180008d90  mov     rdx, [rsp+48h+BindingVector]; BindingVector
0x180008d95  lea     rcx, qword_18001C860; IfSpec
0x180008d9c  xor     r9d, r9d; Annotation
0x180008d9f  xor     r8d, r8d; UuidVector
0x180008da2  call    cs:__imp_RpcEpRegisterW
0x180008da8  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x180008dad  mov     ebx, eax
0x180008daf  call    cs:__imp_RpcBindingVectorFree
0x180008db5  test    ebx, ebx
0x180008db7  jz      short loc_180008DCC
0x180008db9  xor     edx, edx; MgrTypeUuid
0x180008dbb  lea     rcx, qword_18001C860; IfSpec
0x180008dc2  lea     r8d, [rdx+1]; RundownContextHandles
0x180008dc6  call    cs:__imp_RpcServerUnregisterIfEx
0x180008dcc  mov     ecx, ebx; int
0x180008dce  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x180008dd3  add     rsp, 40h
0x180008dd7  pop     rbx
0x180008dd8  retn
```
