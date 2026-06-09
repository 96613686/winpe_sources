# KerbCopyDomainRelativeSid(void *,void *,ulong)

- ea: `0x180038e0c`
- end: `0x180038e73`
- name: `?KerbCopyDomainRelativeSid@@YAKPEAX0K@Z`
- size: `103`
- prototype: `unsigned int __fastcall(PSID Sid, PSID SourceSid, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180003bc0`
- `0x180039f20`

## callees

- `0x180038e0c`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180038e23`
- `ntdll!RtlSubAuthorityCountSid` at `0x180038e50`
- `ntdll!RtlSubAuthorityCountSid` at `0x180038e23`
- `ntdll!RtlSubAuthorityCountSid` at `0x180038e50`
- `ntdll!RtlLengthRequiredSid` at `0x180038e2f`
- `ntdll!RtlLengthRequiredSid` at `0x180038e2f`
- `ntdll!RtlCopySid` at `0x180038e3f`
- `ntdll!RtlCopySid` at `0x180038e3f`
- `ntdll!RtlSubAuthoritySid` at `0x180038e5d`
- `ntdll!RtlSubAuthoritySid` at `0x180038e5d`

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
0x180038e0c  push    rbx
0x180038e0e  push    rbp
0x180038e0f  push    rsi
0x180038e10  push    rdi
0x180038e11  push    r14
0x180038e13  sub     rsp, 20h
0x180038e17  mov     rdi, rcx
0x180038e1a  mov     r14d, r8d
0x180038e1d  mov     rcx, rdx; Sid
0x180038e20  mov     rbx, rdx
0x180038e23  call    cs:__imp_RtlSubAuthorityCountSid
0x180038e29  movzx   esi, byte ptr [rax]
0x180038e2c  lea     ecx, [rsi+1]; SubAuthorityCount
0x180038e2f  call    cs:__imp_RtlLengthRequiredSid
0x180038e35  mov     r8, rbx; SourceSid
0x180038e38  mov     rdx, rdi; DestinationSid
0x180038e3b  mov     ecx, eax; DestinationSidLength
0x180038e3d  mov     ebp, eax
0x180038e3f  call    cs:__imp_RtlCopySid
0x180038e45  test    eax, eax
0x180038e47  jns     short loc_180038E4D
0x180038e49  xor     eax, eax
0x180038e4b  jmp     short loc_180038E68
0x180038e4d  mov     rcx, rdi; Sid
0x180038e50  call    cs:__imp_RtlSubAuthorityCountSid
0x180038e56  mov     edx, esi; SubAuthority
0x180038e58  mov     rcx, rdi; Sid
0x180038e5b  inc     byte ptr [rax]
0x180038e5d  call    cs:__imp_RtlSubAuthoritySid
0x180038e63  mov     [rax], r14d
0x180038e66  mov     eax, ebp
0x180038e68  add     rsp, 20h
0x180038e6c  pop     r14
0x180038e6e  pop     rdi
0x180038e6f  pop     rsi
0x180038e70  pop     rbp
0x180038e71  pop     rbx
0x180038e72  retn
```
