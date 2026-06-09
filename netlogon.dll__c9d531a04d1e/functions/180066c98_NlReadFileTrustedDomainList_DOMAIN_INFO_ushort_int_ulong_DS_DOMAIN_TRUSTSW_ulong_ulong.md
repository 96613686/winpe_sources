# NlReadFileTrustedDomainList(_DOMAIN_INFO *,ushort *,int,ulong,_DS_DOMAIN_TRUSTSW * *,ulong *,ulong *)

- ea: `0x180066c98`
- end: `0x18006733b`
- name: `?NlReadFileTrustedDomainList@@YAKPEAU_DOMAIN_INFO@@PEAGHKPEAPEAU_DS_DOMAIN_TRUSTSW@@PEAK3@Z`
- size: `1699`
- prototype: `__int64 __fastcall(struct _DOMAIN_INFO *, unsigned __int16 *, int, int, struct _DS_DOMAIN_TRUSTSW **, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006b2e0`
- `0x180072dc4`

## callees

- `0x180007278`
- `0x180007b50`
- `0x18001606c`
- `0x18003eb40`
- `0x180066c98`
- `0x1800822bc`
- `0x18008315c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066d92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180066d92`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180066ff6`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180066ff6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800672fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006730b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800672fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006730b`
- `ntdll!RtlLengthSid` at `0x180066e72`
- `ntdll!RtlLengthSid` at `0x180066e72`
- `ntdll!RtlValidSid` at `0x180066e61`
- `ntdll!RtlValidSid` at `0x180066e61`
- `netutils!NetApiBufferFree` at `0x1800672e2`
- `netutils!NetApiBufferFree` at `0x1800672e2`
- `netutils!NetpwNameCompare` at `0x180067085`
- `netutils!NetpwNameCompare` at `0x180067085`

## string_xrefs

- `0x180066d1e`: `NlReadFileForestTrustList: error reading binary log: %s.\n`
- `0x180066d50`: `NlReadFileForestTrustList: %ws: size too small: %ld.\n`
- `0x180066d74`: `NlReadFileForestTrustList: %ws: Version wrong: %ld.\n`
- `0x1800671c8`: `NlReadFileForestTrustList: Entry too big or small: %Ix %lx.\n`
- `0x1800671b5`: `NlReadFileForestTrustList: size not aligned %lx.\n`
- `0x18006711e`: `NlReadFileForestTrustList: DomainSid missing (A): %Ix\n`
- `0x180067115`: `NlReadFileForestTrustList: DomainSid missing (B): %Ix\n`
- `0x180067102`: `NlReadFileForestTrustList: RtlValidSid returned false for DomainSid.\n`
- `0x1800670ef`: `NlReadFileForestTrustList: DomainSidSize mismatch: %ld %ld\n`
- `0x180067159`: `NlReadFileForestTrustList: NetbiosDomainName missing: %Ix\n`
- `0x180067140`: `NlReadFileForestTrustList: NetbiosDomainNameSize not aligned: %ld %Ix\n`
- `0x180067137`: `NlReadFileForestTrustList: NetbiosDomainName not zero terminated: %Ix\n`
- `0x180067174`: `NlReadFileForestTrustList: DnsDomainName missing: %Ix\n`
- `0x18006716b`: `NlReadFileForestTrustList: DnsDomainNameSize not aligned: %ld %Ix\n`
- `0x180067162`: `NlReadFileForestTrustList: DnsDomainName not zero terminated: %Ix\n`
- `0x180067198`: `NlReadFileForestTrustList: Cannot allocate entry %lx\n`
- `0x180067180`: `NlReadFileForestTrustList: Index causes overflow: 0x%x`
- `0x180067042`: `NlReadFileForestTrustList: %ws: Duplicate primary domain entry: %ws %ws %Ix\n`
- `0x1800670b7`: `NlReadFileForestTrustList: %ws: Log file isn't for primary domain: %ws %ws\n`
- `0x1800671f7`: `NlReadFileForestTrustList: %ws: No primary domain record in Log file\n`
- `0x180067285`: `NlReadFileForestTrustList: ParentIndex %lu is out of range %lu\n`
- `0x180067266`: `NlReadFileForestTrustList: ReturnedList entry %lu is not in the forest\n`

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
  v12 = NlReadBinaryLog(a2, a3, &v52, &v50);
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
0x180066c98  mov     rax, rsp
0x180066c9b  mov     [rax+10h], rbx
0x180066c9f  mov     [rax+20h], r9d
0x180066ca3  mov     [rax+8], rcx
0x180066ca7  push    rbp
0x180066ca8  push    rsi
0x180066ca9  push    rdi
0x180066caa  push    r12
0x180066cac  push    r13
0x180066cae  push    r14
0x180066cb0  push    r15
0x180066cb2  lea     rbp, [rax-47h]
0x180066cb6  sub     rsp, 0E0h
0x180066cbd  mov     rcx, [rbp+3Fh+arg_20]
0x180066cc1  mov     r12, rdx
0x180066cc4  mov     rsi, [rbp+3Fh+arg_30]
0x180066cc8  xor     edx, edx
0x180066cca  mov     r15, [rbp+3Fh+arg_28]
0x180066cce  mov     eax, r8d
0x180066cd1  mov     r13d, r9d
0x180066cd4  mov     [rbp+3Fh+var_A0], edx
0x180066cd7  mov     [rcx], rdx
0x180066cda  lea     r9, [rbp+3Fh+var_A0]; unsigned int *
0x180066cde  mov     [rsi], edx
0x180066ce0  lea     r8, [rbp+3Fh+var_90]; unsigned __int8 **
0x180066ce4  mov     [r15], edx
0x180066ce7  xorps   xmm0, xmm0
0x180066cea  mov     [rbp+3Fh+var_90], rdx
0x180066cee  mov     edi, edx
0x180066cf0  mov     qword ptr [rbp+3Fh+var_98], rdx
0x180066cf4  mov     rcx, r12; unsigned __int16 *
0x180066cf7  mov     [rbp+3Fh+var_38], rdx
0x180066cfb  mov     [rbp+3Fh+hMem], rdx
0x180066cff  mov     [rbp+3Fh+Buffer], rdx
0x180066d03  mov     edx, eax; int
0x180066d05  movdqu  [rbp+3Fh+var_48], xmm0
0x180066d0a  call    ?NlReadBinaryLog@@YAKPEAGHPEAPEAEPEAK@Z; NlReadBinaryLog(ushort *,int,uchar * *,ulong *)
0x180066d0f  mov     r14, [rbp+3Fh+var_90]
0x180066d13  xor     ecx, ecx
0x180066d15  mov     ebx, eax
0x180066d17  test    eax, eax
0x180066d19  jz      short loc_180066D38
0x180066d1b  mov     r8, r12
0x180066d1e  lea     rdx, aNlreadfilefore_12; "NlReadFileForestTrustList: error readin"...
0x180066d25  mov     ecx, 100h; unsigned int
0x180066d2a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180066d2f  mov     r12, [rbp+3Fh+arg_20]
0x180066d33  jmp     loc_1800672D9
0x180066d38  mov     ebx, [rbp+3Fh+var_A0]
0x180066d3b  test    ebx, ebx
0x180066d3d  jnz     short loc_180066D48
0x180066d3f  mov     r12, [rbp+3Fh+arg_20]
0x180066d43  jmp     loc_1800672D7
0x180066d48  cmp     ebx, 4
0x180066d4b  jnb     short loc_180066D6B
0x180066d4d  mov     r9d, ebx
0x180066d50  lea     rdx, aNlreadfilefore_15; "NlReadFileForestTrustList: %ws: size to"...
0x180066d57  mov     r8, r12
0x180066d5a  mov     ecx, 100h; unsigned int
0x180066d5f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180066d64  mov     ebx, 54Eh
0x180066d69  jmp     short loc_180066D2F
0x180066d6b  cmp     dword ptr [r14], 1
0x180066d6f  jz      short loc_180066D7D
0x180066d71  mov     r9d, [r14]
0x180066d74  lea     rdx, aNlreadfilefore; "NlReadFileForestTrustList: %ws: Version"...
0x180066d7b  jmp     short loc_180066D57
0x180066d7d  mov     eax, r13d
0x180066d80  and     eax, 1
0x180066d83  mov     dword ptr [rbp+3Fh+var_90], eax
0x180066d86  jz      short loc_180066DB4
0x180066d88  mov     edx, 0C8h; uBytes
0x180066d8d  mov     ecx, 40h ; '@'; uFlags
0x180066d92  call    cs:__imp_LocalAlloc
0x180066d98  xor     ecx, ecx
0x180066d9a  mov     [rbp+3Fh+hMem], rax
0x180066d9e  mov     rdi, rax
0x180066da1  test    rax, rax
0x180066da4  jnz     short loc_180066DAB
0x180066da6  lea     ebx, [rax+8]
0x180066da9  jmp     short loc_180066D2F
0x180066dab  mov     [rbp+3Fh+var_A0], 32h ; '2'
0x180066db2  jmp     short loc_180066DB7
0x180066db4  mov     [rbp+3Fh+var_A0], ecx
0x180066db7  lea     r11, [r14+rbx]
0x180066dbb  mov     [rbp+3Fh+var_B0], cl
0x180066dbe  mov     r13d, ecx
0x180066dc1  mov     [rbp+3Fh+var_58], r11
0x180066dc5  mov     ebx, 8
0x180066dca  lea     rcx, [r14+4]; unsigned __int64
0x180066dce  mov     edx, ebx; unsigned __int64
0x180066dd0  lea     r8, [rbp+3Fh+var_98]; unsigned __int64 *
0x180066dd4  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180066dd9  mov     rdi, qword ptr [rbp+3Fh+var_98]
0x180066ddd  xor     ecx, ecx
0x180066ddf  mov     esi, 100h
0x180066de4  mov     eax, [rbp+3Fh+arg_18]
0x180066de7  lea     r15, [rdi+30h]
0x180066deb  cmp     r15, r11
0x180066dee  ja      loc_1800671EF
0x180066df4  mov     r9d, [rdi]
0x180066df7  xorps   xmm0, xmm0
0x180066dfa  xorps   xmm1, xmm1
0x180066dfd  mov     [rbp+3Fh+var_98], ecx
0x180066e00  movups  xmmword ptr [rbp+3Fh+var_68.Length], xmm0
0x180066e04  mov     [rbp+3Fh+var_88], rcx
0x180066e08  lea     r10, [r9+rdi]
0x180066e0c  mov     [rbp+3Fh+var_80], r10
0x180066e10  movups  xmmword ptr [rbp+3Fh+var_78.Length], xmm1
0x180066e14  cmp     r10, r11
0x180066e17  ja      loc_1800671C5
0x180066e1d  cmp     r10, rdi
0x180066e20  jbe     loc_1800671C5
0x180066e26  test    r9b, 7
0x180066e2a  jnz     loc_1800671B2
0x180066e30  test    [rdi+0Ch], eax
0x180066e33  jnz     short loc_180066E3D
0x180066e35  mov     rdi, r10
0x180066e38  inc     r13d
0x180066e3b  jmp     short loc_180066DE7
0x180066e3d  cmp     [rdi+1Ch], ecx
0x180066e40  jz      short loc_180066E95
0x180066e42  lea     rax, [r15+0Ch]
0x180066e46  cmp     rax, r10
0x180066e49  ja      loc_18006711E
0x180066e4f  mov     eax, [rdi+1Ch]
0x180066e52  add     rax, r15
0x180066e55  cmp     rax, r10
0x180066e58  ja      loc_180067115
0x180066e5e  mov     rcx, r15; Sid
0x180066e61  call    cs:__imp_RtlValidSid
0x180066e67  test    al, al
0x180066e69  jz      loc_180067102
0x180066e6f  mov     rcx, r15; Sid
0x180066e72  call    cs:__imp_RtlLengthSid
0x180066e78  mov     r8d, [rdi+1Ch]
0x180066e7c  cmp     r8d, eax
0x180066e7f  jnz     loc_1800670EC
0x180066e85  mov     r10, [rbp+3Fh+var_80]
0x180066e89  mov     r9, r15
0x180066e8c  mov     eax, eax
0x180066e8e  add     rax, r15
0x180066e91  xor     ecx, ecx
0x180066e93  jmp     short loc_180066E9B
0x180066e95  mov     r9, rcx
0x180066e98  mov     rax, r15
0x180066e9b  mov     r8d, [rdi+4]
0x180066e9f  test    r8d, r8d
0x180066ea2  jz      short loc_180066EE2
0x180066ea4  lea     rdx, [r8+rax]
0x180066ea8  mov     ecx, r8d
0x180066eab  cmp     rdx, r10
0x180066eae  ja      loc_180067159
0x180066eb4  cmp     rdx, rax
0x180066eb7  jbe     loc_180067159
0x180066ebd  test    r8b, 1
0x180066ec1  jnz     loc_180067140
0x180066ec7  shr     rcx, 1
0x180066eca  xor     r11d, r11d
0x180066ecd  mov     [rbp+3Fh+var_68.Buffer], rax
0x180066ed1  cmp     [rax+rcx*2-2], r11w
0x180066ed7  jnz     loc_180067137
0x180066edd  mov     rax, rdx
0x180066ee0  xor     ecx, ecx
0x180066ee2  mov     r8d, [rdi+8]
0x180066ee6  test    r8d, r8d
0x180066ee9  jz      short loc_180066F26
0x180066eeb  lea     rdx, [r8+rax]
0x180066eef  mov     ecx, r8d
0x180066ef2  cmp     rdx, r10
0x180066ef5  ja      loc_180067174
0x180066efb  cmp     rdx, rax
0x180066efe  jbe     loc_180067174
0x180066f04  test    r8b, 1
0x180066f08  jnz     loc_18006716B
0x180066f0e  shr     rcx, 1
0x180066f11  xor     r11d, r11d
0x180066f14  mov     [rbp+3Fh+var_78.Buffer], rax
0x180066f18  cmp     [rax+rcx*2-2], r11w
0x180066f1e  jnz     loc_180067162
0x180066f24  xor     ecx, ecx
0x180066f26  movzx   eax, word ptr [rdi+4]
0x180066f2a  mov     [rbp+3Fh+var_68.MaximumLength], ax
0x180066f2e  test    ax, ax
0x180066f31  jnz     short loc_180066F39
0x180066f33  mov     [rbp+3Fh+var_68.Length], cx
0x180066f37  jmp     short loc_180066F41
0x180066f39  sub     ax, 2
0x180066f3d  mov     [rbp+3Fh+var_68.Length], ax
0x180066f41  movzx   eax, word ptr [rdi+8]
0x180066f45  mov     [rbp+3Fh+var_78.MaximumLength], ax
0x180066f49  test    ax, ax
0x180066f4c  jnz     short loc_180066F54
0x180066f4e  mov     [rbp+3Fh+var_78.Length], cx
0x180066f52  jmp     short loc_180066F5C
0x180066f54  sub     ax, 2
0x180066f58  mov     [rbp+3Fh+var_78.Length], ax
0x180066f5c  mov     eax, [rdi+1Ch]
0x180066f5f  lea     rdx, [rdi+20h]
0x180066f63  neg     eax
0x180066f65  lea     r8, [rbp+3Fh+var_78]; struct _UNICODE_STRING *
0x180066f69  lea     rax, [rbp+3Fh+var_88]
0x180066f6d  mov     [rsp+50h], rax; struct _DS_DOMAIN_TRUSTSW **
0x180066f72  sbb     rcx, rcx
0x180066f75  and     rcx, r9
0x180066f78  lea     rax, [rbp+3Fh+var_98]
0x180066f7c  mov     r9d, [rdi+0Ch]; unsigned int
0x180066f80  mov     [rsp+110h+var_C8], rax; unsigned int *
0x180066f85  mov     eax, [rdi+18h]
0x180066f88  mov     [rsp+110h+var_D0], rdx; struct _GUID *
0x180066f8d  lea     rdx, [rbp+3Fh+var_68]; struct _UNICODE_STRING *
0x180066f91  mov     [rsp+110h+Sid], rcx; Sid
0x180066f96  lea     rcx, [rbp+3Fh+Buffer]; struct _BUFFER_DESCRIPTOR *
0x180066f9a  mov     [rsp+110h+var_E0], eax; unsigned int
0x180066f9e  mov     eax, [rdi+14h]
0x180066fa1  mov     [rsp+110h+var_E8], eax; unsigned int
0x180066fa5  mov     eax, [rdi+10h]
0x180066fa8  mov     [rsp+110h+var_F0], eax; unsigned int
0x180066fac  call    ?NlAllocateForestTrustListEntry@@YAJPEAU_BUFFER_DESCRIPTOR@@PEAU_UNICODE_STRING@@1KKKKPEAXPEAU_GUID@@PEAKPEAPEAU_DS_DOMAIN_TRUSTSW@@@Z; NlAllocateForestTrustListEntry(_BUFFER_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,ulong,void *,_GUID *,ulong *,_DS_DOMAIN_TRUSTSW * *)
0x180066fb1  mov     r15d, eax
0x180066fb4  xor     eax, eax
0x180066fb6  test    r15d, r15d
0x180066fb9  js      loc_180067195
0x180066fbf  cmp     dword ptr [rbp+3Fh+var_90], eax
0x180066fc2  jz      short loc_18006701A
0x180066fc4  cmp     r13d, [rbp+3Fh+var_A0]
0x180066fc8  jb      short loc_180067009
0x180066fca  cmp     r13d, 0FFFFFFCDh
0x180066fce  ja      loc_18006717D
0x180066fd4  lea     eax, [r13+32h]
0x180066fd8  mov     [rbp+3Fh+var_A0], eax
0x180066fdb  cmp     eax, 3FFFFFFFh
0x180066fe0  jnb     loc_18006717D
0x180066fe6  mov     rcx, [rbp+3Fh+hMem]; hMem
0x180066fea  mov     r8d, 42h ; 'B'; uFlags
0x180066ff0  mov     edx, eax
0x180066ff2  shl     rdx, 2; uBytes
0x180066ff6  call    cs:__imp_LocalReAlloc
0x180066ffc  test    rax, rax
0x180066fff  jz      loc_1800671DE
0x180067005  mov     [rbp+3Fh+hMem], rax
0x180067009  mov     r9, [rbp+3Fh+arg_30]
0x18006700d  mov     rdx, [rbp+3Fh+hMem]
0x180067011  mov     ecx, r13d
0x180067014  mov     eax, [r9]
0x180067017  mov     [rdx+rcx*4], eax
0x18006701a  mov     rcx, [rbp+3Fh+arg_28]
0x18006701e  mov     eax, [rbp+3Fh+var_98]
0x180067021  mov     r15, [rbp+3Fh+var_88]
0x180067025  add     [rcx], eax
0x180067027  xor     ecx, ecx
0x180067029  mov     rax, [rbp+3Fh+arg_30]
0x18006702d  inc     dword ptr [rax]
0x18006702f  test    [r15+10h], bl
0x180067033  jz      loc_1800670DC
0x180067039  cmp     [rbp+3Fh+var_B0], cl
0x18006703c  jz      short loc_180067065
0x18006703e  mov     rax, [r15+8]
0x180067042  lea     rdx, aNlreadfilefore_10; "NlReadFileForestTrustList: %ws: Duplica"...
0x180067049  mov     r9, [r15]
0x18006704c  sub     rdi, r14
0x18006704f  mov     qword ptr [rsp+110h+var_E8], rdi
0x180067054  mov     r8, r12
0x180067057  mov     ecx, esi; unsigned int
0x180067059  mov     qword ptr [rsp+110h+var_F0], rax
0x18006705e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180067063  xor     ecx, ecx
0x180067065  mov     rax, [rbp+3Fh+arg_0]
0x180067069  mov     [rbp+3Fh+var_B0], 1
0x18006706d  test    rax, rax
0x180067070  jz      short loc_1800670DC
0x180067072  mov     rcx, [r15]
0x180067075  test    rcx, rcx
0x180067078  jz      short loc_180067093
0x18006707a  xor     r9d, r9d
0x18006707d  lea     rdx, [rax+48h]
0x180067081  lea     r8d, [r9+6]
0x180067085  call    cs:__imp_NetpwNameCompare
0x18006708b  test    eax, eax
0x18006708d  jnz     short loc_1800670B3
0x18006708f  mov     rax, [rbp+3Fh+arg_0]
0x180067093  mov     rcx, [r15+8]; unsigned __int16 *
0x180067097  test    rcx, rcx
0x18006709a  jz      short loc_1800670DA
0x18006709c  mov     rdx, [rax+90h]; unsigned __int16 *
0x1800670a3  test    rdx, rdx
0x1800670a6  jz      short loc_1800670DA
0x1800670a8  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x1800670ad  xor     ecx, ecx
0x1800670af  test    eax, eax
0x1800670b1  jnz     short loc_1800670DC
0x1800670b3  mov     rax, [r15+8]
0x1800670b7  lea     rdx, aNlreadfilefore_11; "NlReadFileForestTrustList: %ws: Log fil"...
0x1800670be  mov     r9, [r15]
0x1800670c1  mov     r8, r12
0x1800670c4  mov     ecx, esi; unsigned int
0x1800670c6  mov     qword ptr [rsp+110h+var_F0], rax
0x1800670cb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800670d0  mov     ebx, 54Bh
0x1800670d5  jmp     loc_1800671DE
  ... truncated ...
```
