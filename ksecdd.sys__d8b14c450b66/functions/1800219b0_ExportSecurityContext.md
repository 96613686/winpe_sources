# ExportSecurityContext

- ea: `0x1800219b0`
- end: `0x1800219e2`
- name: `ExportSecurityContext`
- size: `50`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, ULONG fFlags, PSecBuffer pPackedContext, void **pToken)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800219b0`
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
0x1800219b0  sub     rsp, 38h
0x1800219b4  test    rcx, rcx
0x1800219b7  jz      short loc_1800219D7
0x1800219b9  test    r8, r8
0x1800219bc  jz      short loc_1800219D7
0x1800219be  mov     [rsp+38h+var_18], r9
0x1800219c3  mov     r9, r8
0x1800219c6  mov     r8d, edx
0x1800219c9  mov     rdx, [rcx+8]
0x1800219cd  mov     rcx, [rcx]
0x1800219d0  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KKPEAU_SecBuffer@@PEAPEAX@Z$0FI@@KernelPackageCallValidatorWorkers@@SAJ_K0KPEAU_SecBuffer@@PEAPEAX@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,ulong,_SecBuffer *,void * *),88>::InvokeById(unsigned __int64,unsigned __int64,ulong,_SecBuffer *,void * *)
0x1800219d5  jmp     short loc_1800219DC
0x1800219d7  mov     eax, 0C000000Dh
0x1800219dc  add     rsp, 38h
0x1800219e0  retn
```
