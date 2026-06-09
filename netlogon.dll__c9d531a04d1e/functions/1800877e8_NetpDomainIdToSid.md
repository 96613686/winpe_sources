# NetpDomainIdToSid

- ea: `0x1800877e8`
- end: `0x18008786a`
- name: `NetpDomainIdToSid`
- size: `130`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180035f90`
- `0x1800508a8`
- `0x180050b20`
- `0x18005113c`
- `0x18005b270`
- `0x18005b500`
- `0x1800876d8`

## callees

- `0x180003200`
- `0x180003670`
- `0x1800877e8`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x180087854`
- `ntdll!RtlSubAuthoritySid` at `0x180087854`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800877fc`
- `ntdll!RtlSubAuthorityCountSid` at `0x180087847`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800877fc`
- `ntdll!RtlSubAuthorityCountSid` at `0x180087847`
- `ntdll!RtlCopySid` at `0x18008782e`
- `ntdll!RtlCopySid` at `0x18008782e`
- `ntdll!RtlLengthRequiredSid` at `0x180087808`
- `ntdll!RtlLengthRequiredSid` at `0x180087808`

## pseudocode

```c
__int64 __fastcall NetpDomainIdToSid(PSID SourceSid, ULONG a2, PSID *a3)
{
  ULONG v6; // edi
  ULONG v7; // ebp
  void *v8; // rax
  NTSTATUS v10; // eax
  PSID v11; // rcx
  PUCHAR v12; // rax

  v6 = *RtlSubAuthorityCountSid(SourceSid);
  v7 = RtlLengthRequiredSid(v6 + 1);
  v8 = (void *)NetpMemoryAllocate(v7);
  *a3 = v8;
  if ( !v8 )
    return 8;
  v10 = RtlCopySid(v7, v8, SourceSid);
  v11 = *a3;
  if ( v10 >= 0 )
  {
    v12 = RtlSubAuthorityCountSid(v11);
    ++*v12;
    *RtlSubAuthoritySid(*a3, v6) = a2;
    return 0;
  }
  else
  {
    NetpMemoryFree(v11);
    return 2140;
  }
}

```

## disassembly

```asm
0x1800877e8  push    rbx
0x1800877ea  push    rbp
0x1800877eb  push    rsi
0x1800877ec  push    rdi
0x1800877ed  push    r14
0x1800877ef  sub     rsp, 20h
0x1800877f3  mov     rbx, r8
0x1800877f6  mov     r14d, edx
0x1800877f9  mov     rsi, rcx
0x1800877fc  call    cs:__imp_RtlSubAuthorityCountSid
0x180087802  movzx   edi, byte ptr [rax]
0x180087805  lea     ecx, [rdi+1]; SubAuthorityCount
0x180087808  call    cs:__imp_RtlLengthRequiredSid
0x18008780e  mov     ecx, eax
0x180087810  mov     ebp, eax
0x180087812  call    NetpMemoryAllocate
0x180087817  mov     [rbx], rax
0x18008781a  test    rax, rax
0x18008781d  jnz     short loc_180087826
0x18008781f  mov     eax, 8
0x180087824  jmp     short loc_18008785F
0x180087826  mov     r8, rsi; SourceSid
0x180087829  mov     rdx, rax; DestinationSid
0x18008782c  mov     ecx, ebp; DestinationSidLength
0x18008782e  call    cs:__imp_RtlCopySid
0x180087834  mov     rcx, [rbx]; Sid
0x180087837  test    eax, eax
0x180087839  jns     short loc_180087847
0x18008783b  call    NetpMemoryFree
0x180087840  mov     eax, 85Ch
0x180087845  jmp     short loc_18008785F
0x180087847  call    cs:__imp_RtlSubAuthorityCountSid
0x18008784d  mov     edx, edi; SubAuthority
0x18008784f  inc     byte ptr [rax]
0x180087851  mov     rcx, [rbx]; Sid
0x180087854  call    cs:__imp_RtlSubAuthoritySid
0x18008785a  mov     [rax], r14d
0x18008785d  xor     eax, eax
0x18008785f  add     rsp, 20h
0x180087863  pop     r14
0x180087865  pop     rdi
0x180087866  pop     rsi
0x180087867  pop     rbp
0x180087868  pop     rbx
0x180087869  retn
```
