# QuerySecurityContextToken

- ea: `0x180029370`
- end: `0x180029413`
- name: `QuerySecurityContextToken`
- size: `163`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, void **Token)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007ba8`
- `0x180029370`
- `0x180029aa0`

## import_xrefs

- `ntoskrnl!NtDuplicateObject` at `0x180029400`
- `ntoskrnl!NtDuplicateObject` at `0x180029400`

## pseudocode

```c
SECURITY_STATUS __stdcall QuerySecurityContextToken(PCtxtHandle phContext, void **Token)
{
  SECURITY_STATUS result; // eax
  HANDLE SourceHandle; // [rsp+50h] [rbp+8h] BYREF

  SourceHandle = 0;
  if ( phContext )
  {
    result = KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,void * *,void * *),64>::InvokeById(
               phContext->dwLower,
               phContext->dwUpper,
               &SourceHandle,
               0);
    if ( result >= 0 )
      return NtDuplicateObject(
               KsecSystemProcessHandle,
               SourceHandle,
               (HANDLE)0xFFFFFFFFFFFFFFFFLL,
               Token,
               0,
               0x200u,
               2u);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, &WPP_bf88770bd570357164879d008cd144d3_Traceguids);
    return -1073741811;
  }
  return result;
}

```

## disassembly

```asm
0x180029370  push    rbx
0x180029372  sub     rsp, 40h
0x180029376  mov     [rsp+48h+SourceHandle], 0
0x18002937f  mov     rbx, rdx
0x180029382  test    rcx, rcx
0x180029385  jnz     short loc_1800293BD
0x180029387  mov     rcx, cs:WPP_GLOBAL_Control
0x18002938e  lea     rax, WPP_GLOBAL_Control
0x180029395  cmp     rcx, rax
0x180029398  jz      short loc_1800293B6
0x18002939a  mov     eax, [rcx+2Ch]
0x18002939d  test    al, 1
0x18002939f  jz      short loc_1800293B6
0x1800293a1  mov     rcx, [rcx+18h]
0x1800293a5  lea     r8, WPP_bf88770bd570357164879d008cd144d3_Traceguids
0x1800293ac  mov     edx, 0Fh
0x1800293b1  call    WPP_SF_
0x1800293b6  mov     eax, 0C000000Dh
0x1800293bb  jmp     short loc_18002940C
0x1800293bd  mov     rdx, [rcx+8]
0x1800293c1  lea     r8, [rsp+48h+SourceHandle]
0x1800293c6  mov     rcx, [rcx]
0x1800293c9  xor     r9d, r9d
0x1800293cc  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KPEAPEAX1@Z$0EA@@KernelPackageCallValidatorWorkers@@SAJ_K0PEAPEAX1@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,void * *,void * *),64>::InvokeById(unsigned __int64,unsigned __int64,void * *,void * *)
0x1800293d1  test    eax, eax
0x1800293d3  js      short loc_18002940C
0x1800293d5  mov     rdx, [rsp+48h+SourceHandle]; SourceHandle
0x1800293da  mov     r9, rbx; TargetHandle
0x1800293dd  mov     rcx, cs:KsecSystemProcessHandle; SourceProcessHandle
0x1800293e4  or      r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x1800293e8  mov     [rsp+48h+Options], 2; Options
0x1800293f0  mov     [rsp+48h+HandleAttributes], 200h; HandleAttributes
0x1800293f8  mov     [rsp+48h+DesiredAccess], 0; DesiredAccess
0x180029400  call    cs:__imp_NtDuplicateObject
0x180029407  nop     dword ptr [rax+rax+00h]
0x18002940c  add     rsp, 40h
0x180029410  pop     rbx
0x180029411  retn
```
