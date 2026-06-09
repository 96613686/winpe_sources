# NlpMakeDomainRelativeSid

- ea: `0x180040338`
- end: `0x1800403be`
- name: `NlpMakeDomainRelativeSid`
- size: `134`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a470`
- `0x180022220`
- `0x1800427d0`
- `0x18004417c`

## callees

- `0x180040338`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x1800403a7`
- `ntdll!RtlSubAuthoritySid` at `0x1800403a7`
- `ntdll!RtlSubAuthorityCountSid` at `0x180040349`
- `ntdll!RtlSubAuthorityCountSid` at `0x18004039a`
- `ntdll!RtlSubAuthorityCountSid` at `0x180040349`
- `ntdll!RtlSubAuthorityCountSid` at `0x18004039a`
- `ntdll!RtlLengthRequiredSid` at `0x180040355`
- `ntdll!RtlLengthRequiredSid` at `0x180040355`
- `ntdll!RtlCopySid` at `0x18004037f`
- `ntdll!RtlCopySid` at `0x18004037f`

## pseudocode

```c
void *__fastcall NlpMakeDomainRelativeSid(PSID SourceSid, ULONG a2)
{
  ULONG v4; // ebp
  __int64 v5; // rsi
  void *v6; // rax
  void *v7; // rbx
  PUCHAR v9; // rax

  v4 = *RtlSubAuthorityCountSid(SourceSid);
  v5 = RtlLengthRequiredSid(v4 + 1);
  v6 = (void *)((__int64 (__fastcall *)(__int64))qword_180088238)(v5);
  v7 = v6;
  if ( !v6 )
    return 0;
  if ( RtlCopySid(v5, v6, SourceSid) < 0 )
  {
    ((void (__fastcall *)(void *))qword_180088240)(v7);
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
0x180040338  push    rbx
0x18004033a  push    rbp
0x18004033b  push    rsi
0x18004033c  push    rdi
0x18004033d  push    r14
0x18004033f  sub     rsp, 20h
0x180040343  mov     r14d, edx
0x180040346  mov     rdi, rcx
0x180040349  call    cs:__imp_RtlSubAuthorityCountSid
0x18004034f  movzx   ebp, byte ptr [rax]
0x180040352  lea     ecx, [rbp+1]; SubAuthorityCount
0x180040355  call    cs:__imp_RtlLengthRequiredSid
0x18004035b  mov     esi, eax
0x18004035d  mov     ecx, eax
0x18004035f  mov     rax, cs:qword_180088238
0x180040366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004036b  mov     rbx, rax
0x18004036e  test    rax, rax
0x180040371  jnz     short loc_180040377
0x180040373  xor     eax, eax
0x180040375  jmp     short loc_1800403B3
0x180040377  mov     r8, rdi; SourceSid
0x18004037a  mov     rdx, rbx; DestinationSid
0x18004037d  mov     ecx, esi; DestinationSidLength
0x18004037f  call    cs:__imp_RtlCopySid
0x180040385  mov     rcx, rbx; Sid
0x180040388  test    eax, eax
0x18004038a  jns     short loc_18004039A
0x18004038c  mov     rax, cs:qword_180088240
0x180040393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040398  jmp     short loc_180040373
0x18004039a  call    cs:__imp_RtlSubAuthorityCountSid
0x1800403a0  mov     edx, ebp; SubAuthority
0x1800403a2  mov     rcx, rbx; Sid
0x1800403a5  inc     byte ptr [rax]
0x1800403a7  call    cs:__imp_RtlSubAuthoritySid
0x1800403ad  mov     [rax], r14d
0x1800403b0  mov     rax, rbx
0x1800403b3  add     rsp, 20h
0x1800403b7  pop     r14
0x1800403b9  pop     rdi
0x1800403ba  pop     rsi
0x1800403bb  pop     rbp
0x1800403bc  pop     rbx
0x1800403bd  retn
```
