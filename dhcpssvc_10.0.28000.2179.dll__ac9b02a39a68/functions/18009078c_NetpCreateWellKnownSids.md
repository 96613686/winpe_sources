# NetpCreateWellKnownSids

- ea: `0x18009078c`
- end: `0x180090958`
- name: `NetpCreateWellKnownSids`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025144`

## callees

- `0x18009078c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x1800908c0`
- `ntdll!RtlCopySid` at `0x1800908c0`
- `ntdll!RtlSubAuthorityCountSid` at `0x18009087a`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800908d3`
- `ntdll!RtlSubAuthorityCountSid` at `0x18009087a`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800908d3`
- `ntdll!RtlInitializeSid` at `0x180090809`
- `ntdll!RtlInitializeSid` at `0x180090809`
- `ntdll!RtlLengthRequiredSid` at `0x1800907c3`
- `ntdll!RtlLengthRequiredSid` at `0x18009088e`
- `ntdll!RtlLengthRequiredSid` at `0x1800907c3`
- `ntdll!RtlLengthRequiredSid` at `0x18009088e`
- `ntdll!RtlSubAuthoritySid` at `0x18009081e`
- `ntdll!RtlSubAuthoritySid` at `0x180090840`
- `ntdll!RtlSubAuthoritySid` at `0x1800908e7`
- `ntdll!RtlSubAuthoritySid` at `0x18009081e`
- `ntdll!RtlSubAuthoritySid` at `0x180090840`
- `ntdll!RtlSubAuthoritySid` at `0x1800908e7`
- `KERNEL32!LocalAlloc` at `0x1800907db`
- `KERNEL32!LocalAlloc` at `0x1800908a4`
- `KERNEL32!LocalAlloc` at `0x1800907db`
- `KERNEL32!LocalAlloc` at `0x1800908a4`
- `KERNEL32!LocalFree` at `0x18009090e`
- `KERNEL32!LocalFree` at `0x18009090e`

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
  v1 = (ULONG *)&unk_1800F8A08;
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
    RtlInitializeSid(v5, (PSID_IDENTIFIER_AUTHORITY)((char *)&unk_1800F8A0C + 32 * v0), v2);
    *RtlSubAuthoritySid(**((PSID **)v1 - 1), 0) = v1[3];
    if ( *v1 == 2 )
      *RtlSubAuthoritySid(**((PSID **)v1 - 1), 1u) = v1[4];
    ++v0;
    v1 += 8;
    if ( v0 >= 0xB )
    {
      v6 = 0;
      for ( i = (ULONG *)&unk_1800F8978; ; i += 4 )
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
0x18009078c  mov     rax, rsp
0x18009078f  mov     [rax+8], rbx
0x180090793  mov     [rax+10h], rbp
0x180090797  mov     [rax+18h], rsi
0x18009079b  mov     [rax+20h], rdi
0x18009079f  push    r12
0x1800907a1  push    r14
0x1800907a3  push    r15
0x1800907a5  sub     rsp, 20h
0x1800907a9  xor     edi, edi
0x1800907ab  lea     rbx, unk_1800F8A08
0x1800907b2  mov     esi, [rbx]
0x1800907b4  cmp     esi, 2
0x1800907b7  ja      loc_180090933
0x1800907bd  mov     r14, [rbx-8]
0x1800907c1  mov     ecx, esi; SubAuthorityCount
0x1800907c3  call    cs:__imp_RtlLengthRequiredSid
0x1800907ca  nop     dword ptr [rax+rax+00h]
0x1800907cf  test    eax, eax
0x1800907d1  jz      loc_180090925
0x1800907d7  mov     edx, eax; uBytes
0x1800907d9  xor     ecx, ecx; uFlags
0x1800907db  call    cs:__imp_LocalAlloc
0x1800907e2  nop     dword ptr [rax+rax+00h]
0x1800907e7  mov     [r14], rax
0x1800907ea  test    rax, rax
0x1800907ed  jz      loc_18009092C
0x1800907f3  lea     rcx, unk_1800F8A0C
0x1800907fa  mov     edx, edi
0x1800907fc  shl     rdx, 5
0x180090800  mov     r8b, sil; SubAuthorityCount
0x180090803  add     rdx, rcx; IdentifierAuthority
0x180090806  mov     rcx, rax; Sid
0x180090809  call    cs:__imp_RtlInitializeSid
0x180090810  nop     dword ptr [rax+rax+00h]
0x180090815  mov     rcx, [rbx-8]
0x180090819  xor     edx, edx; SubAuthority
0x18009081b  mov     rcx, [rcx]; Sid
0x18009081e  call    cs:__imp_RtlSubAuthoritySid
0x180090825  nop     dword ptr [rax+rax+00h]
0x18009082a  mov     ecx, [rbx+0Ch]
0x18009082d  mov     [rax], ecx
0x18009082f  cmp     dword ptr [rbx], 2
0x180090832  jnz     short loc_180090851
0x180090834  mov     rcx, [rbx-8]
0x180090838  mov     edx, 1; SubAuthority
0x18009083d  mov     rcx, [rcx]; Sid
0x180090840  call    cs:__imp_RtlSubAuthoritySid
0x180090847  nop     dword ptr [rax+rax+00h]
0x18009084c  mov     ecx, [rbx+10h]
0x18009084f  mov     [rax], ecx
0x180090851  inc     edi
0x180090853  add     rbx, 20h ; ' '
0x180090857  cmp     edi, 0Bh
0x18009085a  jb      loc_1800907B2
0x180090860  xor     esi, esi
0x180090862  lea     rdi, unk_1800F8978
0x180090869  mov     r14, cs:BuiltinDomainSid
0x180090870  mov     rbx, [rdi-8]
0x180090874  mov     rcx, r14; Sid
0x180090877  mov     r12d, [rdi]
0x18009087a  call    cs:__imp_RtlSubAuthorityCountSid
0x180090881  nop     dword ptr [rax+rax+00h]
0x180090886  movzx   r15d, byte ptr [rax]
0x18009088a  lea     ecx, [r15+1]; SubAuthorityCount
0x18009088e  call    cs:__imp_RtlLengthRequiredSid
0x180090895  nop     dword ptr [rax+rax+00h]
0x18009089a  mov     ebp, eax
0x18009089c  test    eax, eax
0x18009089e  jz      short loc_18009091C
0x1800908a0  mov     edx, ebp; uBytes
0x1800908a2  xor     ecx, ecx; uFlags
0x1800908a4  call    cs:__imp_LocalAlloc
0x1800908ab  nop     dword ptr [rax+rax+00h]
0x1800908b0  mov     [rbx], rax
0x1800908b3  test    rax, rax
0x1800908b6  jz      short loc_18009092C
0x1800908b8  mov     r8, r14; SourceSid
0x1800908bb  mov     rdx, rax; DestinationSid
0x1800908be  mov     ecx, ebp; DestinationSidLength
0x1800908c0  call    cs:__imp_RtlCopySid
0x1800908c7  nop     dword ptr [rax+rax+00h]
0x1800908cc  mov     rcx, [rbx]; hMem
0x1800908cf  test    eax, eax
0x1800908d1  js      short loc_180090909
0x1800908d3  call    cs:__imp_RtlSubAuthorityCountSid
0x1800908da  nop     dword ptr [rax+rax+00h]
0x1800908df  mov     edx, r15d; SubAuthority
0x1800908e2  inc     byte ptr [rax]
0x1800908e4  mov     rcx, [rbx]; Sid
0x1800908e7  call    cs:__imp_RtlSubAuthoritySid
0x1800908ee  nop     dword ptr [rax+rax+00h]
0x1800908f3  inc     esi
0x1800908f5  add     rdi, 10h
0x1800908f9  mov     [rax], r12d
0x1800908fc  cmp     esi, 9
0x1800908ff  jb      loc_180090869
0x180090905  xor     eax, eax
0x180090907  jmp     short loc_180090938
0x180090909  test    rcx, rcx
0x18009090c  jz      short loc_18009092C
0x18009090e  call    cs:__imp_LocalFree
0x180090915  nop     dword ptr [rax+rax+00h]
0x18009091a  jmp     short loc_18009092C
0x18009091c  mov     qword ptr [rbx], 0
0x180090923  jmp     short loc_18009092C
0x180090925  mov     qword ptr [r14], 0
0x18009092c  mov     eax, 0C0000017h
0x180090931  jmp     short loc_180090938
0x180090933  mov     eax, 0C000000Dh
0x180090938  mov     rbx, [rsp+38h+arg_0]
0x18009093d  mov     rbp, [rsp+38h+arg_8]
0x180090942  mov     rsi, [rsp+38h+arg_10]
0x180090947  mov     rdi, [rsp+38h+arg_18]
0x18009094c  add     rsp, 20h
0x180090950  pop     r15
0x180090952  pop     r14
0x180090954  pop     r12
0x180090956  retn
```
