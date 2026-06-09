# DfsRootFolder::AddMetadataLink(_UNICODE_STRING *,_UNICODE_STRING *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1400287a0`
- end: `0x140028c34`
- name: `?AddMetadataLink@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@0PEBG11K@Z`
- size: `1172`
- prototype: `unsigned int __usercall@<eax>(DfsRootFolder *__hidden this@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x140010348`

## callees

- `0x140005a94`
- `0x14000a354`
- `0x14000abc4`
- `0x14000f784`
- `0x14000f808`
- `0x1400287a0`
- `0x140028c3c`
- `0x14002b5d0`
- `0x140031108`
- `0x1400316bc`
- `0x140032398`
- `0x140058db8`
- `0x1400594a4`
- `0x14005ce3a`
- `0x14005ce70`
- `0x14005e010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140028848`
- `ntdll!RtlInitUnicodeString` at `0x140028848`
- `RPCRT4!UuidCreate` at `0x140028858`
- `RPCRT4!UuidCreate` at `0x140028858`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028bc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140028bc2`
- `dfscli!I_NetDfsIsThisADomainName` at `0x14002894d`
- `dfscli!I_NetDfsIsThisADomainName` at `0x14002894d`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::AddMetadataLink(
        RTL_SRWLOCK *this,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        WCHAR *a4,
        WCHAR *netname,
        unsigned __int16 *a6,
        char a7)
{
  unsigned int VisibleNameContext; // esi
  __int64 v11; // rax
  __int64 (__fastcall **Ptr)(RTL_SRWLOCK *, unsigned __int64 *); // rax
  struct _UNICODE_STRING *v13; // rdx
  __int64 v14; // rax
  void (__fastcall **v15)(RTL_SRWLOCK *); // rax
  DfsStore *v16; // rcx
  DfsStore *v17; // rcx
  unsigned __int8 v18; // r13
  __int64 v19; // rax
  int v20; // r8d
  __int64 v21; // r9
  int v22; // r8d
  struct _UNICODE_STRING *v23; // r12
  DfsGeneric *v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rax
  unsigned __int8 v28; // [rsp+40h] [rbp-C0h] BYREF
  char v29; // [rsp+41h] [rbp-BFh]
  char v30; // [rsp+42h] [rbp-BEh]
  unsigned __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  DfsGeneric *v32; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v34[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING *v35; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING v36; // [rsp+80h] [rbp-80h] BYREF
  __int128 v37; // [rsp+90h] [rbp-70h] BYREF
  __int64 v38; // [rsp+A0h] [rbp-60h]
  _BYTE v39[64]; // [rsp+B0h] [rbp-50h] BYREF
  UUID Uuid; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v41[68]; // [rsp+100h] [rbp+0h] BYREF
  int v42; // [rsp+144h] [rbp+44h]

  v35 = a3;
  v38 = 0;
  v37 = 0;
  memset_0(v39, 0, sizeof(v39));
  memset_0(v41, 0, 0x98u);
  v31 = 0;
  v28 = 0;
  v30 = 0;
  *(_OWORD *)v34 = 0;
  v29 = 0;
  DestinationString = 0;
  v36 = 0;
  Uuid = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  VisibleNameContext = UuidCreate(&Uuid);
  if ( VisibleNameContext )
    goto LABEL_29;
  v11 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 3))(this);
  VisibleNameContext = (*(__int64 (__fastcall **)(__int64, UUID *, unsigned __int16 **))(*(_QWORD *)v11 + 80LL))(
                         v11,
                         &Uuid,
                         v34);
  if ( VisibleNameContext )
    goto LABEL_29;
  Ptr = (__int64 (__fastcall **)(RTL_SRWLOCK *, unsigned __int64 *))this->Ptr;
  v30 = 1;
  VisibleNameContext = Ptr[7](this, &v31);
  if ( VisibleNameContext )
    goto LABEL_29;
  VisibleNameContext = DfsRootFolder::GetVisibleNameContext((DfsRootFolder *)this, v13, &DestinationString);
  if ( VisibleNameContext )
    goto LABEL_29;
  v14 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 3))(this);
  VisibleNameContext = (*(__int64 (__fastcall **)(__int64, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *))(*(_QWORD *)v14 + 208LL))(
                         v14,
                         &DestinationString,
                         a2,
                         &v36);
  if ( VisibleNameContext )
    goto LABEL_29;
  v15 = (void (__fastcall **)(RTL_SRWLOCK *))this->Ptr;
  v29 = 1;
  v15[3](this);
  VisibleNameContext = DfsStore::StoreInitializeNameInformation(
                         v16,
                         (struct _DFS_NAME_INFORMATION_ *)v41,
                         &v36,
                         &Uuid,
                         a6);
  if ( VisibleNameContext )
    goto LABEL_29;
  if ( !(unsigned int)I_NetDfsIsThisADomainName(a4) || !(unsigned int)DfsIsThisAStandAloneDfsName(a4, netname) )
    v42 |= 0x10u;
  (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 3))(this);
  VisibleNameContext = DfsStore::StoreInitializeReplicaInformation(
                         v17,
                         (struct _DFS_REPLICA_LIST_INFORMATION_ *)&v37,
                         (struct _DFS_REPLICA_INFORMATION__ *)v39,
                         a4,
                         netname);
  if ( VisibleNameContext || (VisibleNameContext = DfsRootFolder::AcquireRootLock((DfsRootFolder *)this, 1u)) != 0 )
  {
LABEL_29:
    v18 = v28;
  }
  else
  {
    v18 = 1;
    v19 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 3))(this);
    VisibleNameContext = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _BYTE *, __int128 *, unsigned __int16 **))(*(_QWORD *)v19 + 24LL))(
                           v19,
                           v31,
                           v41,
                           &v37,
                           v34);
    if ( VisibleNameContext )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x840) != 0
        && *((_BYTE *)pWppControl + 25) )
      {
        WPP_SF_ZSSD(
          *((_QWORD *)pWppControl + 2),
          52,
          v20,
          (_DWORD)a2,
          (__int64)a4,
          (__int64)netname,
          VisibleNameContext);
      }
      LOBYTE(v21) = 1;
      (*((void (__fastcall **)(RTL_SRWLOCK *, __int64, _QWORD, __int64))this->Ptr + 4))(this, 3, 0, v21);
    }
    else
    {
      VisibleNameContext = DfsRootFolder::UpdateLinkInformation((DfsRootFolder *)this, v31, v34[1], 1u);
      if ( VisibleNameContext )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x840) != 0
          && *((_BYTE *)pWppControl + 25) )
        {
          WPP_SF_ZSSD(
            *((_QWORD *)pWppControl + 2),
            53,
            v22,
            (_DWORD)a2,
            (__int64)a4,
            (__int64)netname,
            VisibleNameContext);
        }
        if ( VisibleNameContext == 183 && (a7 & 1) == 0 )
        {
          v23 = v35;
          v32 = 0;
          v28 = 0;
          if ( !DfsRootFolder::ValidateLinkName((DfsRootFolder *)this, v35, &v28, 1u, &v32, 0) )
          {
            v24 = v32;
            VisibleNameContext = DfsRootFolder::AddMetadataLinkReplicaLocked(
                                   (DfsRootFolder *)this,
                                   v23,
                                   a4,
                                   netname,
                                   v32);
            DfsGeneric::ReleaseReference(v24);
          }
        }
      }
    }
  }
  DfsFreeUnicodeString(&DestinationString);
  if ( v29 )
  {
    v25 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 3))(this);
    (*(void (__fastcall **)(__int64, struct _UNICODE_STRING *))(*(_QWORD *)v25 + 216LL))(v25, &v36);
  }
  if ( v31 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 8))(this);
  if ( v30 )
  {
    v26 = (*((__int64 (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 3))(this);
    (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v26 + 88LL))(v26, v34);
  }
  if ( v18 )
  {
    ++LODWORD(this[15].Ptr);
    ReleaseSRWLockExclusive(this + 14);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 54, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids, VisibleNameContext);
  }
  return VisibleNameContext;
}

```

## disassembly

```asm
0x1400287a0  push    rbp
0x1400287a2  push    rbx
0x1400287a3  push    rsi
0x1400287a4  push    rdi
0x1400287a5  push    r12
0x1400287a7  push    r13
0x1400287a9  push    r14
0x1400287ab  push    r15
0x1400287ad  lea     rbp, [rsp-0B8h]
0x1400287b5  sub     rsp, 1B8h
0x1400287bc  mov     rax, cs:__security_cookie
0x1400287c3  xor     rax, rsp
0x1400287c6  mov     [rbp+0F0h+var_50], rax
0x1400287cd  mov     r15, [rbp+0F0h+netname]
0x1400287d4  xor     eax, eax
0x1400287d6  mov     r13, [rbp+0F0h+arg_28]
0x1400287dd  mov     r12, rdx
0x1400287e0  mov     [rsp+1F0h+var_178], r8
0x1400287e5  mov     rdi, rcx
0x1400287e8  xorps   xmm0, xmm0
0x1400287eb  mov     [rbp+0F0h+var_150], rax
0x1400287ef  lea     ebx, [rax+40h]
0x1400287f2  xor     edx, edx; Val
0x1400287f4  mov     r8d, ebx; Size
0x1400287f7  lea     rcx, [rbp+0F0h+var_140]; void *
0x1400287fb  mov     r14, r9
0x1400287fe  movups  [rbp+0F0h+var_160], xmm0
0x140028802  call    memset_0
0x140028807  xor     edx, edx; Val
0x140028809  lea     r8d, [rbx+58h]; Size
0x14002880d  lea     rcx, [rbp+0F0h+var_F0]; void *
0x140028811  call    memset_0
0x140028816  xor     eax, eax
0x140028818  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x14002881d  xorps   xmm0, xmm0
0x140028820  mov     [rsp+1F0h+var_1A8], rax
0x140028825  xorps   xmm1, xmm1
0x140028828  mov     [rsp+1F0h+var_1B0], al
0x14002882c  xor     edx, edx; SourceString
0x14002882e  mov     [rsp+1F0h+var_1AE], al
0x140028832  movups  xmmword ptr [rsp+1F0h+var_188], xmm0
0x140028837  mov     [rsp+1F0h+var_1AF], al
0x14002883b  movups  xmmword ptr [rsp+1F0h+DestinationString.Length], xmm1
0x140028840  movups  xmmword ptr [rbp+0F0h+var_170.Length], xmm0
0x140028844  movups  xmmword ptr [rbp+0F0h+Uuid.Data1], xmm0
0x140028848  call    cs:__imp_RtlInitUnicodeString
0x14002884f  nop     dword ptr [rax+rax+00h]
0x140028854  lea     rcx, [rbp+0F0h+Uuid]; Uuid
0x140028858  call    cs:__imp_UuidCreate
0x14002885f  nop     dword ptr [rax+rax+00h]
0x140028864  mov     esi, eax
0x140028866  test    eax, eax
0x140028868  jnz     loc_140028B32
0x14002886e  mov     rax, [rdi]
0x140028871  mov     rcx, rdi
0x140028874  mov     rax, [rax+18h]
0x140028878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002887d  mov     r9, rax
0x140028880  lea     r8, [rsp+1F0h+var_188]
0x140028885  lea     rdx, [rbp+0F0h+Uuid]
0x140028889  mov     rcx, [rax]
0x14002888c  mov     rax, [rcx+50h]
0x140028890  mov     rcx, r9
0x140028893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028898  mov     esi, eax
0x14002889a  test    eax, eax
0x14002889c  jnz     loc_140028B32
0x1400288a2  mov     rax, [rdi]
0x1400288a5  lea     rdx, [rsp+1F0h+var_1A8]
0x1400288aa  mov     rcx, rdi
0x1400288ad  mov     [rsp+1F0h+var_1AE], 1
0x1400288b2  mov     rax, [rax+38h]
0x1400288b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400288bb  mov     esi, eax
0x1400288bd  test    eax, eax
0x1400288bf  jnz     loc_140028B32
0x1400288c5  lea     r8, [rsp+1F0h+DestinationString]; struct _UNICODE_STRING *
0x1400288ca  mov     rcx, rdi; this
0x1400288cd  call    ?GetVisibleNameContext@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@0@Z; DfsRootFolder::GetVisibleNameContext(_UNICODE_STRING *,_UNICODE_STRING *)
0x1400288d2  mov     esi, eax
0x1400288d4  test    eax, eax
0x1400288d6  jnz     loc_140028B32
0x1400288dc  mov     rax, [rdi]
0x1400288df  mov     rcx, rdi
0x1400288e2  mov     rax, [rax+18h]
0x1400288e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400288eb  mov     r10, rax
0x1400288ee  lea     r9, [rbp+0F0h+var_170]
0x1400288f2  mov     r8, r12
0x1400288f5  lea     rdx, [rsp+1F0h+DestinationString]
0x1400288fa  mov     rcx, [rax]
0x1400288fd  mov     rax, [rcx+0D0h]
0x140028904  mov     rcx, r10
0x140028907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002890c  mov     esi, eax
0x14002890e  test    eax, eax
0x140028910  jnz     loc_140028B32
0x140028916  mov     rax, [rdi]
0x140028919  mov     rcx, rdi
0x14002891c  mov     [rsp+1F0h+var_1AF], 1
0x140028921  mov     rax, [rax+18h]
0x140028925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002892a  lea     r9, [rbp+0F0h+Uuid]; struct _GUID *
0x14002892e  mov     [rsp+1F0h+var_1D0], r13; unsigned __int16 *
0x140028933  lea     r8, [rbp+0F0h+var_170]; struct _UNICODE_STRING *
0x140028937  lea     rdx, [rbp+0F0h+var_F0]; struct _DFS_NAME_INFORMATION_ *
0x14002893b  call    ?StoreInitializeNameInformation@DfsStore@@QEAAKPEAU_DFS_NAME_INFORMATION_@@PEAU_UNICODE_STRING@@PEAU_GUID@@PEBG@Z; DfsStore::StoreInitializeNameInformation(_DFS_NAME_INFORMATION_ *,_UNICODE_STRING *,_GUID *,ushort const *)
0x140028940  mov     esi, eax
0x140028942  test    eax, eax
0x140028944  jnz     loc_140028B32
0x14002894a  mov     rcx, r14
0x14002894d  call    cs:__imp_I_NetDfsIsThisADomainName
0x140028954  nop     dword ptr [rax+rax+00h]
0x140028959  test    eax, eax
0x14002895b  jz      short loc_14002896C
0x14002895d  mov     rdx, r15; netname
0x140028960  mov     rcx, r14; servername
0x140028963  call    DfsIsThisAStandAloneDfsName
0x140028968  test    eax, eax
0x14002896a  jnz     short loc_140028970
0x14002896c  or      [rbp+0F0h+var_AC], 10h
0x140028970  mov     rax, [rdi]
0x140028973  mov     rcx, rdi
0x140028976  mov     rax, [rax+18h]
0x14002897a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002897f  mov     r9, r14; unsigned __int16 *
0x140028982  mov     [rsp+1F0h+var_1D0], r15; unsigned __int16 *
0x140028987  lea     r8, [rbp+0F0h+var_140]; struct _DFS_REPLICA_INFORMATION__ *
0x14002898b  lea     rdx, [rbp+0F0h+var_160]; struct _DFS_REPLICA_LIST_INFORMATION_ *
0x14002898f  call    ?StoreInitializeReplicaInformation@DfsStore@@QEAAKPEAU_DFS_REPLICA_LIST_INFORMATION_@@PEAU_DFS_REPLICA_INFORMATION__@@PEBG2@Z; DfsStore::StoreInitializeReplicaInformation(_DFS_REPLICA_LIST_INFORMATION_ *,_DFS_REPLICA_INFORMATION__ *,ushort const *,ushort const *)
0x140028994  mov     esi, eax
0x140028996  test    eax, eax
0x140028998  jnz     loc_140028B32
0x14002899e  mov     dl, 1; unsigned __int8
0x1400289a0  mov     rcx, rdi; this
0x1400289a3  call    ?AcquireRootLock@DfsRootFolder@@QEAAKE@Z; DfsRootFolder::AcquireRootLock(uchar)
0x1400289a8  mov     esi, eax
0x1400289aa  test    eax, eax
0x1400289ac  jnz     loc_140028B32
0x1400289b2  mov     rax, [rdi]
0x1400289b5  mov     rcx, rdi
0x1400289b8  mov     r13b, 1
0x1400289bb  mov     rax, [rax+18h]
0x1400289bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400289c4  mov     rdx, [rsp+1F0h+var_1A8]
0x1400289c9  lea     r9, [rbp+0F0h+var_160]
0x1400289cd  mov     r10, rax
0x1400289d0  lea     r8, [rbp+0F0h+var_F0]
0x1400289d4  mov     rcx, [rax]
0x1400289d7  mov     rax, [rcx+18h]
0x1400289db  lea     rcx, [rsp+1F0h+var_188]
0x1400289e0  mov     [rsp+1F0h+var_1D0], rcx
0x1400289e5  mov     rcx, r10
0x1400289e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400289ed  mov     esi, eax
0x1400289ef  test    eax, eax
0x1400289f1  jz      short loc_140028A5B
0x1400289f3  lea     rax, WPP_GLOBAL_Control
0x1400289fa  cmp     cs:WPP_GLOBAL_Control, rax
0x140028a01  jz      short loc_140028A3D
0x140028a03  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140028a0a  test    rcx, rcx
0x140028a0d  jz      short loc_140028A3D
0x140028a0f  bts     ebx, 0Bh
0x140028a13  test    [rcx+1Ch], ebx
0x140028a16  jz      short loc_140028A3D
0x140028a18  cmp     [rcx+19h], r13b
0x140028a1c  jb      short loc_140028A3D
0x140028a1e  mov     rcx, [rcx+10h]
0x140028a22  mov     edx, 34h ; '4'
0x140028a27  mov     [rsp+1F0h+var_1C0], esi
0x140028a2b  mov     r9, r12
0x140028a2e  mov     qword ptr [rsp+1F0h+var_1C8], r15
0x140028a33  mov     [rsp+1F0h+var_1D0], r14
0x140028a38  call    WPP_SF_ZSSD
0x140028a3d  mov     rax, [rdi]
0x140028a40  xor     r8d, r8d
0x140028a43  mov     r9b, r13b
0x140028a46  mov     rcx, rdi
0x140028a49  mov     rax, [rax+20h]
0x140028a4d  lea     edx, [r8+3]
0x140028a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028a56  jmp     loc_140028B37
0x140028a5b  mov     r8, [rsp+1F0h+var_188+8]; unsigned __int16 *
0x140028a60  mov     r9b, r13b; unsigned __int8
0x140028a63  mov     rdx, [rsp+1F0h+var_1A8]; unsigned __int64
0x140028a68  mov     rcx, rdi; this
0x140028a6b  call    ?UpdateLinkInformation@DfsRootFolder@@QEAAK_KPEAGE@Z; DfsRootFolder::UpdateLinkInformation(unsigned __int64,ushort *,uchar)
0x140028a70  mov     esi, eax
0x140028a72  test    eax, eax
0x140028a74  jz      loc_140028B37
0x140028a7a  lea     rax, WPP_GLOBAL_Control
0x140028a81  cmp     cs:WPP_GLOBAL_Control, rax
0x140028a88  jz      short loc_140028AC4
0x140028a8a  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140028a91  test    rcx, rcx
0x140028a94  jz      short loc_140028AC4
0x140028a96  bts     ebx, 0Bh
0x140028a9a  test    [rcx+1Ch], ebx
0x140028a9d  jz      short loc_140028AC4
0x140028a9f  cmp     [rcx+19h], r13b
0x140028aa3  jb      short loc_140028AC4
0x140028aa5  mov     rcx, [rcx+10h]
0x140028aa9  mov     edx, 35h ; '5'
0x140028aae  mov     [rsp+1F0h+var_1C0], esi
0x140028ab2  mov     r9, r12
0x140028ab5  mov     qword ptr [rsp+1F0h+var_1C8], r15
0x140028aba  mov     [rsp+1F0h+var_1D0], r14
0x140028abf  call    WPP_SF_ZSSD
0x140028ac4  cmp     esi, 0B7h
0x140028aca  jnz     short loc_140028B37
0x140028acc  test    byte ptr [rbp+0F0h+arg_30], r13b
0x140028ad3  jnz     short loc_140028B37
0x140028ad5  mov     r12, [rsp+1F0h+var_178]
0x140028ada  lea     rax, [rsp+1F0h+var_1A0]
0x140028adf  and     [rsp+1F0h+var_1A0], 0
0x140028ae5  lea     r8, [rsp+1F0h+var_1B0]; unsigned __int8 *
0x140028aea  mov     rdx, r12; struct _UNICODE_STRING *
0x140028aed  mov     [rsp+1F0h+var_1C8], 0; unsigned __int8
0x140028af2  mov     r9b, r13b; unsigned __int8
0x140028af5  mov     [rsp+1F0h+var_1B0], 0
0x140028afa  mov     rcx, rdi; this
0x140028afd  mov     [rsp+1F0h+var_1D0], rax; struct DfsFolder **
0x140028b02  call    ?ValidateLinkName@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@PEAEEPEAPEAVDfsFolder@@E@Z; DfsRootFolder::ValidateLinkName(_UNICODE_STRING *,uchar *,uchar,DfsFolder * *,uchar)
0x140028b07  test    eax, eax
0x140028b09  jnz     short loc_140028B37
0x140028b0b  mov     rbx, [rsp+1F0h+var_1A0]
0x140028b10  mov     r9, r15; unsigned __int16 *
0x140028b13  mov     r8, r14; unsigned __int16 *
0x140028b16  mov     [rsp+1F0h+var_1D0], rbx; struct DfsFolder *
0x140028b1b  mov     rdx, r12; struct _UNICODE_STRING *
0x140028b1e  mov     rcx, rdi; this
0x140028b21  call    ?AddMetadataLinkReplicaLocked@DfsRootFolder@@QEAAKPEAU_UNICODE_STRING@@PEBG1PEAVDfsFolder@@@Z; DfsRootFolder::AddMetadataLinkReplicaLocked(_UNICODE_STRING *,ushort const *,ushort const *,DfsFolder *)
0x140028b26  mov     rcx, rbx; this
0x140028b29  mov     esi, eax
0x140028b2b  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x140028b30  jmp     short loc_140028B37
0x140028b32  mov     r13b, [rsp+1F0h+var_1B0]
0x140028b37  lea     rcx, [rsp+1F0h+DestinationString]
0x140028b3c  call    DfsFreeUnicodeString
0x140028b41  cmp     [rsp+1F0h+var_1AF], 0
0x140028b46  jz      short loc_140028B70
0x140028b48  mov     rax, [rdi]
0x140028b4b  mov     rcx, rdi
0x140028b4e  mov     rax, [rax+18h]
0x140028b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028b57  mov     r8, rax
0x140028b5a  lea     rdx, [rbp+0F0h+var_170]
0x140028b5e  mov     rcx, [rax]
0x140028b61  mov     rax, [rcx+0D8h]
0x140028b68  mov     rcx, r8
0x140028b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028b70  mov     rdx, [rsp+1F0h+var_1A8]
0x140028b75  test    rdx, rdx
0x140028b78  jz      short loc_140028B89
0x140028b7a  mov     rax, [rdi]
0x140028b7d  mov     rcx, rdi
0x140028b80  mov     rax, [rax+40h]
0x140028b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028b89  cmp     [rsp+1F0h+var_1AE], 0
0x140028b8e  jz      short loc_140028BB6
0x140028b90  mov     rax, [rdi]
0x140028b93  mov     rcx, rdi
0x140028b96  mov     rax, [rax+18h]
0x140028b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028b9f  mov     r8, rax
0x140028ba2  lea     rdx, [rsp+1F0h+var_188]
0x140028ba7  mov     rcx, [rax]
0x140028baa  mov     rax, [rcx+58h]
0x140028bae  mov     rcx, r8
0x140028bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028bb6  test    r13b, r13b
0x140028bb9  jz      short loc_140028BCE
0x140028bbb  inc     dword ptr [rdi+78h]
0x140028bbe  lea     rcx, [rdi+70h]; SRWLock
0x140028bc2  call    cs:__imp_ReleaseSRWLockExclusive
0x140028bc9  nop     dword ptr [rax+rax+00h]
0x140028bce  lea     rax, WPP_GLOBAL_Control
0x140028bd5  cmp     cs:WPP_GLOBAL_Control, rax
0x140028bdc  jz      short loc_140028C0E
0x140028bde  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140028be5  test    rcx, rcx
0x140028be8  jz      short loc_140028C0E
0x140028bea  test    byte ptr [rcx+1Ch], 20h
0x140028bee  jz      short loc_140028C0E
0x140028bf0  cmp     byte ptr [rcx+19h], 2
0x140028bf4  jb      short loc_140028C0E
0x140028bf6  mov     rcx, [rcx+10h]
0x140028bfa  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x140028c01  mov     edx, 36h ; '6'
0x140028c06  mov     r9d, esi
0x140028c09  call    WPP_SF_D
0x140028c0e  mov     eax, esi
0x140028c10  mov     rcx, [rbp+0F0h+var_50]
0x140028c17  xor     rcx, rsp; StackCookie
0x140028c1a  call    __security_check_cookie
0x140028c1f  add     rsp, 1B8h
0x140028c26  pop     r15
0x140028c28  pop     r14
0x140028c2a  pop     r13
  ... truncated ...
```
