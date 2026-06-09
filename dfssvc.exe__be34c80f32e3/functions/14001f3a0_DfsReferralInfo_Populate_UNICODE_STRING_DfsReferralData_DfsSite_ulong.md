# DfsReferralInfo::Populate(_UNICODE_STRING *,DfsReferralData *,DfsSite *,ulong)

- ea: `0x14001f3a0`
- end: `0x14001fcd9`
- name: `?Populate@DfsReferralInfo@@QEAAKPEAU_UNICODE_STRING@@PEAVDfsReferralData@@PEAVDfsSite@@K@Z`
- size: `2361`
- prototype: `unsigned int __usercall@<eax>(DfsReferralInfo *__hidden this@<rcx>, struct _UNICODE_STRING *@<rdx>, struct DfsReferralData *@<r8>, struct DfsSite *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001c3b0`

## callees

- `0x140005c10`
- `0x14000fca8`
- `0x14001b7cc`
- `0x14001ef30`
- `0x14001efd8`
- `0x14001f3a0`
- `0x14001fce0`
- `0x14001fe7c`
- `0x140020148`
- `0x140020240`
- `0x14002039c`
- `0x140034508`
- `0x1400350f8`
- `0x140035788`

## import_xrefs

- `msvcrt!free` at `0x14001fc9e`
- `msvcrt!free` at `0x14001fcb7`
- `msvcrt!free` at `0x14001fc9e`
- `msvcrt!free` at `0x14001fcb7`
- `msvcrt!malloc` at `0x14001f6a0`
- `msvcrt!malloc` at `0x14001f6b5`
- `msvcrt!malloc` at `0x14001f6a0`
- `msvcrt!malloc` at `0x14001f6b5`
- `ntdll!EtwEventWrite` at `0x14001fc8a`
- `ntdll!EtwEventWrite` at `0x14001fc8a`
- `dfscli!I_NetDfsIsThisADomainName` at `0x14001f412`
- `dfscli!I_NetDfsIsThisADomainName` at `0x14001f412`

## pseudocode

```c
__int64 __fastcall DfsReferralInfo::Populate(
        DfsReferralInfo *this,
        struct _UNICODE_STRING *a2,
        struct DfsReferralData *a3,
        DfsSiteCostSupport **a4,
        unsigned int a5)
{
  unsigned int v5; // r12d
  unsigned int v9; // esi
  char v10; // bl
  __int64 v11; // rcx
  char v12; // al
  unsigned int *v13; // rsi
  unsigned int v14; // r11d
  unsigned int v15; // ecx
  unsigned int v16; // r10d
  __int64 i; // rax
  __int64 v18; // rbx
  unsigned int DsInterSiteCost; // eax
  unsigned int v20; // eax
  int v21; // r11d
  __int64 v22; // r8
  _QWORD *v23; // r14
  unsigned int v24; // eax
  const wchar_t *v25; // rcx
  char v26; // r8
  char v27; // bl
  int v28; // eax
  unsigned int v29; // edi
  void *v30; // rax
  char v31; // r11
  PWSTR Buffer; // rdx
  USHORT Length; // cx
  unsigned __int16 *v34; // rax
  int v35; // r9d
  __int64 v36; // r8
  unsigned int v37; // r9d
  unsigned __int16 *v38; // rdx
  unsigned __int16 *v39; // r8
  __int64 v40; // rcx
  const wchar_t *v41; // rax
  int v42; // ecx
  const wchar_t *v43; // rax
  char v44; // r8
  __int64 v45; // rcx
  int v46; // ecx
  unsigned int j; // edi
  __int64 v48; // rdx
  __int64 v49; // r9
  __int64 v50; // rcx
  unsigned __int16 *v51; // rax
  __int64 v52; // r9
  char v53; // r10
  __int64 v54; // r11
  __int64 v55; // r8
  __int64 v56; // r8
  const wchar_t *v57; // rdx
  __int64 v58; // r8
  char *v59; // r13
  unsigned __int16 *v60; // rax
  __int64 v61; // r8
  __int64 v62; // r9
  int v63; // r10d
  const wchar_t *v64; // r11
  struct DfsSiteCostCache *v65; // rax
  __int64 v66; // rdx
  const wchar_t *v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rcx
  unsigned __int16 v71; // cx
  __int64 v72; // r9
  unsigned __int16 v73; // r9
  int v74; // edx
  _WORD *v75; // r8
  int v76; // r9d
  struct DfsSiteCostCache *v77; // rax
  char *v78; // rcx
  __int64 v79; // rcx
  const wchar_t *v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rax
  int v84; // edx
  __int64 v85; // rcx
  _QWORD *v86; // rax
  const wchar_t *v87; // rdx
  __int64 v88; // rax
  int v89; // r8d
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // rcx
  char v95; // [rsp+50h] [rbp-68h]
  char v96; // [rsp+51h] [rbp-67h]
  unsigned int v97; // [rsp+54h] [rbp-64h]
  unsigned int v98; // [rsp+58h] [rbp-60h]
  unsigned int v99; // [rsp+5Ch] [rbp-5Ch] BYREF
  unsigned int v100; // [rsp+60h] [rbp-58h] BYREF
  struct DfsSiteCostCache *v101; // [rsp+68h] [rbp-50h] BYREF
  void *Block; // [rsp+70h] [rbp-48h]
  const wchar_t *v103; // [rsp+78h] [rbp-40h]
  char v104; // [rsp+C0h] [rbp+8h]
  __int16 v106; // [rsp+D0h] [rbp+18h] BYREF

  v5 = a5;
  v99 = 0;
  LOBYTE(v106) = 0;
  v100 = 0;
  v9 = a5;
  v10 = 0;
  v95 = 0;
  v96 = 0;
  v104 = 0;
  Block = 0;
  if ( !*((_BYTE *)a3 + 66)
    || *((_DWORD *)a3 + 10) != 1
    || (v11 = *((_QWORD *)a3 + 6), (*(_DWORD *)(v11 + 40) & 3) != 2)
    || (unsigned int)I_NetDfsIsThisADomainName(*(_QWORD *)(*(_QWORD *)(v11 + 16) + 32LL)) )
  {
    v12 = *((_BYTE *)a3 + 64);
    v5 = 0;
    v10 = *((_BYTE *)a3 + 65);
    v95 = v10;
    v96 = v12 != 0;
    if ( !v12 )
      v5 = v9;
  }
  v13 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && *((char *)pWppControl + 28) < 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_Z(*((_QWORD *)pWppControl + 2), 14, WPP_35d7de7cbef136511440bb1a25f1e49d_Traceguids, a4 + 2);
    v13 = pWppControl;
  }
  v14 = 0;
  v101 = 0;
  if ( v10 )
  {
    DfsSiteCostSupport::Acquire(a4[4], &v101);
    v13 = pWppControl;
    v14 = 0;
  }
  do
  {
    v15 = v14;
    v97 = v14;
    v98 = v14;
    v16 = v14;
    LOBYTE(v103) = v14;
    for ( i = v14; ; i = (unsigned int)((_DWORD)v101 + 1) )
    {
      LODWORD(v101) = i;
      if ( (unsigned int)i >= *((_DWORD *)a3 + 10) )
        break;
      v18 = *((_QWORD *)a3 + 6) + 56 * i;
      if ( (*(_DWORD *)(v18 + 40) & 3) != 2 )
        continue;
      if ( v95 == (_BYTE)v14 || (_BYTE)v103 )
      {
        DfsSite::GetDefaultSiteCost((DfsSite *)a4, *(struct DfsSite **)(*(_QWORD *)(v18 + 16) + 40LL), &v99);
      }
      else
      {
        DsInterSiteCost = DfsGetDsInterSiteCost(
                            (struct DfsSite *)a4,
                            a3,
                            (struct DfsReplica *)v18,
                            (unsigned __int8 *)&v106,
                            &v99);
        v14 = 0;
        LODWORD(v103) = DsInterSiteCost != 0;
        if ( (_BYTE)v106 )
        {
          v13 = pWppControl;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && pWppControl
            && *((char *)pWppControl + 28) < 0
            && *((_BYTE *)pWppControl + 25) >= 3u )
          {
            DfsSite::SiteNameString(*(DfsSite **)(*(_QWORD *)(v18 + 16) + 40LL));
            v20 = (unsigned int)DfsSite::SiteNameString((DfsSite *)a4);
            WPP_SF_SS(
              *((_QWORD *)v13 + 2),
              v21 + 15,
              (unsigned int)WPP_35d7de7cbef136511440bb1a25f1e49d_Traceguids,
              v20,
              v22);
            v13 = pWppControl;
            v14 = 0;
          }
          v16 = v97;
          v15 = v98;
          break;
        }
      }
      v13 = pWppControl;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && *((char *)pWppControl + 28) < 0
        && *((_BYTE *)pWppControl + 25) >= 3u )
      {
        DfsSite::SiteNameString(*(DfsSite **)(*(_QWORD *)(v18 + 16) + 40LL));
        v34 = DfsSite::SiteNameString((DfsSite *)a4);
        WPP_SF_ZSSddd(*((_QWORD *)v13 + 2), v99, v36, v35 + 24, (__int64)v34, v36, *(_WORD *)(v18 + 48), v99, v5);
        v13 = pWppControl;
      }
      if ( DfsIsGlobalPriorityClass(*(enum _DFS_TARGET_PRIORITY_CLASS *)(v18 + 44)) && v96 != (_BYTE)v14 )
      {
        v37 = v99;
      }
      else
      {
        v37 = v99;
        if ( v99 > v5 )
        {
          v16 = v97;
          v15 = v98;
          continue;
        }
      }
      v38 = (unsigned __int16 *)*((_QWORD *)this + 1);
      if ( !v38 )
        v38 = (unsigned __int16 *)(*(_QWORD *)(v18 + 16) + 24LL);
      v39 = (unsigned __int16 *)*((_QWORD *)this + 2);
      if ( !v39 )
        v39 = (unsigned __int16 *)(v18 + 24);
      v40 = 3LL * v97;
      *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v40 + 8) = v18;
      *(_DWORD *)(*((_QWORD *)this + 3) + 8 * v40) = v37;
      v15 = ((*v39 + 7 + *v38) & 0xFFFFFFFC) + v98;
      v16 = v97 + 1;
      v98 = v15;
      ++v97;
    }
  }
  while ( (_BYTE)v106 != (_BYTE)v14 );
  *(_DWORD *)this = v16;
  v23 = 0;
  *((_DWORD *)this + 1) = v15;
  if ( v95 )
  {
    DfsSiteCostSupport::Release(a4[4]);
    v13 = pWppControl;
  }
  if ( *(_DWORD *)this > 1u )
  {
    DfsReferralInfo::ShuffleReplicas(this);
    DfsReferralInfo::SortReplicas(this);
    DfsReferralInfo::SortPreferLogonDC(this);
    v13 = pWppControl;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && v13
    && *((char *)v13 + 28) < 0
    && *((_BYTE *)v13 + 25) >= 3u )
  {
    v24 = (unsigned int)DfsSite::SiteNameString((DfsSite *)a4);
    v25 = L"OFFLINE";
    if ( *((_BYTE *)a3 + 67) != v26 )
      v25 = L"ONLINE";
    WPP_SF_SS(
      *((_QWORD *)v13 + 2),
      17,
      (unsigned int)WPP_35d7de7cbef136511440bb1a25f1e49d_Traceguids,
      v24,
      (__int64)v25);
    v13 = pWppControl;
  }
  v27 = Microsoft_Windows_DFSN_ServerEnableBits;
  if ( (Microsoft_Windows_DFSN_ServerEnableBits & 0x10) == 0 )
  {
    v31 = 1;
LABEL_72:
    v44 = 0;
    goto LABEL_73;
  }
  v28 = *(_DWORD *)this;
  if ( *(_DWORD *)this > 0xDu )
    v28 = 13;
  v100 = v28;
  v29 = 9 * v28;
  v23 = malloc(16LL * (unsigned int)(9 * v28 + 4));
  v30 = malloc((unsigned __int64)v29 << 6);
  Block = v30;
  v31 = 1;
  if ( !v23 || !v30 )
    goto LABEL_72;
  v104 = 1;
  Buffer = a2->Buffer;
  if ( Buffer )
    Length = a2->Length;
  else
    Length = 10;
  *v23 = &v106;
  v41 = L"NULL";
  v23[1] = 2;
  v42 = Length >> 1;
  v106 = v42;
  *((_DWORD *)v23 + 6) = 2 * v42;
  *((_DWORD *)v23 + 7) = 0;
  if ( Buffer )
    v41 = Buffer;
  v23[2] = v41;
  v43 = DfsSite::SiteNameString((DfsSite *)a4);
  if ( v43 )
  {
    v45 = -1;
    do
      ++v45;
    while ( v43[v45] );
    v46 = 2 * v45 + 2;
  }
  else
  {
    v46 = 10;
    v43 = L"NULL";
  }
  v23[4] = v43;
  *((_DWORD *)v23 + 10) = v46;
  *((_DWORD *)v23 + 11) = 0;
  v23[6] = &v100;
  v23[7] = 4;
LABEL_73:
  for ( j = 0; j < *(_DWORD *)this; ++j )
  {
    if ( j )
    {
      v48 = *((_QWORD *)this + 3);
      v49 = *(_QWORD *)(v48 + 24LL * j + 8);
      v50 = *(_QWORD *)(v48 + 24LL * (j - 1) + 8);
      if ( *(_DWORD *)(v49 + 44) != *(_DWORD *)(v50 + 44)
        || *(_WORD *)(v49 + 48) != *(_WORD *)(v50 + 48)
        || *(_DWORD *)(v48 + 24LL * j) != *(_DWORD *)(v48 + 24LL * (j - 1)) )
      {
        *(_BYTE *)(v48 + 24LL * j + 16) = v31;
        v27 = Microsoft_Windows_DFSN_ServerEnableBits;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && v13
      && *((char *)v13 + 28) < 0
      && *((_BYTE *)v13 + 25) >= 3u )
    {
      v51 = DfsSite::SiteNameString(*(DfsSite **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 24LL * j + 8) + 16LL)
                                                + 40LL));
      v56 = v55 + 24;
      v57 = L"====";
      if ( !*(_BYTE *)(v54 + 24LL * j + 16) )
        v57 = L"    ";
      WPP_SF_dSZSddS(
        *((_QWORD *)v13 + 2),
        (_DWORD)v57,
        v56,
        j,
        (__int64)v57,
        v56,
        (__int64)v51,
        *(_DWORD *)(v54 + 24LL * j),
        v53,
        (__int64)(&DfsTargetPriorityClassNameArray)[v52]);
      v13 = pWppControl;
      v27 = Microsoft_Windows_DFSN_ServerEnableBits;
    }
    v44 = v104;
    if ( (v27 & 0x10) != 0 && v104 && j < v100 )
    {
      v58 = *((_QWORD *)this + 3);
      v59 = (char *)Block + 64 * (unsigned __int64)j;
      *((_DWORD *)v59 + 12) = *(_DWORD *)(v58 + 24LL * j);
      *((_DWORD *)v59 + 13) = *(unsigned __int16 *)(*(_QWORD *)(v58 + 24LL * j + 8) + 48LL);
      *((_DWORD *)v59 + 14) = *(_BYTE *)(v58 + 24LL * j + 16) != 0;
      v60 = DfsSite::SiteNameString(*(DfsSite **)(*(_QWORD *)(*(_QWORD *)(v58 + 24LL * j + 8) + 16LL) + 40LL));
      *((_QWORD *)v59 + 4) = v60;
      v64 = v60;
      v65 = (struct DfsSiteCostCache *)L"NULL";
      *((_QWORD *)v59 + 5) = (&DfsTargetPriorityClassNameArray)[*(unsigned int *)(*(_QWORD *)(v61 + 8 * v62 + 8) + 44LL)];
      v66 = *(_QWORD *)(*(_QWORD *)(v61 + 8 * v62 + 8) + 16LL);
      v67 = L"NULL";
      if ( *(_QWORD *)(v66 + 32) )
        v65 = *(struct DfsSiteCostCache **)(v66 + 32);
      *((_QWORD *)v59 + 1) = v65;
      v101 = v65;
      v68 = *(_QWORD *)(v61 + 8 * v62 + 8);
      if ( *(_QWORD *)(v68 + 32) )
        v67 = *(const wchar_t **)(v68 + 32);
      *((_QWORD *)v59 + 3) = v67;
      v69 = *(_QWORD *)(v61 + 8 * v62 + 8);
      v103 = v67;
      v70 = *(_QWORD *)(v69 + 16);
      if ( *(_QWORD *)(v70 + 32) )
        v71 = *(_WORD *)(v70 + 24);
      else
        v71 = 10;
      *(_WORD *)v59 = v71;
      v72 = *(_QWORD *)(v61 + 8 * v62 + 8);
      if ( *(_QWORD *)(v72 + 32) )
        v73 = *(_WORD *)(v72 + 24);
      else
        v73 = 10;
      v74 = v71 >> 1;
      v75 = (char *)Block + 64 * (unsigned __int64)j + 16;
      v76 = v73 >> 1;
      *((_WORD *)Block + 32 * (unsigned __int64)j) = v74;
      v77 = v101;
      v78 = (char *)&v23[2 * (unsigned int)(v63 + 4)];
      *v75 = v76;
      *((_DWORD *)v78 + 3) = 0;
      *(_QWORD *)v78 = v59;
      *((_DWORD *)v78 + 2) = 2;
      v79 = 2LL * (unsigned int)(v63 + 5);
      LODWORD(v23[v79 + 1]) = 2 * v74;
      v23[v79] = v77;
      v80 = v103;
      HIDWORD(v23[v79 + 1]) = 0;
      v81 = 2LL * (unsigned int)(v63 + 6);
      v23[v81] = v75;
      v23[v81 + 1] = 2;
      v82 = 2LL * (unsigned int)(v63 + 7);
      v23[v82] = v80;
      v23[v82 + 1] = (unsigned int)(2 * v76);
      if ( v64 )
      {
        v83 = -1;
        do
          ++v83;
        while ( v64[v83] );
        v84 = 2 * v83 + 2;
      }
      else
      {
        v84 = 10;
        v64 = L"NULL";
      }
      v85 = 2LL * (unsigned int)(v63 + 8);
      HIDWORD(v23[v85 + 1]) = 0;
      v86 = Block;
      LODWORD(v23[v85 + 1]) = v84;
      v23[v85] = v64;
      v87 = (const wchar_t *)v86[8 * (unsigned __int64)j + 5];
      if ( v87 )
      {
        v88 = -1;
        do
          ++v88;
        while ( v87[v88] );
        v89 = 2 * v88 + 2;
      }
      else
      {
        v89 = 10;
        v87 = L"NULL";
      }
      v90 = 2LL * (unsigned int)(v63 + 9);
      LODWORD(v23[v90 + 1]) = v89;
      v44 = v104;
      v23[v90] = v87;
      HIDWORD(v23[v90 + 1]) = 0;
      v91 = 2LL * (unsigned int)(v63 + 10);
      v23[v91] = v59 + 48;
      v23[v91 + 1] = 4;
      v92 = 2LL * (unsigned int)(v63 + 11);
      v23[v92] = v59 + 52;
      v23[v92 + 1] = 4;
      v93 = 2LL * (unsigned int)(v63 + 12);
      v23[v93] = v59 + 56;
      v23[v93 + 1] = 4;
    }
    v31 = 1;
  }
  if ( v44 && (v27 & 0x10) != 0 )
    EtwEventWrite(ServiceCtrlGuid_Context, ReferralTargetInformation, v100 + 8 * v100 + 4, v23);
  if ( v23 )
    free(v23);
  if ( Block )
    free(Block);
  return 0;
}

```

## disassembly

```asm
0x14001f3a0  mov     rax, rsp
0x14001f3a3  mov     [rax+10h], rdx
0x14001f3a7  push    rbx
0x14001f3a8  push    rsi
0x14001f3a9  push    rdi
0x14001f3aa  push    r12
0x14001f3ac  push    r13
0x14001f3ae  push    r14
0x14001f3b0  push    r15
0x14001f3b2  sub     rsp, 80h
0x14001f3b9  mov     r12d, [rsp+0B8h+arg_20]
0x14001f3c1  xor     edx, edx
0x14001f3c3  mov     r13, r9
0x14001f3c6  mov     [rax-5Ch], edx
0x14001f3c9  mov     rdi, r8
0x14001f3cc  mov     [rax+18h], dl
0x14001f3cf  mov     r15, rcx
0x14001f3d2  mov     [rax-58h], edx
0x14001f3d5  lea     eax, [rdx+1]
0x14001f3d8  mov     esi, r12d
0x14001f3db  mov     bl, dl
0x14001f3dd  mov     [rsp+0B8h+var_68], dl
0x14001f3e1  mov     [rsp+0B8h+var_67], dl
0x14001f3e5  mov     [rsp+0B8h+arg_0], dl
0x14001f3ec  mov     [rsp+0B8h+Block], rdx
0x14001f3f1  cmp     [r8+42h], dl
0x14001f3f5  jz      short loc_14001F424
0x14001f3f7  cmp     [r8+28h], eax
0x14001f3fb  jnz     short loc_14001F424
0x14001f3fd  mov     rcx, [r8+30h]
0x14001f401  mov     eax, [rcx+28h]
0x14001f404  and     al, 3
0x14001f406  cmp     al, 2
0x14001f408  jnz     short loc_14001F424
0x14001f40a  mov     rcx, [rcx+10h]
0x14001f40e  mov     rcx, [rcx+20h]
0x14001f412  call    cs:__imp_I_NetDfsIsThisADomainName
0x14001f419  nop     dword ptr [rax+rax+00h]
0x14001f41e  xor     edx, edx
0x14001f420  test    eax, eax
0x14001f422  jz      short loc_14001F43E
0x14001f424  mov     al, [rdi+40h]
0x14001f427  mov     r12d, edx
0x14001f42a  mov     bl, [rdi+41h]
0x14001f42d  test    al, al
0x14001f42f  mov     [rsp+0B8h+var_68], bl
0x14001f433  setnz   [rsp+0B8h+var_67]
0x14001f438  test    al, al
0x14001f43a  cmovz   r12d, esi
0x14001f43e  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f445  lea     rax, WPP_GLOBAL_Control
0x14001f44c  cmp     cs:WPP_GLOBAL_Control, rax
0x14001f453  jz      short loc_14001F486
0x14001f455  test    rsi, rsi
0x14001f458  jz      short loc_14001F486
0x14001f45a  test    byte ptr [rsi+1Ch], 80h
0x14001f45e  jz      short loc_14001F486
0x14001f460  cmp     byte ptr [rsi+19h], 3
0x14001f464  jb      short loc_14001F486
0x14001f466  mov     rcx, [rsi+10h]
0x14001f46a  lea     r9, [r13+10h]
0x14001f46e  mov     edx, 0Eh
0x14001f473  lea     r8, WPP_35d7de7cbef136511440bb1a25f1e49d_Traceguids
0x14001f47a  call    WPP_SF_Z
0x14001f47f  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f486  xor     r11d, r11d
0x14001f489  mov     [rsp+0B8h+var_50], r11
0x14001f48e  test    bl, bl
0x14001f490  jz      short loc_14001F4AA
0x14001f492  mov     rcx, [r13+20h]; this
0x14001f496  lea     rdx, [rsp+0B8h+var_50]; struct DfsSiteCostCache **
0x14001f49b  call    ?Acquire@DfsSiteCostSupport@@QEAAKPEAPEAVDfsSiteCostCache@@@Z; DfsSiteCostSupport::Acquire(DfsSiteCostCache * *)
0x14001f4a0  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f4a7  xor     r11d, r11d
0x14001f4aa  lea     r14, WPP_GLOBAL_Control
0x14001f4b1  mov     ecx, r11d
0x14001f4b4  mov     [rsp+0B8h+var_64], r11d
0x14001f4b9  mov     [rsp+0B8h+var_60], ecx
0x14001f4bd  mov     r10d, r11d
0x14001f4c0  mov     byte ptr [rsp+0B8h+var_40], r11b
0x14001f4c5  mov     edx, 1
0x14001f4ca  mov     eax, r11d
0x14001f4cd  mov     dword ptr [rsp+0B8h+var_50], eax
0x14001f4d1  cmp     eax, [rdi+28h]
0x14001f4d4  jnb     loc_14001F5B1
0x14001f4da  imul    rbx, rax, 38h ; '8'
0x14001f4de  add     rbx, [rdi+30h]
0x14001f4e2  mov     eax, [rbx+28h]
0x14001f4e5  and     al, 3
0x14001f4e7  cmp     al, 2
0x14001f4e9  jnz     loc_14001F7B8
0x14001f4ef  cmp     [rsp+0B8h+var_68], r11b
0x14001f4f4  jz      loc_14001F706
0x14001f4fa  mov     esi, dword ptr [rsp+0B8h+var_40]
0x14001f4fe  test    sil, sil
0x14001f501  jnz     loc_14001F706
0x14001f507  lea     rax, [rsp+0B8h+var_5C]
0x14001f50c  mov     r8, rbx; struct DfsReplica *
0x14001f50f  lea     r9, [rsp+0B8h+arg_10]; unsigned __int8 *
0x14001f517  mov     [rsp+0B8h+var_98], rax; unsigned int *
0x14001f51c  mov     rdx, rdi; this
0x14001f51f  mov     rcx, r13; struct DfsSite *
0x14001f522  call    ?DfsGetDsInterSiteCost@@YAKPEAVDfsSite@@PEAVDfsReferralData@@PEAVDfsReplica@@PEAEPEAK@Z; DfsGetDsInterSiteCost(DfsSite *,DfsReferralData *,DfsReplica *,uchar *,ulong *)
0x14001f527  xor     r11d, r11d
0x14001f52a  movzx   esi, sil
0x14001f52e  test    eax, eax
0x14001f530  lea     eax, [r11+1]
0x14001f534  cmovnz  esi, eax
0x14001f537  mov     dword ptr [rsp+0B8h+var_40], esi
0x14001f53b  cmp     byte ptr [rsp+0B8h+arg_10], r11b
0x14001f543  jz      loc_14001F71E
0x14001f549  cmp     cs:WPP_GLOBAL_Control, r14
0x14001f550  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f557  jz      short loc_14001F5A8
0x14001f559  test    rsi, rsi
0x14001f55c  jz      short loc_14001F5A8
0x14001f55e  test    byte ptr [rsi+1Ch], 80h
0x14001f562  jz      short loc_14001F5A8
0x14001f564  cmp     byte ptr [rsi+19h], 3
0x14001f568  jb      short loc_14001F5A8
0x14001f56a  mov     rcx, [rbx+10h]
0x14001f56e  mov     rcx, [rcx+28h]; this
0x14001f572  call    ?SiteNameString@DfsSite@@QEAAQEAGXZ; DfsSite::SiteNameString(void)
0x14001f577  mov     rcx, r13; this
0x14001f57a  mov     r8, rax
0x14001f57d  call    ?SiteNameString@DfsSite@@QEAAQEAGXZ; DfsSite::SiteNameString(void)
0x14001f582  mov     rcx, [rsi+10h]
0x14001f586  lea     edx, [r11+0Fh]
0x14001f58a  mov     [rsp+0B8h+var_98], r8
0x14001f58f  mov     r9, rax
0x14001f592  lea     r8, WPP_35d7de7cbef136511440bb1a25f1e49d_Traceguids
0x14001f599  call    WPP_SF_SS
0x14001f59e  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f5a5  xor     r11d, r11d
0x14001f5a8  mov     r10d, [rsp+0B8h+var_64]
0x14001f5ad  mov     ecx, [rsp+0B8h+var_60]
0x14001f5b1  cmp     byte ptr [rsp+0B8h+arg_10], r11b
0x14001f5b9  jnz     loc_14001F4B1
0x14001f5bf  xor     r12d, r12d
0x14001f5c2  mov     [r15], r10d
0x14001f5c5  mov     r14d, r12d
0x14001f5c8  mov     [r15+4], ecx
0x14001f5cc  cmp     [rsp+0B8h+var_68], r12b
0x14001f5d1  jz      short loc_14001F5E3
0x14001f5d3  mov     rcx, [r13+20h]; this
0x14001f5d7  call    ?Release@DfsSiteCostSupport@@QEAAXXZ; DfsSiteCostSupport::Release(void)
0x14001f5dc  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f5e3  mov     r8d, 1
0x14001f5e9  cmp     [r15], r8d
0x14001f5ec  jbe     short loc_14001F613
0x14001f5ee  mov     rcx, r15; this
0x14001f5f1  call    ?ShuffleReplicas@DfsReferralInfo@@AEAAXXZ; DfsReferralInfo::ShuffleReplicas(void)
0x14001f5f6  mov     rcx, r15; this
0x14001f5f9  call    ?SortReplicas@DfsReferralInfo@@AEAAXXZ; DfsReferralInfo::SortReplicas(void)
0x14001f5fe  mov     rcx, r15; this
0x14001f601  call    ?SortPreferLogonDC@DfsReferralInfo@@AEAAXXZ; DfsReferralInfo::SortPreferLogonDC(void)
0x14001f606  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f60d  mov     r8d, 1
0x14001f613  lea     rax, WPP_GLOBAL_Control
0x14001f61a  cmp     cs:WPP_GLOBAL_Control, rax
0x14001f621  jz      short loc_14001F676
0x14001f623  test    rsi, rsi
0x14001f626  jz      short loc_14001F676
0x14001f628  test    byte ptr [rsi+1Ch], 80h
0x14001f62c  jz      short loc_14001F676
0x14001f62e  cmp     byte ptr [rsi+19h], 3
0x14001f632  jb      short loc_14001F676
0x14001f634  mov     rcx, r13; this
0x14001f637  call    ?SiteNameString@DfsSite@@QEAAQEAGXZ; DfsSite::SiteNameString(void)
0x14001f63c  cmp     [rdi+43h], r8b
0x14001f640  lea     rdx, aOnline; "ONLINE"
0x14001f647  lea     rcx, aOffline_0; "OFFLINE"
0x14001f64e  mov     r9, rax
0x14001f651  cmovnz  rcx, rdx
0x14001f655  lea     r8, WPP_35d7de7cbef136511440bb1a25f1e49d_Traceguids
0x14001f65c  mov     [rsp+0B8h+var_98], rcx
0x14001f661  mov     edx, 11h
0x14001f666  mov     rcx, [rsi+10h]
0x14001f66a  call    WPP_SF_SS
0x14001f66f  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f676  mov     ebx, cs:Microsoft_Windows_DFSN_ServerEnableBits
0x14001f67c  test    bl, 10h
0x14001f67f  jz      loc_14001F8B4
0x14001f685  mov     eax, [r15]
0x14001f688  mov     ecx, 0Dh
0x14001f68d  cmp     eax, ecx
0x14001f68f  cmova   eax, ecx
0x14001f692  mov     [rsp+0B8h+var_58], eax
0x14001f696  lea     edi, [rax+rax*8]
0x14001f699  lea     ecx, [rdi+4]
0x14001f69c  shl     rcx, 4; Size
0x14001f6a0  call    cs:__imp_malloc
0x14001f6a7  nop     dword ptr [rax+rax+00h]
0x14001f6ac  mov     ecx, edi
0x14001f6ae  mov     r14, rax
0x14001f6b1  shl     rcx, 6; Size
0x14001f6b5  call    cs:__imp_malloc
0x14001f6bc  nop     dword ptr [rax+rax+00h]
0x14001f6c1  mov     [rsp+0B8h+Block], rax
0x14001f6c6  mov     r11d, 1
0x14001f6cc  test    r14, r14
0x14001f6cf  jz      loc_14001F8BA
0x14001f6d5  test    rax, rax
0x14001f6d8  jz      loc_14001F8BA
0x14001f6de  mov     rax, [rsp+0B8h+arg_8]
0x14001f6e6  mov     r8b, r11b
0x14001f6e9  mov     [rsp+0B8h+arg_0], r11b
0x14001f6f1  mov     rdx, [rax+8]
0x14001f6f5  test    rdx, rdx
0x14001f6f8  jz      loc_14001F823
0x14001f6fe  movzx   ecx, word ptr [rax]
0x14001f701  jmp     loc_14001F828
0x14001f706  mov     rdx, [rbx+10h]
0x14001f70a  lea     r8, [rsp+0B8h+var_5C]; unsigned int *
0x14001f70f  mov     rcx, r13; this
0x14001f712  mov     rdx, [rdx+28h]; struct DfsSite *
0x14001f716  call    ?GetDefaultSiteCost@DfsSite@@QEAAXPEAV1@PEAK@Z; DfsSite::GetDefaultSiteCost(DfsSite *,ulong *)
0x14001f71b  xor     r11d, r11d
0x14001f71e  cmp     cs:WPP_GLOBAL_Control, r14
0x14001f725  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f72c  jz      short loc_14001F78D
0x14001f72e  test    rsi, rsi
0x14001f731  jz      short loc_14001F78D
0x14001f733  test    byte ptr [rsi+1Ch], 80h
0x14001f737  jz      short loc_14001F78D
0x14001f739  cmp     byte ptr [rsi+19h], 3
0x14001f73d  jb      short loc_14001F78D
0x14001f73f  mov     r9, [rbx+10h]
0x14001f743  mov     rcx, [r9+28h]; this
0x14001f747  call    ?SiteNameString@DfsSite@@QEAAQEAGXZ; DfsSite::SiteNameString(void)
0x14001f74c  mov     rcx, r13; this
0x14001f74f  mov     r8, rax
0x14001f752  call    ?SiteNameString@DfsSite@@QEAAQEAGXZ; DfsSite::SiteNameString(void)
0x14001f757  movzx   ecx, word ptr [rbx+30h]
0x14001f75b  add     r9, 18h
0x14001f75f  mov     edx, [rsp+0B8h+var_5C]
0x14001f763  mov     [rsp+0B8h+var_78], r12d
0x14001f768  mov     [rsp+0B8h+var_80], edx
0x14001f76c  mov     dword ptr [rsp+0B8h+var_88], ecx
0x14001f770  mov     rcx, [rsi+10h]
0x14001f774  mov     [rsp+0B8h+var_90], r8
0x14001f779  mov     [rsp+0B8h+var_98], rax
0x14001f77e  call    WPP_SF_ZSSddd
0x14001f783  mov     rsi, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001f78a  xor     r11d, r11d
0x14001f78d  mov     ecx, [rbx+2Ch]; enum _DFS_TARGET_PRIORITY_CLASS
0x14001f790  call    ?DfsIsGlobalPriorityClass@@YAEW4_DFS_TARGET_PRIORITY_CLASS@@@Z; DfsIsGlobalPriorityClass(_DFS_TARGET_PRIORITY_CLASS)
0x14001f795  test    al, al
0x14001f797  jz      short loc_14001F7A0
0x14001f799  cmp     [rsp+0B8h+var_67], r11b
0x14001f79e  jnz     short loc_14001F7C3
0x14001f7a0  mov     r9d, [rsp+0B8h+var_5C]
0x14001f7a5  cmp     r9d, r12d
0x14001f7a8  jbe     short loc_14001F7C8
0x14001f7aa  mov     r10d, [rsp+0B8h+var_64]
0x14001f7af  mov     ecx, [rsp+0B8h+var_60]
0x14001f7b3  mov     edx, 1
0x14001f7b8  mov     eax, dword ptr [rsp+0B8h+var_50]
0x14001f7bc  add     eax, edx
0x14001f7be  jmp     loc_14001F4CD
0x14001f7c3  mov     r9d, [rsp+0B8h+var_5C]
0x14001f7c8  mov     rdx, [r15+8]
0x14001f7cc  test    rdx, rdx
0x14001f7cf  jnz     short loc_14001F7D9
0x14001f7d1  mov     rdx, [rbx+10h]
0x14001f7d5  add     rdx, 18h
0x14001f7d9  mov     r8, [r15+10h]
0x14001f7dd  test    r8, r8
0x14001f7e0  jnz     short loc_14001F7E6
0x14001f7e2  lea     r8, [rbx+18h]
0x14001f7e6  mov     r10d, [rsp+0B8h+var_64]
0x14001f7eb  mov     rax, [r15+18h]
0x14001f7ef  lea     rcx, [r10+r10*2]
0x14001f7f3  mov     [rax+rcx*8+8], rbx
0x14001f7f8  mov     rax, [r15+18h]
0x14001f7fc  mov     [rax+rcx*8], r9d
0x14001f800  movzx   edx, word ptr [rdx]
0x14001f803  movzx   ecx, word ptr [r8]
0x14001f807  add     ecx, 7
0x14001f80a  add     edx, ecx
0x14001f80c  mov     ecx, [rsp+0B8h+var_60]
0x14001f810  and     edx, 0FFFFFFFCh
0x14001f813  add     ecx, edx
0x14001f815  inc     r10d
0x14001f818  mov     [rsp+0B8h+var_60], ecx
0x14001f81c  mov     [rsp+0B8h+var_64], r10d
0x14001f821  jmp     short loc_14001F7B3
0x14001f823  mov     ecx, 0Ah
0x14001f828  shr     cx, 1
0x14001f82b  lea     rax, [rsp+0B8h+arg_10]
0x14001f833  mov     [r14], rax
0x14001f836  lea     rax, aNull; "NULL"
0x14001f83d  mov     qword ptr [r14+8], 2
0x14001f845  movzx   ecx, cx
0x14001f848  mov     [rsp+0B8h+arg_10], cx
0x14001f850  add     ecx, ecx
0x14001f852  test    rdx, rdx
0x14001f855  mov     [r14+18h], ecx
0x14001f859  mov     rcx, r13; this
0x14001f85c  mov     [r14+1Ch], r12d
  ... truncated ...
```
