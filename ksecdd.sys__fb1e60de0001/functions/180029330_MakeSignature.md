# MakeSignature

- ea: `0x180029330`
- end: `0x180029362`
- name: `MakeSignature`
- size: `50`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int fQOP, PSecBufferDesc pMessage, unsigned int MessageSeqNo)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180029008`
- `0x180029330`

## pseudocode

```c
SECURITY_STATUS __stdcall MakeSignature(
        PCtxtHandle phContext,
        unsigned int fQOP,
        PSecBufferDesc pMessage,
        unsigned int MessageSeqNo)
{
  if ( phContext && pMessage )
    return KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,unsigned long,_SecBufferDesc *,unsigned long),32>::InvokeById(
             phContext->dwLower,
             phContext->dwUpper,
             fQOP,
             (_DWORD)pMessage,
             MessageSeqNo);
  else
    return -2146893055;
}

```

## disassembly

```asm
0x180029330  sub     rsp, 38h
0x180029334  test    rcx, rcx
0x180029337  jz      short loc_180029357
0x180029339  test    r8, r8
0x18002933c  jz      short loc_180029357
0x18002933e  mov     [rsp+38h+var_18], r9d
0x180029343  mov     r9, r8
0x180029346  mov     r8d, edx
0x180029349  mov     rdx, [rcx+8]
0x18002934d  mov     rcx, [rcx]
0x180029350  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KKPEAU_SecBufferDesc@@K@Z$0CA@@KernelPackageCallValidatorWorkers@@SAJ_K0KPEAU_SecBufferDesc@@K@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,ulong,_SecBufferDesc *,ulong),32>::InvokeById(unsigned __int64,unsigned __int64,ulong,_SecBufferDesc *,ulong)
0x180029355  jmp     short loc_18002935C
0x180029357  mov     eax, 80090301h
0x18002935c  add     rsp, 38h
0x180029360  retn
```
