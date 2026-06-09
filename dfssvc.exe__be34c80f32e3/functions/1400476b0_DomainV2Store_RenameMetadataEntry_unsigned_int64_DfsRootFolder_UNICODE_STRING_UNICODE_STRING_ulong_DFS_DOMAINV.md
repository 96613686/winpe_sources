# DomainV2Store::RenameMetadataEntry(unsigned __int64,DfsRootFolder *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,_DFS_DOMAINV2_METADATA *,_DFS_DOMAINV2_METADATA * *,_DFS_DOMAINV2_METADATA * *,uchar *)

- ea: `0x1400476b0`
- end: `0x140047d93`
- name: `?RenameMetadataEntry@DomainV2Store@@QEAAK_KPEAVDfsRootFolder@@PEAU_UNICODE_STRING@@2KPEAU_DFS_DOMAINV2_METADATA@@PEAPEAU4@4PEAE@Z`
- size: `1763`
- prototype: `unsigned int(DomainV2Store *__hidden this, unsigned __int64, struct DfsRootFolder *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned int, struct _DFS_DOMAINV2_METADATA *, struct _DFS_DOMAINV2_METADATA **, struct _DFS_DOMAINV2_METADATA **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140046d00`

## callees

- `0x140005a94`
- `0x140005ad8`
- `0x14000abc4`
- `0x14000f958`
- `0x14000fca8`
- `0x14000fd24`
- `0x1400316bc`
- `0x14003f5fc`
- `0x1400401ac`
- `0x1400425b8`
- `0x140042a38`
- `0x1400476b0`
- `0x1400583f4`
- `0x14005864c`
- `0x140058708`
- `0x14005bf90`
- `0x14005e010`

## import_xrefs

- `msvcrt!free` at `0x140047c88`
- `msvcrt!free` at `0x140047cbe`
- `msvcrt!free` at `0x14005d890`
- `msvcrt!free` at `0x14005d8c1`
- `msvcrt!free` at `0x140047c88`
- `msvcrt!free` at `0x140047cbe`
- `msvcrt!free` at `0x14005d890`
- `msvcrt!free` at `0x14005d8c1`
- `ntdll!RtlInitUnicodeStringEx` at `0x140047c9f`
- `ntdll!RtlInitUnicodeStringEx` at `0x140047cd5`
- `ntdll!RtlInitUnicodeStringEx` at `0x14005d8a6`
- `ntdll!RtlInitUnicodeStringEx` at `0x14005d8d7`
- `ntdll!RtlInitUnicodeStringEx` at `0x140047c9f`
- `ntdll!RtlInitUnicodeStringEx` at `0x140047cd5`
- `ntdll!RtlInitUnicodeStringEx` at `0x14005d8a6`
- `ntdll!RtlInitUnicodeStringEx` at `0x14005d8d7`

## pseudocode

```c
__int64 __fastcall DomainV2Store::RenameMetadataEntry(
        DomainV2Store *this,
        DomainV2MetadataCache *a2,
        struct DfsRootFolder *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5,
        char a6,
        struct _DFS_DOMAINV2_METADATA *a7,
        struct _DFS_DOMAINV2_METADATA **a8,
        struct _DFS_DOMAINV2_METADATA **a9,
        unsigned __int8 *a10)
{
  DomainV2MetadataCache *v12; // r14
  unsigned __int8 v13; // r12
  char v14; // di
  unsigned int v15; // eax
  unsigned int NamedMetadata; // ebx
  __int64 v17; // r9
  __int64 v18; // r8
  char v19; // al
  unsigned int v20; // eax
  unsigned int *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // eax
  unsigned int *v25; // rcx
  __int64 v26; // rdx
  struct _UNICODE_STRING *v27; // r9
  DfsGeneric *v28; // rsi
  char *v29; // r14
  DomainV2MetadataCache *v30; // rcx
  DomainV2MetadataCache *v31; // rsi
  char v33; // [rsp+41h] [rbp-97h]
  char v34; // [rsp+42h] [rbp-96h]
  struct _DFS_NAME_INFORMATION_ *v35; // [rsp+48h] [rbp-90h] BYREF
  unsigned __int8 v36[8]; // [rsp+50h] [rbp-88h] BYREF
  struct _DFS_DOMAINV2_METADATA *v37; // [rsp+58h] [rbp-80h] BYREF
  DfsGeneric *v38; // [rsp+60h] [rbp-78h] BYREF
  struct _DFS_DOMAINV2_METADATA *Block; // [rsp+68h] [rbp-70h] BYREF
  __int128 v40; // [rsp+70h] [rbp-68h] BYREF
  struct _UNICODE_STRING v41; // [rsp+80h] [rbp-58h] BYREF
  __int128 v42; // [rsp+90h] [rbp-48h] BYREF
  UNICODE_STRING Source; // [rsp+A0h] [rbp-38h] BYREF

  v12 = a2;
  v37 = 0;
  Block = 0;
  v35 = 0;
  Source = 0;
  v42 = 0;
  v40 = 0;
  v41 = 0;
  v38 = 0;
  v36[0] = 0;
  v13 = 0;
  v14 = 0;
  v33 = 0;
  v34 = 0;
  v15 = (*(__int64 (__fastcall **)(DomainV2Store *, DomainV2MetadataCache *, _QWORD, struct _DFS_NAME_INFORMATION_ **))(*(_QWORD *)this + 96LL))(
          this,
          a2,
          *((_QWORD *)a7 + 13),
          &v35);
  NamedMetadata = v15;
  v17 = 0;
  if ( v15 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !pWppControl
      || (pWppControl[7] & 0x820) == 0
      || !*((_BYTE *)pWppControl + 25) )
    {
      goto LABEL_65;
    }
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 36, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, v15);
    goto LABEL_64;
  }
  DfsGetPathComponents((char *)v35 + 16, &Source, &v42, &v40);
  v17 = 0;
  if ( !(_WORD)v40
    || !*((_QWORD *)&v40 + 1)
    || !**((_WORD **)&v40 + 1)
    || (v19 = DfsPathPrefixUnicodeString(a4, &v40, v18), v17 = 0, !v19) )
  {
    NamedMetadata = 0;
    v13 = 0;
    *a10 = 0;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !pWppControl
      || (pWppControl[7] & 0x20) == 0
      || *((_BYTE *)pWppControl + 25) < 3u )
    {
      goto LABEL_65;
    }
    WPP_SF_Z(*((_QWORD *)pWppControl + 2), 37, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, &v40);
    goto LABEL_64;
  }
  v20 = DfsSubstitutePrefix(&Source, (__int64)a4, a5, (PUNICODE_STRING)v35 + 1);
  NamedMetadata = v20;
  v17 = 0;
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v21 = pWppControl;
      if ( pWppControl )
      {
        if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) )
        {
          v22 = 38;
LABEL_17:
          WPP_SF_D(*((_QWORD *)v21 + 2), v22, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, v20);
LABEL_18:
          v13 = 0;
LABEL_64:
          v17 = 0;
          goto LABEL_65;
        }
      }
    }
    goto LABEL_19;
  }
  v34 = 1;
  DfsGetPathComponents((char *)v35 + 16, 0, 0, &v41);
  if ( !(unsigned __int8)DfsPathPrefixUnicodeString(a4, &v41, v23) )
  {
    v24 = DfsRootFolder::ValidateLinkName(a3, &v41, v36, 1u, &v38, 0);
    NamedMetadata = v24;
    v17 = 0;
    if ( v24 || (v14 = 1, (a6 & 1) == 0) )
      v14 = 0;
    if ( v24 != 1168 )
    {
      if ( !v14 )
      {
        if ( v24 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && pWppControl
            && (pWppControl[7] & 0x820) != 0
            && *((_BYTE *)pWppControl + 25) >= 3u )
          {
            WPP_SF_ZD(
              *((_QWORD *)pWppControl + 2),
              40,
              (unsigned int)WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
              (unsigned int)&v41,
              v24);
            goto LABEL_18;
          }
        }
        else
        {
          NamedMetadata = 80;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v25 = pWppControl;
            if ( pWppControl )
            {
              if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) >= 3u )
              {
                v26 = 39;
                v27 = &v41;
LABEL_32:
                WPP_SF_Z(*((_QWORD *)v25 + 2), v26, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, v27);
                goto LABEL_18;
              }
            }
          }
        }
        goto LABEL_19;
      }
      goto LABEL_39;
    }
  }
  if ( v14 )
  {
LABEL_39:
    v28 = v38;
    v29 = (char *)v38 + 64;
    NamedMetadata = DomainV2MetadataCache::GetNamedMetadata(a2, (struct _UNICODE_STRING *)v38 + 4, &v37);
    DfsGeneric::ReleaseReference(v28);
    v17 = 0;
    v38 = 0;
    if ( NamedMetadata )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x820) != 0
        && *((_BYTE *)pWppControl + 25) )
      {
        WPP_SF_DZ(
          *((_QWORD *)pWppControl + 2),
          41,
          (unsigned int)WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
          NamedMetadata,
          (__int64)v29);
        goto LABEL_18;
      }
      goto LABEL_19;
    }
    v12 = a2;
  }
  v20 = DfsSubstitutePrefix(&Source, (__int64)a4, a5, (PUNICODE_STRING)v35 + 2);
  NamedMetadata = v20;
  v17 = 0;
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v21 = pWppControl;
      if ( pWppControl )
      {
        if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) )
        {
          v22 = 42;
          goto LABEL_17;
        }
      }
    }
    goto LABEL_19;
  }
  v33 = 1;
  NamedMetadata = DomainV2MetadataCache::CreateMetadataFromNameInformation(
                    v12,
                    *((const unsigned __int16 **)a7 + 13),
                    v35,
                    &Block);
  v17 = 0;
  if ( !NamedMetadata )
  {
    v13 = 1;
    *a10 = 1;
    *a8 = Block;
    *a9 = v37;
    goto LABEL_65;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    v25 = pWppControl;
    if ( pWppControl )
    {
      if ( (pWppControl[7] & 0x820) != 0 && *((_BYTE *)pWppControl + 25) )
      {
        v26 = 43;
        v27 = a4;
        goto LABEL_32;
      }
    }
  }
LABEL_19:
  v13 = 0;
LABEL_65:
  if ( v13 )
    goto LABEL_71;
  v30 = Block;
  if ( Block )
  {
    DfsDomainV2FreeMetadata(Block);
    v17 = 0;
  }
  if ( !v37 )
    goto LABEL_71;
  if ( !*((_QWORD *)v37 + 13) )
  {
    DomainV2MetadataCache::ReleaseRootMetadataReference(v30, v37);
    v17 = 0;
LABEL_71:
    v31 = a2;
    goto LABEL_72;
  }
  v31 = a2;
  SHashReleaseReference(*((_QWORD *)a2 + 2), v37);
  v17 = 0;
LABEL_72:
  if ( v33 )
  {
    free(*((void **)v35 + 5));
    RtlInitUnicodeStringEx((PUNICODE_STRING)v35 + 2, 0);
    v17 = 0;
  }
  if ( v34 )
  {
    free(*((void **)v35 + 3));
    RtlInitUnicodeStringEx((PUNICODE_STRING)v35 + 2, 0);
  }
  if ( v35 )
    (*(void (__fastcall **)(DomainV2Store *, DomainV2MetadataCache *, struct _DFS_NAME_INFORMATION_ *, __int64))(*(_QWORD *)this + 104LL))(
      this,
      v31,
      v35,
      v17);
  if ( v38 )
    DfsGeneric::ReleaseReference(v38);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_dD(*((_QWORD *)pWppControl + 2), 44, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, NamedMetadata, v13);
  }
  return NamedMetadata;
}

```

## disassembly

```asm
0x1400476b0  mov     r11, rsp
0x1400476b3  mov     [r11+18h], rbx
0x1400476b7  mov     [r11+20h], rsi
0x1400476bb  mov     [r11+10h], rdx
0x1400476bf  mov     [r11+8], rcx
0x1400476c3  push    rdi
0x1400476c4  push    r12
0x1400476c6  push    r13
0x1400476c8  push    r14
0x1400476ca  push    r15
0x1400476cc  sub     rsp, 0B0h
0x1400476d3  mov     r15, r9
0x1400476d6  mov     rsi, r8
0x1400476d9  mov     r14, rdx
0x1400476dc  xor     eax, eax
0x1400476de  mov     [r11-80h], rax
0x1400476e2  mov     [r11-70h], rax
0x1400476e6  mov     [rsp+0D8h+var_90], rax
0x1400476eb  xorps   xmm0, xmm0
0x1400476ee  movups  xmmword ptr [r11-38h], xmm0
0x1400476f3  xorps   xmm1, xmm1
0x1400476f6  movups  xmmword ptr [r11-48h], xmm1
0x1400476fb  movups  [rsp+0D8h+var_68], xmm0
0x140047700  movups  xmmword ptr [r11-58h], xmm1
0x140047705  mov     [r11-78h], rax
0x140047709  mov     [rsp+0D8h+var_88], al
0x14004770d  mov     r12b, al
0x140047710  mov     [rsp+0D8h+var_98], al
0x140047714  mov     dil, al
0x140047717  mov     [rsp+0D8h+var_97], al
0x14004771b  mov     [rsp+0D8h+var_96], al
0x14004771f  mov     rax, [rcx]
0x140047722  mov     r13, [rsp+0D8h+arg_30]
0x14004772a  lea     r9, [rsp+0D8h+var_90]
0x14004772f  mov     r8, [r13+68h]
0x140047733  mov     rax, [rax+60h]
0x140047737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004773c  mov     ebx, eax
0x14004773e  mov     [rsp+0D8h+var_94], eax
0x140047742  xor     r9d, r9d
0x140047745  test    eax, eax
0x140047747  jz      short loc_1400477A0
0x140047749  lea     rdi, WPP_GLOBAL_Control
0x140047750  cmp     cs:WPP_GLOBAL_Control, rdi
0x140047757  jz      loc_140047C3D
0x14004775d  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140047764  test    rcx, rcx
0x140047767  jz      loc_140047C3D
0x14004776d  test    dword ptr [rcx+1Ch], 820h
0x140047774  jz      loc_140047C3D
0x14004777a  cmp     byte ptr [rcx+19h], 1
0x14004777e  jb      loc_140047C3D
0x140047784  lea     edx, [r9+24h]
0x140047788  mov     r9d, eax
0x14004778b  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x140047792  mov     rcx, [rcx+10h]
0x140047796  call    WPP_SF_D
0x14004779b  jmp     loc_140047C3A
0x1400477a0  mov     rcx, [rsp+0D8h+var_90]
0x1400477a5  add     rcx, 10h
0x1400477a9  lea     r9, [rsp+0D8h+var_68]
0x1400477ae  lea     r8, [rsp+0D8h+var_48]
0x1400477b6  lea     rdx, [rsp+0D8h+Source]
0x1400477be  call    DfsGetPathComponents
0x1400477c3  xor     r9d, r9d
0x1400477c6  cmp     word ptr [rsp+0D8h+var_68], r9w
0x1400477cc  jz      loc_140047BDE
0x1400477d2  mov     rax, qword ptr [rsp+0D8h+var_68+8]
0x1400477d7  test    rax, rax
0x1400477da  jz      loc_140047BDE
0x1400477e0  cmp     [rax], r9w
0x1400477e4  jz      loc_140047BDE
0x1400477ea  lea     rdx, [rsp+0D8h+var_68]
0x1400477ef  mov     rcx, r15
0x1400477f2  call    DfsPathPrefixUnicodeString
0x1400477f7  xor     r9d, r9d
0x1400477fa  test    al, al
0x1400477fc  jz      loc_140047BDE
0x140047802  mov     rax, [rsp+0D8h+var_90]
0x140047807  add     rax, 10h
0x14004780b  mov     [rsp+0D8h+Destination], rax; Destination
0x140047810  mov     r12, [rsp+0D8h+arg_20]
0x140047818  mov     [rsp+0D8h+var_B0], r12; PCUNICODE_STRING
0x14004781d  mov     [rsp+0D8h+var_B8], r15; __int64
0x140047822  lea     r9, [rsp+0D8h+var_68]
0x140047827  lea     r8, [rsp+0D8h+var_48]
0x14004782f  mov     edx, 2
0x140047834  lea     rcx, [rsp+0D8h+Source]; Source
0x14004783c  call    DfsSubstitutePrefix
0x140047841  mov     ebx, eax
0x140047843  mov     [rsp+0D8h+var_94], eax
0x140047847  xor     r9d, r9d
0x14004784a  test    eax, eax
0x14004784c  jz      short loc_1400478A4
0x14004784e  lea     rdi, WPP_GLOBAL_Control
0x140047855  cmp     cs:WPP_GLOBAL_Control, rdi
0x14004785c  jz      short loc_14004789A
0x14004785e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140047865  test    rcx, rcx
0x140047868  jz      short loc_14004789A
0x14004786a  test    dword ptr [rcx+1Ch], 820h
0x140047871  jz      short loc_14004789A
0x140047873  cmp     byte ptr [rcx+19h], 1
0x140047877  jb      short loc_14004789A
0x140047879  lea     edx, [r9+26h]
0x14004787d  mov     r9d, eax
0x140047880  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x140047887  mov     rcx, [rcx+10h]
0x14004788b  call    WPP_SF_D
0x140047890  mov     r12b, [rsp+0D8h+var_98]
0x140047895  jmp     loc_140047C3A
0x14004789a  mov     r12b, [rsp+0D8h+var_98]
0x14004789f  jmp     loc_140047C3D
0x1400478a4  mov     [rsp+0D8h+var_96], 1
0x1400478a9  mov     rcx, [rsp+0D8h+var_90]
0x1400478ae  add     rcx, 10h
0x1400478b2  lea     r9, [rsp+0D8h+var_58]
0x1400478ba  xor     r8d, r8d
0x1400478bd  xor     edx, edx
0x1400478bf  call    DfsGetPathComponents
0x1400478c4  lea     rdx, [rsp+0D8h+var_58]
0x1400478cc  mov     rcx, r15
0x1400478cf  call    DfsPathPrefixUnicodeString
0x1400478d4  xor     r9d, r9d
0x1400478d7  test    al, al
0x1400478d9  jnz     loc_1400479FE
0x1400478df  mov     byte ptr [rsp+0D8h+var_B0], r9b; unsigned __int8
0x1400478e4  lea     rax, [rsp+0D8h+var_78]
0x1400478e9  mov     [rsp+0D8h+var_B8], rax; struct DfsFolder **
0x1400478ee  mov     r9b, 1; unsigned __int8
0x1400478f1  lea     r8, [rsp+0D8h+var_88]; unsigned __int8 *
0x1400478f6  lea     rdx, [rsp+0D8h+var_58]; struct _UNICODE_STRING *
0x1400478fe  mov     rcx, rsi; this
0x140047901  call    ?ValidateLinkName@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@PEAEEPEAPEAVDfsFolder@@E@Z; DfsRootFolder::ValidateLinkName(_UNICODE_STRING *,uchar *,uchar,DfsFolder * *,uchar)
0x140047906  mov     ebx, eax
0x140047908  mov     [rsp+0D8h+var_94], eax
0x14004790c  xor     r9d, r9d
0x14004790f  test    eax, eax
0x140047911  jnz     short loc_140047920
0x140047913  test    [rsp+0D8h+arg_28], 1
0x14004791b  mov     dil, 1
0x14004791e  jnz     short loc_140047923
0x140047920  mov     dil, r9b
0x140047923  cmp     eax, 490h
0x140047928  jz      loc_140047A06
0x14004792e  test    dil, dil
0x140047931  jnz     loc_140047A0F
0x140047937  test    eax, eax
0x140047939  jnz     short loc_14004799D
0x14004793b  lea     ebx, [rax+50h]
0x14004793e  mov     [rsp+0D8h+var_94], ebx
0x140047942  lea     rdi, WPP_GLOBAL_Control
0x140047949  cmp     cs:WPP_GLOBAL_Control, rdi
0x140047950  jz      loc_14004789A
0x140047956  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14004795d  test    rcx, rcx
0x140047960  jz      loc_14004789A
0x140047966  test    dword ptr [rcx+1Ch], 820h
0x14004796d  jz      loc_14004789A
0x140047973  cmp     byte ptr [rcx+19h], 3
0x140047977  jb      loc_14004789A
0x14004797d  lea     edx, [rax+27h]
0x140047980  lea     r9, [rsp+0D8h+var_58]
0x140047988  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x14004798f  mov     rcx, [rcx+10h]
0x140047993  call    WPP_SF_Z
0x140047998  jmp     loc_140047890
0x14004799d  lea     rdi, WPP_GLOBAL_Control
0x1400479a4  cmp     cs:WPP_GLOBAL_Control, rdi
0x1400479ab  jz      loc_14004789A
0x1400479b1  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400479b8  test    rcx, rcx
0x1400479bb  jz      loc_14004789A
0x1400479c1  test    dword ptr [rcx+1Ch], 820h
0x1400479c8  jz      loc_14004789A
0x1400479ce  cmp     byte ptr [rcx+19h], 3
0x1400479d2  jb      loc_14004789A
0x1400479d8  mov     edx, 28h ; '('
0x1400479dd  mov     dword ptr [rsp+0D8h+var_B8], eax
0x1400479e1  lea     r9, [rsp+0D8h+var_58]
0x1400479e9  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x1400479f0  mov     rcx, [rcx+10h]
0x1400479f4  call    WPP_SF_ZD
0x1400479f9  jmp     loc_140047890
0x1400479fe  mov     [rsp+0D8h+var_94], 490h
0x140047a06  test    dil, dil
0x140047a09  jz      loc_140047AAB
0x140047a0f  mov     rsi, [rsp+0D8h+var_78]
0x140047a14  lea     r14, [rsi+40h]
0x140047a18  lea     r8, [rsp+0D8h+var_80]; struct _DFS_DOMAINV2_METADATA **
0x140047a1d  mov     rdx, r14; struct _UNICODE_STRING *
0x140047a20  mov     rcx, [rsp+0D8h+arg_8]; this
0x140047a28  call    ?GetNamedMetadata@DomainV2MetadataCache@@QEAAKPEAU_UNICODE_STRING@@PEAPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::GetNamedMetadata(_UNICODE_STRING *,_DFS_DOMAINV2_METADATA * *)
0x140047a2d  mov     ebx, eax
0x140047a2f  mov     [rsp+0D8h+var_94], eax
0x140047a33  mov     rcx, rsi; this
0x140047a36  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x140047a3b  xor     r9d, r9d
0x140047a3e  mov     [rsp+0D8h+var_78], r9
0x140047a43  test    ebx, ebx
0x140047a45  jz      short loc_140047AA3
0x140047a47  lea     rdi, WPP_GLOBAL_Control
0x140047a4e  cmp     cs:WPP_GLOBAL_Control, rdi
0x140047a55  jz      loc_14004789A
0x140047a5b  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140047a62  test    rcx, rcx
0x140047a65  jz      loc_14004789A
0x140047a6b  test    dword ptr [rcx+1Ch], 820h
0x140047a72  jz      loc_14004789A
0x140047a78  cmp     byte ptr [rcx+19h], 1
0x140047a7c  jb      loc_14004789A
0x140047a82  lea     edx, [r9+29h]
0x140047a86  mov     [rsp+0D8h+var_B8], r14
0x140047a8b  mov     r9d, ebx
0x140047a8e  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x140047a95  mov     rcx, [rcx+10h]
0x140047a99  call    WPP_SF_DZ
0x140047a9e  jmp     loc_140047890
0x140047aa3  mov     r14, [rsp+0D8h+arg_8]
0x140047aab  mov     rax, [rsp+0D8h+var_90]
0x140047ab0  add     rax, 20h ; ' '
0x140047ab4  mov     [rsp+0D8h+Destination], rax; Destination
0x140047ab9  mov     [rsp+0D8h+var_B0], r12; PCUNICODE_STRING
0x140047abe  mov     [rsp+0D8h+var_B8], r15; __int64
0x140047ac3  lea     r9, [rsp+0D8h+var_68]
0x140047ac8  lea     r8, [rsp+0D8h+var_48]
0x140047ad0  mov     edx, 2
0x140047ad5  lea     rcx, [rsp+0D8h+Source]; Source
0x140047add  call    DfsSubstitutePrefix
0x140047ae2  mov     ebx, eax
0x140047ae4  mov     [rsp+0D8h+var_94], eax
0x140047ae8  xor     r9d, r9d
0x140047aeb  test    eax, eax
0x140047aed  jz      short loc_140047B33
0x140047aef  lea     rdi, WPP_GLOBAL_Control
0x140047af6  cmp     cs:WPP_GLOBAL_Control, rdi
0x140047afd  jz      loc_14004789A
0x140047b03  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140047b0a  test    rcx, rcx
0x140047b0d  jz      loc_14004789A
0x140047b13  test    dword ptr [rcx+1Ch], 820h
0x140047b1a  jz      loc_14004789A
0x140047b20  cmp     byte ptr [rcx+19h], 1
0x140047b24  jb      loc_14004789A
0x140047b2a  lea     edx, [r9+2Ah]
0x140047b2e  jmp     loc_14004787D
0x140047b33  mov     [rsp+0D8h+var_97], 1
0x140047b38  lea     r9, [rsp+0D8h+Block]; struct _DFS_DOMAINV2_METADATA **
0x140047b3d  mov     r8, [rsp+0D8h+var_90]; struct _DFS_NAME_INFORMATION_ *
0x140047b42  mov     rdx, [r13+68h]; unsigned __int16 *
0x140047b46  mov     rcx, r14; this
0x140047b49  call    ?CreateMetadataFromNameInformation@DomainV2MetadataCache@@QEAAKPEBGPEAU_DFS_NAME_INFORMATION_@@PEAPEAU_DFS_DOMAINV2_METADATA@@@Z; DomainV2MetadataCache::CreateMetadataFromNameInformation(ushort const *,_DFS_NAME_INFORMATION_ *,_DFS_DOMAINV2_METADATA * *)
0x140047b4e  mov     ebx, eax
0x140047b50  mov     [rsp+0D8h+var_94], eax
0x140047b54  xor     r9d, r9d
0x140047b57  test    eax, eax
0x140047b59  jz      short loc_140047BA2
0x140047b5b  lea     rdi, WPP_GLOBAL_Control
0x140047b62  cmp     cs:WPP_GLOBAL_Control, rdi
0x140047b69  jz      loc_14004789A
0x140047b6f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140047b76  test    rcx, rcx
0x140047b79  jz      loc_14004789A
0x140047b7f  test    dword ptr [rcx+1Ch], 820h
0x140047b86  jz      loc_14004789A
0x140047b8c  cmp     byte ptr [rcx+19h], 1
0x140047b90  jb      loc_14004789A
0x140047b96  lea     edx, [r9+2Bh]
0x140047b9a  mov     r9, r15
0x140047b9d  jmp     loc_140047988
0x140047ba2  mov     r12b, 1
0x140047ba5  mov     [rsp+0D8h+var_98], r12b
0x140047baa  mov     rax, [rsp+0D8h+arg_48]
0x140047bb2  mov     [rax], r12b
0x140047bb5  mov     rcx, [rsp+0D8h+arg_38]
0x140047bbd  mov     rax, [rsp+0D8h+Block]
0x140047bc2  mov     [rcx], rax
0x140047bc5  mov     rcx, [rsp+0D8h+arg_40]
0x140047bcd  mov     rax, [rsp+0D8h+var_80]
0x140047bd2  mov     [rcx], rax
0x140047bd5  lea     rdi, WPP_GLOBAL_Control
0x140047bdc  jmp     short loc_140047C3D
0x140047bde  mov     ebx, r9d
0x140047be1  mov     [rsp+0D8h+var_94], ebx
0x140047be5  mov     r12b, r9b
0x140047be8  mov     [rsp+0D8h+var_98], r9b
0x140047bed  mov     rax, [rsp+0D8h+arg_48]
0x140047bf5  mov     [rax], r9b
0x140047bf8  lea     rdi, WPP_GLOBAL_Control
0x140047bff  cmp     cs:WPP_GLOBAL_Control, rdi
0x140047c06  jz      short loc_140047C3D
0x140047c08  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140047c0f  test    rcx, rcx
0x140047c12  jz      short loc_140047C3D
0x140047c14  test    byte ptr [rcx+1Ch], 20h
0x140047c18  jz      short loc_140047C3D
0x140047c1a  cmp     byte ptr [rcx+19h], 3
0x140047c1e  jb      short loc_140047C3D
0x140047c20  mov     edx, 25h ; '%'
0x140047c25  lea     r9, [rsp+0D8h+var_68]
  ... truncated ...
```
