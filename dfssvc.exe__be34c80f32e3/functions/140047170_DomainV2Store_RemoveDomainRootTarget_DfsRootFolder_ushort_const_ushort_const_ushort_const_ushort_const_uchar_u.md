# DomainV2Store::RemoveDomainRootTarget(DfsRootFolder *,ushort const *,ushort const *,ushort const *,ushort const *,uchar,uchar)

- ea: `0x140047170`
- end: `0x14004759e`
- name: `?RemoveDomainRootTarget@DomainV2Store@@UEAAKPEAVDfsRootFolder@@PEBG111EE@Z`
- size: `1070`
- prototype: `unsigned int __fastcall(DomainV2Store *__hidden this, struct DfsRootFolder *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, PCWSTR SourceString, unsigned __int8, char)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1400011c4`
- `0x140005a94`
- `0x140005b28`
- `0x140005c10`
- `0x140005f20`
- `0x14000a354`
- `0x14000e228`
- `0x14000ffbc`
- `0x14002e1b8`
- `0x14003e714`
- `0x140045dec`
- `0x140047170`
- `0x1400475a4`
- `0x140056dd8`
- `0x140057cdc`
- `0x140057f64`
- `0x1400586a8`
- `0x140059044`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400472a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400472a3`

## pseudocode

```c
__int64 __fastcall DomainV2Store::RemoveDomainRootTarget(
        DomainV2Store *this,
        RTL_SRWLOCK *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        PCWSTR SourceString,
        unsigned __int8 a7,
        char a8)
{
  unsigned __int16 *v8; // r12
  unsigned int inited; // ebx
  __int64 v14; // rdx
  int v15; // eax
  unsigned __int8 v16; // r8
  const unsigned __int16 *v17; // rsi
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rdx
  unsigned __int8 v23; // [rsp+30h] [rbp-50h] BYREF
  char v24; // [rsp+31h] [rbp-4Fh]
  unsigned __int8 v25[6]; // [rsp+32h] [rbp-4Eh] BYREF
  unsigned __int16 *v26; // [rsp+38h] [rbp-48h] BYREF
  void *Block; // [rsp+40h] [rbp-40h]
  HKEY v28; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-30h]
  struct _UNICODE_STRING v30; // [rsp+58h] [rbp-28h] BYREF
  struct _UNICODE_STRING v31; // [rsp+68h] [rbp-18h] BYREF

  v23 = 0;
  v31 = 0;
  v8 = 0;
  v26 = 0;
  v30 = 0;
  Block = 0;
  v25[0] = 0;
  v24 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x40) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_SS(
      *((_QWORD *)pWppControl + 2),
      21,
      (unsigned int)WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
      (_DWORD)a5,
      (__int64)SourceString);
  }
  inited = DfsRtlInitUnicodeStringEx(&v31, a3);
  if ( !inited )
  {
    inited = DfsRtlInitUnicodeStringEx(&v30, a5);
    if ( !inited )
    {
      LOBYTE(v14) = 1;
      inited = (*((__int64 (__fastcall **)(RTL_SRWLOCK *, __int64, _QWORD, const unsigned __int16 *))a2->Ptr + 15))(
                 a2,
                 v14,
                 0,
                 a4);
      if ( !inited )
      {
        v24 = 1;
        inited = DomainV2Store::CheckDeleteAccess(this, (struct DfsRootFolder *)a2, a4, &v31, &v30);
        if ( !inited )
        {
          inited = DfsRootFolder::AcquireRootLock((DfsRootFolder *)a2, 1u);
          if ( !inited )
          {
            LODWORD(a2[34].Ptr) |= 0x4000u;
            ++LODWORD(a2[15].Ptr);
            ReleaseSRWLockExclusive(a2 + 14);
            if ( a8 )
              goto LABEL_18;
            inited = DfsGetNamespaceRegistrySubkeyName(a3, SourceString, a7, (const unsigned __int16 **)&v26);
            if ( inited )
            {
              v8 = v26;
              goto LABEL_45;
            }
            v28 = 0;
            v29 = 0;
            v15 = CRegistry::OpenKey(
                    (CRegistry *)&v28,
                    HKEY_LOCAL_MACHINE,
                    L"SOFTWARE\\Microsoft\\Dfs\\Roots\\domainV2",
                    0x20006u);
            v8 = v26;
            if ( v15 )
            {
              inited = 0;
              if ( !CRegistry::DeleteKey(&v28, v26) )
                inited = v29;
            }
            else
            {
              inited = v29;
            }
            CRegistry::~CRegistry((CRegistry *)&v28);
            if ( !inited )
            {
LABEL_18:
              inited = DomainV2Store::RemoveRootTargetFromMetadata(this, (struct DfsRootFolder *)a2, a3, a5, &v23);
              if ( inited == 2 )
              {
                Block = (void *)DfsInvertHostNameToNetbiosOrFqdn(a3, v25);
                v17 = (const unsigned __int16 *)Block;
                if ( !Block )
                {
LABEL_34:
                  if ( !a8 )
                  {
                    v19 = DfsStore::RemoveRootFolder(this, (struct DfsRootFolder *)a2, v16);
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && pWppControl
                      && (((1 << (v19 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
                      && *((_BYTE *)pWppControl + 25) )
                    {
                      WPP_SF_D(*((_QWORD *)pWppControl + 2), 24, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, v19);
                    }
                    v20 = DfsRootFolder::ReleaseRootShareDirectory((DfsRootFolder *)a2);
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && pWppControl
                      && (((1 << (v20 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
                      && *((_BYTE *)pWppControl + 25) >= 3u )
                    {
                      WPP_SF_D(*((_QWORD *)pWppControl + 2), 25, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, v20);
                    }
                  }
                  goto LABEL_45;
                }
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && pWppControl
                  && (pWppControl[7] & 0x20) != 0
                  && *((_BYTE *)pWppControl + 25) >= 3u )
                {
                  WPP_SF_S(
                    *((_QWORD *)pWppControl + 2),
                    inited + 20,
                    WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
                    Block);
                }
                inited = DomainV2Store::RemoveRootTargetFromMetadata(this, (struct DfsRootFolder *)a2, v17, a5, &v23);
              }
              if ( !inited )
              {
                if ( v23 )
                {
                  v18 = DfsDeleteNamespaceEntry(SourceString, a4, 1u);
                  inited = v18;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && pWppControl
                    && (((1 << (v18 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
                    && *((_BYTE *)pWppControl + 25) )
                  {
                    WPP_SF_D(*((_QWORD *)pWppControl + 2), 23, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids, v18);
                  }
                }
              }
              goto LABEL_34;
            }
          }
        }
      }
    }
  }
LABEL_45:
  operator delete(v8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qSD(
      *((_QWORD *)pWppControl + 2),
      26,
      (unsigned int)WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
      (_DWORD)a2,
      (__int64)SourceString,
      inited);
  }
  if ( v24 )
  {
    LOBYTE(v21) = 1;
    (*((void (__fastcall **)(RTL_SRWLOCK *, __int64, _QWORD))a2->Ptr + 16))(a2, v21, inited);
  }
  if ( v25[0] )
    operator delete(Block);
  return inited;
}

```

## disassembly

```asm
0x140047170  mov     [rsp-28h+arg_8], rbx
0x140047175  mov     [rsp-28h+arg_10], rsi
0x14004717a  mov     [rsp-28h+arg_0], rcx
0x14004717f  push    rbp
0x140047180  push    rdi
0x140047181  push    r12
0x140047183  push    r13
0x140047185  push    r15
0x140047187  mov     rbp, rsp
0x14004718a  sub     rsp, 80h
0x140047191  xor     eax, eax
0x140047193  xorps   xmm0, xmm0
0x140047196  xorps   xmm1, xmm1
0x140047199  mov     [rbp+var_50], al
0x14004719c  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x1400471a0  mov     r12d, eax
0x1400471a3  mov     [rbp+var_48], rax
0x1400471a7  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x1400471ab  mov     [rbp+Block], rax
0x1400471af  mov     r13, r9
0x1400471b2  mov     [rbp+var_4E], al
0x1400471b5  mov     rsi, r8
0x1400471b8  mov     [rbp+var_4F], al
0x1400471bb  mov     rdi, rdx
0x1400471be  mov     r15, rcx
0x1400471c1  lea     rcx, WPP_GLOBAL_Control
0x1400471c8  cmp     cs:WPP_GLOBAL_Control, rcx
0x1400471cf  jz      short loc_140047209
0x1400471d1  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400471d8  test    rcx, rcx
0x1400471db  jz      short loc_140047209
0x1400471dd  test    byte ptr [rcx+1Ch], 40h
0x1400471e1  jz      short loc_140047209
0x1400471e3  cmp     byte ptr [rcx+19h], 2
0x1400471e7  jb      short loc_140047209
0x1400471e9  mov     r9, [rbp+arg_20]
0x1400471ed  lea     edx, [rax+15h]
0x1400471f0  mov     rax, [rbp+SourceString]
0x1400471f4  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x1400471fb  mov     rcx, [rcx+10h]
0x1400471ff  mov     [rsp+80h+var_60], rax
0x140047204  call    WPP_SF_SS
0x140047209  mov     rdx, rsi
0x14004720c  lea     rcx, [rbp+var_18]
0x140047210  call    DfsRtlInitUnicodeStringEx
0x140047215  mov     ebx, eax
0x140047217  test    eax, eax
0x140047219  jnz     loc_1400474FE
0x14004721f  mov     rdx, [rbp+arg_20]
0x140047223  lea     rcx, [rbp+var_28]
0x140047227  call    DfsRtlInitUnicodeStringEx
0x14004722c  mov     ebx, eax
0x14004722e  test    eax, eax
0x140047230  jnz     loc_1400474FE
0x140047236  mov     rax, [rdi]
0x140047239  mov     r9, r13
0x14004723c  xor     r8d, r8d
0x14004723f  mov     dl, 1
0x140047241  mov     rcx, rdi
0x140047244  mov     rax, [rax+78h]
0x140047248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004724d  mov     ebx, eax
0x14004724f  test    eax, eax
0x140047251  jnz     loc_1400474FE
0x140047257  lea     rax, [rbp+var_28]
0x14004725b  mov     [rbp+var_4F], 1
0x14004725f  lea     r9, [rbp+var_18]; struct _UNICODE_STRING *
0x140047263  mov     [rsp+80h+var_60], rax; struct _UNICODE_STRING *
0x140047268  mov     r8, r13; unsigned __int16 *
0x14004726b  mov     rdx, rdi; struct DfsRootFolder *
0x14004726e  mov     rcx, r15; this
0x140047271  call    ?CheckDeleteAccess@DomainV2Store@@QEAAKPEAVDfsRootFolder@@PEBGPEAU_UNICODE_STRING@@2@Z; DomainV2Store::CheckDeleteAccess(DfsRootFolder *,ushort const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140047276  mov     ebx, eax
0x140047278  test    eax, eax
0x14004727a  jnz     loc_1400474FE
0x140047280  mov     dl, 1; unsigned __int8
0x140047282  mov     rcx, rdi; this
0x140047285  call    ?AcquireRootLock@DfsRootFolder@@QEAAKE@Z; DfsRootFolder::AcquireRootLock(uchar)
0x14004728a  mov     ebx, eax
0x14004728c  test    eax, eax
0x14004728e  jnz     loc_1400474FE
0x140047294  bts     dword ptr [rdi+110h], 0Eh
0x14004729c  lea     rcx, [rdi+70h]; SRWLock
0x1400472a0  inc     dword ptr [rdi+78h]
0x1400472a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1400472aa  nop     dword ptr [rax+rax+00h]
0x1400472af  mov     r15b, [rbp+arg_38]
0x1400472b3  test    r15b, r15b
0x1400472b6  jnz     short loc_14004732D
0x1400472b8  mov     r8b, [rbp+arg_30]; unsigned __int8
0x1400472bc  lea     r9, [rbp+var_48]; unsigned __int16 **
0x1400472c0  mov     rdx, [rbp+SourceString]; unsigned __int16 *
0x1400472c4  mov     rcx, rsi; unsigned __int16 *
0x1400472c7  call    ?DfsGetNamespaceRegistrySubkeyName@@YAKPEBG0EPEAPEBG@Z; DfsGetNamespaceRegistrySubkeyName(ushort const *,ushort const *,uchar,ushort const * *)
0x1400472cc  mov     ebx, eax
0x1400472ce  test    eax, eax
0x1400472d0  jnz     loc_140047435
0x1400472d6  and     [rbp+var_38], r12
0x1400472da  lea     r8, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Dfs\\Roots\\domain"...
0x1400472e1  and     [rbp+var_30], r12d
0x1400472e5  lea     rcx, [rbp+var_38]; this
0x1400472e9  mov     r9d, 20006h; unsigned int
0x1400472ef  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1400472f6  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x1400472fb  mov     r12, [rbp+var_48]
0x1400472ff  test    eax, eax
0x140047301  jnz     short loc_140047308
0x140047303  mov     ebx, [rbp+var_30]
0x140047306  jmp     short loc_14004731C
0x140047308  mov     rdx, r12; unsigned __int16 *
0x14004730b  lea     rcx, [rbp+var_38]; this
0x14004730f  call    ?DeleteKey@CRegistry@@QEAAHPEBG@Z; CRegistry::DeleteKey(ushort const *)
0x140047314  xor     ebx, ebx
0x140047316  test    eax, eax
0x140047318  cmovz   ebx, [rbp+var_30]
0x14004731c  lea     rcx, [rbp+var_38]; this
0x140047320  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x140047325  test    ebx, ebx
0x140047327  jnz     loc_1400474FE
0x14004732d  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x140047331  lea     rax, [rbp+var_50]
0x140047335  mov     rcx, [rbp+arg_0]; this
0x140047339  mov     r8, rsi; unsigned __int16 *
0x14004733c  mov     rdx, rdi; struct DfsRootFolder *
0x14004733f  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x140047344  call    ?RemoveRootTargetFromMetadata@DomainV2Store@@AEAAKPEAVDfsRootFolder@@PEBG1PEAE@Z; DomainV2Store::RemoveRootTargetFromMetadata(DfsRootFolder *,ushort const *,ushort const *,uchar *)
0x140047349  mov     ebx, eax
0x14004734b  cmp     eax, 2
0x14004734e  jnz     short loc_1400473C8
0x140047350  lea     rdx, [rbp+var_4E]; unsigned __int8 *
0x140047354  mov     rcx, rsi; unsigned __int16 *
0x140047357  call    ?DfsInvertHostNameToNetbiosOrFqdn@@YAPEBGPEBGPEAE@Z; DfsInvertHostNameToNetbiosOrFqdn(ushort const *,uchar *)
0x14004735c  mov     [rbp+Block], rax
0x140047360  mov     rsi, rax
0x140047363  test    rax, rax
0x140047366  jz      loc_14004743E
0x14004736c  lea     rax, WPP_GLOBAL_Control
0x140047373  cmp     cs:WPP_GLOBAL_Control, rax
0x14004737a  jz      short loc_1400473AA
0x14004737c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140047383  test    rcx, rcx
0x140047386  jz      short loc_1400473AA
0x140047388  test    byte ptr [rcx+1Ch], 20h
0x14004738c  jz      short loc_1400473AA
0x14004738e  cmp     byte ptr [rcx+19h], 3
0x140047392  jb      short loc_1400473AA
0x140047394  mov     rcx, [rcx+10h]
0x140047398  lea     edx, [rbx+14h]
0x14004739b  mov     r9, rsi
0x14004739e  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x1400473a5  call    WPP_SF_S
0x1400473aa  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x1400473ae  lea     rax, [rbp+var_50]
0x1400473b2  mov     rcx, [rbp+arg_0]; this
0x1400473b6  mov     r8, rsi; unsigned __int16 *
0x1400473b9  mov     rdx, rdi; struct DfsRootFolder *
0x1400473bc  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x1400473c1  call    ?RemoveRootTargetFromMetadata@DomainV2Store@@AEAAKPEAVDfsRootFolder@@PEBG1PEAE@Z; DomainV2Store::RemoveRootTargetFromMetadata(DfsRootFolder *,ushort const *,ushort const *,uchar *)
0x1400473c6  mov     ebx, eax
0x1400473c8  test    ebx, ebx
0x1400473ca  jnz     short loc_14004743E
0x1400473cc  cmp     [rbp+var_50], bl
0x1400473cf  jz      short loc_14004743E
0x1400473d1  mov     rcx, [rbp+SourceString]; SourceString
0x1400473d5  mov     r8b, 1; unsigned __int8
0x1400473d8  mov     rdx, r13; unsigned __int16 *
0x1400473db  call    ?DfsDeleteNamespaceEntry@@YAKPEBG0E@Z; DfsDeleteNamespaceEntry(ushort const *,ushort const *,uchar)
0x1400473e0  mov     ebx, eax
0x1400473e2  lea     rsi, WPP_GLOBAL_Control
0x1400473e9  cmp     cs:WPP_GLOBAL_Control, rsi
0x1400473f0  jz      short loc_140047445
0x1400473f2  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400473f9  test    rcx, rcx
0x1400473fc  jz      short loc_140047445
0x1400473fe  neg     eax
0x140047400  mov     eax, 20h ; ' '
0x140047405  sbb     edx, edx
0x140047407  and     edx, 0FFFFFFECh
0x14004740a  add     edx, 1Fh
0x14004740d  bts     eax, edx
0x140047410  test    [rcx+1Ch], eax
0x140047413  jz      short loc_140047445
0x140047415  cmp     byte ptr [rcx+19h], 1
0x140047419  jb      short loc_140047445
0x14004741b  mov     rcx, [rcx+10h]
0x14004741f  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x140047426  mov     edx, 17h
0x14004742b  mov     r9d, ebx
0x14004742e  call    WPP_SF_D
0x140047433  jmp     short loc_140047445
0x140047435  mov     r12, [rbp+var_48]
0x140047439  jmp     loc_1400474FE
0x14004743e  lea     rsi, WPP_GLOBAL_Control
0x140047445  test    r15b, r15b
0x140047448  jnz     loc_1400474FE
0x14004744e  mov     rcx, [rbp+arg_0]; this
0x140047452  mov     rdx, rdi; struct DfsRootFolder *
0x140047455  call    ?RemoveRootFolder@DfsStore@@QEAAKPEAVDfsRootFolder@@E@Z; DfsStore::RemoveRootFolder(DfsRootFolder *,uchar)
0x14004745a  mov     r9d, eax
0x14004745d  cmp     cs:WPP_GLOBAL_Control, rsi
0x140047464  jz      short loc_1400474A8
0x140047466  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14004746d  test    r10, r10
0x140047470  jz      short loc_1400474A8
0x140047472  mov     ecx, eax
0x140047474  mov     eax, 20h ; ' '
0x140047479  neg     ecx
0x14004747b  sbb     edx, edx
0x14004747d  and     edx, 0FFFFFFECh
0x140047480  add     edx, 1Fh
0x140047483  bts     eax, edx
0x140047486  test    [r10+1Ch], eax
0x14004748a  jz      short loc_1400474A8
0x14004748c  cmp     byte ptr [r10+19h], 1
0x140047491  jb      short loc_1400474A8
0x140047493  mov     rcx, [r10+10h]
0x140047497  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x14004749e  mov     edx, 18h
0x1400474a3  call    WPP_SF_D
0x1400474a8  mov     rcx, rdi; this
0x1400474ab  call    ?ReleaseRootShareDirectory@DfsRootFolder@@QEAAKXZ; DfsRootFolder::ReleaseRootShareDirectory(void)
0x1400474b0  mov     r9d, eax
0x1400474b3  cmp     cs:WPP_GLOBAL_Control, rsi
0x1400474ba  jz      short loc_1400474FE
0x1400474bc  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400474c3  test    r10, r10
0x1400474c6  jz      short loc_1400474FE
0x1400474c8  mov     ecx, eax
0x1400474ca  mov     eax, 20h ; ' '
0x1400474cf  neg     ecx
0x1400474d1  sbb     edx, edx
0x1400474d3  and     edx, 0FFFFFFECh
0x1400474d6  add     edx, 1Fh
0x1400474d9  bts     eax, edx
0x1400474dc  test    [r10+1Ch], eax
0x1400474e0  jz      short loc_1400474FE
0x1400474e2  cmp     byte ptr [r10+19h], 3
0x1400474e7  jb      short loc_1400474FE
0x1400474e9  mov     rcx, [r10+10h]
0x1400474ed  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x1400474f4  mov     edx, 19h
0x1400474f9  call    WPP_SF_D
0x1400474fe  mov     rcx, r12; Block
0x140047501  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140047506  lea     rax, WPP_GLOBAL_Control
0x14004750d  cmp     cs:WPP_GLOBAL_Control, rax
0x140047514  jz      short loc_140047553
0x140047516  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14004751d  test    rcx, rcx
0x140047520  jz      short loc_140047553
0x140047522  test    byte ptr [rcx+1Ch], 20h
0x140047526  jz      short loc_140047553
0x140047528  cmp     byte ptr [rcx+19h], 3
0x14004752c  jb      short loc_140047553
0x14004752e  mov     rax, [rbp+SourceString]
0x140047532  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x140047539  mov     rcx, [rcx+10h]
0x14004753d  mov     edx, 1Ah
0x140047542  mov     [rsp+80h+var_58], ebx
0x140047546  mov     r9, rdi
0x140047549  mov     [rsp+80h+var_60], rax
0x14004754e  call    WPP_SF_qSD
0x140047553  cmp     [rbp+var_4F], 0
0x140047557  jz      short loc_140047570
0x140047559  mov     rax, [rdi]
0x14004755c  mov     r8d, ebx
0x14004755f  mov     dl, 1
0x140047561  mov     rcx, rdi
0x140047564  mov     rax, [rax+80h]
0x14004756b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047570  cmp     [rbp+var_4E], 0
0x140047574  jz      short loc_14004757F
0x140047576  mov     rcx, [rbp+Block]; Block
0x14004757a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14004757f  lea     r11, [rsp+80h+var_s0]
0x140047587  mov     eax, ebx
0x140047589  mov     rbx, [r11+38h]
0x14004758d  mov     rsi, [r11+40h]
0x140047591  mov     rsp, r11
0x140047594  pop     r15
0x140047596  pop     r13
0x140047598  pop     r12
0x14004759a  pop     rdi
0x14004759b  pop     rbp
0x14004759c  retn
```
