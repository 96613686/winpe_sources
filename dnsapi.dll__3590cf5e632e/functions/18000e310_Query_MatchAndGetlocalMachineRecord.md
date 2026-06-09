# Query_MatchAndGetlocalMachineRecord

- ea: `0x18000e310`
- end: `0x18000edc9`
- name: `Query_MatchAndGetlocalMachineRecord`
- size: `2745`
- prototype: `__int64 __usercall@<rax>(PCNZWCH lpString1@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000dfb8`

## callees

- `0x180005b10`
- `0x180005c1c`
- `0x18000ce40`
- `0x18000ceb8`
- `0x18000d1bc`
- `0x18000df9c`
- `0x18000e310`
- `0x180011d40`
- `0x18002b050`
- `0x18002e894`
- `0x18008b5f0`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed48`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e3ca`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e533`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e59f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e6ed`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e3ca`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e533`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e59f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e6ed`
- `IPHLPAPI!FreeMibTable` at `0x18000eac5`
- `IPHLPAPI!FreeMibTable` at `0x18000eb43`
- `IPHLPAPI!FreeMibTable` at `0x18000edb8`
- `IPHLPAPI!FreeMibTable` at `0x18000eac5`
- `IPHLPAPI!FreeMibTable` at `0x18000eb43`
- `IPHLPAPI!FreeMibTable` at `0x18000edb8`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18000e72e`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18000eaf4`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18000e72e`
- `IPHLPAPI!GetUnicastIpAddressTable` at `0x18000eaf4`

## pseudocode

```c
__int64 __fastcall Query_MatchAndGetlocalMachineRecord(
        WCHAR *lpString1,
        __int16 a2,
        unsigned int a3,
        int a4,
        _DWORD *a5,
        _QWORD *a6)
{
  __int64 v8; // r13
  __int64 cchCount2; // r9
  int v10; // eax
  int v11; // esi
  signed __int32 v12; // eax
  __int64 v13; // r14
  __int64 *v14; // rax
  WCHAR *v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r9
  bool v18; // zf
  WCHAR *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  WCHAR *v22; // r8
  __int64 *v23; // rax
  WCHAR *v24; // rcx
  unsigned int UnicastIpAddressTable; // r15d
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 v30; // rcx
  WCHAR *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r12
  const wchar_t *v34; // rcx
  WCHAR *v35; // rdx
  WCHAR *v36; // rcx
  void *v37; // r12
  __int64 v39; // r9
  unsigned int v40; // r14d
  PMIB_UNICASTIPADDRESS_TABLE v41; // rdi
  __int64 v42; // rbx
  __int64 v43; // rdx
  __int64 v44; // r9
  __int64 v45; // r8
  char *v46; // rsi
  __int16 v47; // ax
  int v48; // esi
  __int64 Record; // r14
  __int64 v50; // rax
  int v51; // eax
  BOOL v52; // esi
  __int64 FullHostName; // rax
  void *v54; // rdi
  WCHAR *v55; // r8
  __int64 v56; // rcx
  WCHAR *v57; // rdx
  __int64 v58; // r9
  WCHAR *v59; // rcx
  WCHAR *HostName; // rax
  __int64 v61; // rcx
  WCHAR *v62; // rdx
  WCHAR *v63; // r8
  __int64 v64; // r9
  WCHAR *v65; // rcx
  __int64 v66; // rdx
  WCHAR *v67; // r8
  __int64 v68; // r9
  __int64 *v69; // rax
  __int64 *v70; // rcx
  __int64 v71; // rdx
  WCHAR *v72; // r8
  __int64 v73; // r9
  __int64 *v74; // rax
  __int64 *v75; // rcx
  __int128 *v76; // rcx
  __int128 v77; // xmm6
  __int64 v78; // rax
  int v79; // eax
  __int64 v80; // rax
  unsigned int v81; // eax
  unsigned int LoopbackRecords; // eax
  DWORD LastError; // eax
  DWORD v84; // eax
  int v85; // [rsp+30h] [rbp-D0h]
  int v86; // [rsp+34h] [rbp-CCh]
  void *v89; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v90; // [rsp+50h] [rbp-B0h]
  _DWORD *v91; // [rsp+58h] [rbp-A8h]
  PMIB_UNICASTIPADDRESS_TABLE Table[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR lpString2[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String2[256]; // [rsp+270h] [rbp+170h] BYREF

  v91 = a5;
  v8 = -1;
  v90 = a6;
  v89 = 0;
  Table[0] = 0;
  if ( lpString1 == L"..localmachine" )
  {
    v10 = 1;
  }
  else
  {
    if ( !lpString1 )
      goto LABEL_7;
    cchCount2 = -1;
    do
      ++cchCount2;
    while ( lpString1[cchCount2] );
    if ( (_DWORD)cchCount2 != 14 )
    {
      if ( (_DWORD)cchCount2 != 15 || lpString1[14] != 46 )
        goto LABEL_7;
      LODWORD(cchCount2) = 14;
    }
    if ( CompareStringW(0x7Fu, 1u, lpString1, cchCount2, L"..localmachine", cchCount2) != 2 )
    {
LABEL_7:
      v10 = 0;
      goto LABEL_8;
    }
    v10 = 1;
  }
LABEL_8:
  v11 = 0;
  v85 = v10;
  if ( !v10 )
    v11 = a4;
  v86 = v11;
  String2[0] = 0;
  lpString2[0] = 0;
  v12 = _InterlockedCompareExchange(&dword_180111A74, 2, 0);
  if ( v12 == 1 )
  {
    v13 = 2147483646;
    v14 = qword_180112000;
    v15 = String2;
    v16 = 2147483646;
    v17 = 256;
    do
    {
      if ( !v16 )
        break;
      if ( !*(_WORD *)v14 )
        break;
      *v15 = *(_WORD *)v14;
      v14 = (__int64 *)((char *)v14 + 2);
      ++v15;
      --v16;
      --v17;
    }
    while ( v17 );
    v18 = v17 == 0;
    v19 = v15 - 1;
    v20 = 2147483646;
    v21 = 256;
    if ( !v18 )
      v19 = v15;
    v22 = lpString2;
    *v19 = 0;
    v23 = qword_180112200;
    do
    {
      if ( !v20 )
        break;
      if ( !*(_WORD *)v23 )
        break;
      *v22 = *(_WORD *)v23;
      v23 = (__int64 *)((char *)v23 + 2);
      ++v22;
      --v20;
      --v21;
    }
    while ( v21 );
    v24 = v22 - 1;
    if ( v21 )
      v24 = v22;
    UnicastIpAddressTable = 0;
    *v24 = 0;
    goto LABEL_24;
  }
  v52 = v12 != 2;
  FullHostName = Reg_GetFullHostName(1);
  v54 = (void *)FullHostName;
  v13 = 2147483646;
  if ( FullHostName )
  {
    UnicastIpAddressTable = 0;
    v55 = String2;
    v56 = 2147483646;
    v57 = (WCHAR *)FullHostName;
    v58 = 256;
    do
    {
      if ( !v56 )
        break;
      if ( !*v57 )
        break;
      *v55++ = *v57++;
      --v56;
      --v58;
    }
    while ( v58 );
    v59 = v55 - 1;
    if ( v58 )
      v59 = v55;
    *v59 = 0;
  }
  else
  {
    LastError = GetLastError();
    UnicastIpAddressTable = LastError;
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_d(1035, 24, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, LastError);
    v52 = 0;
  }
  DnsApiFree(v54);
  HostName = (WCHAR *)Reg_GetHostName(1);
  if ( HostName )
  {
    v61 = 2147483646;
    v62 = lpString2;
    v63 = HostName;
    v64 = 256;
    do
    {
      if ( !v61 )
        break;
      if ( !*v63 )
        break;
      *v62++ = *v63++;
      --v61;
      --v64;
    }
    while ( v64 );
    v65 = v62 - 1;
    if ( v64 )
      v65 = v62;
    *v65 = 0;
    DnsApiFree(HostName);
    if ( v52 )
    {
      if ( UnicastIpAddressTable )
      {
        _InterlockedExchange(&dword_180111A74, 0);
        goto LABEL_52;
      }
      v66 = 2147483646;
      v67 = String2;
      v68 = 256;
      v69 = qword_180112000;
      do
      {
        if ( !v66 )
          break;
        if ( !*v67 )
          break;
        *(_WORD *)v69 = *v67++;
        v69 = (__int64 *)((char *)v69 + 2);
        --v66;
        --v68;
      }
      while ( v68 );
      v70 = (__int64 *)((char *)v69 - 2);
      v71 = 2147483646;
      v72 = lpString2;
      if ( v68 )
        v70 = v69;
      v73 = 256;
      *(_WORD *)v70 = 0;
      v74 = qword_180112200;
      do
      {
        if ( !v71 )
          break;
        if ( !*v72 )
          break;
        *(_WORD *)v74 = *v72++;
        v74 = (__int64 *)((char *)v74 + 2);
        --v71;
        --v73;
      }
      while ( v73 );
      v11 = v86;
      v75 = (__int64 *)((char *)v74 - 2);
      if ( v73 )
        v75 = v74;
      *(_WORD *)v75 = 0;
      _InterlockedExchange(&dword_180111A74, 1);
      goto LABEL_24;
    }
  }
  else
  {
    v84 = GetLastError();
    UnicastIpAddressTable = v84;
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_d(1035, 25, WPP_df5265f5adb03ed46da236b8e39fbd95_Traceguids, v84);
    DnsApiFree(0);
  }
  if ( UnicastIpAddressTable )
    goto LABEL_52;
  v11 = v86;
LABEL_24:
  if ( lpString1 == String2 )
    goto LABEL_64;
  if ( !lpString1 )
    goto LABEL_39;
  v26 = -1;
  do
    ++v26;
  while ( lpString1[v26] );
  v27 = -1;
  do
    ++v27;
  while ( String2[v27] );
  if ( (_DWORD)v27 == (_DWORD)v26 )
    goto LABEL_31;
  if ( (_DWORD)v27 == (_DWORD)v26 + 1 )
  {
    if ( String2[(int)v26] == 46 )
    {
LABEL_31:
      if ( CompareStringW(0x7Fu, 1u, lpString1, v26, String2, v26) == 2 )
        goto LABEL_64;
    }
  }
  else if ( (_DWORD)v27 + 1 == (_DWORD)v26 && lpString1[(int)v27] == 46 )
  {
    LODWORD(v26) = v27;
    goto LABEL_31;
  }
  if ( lpString1 == lpString2 )
    goto LABEL_64;
  v28 = -1;
  do
    ++v28;
  while ( lpString1[v28] );
  v29 = -1;
  do
    ++v29;
  while ( lpString2[v29] );
  if ( (_DWORD)v29 != (_DWORD)v28 )
  {
    if ( (_DWORD)v29 == (_DWORD)v28 + 1 )
    {
      if ( lpString2[(int)v28] != 46 )
        goto LABEL_39;
    }
    else
    {
      if ( (_DWORD)v29 + 1 != (_DWORD)v28 || lpString1[(int)v29] != 46 )
        goto LABEL_39;
      LODWORD(v28) = v29;
    }
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, v28, lpString2, v28) == 2 )
    goto LABEL_64;
LABEL_39:
  v30 = 256;
  v31 = lpString2;
  do
  {
    if ( !*v31 )
      break;
    ++v31;
    --v30;
  }
  while ( v30 );
  v32 = 256 - v30;
  if ( v30 )
  {
    v33 = v30;
    v34 = L".local";
    v35 = &lpString2[v32];
    do
    {
      if ( !v13 )
        break;
      if ( !*v34 )
        break;
      *v35++ = *v34++;
      --v13;
      --v33;
    }
    while ( v33 );
    v36 = v35 - 1;
    if ( v33 )
      v36 = v35;
    *v36 = 0;
    if ( v33 )
    {
      if ( lpString1 )
      {
        v39 = -1;
        do
          ++v39;
        while ( lpString1[v39] );
        do
          ++v8;
        while ( lpString2[v8] );
        if ( (_DWORD)v8 != (_DWORD)v39 )
        {
          if ( (_DWORD)v8 == (_DWORD)v39 + 1 )
          {
            if ( lpString2[(int)v39] != 46 )
              goto LABEL_50;
          }
          else
          {
            if ( (_DWORD)v8 + 1 != (_DWORD)v39 || lpString1[(int)v8] != 46 )
              goto LABEL_50;
            LODWORD(v39) = v8;
          }
        }
        if ( CompareStringW(0x7Fu, 1u, lpString1, v39, lpString2, v39) == 2 )
          goto LABEL_64;
      }
    }
  }
LABEL_50:
  if ( !v85 )
  {
    UnicastIpAddressTable = 9003;
LABEL_52:
    v37 = 0;
    goto LABEL_53;
  }
LABEL_64:
  v40 = a3;
  *v91 = 1;
  if ( a2 != 1 && !a3 )
  {
    v37 = 0;
    goto LABEL_132;
  }
  UnicastIpAddressTable = GetUnicastIpAddressTable(2u, Table);
  if ( UnicastIpAddressTable )
    goto LABEL_52;
  v41 = Table[0];
  v42 = 0;
  v37 = 0;
  v43 = 0;
  if ( !Table[0] )
    goto LABEL_128;
  v44 = 4;
  v45 = 16;
  while ( (unsigned int)v42 < v41->NumEntries )
  {
    v46 = (char *)v41 + 80 * v42;
    if ( *((_DWORD *)v46 + 18) == 4 && (!v86 || !v46[69]) )
    {
      v47 = *((_WORD *)v46 + 4);
      if ( v47 == 2 )
      {
        v48 = *((_DWORD *)v46 + 3);
        if ( v48 == 16777343 )
          goto LABEL_145;
        if ( v40 )
        {
          Record = Dns_AllocateRecord((unsigned int)v45);
          if ( Record )
          {
            v50 = Dns_StringCopyAllocate(String2, 0, 1, 1);
            if ( v50 )
            {
              *(_QWORD *)(Record + 8) = v50;
              v51 = *(_DWORD *)(Record + 20);
              *(_DWORD *)(Record + 16) = 1048604;
              *(_DWORD *)(Record + 24) = 1200;
              *(_DWORD *)(Record + 20) = v51 & 0xFFFFDFE7 | 0x2008;
              *(_QWORD *)(Record + 32) = 0;
              *(_DWORD *)(Record + 40) = -65536;
              *(_DWORD *)(Record + 44) = v48;
LABEL_142:
              if ( !Record )
                goto LABEL_167;
              v43 = 1;
LABEL_144:
              *(_QWORD *)Record = v37;
              v45 = 16;
              v37 = (void *)Record;
              v89 = (void *)Record;
              v44 = 4;
              goto LABEL_145;
            }
LABEL_165:
            DnsApiFree((LPVOID)Record);
          }
        }
        else
        {
          Record = Dns_AllocateRecord((unsigned int)v44);
          if ( Record )
          {
            v80 = Dns_StringCopyAllocate(String2, 0, 1, 1);
            if ( v80 )
            {
              *(_QWORD *)(Record + 8) = v80;
              v81 = *(_DWORD *)(Record + 20) & 0xFFFFFFEF;
              *(_DWORD *)(Record + 16) = 262145;
              *(_DWORD *)(Record + 24) = 1200;
              *(_DWORD *)(Record + 20) = v81 | 0x2008;
              *(_DWORD *)(Record + 32) = v48;
              goto LABEL_142;
            }
            goto LABEL_165;
          }
        }
        Record = 0;
        goto LABEL_142;
      }
      if ( v47 == 23 && !(unsigned int)IP6_IS_ADDR_LOOPBACK(v46 + 16, v43, v45, v44) )
      {
        v77 = *v76;
        Record = Dns_AllocateRecord((unsigned int)v45);
        if ( !Record )
          goto LABEL_167;
        v78 = Dns_StringCopyAllocate(String2, 0, 1, 1);
        if ( !v78 )
        {
          DnsApiFree((LPVOID)Record);
LABEL_167:
          UnicastIpAddressTable = 14;
          goto LABEL_53;
        }
        *(_QWORD *)(Record + 8) = v78;
        v43 = 1;
        v79 = *(_DWORD *)(Record + 20);
        *(_DWORD *)(Record + 16) = 1048604;
        *(_DWORD *)(Record + 24) = 1200;
        *(_DWORD *)(Record + 20) = v79 & 0xFFFFDFE7 | 0x2008;
        *(_OWORD *)(Record + 32) = v77;
        *(_WORD *)(Record + 30) = *((_WORD *)v46 + 16);
        goto LABEL_144;
      }
    }
LABEL_145:
    v40 = a3;
    v42 = (unsigned int)(v42 + 1);
  }
  v11 = v86;
LABEL_128:
  UnicastIpAddressTable = 0;
  if ( !(_DWORD)v43 )
  {
    LoopbackRecords = GetLoopbackRecords(String2, 1, v40, &v89);
    v37 = v89;
    UnicastIpAddressTable = LoopbackRecords;
  }
  if ( !UnicastIpAddressTable )
  {
    FreeMibTable(Table[0]);
    Table[0] = 0;
LABEL_132:
    if ( a2 == 28 )
    {
      UnicastIpAddressTable = GetUnicastIpAddressTable(0x17u, Table);
      if ( !UnicastIpAddressTable )
      {
        UnicastIpAddressTable = GetDnsRecordsFromUnicastAddressTable(
                                  (unsigned int)String2,
                                  28,
                                  v40,
                                  v11,
                                  (__int64)Table[0],
                                  (__int64)&v89);
        if ( !UnicastIpAddressTable )
        {
          FreeMibTable(Table[0]);
          *v90 = v89;
          return UnicastIpAddressTable;
        }
        v37 = v89;
      }
    }
  }
LABEL_53:
  if ( Table[0] )
    FreeMibTable(Table[0]);
  if ( UnicastIpAddressTable && v37 )
  {
    Dns_RecordListFree(v37);
    *v90 = 0;
  }
  else
  {
    *v90 = v37;
  }
  return UnicastIpAddressTable;
}

```

## disassembly

```asm
0x18000e310  mov     [rsp-8+arg_18], rbx
0x18000e315  push    rbp
0x18000e316  push    rsi
0x18000e317  push    rdi
0x18000e318  push    r13
0x18000e31a  push    r14
0x18000e31c  lea     rbp, [rsp-390h]
0x18000e324  sub     rsp, 490h
0x18000e32b  mov     rax, cs:__security_cookie
0x18000e332  xor     rax, rsp
0x18000e335  mov     [rbp+3B0h+var_40], rax
0x18000e33c  mov     rax, [rbp+3B0h+arg_20]
0x18000e343  mov     edi, r9d
0x18000e346  mov     [rsp+4B0h+var_458], rax
0x18000e34b  mov     rbx, rcx
0x18000e34e  mov     rax, [rbp+3B0h+arg_28]
0x18000e355  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000e35c  mov     [rsp+4B0h+var_460], rax
0x18000e361  mov     r14d, 1
0x18000e367  xor     eax, eax
0x18000e369  mov     [rsp+4B0h+var_474], r8d
0x18000e36e  mov     [rsp+4B0h+lpMem], rax
0x18000e373  mov     [rsp+4B0h+var_468], rax
0x18000e378  lea     rax, aLocalmachine; "..localmachine"
0x18000e37f  mov     [rsp+4B0h+var_478], dx
0x18000e384  mov     [rsp+4B0h+Table], 0
0x18000e38d  cmp     rcx, rax
0x18000e390  jz      loc_18000ED08
0x18000e396  test    rcx, rcx
0x18000e399  jz      short loc_18000E3DF
0x18000e39b  mov     r9, r13
0x18000e39e  xchg    ax, ax
0x18000e3a0  inc     r9; cchCount1
0x18000e3a3  cmp     word ptr [rcx+r9*2], 0
0x18000e3a9  jnz     short loc_18000E3A0
0x18000e3ab  cmp     r9d, 0Eh
0x18000e3af  jnz     loc_18000E944
0x18000e3b5  mov     [rsp+4B0h+cchCount2], r9d; cchCount2
0x18000e3ba  mov     r8, rbx; lpString1
0x18000e3bd  mov     edx, r14d; dwCmpFlags
0x18000e3c0  mov     [rsp+4B0h+lpString2], rax; lpString2
0x18000e3c5  mov     ecx, 7Fh; Locale
0x18000e3ca  call    cs:__imp_CompareStringW
0x18000e3d1  nop     dword ptr [rax+rax+00h]
0x18000e3d6  cmp     eax, 2
0x18000e3d9  jz      loc_18000E9FA
0x18000e3df  xor     eax, eax
0x18000e3e1  xor     esi, esi
0x18000e3e3  mov     [rsp+4B0h+arg_8], r12
0x18000e3eb  test    eax, eax
0x18000e3ed  mov     [rsp+4B0h+var_480], eax
0x18000e3f1  mov     [rsp+4B0h+arg_10], r15
0x18000e3f9  mov     ecx, 2
0x18000e3fe  cmovz   esi, edi
0x18000e401  movaps  [rsp+4B0h+var_30], xmm6
0x18000e409  xor     eax, eax
0x18000e40b  mov     [rsp+4B0h+var_47C], esi
0x18000e40f  mov     [rbp+3B0h+String2], ax
0x18000e416  mov     [rsp+4B0h+var_440], ax
0x18000e41b  lock cmpxchg cs:dword_180111A74, ecx
0x18000e423  cmp     eax, r14d
0x18000e426  jnz     loc_18000E852
0x18000e42c  mov     r14d, 7FFFFFFEh
0x18000e432  lea     rax, qword_180112000
0x18000e439  mov     r12d, 100h
0x18000e43f  lea     r8, [rbp+3B0h+String2]
0x18000e446  mov     edx, r14d
0x18000e449  mov     r9d, r12d
0x18000e44c  nop     dword ptr [rax+00h]
0x18000e450  test    rdx, rdx
0x18000e453  jz      short loc_18000E472
0x18000e455  movzx   ecx, word ptr [rax]
0x18000e458  test    cx, cx
0x18000e45b  jz      short loc_18000E472
0x18000e45d  mov     [r8], cx
0x18000e461  add     rax, 2
0x18000e465  add     r8, 2
0x18000e469  dec     rdx
0x18000e46c  sub     r9, 1
0x18000e470  jnz     short loc_18000E450
0x18000e472  test    r9, r9
0x18000e475  lea     rcx, [r8-2]
0x18000e479  mov     rdx, r14
0x18000e47c  mov     r9, r12
0x18000e47f  cmovnz  rcx, r8
0x18000e483  xor     eax, eax
0x18000e485  lea     r8, [rsp+4B0h+var_440]
0x18000e48a  mov     [rcx], ax
0x18000e48d  lea     rax, qword_180112200
0x18000e494  test    rdx, rdx
0x18000e497  jz      short loc_18000E4B6
0x18000e499  movzx   ecx, word ptr [rax]
0x18000e49c  test    cx, cx
0x18000e49f  jz      short loc_18000E4B6
0x18000e4a1  mov     [r8], cx
0x18000e4a5  add     rax, 2
0x18000e4a9  add     r8, 2
0x18000e4ad  dec     rdx
0x18000e4b0  sub     r9, 1
0x18000e4b4  jnz     short loc_18000E494
0x18000e4b6  test    r9, r9
0x18000e4b9  lea     rcx, [r8-2]
0x18000e4bd  cmovnz  rcx, r8
0x18000e4c1  xor     eax, eax
0x18000e4c3  xor     r15d, r15d
0x18000e4c6  mov     [rcx], ax
0x18000e4c9  mov     edi, 1
0x18000e4ce  lea     rax, [rbp+3B0h+String2]
0x18000e4d5  cmp     rbx, rax
0x18000e4d8  jz      loc_18000E702
0x18000e4de  test    rbx, rbx
0x18000e4e1  jz      loc_18000E5B4
0x18000e4e7  mov     r9, r13
0x18000e4ea  nop     word ptr [rax+rax+00h]
0x18000e4f0  inc     r9; cchCount1
0x18000e4f3  cmp     word ptr [rbx+r9*2], 0
0x18000e4f9  jnz     short loc_18000E4F0
0x18000e4fb  lea     rax, [rbp+3B0h+String2]
0x18000e502  mov     rcx, r13
0x18000e505  inc     rcx
0x18000e508  cmp     word ptr [rax+rcx*2], 0
0x18000e50d  jnz     short loc_18000E505
0x18000e50f  cmp     ecx, r9d
0x18000e512  jnz     loc_18000E96E
0x18000e518  lea     rax, [rbp+3B0h+String2]
0x18000e51f  mov     [rsp+4B0h+cchCount2], r9d; cchCount2
0x18000e524  mov     r8, rbx; lpString1
0x18000e527  mov     [rsp+4B0h+lpString2], rax; lpString2
0x18000e52c  mov     edx, edi; dwCmpFlags
0x18000e52e  mov     ecx, 7Fh; Locale
0x18000e533  call    cs:__imp_CompareStringW
0x18000e53a  nop     dword ptr [rax+rax+00h]
0x18000e53f  cmp     eax, 2
0x18000e542  jz      loc_18000E702
0x18000e548  lea     rax, [rsp+4B0h+var_440]
0x18000e54d  cmp     rbx, rax
0x18000e550  jz      loc_18000E702
0x18000e556  mov     r9, r13
0x18000e559  nop     dword ptr [rax+00000000h]
0x18000e560  inc     r9; cchCount1
0x18000e563  cmp     word ptr [rbx+r9*2], 0
0x18000e569  jnz     short loc_18000E560
0x18000e56b  lea     rax, [rsp+4B0h+var_440]
0x18000e570  mov     rcx, r13
0x18000e573  inc     rcx
0x18000e576  cmp     word ptr [rax+rcx*2], 0
0x18000e57b  jnz     short loc_18000E573
0x18000e57d  cmp     ecx, r9d
0x18000e580  jnz     loc_18000E99C
0x18000e586  lea     rax, [rsp+4B0h+var_440]
0x18000e58b  mov     [rsp+4B0h+cchCount2], r9d; cchCount2
0x18000e590  mov     r8, rbx; lpString1
0x18000e593  mov     [rsp+4B0h+lpString2], rax; lpString2
0x18000e598  mov     edx, edi; dwCmpFlags
0x18000e59a  mov     ecx, 7Fh; Locale
0x18000e59f  call    cs:__imp_CompareStringW
0x18000e5a6  nop     dword ptr [rax+rax+00h]
0x18000e5ab  cmp     eax, 2
0x18000e5ae  jz      loc_18000E702
0x18000e5b4  mov     rcx, r12
0x18000e5b7  lea     rax, [rsp+4B0h+var_440]
0x18000e5bc  nop     dword ptr [rax+00h]
0x18000e5c0  cmp     word ptr [rax], 0
0x18000e5c4  jz      short loc_18000E5D0
0x18000e5c6  add     rax, 2
0x18000e5ca  sub     rcx, 1
0x18000e5ce  jnz     short loc_18000E5C0
0x18000e5d0  xor     eax, eax
0x18000e5d2  mov     rdx, r12
0x18000e5d5  sub     rdx, rcx
0x18000e5d8  test    rcx, rcx
0x18000e5db  cmovz   rdx, rax
0x18000e5df  jz      short loc_18000E628
0x18000e5e1  sub     r12, rdx
0x18000e5e4  lea     rcx, aLocal_2; ".local"
0x18000e5eb  lea     rdx, [rsp+rdx*2+4B0h+var_440]
0x18000e5f0  jz      short loc_18000E613
0x18000e5f2  test    r14, r14
0x18000e5f5  jz      short loc_18000E613
0x18000e5f7  movzx   eax, word ptr [rcx]
0x18000e5fa  test    ax, ax
0x18000e5fd  jz      short loc_18000E613
0x18000e5ff  mov     [rdx], ax
0x18000e602  add     rcx, 2
0x18000e606  add     rdx, 2
0x18000e60a  dec     r14
0x18000e60d  sub     r12, 1
0x18000e611  jnz     short loc_18000E5F2
0x18000e613  test    r12, r12
0x18000e616  lea     rcx, [rdx-2]
0x18000e61a  cmovnz  rcx, rdx
0x18000e61e  xor     eax, eax
0x18000e620  mov     [rcx], ax
0x18000e623  test    r12, r12
0x18000e626  jnz     short loc_18000E69F
0x18000e628  cmp     [rsp+4B0h+var_480], 0
0x18000e62d  jnz     loc_18000E702
0x18000e633  mov     r15d, 232Bh
0x18000e639  mov     r12, [rsp+4B0h+lpMem]
0x18000e63e  mov     rcx, [rsp+4B0h+Table]; Memory
0x18000e643  test    rcx, rcx
0x18000e646  jnz     loc_18000EDB8
0x18000e64c  test    r15d, r15d
0x18000e64f  jnz     loc_18000E832
0x18000e655  mov     rcx, [rsp+4B0h+var_460]
0x18000e65a  mov     [rcx], r12
0x18000e65d  movaps  xmm6, [rsp+4B0h+var_30]
0x18000e665  mov     eax, r15d
0x18000e668  mov     r15, [rsp+4B0h+arg_10]
0x18000e670  mov     r12, [rsp+4B0h+arg_8]
0x18000e678  mov     rcx, [rbp+3B0h+var_40]
0x18000e67f  xor     rcx, rsp; StackCookie
0x18000e682  call    __security_check_cookie
0x18000e687  mov     rbx, [rsp+4B0h+arg_18]
0x18000e68f  add     rsp, 490h
0x18000e696  pop     r14
0x18000e698  pop     r13
0x18000e69a  pop     rdi
0x18000e69b  pop     rsi
0x18000e69c  pop     rbp
0x18000e69d  retn
0x18000e69f  test    rbx, rbx
0x18000e6a2  jz      short loc_18000E628
0x18000e6a4  mov     r9, r13
0x18000e6a7  nop     word ptr [rax+rax+00000000h]
0x18000e6b0  inc     r9; cchCount1
0x18000e6b3  cmp     [rbx+r9*2], ax
0x18000e6b8  jnz     short loc_18000E6B0
0x18000e6ba  lea     rax, [rsp+4B0h+var_440]
0x18000e6bf  nop
0x18000e6c0  inc     r13
0x18000e6c3  cmp     word ptr [rax+r13*2], 0
0x18000e6c9  jnz     short loc_18000E6C0
0x18000e6cb  cmp     r13d, r9d
0x18000e6ce  jnz     loc_18000E9CA
0x18000e6d4  lea     rax, [rsp+4B0h+var_440]
0x18000e6d9  mov     [rsp+4B0h+cchCount2], r9d; cchCount2
0x18000e6de  mov     r8, rbx; lpString1
0x18000e6e1  mov     [rsp+4B0h+lpString2], rax; lpString2
0x18000e6e6  mov     edx, edi; dwCmpFlags
0x18000e6e8  mov     ecx, 7Fh; Locale
0x18000e6ed  call    cs:__imp_CompareStringW
0x18000e6f4  nop     dword ptr [rax+rax+00h]
0x18000e6f9  cmp     eax, 2
0x18000e6fc  jnz     loc_18000E628
0x18000e702  mov     rax, [rsp+4B0h+var_458]
0x18000e707  mov     ebx, 1Ch
0x18000e70c  movzx   r13d, [rsp+4B0h+var_478]
0x18000e712  mov     r14d, [rsp+4B0h+var_474]
0x18000e717  mov     [rax], edi
0x18000e719  cmp     r13w, 1
0x18000e71e  jnz     loc_18000EC83
0x18000e724  mov     ecx, 2; Family
0x18000e729  lea     rdx, [rsp+4B0h+Table]; Table
0x18000e72e  call    cs:__imp_GetUnicastIpAddressTable
0x18000e735  nop     dword ptr [rax+rax+00h]
0x18000e73a  mov     r15d, eax
0x18000e73d  test    eax, eax
0x18000e73f  jnz     loc_18000E639
0x18000e745  mov     rdi, [rsp+4B0h+Table]
0x18000e74a  xor     ebx, ebx
0x18000e74c  mov     r12, [rsp+4B0h+lpMem]
0x18000e751  xor     edx, edx
0x18000e753  test    rdi, rdi
0x18000e756  jz      loc_18000EAAC
0x18000e75c  mov     r15d, [rsp+4B0h+var_47C]
0x18000e761  mov     r9d, 4
0x18000e767  mov     r8d, 10h
0x18000e76d  cmp     ebx, [rdi]
0x18000e76f  jnb     loc_18000EDA6
0x18000e775  lea     rsi, [rbx+rbx*4]
0x18000e779  shl     rsi, 4
0x18000e77d  add     rsi, rdi
0x18000e780  cmp     dword ptr [rsi+48h], 4
0x18000e784  jnz     loc_18000EC18
0x18000e78a  test    r15d, r15d
0x18000e78d  jz      short loc_18000E799
0x18000e78f  cmp     byte ptr [rsi+45h], 0
0x18000e793  jnz     loc_18000EC18
0x18000e799  movzx   eax, word ptr [rsi+8]
0x18000e79d  cmp     ax, 2
0x18000e7a1  jnz     loc_18000EB61
0x18000e7a7  mov     esi, [rsi+0Ch]
0x18000e7aa  cmp     esi, 100007Fh
0x18000e7b0  jz      loc_18000EC18
0x18000e7b6  test    r14d, r14d
0x18000e7b9  jz      loc_18000EC24
0x18000e7bf  mov     ecx, r8d
0x18000e7c2  call    Dns_AllocateRecord
0x18000e7c7  mov     r14, rax
0x18000e7ca  test    rax, rax
0x18000e7cd  jz      loc_18000EBEE
0x18000e7d3  mov     eax, 1
0x18000e7d8  lea     rcx, [rbp+3B0h+String2]
0x18000e7df  mov     r9d, eax
0x18000e7e2  mov     r8d, eax
0x18000e7e5  xor     edx, edx
0x18000e7e7  call    Dns_StringCopyAllocate
0x18000e7ec  test    rax, rax
0x18000e7ef  jz      loc_18000ED86
  ... truncated ...
```
