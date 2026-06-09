# LsaDbpDsFixupCallback(void *)

- ea: `0x1800136d4`
- end: `0x180013bb4`
- name: `?LsaDbpDsFixupCallback@@YAKPEAX@Z`
- size: `1248`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180013bc0`

## callees

- `0x180001fb8`
- `0x18000c140`
- `0x18000c400`
- `0x18000fd18`
- `0x18000fd40`
- `0x1800136d4`
- `0x180013cbc`
- `0x180014358`
- `0x1800151f0`
- `0x1800194a8`
- `0x18001f574`
- `0x18001fbcc`
- `0x1800266b0`

## import_xrefs

- `DSPARSE!DsIsMangledDnW` at `0x1800138b0`
- `DSPARSE!DsIsMangledDnW` at `0x1800138b0`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x180013b0e`
- `LSASRV!_fgu__LSAPR_TRUSTED_DOMAIN_INFO` at `0x180013b0e`
- `LSASRV!LsaIRegisterNotification` at `0x180013a66`
- `LSASRV!LsaIRegisterNotification` at `0x180013a66`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x1800139ec`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180013b36`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x1800139ec`
- `LSASRV!LsapDbExpAcquireWriteLockTrustedDomainList` at `0x180013b36`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180013a08`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180013b6d`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180013a08`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180013b6d`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180013b67`
- `LSASRV!LsapDbExpMakeCacheInvalid` at `0x180013b67`
- `LSASRV!LsapFreeLsaHeap` at `0x180013b18`
- `LSASRV!LsapFreeLsaHeap` at `0x180013b22`
- `LSASRV!LsapFreeLsaHeap` at `0x180013b2b`
- `LSASRV!LsapFreeLsaHeap` at `0x180013b18`
- `LSASRV!LsapFreeLsaHeap` at `0x180013b22`
- `LSASRV!LsapFreeLsaHeap` at `0x180013b2b`
- `ntdll!RtlNtStatusToDosError` at `0x180013b9a`
- `ntdll!RtlNtStatusToDosError` at `0x180013b9a`
- `NETLOGON!I_NetNotifyDsChange` at `0x180013a93`
- `NETLOGON!I_NetNotifyDsChange` at `0x180013a93`

## pseudocode

```c
ULONG __fastcall LsaDbpDsFixupCallback(char *a1)
{
  char v2; // r13
  unsigned int v3; // r15d
  _BYTE *v4; // rsi
  int *v5; // r14
  unsigned __int8 v6; // dl
  __int64 v7; // r8
  bool v8; // bp
  unsigned int inited; // eax
  NTSTATUS v10; // ebx
  char v11; // r12
  int v12; // eax
  unsigned int v13; // edx
  unsigned int TrustedDomainInfo; // eax
  _QWORD *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  NTSTATUS v18; // esi
  __int64 v19; // rdx
  unsigned int v20; // eax
  void *v21; // rcx
  int inserted; // ebx
  __int64 v23; // rcx
  unsigned int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v34; // [rsp+30h] [rbp-E8h]
  _BYTE v35[64]; // [rsp+50h] [rbp-C8h] BYREF
  unsigned int v36; // [rsp+90h] [rbp-88h]
  char v37; // [rsp+120h] [rbp+8h] BYREF

  memset_0(v35, 0, 0x78u);
  v2 = 0;
  v37 = 0;
  v3 = 0;
  v4 = WPP_GLOBAL_Control;
  v5 = (int *)(a1 + 40);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_DDSDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      -(int)*((_QWORD *)a1 + 4),
      (unsigned __int8)a1[49],
      *((_DWORD *)a1 + 5),
      *((_DWORD *)a1 + 4),
      (*((_QWORD *)a1 + 4) + 56LL) & -(__int64)(*((_QWORD *)a1 + 4) != 0),
      *v5,
      *((_DWORD *)a1 + 11),
      a1[48],
      a1[49]);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *v5 == 655388 )
  {
    v3 = 4;
  }
  else if ( *v5 == 655394 )
  {
    v3 = 2;
  }
  memset_0(v35, 0, 0x78u);
  v8 = *v5 != 655394 && *v5 != 196619;
  if ( !v3 )
  {
    v10 = 0;
    v11 = 0;
LABEL_17:
    v12 = *v5;
    if ( *v5 == dword_180047D04 )
    {
      v13 = 0x2000;
      if ( *((_DWORD *)a1 + 11) != 3 )
        v13 = 0;
      TrustedDomainInfo = LsaDbpDsGetTrustedDomainInfoEx(
                            *((struct _DSNAME **)a1 + 4),
                            v13,
                            TrustedDomainFullInformation2Internal,
                            (union _LSAPR_TRUSTED_DOMAIN_INFO *)v35,
                            0);
      v10 = TrustedDomainInfo;
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
          TrustedDomainInfo);
        v15 = WPP_GLOBAL_Control;
      }
      if ( v10 >= 0 )
      {
        v8 = 1;
        LOBYTE(v34) = a1[48];
        v16 = LsaDbpDsFixupTrustByInfo(
                *((_QWORD *)a1 + 4),
                (__int64)v35,
                v36,
                *((_DWORD *)a1 + 11),
                *((void **)a1 + 3),
                *(struct _LUID *)(a1 + 16),
                v34,
                a1[49]);
        v10 = v16;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v16);
        if ( a1[48] )
        {
          v17 = LsaDbpNotifyNetlogonOfTrustChange(0, *((unsigned int *)a1 + 11));
          v18 = v17;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v17);
          if ( v10 >= 0 )
            v10 = v18;
        }
        goto LABEL_60;
      }
      if ( v10 == -1073741772 )
      {
        if ( *((_DWORD *)a1 + 11) == 3 )
        {
LABEL_28:
          if ( (*((_BYTE *)v15 + 28) & 4) != 0 )
            WPP_SF_(v15[2], 38, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
          v8 = 1;
          goto LABEL_60;
        }
        if ( *((_DWORD *)a1 + 11) == 7
          && DsIsMangledDnW(
               (LPCWSTR)((*((_QWORD *)a1 + 4) + 56LL) & -(__int64)(*((_QWORD *)a1 + 4) != 0)),
               DS_MANGLE_OBJECT_RDN_FOR_DELETION) )
        {
          v15 = WPP_GLOBAL_Control;
          goto LABEL_28;
        }
      }
LABEL_60:
      if ( v11 )
      {
        LOBYTE(v7) = v2;
        LsaDbpDsDeleteAllocAsNeededEx2(0, v3, v7, (unsigned int)v10 >> 31);
      }
      goto LABEL_62;
    }
    if ( v12 == dword_180047D08 )
    {
      if ( (v4[28] & 4) == 0 )
        goto LABEL_60;
      v19 = 41;
    }
    else
    {
      if ( v12 == (_DWORD)LsaDbpDsClassIds )
      {
        v20 = LsaDbpDsFixupTrustForXrefChange(*((struct _DSNAME **)a1 + 4), v6);
        v21 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v20);
        inserted = LsapDbExpAcquireWriteLockTrustedDomainList(v21);
        if ( inserted >= 0 )
        {
          inserted = LsaDbpForestTrustInsertLocalInfo();
          if ( inserted < 0 )
            LsaDbpPurgeTrustedDomainCache();
          LsapDbExpReleaseLockTrustedDomainList(v23);
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
            (unsigned int)inserted);
        v8 = 1;
        if ( LsaDbpKerberosTrustNotificationFunction )
        {
          LsaIRegisterNotification(LsaDbpKerberosTrustNotificationFunction, *((int *)a1 + 11), 16);
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
        }
        v24 = I_NetNotifyDsChange(3);
        v10 = v24;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, v24);
        goto LABEL_60;
      }
      if ( v12 != 655369 )
      {
        v10 = -1073741811;
        goto LABEL_60;
      }
      if ( (v4[28] & 4) == 0 )
        goto LABEL_60;
      v19 = 46;
    }
    WPP_SF_(*((_QWORD *)v4 + 2), v19, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    goto LABEL_60;
  }
  inited = LsaDbpDsInitAllocAsNeededEx(0, v3, &v37);
  v10 = inited;
  v4 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids, inited);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v10 >= 0 )
  {
    v2 = v37;
    v5 = (int *)(a1 + 40);
    v11 = 1;
    goto LABEL_17;
  }
LABEL_62:
  _fgu__LSAPR_TRUSTED_DOMAIN_INFO(v35, 12);
  LsapFreeLsaHeap(*((_QWORD *)a1 + 3), v25, v26);
  LsapFreeLsaHeap(*((_QWORD *)a1 + 4), v27, v28);
  LsapFreeLsaHeap(a1, v29, v30);
  if ( !v8 && (int)LsapDbExpAcquireWriteLockTrustedDomainList(v31) >= 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
    LsapDbExpMakeCacheInvalid(2);
    LsapDbExpReleaseLockTrustedDomainList(v32);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
      (unsigned int)v10);
  return RtlNtStatusToDosError(v10);
}

```

## disassembly

```asm
0x1800136d4  push    rbx
0x1800136d6  push    rbp
0x1800136d7  push    rsi
0x1800136d8  push    rdi
0x1800136d9  push    r12
0x1800136db  push    r13
0x1800136dd  push    r14
0x1800136df  push    r15
0x1800136e1  sub     rsp, 0D8h
0x1800136e8  mov     rdi, rcx
0x1800136eb  mov     ebx, 78h ; 'x'
0x1800136f0  mov     r8d, ebx; Size
0x1800136f3  lea     rcx, [rsp+118h+var_C8]; void *
0x1800136f8  xor     edx, edx; Val
0x1800136fa  call    memset_0
0x1800136ff  xor     r13b, r13b
0x180013702  mov     [rsp+118h+arg_0], r13b
0x18001370a  xor     r15d, r15d
0x18001370d  mov     rsi, cs:WPP_GLOBAL_Control
0x180013714  lea     r14, [rdi+28h]
0x180013718  test    byte ptr [rsi+1Ch], 4
0x18001371c  jz      short loc_180013771
0x18001371e  mov     rdx, [rdi+20h]
0x180013722  movzx   r9d, byte ptr [rdi+30h]
0x180013727  movzx   r8d, byte ptr [rdi+31h]
0x18001372c  mov     rcx, [rsi+10h]
0x180013730  mov     [rsp+118h+var_D0], r8d
0x180013735  lea     rax, [rdx+38h]
0x180013739  mov     [rsp+118h+var_D8], r9d
0x18001373e  neg     rdx
0x180013741  mov     r9d, [rdi+14h]
0x180013745  sbb     r10, r10
0x180013748  and     r10, rax
0x18001374b  mov     eax, [rdi+2Ch]
0x18001374e  mov     [rsp+118h+var_E0], eax
0x180013752  mov     eax, [r14]
0x180013755  mov     dword ptr [rsp+118h+var_E8], eax
0x180013759  mov     eax, [rdi+10h]
0x18001375c  mov     [rsp+118h+var_F0], r10
0x180013761  mov     dword ptr [rsp+118h+var_F8], eax
0x180013765  call    WPP_SF_DDSDDDD
0x18001376a  mov     rsi, cs:WPP_GLOBAL_Control
0x180013771  mov     eax, [r14]
0x180013774  sub     eax, 0A001Ch
0x180013779  jz      short loc_180013786
0x18001377b  cmp     eax, 6
0x18001377e  jnz     short loc_18001378C
0x180013780  lea     r15d, [rax-4]
0x180013784  jmp     short loc_18001378C
0x180013786  mov     r15d, 4
0x18001378c  mov     r8, rbx; Size
0x18001378f  lea     rcx, [rsp+118h+var_C8]; void *
0x180013794  xor     edx, edx; Val
0x180013796  call    memset_0
0x18001379b  cmp     dword ptr [r14], 0A0022h
0x1800137a2  jz      short loc_1800137B2
0x1800137a4  cmp     dword ptr [r14], 3000Bh
0x1800137ab  jz      short loc_1800137B2
0x1800137ad  mov     bpl, 1
0x1800137b0  jmp     short loc_1800137B5
0x1800137b2  xor     bpl, bpl
0x1800137b5  test    r15d, r15d
0x1800137b8  jz      short loc_180013813
0x1800137ba  lea     r8, [rsp+118h+arg_0]
0x1800137c2  mov     edx, r15d
0x1800137c5  xor     ecx, ecx
0x1800137c7  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x1800137cc  mov     ebx, eax
0x1800137ce  mov     rsi, cs:WPP_GLOBAL_Control
0x1800137d5  test    byte ptr [rsi+1Ch], 4
0x1800137d9  jz      short loc_1800137FA
0x1800137db  mov     rcx, [rsi+10h]
0x1800137df  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x1800137e6  mov     edx, 24h ; '$'
0x1800137eb  mov     r9d, eax
0x1800137ee  call    WPP_SF_d
0x1800137f3  mov     rsi, cs:WPP_GLOBAL_Control
0x1800137fa  test    ebx, ebx
0x1800137fc  js      loc_180013B04
0x180013802  mov     r13b, [rsp+118h+arg_0]
0x18001380a  lea     r14, [rdi+28h]
0x18001380e  mov     r12b, 1
0x180013811  jmp     short loc_180013818
0x180013813  xor     ebx, ebx
0x180013815  xor     r12b, r12b
0x180013818  mov     eax, [r14]
0x18001381b  cmp     eax, cs:dword_180047D04
0x180013821  jnz     loc_180013996
0x180013827  mov     rcx, [rdi+20h]; struct _DSNAME *
0x18001382b  lea     r9, [rsp+118h+var_C8]; union _LSAPR_TRUSTED_DOMAIN_INFO *
0x180013830  xor     eax, eax
0x180013832  mov     edx, 2000h
0x180013837  cmp     dword ptr [rdi+2Ch], 3
0x18001383b  mov     [rsp+118h+var_F8], rax; unsigned int *
0x180013840  cmovnz  edx, eax; unsigned int
0x180013843  lea     r8d, [rax+0Ch]; enum _TRUSTED_INFORMATION_CLASS
0x180013847  call    ?LsaDbpDsGetTrustedDomainInfoEx@@YAJPEAU_DSNAME@@KW4_TRUSTED_INFORMATION_CLASS@@PEAT_LSAPR_TRUSTED_DOMAIN_INFO@@PEAK@Z; LsaDbpDsGetTrustedDomainInfoEx(_DSNAME *,ulong,_TRUSTED_INFORMATION_CLASS,_LSAPR_TRUSTED_DOMAIN_INFO *,ulong *)
0x18001384c  mov     ebx, eax
0x18001384e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013855  test    byte ptr [rcx+1Ch], 4
0x180013859  jz      short loc_18001387A
0x18001385b  mov     rcx, [rcx+10h]
0x18001385f  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013866  mov     edx, 25h ; '%'
0x18001386b  mov     r9d, eax
0x18001386e  call    WPP_SF_d
0x180013873  mov     rcx, cs:WPP_GLOBAL_Control
0x18001387a  test    ebx, ebx
0x18001387c  jns     short loc_1800138E8
0x18001387e  cmp     ebx, 0C0000034h
0x180013884  jnz     loc_180013AEB
0x18001388a  cmp     dword ptr [rdi+2Ch], 3
0x18001388e  jz      short loc_1800138C5
0x180013890  cmp     dword ptr [rdi+2Ch], 7
0x180013894  jnz     loc_180013AEB
0x18001389a  mov     rax, [rdi+20h]
0x18001389e  lea     rdx, [rax+38h]
0x1800138a2  neg     rax
0x1800138a5  sbb     rcx, rcx
0x1800138a8  and     rcx, rdx; pszDn
0x1800138ab  mov     edx, 1; eDsMangleFor
0x1800138b0  call    cs:__imp_DsIsMangledDnW
0x1800138b6  test    eax, eax
0x1800138b8  jz      loc_180013AEB
0x1800138be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800138c5  test    byte ptr [rcx+1Ch], 4
0x1800138c9  jz      short loc_1800138E0
0x1800138cb  mov     rcx, [rcx+10h]
0x1800138cf  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x1800138d6  mov     edx, 26h ; '&'
0x1800138db  call    WPP_SF_
0x1800138e0  mov     bpl, 1
0x1800138e3  jmp     loc_180013AEB
0x1800138e8  mov     al, [rdi+31h]
0x1800138eb  lea     rdx, [rsp+118h+var_C8]
0x1800138f0  mov     r9d, [rdi+2Ch]
0x1800138f4  mov     bpl, 1
0x1800138f7  mov     r8d, [rsp+118h+var_88]
0x1800138ff  mov     rcx, [rdi+20h]
0x180013903  mov     byte ptr [rsp+118h+var_E0], al
0x180013907  mov     al, [rdi+30h]
0x18001390a  mov     byte ptr [rsp+118h+var_E8], al
0x18001390e  mov     rax, [rdi+10h]
0x180013912  mov     [rsp+118h+var_F0], rax
0x180013917  mov     rax, [rdi+18h]
0x18001391b  mov     [rsp+118h+var_F8], rax
0x180013920  call    ?LsaDbpDsFixupTrustByInfo@@YAJPEAU_DSNAME@@PEAU_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2@@KW4_SECURITY_DB_DELTA_TYPE@@PEAXU_LUID@@EE@Z; LsaDbpDsFixupTrustByInfo(_DSNAME *,_LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *,ulong,_SECURITY_DB_DELTA_TYPE,void *,_LUID,uchar,uchar)
0x180013925  mov     ebx, eax
0x180013927  mov     rcx, cs:WPP_GLOBAL_Control
0x18001392e  test    byte ptr [rcx+1Ch], 4
0x180013932  jz      short loc_18001394C
0x180013934  mov     rcx, [rcx+10h]
0x180013938  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x18001393f  mov     edx, 27h ; '''
0x180013944  mov     r9d, eax
0x180013947  call    WPP_SF_d
0x18001394c  cmp     byte ptr [rdi+30h], 0
0x180013950  jz      loc_180013AEB
0x180013956  mov     edx, [rdi+2Ch]
0x180013959  xor     ecx, ecx
0x18001395b  call    ?LsaDbpNotifyNetlogonOfTrustChange@@YAJPEAXW4_SECURITY_DB_DELTA_TYPE@@@Z; LsaDbpNotifyNetlogonOfTrustChange(void *,_SECURITY_DB_DELTA_TYPE)
0x180013960  mov     esi, eax
0x180013962  mov     rcx, cs:WPP_GLOBAL_Control
0x180013969  test    byte ptr [rcx+1Ch], 4
0x18001396d  jz      short loc_180013987
0x18001396f  mov     rcx, [rcx+10h]
0x180013973  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x18001397a  mov     edx, 28h ; '('
0x18001397f  mov     r9d, eax
0x180013982  call    WPP_SF_d
0x180013987  test    ebx, ebx
0x180013989  js      loc_180013AEB
0x18001398f  mov     ebx, esi
0x180013991  jmp     loc_180013AEB
0x180013996  cmp     eax, cs:dword_180047D08
0x18001399c  jnz     short loc_1800139B2
0x18001399e  test    byte ptr [rsi+1Ch], 4
0x1800139a2  jz      loc_180013AEB
0x1800139a8  mov     edx, 29h ; ')'
0x1800139ad  jmp     loc_180013AD4
0x1800139b2  cmp     eax, cs:?LsaDbpDsClassIds@@3PAKA; ulong near * LsaDbpDsClassIds
0x1800139b8  jnz     loc_180013AC2
0x1800139be  mov     rcx, [rdi+20h]; struct _DSNAME *
0x1800139c2  call    ?LsaDbpDsFixupTrustForXrefChange@@YAJPEAU_DSNAME@@E@Z; LsaDbpDsFixupTrustForXrefChange(_DSNAME *,uchar)
0x1800139c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800139ce  test    byte ptr [rcx+1Ch], 4
0x1800139d2  jz      short loc_1800139EC
0x1800139d4  mov     rcx, [rcx+10h]
0x1800139d8  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x1800139df  mov     edx, 2Ah ; '*'
0x1800139e4  mov     r9d, eax
0x1800139e7  call    WPP_SF_d
0x1800139ec  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x1800139f2  mov     ebx, eax
0x1800139f4  test    eax, eax
0x1800139f6  js      short loc_180013A0E
0x1800139f8  call    ?LsaDbpForestTrustInsertLocalInfo@@YAJXZ; LsaDbpForestTrustInsertLocalInfo(void)
0x1800139fd  mov     ebx, eax
0x1800139ff  test    eax, eax
0x180013a01  jns     short loc_180013A08
0x180013a03  call    ?LsaDbpPurgeTrustedDomainCache@@YAXXZ; LsaDbpPurgeTrustedDomainCache(void)
0x180013a08  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180013a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a15  test    byte ptr [rcx+1Ch], 4
0x180013a19  jz      short loc_180013A33
0x180013a1b  mov     rcx, [rcx+10h]
0x180013a1f  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013a26  mov     edx, 2Bh ; '+'
0x180013a2b  mov     r9d, ebx
0x180013a2e  call    WPP_SF_d
0x180013a33  mov     rcx, cs:?LsaDbpKerberosTrustNotificationFunction@@3P6AXW4_SECURITY_DB_DELTA_TYPE@@@ZEA; void (*LsaDbpKerberosTrustNotificationFunction)(_SECURITY_DB_DELTA_TYPE)
0x180013a3a  mov     bpl, 1
0x180013a3d  test    rcx, rcx
0x180013a40  jz      short loc_180013A8E
0x180013a42  movsxd  rdx, dword ptr [rdi+2Ch]
0x180013a46  xor     r9d, r9d
0x180013a49  mov     [rsp+118h+var_E8], 0
0x180013a52  mov     dword ptr [rsp+118h+var_F0], 0
0x180013a5a  mov     dword ptr [rsp+118h+var_F8], 2
0x180013a62  lea     r8d, [r9+10h]
0x180013a66  call    cs:__imp_LsaIRegisterNotification
0x180013a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a73  test    byte ptr [rcx+1Ch], 4
0x180013a77  jz      short loc_180013A8E
0x180013a79  mov     rcx, [rcx+10h]
0x180013a7d  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013a84  mov     edx, 2Ch ; ','
0x180013a89  call    WPP_SF_
0x180013a8e  mov     ecx, 3
0x180013a93  call    cs:__imp_I_NetNotifyDsChange
0x180013a99  mov     ebx, eax
0x180013a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013aa2  test    byte ptr [rcx+1Ch], 4
0x180013aa6  jz      short loc_180013AEB
0x180013aa8  mov     rcx, [rcx+10h]
0x180013aac  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013ab3  mov     edx, 2Dh ; '-'
0x180013ab8  mov     r9d, eax
0x180013abb  call    WPP_SF_d
0x180013ac0  jmp     short loc_180013AEB
0x180013ac2  cmp     eax, 0A0009h
0x180013ac7  jnz     short loc_180013AE6
0x180013ac9  test    byte ptr [rsi+1Ch], 4
0x180013acd  jz      short loc_180013AEB
0x180013acf  mov     edx, 2Eh ; '.'
0x180013ad4  mov     rcx, [rsi+10h]
0x180013ad8  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013adf  call    WPP_SF_
0x180013ae4  jmp     short loc_180013AEB
0x180013ae6  mov     ebx, 0C000000Dh
0x180013aeb  test    r12b, r12b
0x180013aee  jz      short loc_180013B04
0x180013af0  mov     r9d, ebx
0x180013af3  mov     r8b, r13b
0x180013af6  shr     r9d, 1Fh
0x180013afa  mov     edx, r15d
0x180013afd  xor     ecx, ecx
0x180013aff  call    ?LsaDbpDsDeleteAllocAsNeededEx2@@YAXKW4_LSAP_DB_OBJECT_TYPE_ID@@EE@Z; LsaDbpDsDeleteAllocAsNeededEx2(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar,uchar)
0x180013b04  mov     edx, 0Ch
0x180013b09  lea     rcx, [rsp+118h+var_C8]
0x180013b0e  call    cs:__imp__fgu__LSAPR_TRUSTED_DOMAIN_INFO
0x180013b14  mov     rcx, [rdi+18h]
0x180013b18  call    cs:__imp_LsapFreeLsaHeap
0x180013b1e  mov     rcx, [rdi+20h]
0x180013b22  call    cs:__imp_LsapFreeLsaHeap
0x180013b28  mov     rcx, rdi
0x180013b2b  call    cs:__imp_LsapFreeLsaHeap
0x180013b31  test    bpl, bpl
0x180013b34  jnz     short loc_180013B73
0x180013b36  call    cs:__imp_LsapDbExpAcquireWriteLockTrustedDomainList
0x180013b3c  test    eax, eax
0x180013b3e  js      short loc_180013B73
0x180013b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b47  test    byte ptr [rcx+1Ch], 4
0x180013b4b  jz      short loc_180013B62
0x180013b4d  mov     rcx, [rcx+10h]
0x180013b51  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013b58  mov     edx, 2Fh ; '/'
0x180013b5d  call    WPP_SF_
0x180013b62  mov     ecx, 2
0x180013b67  call    cs:__imp_LsapDbExpMakeCacheInvalid
0x180013b6d  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180013b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b7a  test    byte ptr [rcx+1Ch], 4
0x180013b7e  jz      short loc_180013B98
0x180013b80  mov     rcx, [rcx+10h]
0x180013b84  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180013b8b  mov     edx, 30h ; '0'
0x180013b90  mov     r9d, ebx
0x180013b93  call    WPP_SF_d
0x180013b98  mov     ecx, ebx; Status
0x180013b9a  call    cs:__imp_RtlNtStatusToDosError
0x180013ba0  add     rsp, 0D8h
0x180013ba7  pop     r15
0x180013ba9  pop     r14
0x180013bab  pop     r13
0x180013bad  pop     r12
0x180013baf  pop     rdi
0x180013bb0  pop     rsi
0x180013bb1  pop     rbp
  ... truncated ...
```
