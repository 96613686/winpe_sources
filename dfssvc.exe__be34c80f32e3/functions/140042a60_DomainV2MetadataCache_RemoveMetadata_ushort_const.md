# DomainV2MetadataCache::RemoveMetadata(ushort const *)

- ea: `0x140042a60`
- end: `0x140042c25`
- name: `?RemoveMetadata@DomainV2MetadataCache@@QEAAKPEBG@Z`
- size: `453`
- prototype: `unsigned int __fastcall(DomainV2MetadataCache *__hidden this, PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140047150`

## callees

- `0x1400011c4`
- `0x140005b90`
- `0x14003fa40`
- `0x1400425b8`
- `0x140042a38`
- `0x140042a60`
- `0x140042c2c`
- `0x140043534`
- `0x14005bf90`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140042ad3`
- `ntdll!RtlInitUnicodeStringEx` at `0x140042ad3`
- `ntdll!RtlNtStatusToDosError` at `0x140042ae5`
- `ntdll!RtlNtStatusToDosError` at `0x140042ae5`
- `RPCRT4!UuidCreate` at `0x140042aa9`
- `RPCRT4!UuidCreate` at `0x140042aa9`

## pseudocode

```c
__int64 __fastcall DomainV2MetadataCache::RemoveMetadata(DomainV2MetadataCache *this, PCWSTR SourceString)
{
  struct _DFS_DOMAINV2_METADATA *v3; // rdi
  unsigned int NamedMetadata; // ebx
  NTSTATUS inited; // eax
  DomainV2MetadataCache *v7; // rcx
  struct _DFS_DOMAINV2_METADATA *v9; // [rsp+30h] [rbp-40h] BYREF
  void *Block; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-20h] BYREF

  v3 = 0;
  Block = 0;
  v9 = 0;
  DestinationString = 0;
  Uuid = 0;
  NamedMetadata = UuidCreate(&Uuid);
  if ( !NamedMetadata )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
    if ( inited )
    {
      NamedMetadata = RtlNtStatusToDosError(inited);
    }
    else
    {
      NamedMetadata = DomainV2MetadataCache::GetNamedMetadata(this, &DestinationString, &v9);
      if ( NamedMetadata )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0xA00) != 0
          && *((_BYTE *)pWppControl + 25) )
        {
          WPP_SF_SD(
            *((_QWORD *)pWppControl + 2),
            35,
            (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
            (_DWORD)SourceString,
            NamedMetadata);
        }
        v3 = v9;
      }
      else
      {
        v3 = v9;
        NamedMetadata = DomainV2MetadataCache::DeleteLinkInAd(this, v9, (WCHAR **)&Block);
        if ( !NamedMetadata )
        {
          DomainV2MetadataCache::RemoveNamedMetadata(this, &DestinationString);
          DomainV2MetadataCache::UpdateSyncOptimisationInfo(this, (const unsigned __int16 *)Block);
        }
      }
    }
  }
  operator delete(Block);
  if ( v3 )
  {
    if ( *((_QWORD *)v3 + 13) )
      SHashReleaseReference(*((_QWORD *)this + 2), v3);
    else
      DomainV2MetadataCache::ReleaseRootMetadataReference(v7, v3);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (NamedMetadata != 0 ? 11 : 31)) | 0x200) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_SD(
      *((_QWORD *)pWppControl + 2),
      36,
      (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
      (_DWORD)SourceString,
      NamedMetadata);
  }
  return NamedMetadata;
}

```

## disassembly

```asm
0x140042a60  mov     [rsp-28h+arg_10], rbx
0x140042a65  mov     [rsp-28h+arg_18], rsi
0x140042a6a  push    rbp
0x140042a6b  push    rdi
0x140042a6c  push    r12
0x140042a6e  push    r14
0x140042a70  push    r15
0x140042a72  mov     rbp, rsp
0x140042a75  sub     rsp, 70h
0x140042a79  mov     rax, cs:__security_cookie
0x140042a80  xor     rax, rsp
0x140042a83  mov     [rbp+var_10], rax
0x140042a87  mov     rsi, rcx
0x140042a8a  xor     edi, edi
0x140042a8c  and     [rbp+Block], rdi
0x140042a90  lea     rcx, [rbp+Uuid]; Uuid
0x140042a94  xorps   xmm0, xmm0
0x140042a97  mov     [rbp+var_40], rdi
0x140042a9b  xorps   xmm1, xmm1
0x140042a9e  mov     r15, rdx
0x140042aa1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140042aa5  movups  xmmword ptr [rbp+Uuid.Data1], xmm1
0x140042aa9  call    cs:__imp_UuidCreate
0x140042ab0  nop     dword ptr [rax+rax+00h]
0x140042ab5  lea     r12, WPP_GLOBAL_Control
0x140042abc  mov     r14d, 200h
0x140042ac2  mov     ebx, eax
0x140042ac4  test    eax, eax
0x140042ac6  jnz     loc_140042B88
0x140042acc  mov     rdx, r15; SourceString
0x140042acf  lea     rcx, [rbp+DestinationString]; DestinationString
0x140042ad3  call    cs:__imp_RtlInitUnicodeStringEx
0x140042ada  nop     dword ptr [rax+rax+00h]
0x140042adf  test    eax, eax
0x140042ae1  jz      short loc_140042AF8
0x140042ae3  mov     ecx, eax; Status
0x140042ae5  call    cs:__imp_RtlNtStatusToDosError
0x140042aec  nop     dword ptr [rax+rax+00h]
0x140042af1  mov     ebx, eax
0x140042af3  jmp     loc_140042B88
0x140042af8  lea     r8, [rbp+var_40]; struct _DFS_DOMAINV2_METADATA **
0x140042afc  mov     rcx, rsi; this
0x140042aff  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x140042b03  call    ?GetNamedMetadata@DomainV2MetadataCache@@QEAAKPEAU_UNICODE_STRING@@PEAPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::GetNamedMetadata(_UNICODE_STRING *,_DFS_DOMAINV2_METADATA * *)
0x140042b08  mov     ebx, eax
0x140042b0a  test    eax, eax
0x140042b0c  jz      short loc_140042B57
0x140042b0e  cmp     cs:WPP_GLOBAL_Control, r12
0x140042b15  jz      short loc_140042B51
0x140042b17  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140042b1e  test    rcx, rcx
0x140042b21  jz      short loc_140042B51
0x140042b23  mov     eax, r14d
0x140042b26  bts     eax, 0Bh
0x140042b2a  test    [rcx+1Ch], eax
0x140042b2d  jz      short loc_140042B51
0x140042b2f  cmp     byte ptr [rcx+19h], 1
0x140042b33  jb      short loc_140042B51
0x140042b35  mov     rcx, [rcx+10h]
0x140042b39  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x140042b40  mov     edx, 23h ; '#'
0x140042b45  mov     [rsp+70h+var_50], ebx
0x140042b49  mov     r9, r15
0x140042b4c  call    WPP_SF_SD
0x140042b51  mov     rdi, [rbp+var_40]
0x140042b55  jmp     short loc_140042B88
0x140042b57  mov     rdi, [rbp+var_40]
0x140042b5b  lea     r8, [rbp+Block]; unsigned __int16 **
0x140042b5f  mov     rdx, rdi; struct _DFS_DOMAINV2_METADATA *
0x140042b62  mov     rcx, rsi; this
0x140042b65  call    ?DeleteLinkInAd@DomainV2MetadataCache@@QEAAKPEAU_DFS_DOMAINV2_METADATA@@PEAPEBG@Z; DomainV2MetadataCache::DeleteLinkInAd(_DFS_DOMAINV2_METADATA *,ushort const * *)
0x140042b6a  mov     ebx, eax
0x140042b6c  test    eax, eax
0x140042b6e  jnz     short loc_140042B88
0x140042b70  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x140042b74  mov     rcx, rsi; this
0x140042b77  call    ?RemoveNamedMetadata@DomainV2MetadataCache@@QEAAKPEAU_UNICODE_STRING@@@Z; DomainV2MetadataCache::RemoveNamedMetadata(_UNICODE_STRING *)
0x140042b7c  mov     rdx, [rbp+Block]; unsigned __int16 *
0x140042b80  mov     rcx, rsi; this
0x140042b83  call    ?UpdateSyncOptimisationInfo@DomainV2MetadataCache@@AEAAXPEBG@Z; DomainV2MetadataCache::UpdateSyncOptimisationInfo(ushort const *)
0x140042b88  mov     rcx, [rbp+Block]; Block
0x140042b8c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140042b91  test    rdi, rdi
0x140042b94  jz      short loc_140042BB0
0x140042b96  cmp     qword ptr [rdi+68h], 0
0x140042b9b  mov     rdx, rdi; struct _DFS_DOMAINV2_METADATA *
0x140042b9e  jnz     short loc_140042BA7
0x140042ba0  call    ?ReleaseRootMetadataReference@DomainV2MetadataCache@@AEAAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::ReleaseRootMetadataReference(_DFS_DOMAINV2_METADATA *)
0x140042ba5  jmp     short loc_140042BB0
0x140042ba7  mov     rcx, [rsi+10h]
0x140042bab  call    SHashReleaseReference
0x140042bb0  cmp     cs:WPP_GLOBAL_Control, r12
0x140042bb7  jz      short loc_140042BFD
0x140042bb9  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140042bc0  test    rcx, rcx
0x140042bc3  jz      short loc_140042BFD
0x140042bc5  mov     eax, ebx
0x140042bc7  neg     eax
0x140042bc9  sbb     edx, edx
0x140042bcb  and     edx, 0FFFFFFECh
0x140042bce  add     edx, 1Fh
0x140042bd1  bts     r14d, edx
0x140042bd5  test    [rcx+1Ch], r14d
0x140042bd9  jz      short loc_140042BFD
0x140042bdb  cmp     byte ptr [rcx+19h], 3
0x140042bdf  jb      short loc_140042BFD
0x140042be1  mov     rcx, [rcx+10h]
0x140042be5  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x140042bec  mov     edx, 24h ; '$'
0x140042bf1  mov     [rsp+70h+var_50], ebx
0x140042bf5  mov     r9, r15
0x140042bf8  call    WPP_SF_SD
0x140042bfd  mov     eax, ebx
0x140042bff  mov     rcx, [rbp+var_10]
0x140042c03  xor     rcx, rsp; StackCookie
0x140042c06  call    __security_check_cookie
0x140042c0b  lea     r11, [rsp+70h+var_s0]
0x140042c10  mov     rbx, [r11+40h]
0x140042c14  mov     rsi, [r11+48h]
0x140042c18  mov     rsp, r11
0x140042c1b  pop     r15
0x140042c1d  pop     r14
0x140042c1f  pop     r12
0x140042c21  pop     rdi
0x140042c22  pop     rbp
0x140042c23  retn
```
