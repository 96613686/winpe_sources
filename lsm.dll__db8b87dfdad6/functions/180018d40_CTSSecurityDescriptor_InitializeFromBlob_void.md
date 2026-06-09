# CTSSecurityDescriptor::InitializeFromBlob(void *)

- ea: `0x180018d40`
- end: `0x180018dc8`
- name: `?InitializeFromBlob@CTSSecurityDescriptor@@QEAAJPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(HLOCAL *this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800198c4`
- `0x180019dc8`

## callees

- `0x1800074c0`
- `0x180018d40`
- `0x180019f28`

## import_xrefs

- `ntdll!RtlCopySecurityDescriptor` at `0x180018d6e`
- `ntdll!RtlCopySecurityDescriptor` at `0x180018d6e`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180018d5c`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180018d5c`

## string_xrefs

- `0x180018da2`: `Invalid Security Descriptor failed: 0x%x in %s`
- `0x180018db5`: `CTSSecurityDescriptor::InitializeFromBlob`
- `0x180018dab`: `RtlCopySecurityDescriptor failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTSSecurityDescriptor::InitializeFromBlob(HLOCAL *this, void *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  PSECURITY_DESCRIPTOR pDestinationSecurityDescriptor; // [rsp+40h] [rbp+18h] BYREF

  pDestinationSecurityDescriptor = 0;
  if ( IsValidSecurityDescriptor(a2) )
  {
    v4 = RtlCopySecurityDescriptor(a2, &pDestinationSecurityDescriptor);
    v5 = v4 | 0x10000000;
    if ( v4 < 0 )
    {
      _DbgPrintMessage(
        8,
        "RtlCopySecurityDescriptor failed: 0x%x in %s",
        v5,
        "CTSSecurityDescriptor::InitializeFromBlob");
    }
    else
    {
      CUtils::CleanupSD(this[1]);
      this[1] = pDestinationSecurityDescriptor;
    }
  }
  else
  {
    v5 = -2147023558;
    _DbgPrintMessage(
      8,
      "Invalid Security Descriptor failed: 0x%x in %s",
      2147943738LL,
      "CTSSecurityDescriptor::InitializeFromBlob");
  }
  return v5;
}

```

## disassembly

```asm
0x180018d40  mov     [rsp+arg_0], rbx
0x180018d45  push    rdi
0x180018d46  sub     rsp, 20h
0x180018d4a  mov     rdi, rcx
0x180018d4d  mov     [rsp+28h+pDestinationSecurityDescriptor], 0
0x180018d56  mov     rcx, rdx; pSecurityDescriptor
0x180018d59  mov     rbx, rdx
0x180018d5c  call    cs:__imp_IsValidSecurityDescriptor
0x180018d62  test    eax, eax
0x180018d64  jz      short loc_180018D9D
0x180018d66  lea     rdx, [rsp+28h+pDestinationSecurityDescriptor]; pDestinationSecurityDescriptor
0x180018d6b  mov     rcx, rbx; pSourceSecurityDescriptor
0x180018d6e  call    cs:__imp_RtlCopySecurityDescriptor
0x180018d74  mov     ebx, eax
0x180018d76  or      ebx, 10000000h
0x180018d7c  jl      short loc_180018DAB
0x180018d7e  mov     rcx, [rdi+8]; hMem
0x180018d82  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180018d87  mov     rcx, [rsp+28h+pDestinationSecurityDescriptor]
0x180018d8c  mov     [rdi+8], rcx
0x180018d90  mov     eax, ebx
0x180018d92  mov     rbx, [rsp+28h+arg_0]
0x180018d97  add     rsp, 20h
0x180018d9b  pop     rdi
0x180018d9c  retn
0x180018d9d  mov     ebx, 8007053Ah
0x180018da2  lea     rdx, aInvalidSecurit; "Invalid Security Descriptor failed: 0x%"...
0x180018da9  jmp     short loc_180018DB2
0x180018dab  lea     rdx, aRtlcopysecurit; "RtlCopySecurityDescriptor failed: 0x%x "...
0x180018db2  mov     r8d, ebx
0x180018db5  lea     r9, aCtssecuritydes_4; "CTSSecurityDescriptor::InitializeFromBl"...
0x180018dbc  mov     ecx, 8; int
0x180018dc1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018dc6  jmp     short loc_180018D90
```
