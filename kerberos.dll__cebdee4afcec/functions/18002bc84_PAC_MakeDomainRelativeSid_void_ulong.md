# PAC_MakeDomainRelativeSid(void *,ulong)

- ea: `0x18002bc84`
- end: `0x18002bd39`
- name: `?PAC_MakeDomainRelativeSid@@YAPEAXPEAXK@Z`
- size: `181`
- prototype: `void *__fastcall(PSID SourceSid, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800f0144`

## callees

- `0x1800069a0`
- `0x18002bc84`
- `0x18007108c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bd15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bd15`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002bc97`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002bce5`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002bc97`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002bce5`
- `ntdll!RtlLengthRequiredSid` at `0x18002bca5`
- `ntdll!RtlLengthRequiredSid` at `0x18002bca5`
- `ntdll!RtlCopySid` at `0x18002bcd8`
- `ntdll!RtlCopySid` at `0x18002bcd8`
- `ntdll!RtlSubAuthoritySid` at `0x18002bcf3`
- `ntdll!RtlSubAuthoritySid` at `0x18002bcf3`

## pseudocode

```c
void *__fastcall PAC_MakeDomainRelativeSid(PSID SourceSid, ULONG a2)
{
  ULONG v4; // r14d
  ULONG v5; // eax
  size_t v6; // rsi
  void *v7; // rbx
  PUCHAR v8; // rax
  HLOCAL v10; // rax

  v4 = *RtlSubAuthorityCountSid(SourceSid);
  v5 = RtlLengthRequiredSid(v4 + 1);
  v6 = v5;
  if ( KerbGlobalPackageState == 1 )
  {
    v7 = (void *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)(v5);
    if ( !v7 )
      return 0;
  }
  else
  {
    v10 = LocalAlloc(0, v5);
    v7 = v10;
    if ( !v10 )
      return 0;
    memset_0(v10, 0, v6);
  }
  if ( RtlCopySid(v6, v7, SourceSid) >= 0 )
  {
    v8 = RtlSubAuthorityCountSid(v7);
    ++*v8;
    *RtlSubAuthoritySid(v7, v4) = a2;
    return v7;
  }
  KerbFree(v7);
  return 0;
}

```

## disassembly

```asm
0x18002bc84  push    rbx
0x18002bc86  push    rbp
0x18002bc87  push    rsi
0x18002bc88  push    rdi
0x18002bc89  push    r14
0x18002bc8b  push    r15
0x18002bc8d  sub     rsp, 28h
0x18002bc91  mov     r15d, edx
0x18002bc94  mov     rbp, rcx
0x18002bc97  call    cs:__imp_RtlSubAuthorityCountSid
0x18002bc9d  movzx   r14d, byte ptr [rax]
0x18002bca1  lea     ecx, [r14+1]; SubAuthorityCount
0x18002bca5  call    cs:__imp_RtlLengthRequiredSid
0x18002bcab  cmp     cs:?KerbGlobalPackageState@@3W4KerberosState@@A, 1; KerberosState KerbGlobalPackageState
0x18002bcb2  mov     esi, eax
0x18002bcb4  jnz     short loc_18002BD10
0x18002bcb6  mov     r8, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18002bcbd  mov     ecx, esi
0x18002bcbf  mov     rax, [r8+28h]
0x18002bcc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcc8  mov     rbx, rax
0x18002bccb  test    rax, rax
0x18002bcce  jz      short loc_18002BD0C
0x18002bcd0  mov     r8, rbp; SourceSid
0x18002bcd3  mov     rdx, rbx; DestinationSid
0x18002bcd6  mov     ecx, esi; DestinationSidLength
0x18002bcd8  call    cs:__imp_RtlCopySid
0x18002bcde  mov     rcx, rbx; Sid
0x18002bce1  test    eax, eax
0x18002bce3  js      short loc_18002BD32
0x18002bce5  call    cs:__imp_RtlSubAuthorityCountSid
0x18002bceb  mov     edx, r14d; SubAuthority
0x18002bcee  mov     rcx, rbx; Sid
0x18002bcf1  inc     byte ptr [rax]
0x18002bcf3  call    cs:__imp_RtlSubAuthoritySid
0x18002bcf9  mov     [rax], r15d
0x18002bcfc  mov     rax, rbx
0x18002bcff  add     rsp, 28h
0x18002bd03  pop     r15
0x18002bd05  pop     r14
0x18002bd07  pop     rdi
0x18002bd08  pop     rsi
0x18002bd09  pop     rbp
0x18002bd0a  pop     rbx
0x18002bd0b  retn
0x18002bd0c  xor     eax, eax
0x18002bd0e  jmp     short loc_18002BCFF
0x18002bd10  mov     rdx, rsi; uBytes
0x18002bd13  xor     ecx, ecx; uFlags
0x18002bd15  call    cs:__imp_LocalAlloc
0x18002bd1b  mov     rbx, rax
0x18002bd1e  test    rax, rax
0x18002bd21  jz      short loc_18002BD0C
0x18002bd23  mov     r8, rsi; Size
0x18002bd26  xor     edx, edx; Val
0x18002bd28  mov     rcx, rax; void *
0x18002bd2b  call    memset_0
0x18002bd30  jmp     short loc_18002BCD0
0x18002bd32  call    KerbFree
0x18002bd37  jmp     short loc_18002BD0C
```
