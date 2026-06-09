# LsapAuMarshalSIDsToTokenInfo(_SID_AND_ATTRIBUTES *,uchar * *,_SID_AND_ATTRIBUTES *,ulong,ulong,_SAMPR_ULONG_ARRAY,_SAMPR_ULONG_ARRAY,void * *,ulong,int,void *,ulong,int *,void * *)

- ea: `0x180014e94`
- end: `0x180015248`
- name: `?LsapAuMarshalSIDsToTokenInfo@@YAXPEAU_SID_AND_ATTRIBUTES@@PEAPEAE0KKU_SAMPR_ULONG_ARRAY@@2PEAPEAXKHPEAXKPEAH3@Z`
- size: `948`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001531c`

## callees

- `0x180014e94`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180014ef0`
- `ntdll!RtlCopySid` at `0x180014f5b`
- `ntdll!RtlCopySid` at `0x180014fc7`
- `ntdll!RtlCopySid` at `0x180015080`
- `ntdll!RtlCopySid` at `0x180015116`
- `ntdll!RtlCopySid` at `0x18001517a`
- `ntdll!RtlCopySid` at `0x1800151ff`
- `ntdll!RtlCopySid` at `0x180014ef0`
- `ntdll!RtlCopySid` at `0x180014f5b`
- `ntdll!RtlCopySid` at `0x180014fc7`
- `ntdll!RtlCopySid` at `0x180015080`
- `ntdll!RtlCopySid` at `0x180015116`
- `ntdll!RtlCopySid` at `0x18001517a`
- `ntdll!RtlCopySid` at `0x1800151ff`
- `ntdll!RtlSubAuthoritySid` at `0x180014fe7`
- `ntdll!RtlSubAuthoritySid` at `0x18001519a`
- `ntdll!RtlSubAuthoritySid` at `0x180014fe7`
- `ntdll!RtlSubAuthoritySid` at `0x18001519a`
- `ntdll!RtlLengthSid` at `0x180014ed8`
- `ntdll!RtlLengthSid` at `0x180014f3a`
- `ntdll!RtlLengthSid` at `0x180015068`
- `ntdll!RtlLengthSid` at `0x1800150ff`
- `ntdll!RtlLengthSid` at `0x180014ed8`
- `ntdll!RtlLengthSid` at `0x180014f3a`
- `ntdll!RtlLengthSid` at `0x180015068`
- `ntdll!RtlLengthSid` at `0x1800150ff`

## pseudocode

```c
int __fastcall LsapAuMarshalSIDsToTokenInfo(
        __int64 a1,
        PSID *a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        unsigned int a9,
        int a10,
        __int64 a11,
        unsigned int a12,
        _DWORD *a13,
        _QWORD *a14)
{
  unsigned int v14; // r15d
  unsigned int v15; // esi
  __int64 v16; // r13
  __int64 v19; // r12
  __int64 v20; // rdi
  ULONG v21; // eax
  __int64 v22; // rbx
  PSID v23; // r8
  __int64 v24; // rdx
  ULONG v25; // eax
  __int64 v26; // rbx
  PSID v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 v30; // rax
  __int64 v31; // r12
  ULONG v32; // ecx
  ULONG v33; // ebx
  PULONG v34; // rax
  PSID v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r12
  __int64 v39; // rdi
  ULONG v40; // eax
  __int64 v41; // rbx
  PSID v42; // r8
  __int64 v43; // rdx
  __int64 i; // r15
  ULONG v45; // eax
  __int64 v46; // rdi
  PSID v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r9
  ULONG v50; // ebx
  PULONG v51; // rax
  char *v52; // rcx
  __int64 v53; // rax
  unsigned int j; // ebx
  char *v55; // rcx
  __int64 v56; // rax

  v14 = a5;
  v15 = 0;
  v16 = a3;
  if ( a5 )
  {
    v19 = 0;
    do
    {
      v20 = 2 * v19;
      v21 = RtlLengthSid(*(PSID *)(v16 + 16 * v19));
      v22 = v21;
      RtlCopySid(v21, *a2, *(PSID *)(v16 + 16 * v19));
      v23 = *a2;
      ++v19;
      v24 = 2LL * v15;
      *a2 = (char *)*a2 + v22;
      ++v15;
      *(_QWORD *)(a1 + 8 * v24) = v23;
      *(_DWORD *)(a1 + 8 * v24 + 8) = *(_DWORD *)(v16 + 8 * v20 + 8);
    }
    while ( v15 < a5 );
  }
  if ( a10 )
  {
    v25 = RtlLengthSid(*((PSID *)WellKnownSids + 396));
    v26 = v25;
    RtlCopySid(v25, *a2, *((PSID *)WellKnownSids + 396));
    v27 = *a2;
    v28 = v15++;
    v28 *= 2;
    *a2 = (char *)*a2 + v26;
    *(_QWORD *)(a1 + 8 * v28) = v27;
    *(_DWORD *)(a1 + 8 * v28 + 8) = 7;
  }
  v29 = 0;
  if ( *(_DWORD *)a6 )
  {
    LODWORD(v49) = LsapAccountDomainMemberSidLength;
    do
    {
      RtlCopySid(v49, *a2, LsapAccountDomainMemberSid);
      v50 = *(_DWORD *)(*(_QWORD *)(a6 + 8) + 4 * v29);
      v51 = RtlSubAuthoritySid(*a2, (unsigned int)LsapAccountDomainSubCount - 1);
      v52 = (char *)*a2;
      v29 = (unsigned int)(v29 + 1);
      v49 = LsapAccountDomainMemberSidLength;
      *v51 = v50;
      v53 = v15++;
      v53 *= 2;
      *(_QWORD *)(a1 + 8 * v53) = v52;
      *(_DWORD *)(a1 + 8 * v53 + 8) = 7;
      *a2 = &v52[v49];
    }
    while ( (unsigned int)v29 < *(_DWORD *)a6 );
  }
  LODWORD(v30) = a7;
  v31 = 0;
  if ( *(_DWORD *)a7 )
  {
    v32 = LsapBuiltinDomainMemberSidLength;
    do
    {
      RtlCopySid(v32, *a2, LsapBuiltinDomainMemberSid);
      v33 = *(_DWORD *)(*(_QWORD *)(a7 + 8) + 4 * v31);
      v34 = RtlSubAuthoritySid(*a2, (unsigned int)LsapBuiltinDomainSubCount - 1);
      v35 = *a2;
      v36 = 2LL * v15;
      *v34 = v33;
      v37 = *(_QWORD *)(a7 + 8);
      *(_QWORD *)(a1 + 8 * v36) = v35;
      *(_DWORD *)(a1 + 8 * v36 + 8) = 7;
      if ( *(_DWORD *)(v37 + 4 * v31) == 544 )
      {
        if ( a14 )
        {
          *(_DWORD *)(a1 + 16LL * v15 + 8) = 15;
          *a14 = v35;
        }
      }
      else if ( *(_DWORD *)(v37 + 4 * v31) == 569 )
      {
        *a13 = 1;
      }
      v32 = LsapBuiltinDomainMemberSidLength;
      ++v15;
      v31 = (unsigned int)(v31 + 1);
      v30 = (__int64)v35 + LsapBuiltinDomainMemberSidLength;
      *a2 = (PSID)v30;
    }
    while ( (unsigned int)v31 < *(_DWORD *)a7 );
    v14 = a5;
    v16 = a3;
  }
  if ( v14 < a4 )
  {
    v38 = v14;
    do
    {
      v39 = 2 * v38;
      v40 = RtlLengthSid(*(PSID *)(v16 + 16 * v38));
      v41 = v40;
      LODWORD(v30) = RtlCopySid(v40, *a2, *(PSID *)(v16 + 16 * v38));
      v42 = *a2;
      ++v14;
      v43 = 2LL * v15;
      *a2 = (char *)*a2 + v41;
      ++v15;
      ++v38;
      *(_QWORD *)(a1 + 8 * v43) = v42;
      *(_DWORD *)(a1 + 8 * v43 + 8) = *(_DWORD *)(v16 + 8 * v39 + 8);
    }
    while ( v14 < a4 );
  }
  if ( a8 )
  {
    for ( i = 0; (unsigned int)i < a9; *(_DWORD *)(a1 + 8 * v48 + 8) = 7 )
    {
      v45 = RtlLengthSid(*(PSID *)(a8 + 8 * i));
      v46 = v45;
      LODWORD(v30) = RtlCopySid(v45, *a2, *(PSID *)(a8 + 8 * i));
      v47 = *a2;
      i = (unsigned int)(i + 1);
      v48 = 2LL * v15;
      *a2 = (char *)*a2 + v46;
      ++v15;
      *(_QWORD *)(a1 + 8 * v48) = v47;
    }
  }
  if ( a11 )
  {
    for ( j = 0; j < a12; *a2 = v55 + 44 )
    {
      RtlCopySid(0x2Cu, *a2, (PSID)(a11 + 44LL * j));
      v55 = (char *)*a2;
      ++j;
      v56 = v15++;
      v30 = 2 * v56;
      *(_QWORD *)(a1 + 8 * v30) = *a2;
      *(_DWORD *)(a1 + 8 * v30 + 8) = 7;
      LODWORD(v30) = (_DWORD)v55 + 44;
    }
  }
  return v30;
}

```

## disassembly

```asm
0x180014e94  mov     [rsp+arg_0], rbx
0x180014e99  mov     [rsp+arg_18], r9d
0x180014e9e  mov     [rsp+arg_10], r8
0x180014ea3  push    rbp
0x180014ea4  push    rsi
0x180014ea5  push    rdi
0x180014ea6  push    r12
0x180014ea8  push    r13
0x180014eaa  push    r14
0x180014eac  push    r15
0x180014eae  sub     rsp, 20h
0x180014eb2  mov     r15d, [rsp+58h+arg_20]
0x180014eba  xor     esi, esi
0x180014ebc  mov     r13, r8
0x180014ebf  mov     r14, rdx
0x180014ec2  mov     rbp, rcx
0x180014ec5  test    r15d, r15d
0x180014ec8  jz      short loc_180014F22
0x180014eca  xor     r12d, r12d
0x180014ecd  mov     rdi, r12
0x180014ed0  add     rdi, rdi
0x180014ed3  mov     rcx, [r13+rdi*8+0]; Sid
0x180014ed8  call    cs:__imp_RtlLengthSid
0x180014edf  nop     dword ptr [rax+rax+00h]
0x180014ee4  mov     r8, [r13+rdi*8+0]; SourceSid
0x180014ee9  mov     ecx, eax; DestinationSidLength
0x180014eeb  mov     rdx, [r14]; DestinationSid
0x180014eee  mov     ebx, eax
0x180014ef0  call    cs:__imp_RtlCopySid
0x180014ef7  nop     dword ptr [rax+rax+00h]
0x180014efc  mov     r8, [r14]
0x180014eff  inc     r12
0x180014f02  mov     edx, esi
0x180014f04  add     rbx, r8
0x180014f07  add     rdx, rdx
0x180014f0a  mov     [r14], rbx
0x180014f0d  inc     esi
0x180014f0f  mov     [rbp+rdx*8+0], r8
0x180014f14  mov     ecx, [r13+rdi*8+8]
0x180014f19  mov     [rbp+rdx*8+8], ecx
0x180014f1d  cmp     esi, r15d
0x180014f20  jb      short loc_180014ECD
0x180014f22  cmp     [rsp+58h+arg_48], 0
0x180014f2a  jz      short loc_180014F84
0x180014f2c  mov     rcx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180014f33  mov     rcx, [rcx+0C60h]; Sid
0x180014f3a  call    cs:__imp_RtlLengthSid
0x180014f41  nop     dword ptr [rax+rax+00h]
0x180014f46  mov     r8, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180014f4d  mov     ecx, eax; DestinationSidLength
0x180014f4f  mov     rdx, [r14]; DestinationSid
0x180014f52  mov     ebx, eax
0x180014f54  mov     r8, [r8+0C60h]; SourceSid
0x180014f5b  call    cs:__imp_RtlCopySid
0x180014f62  nop     dword ptr [rax+rax+00h]
0x180014f67  mov     rdx, [r14]
0x180014f6a  mov     ecx, esi
0x180014f6c  inc     esi
0x180014f6e  add     rcx, rcx
0x180014f71  add     rbx, rdx
0x180014f74  mov     [r14], rbx
0x180014f77  mov     [rbp+rcx*8+0], rdx
0x180014f7c  mov     dword ptr [rbp+rcx*8+8], 7
0x180014f84  mov     r12, [rsp+58h+arg_28]
0x180014f8c  xor     edi, edi
0x180014f8e  cmp     [r12], edi
0x180014f92  ja      loc_180015166
0x180014f98  mov     rax, [rsp+58h+arg_30]
0x180014fa0  xor     r12d, r12d
0x180014fa3  cmp     [rax], r12d
0x180014fa6  jbe     loc_180015053
0x180014fac  mov     ecx, cs:?LsapBuiltinDomainMemberSidLength@@3KA; DestinationSidLength
0x180014fb2  mov     r13, rax
0x180014fb5  mov     r15, [rsp+58h+arg_68]
0x180014fbd  mov     r8, cs:?LsapBuiltinDomainMemberSid@@3PEAXEA; SourceSid
0x180014fc4  mov     rdx, [r14]; DestinationSid
0x180014fc7  call    cs:__imp_RtlCopySid
0x180014fce  nop     dword ptr [rax+rax+00h]
0x180014fd3  mov     rax, [r13+8]
0x180014fd7  movzx   edx, cs:?LsapBuiltinDomainSubCount@@3EA; uchar LsapBuiltinDomainSubCount
0x180014fde  mov     rcx, [r14]; Sid
0x180014fe1  dec     edx; SubAuthority
0x180014fe3  mov     ebx, [rax+r12*4]
0x180014fe7  call    cs:__imp_RtlSubAuthoritySid
0x180014fee  nop     dword ptr [rax+rax+00h]
0x180014ff3  mov     rdx, [r14]
0x180014ff6  mov     ecx, esi
0x180014ff8  add     rcx, rcx
0x180014ffb  mov     [rax], ebx
0x180014ffd  mov     rax, [r13+8]
0x180015001  mov     [rbp+rcx*8+0], rdx
0x180015006  mov     dword ptr [rbp+rcx*8+8], 7
0x18001500e  cmp     dword ptr [rax+r12*4], 220h
0x180015016  jz      loc_18001514D
0x18001501c  cmp     dword ptr [rax+r12*4], 239h
0x180015024  jz      loc_180015235
0x18001502a  mov     ecx, cs:?LsapBuiltinDomainMemberSidLength@@3KA; ulong LsapBuiltinDomainMemberSidLength
0x180015030  inc     esi
0x180015032  inc     r12d
0x180015035  lea     rax, [rdx+rcx]
0x180015039  mov     [r14], rax
0x18001503c  cmp     r12d, [r13+0]
0x180015040  jb      loc_180014FBD
0x180015046  mov     r15d, [rsp+58h+arg_20]
0x18001504e  mov     r13, [rsp+58h+arg_10]
0x180015053  cmp     r15d, [rsp+58h+arg_18]
0x180015058  jnb     short loc_1800150B7
0x18001505a  mov     r12d, r15d
0x18001505d  mov     rdi, r12
0x180015060  add     rdi, rdi
0x180015063  mov     rcx, [r13+rdi*8+0]; Sid
0x180015068  call    cs:__imp_RtlLengthSid
0x18001506f  nop     dword ptr [rax+rax+00h]
0x180015074  mov     r8, [r13+rdi*8+0]; SourceSid
0x180015079  mov     ecx, eax; DestinationSidLength
0x18001507b  mov     rdx, [r14]; DestinationSid
0x18001507e  mov     ebx, eax
0x180015080  call    cs:__imp_RtlCopySid
0x180015087  nop     dword ptr [rax+rax+00h]
0x18001508c  mov     r8, [r14]
0x18001508f  inc     r15d
0x180015092  mov     edx, esi
0x180015094  add     rbx, r8
0x180015097  add     rdx, rdx
0x18001509a  mov     [r14], rbx
0x18001509d  inc     esi
0x18001509f  inc     r12
0x1800150a2  mov     [rbp+rdx*8+0], r8
0x1800150a7  mov     ecx, [r13+rdi*8+8]
0x1800150ac  mov     [rbp+rdx*8+8], ecx
0x1800150b0  cmp     r15d, [rsp+58h+arg_18]
0x1800150b5  jb      short loc_18001505D
0x1800150b7  mov     r12, [rsp+58h+arg_38]
0x1800150bf  test    r12, r12
0x1800150c2  jnz     short loc_1800150EB
0x1800150c4  mov     rdi, [rsp+58h+arg_50]
0x1800150cc  test    rdi, rdi
0x1800150cf  jnz     loc_1800151DB
0x1800150d5  mov     rbx, [rsp+58h+arg_0]
0x1800150da  add     rsp, 20h
0x1800150de  pop     r15
0x1800150e0  pop     r14
0x1800150e2  pop     r13
0x1800150e4  pop     r12
0x1800150e6  pop     rdi
0x1800150e7  pop     rsi
0x1800150e8  pop     rbp
0x1800150e9  retn
0x1800150eb  mov     r13d, [rsp+58h+arg_40]
0x1800150f3  xor     r15d, r15d
0x1800150f6  test    r13d, r13d
0x1800150f9  jz      short loc_1800150C4
0x1800150fb  mov     rcx, [r12+r15*8]; Sid
0x1800150ff  call    cs:__imp_RtlLengthSid
0x180015106  nop     dword ptr [rax+rax+00h]
0x18001510b  mov     r8, [r12+r15*8]; SourceSid
0x18001510f  mov     ecx, eax; DestinationSidLength
0x180015111  mov     rdx, [r14]; DestinationSid
0x180015114  mov     edi, eax
0x180015116  call    cs:__imp_RtlCopySid
0x18001511d  nop     dword ptr [rax+rax+00h]
0x180015122  mov     rdx, [r14]
0x180015125  inc     r15d
0x180015128  mov     ecx, esi
0x18001512a  add     rdi, rdx
0x18001512d  add     rcx, rcx
0x180015130  mov     [r14], rdi
0x180015133  inc     esi
0x180015135  mov     [rbp+rcx*8+0], rdx
0x18001513a  mov     dword ptr [rbp+rcx*8+8], 7
0x180015142  cmp     r15d, r13d
0x180015145  jnb     loc_1800150C4
0x18001514b  jmp     short loc_1800150FB
0x18001514d  test    r15, r15
0x180015150  jz      loc_18001502A
0x180015156  mov     dword ptr [rbp+rcx*8+8], 0Fh
0x18001515e  mov     [r15], rdx
0x180015161  jmp     loc_18001502A
0x180015166  mov     r9d, cs:?LsapAccountDomainMemberSidLength@@3KA; ulong LsapAccountDomainMemberSidLength
0x18001516d  mov     r8, cs:?LsapAccountDomainMemberSid@@3PEAXEA; SourceSid
0x180015174  mov     ecx, r9d; DestinationSidLength
0x180015177  mov     rdx, [r14]; DestinationSid
0x18001517a  call    cs:__imp_RtlCopySid
0x180015181  nop     dword ptr [rax+rax+00h]
0x180015186  mov     rax, [r12+8]
0x18001518b  movzx   edx, cs:?LsapAccountDomainSubCount@@3EA; uchar LsapAccountDomainSubCount
0x180015192  mov     rcx, [r14]; Sid
0x180015195  dec     edx; SubAuthority
0x180015197  mov     ebx, [rax+rdi*4]
0x18001519a  call    cs:__imp_RtlSubAuthoritySid
0x1800151a1  nop     dword ptr [rax+rax+00h]
0x1800151a6  mov     rcx, [r14]
0x1800151a9  inc     edi
0x1800151ab  mov     r9d, cs:?LsapAccountDomainMemberSidLength@@3KA; ulong LsapAccountDomainMemberSidLength
0x1800151b2  mov     [rax], ebx
0x1800151b4  mov     eax, esi
0x1800151b6  inc     esi
0x1800151b8  add     rax, rax
0x1800151bb  mov     [rbp+rax*8+0], rcx
0x1800151c0  mov     dword ptr [rbp+rax*8+8], 7
0x1800151c8  lea     rax, [rcx+r9]
0x1800151cc  mov     [r14], rax
0x1800151cf  cmp     edi, [r12]
0x1800151d3  jnb     loc_180014F98
0x1800151d9  jmp     short loc_18001516D
0x1800151db  mov     r15d, [rsp+58h+arg_58]
0x1800151e3  xor     ebx, ebx
0x1800151e5  test    r15d, r15d
0x1800151e8  jz      loc_1800150D5
0x1800151ee  mov     rdx, [r14]; DestinationSid
0x1800151f1  mov     ecx, 2Ch ; ','; DestinationSidLength
0x1800151f6  mov     eax, ebx
0x1800151f8  imul    r8, rax, 2Ch ; ','
0x1800151fc  add     r8, rdi; SourceSid
0x1800151ff  call    cs:__imp_RtlCopySid
0x180015206  nop     dword ptr [rax+rax+00h]
0x18001520b  mov     rcx, [r14]
0x18001520e  inc     ebx
0x180015210  mov     eax, esi
0x180015212  inc     esi
0x180015214  add     rax, rax
0x180015217  mov     [rbp+rax*8+0], rcx
0x18001521c  mov     dword ptr [rbp+rax*8+8], 7
0x180015224  lea     rax, [rcx+2Ch]
0x180015228  mov     [r14], rax
0x18001522b  cmp     ebx, r15d
0x18001522e  jb      short loc_1800151EE
0x180015230  jmp     loc_1800150D5
0x180015235  mov     rax, [rsp+58h+arg_60]
0x18001523d  mov     dword ptr [rax], 1
0x180015243  jmp     loc_18001502A
```
