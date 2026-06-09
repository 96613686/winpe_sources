# CTSSecurityDescriptor::InitializeFromBlob(void *)

- ea: `0x180009998`
- end: `0x180009a2d`
- name: `?InitializeFromBlob@CTSSecurityDescriptor@@QEAAJPEAX@Z`
- size: `149`
- prototype: `int(CTSSecurityDescriptor *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a66c`
- `0x18000ab80`

## callees

- `0x1800077a0`
- `0x180009998`
- `0x18000acec`

## import_xrefs

- `ntdll!RtlCopySecurityDescriptor` at `0x1800099cc`
- `ntdll!RtlCopySecurityDescriptor` at `0x1800099cc`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800099b4`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800099b4`

## string_xrefs

- `0x180009a1a`: `CTSSecurityDescriptor::InitializeFromBlob`
- `0x180009a10`: `RtlCopySecurityDescriptor failed: 0x%x in %s`
- `0x180009a07`: `Invalid Security Descriptor failed: 0x%x in %s`

## pseudocode

```c
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
0x180009998  mov     [rsp+arg_0], rbx
0x18000999d  push    rdi
0x18000999e  sub     rsp, 20h
0x1800099a2  mov     rdi, rcx
0x1800099a5  mov     [rsp+28h+pDestinationSecurityDescriptor], 0
0x1800099ae  mov     rcx, rdx; pSecurityDescriptor
0x1800099b1  mov     rbx, rdx
0x1800099b4  call    cs:__imp_IsValidSecurityDescriptor
0x1800099bb  nop     dword ptr [rax+rax+00h]
0x1800099c0  test    eax, eax
0x1800099c2  jz      short loc_180009A02
0x1800099c4  lea     rdx, [rsp+28h+pDestinationSecurityDescriptor]; pDestinationSecurityDescriptor
0x1800099c9  mov     rcx, rbx; pSourceSecurityDescriptor
0x1800099cc  call    cs:__imp_RtlCopySecurityDescriptor
0x1800099d3  nop     dword ptr [rax+rax+00h]
0x1800099d8  mov     ebx, eax
0x1800099da  or      ebx, 10000000h
0x1800099e0  jl      short loc_180009A10
0x1800099e2  mov     rcx, [rdi+8]; hMem
0x1800099e6  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x1800099eb  mov     rcx, [rsp+28h+pDestinationSecurityDescriptor]
0x1800099f0  mov     [rdi+8], rcx
0x1800099f4  mov     eax, ebx
0x1800099f6  mov     rbx, [rsp+28h+arg_0]
0x1800099fb  add     rsp, 20h
0x1800099ff  pop     rdi
0x180009a00  retn
0x180009a02  mov     ebx, 8007053Ah
0x180009a07  lea     rdx, aInvalidSecurit; "Invalid Security Descriptor failed: 0x%"...
0x180009a0e  jmp     short loc_180009A17
0x180009a10  lea     rdx, aRtlcopysecurit; "RtlCopySecurityDescriptor failed: 0x%x "...
0x180009a17  mov     r8d, ebx
0x180009a1a  lea     r9, aCtssecuritydes_4; "CTSSecurityDescriptor::InitializeFromBl"...
0x180009a21  mov     ecx, 8; int
0x180009a26  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009a2b  jmp     short loc_1800099F4
```
