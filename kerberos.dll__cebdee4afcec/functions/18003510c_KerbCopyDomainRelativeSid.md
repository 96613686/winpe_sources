# KerbCopyDomainRelativeSid

- ea: `0x18003510c`
- end: `0x180035173`
- name: `KerbCopyDomainRelativeSid`
- size: `103`
- prototype: `__int64 __fastcall(PSID Sid, PSID SourceSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800841e4`

## callees

- `0x18003510c`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180035123`
- `ntdll!RtlSubAuthorityCountSid` at `0x180035150`
- `ntdll!RtlSubAuthorityCountSid` at `0x180035123`
- `ntdll!RtlSubAuthorityCountSid` at `0x180035150`
- `ntdll!RtlLengthRequiredSid` at `0x18003512f`
- `ntdll!RtlLengthRequiredSid` at `0x18003512f`
- `ntdll!RtlCopySid` at `0x18003513f`
- `ntdll!RtlCopySid` at `0x18003513f`
- `ntdll!RtlSubAuthoritySid` at `0x18003515d`
- `ntdll!RtlSubAuthoritySid` at `0x18003515d`

## pseudocode

```c
__int64 __fastcall KerbCopyDomainRelativeSid(PSID Sid, PSID SourceSid, ULONG a3)
{
  ULONG v6; // esi
  ULONG v7; // ebp
  PUCHAR v9; // rax

  v6 = *RtlSubAuthorityCountSid(SourceSid);
  v7 = RtlLengthRequiredSid(v6 + 1);
  if ( RtlCopySid(v7, Sid, SourceSid) < 0 )
    return 0;
  v9 = RtlSubAuthorityCountSid(Sid);
  ++*v9;
  *RtlSubAuthoritySid(Sid, v6) = a3;
  return v7;
}

```

## disassembly

```asm
0x18003510c  push    rbx
0x18003510e  push    rbp
0x18003510f  push    rsi
0x180035110  push    rdi
0x180035111  push    r14
0x180035113  sub     rsp, 20h
0x180035117  mov     rdi, rcx
0x18003511a  mov     r14d, r8d
0x18003511d  mov     rcx, rdx; Sid
0x180035120  mov     rbx, rdx
0x180035123  call    cs:__imp_RtlSubAuthorityCountSid
0x180035129  movzx   esi, byte ptr [rax]
0x18003512c  lea     ecx, [rsi+1]; SubAuthorityCount
0x18003512f  call    cs:__imp_RtlLengthRequiredSid
0x180035135  mov     r8, rbx; SourceSid
0x180035138  mov     rdx, rdi; DestinationSid
0x18003513b  mov     ecx, eax; DestinationSidLength
0x18003513d  mov     ebp, eax
0x18003513f  call    cs:__imp_RtlCopySid
0x180035145  test    eax, eax
0x180035147  jns     short loc_18003514D
0x180035149  xor     eax, eax
0x18003514b  jmp     short loc_180035168
0x18003514d  mov     rcx, rdi; Sid
0x180035150  call    cs:__imp_RtlSubAuthorityCountSid
0x180035156  mov     edx, esi; SubAuthority
0x180035158  mov     rcx, rdi; Sid
0x18003515b  inc     byte ptr [rax]
0x18003515d  call    cs:__imp_RtlSubAuthoritySid
0x180035163  mov     [rax], r14d
0x180035166  mov     eax, ebp
0x180035168  add     rsp, 20h
0x18003516c  pop     r14
0x18003516e  pop     rdi
0x18003516f  pop     rsi
0x180035170  pop     rbp
0x180035171  pop     rbx
0x180035172  retn
```
