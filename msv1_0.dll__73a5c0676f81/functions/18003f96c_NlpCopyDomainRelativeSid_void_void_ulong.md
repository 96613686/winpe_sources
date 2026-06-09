# NlpCopyDomainRelativeSid(void *,void *,ulong)

- ea: `0x18003f96c`
- end: `0x18003f9d3`
- name: `?NlpCopyDomainRelativeSid@@YAKPEAX0K@Z`
- size: `103`
- prototype: `unsigned int __fastcall(PSID Sid, PSID SourceSid, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800405e8`

## callees

- `0x18003f96c`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18003f9bd`
- `ntdll!RtlSubAuthoritySid` at `0x18003f9bd`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003f983`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003f9b0`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003f983`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003f9b0`
- `ntdll!RtlLengthRequiredSid` at `0x18003f98f`
- `ntdll!RtlLengthRequiredSid` at `0x18003f98f`
- `ntdll!RtlCopySid` at `0x18003f99f`
- `ntdll!RtlCopySid` at `0x18003f99f`

## pseudocode

```c
__int64 __fastcall NlpCopyDomainRelativeSid(PSID Sid, PSID SourceSid, ULONG a3)
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
0x18003f96c  push    rbx
0x18003f96e  push    rbp
0x18003f96f  push    rsi
0x18003f970  push    rdi
0x18003f971  push    r14
0x18003f973  sub     rsp, 20h
0x18003f977  mov     rdi, rcx
0x18003f97a  mov     r14d, r8d
0x18003f97d  mov     rcx, rdx; Sid
0x18003f980  mov     rbx, rdx
0x18003f983  call    cs:__imp_RtlSubAuthorityCountSid
0x18003f989  movzx   esi, byte ptr [rax]
0x18003f98c  lea     ecx, [rsi+1]; SubAuthorityCount
0x18003f98f  call    cs:__imp_RtlLengthRequiredSid
0x18003f995  mov     r8, rbx; SourceSid
0x18003f998  mov     rdx, rdi; DestinationSid
0x18003f99b  mov     ecx, eax; DestinationSidLength
0x18003f99d  mov     ebp, eax
0x18003f99f  call    cs:__imp_RtlCopySid
0x18003f9a5  test    eax, eax
0x18003f9a7  jns     short loc_18003F9AD
0x18003f9a9  xor     eax, eax
0x18003f9ab  jmp     short loc_18003F9C8
0x18003f9ad  mov     rcx, rdi; Sid
0x18003f9b0  call    cs:__imp_RtlSubAuthorityCountSid
0x18003f9b6  mov     edx, esi; SubAuthority
0x18003f9b8  mov     rcx, rdi; Sid
0x18003f9bb  inc     byte ptr [rax]
0x18003f9bd  call    cs:__imp_RtlSubAuthoritySid
0x18003f9c3  mov     [rax], r14d
0x18003f9c6  mov     eax, ebp
0x18003f9c8  add     rsp, 20h
0x18003f9cc  pop     r14
0x18003f9ce  pop     rdi
0x18003f9cf  pop     rsi
0x18003f9d0  pop     rbp
0x18003f9d1  pop     rbx
0x18003f9d2  retn
```
