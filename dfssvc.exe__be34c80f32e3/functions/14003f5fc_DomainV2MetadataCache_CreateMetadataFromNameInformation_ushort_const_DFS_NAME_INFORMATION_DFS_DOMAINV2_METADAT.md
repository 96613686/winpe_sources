# DomainV2MetadataCache::CreateMetadataFromNameInformation(ushort const *,_DFS_NAME_INFORMATION_ *,_DFS_DOMAINV2_METADATA * *)

- ea: `0x14003f5fc`
- end: `0x14003f825`
- name: `?CreateMetadataFromNameInformation@DomainV2MetadataCache@@QEAAKPEBGPEAU_DFS_NAME_INFORMATION_@@PEAPEAU_DFS_DOMAINV2_METADATA@@@Z`
- size: `553`
- prototype: `unsigned int __fastcall(DomainV2MetadataCache *__hidden this, const unsigned __int16 *, struct _DFS_NAME_INFORMATION_ *, struct _DFS_DOMAINV2_METADATA **)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x140040318`
- `0x1400476b0`

## callees

- `0x1400011d0`
- `0x14000fd24`
- `0x14001e548`
- `0x14003f5fc`
- `0x1400401ac`
- `0x14004079c`
- `0x1400408fc`
- `0x1400425b8`
- `0x140042a38`
- `0x14005bf90`
- `0x14005ce3a`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x14003f643`
- `ntdll!RtlInitUnicodeStringEx` at `0x14003f7b8`
- `ntdll!RtlInitUnicodeStringEx` at `0x14003f643`
- `ntdll!RtlInitUnicodeStringEx` at `0x14003f7b8`
- `RPCRT4!UuidCreate` at `0x14003f6e4`
- `RPCRT4!UuidCreate` at `0x14003f6e4`

## pseudocode

```c
RPC_STATUS __fastcall DomainV2MetadataCache::CreateMetadataFromNameInformation(
        DomainV2MetadataCache *this,
        const unsigned __int16 *a2,
        struct _DFS_NAME_INFORMATION_ *a3,
        struct _DFS_DOMAINV2_METADATA **a4)
{
  char *v6; // rdi
  unsigned int NamedMetadata; // eax
  struct _DFS_DOMAINV2_METADATA *v9; // rsi
  int v10; // ebx
  DomainV2MetadataCache *v11; // rcx
  RPC_STATUS result; // eax
  char *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  unsigned __int16 *v17; // rax
  struct _DFS_DOMAINV2_METADATA *v18; // [rsp+30h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-70h] BYREF
  UUID Uuid; // [rsp+48h] [rbp-60h] BYREF

  DestinationString = 0;
  v18 = 0;
  v6 = 0;
  Uuid = 0;
  RtlInitUnicodeStringEx(&DestinationString, a2);
  NamedMetadata = DomainV2MetadataCache::GetNamedMetadata(this, &DestinationString, &v18);
  v9 = v18;
  v10 = NamedMetadata;
  if ( NamedMetadata )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0xA00) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_ZD(
        *((_QWORD *)pWppControl + 2),
        75,
        (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
        (_DWORD)a3 + 16,
        NamedMetadata);
    }
    goto LABEL_7;
  }
  result = UuidCreate(&Uuid);
  if ( result )
    return result;
  v13 = (char *)operator new(0xE0u);
  v6 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 0xE0u);
    *((_DWORD *)v6 + 6) = 1;
    *((_QWORD *)v6 + 1) = v6 + 80;
    *((_QWORD *)v6 + 2) = v6;
    *((_DWORD *)v6 + 14) = *((_DWORD *)this + 13);
    *(UUID *)(v6 + 152) = Uuid;
    *(_OWORD *)(v6 + 120) = *(_OWORD *)((char *)v9 + 120);
    *(_OWORD *)(v6 + 136) = *(_OWORD *)((char *)v9 + 136);
    v14 = *((_QWORD *)v9 + 13);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)(v14 + 2 * v15) );
      v16 = v15 + 1;
      v17 = (unsigned __int16 *)operator new(saturated_mul(v16, 2u));
      *((_QWORD *)v6 + 13) = v17;
      if ( !v17 )
      {
        v10 = 8;
        goto LABEL_7;
      }
      StringCchCopyW(v17, v16, *((const unsigned __int16 **)v9 + 13));
    }
    RtlInitUnicodeStringEx((PUNICODE_STRING)v6 + 5, *((PCWSTR *)v6 + 13));
    v10 = anonymous_namespace_::DfspCloneNameInformation_0(v6, a3);
    if ( !v10 )
    {
      v10 = anonymous_namespace_::DfspCloneTargetInformation(v6, v9);
      if ( !v10 )
      {
        v10 = 0;
        *a4 = (struct _DFS_DOMAINV2_METADATA *)v6;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v10 = 8;
  }
LABEL_7:
  DfsDomainV2FreeMetadata((struct _DFS_DOMAINV2_METADATA *)v6);
LABEL_8:
  if ( v9 )
  {
    if ( *((_QWORD *)v9 + 13) )
      SHashReleaseReference(*((_QWORD *)this + 2), v9);
    else
      DomainV2MetadataCache::ReleaseRootMetadataReference(v11, v9);
  }
  return v10;
}

```

## disassembly

```asm
0x14003f5fc  push    rbx
0x14003f5fe  push    rbp
0x14003f5ff  push    rsi
0x14003f600  push    rdi
0x14003f601  push    r12
0x14003f603  push    r13
0x14003f605  push    r14
0x14003f607  push    r15
0x14003f609  sub     rsp, 68h
0x14003f60d  mov     rax, cs:__security_cookie
0x14003f614  xor     rax, rsp
0x14003f617  mov     [rsp+0A8h+var_50], rax
0x14003f61c  mov     r13, rcx
0x14003f61f  xorps   xmm0, xmm0
0x14003f622  xorps   xmm1, xmm1
0x14003f625  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x14003f62a  xor     ebp, ebp
0x14003f62c  mov     r12, r9
0x14003f62f  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x14003f634  mov     [rsp+0A8h+var_78], rbp
0x14003f639  mov     edi, ebp
0x14003f63b  movups  xmmword ptr [rsp+0A8h+Uuid.Data1], xmm1
0x14003f640  mov     r15, r8
0x14003f643  call    cs:__imp_RtlInitUnicodeStringEx
0x14003f64a  nop     dword ptr [rax+rax+00h]
0x14003f64f  lea     r8, [rsp+0A8h+var_78]; struct _DFS_DOMAINV2_METADATA **
0x14003f654  mov     rcx, r13; this
0x14003f657  lea     rdx, [rsp+0A8h+DestinationString]; struct _UNICODE_STRING *
0x14003f65c  call    ?GetNamedMetadata@DomainV2MetadataCache@@QEAAKPEAU_UNICODE_STRING@@PEAPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::GetNamedMetadata(_UNICODE_STRING *,_DFS_DOMAINV2_METADATA * *)
0x14003f661  mov     rsi, [rsp+0A8h+var_78]
0x14003f666  mov     ebx, eax
0x14003f668  test    eax, eax
0x14003f66a  jz      short loc_14003F6DF
0x14003f66c  lea     rax, WPP_GLOBAL_Control
0x14003f673  cmp     cs:WPP_GLOBAL_Control, rax
0x14003f67a  jz      short loc_14003F6B7
0x14003f67c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003f683  test    rcx, rcx
0x14003f686  jz      short loc_14003F6B7
0x14003f688  mov     eax, 200h
0x14003f68d  bts     eax, 0Bh
0x14003f691  test    [rcx+1Ch], eax
0x14003f694  jz      short loc_14003F6B7
0x14003f696  cmp     byte ptr [rcx+19h], 1
0x14003f69a  jb      short loc_14003F6B7
0x14003f69c  mov     rcx, [rcx+10h]
0x14003f6a0  lea     r9, [r15+10h]
0x14003f6a4  lea     edx, [rbp+4Bh]
0x14003f6a7  mov     [rsp+0A8h+var_88], ebx
0x14003f6ab  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003f6b2  call    WPP_SF_ZD
0x14003f6b7  mov     rcx, rdi; Block
0x14003f6ba  call    ?DfsDomainV2FreeMetadata@@YAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DfsDomainV2FreeMetadata(_DFS_DOMAINV2_METADATA *)
0x14003f6bf  test    rsi, rsi
0x14003f6c2  jz      loc_14003F804
0x14003f6c8  mov     rdx, rsi; struct _DFS_DOMAINV2_METADATA *
0x14003f6cb  cmp     [rsi+68h], rbp
0x14003f6cf  jnz     loc_14003F7FB
0x14003f6d5  call    ?ReleaseRootMetadataReference@DomainV2MetadataCache@@AEAAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::ReleaseRootMetadataReference(_DFS_DOMAINV2_METADATA *)
0x14003f6da  jmp     loc_14003F804
0x14003f6df  lea     rcx, [rsp+0A8h+Uuid]; Uuid
0x14003f6e4  call    cs:__imp_UuidCreate
0x14003f6eb  nop     dword ptr [rax+rax+00h]
0x14003f6f0  test    eax, eax
0x14003f6f2  jnz     loc_14003F806
0x14003f6f8  mov     ebx, 0E0h
0x14003f6fd  mov     ecx, ebx; Size
0x14003f6ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003f704  mov     rdi, rax
0x14003f707  test    rax, rax
0x14003f70a  jnz     short loc_14003F711
0x14003f70c  lea     ebx, [rax+8]
0x14003f70f  jmp     short loc_14003F6B7
0x14003f711  mov     r8, rbx; Size
0x14003f714  xor     edx, edx; Val
0x14003f716  mov     rcx, rdi; void *
0x14003f719  call    memset_0
0x14003f71e  mov     dword ptr [rdi+18h], 1
0x14003f725  lea     rbp, [rdi+50h]
0x14003f729  mov     [rdi+8], rbp
0x14003f72d  xor     ecx, ecx
0x14003f72f  mov     [rdi+10h], rdi
0x14003f733  mov     eax, [r13+34h]
0x14003f737  mov     [rdi+38h], eax
0x14003f73a  movups  xmm0, xmmword ptr [rsp+0A8h+Uuid.Data1]
0x14003f73f  movdqu  xmmword ptr [rdi+98h], xmm0
0x14003f747  movups  xmm1, xmmword ptr [rsi+78h]
0x14003f74b  movdqu  xmmword ptr [rdi+78h], xmm1
0x14003f750  movups  xmm0, xmmword ptr [rsi+88h]
0x14003f757  movdqu  xmmword ptr [rdi+88h], xmm0
0x14003f75f  mov     rax, [rsi+68h]
0x14003f763  test    rax, rax
0x14003f766  jz      short loc_14003F7B1
0x14003f768  or      r8, 0FFFFFFFFFFFFFFFFh
0x14003f76c  mov     rbx, r8
0x14003f76f  inc     rbx
0x14003f772  cmp     [rax+rbx*2], cx
0x14003f776  jnz     short loc_14003F76F
0x14003f778  inc     rbx
0x14003f77b  mov     eax, 2
0x14003f780  mul     rbx
0x14003f783  cmovo   rax, r8
0x14003f787  mov     rcx, rax; Size
0x14003f78a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003f78f  mov     [rdi+68h], rax
0x14003f793  test    rax, rax
0x14003f796  jnz     short loc_14003F7A2
0x14003f798  lea     ebx, [rax+8]
0x14003f79b  xor     ebp, ebp
0x14003f79d  jmp     loc_14003F6B7
0x14003f7a2  mov     r8, [rsi+68h]; unsigned __int16 *
0x14003f7a6  mov     rdx, rbx; unsigned __int64
0x14003f7a9  mov     rcx, rax; unsigned __int16 *
0x14003f7ac  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003f7b1  mov     rdx, [rdi+68h]; SourceString
0x14003f7b5  mov     rcx, rbp; DestinationString
0x14003f7b8  call    cs:__imp_RtlInitUnicodeStringEx
0x14003f7bf  nop     dword ptr [rax+rax+00h]
0x14003f7c4  mov     rdx, r15
0x14003f7c7  mov     rcx, rdi
0x14003f7ca  call    _anonymous_namespace___DfspCloneNameInformation_0
0x14003f7cf  xor     ebp, ebp
0x14003f7d1  mov     ebx, eax
0x14003f7d3  test    eax, eax
0x14003f7d5  jnz     loc_14003F6B7
0x14003f7db  mov     rdx, rsi
0x14003f7de  mov     rcx, rdi
0x14003f7e1  call    _anonymous_namespace___DfspCloneTargetInformation
0x14003f7e6  mov     ebx, eax
0x14003f7e8  test    eax, eax
0x14003f7ea  jnz     loc_14003F6B7
0x14003f7f0  mov     ebx, ebp
0x14003f7f2  mov     [r12], rdi
0x14003f7f6  jmp     loc_14003F6BF
0x14003f7fb  mov     rcx, [r13+10h]
0x14003f7ff  call    SHashReleaseReference
0x14003f804  mov     eax, ebx
0x14003f806  mov     rcx, [rsp+0A8h+var_50]
0x14003f80b  xor     rcx, rsp; StackCookie
0x14003f80e  call    __security_check_cookie
0x14003f813  add     rsp, 68h
0x14003f817  pop     r15
0x14003f819  pop     r14
0x14003f81b  pop     r13
0x14003f81d  pop     r12
0x14003f81f  pop     rdi
0x14003f820  pop     rsi
0x14003f821  pop     rbp
0x14003f822  pop     rbx
0x14003f823  retn
```
