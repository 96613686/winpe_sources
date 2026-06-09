# Pku2uFilterGroupMembership(_SID_AND_ATTRIBUTES_LIST *,void *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,ulong *)

- ea: `0x18003970c`
- end: `0x180039900`
- name: `?Pku2uFilterGroupMembership@@YAJPEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_SAMPR_GET_GROUPS_BUFFER@@0PEAK@Z`
- size: `500`
- prototype: `int(struct _SID_AND_ATTRIBUTES_LIST *, void *, struct _SAMPR_GET_GROUPS_BUFFER *, struct _SID_AND_ATTRIBUTES_LIST *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004830`
- `0x180038e7c`

## callees

- `0x180018870`
- `0x18003970c`
- `0x180044f80`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180039893`
- `ntdll!RtlSubAuthorityCountSid` at `0x180039893`
- `ntdll!RtlLengthRequiredSid` at `0x180039778`
- `ntdll!RtlLengthRequiredSid` at `0x180039778`
- `ntdll!RtlSubAuthoritySid` at `0x1800398a6`
- `ntdll!RtlSubAuthoritySid` at `0x1800398a6`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180039784`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180039790`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180039784`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180039790`
- `ntdll!RtlLengthSid` at `0x1800397c6`
- `ntdll!RtlLengthSid` at `0x1800397c6`

## pseudocode

```c
__int64 __fastcall Pku2uFilterGroupMembership(
        struct _SID_AND_ATTRIBUTES_LIST *a1,
        unsigned __int8 *a2,
        struct _SAMPR_GET_GROUPS_BUFFER *a3,
        struct _SID_AND_ATTRIBUTES_LIST *a4,
        unsigned int *a5)
{
  struct _SID_AND_ATTRIBUTES_LIST *v5; // r12
  unsigned int v7; // ebp
  unsigned int v8; // r14d
  unsigned int v9; // r13d
  ULONG v11; // ecx
  __int64 v12; // r15
  unsigned __int8 *v13; // rbx
  ULONG v14; // edi
  PSID_IDENTIFIER_AUTHORITY v15; // rbx
  PSID_IDENTIFIER_AUTHORITY v16; // rax
  void *v17; // rax
  unsigned int v18; // edi
  void *v19; // rax
  unsigned int v20; // r13d
  unsigned int v21; // r15d
  unsigned int v22; // ebp
  __int64 v23; // rax
  int v24; // ecx
  __int64 v25; // rbx
  PUCHAR v26; // rax
  __int64 v27; // rdx
  unsigned int v29; // [rsp+70h] [rbp+8h]

  v5 = a4;
  *(_DWORD *)a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  v7 = 0;
  *(_DWORD *)a4 = 0;
  v8 = 0;
  *((_QWORD *)a4 + 1) = 0;
  v9 = 0;
  v29 = 0;
  if ( *(_DWORD *)a1 )
  {
    do
    {
      v11 = a2[1];
      v12 = 16LL * v9;
      v13 = *(unsigned __int8 **)(v12 + *((_QWORD *)a1 + 1));
      if ( v13[1] == v11 + 1
        && (v14 = RtlLengthRequiredSid(v11) - 2,
            v15 = RtlIdentifierAuthoritySid(v13),
            v16 = RtlIdentifierAuthoritySid(a2),
            !memcmp_0(v16, v15, v14)) )
      {
        *(_DWORD *)(v12 + *((_QWORD *)a1 + 1) + 8) |= 0x20000000u;
        ++v7;
      }
      else
      {
        ++v8;
        v29 += RtlLengthSid(*(PSID *)(v12 + *((_QWORD *)a1 + 1))) + 16;
      }
      ++v9;
    }
    while ( v9 < *(_DWORD *)a1 );
    v5 = a4;
    if ( v7 )
    {
      v17 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 8LL * v7);
      *((_QWORD *)a3 + 1) = v17;
      if ( !v17 )
        return (unsigned int)-1073741801;
      *(_DWORD *)a3 = v7;
    }
    if ( v8 )
    {
      v19 = basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, 16LL * v8);
      *((_QWORD *)a4 + 1) = v19;
      if ( !v19 )
        return (unsigned int)-1073741801;
      *(_DWORD *)a4 = v8;
    }
  }
  v18 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  if ( *(_DWORD *)a1 )
  {
    do
    {
      v23 = *((_QWORD *)a1 + 1);
      v24 = *(_DWORD *)(v23 + 16LL * v22 + 8);
      if ( (v24 & 0x20000000) != 0 )
      {
        v25 = v20;
        *(_DWORD *)(*((_QWORD *)a3 + 1) + 8LL * v20 + 4) = v24 & 0xDFFFFFFF;
        v26 = RtlSubAuthorityCountSid(*(PSID *)(*((_QWORD *)a1 + 1) + 16LL * v22));
        ++v20;
        *(_DWORD *)(*((_QWORD *)a3 + 1) + 8 * v25) = *RtlSubAuthoritySid(
                                                        *(PSID *)(*((_QWORD *)a1 + 1) + 16LL * v22),
                                                        (unsigned int)*v26 - 1);
      }
      else
      {
        v27 = 2LL * v21++;
        *(_OWORD *)(*((_QWORD *)v5 + 1) + 8 * v27) = *(_OWORD *)(v23 + 16LL * v22);
      }
      ++v22;
    }
    while ( v22 < *(_DWORD *)a1 );
    v18 = 0;
  }
  *a5 = v29;
  return v18;
}

```

## disassembly

```asm
0x18003970c  mov     rax, rsp
0x18003970f  mov     [rax+20h], r9
0x180039713  mov     [rax+18h], r8
0x180039717  mov     [rax+10h], rdx
0x18003971b  push    rbx
0x18003971c  push    rbp
0x18003971d  push    rsi
0x18003971e  push    rdi
0x18003971f  push    r12
0x180039721  push    r13
0x180039723  push    r14
0x180039725  push    r15
0x180039727  sub     rsp, 28h
0x18003972b  xor     ebx, ebx
0x18003972d  mov     r12, r9
0x180039730  mov     [r8], ebx
0x180039733  mov     rsi, rcx
0x180039736  mov     [r8+8], rbx
0x18003973a  mov     ebp, ebx
0x18003973c  mov     [r9], ebx
0x18003973f  mov     r14d, ebx
0x180039742  mov     [r9+8], rbx
0x180039746  mov     r13d, ebx
0x180039749  mov     [rsp+68h+arg_0], ebx
0x18003974d  cmp     [rcx], ebx
0x18003974f  jbe     loc_180039846
0x180039755  mov     r12, rdx
0x180039758  mov     rax, [rsi+8]
0x18003975c  movzx   ecx, byte ptr [r12+1]; SubAuthorityCount
0x180039762  mov     r15d, r13d
0x180039765  shl     r15, 4
0x180039769  mov     rbx, [r15+rax]
0x18003976d  lea     eax, [rcx+1]
0x180039770  movzx   edx, byte ptr [rbx+1]
0x180039774  cmp     edx, eax
0x180039776  jnz     short loc_1800397B9
0x180039778  call    cs:__imp_RtlLengthRequiredSid
0x18003977e  mov     rcx, rbx; Sid
0x180039781  lea     edi, [rax-2]
0x180039784  call    cs:__imp_RtlIdentifierAuthoritySid
0x18003978a  mov     rcx, r12; Sid
0x18003978d  mov     rbx, rax
0x180039790  call    cs:__imp_RtlIdentifierAuthoritySid
0x180039796  mov     r8d, edi; Size
0x180039799  mov     rdx, rbx; Buf2
0x18003979c  mov     rcx, rax; Buf1
0x18003979f  call    memcmp_0
0x1800397a4  xor     ebx, ebx
0x1800397a6  test    eax, eax
0x1800397a8  jnz     short loc_1800397BB
0x1800397aa  mov     rax, [rsi+8]
0x1800397ae  bts     dword ptr [r15+rax+8], 1Dh
0x1800397b5  inc     ebp
0x1800397b7  jmp     short loc_1800397D9
0x1800397b9  xor     ebx, ebx
0x1800397bb  mov     rcx, [rsi+8]
0x1800397bf  inc     r14d
0x1800397c2  mov     rcx, [r15+rcx]; Sid
0x1800397c6  call    cs:__imp_RtlLengthSid
0x1800397cc  mov     ecx, [rsp+68h+arg_0]
0x1800397d0  add     ecx, 10h
0x1800397d3  add     ecx, eax
0x1800397d5  mov     [rsp+68h+arg_0], ecx
0x1800397d9  inc     r13d
0x1800397dc  cmp     r13d, [rsi]
0x1800397df  jb      loc_180039758
0x1800397e5  mov     r12, [rsp+68h+arg_18]
0x1800397ed  test    ebp, ebp
0x1800397ef  jz      short loc_180039820
0x1800397f1  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x1800397f8  mov     edx, ebp
0x1800397fa  shl     rdx, 3; unsigned __int64
0x1800397fe  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180039803  mov     rcx, [rsp+68h+arg_10]
0x18003980b  mov     [rcx+8], rax
0x18003980f  test    rax, rax
0x180039812  jnz     short loc_18003981E
0x180039814  mov     edi, 0C0000017h
0x180039819  jmp     loc_1800398ED
0x18003981e  mov     [rcx], ebp
0x180039820  test    r14d, r14d
0x180039823  jz      short loc_180039846
0x180039825  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18003982c  mov     edx, r14d
0x18003982f  shl     rdx, 4; unsigned __int64
0x180039833  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180039838  mov     [r12+8], rax
0x18003983d  test    rax, rax
0x180039840  jz      short loc_180039814
0x180039842  mov     [r12], r14d
0x180039846  mov     edi, ebx
0x180039848  mov     dword ptr [rsp+68h+arg_18], ebx
0x18003984f  mov     r13d, ebx
0x180039852  mov     r15d, ebx
0x180039855  mov     ebp, ebx
0x180039857  cmp     [rsi], ebx
0x180039859  jbe     loc_1800398DF
0x18003985f  mov     rdi, [rsp+68h+arg_10]
0x180039867  mov     rax, [rsi+8]
0x18003986b  mov     r14d, ebp
0x18003986e  add     r14, r14
0x180039871  mov     ecx, [rax+r14*8+8]
0x180039876  bt      ecx, 1Dh
0x18003987a  jnb     short loc_1800398BA
0x18003987c  mov     rax, [rdi+8]
0x180039880  btr     ecx, 1Dh
0x180039884  mov     ebx, r13d
0x180039887  mov     [rax+rbx*8+4], ecx
0x18003988b  mov     rcx, [rsi+8]
0x18003988f  mov     rcx, [rcx+r14*8]; Sid
0x180039893  call    cs:__imp_RtlSubAuthorityCountSid
0x180039899  mov     rcx, [rsi+8]
0x18003989d  movzx   edx, byte ptr [rax]
0x1800398a0  mov     rcx, [rcx+r14*8]; Sid
0x1800398a4  dec     edx; SubAuthority
0x1800398a6  call    cs:__imp_RtlSubAuthoritySid
0x1800398ac  mov     rcx, [rdi+8]
0x1800398b0  inc     r13d
0x1800398b3  mov     eax, [rax]
0x1800398b5  mov     [rcx+rbx*8], eax
0x1800398b8  jmp     short loc_1800398D2
0x1800398ba  mov     rcx, [r12+8]
0x1800398bf  movups  xmm0, xmmword ptr [rax+r14*8]
0x1800398c4  mov     edx, r15d
0x1800398c7  add     rdx, rdx
0x1800398ca  inc     r15d
0x1800398cd  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x1800398d2  inc     ebp
0x1800398d4  cmp     ebp, [rsi]
0x1800398d6  jb      short loc_180039867
0x1800398d8  mov     edi, dword ptr [rsp+68h+arg_18]
0x1800398df  mov     rcx, [rsp+68h+arg_20]
0x1800398e7  mov     eax, [rsp+68h+arg_0]
0x1800398eb  mov     [rcx], eax
0x1800398ed  mov     eax, edi
0x1800398ef  add     rsp, 28h
0x1800398f3  pop     r15
0x1800398f5  pop     r14
0x1800398f7  pop     r13
0x1800398f9  pop     r12
0x1800398fb  pop     rdi
0x1800398fc  pop     rsi
0x1800398fd  pop     rbp
0x1800398fe  pop     rbx
0x1800398ff  retn
```
