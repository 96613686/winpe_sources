# LsapSplitSid

- ea: `0x180037140`
- end: `0x1800371d7`
- name: `LsapSplitSid`
- size: `151`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001cc08`
- `0x18001e138`

## callees

- `0x180037140`
- `0x18003ad3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037185`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037185`
- `ntdll!RtlSubAuthorityCountSid` at `0x180037156`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800371ae`
- `ntdll!RtlSubAuthorityCountSid` at `0x180037156`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800371ae`
- `ntdll!RtlSubAuthoritySid` at `0x1800371bd`
- `ntdll!RtlSubAuthoritySid` at `0x1800371bd`
- `ntdll!RtlLengthSid` at `0x180037170`
- `ntdll!RtlLengthSid` at `0x180037170`

## pseudocode

```c
__int64 __fastcall LsapSplitSid(void *Src, void **a2, ULONG *a3)
{
  int v6; // r14d
  __int64 result; // rax
  ULONG v8; // eax
  void *v9; // rbx
  size_t v10; // rbp
  HLOCAL v11; // rax
  PUCHAR v12; // rax
  ULONG v13; // ecx

  v6 = *RtlSubAuthorityCountSid(Src);
  if ( !(_BYTE)v6 )
    return 3221225592LL;
  v8 = RtlLengthSid(Src);
  v9 = *a2;
  v10 = v8;
  if ( !*a2 )
  {
    v11 = LocalAlloc(0x40u, v8);
    *a2 = v11;
    v9 = v11;
    if ( !v11 )
      return 3221225626LL;
  }
  memmove_0(v9, Src, v10);
  v12 = RtlSubAuthorityCountSid(v9);
  --*v12;
  v13 = *RtlSubAuthoritySid(Src, v6 - 1);
  result = 0;
  *a3 = v13;
  return result;
}

```

## disassembly

```asm
0x180037140  push    rbx
0x180037142  push    rbp
0x180037143  push    rsi
0x180037144  push    rdi
0x180037145  push    r14
0x180037147  push    r15
0x180037149  sub     rsp, 28h
0x18003714d  mov     r15, r8
0x180037150  mov     rsi, rdx
0x180037153  mov     rdi, rcx
0x180037156  call    cs:__imp_RtlSubAuthorityCountSid
0x18003715c  movzx   r14d, byte ptr [rax]
0x180037160  cmp     r14b, 1
0x180037164  jnb     short loc_18003716D
0x180037166  mov     eax, 0C0000078h
0x18003716b  jmp     short loc_1800371CA
0x18003716d  mov     rcx, rdi; Sid
0x180037170  call    cs:__imp_RtlLengthSid
0x180037176  mov     rbx, [rsi]
0x180037179  mov     ebp, eax
0x18003717b  test    rbx, rbx
0x18003717e  jnz     short loc_18003719D
0x180037180  mov     edx, ebp; uBytes
0x180037182  lea     ecx, [rbx+40h]; uFlags
0x180037185  call    cs:__imp_LocalAlloc
0x18003718b  mov     [rsi], rax
0x18003718e  mov     rbx, rax
0x180037191  test    rax, rax
0x180037194  jnz     short loc_18003719D
0x180037196  mov     eax, 0C000009Ah
0x18003719b  jmp     short loc_1800371CA
0x18003719d  mov     r8, rbp; Size
0x1800371a0  mov     rdx, rdi; Src
0x1800371a3  mov     rcx, rbx; void *
0x1800371a6  call    memmove_0
0x1800371ab  mov     rcx, rbx; Sid
0x1800371ae  call    cs:__imp_RtlSubAuthorityCountSid
0x1800371b4  lea     edx, [r14-1]; SubAuthority
0x1800371b8  mov     rcx, rdi; Sid
0x1800371bb  dec     byte ptr [rax]
0x1800371bd  call    cs:__imp_RtlSubAuthoritySid
0x1800371c3  mov     ecx, [rax]
0x1800371c5  xor     eax, eax
0x1800371c7  mov     [r15], ecx
0x1800371ca  add     rsp, 28h
0x1800371ce  pop     r15
0x1800371d0  pop     r14
0x1800371d2  pop     rdi
0x1800371d3  pop     rsi
0x1800371d4  pop     rbp
0x1800371d5  pop     rbx
0x1800371d6  retn
```
