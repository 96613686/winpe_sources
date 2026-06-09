# Cache_FindEntry

- ea: `0x1800113b0`
- end: `0x180011c1c`
- name: `Cache_FindEntry`
- size: `2156`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpSrcStr@<rcx>, __int16, int, int)`
- caller_count: `6`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180010670`
- `0x1800111f0`
- `0x1800136fc`
- `0x1800159a8`
- `0x18002996c`
- `0x1800310bc`

## callees

- `0x1800113b0`
- `0x180011d50`
- `0x1800122e0`
- `0x180012970`
- `0x180029e28`
- `0x180029e48`
- `0x18002bec4`
- `0x18003d67c`
- `0x180040cd4`
- `0x180046ec0`
- `0x18007a6e8`
- `0x180083160`
- `0x180085fb8`
- `0x180086010`
- `0x180086384`
- `0x180086b1c`
- `0x180086c38`
- `0x180086cbc`
- `0x18008733c`

## import_xrefs

- `DNSAPI!DnsNameCompare_W` at `0x1800115bf`
- `DNSAPI!DnsNameCompare_W` at `0x1800115bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011b4a`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800114a7`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800114a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011811`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180011811`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011824`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180011824`

## pseudocode

```c
__int64 __fastcall Cache_FindEntry(
        WCHAR *lpSrcStr,
        WCHAR *a2,
        WCHAR *a3,
        __int64 a4,
        unsigned __int16 a5,
        int a6,
        int a7)
{
  __int64 v7; // r15
  __int64 v8; // r14
  int v9; // r13d
  int v10; // esi
  WCHAR *v11; // r12
  const WCHAR *v12; // rbx
  unsigned __int16 v13; // bp
  unsigned __int64 v14; // rcx
  int v15; // r9d
  int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // edi
  unsigned int v20; // ebx
  __int64 v21; // rdx
  unsigned __int64 v22; // rdi
  WCHAR *v23; // rbx
  __int64 v24; // rsi
  unsigned int v25; // eax
  WCHAR v26; // ax
  int v27; // ebp
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // esi
  unsigned int v34; // ebx
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // r9
  unsigned int v41; // eax
  int v42; // ecx
  int v43; // r8d
  __int64 v44; // rcx
  int v45; // edx
  int cchDest; // [rsp+28h] [rbp-2A0h]
  int v47; // [rsp+50h] [rbp-278h]
  WCHAR *v48; // [rsp+58h] [rbp-270h] BYREF
  WCHAR DestStr[264]; // [rsp+70h] [rbp-258h] BYREF

  v7 = 0;
  v47 = (int)a3;
  LOBYTE(v8) = 0;
  v48 = 0;
  v9 = a4;
  DestStr[0] = 0;
  v10 = (int)a3;
  v11 = a2;
  v12 = lpSrcStr;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    if ( a2 )
    {
      v44 = *((_QWORD *)a2 + 4);
      v45 = *((_DWORD *)a2 + 7);
    }
    else
    {
      v44 = 0;
      v45 = 0;
    }
    v13 = a5;
    WPP_SF_SlSddDl(v44, v45, a7, (_DWORD)v12, v45, v44, (char)a3, a5, a4, a7);
  }
  else
  {
    v13 = a5;
  }
  if ( v11 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF__SOCKADDR_(lpSrcStr, 26, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids, v11);
  if ( !g_HashTable )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(lpSrcStr, a2, a3, a4);
    goto LABEL_45;
  }
  if ( !v12 )
    goto LABEL_45;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_S(1035, 19, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids, v12);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SDl(v42, 12, v43, (_DWORD)v12, 0, 0);
  }
  v14 = -1;
  do
    ++v14;
  while ( v12[v14] );
  if ( v14 >= 0x100 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      WPP_SF_d(1035, 20, WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids, 122);
      goto LABEL_45;
    }
    return v7;
  }
  v15 = v14 + 1;
  DestStr[0] = 0;
  if ( (unsigned int)(v14 + 1) > 0x100 )
  {
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      WPP_SF_dSd(1055, 21, (unsigned int)WPP_cbc9ee43c5fe302a9f5529f24a263f79_Traceguids, 256, (__int64)v12, v15);
    SetLastError(0x7Au);
    goto LABEL_45;
  }
  v16 = LCMapStringW(0x7Fu, 0x100u, v12, v15, DestStr, 256);
  LODWORD(lpSrcStr) = v16 - 1;
  if ( (unsigned int)(v16 - 1) > 0xFF )
    goto LABEL_45;
  v17 = v16 - 1;
  if ( v17 > 1 )
  {
    v18 = v17 - 1;
    if ( DestStr[v18] == 46 )
      DestStr[(unsigned int)v18] = 0;
  }
  v19 = g_HashTableSize;
  a3 = DestStr;
  v20 = 0;
  v21 = 0;
  do
  {
    v20 = *((_DWORD *)qword_180095210 + ((unsigned __int64)*a3 >> 8))
        ^ __ROL4__(*((_DWORD *)qword_180095210 + (unsigned __int8)*a3) ^ __ROL4__(v20, 1), 1);
    if ( !*a3 )
      break;
    ++a3;
    v21 = (unsigned int)(v21 + 1);
  }
  while ( (_DWORD)v21 != -1 );
  if ( v11 )
  {
    if ( !(unsigned int)ServerInfoAddressValid(v11, v21, a3) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v39, v38, a3, v40);
    if ( *v11 == 2 )
    {
      v20 = *((_DWORD *)qword_180095210 + ((unsigned __int64)*((unsigned int *)v11 + 1) >> 24))
          ^ __ROL4__(
              *((_DWORD *)qword_180095210 + (unsigned __int8)BYTE2(*((_DWORD *)v11 + 1)))
            ^ __ROL4__(
                *((_DWORD *)qword_180095210 + (unsigned __int8)BYTE1(*((_DWORD *)v11 + 1)))
              ^ __ROL4__(*((_DWORD *)qword_180095210 + (unsigned __int8)*((_DWORD *)v11 + 1)) ^ __ROL4__(v20, 1), 1),
                1),
              1);
    }
    else if ( *v11 == 23 )
    {
      v20 = DnsComputeIn6AddrHash(v11 + 4, v20);
    }
    v20 = *((_DWORD *)qword_180095210 + ((unsigned __int64)*((unsigned int *)v11 + 7) >> 24))
        ^ __ROL4__(
            *((_DWORD *)qword_180095210 + (unsigned __int8)BYTE2(*((_DWORD *)v11 + 7)))
          ^ __ROL4__(
              *((_DWORD *)qword_180095210 + (unsigned __int8)BYTE1(*((_DWORD *)v11 + 7)))
            ^ __ROL4__(*((_DWORD *)qword_180095210 + (unsigned __int8)*((_DWORD *)v11 + 7)) ^ __ROL4__(v20, 1), 1),
              1),
            1);
    if ( *((_QWORD *)v11 + 4) )
    {
      v41 = WxComputePrefixHash();
      v20 = *((_DWORD *)qword_180095210 + ((unsigned __int64)v41 >> 24))
          ^ __ROL4__(
              *((_DWORD *)qword_180095210 + BYTE2(v41))
            ^ __ROL4__(
                *((_DWORD *)qword_180095210 + BYTE1(v41))
              ^ __ROL4__(*((_DWORD *)qword_180095210 + (unsigned __int8)v41) ^ __ROL4__(v20, 1), 1),
                1),
              1);
    }
  }
  LODWORD(a2) = v20 % v19;
  v8 = v20 % v19;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SD(1035, 27, (unsigned int)WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids, (unsigned int)DestStr, v20 % v19);
  lpSrcStr = (WCHAR *)g_HashTable;
  v22 = 16 * v8;
  v23 = (WCHAR *)*((_QWORD *)g_HashTable + 2 * v8);
  if ( v23 == (WCHAR *)((char *)g_HashTable + 16 * v8) )
  {
LABEL_22:
    if ( a7 )
    {
      Cache_CreateEntry((unsigned int)DestStr, (_DWORD)v11, v10, v9, a5, cchDest, (__int64)&v48);
      v7 = (__int64)v48;
    }
    goto LABEL_45;
  }
  while ( 1 )
  {
    v24 = *((_QWORD *)v23 + 14);
    v7 = (__int64)(v23 - 4);
    v48 = v23 - 4;
    if ( v24 )
      break;
LABEL_41:
    v23 = *(WCHAR **)v23;
    v7 = 0;
    v48 = 0;
    if ( v23 == &lpSrcStr[v22 / 2] )
      goto LABEL_67;
  }
  if ( !DnsNameCompare_W(DestStr, *((PCWSTR *)v23 + 4)) )
    goto LABEL_40;
  if ( !v11 )
  {
    if ( !v23[20] )
      goto LABEL_28;
LABEL_40:
    lpSrcStr = (WCHAR *)g_HashTable;
    goto LABEL_41;
  }
  if ( !(unsigned int)ServerInfoAddressValid(v11, a2, a3) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v30, v29, v31, v32);
  if ( !(unsigned int)ServerInfoEqual(v11, v23 + 20) )
    goto LABEL_40;
LABEL_28:
  if ( a6 )
    goto LABEL_66;
  if ( (v9 & 0x2000) != 0 && !(unsigned int)Idn_IsPunycode(*(_QWORD *)(v24 + 8))
    || (v9 & 0x4000) != 0 && (unsigned int)Idn_IsPunycode(*(_QWORD *)(v24 + 8)) )
  {
    goto LABEL_40;
  }
  LODWORD(lpSrcStr) = *((_DWORD *)v23 + 22);
  v25 = ((unsigned int)lpSrcStr >> 1) & 1;
  LODWORD(a2) = (unsigned __int8)lpSrcStr & 1;
  if ( ((unsigned __int8)lpSrcStr & 1) == 0 && !v25 || v23[48] != v13 )
  {
    LODWORD(a3) = v47;
    if ( *((_DWORD *)v23 + 23) == v47 )
    {
      if ( (v9 & 0x8000) != 0
        || ((unsigned __int8)lpSrcStr & 1) != 0
        || v25
        || (((unsigned __int8)v9 ^ (unsigned __int8)lpSrcStr) & 0x20) == 0
        && (((unsigned __int8)v9 ^ (unsigned __int8)lpSrcStr) & 0x40) == 0
        && (((unsigned __int16)v9 ^ (unsigned __int16)lpSrcStr) & 0x800) == 0
        && ((v9 & 8) == 0 || (((unsigned __int8)v9 ^ (unsigned __int8)lpSrcStr) & 4) == 0)
        && (((unsigned __int16)v9 ^ (unsigned __int16)lpSrcStr) & 0x1000) == 0
        && (((unsigned __int16)v9 ^ (unsigned __int16)lpSrcStr) & 0x400) == 0
        && ((v9 ^ (unsigned int)lpSrcStr) & 0x40000) == 0
        && ((v9 ^ (unsigned __int8)lpSrcStr) & 0x80u) == 0
        && (!g_fVelocityZtdns
         || (LODWORD(lpSrcStr) = v9 ^ (unsigned int)lpSrcStr, ((unsigned int)lpSrcStr & 0x80000) == 0)) )
      {
        v26 = v23[48];
        LODWORD(a2) = a5;
        if ( v26 == a5 )
          goto LABEL_66;
        if ( (v9 & 0x10000) != 0 )
          goto LABEL_66;
        LODWORD(lpSrcStr) = 255;
        if ( v26 == 255 && !*(_WORD *)(v24 + 18) )
          goto LABEL_66;
        if ( *(_WORD *)(v24 + 16) == 5 && a5 != 5 )
        {
          for ( lpSrcStr = *(WCHAR **)v24; lpSrcStr; lpSrcStr = *(WCHAR **)lpSrcStr )
          {
            if ( (*((_DWORD *)lpSrcStr + 5) & 3) == 1 && lpSrcStr[8] == a5 )
              goto LABEL_66;
          }
        }
        v13 = a5;
      }
    }
    goto LABEL_40;
  }
LABEL_66:
  if ( v23 == (WCHAR *)8 )
  {
LABEL_67:
    v10 = v47;
    goto LABEL_22;
  }
  v27 = 0;
  v33 = 1;
  if ( (*(_BYTE *)(v7 + 96) & 3) == 0 )
  {
    AcquireSRWLockShared(&SRWLock);
    v34 = dword_1800ABC2C;
    ReleaseSRWLockShared(&SRWLock);
    if ( *(_DWORD *)(v7 + 88) < v34 )
    {
      v27 = 1;
      if ( !a7 )
      {
        v7 = 0;
        goto LABEL_45;
      }
    }
  }
  if ( (v9 & 0x20000) == 0 || (*(_DWORD *)(v7 + 96) & 0x20000) != 0 )
  {
    v33 = 0;
  }
  else if ( !a7 )
  {
    v7 = 0;
    goto LABEL_45;
  }
  v35 = *(_QWORD *)(v7 + 120);
  if ( !v35
    || (*(_BYTE *)(v35 + 20) & 0xC0) == 0 && *(_DWORD *)(v35 + 24) <= (unsigned int)g_CurrentCacheTime
    || (v27 || v33) && a7 )
  {
    if ( !v27 && !v33 && (byte_1800AB58B & 0x10) != 0 )
      WPP_SF_Sdd(
        284,
        28,
        (unsigned int)WPP_24c6b60c4de03efdc0b32d9f61eefc6e_Traceguids,
        *(_QWORD *)(v7 + 40),
        *(_WORD *)(v7 + 104),
        *(_DWORD *)(v7 + 92));
    Cache_RemoveEntryFromHashTable((LPVOID)v7);
    v7 = 0;
    v48 = 0;
    goto LABEL_67;
  }
  v36 = v7 + 8;
  lpSrcStr = (WCHAR *)((char *)g_HashTable + v22);
  if ( *(_QWORD *)((char *)g_HashTable + v22) != v7 + 8 )
  {
    v37 = *(_QWORD *)v36;
    if ( *(_QWORD *)(*(_QWORD *)v36 + 8LL) != v36
      || (a3 = *(WCHAR **)(v7 + 16), *(_QWORD *)a3 != v36)
      || (*(_QWORD *)a3 = v37,
          *(_QWORD *)(v37 + 8) = a3,
          *(_QWORD *)(v7 + 16) = v7 + 8,
          *(_QWORD *)v36 = v36,
          a2 = *(WCHAR **)lpSrcStr,
          *(WCHAR **)(*(_QWORD *)lpSrcStr + 8LL) != lpSrcStr) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)v36 = a2;
    *(_QWORD *)(v7 + 16) = lpSrcStr;
    *((_QWORD *)a2 + 1) = v36;
    *(_QWORD *)lpSrcStr = v36;
  }
LABEL_45:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_Sdq((_DWORD)lpSrcStr, (_DWORD)a2, (_DWORD)a3, (unsigned int)DestStr, v8, v7);
  return v7;
}

```

## disassembly

```asm
0x1800113b0  push    rbx
0x1800113b2  push    rbp
0x1800113b3  push    rsi
0x1800113b4  push    r12
0x1800113b6  push    r13
0x1800113b8  push    r14
0x1800113ba  push    r15
0x1800113bc  sub     rsp, 290h
0x1800113c3  mov     rax, cs:__security_cookie
0x1800113ca  xor     rax, rsp
0x1800113cd  mov     [rsp+2C8h+var_48], rax
0x1800113d5  xor     r15d, r15d
0x1800113d8  mov     [rsp+2C8h+var_278], r8d
0x1800113dd  xor     r14d, r14d
0x1800113e0  mov     [rsp+2C8h+var_270], r15
0x1800113e5  xor     eax, eax
0x1800113e7  mov     r13d, r9d
0x1800113ea  mov     [rsp+2C8h+DestStr], ax
0x1800113ef  mov     esi, r8d
0x1800113f2  mov     r12, rdx
0x1800113f5  mov     rbx, rcx
0x1800113f8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800113ff  jnz     loc_180011AAF
0x180011405  movzx   ebp, [rsp+2C8h+arg_20]
0x18001140d  test    r12, r12
0x180011410  jnz     loc_180011945
0x180011416  cmp     cs:g_HashTable, r14
0x18001141d  mov     [rsp+2C8h+arg_10], rdi
0x180011425  jz      loc_180011AF9
0x18001142b  test    rbx, rbx
0x18001142e  jz      loc_1800116AB
0x180011434  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001143b  jnz     loc_180011A6A
0x180011441  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180011448  mov     rcx, rdx
0x18001144b  nop     dword ptr [rax+rax+00h]
0x180011450  inc     rcx
0x180011453  cmp     [rbx+rcx*2], r14w
0x180011458  jnz     short loc_180011450
0x18001145a  cmp     rcx, 100h
0x180011461  jnb     loc_180011BEE
0x180011467  xor     eax, eax
0x180011469  lea     r9d, [rcx+1]; cchSrc
0x18001146d  mov     [rsp+2C8h+DestStr], ax
0x180011472  test    r9d, r9d
0x180011475  jz      loc_180011B03
0x18001147b  cmp     r9d, 100h
0x180011482  ja      loc_180011B17
0x180011488  lea     rax, [rsp+2C8h+DestStr]
0x18001148d  mov     [rsp+2C8h+cchDest], 100h; cchDest
0x180011495  mov     r8, rbx; lpSrcStr
0x180011498  mov     [rsp+2C8h+lpDestStr], rax; lpDestStr
0x18001149d  mov     edx, 100h; dwMapFlags
0x1800114a2  mov     ecx, 7Fh; Locale
0x1800114a7  call    cs:__imp_LCMapStringW
0x1800114ad  lea     ecx, [rax-1]
0x1800114b0  cmp     ecx, 0FFh
0x1800114b6  ja      loc_1800116AB
0x1800114bc  dec     eax
0x1800114be  cmp     eax, 1
0x1800114c1  jbe     short loc_1800114D6
0x1800114c3  dec     eax
0x1800114c5  mov     ecx, eax
0x1800114c7  cmp     [rsp+rax*2+2C8h+DestStr], 2Eh ; '.'
0x1800114cd  jnz     short loc_1800114D6
0x1800114cf  xor     eax, eax
0x1800114d1  mov     [rsp+rcx*2+2C8h+DestStr], ax
0x1800114d6  mov     edi, cs:g_HashTableSize
0x1800114dc  lea     r8, [rsp+2C8h+DestStr]
0x1800114e1  xor     ebx, ebx
0x1800114e3  lea     r14, qword_180095210
0x1800114ea  xor     edx, edx
0x1800114ec  nop     dword ptr [rax+00h]
0x1800114f0  movzx   ecx, word ptr [r8]
0x1800114f4  rol     ebx, 1
0x1800114f6  movzx   eax, cl
0x1800114f9  xor     ebx, [r14+rax*4]
0x1800114fd  mov     eax, ecx
0x1800114ff  shr     rax, 8
0x180011503  rol     ebx, 1
0x180011505  xor     ebx, [r14+rax*4]
0x180011509  test    cx, cx
0x18001150c  jz      short loc_180011519
0x18001150e  add     r8, 2
0x180011512  inc     edx
0x180011514  cmp     edx, 0FFFFFFFFh
0x180011517  jb      short loc_1800114F0
0x180011519  test    r12, r12
0x18001151c  jnz     loc_180011981
0x180011522  xor     edx, edx
0x180011524  mov     eax, ebx
0x180011526  div     edi
0x180011528  mov     r14d, edx
0x18001152b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180011532  jnz     loc_180011B7C
0x180011538  mov     rcx, cs:g_HashTable
0x18001153f  mov     rdi, r14
0x180011542  shl     rdi, 4
0x180011546  mov     rbx, [rdi+rcx]
0x18001154a  lea     rax, [rdi+rcx]
0x18001154e  cmp     rbx, rax
0x180011551  jnz     short loc_1800115A0
0x180011553  cmp     [rsp+2C8h+arg_30], 0
0x18001155b  jz      loc_1800116AB
0x180011561  lea     rax, [rsp+2C8h+var_270]
0x180011566  mov     r9d, r13d
0x180011569  mov     [rsp+2C8h+var_298], rax
0x18001156e  lea     rcx, [rsp+2C8h+DestStr]
0x180011573  movzx   eax, [rsp+2C8h+arg_20]
0x18001157b  mov     r8d, esi
0x18001157e  mov     rdx, r12
0x180011581  mov     word ptr [rsp+2C8h+lpDestStr], ax
0x180011586  call    Cache_CreateEntry
0x18001158b  mov     r15, [rsp+2C8h+var_270]
0x180011590  jmp     loc_1800116AB
0x1800115a0  mov     rsi, [rbx+70h]
0x1800115a4  lea     r15, [rbx-8]
0x1800115a8  mov     [rsp+2C8h+var_270], r15
0x1800115ad  test    rsi, rsi
0x1800115b0  jz      loc_18001167B
0x1800115b6  mov     rdx, [rbx+20h]; pName2
0x1800115ba  lea     rcx, [rsp+2C8h+DestStr]; pName1
0x1800115bf  call    cs:__imp_DnsNameCompare_W
0x1800115c5  test    eax, eax
0x1800115c7  jz      loc_180011674
0x1800115cd  test    r12, r12
0x1800115d0  jnz     loc_180011782
0x1800115d6  cmp     [rbx+28h], r12w
0x1800115db  jnz     loc_180011674
0x1800115e1  cmp     [rsp+2C8h+arg_28], 0
0x1800115e9  jnz     loc_1800117B5
0x1800115ef  bt      r13d, 0Dh
0x1800115f4  jb      loc_18001192F
0x1800115fa  bt      r13d, 0Eh
0x1800115ff  jb      loc_18001196B
0x180011605  mov     ecx, [rbx+58h]
0x180011608  mov     eax, ecx
0x18001160a  shr     eax, 1
0x18001160c  mov     edx, ecx
0x18001160e  and     eax, 1
0x180011611  and     edx, 1
0x180011614  jnz     loc_1800117AB
0x18001161a  test    eax, eax
0x18001161c  jnz     loc_1800117AB
0x180011622  mov     r8d, [rsp+2C8h+var_278]
0x180011627  cmp     [rbx+5Ch], r8d
0x18001162b  jnz     short loc_180011674
0x18001162d  bt      r13d, 0Fh
0x180011632  jnb     loc_1800116E6
0x180011638  movzx   eax, word ptr [rbx+60h]
0x18001163c  movzx   edx, [rsp+2C8h+arg_20]
0x180011644  cmp     ax, dx
0x180011647  jz      loc_1800117B5
0x18001164d  bt      r13d, 10h
0x180011652  jb      loc_1800117B5
0x180011658  mov     ecx, 0FFh
0x18001165d  cmp     ax, cx
0x180011660  jz      loc_1800117EF
0x180011666  cmp     word ptr [rsi+10h], 5
0x18001166b  jz      loc_1800117C3
0x180011671  movzx   ebp, dx
0x180011674  mov     rcx, cs:g_HashTable
0x18001167b  mov     rbx, [rbx]
0x18001167e  lea     rax, [rdi+rcx]
0x180011682  xor     r15d, r15d
0x180011685  mov     [rsp+2C8h+var_270], r15
0x18001168a  cmp     rbx, rax
0x18001168d  jnz     loc_1800115A0
0x180011693  jmp     loc_1800117BA
0x180011698  cmp     [rsp+2C8h+arg_30], 0
0x1800116a0  mov     ebp, esi
0x1800116a2  jnz     loc_180011834
0x1800116a8  xor     r15d, r15d
0x1800116ab  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800116b2  jnz     loc_180011A51
0x1800116b8  mov     rdi, [rsp+2C8h+arg_10]
0x1800116c0  mov     rax, r15
0x1800116c3  mov     rcx, [rsp+2C8h+var_48]
0x1800116cb  xor     rcx, rsp; StackCookie
0x1800116ce  call    __security_check_cookie
0x1800116d3  add     rsp, 290h
0x1800116da  pop     r15
0x1800116dc  pop     r14
0x1800116de  pop     r13
0x1800116e0  pop     r12
0x1800116e2  pop     rsi
0x1800116e3  pop     rbp
0x1800116e4  pop     rbx
0x1800116e5  retn
0x1800116e6  test    edx, edx
0x1800116e8  jnz     loc_180011638
0x1800116ee  test    eax, eax
0x1800116f0  jnz     loc_180011638
0x1800116f6  mov     eax, ecx
0x1800116f8  xor     eax, r13d
0x1800116fb  test    al, 20h
0x1800116fd  jnz     loc_180011674
0x180011703  mov     eax, ecx
0x180011705  xor     eax, r13d
0x180011708  test    al, 40h
0x18001170a  jnz     loc_180011674
0x180011710  mov     eax, ecx
0x180011712  xor     eax, r13d
0x180011715  bt      eax, 0Bh
0x180011719  jb      loc_180011674
0x18001171f  test    r13b, 8
0x180011723  jnz     loc_180011BAB
0x180011729  mov     eax, ecx
0x18001172b  xor     eax, r13d
0x18001172e  bt      eax, 0Ch
0x180011732  jb      loc_180011674
0x180011738  mov     eax, ecx
0x18001173a  xor     eax, r13d
0x18001173d  bt      eax, 0Ah
0x180011741  jb      loc_180011674
0x180011747  mov     eax, ecx
0x180011749  xor     eax, r13d
0x18001174c  bt      eax, 12h
0x180011750  jb      loc_180011674
0x180011756  mov     eax, ecx
0x180011758  xor     eax, r13d
0x18001175b  test    al, al
0x18001175d  js      loc_180011674
0x180011763  cmp     cs:g_fVelocityZtdns, 0
0x18001176a  jz      loc_180011638
0x180011770  xor     ecx, r13d
0x180011773  bt      ecx, 13h
0x180011777  jb      loc_180011674
0x18001177d  jmp     loc_180011638
0x180011782  mov     rcx, r12
0x180011785  call    ServerInfoAddressValid
0x18001178a  test    eax, eax
0x18001178c  jz      loc_180011BA1
0x180011792  lea     rdx, [rbx+28h]
0x180011796  mov     rcx, r12
0x180011799  call    ServerInfoEqual
0x18001179e  test    eax, eax
0x1800117a0  jnz     loc_1800115E1
0x1800117a6  jmp     loc_180011674
0x1800117ab  cmp     [rbx+60h], bp
0x1800117af  jnz     loc_180011622
0x1800117b5  test    r15, r15
0x1800117b8  jnz     short loc_1800117FC
0x1800117ba  mov     esi, [rsp+2C8h+var_278]
0x1800117be  jmp     loc_180011553
0x1800117c3  cmp     dx, 5
0x1800117c7  jz      loc_180011671
0x1800117cd  mov     rcx, [rsi]
0x1800117d0  test    rcx, rcx
0x1800117d3  jz      loc_180011671
0x1800117d9  mov     eax, [rcx+14h]
0x1800117dc  and     al, 3
0x1800117de  cmp     al, 1
0x1800117e0  jz      short loc_1800117E7
0x1800117e2  mov     rcx, [rcx]
0x1800117e5  jmp     short loc_1800117D0
0x1800117e7  cmp     [rcx+10h], dx
0x1800117eb  jnz     short loc_1800117E2
0x1800117ed  jmp     short loc_1800117B5
0x1800117ef  cmp     word ptr [rsi+12h], 0
0x1800117f4  jnz     loc_180011666
0x1800117fa  jmp     short loc_1800117B5
0x1800117fc  xor     ebp, ebp
0x1800117fe  mov     esi, 1
0x180011803  test    byte ptr [r15+60h], 3
0x180011808  jnz     short loc_180011834
0x18001180a  lea     rcx, SRWLock; SRWLock
0x180011811  call    cs:__imp_AcquireSRWLockShared
0x180011817  mov     ebx, cs:dword_1800ABC2C
0x18001181d  lea     rcx, SRWLock; SRWLock
0x180011824  call    cs:__imp_ReleaseSRWLockShared
0x18001182a  cmp     [r15+58h], ebx
0x18001182e  jb      loc_180011698
0x180011834  bt      r13d, 11h
0x180011839  jb      loc_1800118C2
0x18001183f  xor     esi, esi
0x180011841  mov     rcx, [r15+78h]
0x180011845  test    rcx, rcx
0x180011848  jz      loc_1800118F5
0x18001184e  test    byte ptr [rcx+14h], 0C0h
0x180011852  jz      loc_1800118E6
0x180011858  test    ebp, ebp
0x18001185a  jnz     loc_18001191F
0x180011860  test    esi, esi
0x180011862  jnz     loc_18001191F
0x180011868  mov     rcx, cs:g_HashTable
0x18001186f  lea     rax, [r15+8]
0x180011873  add     rcx, rdi
0x180011876  cmp     [rcx], rax
0x180011879  jz      loc_1800116AB
0x18001187f  mov     rdx, [rax]
0x180011882  cmp     [rdx+8], rax
0x180011886  jnz     short loc_1800118A8
0x180011888  mov     r8, [rax+8]
0x18001188c  cmp     [r8], rax
0x18001188f  jnz     short loc_1800118A8
0x180011891  mov     [r8], rdx
0x180011894  mov     [rdx+8], r8
0x180011898  mov     [rax+8], rax
0x18001189c  mov     [rax], rax
  ... truncated ...
```
