# NlReadFileTrustedDomainList(_DOMAIN_INFO *,ushort *,int,ulong,_DS_DOMAIN_TRUSTSW * *,ulong *,ulong *)

- ea: `0x18006b978`
- end: `0x18006c04f`
- name: `?NlReadFileTrustedDomainList@@YAKPEAU_DOMAIN_INFO@@PEAGHKPEAPEAU_DS_DOMAIN_TRUSTSW@@PEAK3@Z`
- size: `1751`
- prototype: `unsigned int(struct _DOMAIN_INFO *, unsigned __int16 *, int, unsigned int, struct _DS_DOMAIN_TRUSTSW **, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180070380`
- `0x180078454`

## callees

- `0x180007518`
- `0x180007e90`
- `0x180016a70`
- `0x180041390`
- `0x18006b978`
- `0x180088374`
- `0x1800892fc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ba72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006ba72`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18006bceb`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18006bceb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c002`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c018`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c002`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c018`
- `ntdll!RtlLengthSid` at `0x18006bb61`
- `ntdll!RtlLengthSid` at `0x18006bb61`
- `ntdll!RtlValidSid` at `0x18006bb4a`
- `ntdll!RtlValidSid` at `0x18006bb4a`
- `netutils!NetApiBufferFree` at `0x18006bfe3`
- `netutils!NetApiBufferFree` at `0x18006bfe3`
- `netutils!NetpwNameCompare` at `0x18006bd80`
- `netutils!NetpwNameCompare` at `0x18006bd80`

## string_xrefs

- `0x18006b9fe`: `NlReadFileForestTrustList: error reading binary log: %s.\n`
- `0x18006ba30`: `NlReadFileForestTrustList: %ws: size too small: %ld.\n`
- `0x18006ba54`: `NlReadFileForestTrustList: %ws: Version wrong: %ld.\n`
- `0x18006bec9`: `NlReadFileForestTrustList: Entry too big or small: %Ix %lx.\n`
- `0x18006beb6`: `NlReadFileForestTrustList: size not aligned %lx.\n`
- `0x18006be1f`: `NlReadFileForestTrustList: DomainSid missing (A): %Ix\n`
- `0x18006be16`: `NlReadFileForestTrustList: DomainSid missing (B): %Ix\n`
- `0x18006be03`: `NlReadFileForestTrustList: RtlValidSid returned false for DomainSid.\n`
- `0x18006bdf0`: `NlReadFileForestTrustList: DomainSidSize mismatch: %ld %ld\n`
- `0x18006be5a`: `NlReadFileForestTrustList: NetbiosDomainName missing: %Ix\n`
- `0x18006be41`: `NlReadFileForestTrustList: NetbiosDomainNameSize not aligned: %ld %Ix\n`
- `0x18006be38`: `NlReadFileForestTrustList: NetbiosDomainName not zero terminated: %Ix\n`
- `0x18006be75`: `NlReadFileForestTrustList: DnsDomainName missing: %Ix\n`
- `0x18006be6c`: `NlReadFileForestTrustList: DnsDomainNameSize not aligned: %ld %Ix\n`
- `0x18006be63`: `NlReadFileForestTrustList: DnsDomainName not zero terminated: %Ix\n`
- `0x18006be99`: `NlReadFileForestTrustList: Cannot allocate entry %lx\n`
- `0x18006be81`: `NlReadFileForestTrustList: Index causes overflow: 0x%x`
- `0x18006bd3d`: `NlReadFileForestTrustList: %ws: Duplicate primary domain entry: %ws %ws %Ix\n`
- `0x18006bdb8`: `NlReadFileForestTrustList: %ws: Log file isn't for primary domain: %ws %ws\n`
- `0x18006bef8`: `NlReadFileForestTrustList: %ws: No primary domain record in Log file\n`
- `0x18006bf86`: `NlReadFileForestTrustList: ParentIndex %lu is out of range %lu\n`
- `0x18006bf67`: `NlReadFileForestTrustList: ReturnedList entry %lu is not in the forest\n`

## pseudocode

```c
__int64 __fastcall NlReadFileTrustedDomainList(
        struct _DOMAIN_INFO *a1,
        unsigned __int16 *a2,
        int a3,
        int a4,
        struct _DS_DOMAIN_TRUSTSW **a5,
        unsigned int *a6,
        unsigned int *a7)
{
  unsigned int *v8; // rsi
  unsigned int *v9; // r15
  char v10; // r13
  void *v11; // rdi
  unsigned int v12; // eax
  _BYTE *v13; // r14
  unsigned int v14; // ebx
  struct _DS_DOMAIN_TRUSTSW **v15; // r12
  __int64 v16; // rbx
  unsigned int v17; // r13d
  unsigned __int64 v18; // r11
  unsigned int *v19; // rdi
  unsigned int v20; // ecx
  unsigned int *v21; // r15
  __int64 v22; // r9
  unsigned __int64 v23; // r10
  ULONG v24; // eax
  __int64 v25; // r8
  unsigned __int64 v26; // r9
  WCHAR *v27; // rax
  __int64 v28; // r8
  __int64 v29; // r8
  USHORT v30; // ax
  USHORT v31; // ax
  NTSTATUS v32; // r15d
  unsigned int *v33; // rax
  struct _DS_DOMAIN_TRUSTSW *v34; // r15
  struct _DOMAIN_INFO *v35; // rax
  const unsigned __int16 *DnsDomainName; // rcx
  const unsigned __int16 *v37; // rdx
  int v38; // eax
  _BYTE *v39; // rdx
  unsigned int v40; // r9d
  __int64 v41; // r10
  __int64 v42; // r8
  __int64 v43; // r8
  unsigned int i; // r8d
  __int64 v45; // rax
  struct _DS_DOMAIN_TRUSTSW *v46; // rcx
  char v48; // [rsp+68h] [rbp-71h]
  unsigned int *hMem; // [rsp+70h] [rbp-69h]
  unsigned int v50; // [rsp+78h] [rbp-61h] BYREF
  unsigned int v51[2]; // [rsp+80h] [rbp-59h] BYREF
  HLOCAL v52; // [rsp+88h] [rbp-51h] BYREF
  struct _DS_DOMAIN_TRUSTSW *v53; // [rsp+90h] [rbp-49h] BYREF
  unsigned int *v54; // [rsp+98h] [rbp-41h]
  struct _UNICODE_STRING v55; // [rsp+A0h] [rbp-39h] BYREF
  struct _UNICODE_STRING v56; // [rsp+B0h] [rbp-29h] BYREF
  char *v57; // [rsp+C0h] [rbp-19h]
  LPVOID Buffer; // [rsp+C8h] [rbp-11h] BYREF
  __int128 v59; // [rsp+D0h] [rbp-9h]
  __int64 v60; // [rsp+E0h] [rbp+7h]

  v8 = a7;
  v9 = a6;
  v10 = a4;
  v50 = 0;
  *a5 = 0;
  *a7 = 0;
  *a6 = 0;
  v52 = 0;
  v11 = 0;
  *(_QWORD *)v51 = 0;
  v60 = 0;
  hMem = 0;
  Buffer = 0;
  v59 = 0;
  v12 = NlReadBinaryLog(a2, a3, (unsigned __int8 **)&v52, &v50);
  v13 = v52;
  v14 = v12;
  if ( v12 )
  {
    NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: error reading binary log: %s.\n", a2);
LABEL_3:
    v15 = a5;
    goto LABEL_102;
  }
  v16 = v50;
  if ( !v50 )
  {
    v15 = a5;
    goto LABEL_101;
  }
  if ( v50 < 4 )
  {
    NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: %ws: size too small: %ld.\n", a2, v50);
LABEL_8:
    v14 = 1358;
    goto LABEL_3;
  }
  if ( *(_DWORD *)v52 != 1 )
  {
    NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: %ws: Version wrong: %ld.\n", a2, *(unsigned int *)v52);
    goto LABEL_8;
  }
  LODWORD(v52) = v10 & 1;
  if ( (v10 & 1) != 0 )
  {
    hMem = (unsigned int *)LocalAlloc(0x40u, 0xC8u);
    v11 = hMem;
    if ( !hMem )
    {
      v14 = 8;
      goto LABEL_3;
    }
    v50 = 50;
  }
  else
  {
    v50 = 0;
  }
  v48 = 0;
  v17 = 0;
  v57 = &v13[v16];
  v14 = 8;
  NetpULongPtrRoundUp((unsigned __int64)(v13 + 4), 8u, (unsigned __int64 *)v51);
  v19 = *(unsigned int **)v51;
  v20 = 0;
  while ( 1 )
  {
    v21 = v19 + 12;
    if ( (unsigned __int64)(v19 + 12) > v18 )
      break;
    v22 = *v19;
    v51[0] = 0;
    v56 = 0;
    v53 = 0;
    v23 = (unsigned __int64)v19 + v22;
    v54 = (unsigned int *)((char *)v19 + v22);
    v55 = 0;
    if ( (unsigned __int64)v19 + v22 > v18 || v23 <= (unsigned __int64)v19 )
    {
      NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: Entry too big or small: %Ix %lx.\n", (char *)v19 - v13);
      goto LABEL_82;
    }
    if ( (v22 & 7) != 0 )
    {
      NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: size not aligned %lx.\n", (unsigned int)v22);
      goto LABEL_82;
    }
    if ( (a4 & v19[3]) != 0 )
    {
      if ( v19[7] )
      {
        if ( (unsigned __int64)(v19 + 15) > v23 )
        {
          NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: DomainSid missing (A): %Ix\n", (char *)v19 - v13);
          goto LABEL_82;
        }
        if ( (unsigned __int64)v21 + v19[7] > v23 )
        {
          NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: DomainSid missing (B): %Ix\n", (char *)v19 - v13);
          goto LABEL_82;
        }
        if ( !RtlValidSid(v19 + 12) )
        {
          NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: RtlValidSid returned false for DomainSid.\n");
          goto LABEL_82;
        }
        v24 = RtlLengthSid(v19 + 12);
        v25 = v19[7];
        if ( (_DWORD)v25 != v24 )
        {
          NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: DomainSidSize mismatch: %ld %ld\n", v25, v24);
LABEL_82:
          v14 = 1358;
          goto LABEL_83;
        }
        v23 = (unsigned __int64)v54;
        v26 = (unsigned __int64)(v19 + 12);
        v27 = (WCHAR *)((char *)v21 + v24);
      }
      else
      {
        v26 = 0;
        v27 = (WCHAR *)(v19 + 12);
      }
      v28 = v19[1];
      if ( (_DWORD)v28 )
      {
        if ( (unsigned __int64)v27 + v28 > v23 || (WCHAR *)((char *)v27 + v28) <= v27 )
        {
          NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: NetbiosDomainName missing: %Ix\n", (char *)v19 - v13);
          goto LABEL_82;
        }
        if ( (v28 & 1) != 0 )
        {
          NlPrintRoutine(
            0x100u,
            L"NlReadFileForestTrustList: NetbiosDomainNameSize not aligned: %ld %Ix\n",
            v28,
            (char *)v19 - v13);
          goto LABEL_82;
        }
        v56.Buffer = v27;
        if ( v27[((unsigned __int64)(unsigned int)v28 >> 1) - 1] )
        {
          NlPrintRoutine(
            0x100u,
            L"NlReadFileForestTrustList: NetbiosDomainName not zero terminated: %Ix\n",
            (char *)v19 - v13);
          goto LABEL_82;
        }
        v27 = (WCHAR *)((char *)v27 + v28);
      }
      v29 = v19[2];
      if ( (_DWORD)v29 )
      {
        if ( (unsigned __int64)v27 + v29 > v23 || (WCHAR *)((char *)v27 + v29) <= v27 )
        {
          NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: DnsDomainName missing: %Ix\n", (char *)v19 - v13);
          goto LABEL_82;
        }
        if ( (v29 & 1) != 0 )
        {
          NlPrintRoutine(
            0x100u,
            L"NlReadFileForestTrustList: DnsDomainNameSize not aligned: %ld %Ix\n",
            v29,
            (char *)v19 - v13);
          goto LABEL_82;
        }
        v55.Buffer = v27;
        if ( v27[((unsigned __int64)(unsigned int)v29 >> 1) - 1] )
        {
          NlPrintRoutine(
            0x100u,
            L"NlReadFileForestTrustList: DnsDomainName not zero terminated: %Ix\n",
            (char *)v19 - v13);
          goto LABEL_82;
        }
      }
      v30 = *((_WORD *)v19 + 2);
      v56.MaximumLength = v30;
      if ( v30 )
        v56.Length = v30 - 2;
      else
        v56.Length = 0;
      v31 = *((_WORD *)v19 + 4);
      v55.MaximumLength = v31;
      if ( v31 )
        v55.Length = v31 - 2;
      else
        v55.Length = 0;
      v32 = NlAllocateForestTrustListEntry(
              (struct _BUFFER_DESCRIPTOR *)&Buffer,
              &v56,
              &v55,
              v19[3],
              v19[4],
              v19[5],
              v19[6],
              (PSID)(v26 & -(__int64)(v19[7] != 0)),
              (struct _GUID *)v19 + 2,
              v51,
              &v53);
      if ( v32 < 0 )
      {
        NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: Cannot allocate entry %lx\n", (unsigned int)v32);
        v14 = NetpNtStatusToApiStatus(v32);
        goto LABEL_83;
      }
      if ( (_DWORD)v52 )
      {
        if ( v17 >= v50 )
        {
          if ( v17 > 0xFFFFFFCD || (v50 = v17 + 50, v17 + 50 >= 0x3FFFFFFF) )
          {
            NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: Index causes overflow: 0x%x", v17);
            v14 = 534;
            goto LABEL_83;
          }
          v33 = (unsigned int *)LocalReAlloc(hMem, 4LL * (v17 + 50), 0x42u);
          if ( !v33 )
            goto LABEL_83;
          hMem = v33;
        }
        hMem[v17] = *a7;
      }
      v34 = v53;
      *a6 += v51[0];
      v20 = 0;
      ++*a7;
      if ( (v34->Flags & 8) != 0 )
      {
        if ( v48 )
        {
          NlPrintRoutine(
            0x100u,
            L"NlReadFileForestTrustList: %ws: Duplicate primary domain entry: %ws %ws %Ix\n",
            a2,
            v34->NetbiosDomainName,
            v34->DnsDomainName,
            (char *)v19 - v13);
          v20 = 0;
        }
        v35 = a1;
        v48 = 1;
        if ( a1 )
        {
          if ( v34->NetbiosDomainName )
          {
            if ( (unsigned int)NetpwNameCompare(v34->NetbiosDomainName, (char *)a1 + 72, 6) )
              goto LABEL_65;
            v35 = a1;
          }
          DnsDomainName = v34->DnsDomainName;
          if ( DnsDomainName && (v37 = (const unsigned __int16 *)*((_QWORD *)v35 + 18)) != 0 )
          {
            v38 = NlEqualDnsName(DnsDomainName, v37);
            v20 = 0;
            if ( !v38 )
            {
LABEL_65:
              NlPrintRoutine(
                0x100u,
                L"NlReadFileForestTrustList: %ws: Log file isn't for primary domain: %ws %ws\n",
                a2,
                v34->NetbiosDomainName,
                v34->DnsDomainName);
              v14 = 1355;
LABEL_83:
              v11 = hMem;
              v8 = a7;
              v9 = a6;
              goto LABEL_3;
            }
          }
          else
          {
            v20 = 0;
          }
        }
      }
      v19 = v54;
      ++v17;
      v18 = (unsigned __int64)v57;
    }
    else
    {
      v19 = (unsigned int *)((char *)v19 + v22);
      ++v17;
    }
  }
  if ( !v48 )
  {
    NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: %ws: No primary domain record in Log file\n", a2);
    v20 = 0;
  }
  v15 = a5;
  v39 = Buffer;
  *a5 = (struct _DS_DOMAIN_TRUSTSW *)Buffer;
  v40 = *a7;
  if ( (_DWORD)v52 )
  {
    while ( 1 )
    {
      if ( v20 >= v40 )
        goto LABEL_100;
      v41 = 56LL * v20;
      if ( (*(_DWORD *)&v39[v41 + 16] & 5) == 1 )
      {
        v42 = *(unsigned int *)&v39[v41 + 20];
        if ( (unsigned int)v42 >= v17 || (unsigned int)v42 >= v50 )
        {
          NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: ParentIndex %lu is out of range %lu\n", v42, v17);
          v11 = hMem;
          goto LABEL_96;
        }
        _mm_lfence();
        v11 = hMem;
        v43 = hMem[v42];
        if ( (v39[56 * v43 + 16] & 1) == 0 )
        {
          NlPrintRoutine(0x100u, L"NlReadFileForestTrustList: ReturnedList entry %lu is not in the forest\n");
LABEL_96:
          v8 = a7;
          v14 = 1358;
          v9 = a6;
          goto LABEL_102;
        }
      }
      else
      {
        LODWORD(v43) = 0;
      }
      *(_DWORD *)&v39[v41 + 20] = v43;
      ++v20;
    }
  }
  if ( v40 )
  {
    for ( i = 0; i < v40; ++i )
    {
      v45 = i;
      *(_DWORD *)&v39[56 * v45 + 20] = 0;
    }
  }
LABEL_100:
  v11 = hMem;
  v8 = a7;
  v9 = a6;
  Buffer = 0;
LABEL_101:
  v14 = 0;
LABEL_102:
  v46 = (struct _DS_DOMAIN_TRUSTSW *)Buffer;
  if ( Buffer )
  {
    NetApiBufferFree(Buffer);
    v46 = 0;
    *v8 = 0;
    *v9 = 0;
    *v15 = 0;
  }
  if ( v11 )
  {
    LocalFree(v11);
    v46 = 0;
  }
  if ( v13 )
  {
    LocalFree(v13);
    v46 = 0;
  }
  if ( *v15 == v46 )
  {
    *v8 = (unsigned int)v46;
    *v9 = (unsigned int)v46;
  }
  return v14;
}

```

## disassembly

```asm
0x18006b978  mov     rax, rsp
0x18006b97b  mov     [rax+10h], rbx
0x18006b97f  mov     [rax+20h], r9d
0x18006b983  mov     [rax+8], rcx
0x18006b987  push    rbp
0x18006b988  push    rsi
0x18006b989  push    rdi
0x18006b98a  push    r12
0x18006b98c  push    r13
0x18006b98e  push    r14
0x18006b990  push    r15
0x18006b992  lea     rbp, [rax-47h]
0x18006b996  sub     rsp, 0E0h
0x18006b99d  mov     rcx, [rbp+3Fh+arg_20]
0x18006b9a1  mov     r12, rdx
0x18006b9a4  mov     rsi, [rbp+3Fh+arg_30]
0x18006b9a8  xor     edx, edx
0x18006b9aa  mov     r15, [rbp+3Fh+arg_28]
0x18006b9ae  mov     eax, r8d
0x18006b9b1  mov     r13d, r9d
0x18006b9b4  mov     [rbp+3Fh+var_A0], edx
0x18006b9b7  mov     [rcx], rdx
0x18006b9ba  lea     r9, [rbp+3Fh+var_A0]; unsigned int *
0x18006b9be  mov     [rsi], edx
0x18006b9c0  lea     r8, [rbp+3Fh+var_90]; unsigned __int8 **
0x18006b9c4  mov     [r15], edx
0x18006b9c7  xorps   xmm0, xmm0
0x18006b9ca  mov     [rbp+3Fh+var_90], rdx
0x18006b9ce  mov     edi, edx
0x18006b9d0  mov     qword ptr [rbp+3Fh+var_98], rdx
0x18006b9d4  mov     rcx, r12; unsigned __int16 *
0x18006b9d7  mov     [rbp+3Fh+var_38], rdx
0x18006b9db  mov     [rbp+3Fh+hMem], rdx
0x18006b9df  mov     [rbp+3Fh+Buffer], rdx
0x18006b9e3  mov     edx, eax; int
0x18006b9e5  movdqu  [rbp+3Fh+var_48], xmm0
0x18006b9ea  call    ?NlReadBinaryLog@@YAKPEAGHPEAPEAEPEAK@Z; NlReadBinaryLog(ushort *,int,uchar * *,ulong *)
0x18006b9ef  mov     r14, [rbp+3Fh+var_90]
0x18006b9f3  xor     ecx, ecx
0x18006b9f5  mov     ebx, eax
0x18006b9f7  test    eax, eax
0x18006b9f9  jz      short loc_18006BA18
0x18006b9fb  mov     r8, r12
0x18006b9fe  lea     rdx, aNlreadfilefore_12; "NlReadFileForestTrustList: error readin"...
0x18006ba05  mov     ecx, 100h; unsigned int
0x18006ba0a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006ba0f  mov     r12, [rbp+3Fh+arg_20]
0x18006ba13  jmp     loc_18006BFDA
0x18006ba18  mov     ebx, [rbp+3Fh+var_A0]
0x18006ba1b  test    ebx, ebx
0x18006ba1d  jnz     short loc_18006BA28
0x18006ba1f  mov     r12, [rbp+3Fh+arg_20]
0x18006ba23  jmp     loc_18006BFD8
0x18006ba28  cmp     ebx, 4
0x18006ba2b  jnb     short loc_18006BA4B
0x18006ba2d  mov     r9d, ebx
0x18006ba30  lea     rdx, aNlreadfilefore_15; "NlReadFileForestTrustList: %ws: size to"...
0x18006ba37  mov     r8, r12
0x18006ba3a  mov     ecx, 100h; unsigned int
0x18006ba3f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006ba44  mov     ebx, 54Eh
0x18006ba49  jmp     short loc_18006BA0F
0x18006ba4b  cmp     dword ptr [r14], 1
0x18006ba4f  jz      short loc_18006BA5D
0x18006ba51  mov     r9d, [r14]
0x18006ba54  lea     rdx, aNlreadfilefore; "NlReadFileForestTrustList: %ws: Version"...
0x18006ba5b  jmp     short loc_18006BA37
0x18006ba5d  mov     eax, r13d
0x18006ba60  and     eax, 1
0x18006ba63  mov     dword ptr [rbp+3Fh+var_90], eax
0x18006ba66  jz      short loc_18006BA9D
0x18006ba68  mov     edx, 0C8h; uBytes
0x18006ba6d  mov     ecx, 40h ; '@'; uFlags
0x18006ba72  call    cs:__imp_LocalAlloc
0x18006ba79  nop     dword ptr [rax+rax+00h]
0x18006ba7e  xor     ecx, ecx
0x18006ba80  mov     [rbp+3Fh+hMem], rax
0x18006ba84  mov     rdi, rax
0x18006ba87  test    rax, rax
0x18006ba8a  jnz     short loc_18006BA94
0x18006ba8c  lea     ebx, [rax+8]
0x18006ba8f  jmp     loc_18006BA0F
0x18006ba94  mov     [rbp+3Fh+var_A0], 32h ; '2'
0x18006ba9b  jmp     short loc_18006BAA0
0x18006ba9d  mov     [rbp+3Fh+var_A0], ecx
0x18006baa0  lea     r11, [r14+rbx]
0x18006baa4  mov     [rbp+3Fh+var_B0], cl
0x18006baa7  mov     r13d, ecx
0x18006baaa  mov     [rbp+3Fh+var_58], r11
0x18006baae  mov     ebx, 8
0x18006bab3  lea     rcx, [r14+4]; unsigned __int64
0x18006bab7  mov     edx, ebx; unsigned __int64
0x18006bab9  lea     r8, [rbp+3Fh+var_98]; unsigned __int64 *
0x18006babd  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18006bac2  mov     rdi, qword ptr [rbp+3Fh+var_98]
0x18006bac6  xor     ecx, ecx
0x18006bac8  mov     esi, 100h
0x18006bacd  mov     eax, [rbp+3Fh+arg_18]
0x18006bad0  lea     r15, [rdi+30h]
0x18006bad4  cmp     r15, r11
0x18006bad7  ja      loc_18006BEF0
0x18006badd  mov     r9d, [rdi]
0x18006bae0  xorps   xmm0, xmm0
0x18006bae3  xorps   xmm1, xmm1
0x18006bae6  mov     [rbp+3Fh+var_98], ecx
0x18006bae9  movups  xmmword ptr [rbp+3Fh+var_68.Length], xmm0
0x18006baed  mov     [rbp+3Fh+var_88], rcx
0x18006baf1  lea     r10, [r9+rdi]
0x18006baf5  mov     [rbp+3Fh+var_80], r10
0x18006baf9  movups  xmmword ptr [rbp+3Fh+var_78.Length], xmm1
0x18006bafd  cmp     r10, r11
0x18006bb00  ja      loc_18006BEC6
0x18006bb06  cmp     r10, rdi
0x18006bb09  jbe     loc_18006BEC6
0x18006bb0f  test    r9b, 7
0x18006bb13  jnz     loc_18006BEB3
0x18006bb19  test    [rdi+0Ch], eax
0x18006bb1c  jnz     short loc_18006BB26
0x18006bb1e  mov     rdi, r10
0x18006bb21  inc     r13d
0x18006bb24  jmp     short loc_18006BAD0
0x18006bb26  cmp     [rdi+1Ch], ecx
0x18006bb29  jz      short loc_18006BB8A
0x18006bb2b  lea     rax, [r15+0Ch]
0x18006bb2f  cmp     rax, r10
0x18006bb32  ja      loc_18006BE1F
0x18006bb38  mov     eax, [rdi+1Ch]
0x18006bb3b  add     rax, r15
0x18006bb3e  cmp     rax, r10
0x18006bb41  ja      loc_18006BE16
0x18006bb47  mov     rcx, r15; Sid
0x18006bb4a  call    cs:__imp_RtlValidSid
0x18006bb51  nop     dword ptr [rax+rax+00h]
0x18006bb56  test    al, al
0x18006bb58  jz      loc_18006BE03
0x18006bb5e  mov     rcx, r15; Sid
0x18006bb61  call    cs:__imp_RtlLengthSid
0x18006bb68  nop     dword ptr [rax+rax+00h]
0x18006bb6d  mov     r8d, [rdi+1Ch]
0x18006bb71  cmp     r8d, eax
0x18006bb74  jnz     loc_18006BDED
0x18006bb7a  mov     r10, [rbp+3Fh+var_80]
0x18006bb7e  mov     r9, r15
0x18006bb81  mov     eax, eax
0x18006bb83  add     rax, r15
0x18006bb86  xor     ecx, ecx
0x18006bb88  jmp     short loc_18006BB90
0x18006bb8a  mov     r9, rcx
0x18006bb8d  mov     rax, r15
0x18006bb90  mov     r8d, [rdi+4]
0x18006bb94  test    r8d, r8d
0x18006bb97  jz      short loc_18006BBD7
0x18006bb99  lea     rdx, [r8+rax]
0x18006bb9d  mov     ecx, r8d
0x18006bba0  cmp     rdx, r10
0x18006bba3  ja      loc_18006BE5A
0x18006bba9  cmp     rdx, rax
0x18006bbac  jbe     loc_18006BE5A
0x18006bbb2  test    r8b, 1
0x18006bbb6  jnz     loc_18006BE41
0x18006bbbc  shr     rcx, 1
0x18006bbbf  xor     r11d, r11d
0x18006bbc2  mov     [rbp+3Fh+var_68.Buffer], rax
0x18006bbc6  cmp     [rax+rcx*2-2], r11w
0x18006bbcc  jnz     loc_18006BE38
0x18006bbd2  mov     rax, rdx
0x18006bbd5  xor     ecx, ecx
0x18006bbd7  mov     r8d, [rdi+8]
0x18006bbdb  test    r8d, r8d
0x18006bbde  jz      short loc_18006BC1B
0x18006bbe0  lea     rdx, [r8+rax]
0x18006bbe4  mov     ecx, r8d
0x18006bbe7  cmp     rdx, r10
0x18006bbea  ja      loc_18006BE75
0x18006bbf0  cmp     rdx, rax
0x18006bbf3  jbe     loc_18006BE75
0x18006bbf9  test    r8b, 1
0x18006bbfd  jnz     loc_18006BE6C
0x18006bc03  shr     rcx, 1
0x18006bc06  xor     r11d, r11d
0x18006bc09  mov     [rbp+3Fh+var_78.Buffer], rax
0x18006bc0d  cmp     [rax+rcx*2-2], r11w
0x18006bc13  jnz     loc_18006BE63
0x18006bc19  xor     ecx, ecx
0x18006bc1b  movzx   eax, word ptr [rdi+4]
0x18006bc1f  mov     [rbp+3Fh+var_68.MaximumLength], ax
0x18006bc23  test    ax, ax
0x18006bc26  jnz     short loc_18006BC2E
0x18006bc28  mov     [rbp+3Fh+var_68.Length], cx
0x18006bc2c  jmp     short loc_18006BC36
0x18006bc2e  sub     ax, 2
0x18006bc32  mov     [rbp+3Fh+var_68.Length], ax
0x18006bc36  movzx   eax, word ptr [rdi+8]
0x18006bc3a  mov     [rbp+3Fh+var_78.MaximumLength], ax
0x18006bc3e  test    ax, ax
0x18006bc41  jnz     short loc_18006BC49
0x18006bc43  mov     [rbp+3Fh+var_78.Length], cx
0x18006bc47  jmp     short loc_18006BC51
0x18006bc49  sub     ax, 2
0x18006bc4d  mov     [rbp+3Fh+var_78.Length], ax
0x18006bc51  mov     eax, [rdi+1Ch]
0x18006bc54  lea     rdx, [rdi+20h]
0x18006bc58  neg     eax
0x18006bc5a  lea     r8, [rbp+3Fh+var_78]; struct _UNICODE_STRING *
0x18006bc5e  lea     rax, [rbp+3Fh+var_88]
0x18006bc62  mov     [rsp+50h], rax; struct _DS_DOMAIN_TRUSTSW **
0x18006bc67  sbb     rcx, rcx
0x18006bc6a  and     rcx, r9
0x18006bc6d  lea     rax, [rbp+3Fh+var_98]
0x18006bc71  mov     r9d, [rdi+0Ch]; unsigned int
0x18006bc75  mov     [rsp+110h+var_C8], rax; unsigned int *
0x18006bc7a  mov     eax, [rdi+18h]
0x18006bc7d  mov     [rsp+110h+var_D0], rdx; struct _GUID *
0x18006bc82  lea     rdx, [rbp+3Fh+var_68]; struct _UNICODE_STRING *
0x18006bc86  mov     [rsp+110h+Sid], rcx; Sid
0x18006bc8b  lea     rcx, [rbp+3Fh+Buffer]; struct _BUFFER_DESCRIPTOR *
0x18006bc8f  mov     [rsp+110h+var_E0], eax; unsigned int
0x18006bc93  mov     eax, [rdi+14h]
0x18006bc96  mov     [rsp+110h+var_E8], eax; unsigned int
0x18006bc9a  mov     eax, [rdi+10h]
0x18006bc9d  mov     [rsp+110h+var_F0], eax; unsigned int
0x18006bca1  call    ?NlAllocateForestTrustListEntry@@YAJPEAU_BUFFER_DESCRIPTOR@@PEAU_UNICODE_STRING@@1KKKKPEAXPEAU_GUID@@PEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z; NlAllocateForestTrustListEntry(_BUFFER_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,ulong,void *,_GUID *,ulong *,_DS_DOMAIN_TRUSTSW * *)
0x18006bca6  mov     r15d, eax
0x18006bca9  xor     eax, eax
0x18006bcab  test    r15d, r15d
0x18006bcae  js      loc_18006BE96
0x18006bcb4  cmp     dword ptr [rbp+3Fh+var_90], eax
0x18006bcb7  jz      short loc_18006BD15
0x18006bcb9  cmp     r13d, [rbp+3Fh+var_A0]
0x18006bcbd  jb      short loc_18006BD04
0x18006bcbf  cmp     r13d, 0FFFFFFCDh
0x18006bcc3  ja      loc_18006BE7E
0x18006bcc9  lea     eax, [r13+32h]
0x18006bccd  mov     [rbp+3Fh+var_A0], eax
0x18006bcd0  cmp     eax, 3FFFFFFFh
0x18006bcd5  jnb     loc_18006BE7E
0x18006bcdb  mov     rcx, [rbp+3Fh+hMem]; hMem
0x18006bcdf  mov     r8d, 42h ; 'B'; uFlags
0x18006bce5  mov     edx, eax
0x18006bce7  shl     rdx, 2; uBytes
0x18006bceb  call    cs:__imp_LocalReAlloc
0x18006bcf2  nop     dword ptr [rax+rax+00h]
0x18006bcf7  test    rax, rax
0x18006bcfa  jz      loc_18006BEDF
0x18006bd00  mov     [rbp+3Fh+hMem], rax
0x18006bd04  mov     r9, [rbp+3Fh+arg_30]
0x18006bd08  mov     rdx, [rbp+3Fh+hMem]
0x18006bd0c  mov     ecx, r13d
0x18006bd0f  mov     eax, [r9]
0x18006bd12  mov     [rdx+rcx*4], eax
0x18006bd15  mov     rcx, [rbp+3Fh+arg_28]
0x18006bd19  mov     eax, [rbp+3Fh+var_98]
0x18006bd1c  mov     r15, [rbp+3Fh+var_88]
0x18006bd20  add     [rcx], eax
0x18006bd22  xor     ecx, ecx
0x18006bd24  mov     rax, [rbp+3Fh+arg_30]
0x18006bd28  inc     dword ptr [rax]
0x18006bd2a  test    [r15+10h], bl
0x18006bd2e  jz      loc_18006BDDD
0x18006bd34  cmp     [rbp+3Fh+var_B0], cl
0x18006bd37  jz      short loc_18006BD60
0x18006bd39  mov     rax, [r15+8]
0x18006bd3d  lea     rdx, aNlreadfilefore_10; "NlReadFileForestTrustList: %ws: Duplica"...
0x18006bd44  mov     r9, [r15]
0x18006bd47  sub     rdi, r14
0x18006bd4a  mov     qword ptr [rsp+110h+var_E8], rdi
0x18006bd4f  mov     r8, r12
0x18006bd52  mov     ecx, esi; unsigned int
0x18006bd54  mov     qword ptr [rsp+110h+var_F0], rax
0x18006bd59  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006bd5e  xor     ecx, ecx
0x18006bd60  mov     rax, [rbp+3Fh+arg_0]
0x18006bd64  mov     [rbp+3Fh+var_B0], 1
0x18006bd68  test    rax, rax
0x18006bd6b  jz      short loc_18006BDDD
0x18006bd6d  mov     rcx, [r15]
0x18006bd70  test    rcx, rcx
0x18006bd73  jz      short loc_18006BD94
0x18006bd75  xor     r9d, r9d
0x18006bd78  lea     rdx, [rax+48h]
0x18006bd7c  lea     r8d, [r9+6]
0x18006bd80  call    cs:__imp_NetpwNameCompare
0x18006bd87  nop     dword ptr [rax+rax+00h]
0x18006bd8c  test    eax, eax
0x18006bd8e  jnz     short loc_18006BDB4
0x18006bd90  mov     rax, [rbp+3Fh+arg_0]
0x18006bd94  mov     rcx, [r15+8]; unsigned __int16 *
0x18006bd98  test    rcx, rcx
0x18006bd9b  jz      short loc_18006BDDB
0x18006bd9d  mov     rdx, [rax+90h]; unsigned __int16 *
0x18006bda4  test    rdx, rdx
0x18006bda7  jz      short loc_18006BDDB
0x18006bda9  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18006bdae  xor     ecx, ecx
0x18006bdb0  test    eax, eax
0x18006bdb2  jnz     short loc_18006BDDD
0x18006bdb4  mov     rax, [r15+8]
0x18006bdb8  lea     rdx, aNlreadfilefore_11; "NlReadFileForestTrustList: %ws: Log fil"...
0x18006bdbf  mov     r9, [r15]
0x18006bdc2  mov     r8, r12
  ... truncated ...
```
