# LsaDbpDsFixupTrustForXrefChange(_DSNAME *,uchar)

- ea: `0x180014358`
- end: `0x180014a39`
- name: `?LsaDbpDsFixupTrustForXrefChange@@YAJPEAU_DSNAME@@E@Z`
- size: `1761`
- prototype: `__int64 __fastcall(struct _DSNAME *, unsigned __int8)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800136d4`

## callees

- `0x180001670`
- `0x18000b7c8`
- `0x18000fd18`
- `0x18000fd40`
- `0x180011f90`
- `0x180012254`
- `0x180012758`
- `0x18001287c`
- `0x180014358`
- `0x18001f574`
- `0x18001fbcc`
- `0x180020398`
- `0x18003ad30`

## import_xrefs

- `LSASRV!LsapAllocateLsaHeap` at `0x1800144bd`
- `LSASRV!LsapAllocateLsaHeap` at `0x180014500`
- `LSASRV!LsapAllocateLsaHeap` at `0x180014544`
- `LSASRV!LsapAllocateLsaHeap` at `0x1800144bd`
- `LSASRV!LsapAllocateLsaHeap` at `0x180014500`
- `LSASRV!LsapAllocateLsaHeap` at `0x180014544`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149a9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149b9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149c9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149d9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149e8`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149a9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149b9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149c9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149d9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800149e8`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x18001499b`
- `LSASRV!__imp_?SpmpEventWrite@@YAKPEBU_EVENT_DESCRIPTOR@@PEAGZZ` at `0x18001499b`
- `ntdll!RtlLengthSid` at `0x1800145a3`
- `ntdll!RtlLengthSid` at `0x1800145a3`

## pseudocode

```c
__int64 __fastcall LsaDbpDsFixupTrustForXrefChange(struct _DSNAME *a1)
{
  int v1; // edi
  PSID v3; // rsi
  char v4; // r12
  char v5; // r15
  struct _DSNAME *v6; // r14
  struct _DSNAME *v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  char v10; // bl
  __int64 v11; // r15
  char v12; // r13
  __int64 v13; // r12
  __int64 v14; // rsi
  __int64 v15; // rcx
  void *v16; // rax
  __int64 v17; // rcx
  WCHAR *v18; // rax
  void *LsaHeap; // rax
  struct _DSNAME *v20; // rdi
  int v21; // eax
  int v22; // r13d
  int v23; // eax
  int *v24; // rax
  int v25; // eax
  struct _UNICODE_STRING *v26; // r8
  char v28; // [rsp+30h] [rbp-D0h]
  char v29; // [rsp+31h] [rbp-CFh]
  int inited; // [rsp+34h] [rbp-CCh] BYREF
  char v31; // [rsp+38h] [rbp-C8h]
  char v32; // [rsp+39h] [rbp-C7h] BYREF
  char v33; // [rsp+3Ah] [rbp-C6h]
  int v34; // [rsp+3Ch] [rbp-C4h]
  int v35; // [rsp+40h] [rbp-C0h]
  unsigned int v36; // [rsp+44h] [rbp-BCh] BYREF
  struct _UNICODE_STRING v37; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v38; // [rsp+58h] [rbp-A8h]
  int v39; // [rsp+5Ch] [rbp-A4h]
  struct _DSNAME *v40; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h]
  __int128 v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h] BYREF
  struct _ATTRSIMPLE near **v44; // [rsp+88h] [rbp-78h]
  __int128 v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-60h]
  struct _DSNAME *v47; // [rsp+A8h] [rbp-58h]
  struct _UNICODE_STRING v48; // [rsp+B0h] [rbp-50h] BYREF
  int v49; // [rsp+C0h] [rbp-40h] BYREF
  struct _DSNAME *v50; // [rsp+C8h] [rbp-38h]
  ULONG v51; // [rsp+D0h] [rbp-30h] BYREF
  PSID v52; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING v53; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v54; // [rsp+F0h] [rbp-10h] BYREF
  PSID v55; // [rsp+100h] [rbp+0h]
  int **v56; // [rsp+108h] [rbp+8h]
  int v57; // [rsp+110h] [rbp+10h]
  int v58; // [rsp+114h] [rbp+14h]
  __int64 v59; // [rsp+118h] [rbp+18h]
  int *p_Length; // [rsp+120h] [rbp+20h]
  int v61; // [rsp+130h] [rbp+30h] BYREF
  unsigned int *v62; // [rsp+138h] [rbp+38h]
  int *v63; // [rsp+140h] [rbp+40h] BYREF
  struct _DSNAME *v64; // [rsp+148h] [rbp+48h]
  int Length; // [rsp+150h] [rbp+50h] BYREF
  PWSTR Buffer; // [rsp+158h] [rbp+58h]

  v47 = a1;
  HIDWORD(v43) = 0;
  LOBYTE(v1) = 0;
  Sid = 0;
  v34 = v1;
  v28 = 0;
  v45 = 0;
  v3 = 0;
  v29 = 0;
  v37 = 0;
  v4 = 0;
  v5 = 0;
  v42 = 0;
  inited = 0;
  v6 = 0;
  v40 = 0;
  v36 = 0;
  v38 = 0;
  v39 = 0;
  v35 = 0;
  v46 = 0;
  v32 = 0;
  v31 = 0;
  v33 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids);
  v37 = 0;
  v42 = 0;
  v48 = 0;
  inited = LsaDbpDsInitAllocAsNeededEx(0, 2, &v32);
  v10 = 1;
  if ( inited < 0 )
    goto LABEL_53;
  v31 = 1;
  v44 = &LsaDbpDsTrustedDomainFixupXRefAttributes;
  LODWORD(v43) = 3;
  inited = LsaDbpDsReadByDsName(a1, 0, (struct _ATTRBLOCKSIMPLE *)&v43, (struct _ATTRBLOCKSIMPLE *)&v45);
  if ( inited < 0 )
    goto LABEL_53;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( !(_DWORD)v45 )
  {
    v5 = 0;
    v4 = 0;
LABEL_53:
    v22 = 0;
    goto LABEL_54;
  }
  v14 = *((_QWORD *)&v45 + 1);
  do
  {
    switch ( *(_DWORD *)(v14 + 24 * v13) )
    {
      case 0x20010:
        v11 = *(_QWORD *)(*(_QWORD *)(v14 + 24 * v13 + 16) + 8LL);
        if ( *(_DWORD *)(v11 + 4) )
        {
          LsaHeap = (void *)LsapAllocateLsaHeap(*(unsigned int *)(v11 + 4));
          Sid = LsaHeap;
          if ( !LsaHeap )
          {
LABEL_28:
            inited = -1073741801;
            goto LABEL_64;
          }
          memcpy_0(LsaHeap, (const void *)(v11 + 24), *(unsigned int *)(v11 + 4));
        }
        v12 = 1;
        break;
      case 0x9001C:
        v17 = **(unsigned __int16 **)(v14 + 24 * v13 + 16);
        v37.Length = v17;
        v37.MaximumLength = v17;
        v18 = (WCHAR *)LsapAllocateLsaHeap(v17);
        v37.Buffer = v18;
        if ( !v18 )
          goto LABEL_28;
        memcpy_0(v18, *(const void **)(*(_QWORD *)(v14 + 24 * v13 + 16) + 8LL), v37.Length);
        v28 = 1;
        break;
      case 0x90057:
        v15 = **(unsigned __int16 **)(v14 + 24 * v13 + 16);
        LOWORD(v42) = v15;
        WORD1(v42) = v15;
        v16 = (void *)LsapAllocateLsaHeap(v15);
        *((_QWORD *)&v42 + 1) = v16;
        if ( !v16 )
          goto LABEL_28;
        memcpy_0(v16, *(const void **)(*(_QWORD *)(v14 + 24 * v13 + 16) + 8LL), (unsigned __int16)v42);
        v29 = 1;
        break;
    }
    v13 = (unsigned int)(v13 + 1);
  }
  while ( (unsigned int)v13 < (unsigned int)v45 );
  v3 = Sid;
  if ( v12 && *(_DWORD *)(v11 + 4) )
  {
    v20 = qword_180047050;
    v49 = *(_DWORD *)qword_180047050;
    v50 = qword_180047050;
    v51 = RtlLengthSid(Sid);
    v52 = v3;
    v63 = &v49;
    v61 = 590606;
    Buffer = (PWSTR)&v51;
    LODWORD(v62) = 1;
    LODWORD(v64) = 589945;
    Length = 1;
    v21 = LsaDbpDsSearchUnique(0, qword_180047010, (struct _ATTRSIMPLE *)&v61, 2u, &v40);
    v5 = v29;
    inited = v21;
    if ( v21 != -1073741772 )
      goto LABEL_24;
    if ( !v29 )
    {
LABEL_26:
      inited = 0;
      goto LABEL_27;
    }
    v61 = *(_DWORD *)v20;
    LODWORD(v63) = (unsigned __int16)v42;
    v64 = (struct _DSNAME *)*((_QWORD *)&v42 + 1);
    *(_QWORD *)&v54 = &v61;
    v56 = &v63;
    v62 = (unsigned int *)v20;
    *(_DWORD *)&v53.Length = 590606;
    LODWORD(v53.Buffer) = 1;
    DWORD2(v54) = 589957;
    LODWORD(v55) = 1;
    v21 = LsaDbpDsSearchUnique(0, qword_180047010, (struct _ATTRSIMPLE *)&v53, 2u, &v40);
    inited = v21;
LABEL_24:
    if ( v21 < 0 )
    {
      if ( v21 == -1073741772 )
        goto LABEL_26;
LABEL_27:
      v6 = v40;
      LOBYTE(v1) = v34;
      v4 = v28;
      v22 = v35;
      goto LABEL_54;
    }
    v6 = v40;
    v33 = 1;
    LODWORD(v43) = 11;
    v44 = &LsaDbpDsTrustedDomainFixupAttributes;
    v23 = LsaDbpDsReadByDsName(v40, 0, (struct _ATTRBLOCKSIMPLE *)&v43, (struct _ATTRBLOCKSIMPLE *)&v45);
    inited = v23;
    if ( v23 >= 0 )
    {
      v9 = 0;
      v22 = 0;
      if ( (_DWORD)v45 )
      {
        v8 = *((_QWORD *)&v45 + 1);
        do
        {
          v7 = (struct _DSNAME *)(3 * v9);
          switch ( *(_DWORD *)(*((_QWORD *)&v45 + 1) + 24 * v9) )
          {
            case 0x90084:
              v38 = **(_DWORD **)(*(_QWORD *)(*((_QWORD *)&v45 + 1) + 24 * v9 + 16) + 8LL);
              break;
            case 0x90088:
              v36 = **(_DWORD **)(*(_QWORD *)(*((_QWORD *)&v45 + 1) + 24 * v9 + 16) + 8LL);
              break;
            case 0x901D6:
              v39 = **(_DWORD **)(*(_QWORD *)(*((_QWORD *)&v45 + 1) + 24 * v9 + 16) + 8LL);
              break;
            case 0x906A6:
              v24 = *(int **)(*((_QWORD *)&v45 + 1) + 24 * v9 + 16);
              v22 = *v24;
              v46 = *((_QWORD *)v24 + 1);
              break;
          }
          v9 = (unsigned int)(v9 + 1);
        }
        while ( (unsigned int)v9 < (unsigned int)v45 );
      }
      v4 = v28;
      if ( (v36 & 1) == 0 )
        goto LABEL_51;
      if ( !v28 )
        goto LABEL_51;
      v62 = &v36;
      v64 = v47;
      v61 = 4;
      LODWORD(v63) = *(_DWORD *)v47;
      Length = v37.Length;
      Buffer = v37.Buffer;
      *(_QWORD *)&v54 = &v61;
      v56 = &v63;
      p_Length = &Length;
      v36 = v36 & 0xFFFFFFFC | 2;
      v44 = (struct _ATTRSIMPLE near **)&v53;
      *(_DWORD *)&v53.Length = 589960;
      LODWORD(v53.Buffer) = 1;
      DWORD2(v54) = 590296;
      LODWORD(v55) = 1;
      v57 = 589957;
      LODWORD(v59) = 1;
      v43 = 3;
      inited = LsaDbpDsWriteByDsName(v6, 0x43u, (struct _ATTRBLOCKSIMPLE *)&v43);
      if ( inited < 0 )
        goto LABEL_51;
      inited = LsaDbpDsTruncateNameToFitCN(&v37, &v48);
      if ( inited >= 0 )
      {
        v25 = LsaDbpDsRenameObject(v6, v7, v8, &v48);
        LOBYTE(v1) = v34;
        if ( v25 >= 0 )
          LOBYTE(v1) = 1;
        inited = v25;
      }
      else
      {
LABEL_51:
        LOBYTE(v1) = v34;
      }
    }
    else
    {
      LOBYTE(v1) = v34;
      v4 = v28;
      v22 = v35;
      if ( v23 == -1073741772 )
        inited = 0;
    }
  }
  else
  {
    LOBYTE(v1) = v34;
    v22 = 0;
    v5 = v29;
    v4 = v28;
  }
LABEL_54:
  if ( inited >= 0 && (_BYTE)v1 )
  {
    *(_QWORD *)&v53.Length = 0;
    v54 = 0;
    v53.Buffer = 0;
    if ( v4 )
      v53 = v37;
    if ( v5 )
      v54 = v42;
    v56 = (int **)__PAIR64__(v36, v38);
    v57 = v39;
    v59 = v46;
    v55 = v3;
    v58 = v22;
    LsaDbpFixupTrustedDomainListEntry(
      v3,
      (struct _LSAPR_UNICODE_STRING *)&v53,
      (struct _LSAPR_UNICODE_STRING *)&v54,
      (struct _LSAPR_TRUSTED_DOMAIN_INFORMATION_EX2 *)&v53,
      0);
  }
  if ( v31 )
  {
    if ( inited >= 0 )
      v10 = 0;
LABEL_64:
    LOBYTE(v8) = v32;
    LOBYTE(v9) = v10;
    LsaDbpDsDeleteAllocAsNeededEx2(0, 2, v8, v9);
  }
  if ( inited < 0 && v33 )
  {
    if ( v28 )
    {
      v26 = &v37;
    }
    else
    {
      if ( !v29 )
        goto LABEL_72;
      v26 = (struct _UNICODE_STRING *)&v42;
    }
    SpmpEventWrite((const struct _EVENT_DESCRIPTOR *)LSA_TRUST_UPGRADE_ERROR, L"ub", v26, 4, &inited);
  }
LABEL_72:
  if ( v6 )
    LsapFreeLsaHeap(v6, v7, v8);
  if ( v37.Buffer )
    LsapFreeLsaHeap(v37.Buffer, v7, v8);
  if ( *((_QWORD *)&v42 + 1) )
    LsapFreeLsaHeap(*((_QWORD *)&v42 + 1), v7, v8);
  if ( Sid )
    LsapFreeLsaHeap(Sid, v7, v8);
  if ( v48.Buffer )
    LsapFreeLsaHeap(v48.Buffer, v7, v8);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      &WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids,
      (unsigned int)inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180014358  push    rbp
0x18001435a  push    rbx
0x18001435b  push    rsi
0x18001435c  push    rdi
0x18001435d  push    r12
0x18001435f  push    r13
0x180014361  push    r14
0x180014363  push    r15
0x180014365  lea     rbp, [rsp-78h]
0x18001436a  sub     rsp, 178h
0x180014371  mov     rax, cs:__security_cookie
0x180014378  xor     rax, rsp
0x18001437b  mov     [rbp+0B0h+var_50], rax
0x18001437f  xor     eax, eax
0x180014381  mov     [rbp+0B0h+var_108], rcx
0x180014385  xorps   xmm0, xmm0
0x180014388  mov     dword ptr [rbp+0B0h+var_130+4], eax
0x18001438b  mov     dil, al
0x18001438e  mov     [rsp+1B0h+Sid], rax
0x180014393  xorps   xmm1, xmm1
0x180014396  mov     [rsp+1B0h+var_174], edi
0x18001439a  mov     r13, rcx
0x18001439d  mov     [rsp+1B0h+var_180], al
0x1800143a1  movups  [rbp+0B0h+var_120], xmm0
0x1800143a5  mov     esi, eax
0x1800143a7  mov     [rsp+1B0h+var_17F], al
0x1800143ab  movups  xmmword ptr [rsp+1B0h+var_168.Length], xmm1
0x1800143b0  mov     r12b, al
0x1800143b3  mov     r15b, al
0x1800143b6  movups  [rsp+1B0h+var_140], xmm0
0x1800143bb  mov     [rsp+1B0h+var_17C], eax
0x1800143bf  mov     r14d, eax
0x1800143c2  mov     [rsp+1B0h+var_150], rax
0x1800143c7  mov     [rsp+1B0h+var_16C], eax
0x1800143cb  mov     [rsp+1B0h+var_158], eax
0x1800143cf  mov     [rsp+1B0h+var_154], eax
0x1800143d3  mov     [rsp+1B0h+var_170], eax
0x1800143d7  mov     [rbp+0B0h+var_110], rax
0x1800143db  mov     [rsp+1B0h+var_177], al
0x1800143df  mov     [rsp+1B0h+var_178], al
0x1800143e3  mov     [rsp+1B0h+var_176], al
0x1800143e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143ee  test    byte ptr [rcx+1Ch], 4
0x1800143f2  jz      short loc_180014407
0x1800143f4  mov     rcx, [rcx+10h]
0x1800143f8  lea     edx, [rax+14h]
0x1800143fb  lea     r8, WPP_2fe947218f0e3625c9220b7dbfff8490_Traceguids
0x180014402  call    WPP_SF_
0x180014407  xorps   xmm0, xmm0
0x18001440a  lea     r8, [rsp+1B0h+var_177]
0x18001440f  xorps   xmm1, xmm1
0x180014412  mov     edx, 2
0x180014417  xor     ecx, ecx
0x180014419  movups  xmmword ptr [rsp+1B0h+var_168.Length], xmm0
0x18001441e  movups  [rsp+1B0h+var_140], xmm1
0x180014423  movups  xmmword ptr [rbp+0B0h+var_100.Length], xmm0
0x180014427  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x18001442c  mov     [rsp+1B0h+var_17C], eax
0x180014430  mov     ebx, 1
0x180014435  test    eax, eax
0x180014437  js      loc_18001488A
0x18001443d  lea     rax, ?LsaDbpDsTrustedDomainFixupXRefAttributes@@3PAU_ATTRSIMPLE@@A; _ATTRSIMPLE near * LsaDbpDsTrustedDomainFixupXRefAttributes
0x180014444  mov     [rsp+1B0h+var_178], bl
0x180014448  lea     r9, [rbp+0B0h+var_120]; struct _ATTRBLOCKSIMPLE *
0x18001444c  mov     [rbp+0B0h+var_128], rax
0x180014450  lea     r8, [rbp+0B0h+var_130]; struct _ATTRBLOCKSIMPLE *
0x180014454  mov     dword ptr [rbp+0B0h+var_130], 3
0x18001445b  xor     edx, edx; unsigned int
0x18001445d  mov     rcx, r13; struct _DSNAME *
0x180014460  call    ?LsaDbpDsReadByDsName@@YAJPEAU_DSNAME@@KPEAU_ATTRBLOCKSIMPLE@@1@Z; LsaDbpDsReadByDsName(_DSNAME *,ulong,_ATTRBLOCKSIMPLE *,_ATTRBLOCKSIMPLE *)
0x180014465  mov     [rsp+1B0h+var_17C], eax
0x180014469  test    eax, eax
0x18001446b  js      loc_18001488A
0x180014471  xor     r15d, r15d
0x180014474  xor     r13b, r13b
0x180014477  xor     r12d, r12d
0x18001447a  cmp     dword ptr [rbp+0B0h+var_120], esi
0x18001447d  jbe     loc_180014884
0x180014483  mov     rsi, qword ptr [rbp+0B0h+var_120+8]
0x180014487  lea     rdi, [r12+r12*2]
0x18001448b  mov     ecx, [rsi+rdi*8]
0x18001448e  sub     ecx, 20010h
0x180014494  jz      loc_180014531
0x18001449a  sub     ecx, 7000Ch
0x1800144a0  jz      short loc_1800144EE
0x1800144a2  cmp     ecx, 3Bh ; ';'
0x1800144a5  jnz     loc_18001456B
0x1800144ab  mov     rax, [rsi+rdi*8+10h]
0x1800144b0  movzx   ecx, word ptr [rax]
0x1800144b3  mov     word ptr [rsp+1B0h+var_140], cx
0x1800144b8  mov     word ptr [rsp+1B0h+var_140+2], cx
0x1800144bd  call    cs:__imp_LsapAllocateLsaHeap
0x1800144c3  mov     qword ptr [rsp+1B0h+var_140+8], rax
0x1800144c8  test    rax, rax
0x1800144cb  jz      loc_18001469C
0x1800144d1  mov     rdx, [rsi+rdi*8+10h]
0x1800144d6  mov     rcx, rax; void *
0x1800144d9  movzx   r8d, word ptr [rsp+1B0h+var_140]; Size
0x1800144df  mov     rdx, [rdx+8]; Src
0x1800144e3  call    memcpy_0
0x1800144e8  mov     [rsp+1B0h+var_17F], bl
0x1800144ec  jmp     short loc_18001456B
0x1800144ee  mov     rax, [rsi+rdi*8+10h]
0x1800144f3  movzx   ecx, word ptr [rax]
0x1800144f6  mov     [rsp+1B0h+var_168.Length], cx
0x1800144fb  mov     [rsp+1B0h+var_168.MaximumLength], cx
0x180014500  call    cs:__imp_LsapAllocateLsaHeap
0x180014506  mov     [rsp+1B0h+var_168.Buffer], rax
0x18001450b  test    rax, rax
0x18001450e  jz      loc_18001469C
0x180014514  mov     rdx, [rsi+rdi*8+10h]
0x180014519  mov     rcx, rax; void *
0x18001451c  movzx   r8d, [rsp+1B0h+var_168.Length]; Size
0x180014522  mov     rdx, [rdx+8]; Src
0x180014526  call    memcpy_0
0x18001452b  mov     [rsp+1B0h+var_180], bl
0x18001452f  jmp     short loc_18001456B
0x180014531  mov     rax, [rsi+rdi*8+10h]
0x180014536  mov     r15, [rax+8]
0x18001453a  cmp     [r15+4], r14d
0x18001453e  jbe     short loc_180014568
0x180014540  mov     ecx, [r15+4]
0x180014544  call    cs:__imp_LsapAllocateLsaHeap
0x18001454a  mov     [rsp+1B0h+Sid], rax
0x18001454f  test    rax, rax
0x180014552  jz      loc_18001469C
0x180014558  mov     r8d, [r15+4]; Size
0x18001455c  lea     rdx, [r15+18h]; Src
0x180014560  mov     rcx, rax; void *
0x180014563  call    memcpy_0
0x180014568  mov     r13b, bl
0x18001456b  add     r12d, ebx
0x18001456e  cmp     r12d, dword ptr [rbp+0B0h+var_120]
0x180014572  jb      loc_180014487
0x180014578  mov     rsi, [rsp+1B0h+Sid]
0x18001457d  test    r13b, r13b
0x180014580  jz      loc_18001486B
0x180014586  cmp     [r15+4], r14d
0x18001458a  jbe     loc_18001486B
0x180014590  mov     rdi, cs:qword_180047050
0x180014597  mov     rcx, rsi; Sid
0x18001459a  mov     eax, [rdi]
0x18001459c  mov     [rbp+0B0h+var_F0], eax
0x18001459f  mov     [rbp+0B0h+var_E8], rdi
0x1800145a3  call    cs:__imp_RtlLengthSid
0x1800145a9  mov     rdx, cs:qword_180047010; struct _DSNAME *
0x1800145b0  lea     r8, [rbp+0B0h+var_80]; struct _ATTRSIMPLE *
0x1800145b4  mov     [rbp+0B0h+var_E0], eax
0x1800145b7  mov     r14d, 9030Eh
0x1800145bd  lea     rax, [rbp+0B0h+var_F0]
0x1800145c1  mov     [rbp+0B0h+var_D8], rsi
0x1800145c5  mov     [rbp+0B0h+var_70], rax
0x1800145c9  mov     r9d, 2; unsigned int
0x1800145cf  lea     rax, [rbp+0B0h+var_E0]
0x1800145d3  mov     [rbp+0B0h+var_80], r14d
0x1800145d7  mov     [rbp+0B0h+var_58], rax
0x1800145db  xor     ecx, ecx; unsigned int
0x1800145dd  lea     rax, [rsp+1B0h+var_150]
0x1800145e2  mov     dword ptr [rbp+0B0h+var_78], ebx
0x1800145e5  mov     [rsp+1B0h+var_190], rax; struct _DSNAME **
0x1800145ea  mov     dword ptr [rbp+0B0h+var_68], 90079h
0x1800145f1  mov     [rbp+0B0h+var_60], ebx
0x1800145f4  call    ?LsaDbpDsSearchUnique@@YAJKPEAU_DSNAME@@PEAU_ATTRSIMPLE@@KPEAPEAU1@@Z; LsaDbpDsSearchUnique(ulong,_DSNAME *,_ATTRSIMPLE *,ulong,_DSNAME * *)
0x1800145f9  mov     r15b, [rsp+1B0h+var_17F]
0x1800145fe  mov     r12d, 0C0000034h
0x180014604  mov     [rsp+1B0h+var_17C], eax
0x180014608  cmp     eax, r12d
0x18001460b  jnz     short loc_180014673
0x18001460d  test    r15b, r15b
0x180014610  jz      short loc_18001467C
0x180014612  mov     eax, [rdi]
0x180014614  lea     r8, [rbp+0B0h+var_D0]; struct _ATTRSIMPLE *
0x180014618  mov     rdx, cs:qword_180047010; struct _DSNAME *
0x18001461f  mov     r9d, 2; unsigned int
0x180014625  mov     [rbp+0B0h+var_80], eax
0x180014628  xor     ecx, ecx; unsigned int
0x18001462a  movzx   eax, word ptr [rsp+1B0h+var_140]
0x18001462f  mov     dword ptr [rbp+0B0h+var_70], eax
0x180014632  mov     rax, qword ptr [rsp+1B0h+var_140+8]
0x180014637  mov     [rbp+0B0h+var_68], rax
0x18001463b  lea     rax, [rbp+0B0h+var_80]
0x18001463f  mov     qword ptr [rbp+0B0h+var_C0], rax
0x180014643  lea     rax, [rbp+0B0h+var_70]
0x180014647  mov     [rbp+0B0h+var_A8], rax
0x18001464b  lea     rax, [rsp+1B0h+var_150]
0x180014650  mov     [rsp+1B0h+var_190], rax; struct _DSNAME **
0x180014655  mov     [rbp+0B0h+var_78], rdi
0x180014659  mov     dword ptr [rbp+0B0h+var_D0], r14d
0x18001465d  mov     dword ptr [rbp+0B0h+var_C8], ebx
0x180014660  mov     dword ptr [rbp+0B0h+var_C0+8], 90085h
0x180014667  mov     dword ptr [rbp+0B0h+var_B0], ebx
0x18001466a  call    ?LsaDbpDsSearchUnique@@YAJKPEAU_DSNAME@@PEAU_ATTRSIMPLE@@KPEAPEAU1@@Z; LsaDbpDsSearchUnique(ulong,_DSNAME *,_ATTRSIMPLE *,ulong,_DSNAME * *)
0x18001466f  mov     [rsp+1B0h+var_17C], eax
0x180014673  test    eax, eax
0x180014675  jns     short loc_1800146A9
0x180014677  cmp     eax, r12d
0x18001467a  jnz     short loc_180014684
0x18001467c  mov     [rsp+1B0h+var_17C], 0
0x180014684  mov     r14, [rsp+1B0h+var_150]
0x180014689  mov     edi, [rsp+1B0h+var_174]
0x18001468d  mov     r12b, [rsp+1B0h+var_180]
0x180014692  mov     r13d, [rsp+1B0h+var_170]
0x180014697  jmp     loc_18001488D
0x18001469c  mov     [rsp+1B0h+var_17C], 0C0000017h
0x1800146a4  jmp     loc_180014941
0x1800146a9  mov     r14, [rsp+1B0h+var_150]
0x1800146ae  lea     rax, ?LsaDbpDsTrustedDomainFixupAttributes@@3PAU_ATTRSIMPLE@@A; _ATTRSIMPLE near * LsaDbpDsTrustedDomainFixupAttributes
0x1800146b5  mov     rcx, r14; struct _DSNAME *
0x1800146b8  mov     [rsp+1B0h+var_176], bl
0x1800146bc  lea     r9, [rbp+0B0h+var_120]; struct _ATTRBLOCKSIMPLE *
0x1800146c0  mov     dword ptr [rbp+0B0h+var_130], 0Bh
0x1800146c7  lea     r8, [rbp+0B0h+var_130]; struct _ATTRBLOCKSIMPLE *
0x1800146cb  mov     [rbp+0B0h+var_128], rax
0x1800146cf  xor     edx, edx; unsigned int
0x1800146d1  call    ?LsaDbpDsReadByDsName@@YAJPEAU_DSNAME@@KPEAU_ATTRBLOCKSIMPLE@@1@Z; LsaDbpDsReadByDsName(_DSNAME *,ulong,_ATTRBLOCKSIMPLE *,_ATTRBLOCKSIMPLE *)
0x1800146d6  mov     [rsp+1B0h+var_17C], eax
0x1800146da  test    eax, eax
0x1800146dc  jns     short loc_180014702
0x1800146de  mov     edi, [rsp+1B0h+var_174]
0x1800146e2  cmp     eax, r12d
0x1800146e5  mov     r12b, [rsp+1B0h+var_180]
0x1800146ea  mov     r13d, [rsp+1B0h+var_170]
0x1800146ef  jnz     loc_18001488D
0x1800146f5  mov     [rsp+1B0h+var_17C], 0
0x1800146fd  jmp     loc_18001488D
0x180014702  mov     r10d, dword ptr [rbp+0B0h+var_120]
0x180014706  xor     r9d, r9d
0x180014709  mov     r13d, r9d
0x18001470c  test    r10d, r10d
0x18001470f  jz      short loc_180014785
0x180014711  mov     r8, qword ptr [rbp+0B0h+var_120+8]
0x180014715  lea     rdx, [r9+r9*2]
0x180014719  mov     ecx, [r8+rdx*8]
0x18001471d  sub     ecx, 90084h
0x180014723  jz      short loc_18001476E
0x180014725  sub     ecx, 4
0x180014728  jz      short loc_18001475D
0x18001472a  sub     ecx, 14Eh
0x180014730  jz      short loc_18001474C
0x180014732  cmp     ecx, 4D0h
0x180014738  jnz     short loc_18001477D
0x18001473a  mov     rax, [r8+rdx*8+10h]
0x18001473f  mov     r13d, [rax]
0x180014742  mov     rax, [rax+8]
0x180014746  mov     [rbp+0B0h+var_110], rax
0x18001474a  jmp     short loc_18001477D
0x18001474c  mov     rax, [r8+rdx*8+10h]
0x180014751  mov     rcx, [rax+8]
0x180014755  mov     eax, [rcx]
0x180014757  mov     [rsp+1B0h+var_154], eax
0x18001475b  jmp     short loc_18001477D
0x18001475d  mov     rax, [r8+rdx*8+10h]
0x180014762  mov     rcx, [rax+8]
0x180014766  mov     eax, [rcx]
0x180014768  mov     [rsp+1B0h+var_16C], eax
0x18001476c  jmp     short loc_18001477D
0x18001476e  mov     rax, [r8+rdx*8+10h]
0x180014773  mov     rcx, [rax+8]
0x180014777  mov     eax, [rcx]
0x180014779  mov     [rsp+1B0h+var_158], eax
0x18001477d  add     r9d, ebx
0x180014780  cmp     r9d, r10d
0x180014783  jb      short loc_180014715
0x180014785  mov     ecx, [rsp+1B0h+var_16C]
0x180014789  mov     r12b, [rsp+1B0h+var_180]
0x18001478e  test    bl, cl
0x180014790  jz      loc_18001487E
0x180014796  test    r12b, r12b
0x180014799  jz      loc_18001487E
0x18001479f  mov     rdx, [rbp+0B0h+var_108]
0x1800147a3  lea     rax, [rsp+1B0h+var_16C]
0x1800147a8  mov     [rbp+0B0h+var_78], rax
0x1800147ac  lea     r8, [rbp+0B0h+var_130]; struct _ATTRBLOCKSIMPLE *
0x1800147b0  and     ecx, 0FFFFFFFEh
0x1800147b3  mov     [rbp+0B0h+var_68], rdx
0x1800147b7  or      ecx, 2
0x1800147ba  mov     [rbp+0B0h+var_80], 4
0x1800147c1  mov     eax, [rdx]
0x1800147c3  mov     edx, 43h ; 'C'; unsigned int
0x1800147c8  mov     dword ptr [rbp+0B0h+var_70], eax
0x1800147cb  movzx   eax, [rsp+1B0h+var_168.Length]
0x1800147d0  mov     [rbp+0B0h+var_60], eax
0x1800147d3  mov     rax, [rsp+1B0h+var_168.Buffer]
0x1800147d8  mov     [rbp+0B0h+var_58], rax
0x1800147dc  lea     rax, [rbp+0B0h+var_80]
0x1800147e0  mov     qword ptr [rbp+0B0h+var_C0], rax
0x1800147e4  lea     rax, [rbp+0B0h+var_70]
0x1800147e8  mov     [rbp+0B0h+var_A8], rax
0x1800147ec  lea     rax, [rbp+0B0h+var_60]
0x1800147f0  mov     [rbp+0B0h+var_90], rax
0x1800147f4  lea     rax, [rbp+0B0h+var_D0]
0x1800147f8  mov     [rsp+1B0h+var_16C], ecx
0x1800147fc  mov     rcx, r14; struct _DSNAME *
0x1800147ff  mov     [rbp+0B0h+var_128], rax
0x180014803  mov     dword ptr [rbp+0B0h+var_D0], 90088h
0x18001480a  mov     dword ptr [rbp+0B0h+var_C8], ebx
0x18001480d  mov     dword ptr [rbp+0B0h+var_C0+8], 901D8h
0x180014814  mov     dword ptr [rbp+0B0h+var_B0], ebx
0x180014817  mov     [rbp+0B0h+var_A0], 90085h
0x18001481e  mov     dword ptr [rbp+0B0h+var_98], ebx
  ... truncated ...
```
