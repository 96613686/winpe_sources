# DomainV2MetadataCache::CreateMetadataFromTargetInformation(ushort const *,_DFS_REPLICA_LIST_INFORMATION_ *,_DFS_DOMAINV2_METADATA * *)

- ea: `0x14003f82c`
- end: `0x14003fa39`
- name: `?CreateMetadataFromTargetInformation@DomainV2MetadataCache@@AEAAKPEBGPEAU_DFS_REPLICA_LIST_INFORMATION_@@PEAPEAU_DFS_DOMAINV2_METADATA@@@Z`
- size: `525`
- prototype: `unsigned int __fastcall(DomainV2MetadataCache *__hidden this, const unsigned __int16 *, struct _DFS_REPLICA_LIST_INFORMATION_ *, struct _DFS_DOMAINV2_METADATA **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x14004046c`

## callees

- `0x1400011d0`
- `0x140005b90`
- `0x14001e548`
- `0x14003f82c`
- `0x1400401ac`
- `0x1400405c0`
- `0x140040a1c`
- `0x1400425b8`
- `0x140042a38`
- `0x14005bf90`
- `0x14005ce3a`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x14003f87a`
- `ntdll!RtlInitUnicodeStringEx` at `0x14003f9cb`
- `ntdll!RtlInitUnicodeStringEx` at `0x14003f87a`
- `ntdll!RtlInitUnicodeStringEx` at `0x14003f9cb`
- `RPCRT4!UuidCreate` at `0x14003f91b`
- `RPCRT4!UuidCreate` at `0x14003f91b`

## pseudocode

```c
RPC_STATUS __fastcall DomainV2MetadataCache::CreateMetadataFromTargetInformation(
        DomainV2MetadataCache *this,
        const unsigned __int16 *a2,
        struct _DFS_REPLICA_LIST_INFORMATION_ *a3,
        struct _DFS_DOMAINV2_METADATA **a4)
{
  char *v5; // rdi
  unsigned int NamedMetadata; // eax
  struct _DFS_DOMAINV2_METADATA *v9; // rsi
  int v10; // ebx
  DomainV2MetadataCache *v11; // rcx
  RPC_STATUS result; // eax
  char *v13; // rax
  __int64 v14; // rbx
  unsigned __int64 v15; // rbx
  unsigned __int16 *v16; // rax
  struct _DFS_DOMAINV2_METADATA *v17; // [rsp+30h] [rbp-88h] BYREF
  struct _DFS_REPLICA_LIST_INFORMATION_ *v18; // [rsp+38h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-78h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-68h] BYREF

  v18 = a3;
  DestinationString = 0;
  v17 = 0;
  v5 = 0;
  Uuid = 0;
  RtlInitUnicodeStringEx(&DestinationString, a2);
  NamedMetadata = DomainV2MetadataCache::GetNamedMetadata(this, &DestinationString, &v17);
  v9 = v17;
  v10 = NamedMetadata;
  if ( NamedMetadata )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0xA00) != 0
      && *((_BYTE *)pWppControl + 25) )
    {
      WPP_SF_SD(
        *((_QWORD *)pWppControl + 2),
        76,
        (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
        (_DWORD)a2,
        NamedMetadata);
    }
    goto LABEL_7;
  }
  result = UuidCreate(&Uuid);
  if ( result )
    return result;
  v13 = (char *)operator new(0xE0u);
  v5 = v13;
  if ( !v13 )
    goto LABEL_13;
  memset_0(v13, 0, 0xE0u);
  *((_DWORD *)v5 + 6) = 1;
  *((_QWORD *)v5 + 1) = v5 + 80;
  *((_QWORD *)v5 + 2) = v5;
  *((_DWORD *)v5 + 14) = *((_DWORD *)this + 13);
  *(UUID *)(v5 + 152) = Uuid;
  if ( a2 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v15 = v14 + 1;
    v16 = (unsigned __int16 *)operator new(saturated_mul(v15, 2u));
    *((_QWORD *)v5 + 13) = v16;
    if ( !v16 )
    {
LABEL_13:
      v10 = 8;
      goto LABEL_7;
    }
    StringCchCopyW(v16, v15, a2);
  }
  RtlInitUnicodeStringEx((PUNICODE_STRING)v5 + 5, *((PCWSTR *)v5 + 13));
  v10 = anonymous_namespace_::DfspCloneNameInformation(v5, v9);
  if ( !v10 )
  {
    v10 = anonymous_namespace_::DfspCloneTargetInformation_0(v5, v18);
    if ( !v10 )
    {
      v10 = 0;
      *a4 = (struct _DFS_DOMAINV2_METADATA *)v5;
      goto LABEL_8;
    }
  }
LABEL_7:
  DfsDomainV2FreeMetadata((struct _DFS_DOMAINV2_METADATA *)v5);
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
0x14003f82c  push    rbx
0x14003f82e  push    rbp
0x14003f82f  push    rsi
0x14003f830  push    rdi
0x14003f831  push    r12
0x14003f833  push    r13
0x14003f835  push    r14
0x14003f837  push    r15
0x14003f839  sub     rsp, 78h
0x14003f83d  mov     rax, cs:__security_cookie
0x14003f844  xor     rax, rsp
0x14003f847  mov     [rsp+0B8h+var_58], rax
0x14003f84c  mov     r13, rcx
0x14003f84f  mov     [rsp+0B8h+var_80], r8
0x14003f854  xorps   xmm0, xmm0
0x14003f857  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14003f85c  xorps   xmm1, xmm1
0x14003f85f  xor     r14d, r14d
0x14003f862  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x14003f867  mov     [rsp+0B8h+var_88], r14
0x14003f86c  mov     edi, r14d
0x14003f86f  movups  xmmword ptr [rsp+0B8h+Uuid.Data1], xmm1
0x14003f874  mov     r12, r9
0x14003f877  mov     rbp, rdx
0x14003f87a  call    cs:__imp_RtlInitUnicodeStringEx
0x14003f881  nop     dword ptr [rax+rax+00h]
0x14003f886  lea     r8, [rsp+0B8h+var_88]; struct _DFS_DOMAINV2_METADATA **
0x14003f88b  mov     rcx, r13; this
0x14003f88e  lea     rdx, [rsp+0B8h+DestinationString]; struct _UNICODE_STRING *
0x14003f893  call    ?GetNamedMetadata@DomainV2MetadataCache@@QEAAKPEAU_UNICODE_STRING@@PEAPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::GetNamedMetadata(_UNICODE_STRING *,_DFS_DOMAINV2_METADATA * *)
0x14003f898  mov     rsi, [rsp+0B8h+var_88]
0x14003f89d  mov     ebx, eax
0x14003f89f  test    eax, eax
0x14003f8a1  jz      short loc_14003F916
0x14003f8a3  lea     rax, WPP_GLOBAL_Control
0x14003f8aa  cmp     cs:WPP_GLOBAL_Control, rax
0x14003f8b1  jz      short loc_14003F8EE
0x14003f8b3  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003f8ba  test    rcx, rcx
0x14003f8bd  jz      short loc_14003F8EE
0x14003f8bf  mov     eax, 200h
0x14003f8c4  bts     eax, 0Bh
0x14003f8c8  test    [rcx+1Ch], eax
0x14003f8cb  jz      short loc_14003F8EE
0x14003f8cd  cmp     byte ptr [rcx+19h], 1
0x14003f8d1  jb      short loc_14003F8EE
0x14003f8d3  mov     rcx, [rcx+10h]
0x14003f8d7  lea     edx, [r14+4Ch]
0x14003f8db  mov     r9, rbp
0x14003f8de  mov     [rsp+0B8h+var_98], ebx
0x14003f8e2  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003f8e9  call    WPP_SF_SD
0x14003f8ee  mov     rcx, rdi; Block
0x14003f8f1  call    ?DfsDomainV2FreeMetadata@@YAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DfsDomainV2FreeMetadata(_DFS_DOMAINV2_METADATA *)
0x14003f8f6  test    rsi, rsi
0x14003f8f9  jz      loc_14003FA18
0x14003f8ff  mov     rdx, rsi; struct _DFS_DOMAINV2_METADATA *
0x14003f902  cmp     [rsi+68h], r14
0x14003f906  jnz     loc_14003FA0F
0x14003f90c  call    ?ReleaseRootMetadataReference@DomainV2MetadataCache@@AEAAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::ReleaseRootMetadataReference(_DFS_DOMAINV2_METADATA *)
0x14003f911  jmp     loc_14003FA18
0x14003f916  lea     rcx, [rsp+0B8h+Uuid]; Uuid
0x14003f91b  call    cs:__imp_UuidCreate
0x14003f922  nop     dword ptr [rax+rax+00h]
0x14003f927  test    eax, eax
0x14003f929  jnz     loc_14003FA1A
0x14003f92f  mov     ebx, 0E0h
0x14003f934  mov     ecx, ebx; Size
0x14003f936  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003f93b  mov     rdi, rax
0x14003f93e  test    rax, rax
0x14003f941  jnz     short loc_14003F94A
0x14003f943  mov     ebx, 8
0x14003f948  jmp     short loc_14003F8EE
0x14003f94a  mov     r8, rbx; Size
0x14003f94d  xor     edx, edx; Val
0x14003f94f  mov     rcx, rdi; void *
0x14003f952  call    memset_0
0x14003f957  mov     dword ptr [rdi+18h], 1
0x14003f95e  lea     r15, [rdi+50h]
0x14003f962  mov     [rdi+8], r15
0x14003f966  mov     [rdi+10h], rdi
0x14003f96a  mov     eax, [r13+34h]
0x14003f96e  mov     [rdi+38h], eax
0x14003f971  xor     eax, eax
0x14003f973  movups  xmm0, xmmword ptr [rsp+0B8h+Uuid.Data1]
0x14003f978  movdqu  xmmword ptr [rdi+98h], xmm0
0x14003f980  test    rbp, rbp
0x14003f983  jz      short loc_14003F9C4
0x14003f985  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14003f989  mov     rbx, rcx
0x14003f98c  inc     rbx
0x14003f98f  cmp     [rbp+rbx*2+0], ax
0x14003f994  jnz     short loc_14003F98C
0x14003f996  inc     rbx
0x14003f999  mov     eax, 2
0x14003f99e  mul     rbx
0x14003f9a1  cmovo   rax, rcx
0x14003f9a5  mov     rcx, rax; Size
0x14003f9a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003f9ad  mov     [rdi+68h], rax
0x14003f9b1  test    rax, rax
0x14003f9b4  jz      short loc_14003F943
0x14003f9b6  mov     r8, rbp; unsigned __int16 *
0x14003f9b9  mov     rdx, rbx; unsigned __int64
0x14003f9bc  mov     rcx, rax; unsigned __int16 *
0x14003f9bf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003f9c4  mov     rdx, [rdi+68h]; SourceString
0x14003f9c8  mov     rcx, r15; DestinationString
0x14003f9cb  call    cs:__imp_RtlInitUnicodeStringEx
0x14003f9d2  nop     dword ptr [rax+rax+00h]
0x14003f9d7  mov     rdx, rsi
0x14003f9da  mov     rcx, rdi
0x14003f9dd  call    _anonymous_namespace___DfspCloneNameInformation
0x14003f9e2  mov     ebx, eax
0x14003f9e4  test    eax, eax
0x14003f9e6  jnz     loc_14003F8EE
0x14003f9ec  mov     rdx, [rsp+0B8h+var_80]
0x14003f9f1  mov     rcx, rdi
0x14003f9f4  call    _anonymous_namespace___DfspCloneTargetInformation_0
0x14003f9f9  mov     ebx, eax
0x14003f9fb  test    eax, eax
0x14003f9fd  jnz     loc_14003F8EE
0x14003fa03  mov     ebx, r14d
0x14003fa06  mov     [r12], rdi
0x14003fa0a  jmp     loc_14003F8F6
0x14003fa0f  mov     rcx, [r13+10h]
0x14003fa13  call    SHashReleaseReference
0x14003fa18  mov     eax, ebx
0x14003fa1a  mov     rcx, [rsp+0B8h+var_58]
0x14003fa1f  xor     rcx, rsp; StackCookie
0x14003fa22  call    __security_check_cookie
0x14003fa27  add     rsp, 78h
0x14003fa2b  pop     r15
0x14003fa2d  pop     r14
0x14003fa2f  pop     r13
0x14003fa31  pop     r12
0x14003fa33  pop     rdi
0x14003fa34  pop     rsi
0x14003fa35  pop     rbp
0x14003fa36  pop     rbx
0x14003fa37  retn
```
