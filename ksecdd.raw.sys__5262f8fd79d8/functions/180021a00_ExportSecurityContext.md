# ExportSecurityContext

- ea: `0x180021a00`
- end: `0x180021a32`
- name: `ExportSecurityContext`
- size: `50`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, ULONG fFlags, PSecBuffer pPackedContext, void **pToken)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180021a00`
- `0x180029d80`

## pseudocode

```c
SECURITY_STATUS __stdcall ExportSecurityContext(
        PCtxtHandle phContext,
        ULONG fFlags,
        PSecBuffer pPackedContext,
        void **pToken)
{
  if ( phContext && pPackedContext )
    return KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,unsigned long,_SecBuffer *,void * *),88>::InvokeById(
             phContext->dwLower,
             phContext->dwUpper,
             fFlags,
             (_DWORD)pPackedContext,
             (__int64)pToken);
  else
    return -1073741811;
}

```

## disassembly

```asm
0x180021a00  sub     rsp, 38h
0x180021a04  test    rcx, rcx
0x180021a07  jz      short loc_180021A27
0x180021a09  test    r8, r8
0x180021a0c  jz      short loc_180021A27
0x180021a0e  mov     [rsp+38h+var_18], r9
0x180021a13  mov     r9, r8
0x180021a16  mov     r8d, edx
0x180021a19  mov     rdx, [rcx+8]
0x180021a1d  mov     rcx, [rcx]
0x180021a20  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KKPEAU_SecBuffer@@PEAPEAX@Z$0FI@@KernelPackageCallValidatorWorkers@@SAJ_K0KPEAU_SecBuffer@@PEAPEAX@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,ulong,_SecBuffer *,void * *),88>::InvokeById(unsigned __int64,unsigned __int64,ulong,_SecBuffer *,void * *)
0x180021a25  jmp     short loc_180021A2C
0x180021a27  mov     eax, 0C000000Dh
0x180021a2c  add     rsp, 38h
0x180021a30  retn
```
