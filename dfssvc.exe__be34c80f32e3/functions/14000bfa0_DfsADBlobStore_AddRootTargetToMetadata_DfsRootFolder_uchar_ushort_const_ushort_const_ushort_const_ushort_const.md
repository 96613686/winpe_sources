# DfsADBlobStore::AddRootTargetToMetadata(DfsRootFolder *,uchar,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x14000bfa0`
- end: `0x14000c1e1`
- name: `?AddRootTargetToMetadata@DfsADBlobStore@@QEAAKPEAVDfsRootFolder@@EPEBG111@Z`
- size: `577`
- prototype: `unsigned int __usercall@<eax>(DfsADBlobStore *__hidden this@<rcx>, struct DfsRootFolder *@<rdx>, unsigned __int8@<r8b>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x14000c2bc`

## callees

- `0x14000851c`
- `0x14000bfa0`
- `0x14000dc74`
- `0x14000f784`
- `0x14000f808`
- `0x1400364d4`
- `0x14004a414`
- `0x1400586a8`
- `0x140058b04`
- `0x140058db8`
- `0x14005ce3a`
- `0x14005ce70`
- `0x14005e010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000c0b9`
- `ntdll!RtlInitUnicodeString` at `0x14000c0b9`
- `RPCRT4!UuidCreate` at `0x14000c040`
- `RPCRT4!UuidCreate` at `0x14000c040`

## pseudocode

```c
__int64 __fastcall DfsADBlobStore::AddRootTargetToMetadata(
        DfsADBlobStore *this,
        struct DfsRootFolder *a2,
        char a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned __int16 *a7)
{
  unsigned int inited; // ebx
  __int64 v12; // r8
  DfsADBlobCache *v13; // rsi
  unsigned int NamedBlob; // eax
  const unsigned __int16 *AdDomainName; // rax
  DfsStore *v16; // rcx
  DfsStore *v17; // rcx
  DfsADBlobCache *v19; // [rsp+30h] [rbp-D0h] BYREF
  struct _BLOB_DATA *v20; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING v21; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  _BYTE v26[64]; // [rsp+90h] [rbp-70h] BYREF
  UUID Uuid; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v28[68]; // [rsp+E0h] [rbp-20h] BYREF
  int v29; // [rsp+124h] [rbp+24h]

  v25 = 0;
  v24 = 0;
  memset_0(v26, 0, sizeof(v26));
  memset_0(v28, 0, 0x98u);
  v19 = 0;
  v21 = 0;
  v23 = 0;
  Uuid = 0;
  inited = DfsRtlInitUnicodeStringEx(&v23, 0);
  if ( !inited )
  {
    inited = UuidCreate(&Uuid);
    if ( !inited )
    {
      inited = (*(__int64 (__fastcall **)(struct DfsRootFolder *, DfsADBlobCache **))(*(_QWORD *)a2 + 56LL))(a2, &v19);
      if ( !inited )
      {
        if ( a3 )
          goto LABEL_9;
        LOBYTE(v12) = 1;
        inited = (*(__int64 (__fastcall **)(struct DfsRootFolder *, __int64, __int64))(*(_QWORD *)a2 + 32LL))(
                   a2,
                   1,
                   v12);
        if ( inited )
          goto LABEL_11;
        v13 = v19;
        v20 = 0;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, 0);
        NamedBlob = DfsADBlobCache::GetNamedBlob(v13, &DestinationString, &v20);
        inited = NamedBlob;
        if ( !NamedBlob )
        {
          DfsADBlobCache::ReleaseBlobCacheReference(v13, v20);
          inited = DfsStore::AddChildReplica(this, (unsigned __int64)v19, 0, a4, a5);
          goto LABEL_11;
        }
        if ( NamedBlob == 1168 )
        {
LABEL_9:
          AdDomainName = DfsGetAdDomainName();
          inited = DfsCreateUnicodePathString(&v21, 1, AdDomainName, a6);
          if ( !inited )
          {
            DfsStore::StoreInitializeNameInformation(v16, (struct _DFS_NAME_INFORMATION_ *)v28, &v21, &Uuid, a7);
            v29 |= 0x80u;
            DfsStore::StoreInitializeReplicaInformation(
              v17,
              (struct _DFS_REPLICA_LIST_INFORMATION_ *)&v24,
              (struct _DFS_REPLICA_INFORMATION__ *)v26,
              a4,
              a5);
            inited = (*(__int64 (__fastcall **)(DfsADBlobStore *, DfsADBlobCache *, _BYTE *, __int128 *, __int128 *))(*(_QWORD *)this + 24LL))(
                       this,
                       v19,
                       v28,
                       &v24,
                       &v23);
            DfsFreeUnicodeString(&v21);
          }
        }
      }
    }
  }
LABEL_11:
  if ( v19 )
    (*(void (__fastcall **)(struct DfsRootFolder *))(*(_QWORD *)a2 + 64LL))(a2);
  return inited;
}

```

## disassembly

```asm
0x14000bfa0  push    rbp
0x14000bfa2  push    rbx
0x14000bfa3  push    rsi
0x14000bfa4  push    rdi
0x14000bfa5  push    r12
0x14000bfa7  push    r14
0x14000bfa9  push    r15
0x14000bfab  lea     rbp, [rsp-90h]
0x14000bfb3  sub     rsp, 190h
0x14000bfba  mov     rax, cs:__security_cookie
0x14000bfc1  xor     rax, rsp
0x14000bfc4  mov     [rbp+0C0h+var_40], rax
0x14000bfcb  mov     r12, [rbp+0C0h+arg_20]
0x14000bfd2  xor     eax, eax
0x14000bfd4  mov     sil, r8b
0x14000bfd7  mov     [rbp+0C0h+var_140], rax
0x14000bfdb  mov     rdi, rdx
0x14000bfde  mov     r14, rcx
0x14000bfe1  xorps   xmm0, xmm0
0x14000bfe4  lea     rcx, [rbp+0C0h+var_130]; void *
0x14000bfe8  lea     r8d, [rax+40h]; Size
0x14000bfec  xor     edx, edx; Val
0x14000bfee  mov     r15, r9
0x14000bff1  movups  [rsp+1C0h+var_150], xmm0
0x14000bff6  call    memset_0
0x14000bffb  xor     edx, edx; Val
0x14000bffd  lea     rcx, [rbp+0C0h+var_E0]; void *
0x14000c001  mov     r8d, 98h; Size
0x14000c007  call    memset_0
0x14000c00c  and     [rsp+1C0h+var_190], 0
0x14000c012  lea     rcx, [rsp+1C0h+var_160]
0x14000c017  xorps   xmm0, xmm0
0x14000c01a  xorps   xmm1, xmm1
0x14000c01d  xor     edx, edx
0x14000c01f  movups  xmmword ptr [rsp+1C0h+var_180.Length], xmm0
0x14000c024  movups  [rsp+1C0h+var_160], xmm1
0x14000c029  movups  xmmword ptr [rbp+0C0h+Uuid.Data1], xmm0
0x14000c02d  call    DfsRtlInitUnicodeStringEx
0x14000c032  mov     ebx, eax
0x14000c034  test    eax, eax
0x14000c036  jnz     loc_14000C1A4
0x14000c03c  lea     rcx, [rbp+0C0h+Uuid]; Uuid
0x14000c040  call    cs:__imp_UuidCreate
0x14000c047  nop     dword ptr [rax+rax+00h]
0x14000c04c  mov     ebx, eax
0x14000c04e  test    eax, eax
0x14000c050  jnz     loc_14000C1A4
0x14000c056  mov     rax, [rdi]
0x14000c059  lea     rdx, [rsp+1C0h+var_190]
0x14000c05e  mov     rcx, rdi
0x14000c061  mov     rax, [rax+38h]
0x14000c065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c06a  mov     ebx, eax
0x14000c06c  test    eax, eax
0x14000c06e  jnz     loc_14000C1A4
0x14000c074  test    sil, sil
0x14000c077  jnz     loc_14000C114
0x14000c07d  mov     rax, [rdi]
0x14000c080  lea     edx, [rbx+1]
0x14000c083  mov     r9b, 1
0x14000c086  mov     rcx, rdi
0x14000c089  mov     r8b, r9b
0x14000c08c  mov     rax, [rax+20h]
0x14000c090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c095  mov     ebx, eax
0x14000c097  test    eax, eax
0x14000c099  jnz     loc_14000C1A4
0x14000c09f  mov     rsi, [rsp+1C0h+var_190]
0x14000c0a4  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x14000c0a9  and     [rsp+1C0h+var_188], 0
0x14000c0af  xorps   xmm0, xmm0
0x14000c0b2  xor     edx, edx; SourceString
0x14000c0b4  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x14000c0b9  call    cs:__imp_RtlInitUnicodeString
0x14000c0c0  nop     dword ptr [rax+rax+00h]
0x14000c0c5  lea     r8, [rsp+1C0h+var_188]; struct _BLOB_DATA **
0x14000c0ca  mov     rcx, rsi; this
0x14000c0cd  lea     rdx, [rsp+1C0h+DestinationString]; struct _UNICODE_STRING *
0x14000c0d2  call    ?GetNamedBlob@DfsADBlobCache@@QEAAKPEAU_UNICODE_STRING@@PEAPEAU_BLOB_DATA@@@Z; DfsADBlobCache::GetNamedBlob(_UNICODE_STRING *,_BLOB_DATA * *)
0x14000c0d7  mov     ebx, eax
0x14000c0d9  test    eax, eax
0x14000c0db  jnz     short loc_14000C109
0x14000c0dd  mov     rdx, [rsp+1C0h+var_188]; struct _BLOB_DATA *
0x14000c0e2  mov     rcx, rsi; this
0x14000c0e5  call    ?ReleaseBlobCacheReference@DfsADBlobCache@@QEAAXPEAU_BLOB_DATA@@@Z; DfsADBlobCache::ReleaseBlobCacheReference(_BLOB_DATA *)
0x14000c0ea  mov     rdx, [rsp+1C0h+var_190]; unsigned __int64
0x14000c0ef  mov     r9, r15; unsigned __int16 *
0x14000c0f2  xor     r8d, r8d; unsigned __int16 *
0x14000c0f5  mov     [rsp+1C0h+var_1A0], r12; unsigned __int16 *
0x14000c0fa  mov     rcx, r14; this
0x14000c0fd  call    ?AddChildReplica@DfsStore@@QEAAK_KPEBG11@Z; DfsStore::AddChildReplica(unsigned __int64,ushort const *,ushort const *,ushort const *)
0x14000c102  mov     ebx, eax
0x14000c104  jmp     loc_14000C1A4
0x14000c109  cmp     eax, 490h
0x14000c10e  jnz     loc_14000C1A4
0x14000c114  call    ?DfsGetAdDomainName@@YAPEBGXZ; DfsGetAdDomainName(void)
0x14000c119  mov     r9, [rbp+0C0h+arg_28]
0x14000c120  lea     rcx, [rsp+1C0h+var_180]
0x14000c125  mov     r8, rax
0x14000c128  mov     edx, 1
0x14000c12d  call    DfsCreateUnicodePathString
0x14000c132  mov     ebx, eax
0x14000c134  test    eax, eax
0x14000c136  jnz     short loc_14000C1A4
0x14000c138  mov     rax, [rbp+0C0h+arg_30]
0x14000c13f  lea     r9, [rbp+0C0h+Uuid]; struct _GUID *
0x14000c143  lea     r8, [rsp+1C0h+var_180]; struct _UNICODE_STRING *
0x14000c148  mov     [rsp+1C0h+var_1A0], rax; unsigned __int16 *
0x14000c14d  lea     rdx, [rbp+0C0h+var_E0]; struct _DFS_NAME_INFORMATION_ *
0x14000c151  call    ?StoreInitializeNameInformation@DfsStore@@QEAAKPEAU_DFS_NAME_INFORMATION_@@PEAU_UNICODE_STRING@@PEAU_GUID@@PEBG@Z; DfsStore::StoreInitializeNameInformation(_DFS_NAME_INFORMATION_ *,_UNICODE_STRING *,_GUID *,ushort const *)
0x14000c156  bts     [rbp+0C0h+var_9C], 7
0x14000c15b  lea     r8, [rbp+0C0h+var_130]; struct _DFS_REPLICA_INFORMATION__ *
0x14000c15f  mov     r9, r15; unsigned __int16 *
0x14000c162  mov     [rsp+1C0h+var_1A0], r12; unsigned __int16 *
0x14000c167  lea     rdx, [rsp+1C0h+var_150]; struct _DFS_REPLICA_LIST_INFORMATION_ *
0x14000c16c  call    ?StoreInitializeReplicaInformation@DfsStore@@QEAAKPEAU_DFS_REPLICA_LIST_INFORMATION_@@PEAU_DFS_REPLICA_INFORMATION__@@PEBG2@Z; DfsStore::StoreInitializeReplicaInformation(_DFS_REPLICA_LIST_INFORMATION_ *,_DFS_REPLICA_INFORMATION__ *,ushort const *,ushort const *)
0x14000c171  mov     rax, [r14]
0x14000c174  lea     rcx, [rsp+1C0h+var_160]
0x14000c179  mov     rdx, [rsp+1C0h+var_190]
0x14000c17e  lea     r9, [rsp+1C0h+var_150]
0x14000c183  mov     [rsp+1C0h+var_1A0], rcx
0x14000c188  lea     r8, [rbp+0C0h+var_E0]
0x14000c18c  mov     rcx, r14
0x14000c18f  mov     rax, [rax+18h]
0x14000c193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c198  lea     rcx, [rsp+1C0h+var_180]
0x14000c19d  mov     ebx, eax
0x14000c19f  call    DfsFreeUnicodeString
0x14000c1a4  mov     rdx, [rsp+1C0h+var_190]
0x14000c1a9  test    rdx, rdx
0x14000c1ac  jz      short loc_14000C1BD
0x14000c1ae  mov     rax, [rdi]
0x14000c1b1  mov     rcx, rdi
0x14000c1b4  mov     rax, [rax+40h]
0x14000c1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c1bd  mov     eax, ebx
0x14000c1bf  mov     rcx, [rbp+0C0h+var_40]
0x14000c1c6  xor     rcx, rsp; StackCookie
0x14000c1c9  call    __security_check_cookie
0x14000c1ce  add     rsp, 190h
0x14000c1d5  pop     r15
0x14000c1d7  pop     r14
0x14000c1d9  pop     r12
0x14000c1db  pop     rdi
0x14000c1dc  pop     rsi
0x14000c1dd  pop     rbx
0x14000c1de  pop     rbp
0x14000c1df  retn
```
