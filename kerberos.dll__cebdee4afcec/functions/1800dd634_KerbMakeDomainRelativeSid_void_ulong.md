# KerbMakeDomainRelativeSid(void *,ulong)

- ea: `0x1800dd634`
- end: `0x1800dd6ac`
- name: `?KerbMakeDomainRelativeSid@@YAPEAXPEAXK@Z`
- size: `120`
- prototype: `void *__fastcall(PSID SourceSid, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800b9c50`
- `0x1800b9dd0`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x1800dd634`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x1800dd645`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800dd688`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800dd645`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800dd688`
- `ntdll!RtlLengthRequiredSid` at `0x1800dd651`
- `ntdll!RtlLengthRequiredSid` at `0x1800dd651`
- `ntdll!RtlCopySid` at `0x1800dd674`
- `ntdll!RtlCopySid` at `0x1800dd674`
- `ntdll!RtlSubAuthoritySid` at `0x1800dd695`
- `ntdll!RtlSubAuthoritySid` at `0x1800dd695`

## pseudocode

```c
void *__fastcall KerbMakeDomainRelativeSid(PSID SourceSid, ULONG a2)
{
  ULONG v4; // ebp
  ULONG v5; // esi
  void *v6; // rax
  void *v7; // rbx
  PUCHAR v9; // rax

  v4 = *RtlSubAuthorityCountSid(SourceSid);
  v5 = RtlLengthRequiredSid(v4 + 1);
  v6 = MIDL_user_allocate(v5);
  v7 = v6;
  if ( !v6 )
    return 0;
  if ( RtlCopySid(v5, v6, SourceSid) < 0 )
  {
    KerbFree(v7);
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
0x1800dd634  push    rbx
0x1800dd636  push    rbp
0x1800dd637  push    rsi
0x1800dd638  push    rdi
0x1800dd639  push    r14
0x1800dd63b  sub     rsp, 20h
0x1800dd63f  mov     r14d, edx
0x1800dd642  mov     rdi, rcx
0x1800dd645  call    cs:__imp_RtlSubAuthorityCountSid
0x1800dd64b  movzx   ebp, byte ptr [rax]
0x1800dd64e  lea     ecx, [rbp+1]; SubAuthorityCount
0x1800dd651  call    cs:__imp_RtlLengthRequiredSid
0x1800dd657  mov     ecx, eax; size
0x1800dd659  mov     esi, eax
0x1800dd65b  call    MIDL_user_allocate
0x1800dd660  mov     rbx, rax
0x1800dd663  test    rax, rax
0x1800dd666  jnz     short loc_1800DD66C
0x1800dd668  xor     eax, eax
0x1800dd66a  jmp     short loc_1800DD6A1
0x1800dd66c  mov     r8, rdi; SourceSid
0x1800dd66f  mov     rdx, rbx; DestinationSid
0x1800dd672  mov     ecx, esi; DestinationSidLength
0x1800dd674  call    cs:__imp_RtlCopySid
0x1800dd67a  mov     rcx, rbx; Sid
0x1800dd67d  test    eax, eax
0x1800dd67f  jns     short loc_1800DD688
0x1800dd681  call    KerbFree
0x1800dd686  jmp     short loc_1800DD668
0x1800dd688  call    cs:__imp_RtlSubAuthorityCountSid
0x1800dd68e  mov     edx, ebp; SubAuthority
0x1800dd690  mov     rcx, rbx; Sid
0x1800dd693  inc     byte ptr [rax]
0x1800dd695  call    cs:__imp_RtlSubAuthoritySid
0x1800dd69b  mov     [rax], r14d
0x1800dd69e  mov     rax, rbx
0x1800dd6a1  add     rsp, 20h
0x1800dd6a5  pop     r14
0x1800dd6a7  pop     rdi
0x1800dd6a8  pop     rsi
0x1800dd6a9  pop     rbp
0x1800dd6aa  pop     rbx
0x1800dd6ab  retn
```
