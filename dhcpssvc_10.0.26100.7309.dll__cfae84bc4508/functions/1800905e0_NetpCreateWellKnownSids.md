# NetpCreateWellKnownSids

- ea: `0x1800905e0`
- end: `0x1800907a6`
- name: `NetpCreateWellKnownSids`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025bf4`

## callees

- `0x1800905e0`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180090714`
- `ntdll!RtlCopySid` at `0x180090714`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800906ce`
- `ntdll!RtlSubAuthorityCountSid` at `0x180090727`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800906ce`
- `ntdll!RtlSubAuthorityCountSid` at `0x180090727`
- `ntdll!RtlInitializeSid` at `0x18009065d`
- `ntdll!RtlInitializeSid` at `0x18009065d`
- `ntdll!RtlLengthRequiredSid` at `0x180090617`
- `ntdll!RtlLengthRequiredSid` at `0x1800906e2`
- `ntdll!RtlLengthRequiredSid` at `0x180090617`
- `ntdll!RtlLengthRequiredSid` at `0x1800906e2`
- `ntdll!RtlSubAuthoritySid` at `0x180090672`
- `ntdll!RtlSubAuthoritySid` at `0x180090694`
- `ntdll!RtlSubAuthoritySid` at `0x18009073b`
- `ntdll!RtlSubAuthoritySid` at `0x180090672`
- `ntdll!RtlSubAuthoritySid` at `0x180090694`
- `ntdll!RtlSubAuthoritySid` at `0x18009073b`
- `KERNEL32!LocalAlloc` at `0x18009062f`
- `KERNEL32!LocalAlloc` at `0x1800906f8`
- `KERNEL32!LocalAlloc` at `0x18009062f`
- `KERNEL32!LocalAlloc` at `0x1800906f8`
- `KERNEL32!LocalFree` at `0x180090762`
- `KERNEL32!LocalFree` at `0x180090762`

## pseudocode

```c
__int64 NetpCreateWellKnownSids()
{
  unsigned int v0; // edi
  ULONG *v1; // rbx
  ULONG v2; // esi
  _QWORD *v3; // r14
  ULONG v4; // eax
  HLOCAL v5; // rax
  unsigned int v6; // esi
  ULONG *i; // rdi
  PSID v8; // r14
  PSID *v9; // rbx
  ULONG v10; // r12d
  ULONG v11; // r15d
  ULONG v12; // eax
  ULONG v13; // ebp
  HLOCAL v14; // rax
  NTSTATUS v15; // eax
  PSID v16; // rcx
  PUCHAR v17; // rax

  v0 = 0;
  v1 = (ULONG *)&unk_1800F6A08;
  while ( 1 )
  {
    v2 = *v1;
    if ( *v1 > 2 )
      break;
    v3 = (_QWORD *)*((_QWORD *)v1 - 1);
    v4 = RtlLengthRequiredSid(v2);
    if ( !v4 )
    {
      *v3 = 0;
      return 3221225495LL;
    }
    v5 = LocalAlloc(0, v4);
    *v3 = v5;
    if ( !v5 )
      return 3221225495LL;
    RtlInitializeSid(v5, (PSID_IDENTIFIER_AUTHORITY)((char *)&unk_1800F6A0C + 32 * v0), v2);
    *RtlSubAuthoritySid(**((PSID **)v1 - 1), 0) = v1[3];
    if ( *v1 == 2 )
      *RtlSubAuthoritySid(**((PSID **)v1 - 1), 1u) = v1[4];
    ++v0;
    v1 += 8;
    if ( v0 >= 0xB )
    {
      v6 = 0;
      for ( i = (ULONG *)&unk_1800F6978; ; i += 4 )
      {
        v8 = BuiltinDomainSid;
        v9 = (PSID *)*((_QWORD *)i - 1);
        v10 = *i;
        v11 = *RtlSubAuthorityCountSid(BuiltinDomainSid);
        v12 = RtlLengthRequiredSid(v11 + 1);
        v13 = v12;
        if ( !v12 )
        {
          *v9 = 0;
          return 3221225495LL;
        }
        v14 = LocalAlloc(0, v12);
        *v9 = v14;
        if ( !v14 )
          return 3221225495LL;
        v15 = RtlCopySid(v13, v14, v8);
        v16 = *v9;
        if ( v15 < 0 )
          break;
        v17 = RtlSubAuthorityCountSid(v16);
        ++*v17;
        ++v6;
        *RtlSubAuthoritySid(*v9, v11) = v10;
        if ( v6 >= 9 )
          return 0;
      }
      if ( v16 )
        LocalFree(v16);
      return 3221225495LL;
    }
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1800905e0  mov     rax, rsp
0x1800905e3  mov     [rax+8], rbx
0x1800905e7  mov     [rax+10h], rbp
0x1800905eb  mov     [rax+18h], rsi
0x1800905ef  mov     [rax+20h], rdi
0x1800905f3  push    r12
0x1800905f5  push    r14
0x1800905f7  push    r15
0x1800905f9  sub     rsp, 20h
0x1800905fd  xor     edi, edi
0x1800905ff  lea     rbx, unk_1800F6A08
0x180090606  mov     esi, [rbx]
0x180090608  cmp     esi, 2
0x18009060b  ja      loc_180090781
0x180090611  mov     r14, [rbx-8]
0x180090615  mov     ecx, esi; SubAuthorityCount
0x180090617  call    cs:__imp_RtlLengthRequiredSid
0x18009061e  nop     dword ptr [rax+rax+00h]
0x180090623  test    eax, eax
0x180090625  jz      loc_180090776
0x18009062b  mov     edx, eax; uBytes
0x18009062d  xor     ecx, ecx; uFlags
0x18009062f  call    cs:__imp_LocalAlloc
0x180090636  nop     dword ptr [rax+rax+00h]
0x18009063b  mov     [r14], rax
0x18009063e  test    rax, rax
0x180090641  jz      loc_18009077A
0x180090647  lea     rcx, unk_1800F6A0C
0x18009064e  mov     edx, edi
0x180090650  shl     rdx, 5
0x180090654  mov     r8b, sil; SubAuthorityCount
0x180090657  add     rdx, rcx; IdentifierAuthority
0x18009065a  mov     rcx, rax; Sid
0x18009065d  call    cs:__imp_RtlInitializeSid
0x180090664  nop     dword ptr [rax+rax+00h]
0x180090669  mov     rcx, [rbx-8]
0x18009066d  xor     edx, edx; SubAuthority
0x18009066f  mov     rcx, [rcx]; Sid
0x180090672  call    cs:__imp_RtlSubAuthoritySid
0x180090679  nop     dword ptr [rax+rax+00h]
0x18009067e  mov     ecx, [rbx+0Ch]
0x180090681  mov     [rax], ecx
0x180090683  cmp     dword ptr [rbx], 2
0x180090686  jnz     short loc_1800906A5
0x180090688  mov     rcx, [rbx-8]
0x18009068c  mov     edx, 1; SubAuthority
0x180090691  mov     rcx, [rcx]; Sid
0x180090694  call    cs:__imp_RtlSubAuthoritySid
0x18009069b  nop     dword ptr [rax+rax+00h]
0x1800906a0  mov     ecx, [rbx+10h]
0x1800906a3  mov     [rax], ecx
0x1800906a5  inc     edi
0x1800906a7  add     rbx, 20h ; ' '
0x1800906ab  cmp     edi, 0Bh
0x1800906ae  jb      loc_180090606
0x1800906b4  xor     esi, esi
0x1800906b6  lea     rdi, unk_1800F6978
0x1800906bd  mov     r14, cs:BuiltinDomainSid
0x1800906c4  mov     rbx, [rdi-8]
0x1800906c8  mov     rcx, r14; Sid
0x1800906cb  mov     r12d, [rdi]
0x1800906ce  call    cs:__imp_RtlSubAuthorityCountSid
0x1800906d5  nop     dword ptr [rax+rax+00h]
0x1800906da  movzx   r15d, byte ptr [rax]
0x1800906de  lea     ecx, [r15+1]; SubAuthorityCount
0x1800906e2  call    cs:__imp_RtlLengthRequiredSid
0x1800906e9  nop     dword ptr [rax+rax+00h]
0x1800906ee  mov     ebp, eax
0x1800906f0  test    eax, eax
0x1800906f2  jz      short loc_180090770
0x1800906f4  mov     edx, ebp; uBytes
0x1800906f6  xor     ecx, ecx; uFlags
0x1800906f8  call    cs:__imp_LocalAlloc
0x1800906ff  nop     dword ptr [rax+rax+00h]
0x180090704  mov     [rbx], rax
0x180090707  test    rax, rax
0x18009070a  jz      short loc_18009077A
0x18009070c  mov     r8, r14; SourceSid
0x18009070f  mov     rdx, rax; DestinationSid
0x180090712  mov     ecx, ebp; DestinationSidLength
0x180090714  call    cs:__imp_RtlCopySid
0x18009071b  nop     dword ptr [rax+rax+00h]
0x180090720  mov     rcx, [rbx]; hMem
0x180090723  test    eax, eax
0x180090725  js      short loc_18009075D
0x180090727  call    cs:__imp_RtlSubAuthorityCountSid
0x18009072e  nop     dword ptr [rax+rax+00h]
0x180090733  mov     edx, r15d; SubAuthority
0x180090736  inc     byte ptr [rax]
0x180090738  mov     rcx, [rbx]; Sid
0x18009073b  call    cs:__imp_RtlSubAuthoritySid
0x180090742  nop     dword ptr [rax+rax+00h]
0x180090747  inc     esi
0x180090749  add     rdi, 10h
0x18009074d  mov     [rax], r12d
0x180090750  cmp     esi, 9
0x180090753  jb      loc_1800906BD
0x180090759  xor     eax, eax
0x18009075b  jmp     short loc_180090786
0x18009075d  test    rcx, rcx
0x180090760  jz      short loc_18009077A
0x180090762  call    cs:__imp_LocalFree
0x180090769  nop     dword ptr [rax+rax+00h]
0x18009076e  jmp     short loc_18009077A
0x180090770  and     qword ptr [rbx], 0
0x180090774  jmp     short loc_18009077A
0x180090776  and     qword ptr [r14], 0
0x18009077a  mov     eax, 0C0000017h
0x18009077f  jmp     short loc_180090786
0x180090781  mov     eax, 0C000000Dh
0x180090786  mov     rbx, [rsp+38h+arg_0]
0x18009078b  mov     rbp, [rsp+38h+arg_8]
0x180090790  mov     rsi, [rsp+38h+arg_10]
0x180090795  mov     rdi, [rsp+38h+arg_18]
0x18009079a  add     rsp, 20h
0x18009079e  pop     r15
0x1800907a0  pop     r14
0x1800907a2  pop     r12
0x1800907a4  retn
```
