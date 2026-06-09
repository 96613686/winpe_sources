# IASInitializeChildSid

- ea: `0x18002a824`
- end: `0x18002a871`
- name: `IASInitializeChildSid`
- size: `77`
- prototype: `__int64 __fastcall(PSID Sid, PSID SourceSid)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180027e8c`
- `0x1800282e4`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18002a85e`
- `ntdll!RtlSubAuthoritySid` at `0x18002a85e`
- `ntdll!RtlCopySid` at `0x18002a83f`
- `ntdll!RtlCopySid` at `0x18002a83f`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002a848`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002a848`

## pseudocode

```c
PULONG __fastcall IASInitializeChildSid(PSID Sid, PSID SourceSid, ULONG a3)
{
  PUCHAR v5; // rax
  ULONG v6; // r9d
  PULONG result; // rax

  RtlCopySid(0x7FFFFFFFu, Sid, SourceSid);
  v5 = RtlSubAuthorityCountSid(Sid);
  v6 = *v5;
  *v5 = v6 + 1;
  result = RtlSubAuthoritySid(Sid, v6);
  *result = a3;
  return result;
}

```

## disassembly

```asm
0x18002a824  mov     [rsp+arg_0], rbx
0x18002a829  push    rdi
0x18002a82a  sub     rsp, 20h
0x18002a82e  mov     edi, r8d
0x18002a831  mov     rbx, rcx
0x18002a834  mov     r8, rdx; SourceSid
0x18002a837  mov     rdx, rcx; DestinationSid
0x18002a83a  mov     ecx, 7FFFFFFFh; DestinationSidLength
0x18002a83f  call    cs:__imp_RtlCopySid
0x18002a845  mov     rcx, rbx; Sid
0x18002a848  call    cs:__imp_RtlSubAuthorityCountSid
0x18002a84e  mov     rcx, rbx; Sid
0x18002a851  movzx   r9d, byte ptr [rax]
0x18002a855  lea     edx, [r9+1]
0x18002a859  mov     [rax], dl
0x18002a85b  mov     edx, r9d; SubAuthority
0x18002a85e  call    cs:__imp_RtlSubAuthoritySid
0x18002a864  mov     rbx, [rsp+28h+arg_0]
0x18002a869  mov     [rax], edi
0x18002a86b  add     rsp, 20h
0x18002a86f  pop     rdi
0x18002a870  retn
```
