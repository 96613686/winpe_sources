# DfspDcGetReferralDataFromCache(_UNICODE_STRING *,DfsReferralData * *,DfsDomainRootPerfCtrSetInst * *)

- ea: `0x14001d384`
- end: `0x14001d85c`
- name: `?DfspDcGetReferralDataFromCache@@YAKPEAU_UNICODE_STRING@@PEAPEAVDfsReferralData@@PEAPEAVDfsDomainRootPerfCtrSetInst@@@Z`
- size: `1240`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *, struct DfsReferralData **, struct DfsDomainRootPerfCtrSetInst **)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d158`

## callees

- `0x1400096d8`
- `0x14000971c`
- `0x14000aa44`
- `0x14000abc4`
- `0x14000b934`
- `0x14000fca8`
- `0x14001a82c`
- `0x14001a85c`
- `0x14001ba64`
- `0x14001cf04`
- `0x14001cfa8`
- `0x14001d384`
- `0x14001d864`
- `0x14001d9a8`
- `0x14001e5dc`
- `0x14001e6d4`
- `0x1400583f4`
- `0x140058ce0`
- `0x140058db8`
- `0x14005b158`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14001d6a9`
- `ntdll!RtlInitUnicodeString` at `0x14001d6d4`
- `ntdll!RtlInitUnicodeString` at `0x14001d6a9`
- `ntdll!RtlInitUnicodeString` at `0x14001d6d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001d42d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001d705`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001d42d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001d705`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d5b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d751`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d5b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001d751`

## pseudocode

```c
__int64 __fastcall DfspDcGetReferralDataFromCache(
        struct _UNICODE_STRING *a1,
        struct DfsReferralData **a2,
        struct DfsDomainRootPerfCtrSetInst **a3)
{
  DfsGeneric *v5; // rsi
  char v6; // r14
  __int64 v7; // rbx
  DfsNamespacePerfCtrSetInst *v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r14d
  unsigned int RootReferralData; // eax
  __int64 v13; // rcx
  unsigned int v14; // r15d
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rbx
  volatile signed __int32 *v18; // rax
  __int64 v19; // rcx
  unsigned int *v20; // r10
  __int64 v22; // [rsp+38h] [rbp-49h] BYREF
  DfsNamespacePerfCtrSetInst *v23; // [rsp+40h] [rbp-41h] BYREF
  DfsGeneric *v24; // [rsp+48h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-31h] BYREF
  struct _UNICODE_STRING v26; // [rsp+60h] [rbp-21h] BYREF
  __int128 v27; // [rsp+70h] [rbp-11h] BYREF
  __int128 v28; // [rsp+80h] [rbp-1h] BYREF
  _OWORD v29[4]; // [rsp+90h] [rbp+Fh] BYREF
  char v32; // [rsp+100h] [rbp+7Fh] BYREF

  v24 = 0;
  LOBYTE(v5) = 0;
  v23 = 0;
  *a2 = 0;
  v6 = 0;
  v27 = 0;
  v32 = 0;
  v29[0] = 0;
  LOBYTE(v22) = 0;
  v26 = 0;
  *a3 = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_Z(*((_QWORD *)pWppControl + 2), 33, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids, a1);
  }
  v7 = qword_1400715F0;
  EnterCriticalSection(*(LPCRITICAL_SECTION *)(qword_1400715F0 + 24));
  ++*(_DWORD *)(v7 + 16);
  if ( (unsigned int)DfsFindUnicodePrefixLocked(
                       qword_1400715F0,
                       (_DWORD)a1,
                       (unsigned int)&v27,
                       (unsigned int)&v23,
                       (__int64)&v32) )
    goto LABEL_23;
  _InterlockedIncrement((volatile signed __int32 *)v23 + 2);
  v8 = v23;
  v9 = *((_QWORD *)v23 + 18);
  if ( !v9 )
  {
    LOBYTE(v5) = (_BYTE)v24;
LABEL_24:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_Z(*((_QWORD *)pWppControl + 2), 36, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids, a1);
    }
    goto LABEL_29;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
  v5 = (DfsGeneric *)*((_QWORD *)v8 + 18);
  v24 = v5;
  if ( !v5 )
  {
LABEL_23:
    v8 = v23;
    goto LABEL_24;
  }
  if ( DfsReferralData::TimeToRefresh(v5) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_qZ(
        *((_QWORD *)pWppControl + 2),
        35,
        (unsigned int)WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids,
        (_DWORD)v5,
        (__int64)a1);
    }
    DfsGeneric::ReleaseReference(v5);
    v8 = v23;
    LOBYTE(v5) = 0;
    v24 = 0;
    DfsDomainRootPerfCtrSetInst::ReleaseReferralDataLocked(v23);
LABEL_29:
    v6 = 1;
    goto LABEL_30;
  }
  *a2 = v5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qZ(
      *((_QWORD *)pWppControl + 2),
      34,
      (unsigned int)WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids,
      (_DWORD)v5,
      (__int64)a1);
  }
  v8 = v23;
LABEL_30:
  v10 = qword_1400715F0;
  --*(_DWORD *)(qword_1400715F0 + 16);
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v10 + 24));
  if ( !v6 )
  {
    v11 = 0;
LABEL_59:
    v20 = pWppControl;
    goto LABEL_60;
  }
  DfsGetPathComponents(a1, v29, &v26, &v28);
  RootReferralData = DfspDcGetRootReferralData(&v26, &v24, (unsigned __int8 *)&v22);
  v11 = RootReferralData;
  if ( (Microsoft_Windows_DFSN_ServerEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v13, ReferralRootRequestProcessed, RootReferralData);
  if ( v11 )
  {
    if ( v11 == 2 )
      DfspDcRemoveRootReferralPerfCtrFromTable(a1, v8);
    LOBYTE(v5) = (_BYTE)v24;
    goto LABEL_59;
  }
  v14 = 0;
  DestinationString = 0;
  if ( v8 )
    goto LABEL_47;
  v14 = DfsCreateUnicodeString(&DestinationString, &v26);
  if ( !v14 )
  {
    DfsCreateNamespacePerfCtrSetInst<DfsDomainRootPerfCtrSetInst>(v15, &v26, v16, &v23);
    v8 = v23;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x80000020) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_q(*((_QWORD *)pWppControl + 2), 37, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids, v23);
    }
    if ( v8 )
    {
      DfsNamespacePerfCtrSetInst::Initialize(v8);
      *((struct _UNICODE_STRING *)v8 + 8) = DestinationString;
      RtlInitUnicodeString(&DestinationString, 0);
      v14 = DfspDcAddRootReferralPerfCtrToTable(a1, v8);
    }
    else
    {
      DfsFreeUnicodeString(&DestinationString);
      RtlInitUnicodeString(&DestinationString, 0);
    }
  }
  if ( v8 || (DfspDcFindRootReferralPerfCtrFromTable(a1, &v23), (v8 = v23) != 0) )
  {
LABEL_47:
    v17 = qword_1400715F0;
    EnterCriticalSection(*(LPCRITICAL_SECTION *)(qword_1400715F0 + 24));
    ++*(_DWORD *)(v17 + 16);
    if ( *((_QWORD *)v8 + 18) )
    {
      DfsGeneric::ReleaseReference(v24);
      v18 = (volatile signed __int32 *)*((_QWORD *)v8 + 18);
      v24 = (DfsGeneric *)v18;
    }
    else
    {
      v18 = (volatile signed __int32 *)v24;
      *((_QWORD *)v8 + 18) = v24;
    }
    _InterlockedIncrement(v18 + 2);
    v19 = qword_1400715F0;
    --*(_DWORD *)(qword_1400715F0 + 16);
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v19 + 24));
    v8 = v23;
  }
  v5 = v24;
  *a2 = v24;
  v20 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (v14 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qd(*((_QWORD *)pWppControl + 2), 38, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids, v5, v14);
    goto LABEL_59;
  }
LABEL_60:
  if ( v8 )
    *a3 = v8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && v20
    && (((1 << (v11 != 0 ? 11 : 31)) | 0x20) & v20[7]) != 0
    && *((_BYTE *)v20 + 25) )
  {
    WPP_SF_ZqD(
      *((_QWORD *)v20 + 2),
      39,
      (unsigned int)WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids,
      (_DWORD)a1,
      (char)v5,
      v11,
      v22);
  }
  return v11;
}

```

## disassembly

```asm
0x14001d384  mov     rax, rsp
0x14001d387  mov     [rax+8], rbx
0x14001d38b  mov     [rax+18h], r8
0x14001d38f  mov     [rax+10h], rdx
0x14001d393  push    rbp
0x14001d394  push    rsi
0x14001d395  push    rdi
0x14001d396  push    r12
0x14001d398  push    r13
0x14001d39a  push    r14
0x14001d39c  push    r15
0x14001d39e  lea     rbp, [rax-5Fh]
0x14001d3a2  sub     rsp, 0A0h
0x14001d3a9  mov     r15, rdx
0x14001d3ac  xorps   xmm0, xmm0
0x14001d3af  xor     edx, edx
0x14001d3b1  xorps   xmm1, xmm1
0x14001d3b4  mov     r13, rcx
0x14001d3b7  mov     [rbp+57h+var_90], rdx
0x14001d3bb  mov     esi, edx
0x14001d3bd  mov     [rbp+57h+var_98], rdx
0x14001d3c1  mov     [r15], rdx
0x14001d3c4  mov     r14b, dl
0x14001d3c7  movups  [rbp+57h+var_68], xmm0
0x14001d3cb  mov     [rbp+57h+arg_18], dl
0x14001d3ce  movups  [rbp+57h+var_48], xmm1
0x14001d3d2  mov     byte ptr [rbp+57h+var_A0], dl
0x14001d3d5  movups  xmmword ptr [rbp+57h+var_78.Length], xmm0
0x14001d3d9  mov     [r8], rdx
0x14001d3dc  movups  [rbp+57h+var_58], xmm1
0x14001d3e0  lea     rax, WPP_GLOBAL_Control
0x14001d3e7  cmp     cs:WPP_GLOBAL_Control, rax
0x14001d3ee  lea     r12d, [rdx+20h]
0x14001d3f2  jz      short loc_14001D422
0x14001d3f4  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001d3fb  test    rcx, rcx
0x14001d3fe  jz      short loc_14001D422
0x14001d400  test    [rcx+1Ch], r12b
0x14001d404  jz      short loc_14001D422
0x14001d406  cmp     byte ptr [rcx+19h], 3
0x14001d40a  jb      short loc_14001D422
0x14001d40c  mov     rcx, [rcx+10h]
0x14001d410  lea     edx, [rsi+21h]
0x14001d413  mov     r9, r13
0x14001d416  lea     r8, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids
0x14001d41d  call    WPP_SF_Z
0x14001d422  mov     rbx, cs:qword_1400715F0
0x14001d429  mov     rcx, [rbx+18h]; lpCriticalSection
0x14001d42d  call    cs:__imp_EnterCriticalSection
0x14001d434  nop     dword ptr [rax+rax+00h]
0x14001d439  inc     dword ptr [rbx+10h]
0x14001d43c  lea     rax, [rbp+57h+arg_18]
0x14001d440  mov     rcx, cs:qword_1400715F0
0x14001d447  lea     r9, [rbp+57h+var_98]
0x14001d44b  lea     r8, [rbp+57h+var_68]
0x14001d44f  mov     qword ptr [rsp+0D0h+var_B0], rax
0x14001d454  mov     rdx, r13
0x14001d457  call    DfsFindUnicodePrefixLocked
0x14001d45c  test    eax, eax
0x14001d45e  jnz     loc_14001D55C
0x14001d464  mov     rax, [rbp+57h+var_98]
0x14001d468  lock inc dword ptr [rax+8]
0x14001d46c  mov     rdi, [rbp+57h+var_98]
0x14001d470  mov     rax, [rdi+90h]
0x14001d477  test    rax, rax
0x14001d47a  jz      loc_14001D556
0x14001d480  lock inc dword ptr [rax+8]
0x14001d484  mov     rsi, [rdi+90h]
0x14001d48b  mov     [rbp+57h+var_90], rsi
0x14001d48f  test    rsi, rsi
0x14001d492  jz      loc_14001D55C
0x14001d498  mov     rcx, rsi; this
0x14001d49b  call    ?TimeToRefresh@DfsReferralData@@QEAAEXZ; DfsReferralData::TimeToRefresh(void)
0x14001d4a0  test    al, al
0x14001d4a2  jnz     short loc_14001D4F5
0x14001d4a4  mov     [r15], rsi
0x14001d4a7  lea     rbx, WPP_GLOBAL_Control
0x14001d4ae  cmp     cs:WPP_GLOBAL_Control, rbx
0x14001d4b5  jz      short loc_14001D4EC
0x14001d4b7  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001d4be  test    rcx, rcx
0x14001d4c1  jz      short loc_14001D4EC
0x14001d4c3  test    [rcx+1Ch], r12b
0x14001d4c7  jz      short loc_14001D4EC
0x14001d4c9  cmp     byte ptr [rcx+19h], 3
0x14001d4cd  jb      short loc_14001D4EC
0x14001d4cf  mov     rcx, [rcx+10h]
0x14001d4d3  lea     r8, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids
0x14001d4da  mov     edx, 22h ; '"'
0x14001d4df  mov     qword ptr [rsp+0D0h+var_B0], r13
0x14001d4e4  mov     r9, rsi
0x14001d4e7  call    WPP_SF_qZ
0x14001d4ec  mov     rdi, [rbp+57h+var_98]
0x14001d4f0  jmp     loc_14001D5A3
0x14001d4f5  lea     rbx, WPP_GLOBAL_Control
0x14001d4fc  cmp     cs:WPP_GLOBAL_Control, rbx
0x14001d503  jz      short loc_14001D53A
0x14001d505  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001d50c  test    rcx, rcx
0x14001d50f  jz      short loc_14001D53A
0x14001d511  test    [rcx+1Ch], r12b
0x14001d515  jz      short loc_14001D53A
0x14001d517  cmp     byte ptr [rcx+19h], 3
0x14001d51b  jb      short loc_14001D53A
0x14001d51d  mov     rcx, [rcx+10h]
0x14001d521  lea     r8, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids
0x14001d528  mov     edx, 23h ; '#'
0x14001d52d  mov     qword ptr [rsp+0D0h+var_B0], r13
0x14001d532  mov     r9, rsi
0x14001d535  call    WPP_SF_qZ
0x14001d53a  mov     rcx, rsi; this
0x14001d53d  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14001d542  mov     rdi, [rbp+57h+var_98]
0x14001d546  xor     esi, esi
0x14001d548  mov     rcx, rdi; this
0x14001d54b  mov     [rbp+57h+var_90], rsi
0x14001d54f  call    ?ReleaseReferralDataLocked@DfsDomainRootPerfCtrSetInst@@QEAAXXZ; DfsDomainRootPerfCtrSetInst::ReleaseReferralDataLocked(void)
0x14001d554  jmp     short loc_14001D5A0
0x14001d556  mov     rsi, [rbp+57h+var_90]
0x14001d55a  jmp     short loc_14001D560
0x14001d55c  mov     rdi, [rbp+57h+var_98]
0x14001d560  lea     rbx, WPP_GLOBAL_Control
0x14001d567  cmp     cs:WPP_GLOBAL_Control, rbx
0x14001d56e  jz      short loc_14001D5A0
0x14001d570  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001d577  test    rcx, rcx
0x14001d57a  jz      short loc_14001D5A0
0x14001d57c  test    [rcx+1Ch], r12b
0x14001d580  jz      short loc_14001D5A0
0x14001d582  cmp     byte ptr [rcx+19h], 3
0x14001d586  jb      short loc_14001D5A0
0x14001d588  mov     rcx, [rcx+10h]
0x14001d58c  lea     r8, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids
0x14001d593  mov     edx, 24h ; '$'
0x14001d598  mov     r9, r13
0x14001d59b  call    WPP_SF_Z
0x14001d5a0  mov     r14b, 1
0x14001d5a3  mov     rcx, cs:qword_1400715F0
0x14001d5aa  dec     dword ptr [rcx+10h]
0x14001d5ad  mov     rcx, [rcx+18h]; lpCriticalSection
0x14001d5b1  call    cs:__imp_LeaveCriticalSection
0x14001d5b8  nop     dword ptr [rax+rax+00h]
0x14001d5bd  test    r14b, r14b
0x14001d5c0  jnz     short loc_14001D5CA
0x14001d5c2  xor     r14d, r14d
0x14001d5c5  jmp     loc_14001D7DC
0x14001d5ca  lea     r9, [rbp+57h+var_58]
0x14001d5ce  mov     rcx, r13
0x14001d5d1  lea     r8, [rbp+57h+var_78]
0x14001d5d5  lea     rdx, [rbp+57h+var_48]
0x14001d5d9  call    DfsGetPathComponents
0x14001d5de  lea     r8, [rbp+57h+var_A0]; unsigned __int8 *
0x14001d5e2  lea     rdx, [rbp+57h+var_90]; struct DfsFolderReferralData **
0x14001d5e6  lea     rcx, [rbp+57h+var_78]; struct _UNICODE_STRING *
0x14001d5ea  call    ?DfspDcGetRootReferralData@@YAKPEAU_UNICODE_STRING@@PEAPEAVDfsFolderReferralData@@PEAE@Z; DfspDcGetRootReferralData(_UNICODE_STRING *,DfsFolderReferralData * *,uchar *)
0x14001d5ef  test    byte ptr cs:Microsoft_Windows_DFSN_ServerEnableBits, 1
0x14001d5f6  mov     r14d, eax
0x14001d5f9  jz      short loc_14001D60A
0x14001d5fb  mov     r8d, eax
0x14001d5fe  lea     rdx, ReferralRootRequestProcessed
0x14001d605  call    McTemplateU0q_EtwEventWriteTransfer
0x14001d60a  test    r14d, r14d
0x14001d60d  jnz     loc_14001D7C7
0x14001d613  xor     r15d, r15d
0x14001d616  xorps   xmm0, xmm0
0x14001d619  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001d61d  test    rdi, rdi
0x14001d620  jnz     loc_14001D6FA
0x14001d626  lea     rdx, [rbp+57h+var_78]
0x14001d62a  lea     rcx, [rbp+57h+DestinationString]
0x14001d62e  call    DfsCreateUnicodeString
0x14001d633  mov     r15d, eax
0x14001d636  test    eax, eax
0x14001d638  jnz     loc_14001D6E0
0x14001d63e  lea     r9, [rbp+57h+var_98]
0x14001d642  lea     rdx, [rbp+57h+var_78]
0x14001d646  call    ??$DfsCreateNamespacePerfCtrSetInst@VDfsDomainRootPerfCtrSetInst@@@@YAXPEAU_UNICODE_STRING@@00PEAPEAVDfsDomainRootPerfCtrSetInst@@@Z; DfsCreateNamespacePerfCtrSetInst<DfsDomainRootPerfCtrSetInst>(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,DfsDomainRootPerfCtrSetInst * *)
0x14001d64b  cmp     cs:WPP_GLOBAL_Control, rbx
0x14001d652  mov     rdi, [rbp+57h+var_98]
0x14001d656  jz      short loc_14001D68A
0x14001d658  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001d65f  test    rcx, rcx
0x14001d662  jz      short loc_14001D68A
0x14001d664  test    dword ptr [rcx+1Ch], 80000020h
0x14001d66b  jz      short loc_14001D68A
0x14001d66d  cmp     byte ptr [rcx+19h], 3
0x14001d671  jb      short loc_14001D68A
0x14001d673  mov     rcx, [rcx+10h]
0x14001d677  lea     edx, [r14+25h]
0x14001d67b  mov     r9, rdi
0x14001d67e  lea     r8, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids
0x14001d685  call    WPP_SF_q
0x14001d68a  test    rdi, rdi
0x14001d68d  jz      short loc_14001D6C5
0x14001d68f  mov     rcx, rdi; this
0x14001d692  call    ?Initialize@DfsNamespacePerfCtrSetInst@@QEAAXXZ; DfsNamespacePerfCtrSetInst::Initialize(void)
0x14001d697  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x14001d69b  xor     edx, edx; SourceString
0x14001d69d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001d6a1  movdqu  xmmword ptr [rdi+80h], xmm0
0x14001d6a9  call    cs:__imp_RtlInitUnicodeString
0x14001d6b0  nop     dword ptr [rax+rax+00h]
0x14001d6b5  mov     rdx, rdi; struct DfsDomainRootPerfCtrSetInst *
0x14001d6b8  mov     rcx, r13; struct _UNICODE_STRING *
0x14001d6bb  call    ?DfspDcAddRootReferralPerfCtrToTable@@YAKPEAU_UNICODE_STRING@@PEAVDfsDomainRootPerfCtrSetInst@@@Z; DfspDcAddRootReferralPerfCtrToTable(_UNICODE_STRING *,DfsDomainRootPerfCtrSetInst *)
0x14001d6c0  mov     r15d, eax
0x14001d6c3  jmp     short loc_14001D6E0
0x14001d6c5  lea     rcx, [rbp+57h+DestinationString]
0x14001d6c9  call    DfsFreeUnicodeString
0x14001d6ce  xor     edx, edx; SourceString
0x14001d6d0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001d6d4  call    cs:__imp_RtlInitUnicodeString
0x14001d6db  nop     dword ptr [rax+rax+00h]
0x14001d6e0  test    rdi, rdi
0x14001d6e3  jnz     short loc_14001D6FA
0x14001d6e5  lea     rdx, [rbp+57h+var_98]; struct DfsDomainRootPerfCtrSetInst **
0x14001d6e9  mov     rcx, r13; struct _UNICODE_STRING *
0x14001d6ec  call    ?DfspDcFindRootReferralPerfCtrFromTable@@YAXPEAU_UNICODE_STRING@@PEAPEAVDfsDomainRootPerfCtrSetInst@@@Z; DfspDcFindRootReferralPerfCtrFromTable(_UNICODE_STRING *,DfsDomainRootPerfCtrSetInst * *)
0x14001d6f1  mov     rdi, [rbp+57h+var_98]
0x14001d6f5  test    rdi, rdi
0x14001d6f8  jz      short loc_14001D768
0x14001d6fa  mov     rbx, cs:qword_1400715F0
0x14001d701  mov     rcx, [rbx+18h]; lpCriticalSection
0x14001d705  call    cs:__imp_EnterCriticalSection
0x14001d70c  nop     dword ptr [rax+rax+00h]
0x14001d711  inc     dword ptr [rbx+10h]
0x14001d714  cmp     qword ptr [rdi+90h], 0
0x14001d71c  jnz     short loc_14001D72B
0x14001d71e  mov     rax, [rbp+57h+var_90]
0x14001d722  mov     [rdi+90h], rax
0x14001d729  jmp     short loc_14001D73F
0x14001d72b  mov     rcx, [rbp+57h+var_90]; this
0x14001d72f  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14001d734  mov     rax, [rdi+90h]
0x14001d73b  mov     [rbp+57h+var_90], rax
0x14001d73f  lock inc dword ptr [rax+8]
0x14001d743  mov     rcx, cs:qword_1400715F0
0x14001d74a  dec     dword ptr [rcx+10h]
0x14001d74d  mov     rcx, [rcx+18h]; lpCriticalSection
0x14001d751  call    cs:__imp_LeaveCriticalSection
0x14001d758  nop     dword ptr [rax+rax+00h]
0x14001d75d  mov     rdi, [rbp+57h+var_98]
0x14001d761  lea     rbx, WPP_GLOBAL_Control
0x14001d768  mov     rax, [rbp+57h+arg_8]
0x14001d76c  mov     rsi, [rbp+57h+var_90]
0x14001d770  mov     [rax], rsi
0x14001d773  cmp     cs:WPP_GLOBAL_Control, rbx
0x14001d77a  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001d781  jz      short loc_14001D7E3
0x14001d783  test    r10, r10
0x14001d786  jz      short loc_14001D7E3
0x14001d788  mov     eax, r15d
0x14001d78b  neg     eax
0x14001d78d  mov     eax, r12d
0x14001d790  sbb     edx, edx
0x14001d792  and     edx, 0FFFFFFECh
0x14001d795  add     edx, 1Fh
0x14001d798  bts     eax, edx
0x14001d79b  test    [r10+1Ch], eax
0x14001d79f  jz      short loc_14001D7E3
0x14001d7a1  cmp     byte ptr [r10+19h], 3
0x14001d7a6  jb      short loc_14001D7E3
0x14001d7a8  mov     rcx, [r10+10h]
0x14001d7ac  lea     r8, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids
0x14001d7b3  mov     edx, 26h ; '&'
0x14001d7b8  mov     [rsp+0D0h+var_B0], r15d
0x14001d7bd  mov     r9, rsi
0x14001d7c0  call    WPP_SF_qd
0x14001d7c5  jmp     short loc_14001D7DC
0x14001d7c7  cmp     r14d, 2
0x14001d7cb  jnz     short loc_14001D7D8
0x14001d7cd  mov     rdx, rdi; struct DfsDomainRootPerfCtrSetInst *
0x14001d7d0  mov     rcx, r13; struct _UNICODE_STRING *
0x14001d7d3  call    ?DfspDcRemoveRootReferralPerfCtrFromTable@@YAKPEAU_UNICODE_STRING@@PEAVDfsDomainRootPerfCtrSetInst@@@Z; DfspDcRemoveRootReferralPerfCtrFromTable(_UNICODE_STRING *,DfsDomainRootPerfCtrSetInst *)
0x14001d7d8  mov     rsi, [rbp+57h+var_90]
0x14001d7dc  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001d7e3  test    rdi, rdi
0x14001d7e6  jz      short loc_14001D7EF
0x14001d7e8  mov     rax, [rbp+57h+arg_10]
0x14001d7ec  mov     [rax], rdi
0x14001d7ef  cmp     cs:WPP_GLOBAL_Control, rbx
0x14001d7f6  jz      short loc_14001D83D
0x14001d7f8  test    r10, r10
0x14001d7fb  jz      short loc_14001D83D
0x14001d7fd  mov     eax, r14d
0x14001d800  neg     eax
0x14001d802  sbb     ecx, ecx
0x14001d804  and     ecx, 0FFFFFFECh
0x14001d807  add     ecx, 1Fh
0x14001d80a  bts     r12d, ecx
0x14001d80e  test    [r10+1Ch], r12d
0x14001d812  jz      short loc_14001D83D
0x14001d814  cmp     byte ptr [r10+19h], 1
0x14001d819  jb      short loc_14001D83D
0x14001d81b  mov     rcx, [r10+10h]
0x14001d81f  lea     r8, WPP_967a355e3a8a3c7500cdeb97aa8a8c73_Traceguids
0x14001d826  mov     edx, 27h ; '''
0x14001d82b  mov     [rsp+28h], r14d
0x14001d830  mov     r9, r13
0x14001d833  mov     qword ptr [rsp+0D0h+var_B0], rsi
  ... truncated ...
```
