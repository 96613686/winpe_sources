# CompleteAuthToken

- ea: `0x180029300`
- end: `0x18002932a`
- name: `CompleteAuthToken`
- size: `42`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, PSecBufferDesc pToken)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800290c4`
- `0x180029300`

## pseudocode

```c
SECURITY_STATUS __stdcall CompleteAuthToken(PCtxtHandle phContext, PSecBufferDesc pToken)
{
  if ( phContext && pToken )
    return KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,_SecBufferDesc *),80>::InvokeById(
             phContext->dwLower,
             phContext->dwUpper,
             pToken);
  else
    return -1073741811;
}

```

## disassembly

```asm
0x180029300  sub     rsp, 28h
0x180029304  test    rcx, rcx
0x180029307  jz      short loc_18002931F
0x180029309  test    rdx, rdx
0x18002930c  jz      short loc_18002931F
0x18002930e  mov     r8, rdx
0x180029311  mov     rdx, [rcx+8]
0x180029315  mov     rcx, [rcx]
0x180029318  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KPEAU_SecBufferDesc@@@Z$0FA@@KernelPackageCallValidatorWorkers@@SAJ_K0PEAU_SecBufferDesc@@@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,_SecBufferDesc *),80>::InvokeById(unsigned __int64,unsigned __int64,_SecBufferDesc *)
0x18002931d  jmp     short loc_180029324
0x18002931f  mov     eax, 0C000000Dh
0x180029324  add     rsp, 28h
0x180029328  retn
```
