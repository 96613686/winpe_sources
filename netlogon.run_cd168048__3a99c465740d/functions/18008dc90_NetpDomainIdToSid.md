# NetpDomainIdToSid

- ea: `0x18008dc90`
- end: `0x18008dd31`
- name: `NetpDomainIdToSid`
- size: `161`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `7`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180037ff4`
- `0x180054030`
- `0x1800542fc`
- `0x1800549a4`
- `0x18005f4c0`
- `0x18005f750`
- `0x18008db68`

## callees

- `0x180003320`
- `0x1800037f0`
- `0x18008dc90`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18008dd14`
- `ntdll!RtlSubAuthoritySid` at `0x18008dd14`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008dca4`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008dd01`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008dca4`
- `ntdll!RtlSubAuthorityCountSid` at `0x18008dd01`
- `ntdll!RtlCopySid` at `0x18008dce2`
- `ntdll!RtlCopySid` at `0x18008dce2`
- `ntdll!RtlLengthRequiredSid` at `0x18008dcb6`
- `ntdll!RtlLengthRequiredSid` at `0x18008dcb6`

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
0x18008dc90  push    rbx
0x18008dc92  push    rbp
0x18008dc93  push    rsi
0x18008dc94  push    rdi
0x18008dc95  push    r14
0x18008dc97  sub     rsp, 20h
0x18008dc9b  mov     rbx, r8
0x18008dc9e  mov     r14d, edx
0x18008dca1  mov     rsi, rcx
0x18008dca4  call    cs:__imp_RtlSubAuthorityCountSid
0x18008dcab  nop     dword ptr [rax+rax+00h]
0x18008dcb0  movzx   edi, byte ptr [rax]
0x18008dcb3  lea     ecx, [rdi+1]; SubAuthorityCount
0x18008dcb6  call    cs:__imp_RtlLengthRequiredSid
0x18008dcbd  nop     dword ptr [rax+rax+00h]
0x18008dcc2  mov     ecx, eax
0x18008dcc4  mov     ebp, eax
0x18008dcc6  call    NetpMemoryAllocate
0x18008dccb  mov     [rbx], rax
0x18008dcce  test    rax, rax
0x18008dcd1  jnz     short loc_18008DCDA
0x18008dcd3  mov     eax, 8
0x18008dcd8  jmp     short loc_18008DD25
0x18008dcda  mov     r8, rsi; SourceSid
0x18008dcdd  mov     rdx, rax; DestinationSid
0x18008dce0  mov     ecx, ebp; DestinationSidLength
0x18008dce2  call    cs:__imp_RtlCopySid
0x18008dce9  nop     dword ptr [rax+rax+00h]
0x18008dcee  mov     rcx, [rbx]; Sid
0x18008dcf1  test    eax, eax
0x18008dcf3  jns     short loc_18008DD01
0x18008dcf5  call    NetpMemoryFree
0x18008dcfa  mov     eax, 85Ch
0x18008dcff  jmp     short loc_18008DD25
0x18008dd01  call    cs:__imp_RtlSubAuthorityCountSid
0x18008dd08  nop     dword ptr [rax+rax+00h]
0x18008dd0d  mov     edx, edi; SubAuthority
0x18008dd0f  inc     byte ptr [rax]
0x18008dd11  mov     rcx, [rbx]; Sid
0x18008dd14  call    cs:__imp_RtlSubAuthoritySid
0x18008dd1b  nop     dword ptr [rax+rax+00h]
0x18008dd20  mov     [rax], r14d
0x18008dd23  xor     eax, eax
0x18008dd25  add     rsp, 20h
0x18008dd29  pop     r14
0x18008dd2b  pop     rdi
0x18008dd2c  pop     rsi
0x18008dd2d  pop     rbp
0x18008dd2e  pop     rbx
0x18008dd2f  retn
```
