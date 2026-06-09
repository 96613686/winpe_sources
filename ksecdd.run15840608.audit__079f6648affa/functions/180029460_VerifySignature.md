# VerifySignature

- ea: `0x180029460`
- end: `0x180029492`
- name: `VerifySignature`
- size: `50`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, PSecBufferDesc pMessage, unsigned int MessageSeqNo, unsigned int *pfQOP)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180029180`
- `0x180029460`

## pseudocode

```c
SECURITY_STATUS __stdcall VerifySignature(
        PCtxtHandle phContext,
        PSecBufferDesc pMessage,
        unsigned int MessageSeqNo,
        unsigned int *pfQOP)
{
  if ( phContext && pMessage )
    return KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,_SecBufferDesc *,unsigned long,unsigned long *),40>::InvokeById(
             phContext->dwLower,
             phContext->dwUpper,
             (_DWORD)pMessage,
             MessageSeqNo,
             (__int64)pfQOP);
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180029460  sub     rsp, 38h
0x180029464  test    rcx, rcx
0x180029467  jz      short loc_180029487
0x180029469  test    rdx, rdx
0x18002946c  jz      short loc_180029487
0x18002946e  mov     [rsp+38h+var_18], r9
0x180029473  mov     r9d, r8d
0x180029476  mov     r8, rdx
0x180029479  mov     rdx, [rcx+8]
0x18002947d  mov     rcx, [rcx]
0x180029480  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KPEAU_SecBufferDesc@@KPEAK@Z$0CI@@KernelPackageCallValidatorWorkers@@SAJ_K0PEAU_SecBufferDesc@@KPEAK@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,_SecBufferDesc *,ulong,ulong *),40>::InvokeById(unsigned __int64,unsigned __int64,_SecBufferDesc *,ulong,ulong *)
0x180029485  jmp     short loc_18002948C
0x180029487  mov     eax, 80090301h
0x18002948c  add     rsp, 38h
0x180029490  retn
```
