# PAC_MakeDomainRelativeSid(void *,ulong)

- ea: `0x18004466c`
- end: `0x1800446eb`
- name: `?PAC_MakeDomainRelativeSid@@YAPEAXPEAXK@Z`
- size: `127`
- prototype: `void *__fastcall(PSID SourceSid, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002e40`
- `0x1800044f0`

## callees

- `0x1800057f0`
- `0x180018870`
- `0x18004466c`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18004467d`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800446c7`
- `ntdll!RtlSubAuthorityCountSid` at `0x18004467d`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800446c7`
- `ntdll!RtlLengthRequiredSid` at `0x180044689`
- `ntdll!RtlLengthRequiredSid` at `0x180044689`
- `ntdll!RtlCopySid` at `0x1800446b3`
- `ntdll!RtlCopySid` at `0x1800446b3`
- `ntdll!RtlSubAuthoritySid` at `0x1800446d4`
- `ntdll!RtlSubAuthoritySid` at `0x1800446d4`

## pseudocode

```c
void *__fastcall PAC_MakeDomainRelativeSid(PSID SourceSid, ULONG a2)
{
  ULONG v4; // ebp
  ULONG v5; // esi
  void *v6; // rax
  void *v7; // rbx
  PUCHAR v9; // rax

  v4 = *RtlSubAuthorityCountSid(SourceSid);
  v5 = RtlLengthRequiredSid(v4 + 1);
  v6 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v5);
  v7 = v6;
  if ( !v6 )
    return 0;
  if ( RtlCopySid(v5, v6, SourceSid) < 0 )
  {
    Pku2uFree(v7);
    return 0;
  }
  v9 = RtlSubAuthorityCountSid(v7);
  ++*v9;
  *RtlSubAuthoritySid(v7, v4) = a2;
  return v7;
}

```

## disassembly

```asm
0x18004466c  push    rbx
0x18004466e  push    rbp
0x18004466f  push    rsi
0x180044670  push    rdi
0x180044671  push    r14
0x180044673  sub     rsp, 20h
0x180044677  mov     r14d, edx
0x18004467a  mov     rdi, rcx
0x18004467d  call    cs:__imp_RtlSubAuthorityCountSid
0x180044683  movzx   ebp, byte ptr [rax]
0x180044686  lea     ecx, [rbp+1]; SubAuthorityCount
0x180044689  call    cs:__imp_RtlLengthRequiredSid
0x18004468f  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180044696  mov     edx, eax; unsigned __int64
0x180044698  mov     esi, eax
0x18004469a  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18004469f  mov     rbx, rax
0x1800446a2  test    rax, rax
0x1800446a5  jnz     short loc_1800446AB
0x1800446a7  xor     eax, eax
0x1800446a9  jmp     short loc_1800446E0
0x1800446ab  mov     r8, rdi; SourceSid
0x1800446ae  mov     rdx, rbx; DestinationSid
0x1800446b1  mov     ecx, esi; DestinationSidLength
0x1800446b3  call    cs:__imp_RtlCopySid
0x1800446b9  mov     rcx, rbx; void *
0x1800446bc  test    eax, eax
0x1800446be  jns     short loc_1800446C7
0x1800446c0  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x1800446c5  jmp     short loc_1800446A7
0x1800446c7  call    cs:__imp_RtlSubAuthorityCountSid
0x1800446cd  mov     edx, ebp; SubAuthority
0x1800446cf  mov     rcx, rbx; Sid
0x1800446d2  inc     byte ptr [rax]
0x1800446d4  call    cs:__imp_RtlSubAuthoritySid
0x1800446da  mov     [rax], r14d
0x1800446dd  mov     rax, rbx
0x1800446e0  add     rsp, 20h
0x1800446e4  pop     r14
0x1800446e6  pop     rdi
0x1800446e7  pop     rsi
0x1800446e8  pop     rbp
0x1800446e9  pop     rbx
0x1800446ea  retn
```
