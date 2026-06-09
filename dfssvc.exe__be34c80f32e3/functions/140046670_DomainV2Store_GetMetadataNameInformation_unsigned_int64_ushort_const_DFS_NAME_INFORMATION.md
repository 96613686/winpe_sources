# DomainV2Store::GetMetadataNameInformation(unsigned __int64,ushort const *,_DFS_NAME_INFORMATION_ * *)

- ea: `0x140046670`
- end: `0x140046942`
- name: `?GetMetadataNameInformation@DomainV2Store@@UEAAK_KPEBGPEAPEAU_DFS_NAME_INFORMATION_@@@Z`
- size: `722`
- prototype: `unsigned int(DomainV2Store *__hidden this, unsigned __int64, const unsigned __int16 *, struct _DFS_NAME_INFORMATION_ **)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140008ecc`
- `0x14001e548`
- `0x1400425b8`
- `0x140042a38`
- `0x140046670`
- `0x140048178`
- `0x14004a414`
- `0x140056b20`
- `0x1400586a8`
- `0x14005bf90`
- `0x14005ce22`
- `0x14005ce3a`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1400467f1`
- `ntdll!RtlInitUnicodeStringEx` at `0x140046804`
- `ntdll!RtlInitUnicodeStringEx` at `0x140046838`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400467f1`
- `ntdll!RtlInitUnicodeStringEx` at `0x140046804`
- `ntdll!RtlInitUnicodeStringEx` at `0x140046838`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14004675b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14004685f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14004675b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x14004685f`

## pseudocode

```c
__int64 __fastcall DomainV2Store::GetMetadataNameInformation(
        DomainV2Store *this,
        __int64 a2,
        const unsigned __int16 *a3,
        struct _DFS_NAME_INFORMATION_ **a4)
{
  char *v5; // rbx
  unsigned int inited; // esi
  unsigned int NamedMetadata; // eax
  DomainV2MetadataCache *v8; // rcx
  struct _DFS_DOMAINV2_METADATA *v9; // rdi
  unsigned __int64 v10; // rsi
  const unsigned __int16 *AdDomainName; // rax
  __int64 v12; // rcx
  __int64 v13; // r14
  __int64 v14; // rcx
  unsigned __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // rax
  DWORD v18; // ebx
  __int64 v19; // rsi
  void *v20; // rcx
  size_t v21; // rbp
  char *v22; // rax
  const unsigned __int16 *v23; // rax
  const unsigned __int16 *v24; // r8
  unsigned __int16 *v25; // r14
  DWORD SecurityDescriptorLength; // eax
  int v27; // ecx
  int v28; // eax
  __int128 v29; // xmm0
  unsigned __int16 *v30; // rcx
  struct _DFS_NAME_INFORMATION_ **v31; // rax
  struct _UNICODE_STRING v33; // [rsp+30h] [rbp-48h] BYREF
  struct _DFS_DOMAINV2_METADATA *v34; // [rsp+88h] [rbp+10h] BYREF
  const unsigned __int16 *v35; // [rsp+90h] [rbp+18h]
  struct _DFS_NAME_INFORMATION_ **v36; // [rsp+98h] [rbp+20h]

  v36 = a4;
  v35 = a3;
  v34 = 0;
  v33 = 0;
  v5 = 0;
  inited = DfsRtlInitUnicodeStringEx(&v33, a3);
  if ( !inited )
  {
    NamedMetadata = DomainV2MetadataCache::GetNamedMetadata((DomainV2MetadataCache *)a2, &v33, &v34);
    v9 = v34;
    inited = NamedMetadata;
    if ( !NamedMetadata )
    {
      v10 = 0;
      AdDomainName = DfsGetAdDomainName();
      v12 = -1;
      do
        ++v12;
      while ( AdDomainName[v12] );
      v13 = 2 * v12;
      v14 = *((_QWORD *)v9 + 14);
      v15 = *(unsigned __int16 *)(a2 + 1128) + 8LL + v13;
      if ( v14 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(v14 + 2 * v16) );
        v15 += 2 * v16;
      }
      v17 = *((_QWORD *)v9 + 22);
      v18 = v15 + 152;
      if ( v17 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)(v17 + 2 * v19) );
        v10 = v19 + 1;
        v18 += 2 * v10;
      }
      v20 = (void *)*((_QWORD *)v9 + 24);
      if ( v20 )
        v18 = GetSecurityDescriptorLength(v20) + ((v18 + 7) & 0xFFFFFFF8);
      v21 = v18;
      v22 = (char *)operator new(v18);
      v5 = v22;
      if ( v22 )
      {
        memset_0(v22, 0, v21);
        v23 = DfsGetAdDomainName();
        StringCbPrintfW((unsigned __int16 *)v5 + 76, v15, L"\\\\%s\\%wZ", v23, a2 + 1128);
        v24 = (const unsigned __int16 *)*((_QWORD *)v9 + 14);
        if ( v24 )
          StringCbCatW((unsigned __int16 *)v5 + 76, v15, v24);
        RtlInitUnicodeStringEx((PUNICODE_STRING)v5 + 1, (PCWSTR)v5 + 76);
        RtlInitUnicodeStringEx((PUNICODE_STRING)v5 + 2, (PCWSTR)v5 + 76);
        v25 = (unsigned __int16 *)&v5[2 * (v15 >> 1) + 152];
        if ( v10 )
        {
          StringCchCopyW(v25, v10, *((const unsigned __int16 **)v9 + 22));
          RtlInitUnicodeStringEx((PUNICODE_STRING)(v5 + 72), v25);
          v25 += v10;
        }
        if ( *((_QWORD *)v9 + 24) )
        {
          *((_QWORD *)v5 + 16) = v25;
          SecurityDescriptorLength = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)v9 + 24));
          memcpy_0(*((void **)v5 + 16), *((const void **)v9 + 24), SecurityDescriptorLength);
        }
        v27 = *((_DWORD *)v9 + 42);
        *((_DWORD *)v5 + 16) = v27;
        v28 = *((_DWORD *)v9 + 43);
        *((_DWORD *)v5 + 17) = v28;
        if ( (v28 & 0x80u) != 0 )
          *((_DWORD *)v5 + 16) = v27 | 0x200;
        if ( v35 )
          v29 = *(_OWORD *)((char *)v9 + 136);
        else
          v29 = *(_OWORD *)((char *)v9 + 120);
        *((_OWORD *)v5 + 3) = v29;
        *((_DWORD *)v5 + 28) = *((_DWORD *)v9 + 46);
        *((_DWORD *)v5 + 34) = *((_DWORD *)v9 + 15);
        *((_DWORD *)v5 + 35) = *((_DWORD *)v9 + 16);
        *((_QWORD *)v5 + 18) = *((_QWORD *)v9 + 9);
        v30 = (unsigned __int16 *)*((_QWORD *)v9 + 27);
        if ( !v30 || (inited = DfsGetUTCTimeFromString(v30, (struct _FILETIME *)v5 + 15)) == 0 )
        {
          v31 = v36;
          inited = 0;
          *(_QWORD *)v5 = v9;
          *((_DWORD *)v5 + 2) = 0;
          *v31 = (struct _DFS_NAME_INFORMATION_ *)v5;
          return inited;
        }
      }
      else
      {
        inited = 8;
      }
    }
    if ( v9 )
    {
      if ( *((_QWORD *)v9 + 13) )
        SHashReleaseReference(*(_QWORD *)(a2 + 16), v9);
      else
        DomainV2MetadataCache::ReleaseRootMetadataReference(v8, v9);
      operator delete(v5);
    }
  }
  return inited;
}

```

## disassembly

```asm
0x140046670  mov     rax, rsp
0x140046673  mov     [rax+8], rbx
0x140046677  mov     [rax+20h], r9
0x14004667b  mov     [rax+18h], r8
0x14004667f  push    rbp
0x140046680  push    rsi
0x140046681  push    rdi
0x140046682  push    r12
0x140046684  push    r13
0x140046686  push    r14
0x140046688  push    r15
0x14004668a  sub     rsp, 40h
0x14004668e  mov     r13, rdx
0x140046691  lea     rcx, [rax-48h]
0x140046695  xorps   xmm0, xmm0
0x140046698  xor     r15d, r15d
0x14004669b  mov     rdx, r8
0x14004669e  mov     [rax+10h], r15
0x1400466a2  movups  xmmword ptr [rax-48h], xmm0
0x1400466a6  mov     ebx, r15d
0x1400466a9  call    DfsRtlInitUnicodeStringEx
0x1400466ae  mov     esi, eax
0x1400466b0  test    eax, eax
0x1400466b2  jnz     loc_140046927
0x1400466b8  lea     r8, [rsp+78h+arg_8]; struct _DFS_DOMAINV2_METADATA **
0x1400466c0  mov     rcx, r13; this
0x1400466c3  lea     rdx, [rsp+78h+var_48]; struct _UNICODE_STRING *
0x1400466c8  call    ?GetNamedMetadata@DomainV2MetadataCache@@QEAAKPEAU_UNICODE_STRING@@PEAPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::GetNamedMetadata(_UNICODE_STRING *,_DFS_DOMAINV2_METADATA * *)
0x1400466cd  mov     rdi, [rsp+78h+arg_8]
0x1400466d5  mov     esi, eax
0x1400466d7  test    eax, eax
0x1400466d9  jnz     loc_140046783
0x1400466df  mov     esi, r15d
0x1400466e2  lea     r12, [r13+468h]
0x1400466e9  call    ?DfsGetAdDomainName@@YAPEBGXZ; DfsGetAdDomainName(void)
0x1400466ee  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400466f2  mov     rcx, rdx
0x1400466f5  inc     rcx
0x1400466f8  cmp     [rax+rcx*2], r15w
0x1400466fd  jnz     short loc_1400466F5
0x1400466ff  movzx   eax, word ptr [r12]
0x140046704  lea     r14, [rcx+rcx]
0x140046708  mov     rcx, [rdi+70h]
0x14004670c  add     rax, 8
0x140046710  add     r14, rax
0x140046713  test    rcx, rcx
0x140046716  jz      short loc_140046729
0x140046718  mov     rax, rdx
0x14004671b  inc     rax
0x14004671e  cmp     [rcx+rax*2], r15w
0x140046723  jnz     short loc_14004671B
0x140046725  lea     r14, [r14+rax*2]
0x140046729  mov     rax, [rdi+0B0h]
0x140046730  lea     ebx, [r14+98h]
0x140046737  test    rax, rax
0x14004673a  jz      short loc_14004674F
0x14004673c  mov     rsi, rdx
0x14004673f  inc     rsi
0x140046742  cmp     [rax+rsi*2], r15w
0x140046747  jnz     short loc_14004673F
0x140046749  inc     rsi
0x14004674c  lea     ebx, [rbx+rsi*2]
0x14004674f  mov     rcx, [rdi+0C0h]; pSecurityDescriptor
0x140046756  test    rcx, rcx
0x140046759  jz      short loc_14004676F
0x14004675b  call    cs:__imp_GetSecurityDescriptorLength
0x140046762  nop     dword ptr [rax+rax+00h]
0x140046767  add     ebx, 7
0x14004676a  and     ebx, 0FFFFFFF8h
0x14004676d  add     ebx, eax
0x14004676f  mov     ecx, ebx; Size
0x140046771  mov     ebp, ebx
0x140046773  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140046778  mov     rbx, rax
0x14004677b  test    rax, rax
0x14004677e  jnz     short loc_1400467A3
0x140046780  lea     esi, [rax+8]
0x140046783  test    rdi, rdi
0x140046786  jz      loc_140046927
0x14004678c  mov     rdx, rdi; struct _DFS_DOMAINV2_METADATA *
0x14004678f  cmp     [rdi+68h], r15
0x140046793  jnz     loc_140046916
0x140046799  call    ?ReleaseRootMetadataReference@DomainV2MetadataCache@@AEAAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::ReleaseRootMetadataReference(_DFS_DOMAINV2_METADATA *)
0x14004679e  jmp     loc_14004691F
0x1400467a3  mov     r8, rbp; Size
0x1400467a6  xor     edx, edx; Val
0x1400467a8  mov     rcx, rbx; void *
0x1400467ab  call    memset_0
0x1400467b0  lea     r15, [rbx+98h]
0x1400467b7  call    ?DfsGetAdDomainName@@YAPEBGXZ; DfsGetAdDomainName(void)
0x1400467bc  mov     r9, rax
0x1400467bf  mov     [rsp+78h+var_58], r12
0x1400467c4  lea     r8, aSWz; "\\\\%s\\%wZ"
0x1400467cb  mov     rdx, r14; unsigned __int64
0x1400467ce  mov     rcx, r15; unsigned __int16 *
0x1400467d1  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400467d6  mov     r8, [rdi+70h]; unsigned __int16 *
0x1400467da  test    r8, r8
0x1400467dd  jz      short loc_1400467EA
0x1400467df  mov     rdx, r14; unsigned __int64
0x1400467e2  mov     rcx, r15; unsigned __int16 *
0x1400467e5  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1400467ea  lea     rcx, [rbx+10h]; DestinationString
0x1400467ee  mov     rdx, r15; SourceString
0x1400467f1  call    cs:__imp_RtlInitUnicodeStringEx
0x1400467f8  nop     dword ptr [rax+rax+00h]
0x1400467fd  lea     rcx, [rbx+20h]; DestinationString
0x140046801  mov     rdx, r15; SourceString
0x140046804  call    cs:__imp_RtlInitUnicodeStringEx
0x14004680b  nop     dword ptr [rax+rax+00h]
0x140046810  shr     r14, 1
0x140046813  lea     r14, [r15+r14*2]
0x140046817  xor     r15d, r15d
0x14004681a  test    rsi, rsi
0x14004681d  jz      short loc_140046848
0x14004681f  mov     r8, [rdi+0B0h]; unsigned __int16 *
0x140046826  mov     rdx, rsi; unsigned __int64
0x140046829  mov     rcx, r14; unsigned __int16 *
0x14004682c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140046831  lea     rcx, [rbx+48h]; DestinationString
0x140046835  mov     rdx, r14; SourceString
0x140046838  call    cs:__imp_RtlInitUnicodeStringEx
0x14004683f  nop     dword ptr [rax+rax+00h]
0x140046844  lea     r14, [r14+rsi*2]
0x140046848  cmp     [rdi+0C0h], r15
0x14004684f  jz      short loc_140046881
0x140046851  mov     [rbx+80h], r14
0x140046858  mov     rcx, [rdi+0C0h]; pSecurityDescriptor
0x14004685f  call    cs:__imp_GetSecurityDescriptorLength
0x140046866  nop     dword ptr [rax+rax+00h]
0x14004686b  mov     rdx, [rdi+0C0h]; Src
0x140046872  mov     rcx, [rbx+80h]; void *
0x140046879  mov     r8d, eax; Size
0x14004687c  call    memcpy_0
0x140046881  mov     ecx, [rdi+0A8h]
0x140046887  mov     [rbx+40h], ecx
0x14004688a  mov     eax, [rdi+0ACh]
0x140046890  mov     [rbx+44h], eax
0x140046893  test    al, al
0x140046895  jns     short loc_14004689E
0x140046897  bts     ecx, 9
0x14004689b  mov     [rbx+40h], ecx
0x14004689e  cmp     [rsp+78h+arg_10], r15
0x1400468a6  jnz     short loc_1400468AE
0x1400468a8  movups  xmm0, xmmword ptr [rdi+78h]
0x1400468ac  jmp     short loc_1400468B5
0x1400468ae  movups  xmm0, xmmword ptr [rdi+88h]
0x1400468b5  movdqu  xmmword ptr [rbx+30h], xmm0
0x1400468ba  mov     eax, [rdi+0B8h]
0x1400468c0  mov     [rbx+70h], eax
0x1400468c3  mov     eax, [rdi+3Ch]
0x1400468c6  mov     [rbx+88h], eax
0x1400468cc  mov     eax, [rdi+40h]
0x1400468cf  mov     [rbx+8Ch], eax
0x1400468d5  mov     rax, [rdi+48h]
0x1400468d9  mov     [rbx+90h], rax
0x1400468e0  mov     rcx, [rdi+0D8h]; unsigned __int16 *
0x1400468e7  test    rcx, rcx
0x1400468ea  jz      short loc_1400468FF
0x1400468ec  lea     rdx, [rbx+78h]; struct _FILETIME *
0x1400468f0  call    ?DfsGetUTCTimeFromString@@YAKPEAGPEAU_FILETIME@@@Z; DfsGetUTCTimeFromString(ushort *,_FILETIME *)
0x1400468f5  mov     esi, eax
0x1400468f7  test    eax, eax
0x1400468f9  jnz     loc_140046783
0x1400468ff  mov     rax, [rsp+78h+arg_18]
0x140046907  mov     esi, r15d
0x14004690a  mov     [rbx], rdi
0x14004690d  mov     [rbx+8], r15d
0x140046911  mov     [rax], rbx
0x140046914  jmp     short loc_140046927
0x140046916  mov     rcx, [r13+10h]
0x14004691a  call    SHashReleaseReference
0x14004691f  mov     rcx, rbx; Block
0x140046922  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140046927  mov     rbx, [rsp+78h+arg_0]
0x14004692f  mov     eax, esi
0x140046931  add     rsp, 40h
0x140046935  pop     r15
0x140046937  pop     r14
0x140046939  pop     r13
0x14004693b  pop     r12
0x14004693d  pop     rdi
0x14004693e  pop     rsi
0x14004693f  pop     rbp
0x140046940  retn
```
