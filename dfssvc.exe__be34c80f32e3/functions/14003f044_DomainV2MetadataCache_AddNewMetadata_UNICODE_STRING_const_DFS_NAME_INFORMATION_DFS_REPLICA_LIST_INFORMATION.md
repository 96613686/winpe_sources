# DomainV2MetadataCache::AddNewMetadata(_UNICODE_STRING const *,_DFS_NAME_INFORMATION_ *,_DFS_REPLICA_LIST_INFORMATION_ *)

- ea: `0x14003f044`
- end: `0x14003f33d`
- name: `?AddNewMetadata@DomainV2MetadataCache@@QEAAKPEBU_UNICODE_STRING@@PEAU_DFS_NAME_INFORMATION_@@PEAU_DFS_REPLICA_LIST_INFORMATION_@@@Z`
- size: `761`
- prototype: `unsigned int __fastcall(DomainV2MetadataCache *__hidden this, const struct _UNICODE_STRING *, struct _DFS_NAME_INFORMATION_ *, struct _DFS_REPLICA_LIST_INFORMATION_ *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x140045400`

## callees

- `0x1400011d0`
- `0x14000aed8`
- `0x14000fd24`
- `0x1400177fc`
- `0x14003f044`
- `0x1400401ac`
- `0x14004079c`
- `0x140040a1c`
- `0x140042a38`
- `0x140042c2c`
- `0x140042cf4`
- `0x140043690`
- `0x14005bf90`
- `0x14005ce3a`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x14003f1cc`
- `ntdll!RtlInitUnicodeStringEx` at `0x14003f1cc`
- `RPCRT4!UuidCreate` at `0x14003f0ca`
- `RPCRT4!UuidCreate` at `0x14003f0ca`

## pseudocode

```c
RPC_STATUS __fastcall DomainV2MetadataCache::AddNewMetadata(
        DomainV2MetadataCache *this,
        const struct _UNICODE_STRING *a2,
        struct _DFS_NAME_INFORMATION_ *a3,
        struct _DFS_REPLICA_LIST_INFORMATION_ *a4)
{
  int v4; // r13d
  RPC_STATUS result; // eax
  char *v10; // rax
  DomainV2MetadataCache *v11; // rcx
  char *v12; // rbx
  unsigned int v13; // edi
  DomainV2MetadataCache *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // r14
  unsigned __int16 *v18; // rax
  unsigned int *v19; // r10
  UUID Uuid; // [rsp+30h] [rbp-68h] BYREF

  Uuid = 0;
  v4 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_ZZ(
      *((_QWORD *)pWppControl + 2),
      32,
      (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
      (_DWORD)a2,
      (__int64)a3 + 16);
  }
  result = UuidCreate(&Uuid);
  if ( !result )
  {
    v10 = (char *)operator new(0xE0u);
    v12 = v10;
    if ( !v10 )
    {
      v13 = 8;
      goto LABEL_29;
    }
    memset_0(v10, 0, 0xE0u);
    *((_DWORD *)v12 + 6) = 1;
    *((_QWORD *)v12 + 1) = v12 + 80;
    *((_QWORD *)v12 + 2) = v12;
    *((_DWORD *)v12 + 14) = *((_DWORD *)this + 13);
    if ( a2 && a2->Length )
    {
      *(_OWORD *)(v12 + 136) = *((_OWORD *)a3 + 3);
      v15 = *((_QWORD *)this + 3);
      if ( v15 )
        _InterlockedIncrement((volatile signed __int32 *)(v15 + 24));
      v16 = *((_QWORD *)this + 3);
      *(_OWORD *)(v12 + 120) = *(_OWORD *)(v16 + 120);
      DomainV2MetadataCache::ReleaseRootMetadataReference(v14, (struct _DFS_DOMAINV2_METADATA *)v16);
    }
    else
    {
      *(_OWORD *)(v12 + 120) = *((_OWORD *)a3 + 3);
      if ( !a2 )
      {
LABEL_19:
        RtlInitUnicodeStringEx((PUNICODE_STRING)v12 + 5, *((PCWSTR *)v12 + 13));
        v13 = anonymous_namespace_::DfspCloneNameInformation_0(v12, a3);
        if ( !v13 )
        {
          v13 = anonymous_namespace_::DfspCloneTargetInformation_0(v12, a4);
          if ( !v13 )
          {
            *(UUID *)(v12 + 152) = Uuid;
            v13 = DomainV2MetadataCache::SetNamedMetadata(this, (struct _DFS_DOMAINV2_METADATA *)v12);
            if ( v13 )
            {
              v19 = pWppControl;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
              {
LABEL_35:
                if ( v4 )
                {
                  if ( *((_QWORD *)v12 + 13) )
                    SHashReleaseReference(*((_QWORD *)this + 2), v12);
                  else
                    DomainV2MetadataCache::ReleaseRootMetadataReference(v11, (struct _DFS_DOMAINV2_METADATA *)v12);
                }
                else if ( v12 )
                {
                  DfsDomainV2FreeMetadata((struct _DFS_DOMAINV2_METADATA *)v12);
                }
                return v13;
              }
              if ( !pWppControl || (pWppControl[7] & 0xA00) == 0 || !*((_BYTE *)pWppControl + 25) )
              {
LABEL_30:
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                {
                  if ( v19 )
                  {
                    v11 = (DomainV2MetadataCache *)(v13 != 0 ? 11 : 31);
                    if ( (((1 << (v13 != 0 ? 11 : 31)) | 0x200) & v19[7]) != 0 && *((_BYTE *)v19 + 25) >= 3u )
                      WPP_SF_ZD(
                        *((_QWORD *)v19 + 2),
                        34,
                        (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
                        (_DWORD)a3 + 16,
                        v13);
                  }
                }
                goto LABEL_35;
              }
              WPP_SF_ZD(
                *((_QWORD *)pWppControl + 2),
                33,
                (unsigned int)WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids,
                (_DWORD)a3 + 16,
                v13);
            }
            else
            {
              v4 = 1;
              v13 = DomainV2MetadataCache::WriteMetadataToAd(this, (struct _DFS_DOMAINV2_METADATA *)v12, 1);
              if ( v13 )
                DomainV2MetadataCache::RemoveNamedMetadata(this, (struct _UNICODE_STRING *)v12 + 5);
            }
          }
        }
LABEL_29:
        v19 = pWppControl;
        goto LABEL_30;
      }
    }
    if ( a2->Length )
    {
      v17 = ((unsigned __int64)a2->Length >> 1) + 1;
      v18 = (unsigned __int16 *)operator new(saturated_mul(v17, 2u));
      *((_QWORD *)v12 + 13) = v18;
      if ( !v18 )
      {
        v13 = 8;
        goto LABEL_29;
      }
      StringCchPrintfW(v18, v17, L"%wZ", a2);
    }
    goto LABEL_19;
  }
  return result;
}

```

## disassembly

```asm
0x14003f044  push    rbx
0x14003f046  push    rbp
0x14003f047  push    rsi
0x14003f048  push    rdi
0x14003f049  push    r12
0x14003f04b  push    r13
0x14003f04d  push    r14
0x14003f04f  push    r15
0x14003f051  sub     rsp, 58h
0x14003f055  mov     rax, cs:__security_cookie
0x14003f05c  xor     rax, rsp
0x14003f05f  mov     [rsp+98h+var_58], rax
0x14003f064  xorps   xmm0, xmm0
0x14003f067  xor     r14d, r14d
0x14003f06a  movups  xmmword ptr [rsp+98h+Uuid.Data1], xmm0
0x14003f06f  mov     r13d, r14d
0x14003f072  mov     r12, r9
0x14003f075  mov     rbp, r8
0x14003f078  mov     rdi, rdx
0x14003f07b  mov     rsi, rcx
0x14003f07e  lea     rax, WPP_GLOBAL_Control
0x14003f085  cmp     cs:WPP_GLOBAL_Control, rax
0x14003f08c  jz      short loc_14003F0C5
0x14003f08e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003f095  test    rcx, rcx
0x14003f098  jz      short loc_14003F0C5
0x14003f09a  lea     edx, [r14+20h]
0x14003f09e  test    [rcx+1Ch], dl
0x14003f0a1  jz      short loc_14003F0C5
0x14003f0a3  cmp     byte ptr [rcx+19h], 2
0x14003f0a7  jb      short loc_14003F0C5
0x14003f0a9  mov     rcx, [rcx+10h]
0x14003f0ad  lea     rax, [r8+10h]
0x14003f0b1  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003f0b8  mov     [rsp+98h+var_78], rax
0x14003f0bd  mov     r9, rdi
0x14003f0c0  call    WPP_SF_ZZ
0x14003f0c5  lea     rcx, [rsp+98h+Uuid]; Uuid
0x14003f0ca  call    cs:__imp_UuidCreate
0x14003f0d1  nop     dword ptr [rax+rax+00h]
0x14003f0d6  test    eax, eax
0x14003f0d8  jnz     loc_14003F31E
0x14003f0de  mov     ecx, 0E0h; Size
0x14003f0e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003f0e8  mov     rbx, rax
0x14003f0eb  mov     r15d, 200h
0x14003f0f1  test    rax, rax
0x14003f0f4  jnz     short loc_14003F0FE
0x14003f0f6  lea     edi, [rax+8]
0x14003f0f9  jmp     loc_14003F299
0x14003f0fe  xor     edx, edx; Val
0x14003f100  mov     r8d, 0E0h; Size
0x14003f106  mov     rcx, rbx; void *
0x14003f109  call    memset_0
0x14003f10e  mov     dword ptr [rbx+18h], 1
0x14003f115  lea     rax, [rbx+50h]
0x14003f119  mov     [rbx+8], rax
0x14003f11d  mov     [rbx+10h], rbx
0x14003f121  mov     eax, [rsi+34h]
0x14003f124  mov     [rbx+38h], eax
0x14003f127  test    rdi, rdi
0x14003f12a  jz      short loc_14003F15F
0x14003f12c  cmp     [rdi], r14w
0x14003f130  jz      short loc_14003F15F
0x14003f132  movups  xmm0, xmmword ptr [rbp+30h]
0x14003f136  movdqu  xmmword ptr [rbx+88h], xmm0
0x14003f13e  mov     rax, [rsi+18h]
0x14003f142  test    rax, rax
0x14003f145  jz      short loc_14003F14B
0x14003f147  lock inc dword ptr [rax+18h]
0x14003f14b  mov     rdx, [rsi+18h]; struct _DFS_DOMAINV2_METADATA *
0x14003f14f  movups  xmm0, xmmword ptr [rdx+78h]
0x14003f153  movdqu  xmmword ptr [rbx+78h], xmm0
0x14003f158  call    ?ReleaseRootMetadataReference@DomainV2MetadataCache@@AEAAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::ReleaseRootMetadataReference(_DFS_DOMAINV2_METADATA *)
0x14003f15d  jmp     short loc_14003F16D
0x14003f15f  movups  xmm0, xmmword ptr [rbp+30h]
0x14003f163  movdqu  xmmword ptr [rbx+78h], xmm0
0x14003f168  test    rdi, rdi
0x14003f16b  jz      short loc_14003F1C4
0x14003f16d  cmp     [rdi], r14w
0x14003f171  jz      short loc_14003F1C4
0x14003f173  movzx   r14d, word ptr [rdi]
0x14003f177  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14003f17e  shr     r14, 1
0x14003f181  mov     eax, 2
0x14003f186  inc     r14
0x14003f189  mul     r14
0x14003f18c  cmovo   rax, rcx
0x14003f190  mov     rcx, rax; Size
0x14003f193  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003f198  mov     [rbx+68h], rax
0x14003f19c  test    rax, rax
0x14003f19f  jnz     short loc_14003F1AC
0x14003f1a1  lea     edi, [rax+8]
0x14003f1a4  xor     r14d, r14d
0x14003f1a7  jmp     loc_14003F299
0x14003f1ac  mov     r9, rdi
0x14003f1af  lea     r8, aWz_0; "%wZ"
0x14003f1b6  mov     rdx, r14; unsigned __int64
0x14003f1b9  mov     rcx, rax; unsigned __int16 *
0x14003f1bc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003f1c1  xor     r14d, r14d
0x14003f1c4  mov     rdx, [rbx+68h]; SourceString
0x14003f1c8  lea     rcx, [rbx+50h]; DestinationString
0x14003f1cc  call    cs:__imp_RtlInitUnicodeStringEx
0x14003f1d3  nop     dword ptr [rax+rax+00h]
0x14003f1d8  mov     rdx, rbp
0x14003f1db  mov     rcx, rbx
0x14003f1de  call    _anonymous_namespace___DfspCloneNameInformation_0
0x14003f1e3  mov     edi, eax
0x14003f1e5  test    eax, eax
0x14003f1e7  jnz     loc_14003F299
0x14003f1ed  mov     rdx, r12
0x14003f1f0  mov     rcx, rbx
0x14003f1f3  call    _anonymous_namespace___DfspCloneTargetInformation_0
0x14003f1f8  mov     edi, eax
0x14003f1fa  test    eax, eax
0x14003f1fc  jnz     loc_14003F299
0x14003f202  movups  xmm0, xmmword ptr [rsp+98h+Uuid.Data1]
0x14003f207  mov     rdx, rbx; struct _DFS_DOMAINV2_METADATA *
0x14003f20a  mov     rcx, rsi; this
0x14003f20d  movdqu  xmmword ptr [rbx+98h], xmm0
0x14003f215  call    ?SetNamedMetadata@DomainV2MetadataCache@@QEAAKPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::SetNamedMetadata(_DFS_DOMAINV2_METADATA *)
0x14003f21a  mov     edi, eax
0x14003f21c  test    eax, eax
0x14003f21e  jz      short loc_14003F273
0x14003f220  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003f227  lea     r12, WPP_GLOBAL_Control
0x14003f22e  cmp     cs:WPP_GLOBAL_Control, r12
0x14003f235  jz      loc_14003F2EF
0x14003f23b  test    r10, r10
0x14003f23e  jz      short loc_14003F2A7
0x14003f240  mov     eax, r15d
0x14003f243  bts     eax, 0Bh
0x14003f247  test    [r10+1Ch], eax
0x14003f24b  jz      short loc_14003F2A7
0x14003f24d  cmp     byte ptr [r10+19h], 1
0x14003f252  jb      short loc_14003F2A7
0x14003f254  mov     rcx, [r10+10h]
0x14003f258  lea     r9, [rbp+10h]
0x14003f25c  mov     edx, 21h ; '!'
0x14003f261  mov     dword ptr [rsp+98h+var_78], edi
0x14003f265  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003f26c  call    WPP_SF_ZD
0x14003f271  jmp     short loc_14003F2A0
0x14003f273  mov     r13d, 1
0x14003f279  mov     rdx, rbx; struct _DFS_DOMAINV2_METADATA *
0x14003f27c  mov     r8d, r13d; int
0x14003f27f  mov     rcx, rsi; this
0x14003f282  call    ?WriteMetadataToAd@DomainV2MetadataCache@@AEAAKPEAU_DFS_DOMAINV2_METADATA@@H@Z; DomainV2MetadataCache::WriteMetadataToAd(_DFS_DOMAINV2_METADATA *,int)
0x14003f287  mov     edi, eax
0x14003f289  test    eax, eax
0x14003f28b  jz      short loc_14003F299
0x14003f28d  lea     rdx, [rbx+50h]; struct _UNICODE_STRING *
0x14003f291  mov     rcx, rsi; this
0x14003f294  call    ?RemoveNamedMetadata@DomainV2MetadataCache@@QEAAKPEAU_UNICODE_STRING@@@Z; DomainV2MetadataCache::RemoveNamedMetadata(_UNICODE_STRING *)
0x14003f299  lea     r12, WPP_GLOBAL_Control
0x14003f2a0  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003f2a7  cmp     cs:WPP_GLOBAL_Control, r12
0x14003f2ae  jz      short loc_14003F2EF
0x14003f2b0  test    r10, r10
0x14003f2b3  jz      short loc_14003F2EF
0x14003f2b5  mov     eax, edi
0x14003f2b7  neg     eax
0x14003f2b9  sbb     ecx, ecx
0x14003f2bb  and     ecx, 0FFFFFFECh
0x14003f2be  add     ecx, 1Fh
0x14003f2c1  bts     r15d, ecx
0x14003f2c5  test    [r10+1Ch], r15d
0x14003f2c9  jz      short loc_14003F2EF
0x14003f2cb  cmp     byte ptr [r10+19h], 3
0x14003f2d0  jb      short loc_14003F2EF
0x14003f2d2  mov     rcx, [r10+10h]
0x14003f2d6  lea     r9, [rbp+10h]
0x14003f2da  mov     edx, 22h ; '"'
0x14003f2df  mov     dword ptr [rsp+98h+var_78], edi
0x14003f2e3  lea     r8, WPP_d3d314d2d7fe3a58703e700d5a946855_Traceguids
0x14003f2ea  call    WPP_SF_ZD
0x14003f2ef  test    r13d, r13d
0x14003f2f2  jz      short loc_14003F30F
0x14003f2f4  mov     rdx, rbx; struct _DFS_DOMAINV2_METADATA *
0x14003f2f7  cmp     [rbx+68h], r14
0x14003f2fb  jnz     short loc_14003F304
0x14003f2fd  call    ?ReleaseRootMetadataReference@DomainV2MetadataCache@@AEAAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::ReleaseRootMetadataReference(_DFS_DOMAINV2_METADATA *)
0x14003f302  jmp     short loc_14003F31C
0x14003f304  mov     rcx, [rsi+10h]
0x14003f308  call    SHashReleaseReference
0x14003f30d  jmp     short loc_14003F31C
0x14003f30f  test    rbx, rbx
0x14003f312  jz      short loc_14003F31C
0x14003f314  mov     rcx, rbx; Block
0x14003f317  call    ?DfsDomainV2FreeMetadata@@YAXPEAU_DFS_DOMAINV2_METADATA@@@Z; DfsDomainV2FreeMetadata(_DFS_DOMAINV2_METADATA *)
0x14003f31c  mov     eax, edi
0x14003f31e  mov     rcx, [rsp+98h+var_58]
0x14003f323  xor     rcx, rsp; StackCookie
0x14003f326  call    __security_check_cookie
0x14003f32b  add     rsp, 58h
0x14003f32f  pop     r15
0x14003f331  pop     r14
0x14003f333  pop     r13
0x14003f335  pop     r12
0x14003f337  pop     rdi
0x14003f338  pop     rsi
0x14003f339  pop     rbp
0x14003f33a  pop     rbx
0x14003f33b  retn
```
