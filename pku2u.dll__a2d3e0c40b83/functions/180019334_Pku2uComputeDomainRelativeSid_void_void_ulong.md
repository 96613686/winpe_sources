# Pku2uComputeDomainRelativeSid(void *,void * *,ulong *)

- ea: `0x180019334`
- end: `0x1800193fd`
- name: `?Pku2uComputeDomainRelativeSid@@YAJPEAXPEAPEAXPEAK@Z`
- size: `201`
- prototype: `__int64 __fastcall(PSID Sid, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004830`
- `0x180038e7c`

## callees

- `0x180019334`
- `0x180021a54`
- `0x180046010`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180019346`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800193cf`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800193ea`
- `ntdll!RtlSubAuthorityCountSid` at `0x180019346`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800193cf`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800193ea`
- `ntdll!RtlLengthRequiredSid` at `0x180019364`
- `ntdll!RtlLengthRequiredSid` at `0x180019364`
- `ntdll!RtlCopySid` at `0x1800193df`
- `ntdll!RtlCopySid` at `0x1800193df`
- `ntdll!RtlSubAuthoritySid` at `0x180019355`
- `ntdll!RtlSubAuthoritySid` at `0x180019355`

## pseudocode

```c
__int64 __fastcall Pku2uComputeDomainRelativeSid(PSID Sid, void **a2, unsigned int *a3)
{
  int v6; // ebx
  size_t v7; // rdi
  void *v8; // rbx
  unsigned int v9; // ebx
  void *v10; // rax
  PUCHAR v11; // rax
  PUCHAR v12; // rax

  v6 = *RtlSubAuthorityCountSid(Sid);
  *a3 = *RtlSubAuthoritySid(Sid, v6 - 1);
  v7 = RtlLengthRequiredSid(v6 - 1);
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    v8 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))((unsigned int)v7);
  }
  else
  {
    v10 = (void *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))((unsigned int)v7);
    v8 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, v7);
      *a2 = v8;
      goto LABEL_7;
    }
  }
  *a2 = v8;
  if ( v8 )
  {
LABEL_7:
    v11 = RtlSubAuthorityCountSid(Sid);
    --*v11;
    v9 = RtlCopySid(v7, *a2, Sid);
    v12 = RtlSubAuthorityCountSid(Sid);
    ++*v12;
    return v9;
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x180019334  push    rbx
0x180019336  push    rbp
0x180019337  push    rsi
0x180019338  push    rdi
0x180019339  sub     rsp, 28h
0x18001933d  mov     rdi, r8
0x180019340  mov     rsi, rdx
0x180019343  mov     rbp, rcx
0x180019346  call    cs:__imp_RtlSubAuthorityCountSid
0x18001934c  mov     rcx, rbp; Sid
0x18001934f  movzx   ebx, byte ptr [rax]
0x180019352  lea     edx, [rbx-1]; SubAuthority
0x180019355  call    cs:__imp_RtlSubAuthoritySid
0x18001935b  lea     ecx, [rbx-1]; SubAuthorityCount
0x18001935e  mov     r9d, [rax]
0x180019361  mov     [rdi], r9d
0x180019364  call    cs:__imp_RtlLengthRequiredSid
0x18001936a  mov     edi, eax
0x18001936c  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180019373  cmp     dword ptr [rax+0D0h], 1
0x18001937a  jnz     short loc_1800193A3
0x18001937c  mov     rdx, [rax+0F0h]
0x180019383  mov     ecx, edi
0x180019385  mov     rax, [rdx+180h]
0x18001938c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019391  mov     rbx, rax
0x180019394  mov     [rsi], rbx
0x180019397  test    rbx, rbx
0x18001939a  jnz     short loc_1800193CC
0x18001939c  mov     ebx, 0C0000017h
0x1800193a1  jmp     short loc_1800193F2
0x1800193a3  mov     rax, [rax+0F8h]
0x1800193aa  mov     ecx, edi
0x1800193ac  mov     rax, [rax]
0x1800193af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800193b4  mov     rbx, rax
0x1800193b7  test    rax, rax
0x1800193ba  jz      short loc_180019394
0x1800193bc  mov     r8, rdi; Size
0x1800193bf  xor     edx, edx; Val
0x1800193c1  mov     rcx, rax; void *
0x1800193c4  call    memset_0
0x1800193c9  mov     [rsi], rbx
0x1800193cc  mov     rcx, rbp; Sid
0x1800193cf  call    cs:__imp_RtlSubAuthorityCountSid
0x1800193d5  mov     r8, rbp; SourceSid
0x1800193d8  mov     ecx, edi; DestinationSidLength
0x1800193da  dec     byte ptr [rax]
0x1800193dc  mov     rdx, [rsi]; DestinationSid
0x1800193df  call    cs:__imp_RtlCopySid
0x1800193e5  mov     rcx, rbp; Sid
0x1800193e8  mov     ebx, eax
0x1800193ea  call    cs:__imp_RtlSubAuthorityCountSid
0x1800193f0  inc     byte ptr [rax]
0x1800193f2  mov     eax, ebx
0x1800193f4  add     rsp, 28h
0x1800193f8  pop     rdi
0x1800193f9  pop     rsi
0x1800193fa  pop     rbp
0x1800193fb  pop     rbx
0x1800193fc  retn
```
