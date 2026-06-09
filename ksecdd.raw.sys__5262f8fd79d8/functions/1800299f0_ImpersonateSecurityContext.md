# ImpersonateSecurityContext

- ea: `0x1800299f0`
- end: `0x180029a8b`
- name: `ImpersonateSecurityContext`
- size: `155`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007ba8`
- `0x1800299f0`
- `0x180029aa0`

## import_xrefs

- `ntoskrnl!PsImpersonateClient` at `0x180029a79`
- `ntoskrnl!PsImpersonateClient` at `0x180029a79`
- `ntoskrnl!SeTokenImpersonationLevel` at `0x180029a55`
- `ntoskrnl!SeTokenImpersonationLevel` at `0x180029a55`

## pseudocode

```c
SECURITY_STATUS __stdcall ImpersonateSecurityContext(PCtxtHandle phContext)
{
  SECURITY_STATUS result; // eax
  SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // eax
  PACCESS_TOKEN Token; // [rsp+40h] [rbp+8h] BYREF

  Token = 0;
  if ( phContext )
  {
    result = KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,void * *,void * *),64>::InvokeById(
               phContext->dwLower,
               phContext->dwUpper,
               0,
               &Token);
    if ( result >= 0 )
    {
      ImpersonationLevel = (unsigned int)SeTokenImpersonationLevel(Token);
      return PsImpersonateClient(KeGetCurrentThread(), Token, 0, 0, ImpersonationLevel);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 14, &WPP_bf88770bd570357164879d008cd144d3_Traceguids);
    return -1073741811;
  }
  return result;
}

```

## disassembly

```asm
0x1800299f0  sub     rsp, 38h
0x1800299f4  mov     [rsp+38h+Token], 0
0x1800299fd  test    rcx, rcx
0x180029a00  jnz     short loc_180029A38
0x180029a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a09  lea     rax, WPP_GLOBAL_Control
0x180029a10  cmp     rcx, rax
0x180029a13  jz      short loc_180029A31
0x180029a15  mov     eax, [rcx+2Ch]
0x180029a18  test    al, 1
0x180029a1a  jz      short loc_180029A31
0x180029a1c  mov     rcx, [rcx+18h]
0x180029a20  lea     r8, WPP_bf88770bd570357164879d008cd144d3_Traceguids
0x180029a27  mov     edx, 0Eh
0x180029a2c  call    WPP_SF_
0x180029a31  mov     eax, 0C000000Dh
0x180029a36  jmp     short loc_180029A85
0x180029a38  mov     rdx, [rcx+8]
0x180029a3c  lea     r9, [rsp+38h+Token]
0x180029a41  mov     rcx, [rcx]
0x180029a44  xor     r8d, r8d
0x180029a47  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KPEAPEAX1@Z$0EA@@KernelPackageCallValidatorWorkers@@SAJ_K0PEAPEAX1@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,void * *,void * *),64>::InvokeById(unsigned __int64,unsigned __int64,void * *,void * *)
0x180029a4c  test    eax, eax
0x180029a4e  js      short loc_180029A85
0x180029a50  mov     rcx, [rsp+38h+Token]
0x180029a55  call    cs:__imp_SeTokenImpersonationLevel
0x180029a5c  nop     dword ptr [rax+rax+00h]
0x180029a61  mov     rdx, [rsp+38h+Token]; Token
0x180029a66  xor     r9d, r9d; EffectiveOnly
0x180029a69  mov     rcx, gs:188h; Thread
0x180029a72  xor     r8d, r8d; CopyOnOpen
0x180029a75  mov     [rsp+38h+ImpersonationLevel], eax; ImpersonationLevel
0x180029a79  call    cs:__imp_PsImpersonateClient
0x180029a80  nop     dword ptr [rax+rax+00h]
0x180029a85  add     rsp, 38h
0x180029a89  retn
```
