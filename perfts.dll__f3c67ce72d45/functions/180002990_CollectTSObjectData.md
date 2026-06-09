# CollectTSObjectData

- ea: `0x180002990`
- end: `0x180003248`
- name: `CollectTSObjectData`
- size: `2232`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callees

- `0x180002820`
- `0x180002990`
- `0x180003250`
- `0x180003314`
- `0x180003800`
- `0x1800038b0`
- `0x180003974`
- `0x1800098f6`
- `0x180009902`
- `0x180009930`

## import_xrefs

- `msvcrt!wcsncat_s` at `0x180002f2d`
- `msvcrt!wcsncat_s` at `0x180002f72`
- `msvcrt!wcsncat_s` at `0x180002f2d`
- `msvcrt!wcsncat_s` at `0x180002f72`
- `msvcrt!wcsncpy_s` at `0x180002fbc`
- `msvcrt!wcsncpy_s` at `0x180002fbc`
- `msvcrt!_ltow` at `0x180002f11`
- `msvcrt!_ltow` at `0x180002f11`
- `ntdll!NtQuerySystemInformation` at `0x180002b2e`
- `ntdll!NtQuerySystemInformation` at `0x180002b7e`
- `ntdll!NtQuerySystemInformation` at `0x180002ba3`
- `ntdll!NtQuerySystemInformation` at `0x180002b2e`
- `ntdll!NtQuerySystemInformation` at `0x180002b7e`
- `ntdll!NtQuerySystemInformation` at `0x180002ba3`
- `ntdll!RtlNtStatusToDosError` at `0x180002bb1`
- `ntdll!RtlNtStatusToDosError` at `0x180002bb1`
- `WINSTA!WinStationEnumerateExW` at `0x180002be3`
- `WINSTA!WinStationEnumerateExW` at `0x180002be3`
- `WINSTA!WinStationFreeMemory` at `0x180003113`
- `WINSTA!WinStationFreeMemory` at `0x18000320c`
- `WINSTA!WinStationFreeMemory` at `0x180003113`
- `WINSTA!WinStationFreeMemory` at `0x18000320c`
- `UTILDLL!StrConnectState` at `0x180002f38`
- `UTILDLL!StrConnectState` at `0x180002f38`
- `KERNEL32!HeapFree` at `0x1800031bb`
- `KERNEL32!HeapFree` at `0x1800031bb`
- `KERNEL32!GetLastError` at `0x180002bf0`
- `KERNEL32!GetLastError` at `0x180002bf0`
- `KERNEL32!HeapReAlloc` at `0x180002b59`
- `KERNEL32!HeapReAlloc` at `0x180002b59`
- `KERNEL32!HeapAlloc` at `0x180002e8f`
- `KERNEL32!HeapAlloc` at `0x180002f85`
- `KERNEL32!HeapAlloc` at `0x180002e8f`
- `KERNEL32!HeapAlloc` at `0x180002f85`

## string_xrefs

- `0x180002bbf`: `PERFTS: GetSystemProcessData FAILED with error 0x%x`

## pseudocode

```c
__int64 __fastcall CollectTSObjectData(wchar_t *String1, unsigned __int64 *a2, unsigned int *a3, _DWORD *a4)
{
  unsigned int *v4; // r15
  _DWORD *v7; // rdi
  unsigned __int64 v8; // r14
  __int64 result; // rax
  __int64 v10; // rsi
  _OWORD *v11; // rax
  _OWORD *v12; // rcx
  __int128 v13; // xmm1
  ULONG v14; // ebx
  __int64 v15; // rsi
  int i; // eax
  ULONG v17; // ebx
  void *v18; // rax
  char *v19; // rcx
  char v20; // al
  __int64 v21; // r10
  __int128 *v22; // rdi
  _OWORD *v23; // rax
  _OWORD *v24; // rcx
  __int128 v25; // xmm1
  _QWORD *v26; // rcx
  __int128 v27; // xmm0
  __int128 *j; // rax
  char *v29; // r12
  int v30; // r13d
  ULONG k; // eax
  int v32; // r13d
  __int128 *v33; // rax
  __int128 *n; // rbx
  int *v35; // r15
  int v36; // r8d
  int v37; // eax
  unsigned int v38; // ecx
  int v39; // r13d
  int v40; // r9d
  int v41; // edx
  __int16 v42; // ax
  __int128 v43; // xmm1
  __int128 v44; // xmm0
  __int128 v45; // xmm1
  _QWORD *v46; // rax
  __int64 v47; // rdx
  _QWORD *v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int128 *v51; // rax
  __int64 v52; // rcx
  wchar_t *Src; // rax
  const wchar_t *v54; // rax
  __int64 v55; // rcx
  LPVOID v56; // rax
  __int64 v57; // rcx
  _DWORD *v58; // rbx
  _QWORD *v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rax
  __int64 v63; // rcx
  void *v64; // rbx
  _QWORD *v65; // rdx
  void **v66; // rcx
  int v67; // eax
  char v68; // cl
  unsigned int m; // eax
  __int64 v70; // rcx
  int v71; // eax
  unsigned __int64 v72; // rax
  int *v73; // rcx
  int v74; // [rsp+20h] [rbp-E0h]
  ULONG ReturnLength; // [rsp+30h] [rbp-D0h] BYREF
  int v76; // [rsp+34h] [rbp-CCh]
  int v77; // [rsp+38h] [rbp-C8h]
  unsigned int v78; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v79; // [rsp+40h] [rbp-C0h]
  int *v80; // [rsp+48h] [rbp-B8h] BYREF
  int v81[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v82; // [rsp+58h] [rbp-A8h]
  int v83[2]; // [rsp+60h] [rbp-A0h]
  _DWORD *v84; // [rsp+68h] [rbp-98h]
  __int128 *v85; // [rsp+70h] [rbp-90h]
  unsigned __int64 *v86; // [rsp+78h] [rbp-88h]
  int v87; // [rsp+80h] [rbp-80h] BYREF
  __int128 v88; // [rsp+84h] [rbp-7Ch]
  __int128 v89; // [rsp+94h] [rbp-6Ch]
  __int128 v90; // [rsp+A4h] [rbp-5Ch]
  __int128 v91; // [rsp+B4h] [rbp-4Ch]
  __int16 v92; // [rsp+C4h] [rbp-3Ch]
  int v93; // [rsp+C8h] [rbp-38h]
  wchar_t Buffer[56]; // [rsp+540h] [rbp+440h] BYREF

  v4 = a3;
  v82 = a3;
  v86 = a2;
  v84 = a4;
  *(_QWORD *)v81 = 0;
  v7 = a4;
  memset_0(&v87, 0, 0x4C0u);
  v8 = *a2;
  v80 = 0;
  v78 = 0;
  if ( !wcscmp_0(String1, L"Costly") || !wcscmp_0(String1, L"MetadataCostly") )
  {
    result = 0;
    goto LABEL_99;
  }
  if ( !wcscmp_0(String1, L"MetadataGlobal") )
  {
    if ( *v4 >= 0x298 )
    {
      v10 = 5;
      v11 = &WinStationDataDefinition;
      v12 = (_OWORD *)v8;
      do
      {
        *v12 = *v11;
        v12[1] = v11[1];
        v12[2] = v11[2];
        v12[3] = v11[3];
        v12[4] = v11[4];
        v12[5] = v11[5];
        v12[6] = v11[6];
        v13 = v11[7];
        v11 += 8;
        v12[7] = v13;
        v12 += 8;
        --v10;
      }
      while ( v10 );
      *v12 = *v11;
      *((_QWORD *)v12 + 2) = *((_QWORD *)v11 + 2);
      *(_DWORD *)v8 = 664;
      *(_DWORD *)(v8 + 40) = -2;
      *a2 = v8 + 664;
      *v4 = 664;
      *v7 = 1;
      return 0;
    }
    result = 234;
LABEL_99:
    *v4 = 0;
    *v7 = 0;
    return result;
  }
  v79 = 1266 * NumCachedWinStations + 668;
  if ( *v4 < v79 )
  {
    v14 = 234;
    goto LABEL_82;
  }
  ReturnLength = 0;
  v15 = 5;
  for ( i = NtQuerySystemInformation(SystemProcessInformation, pProcessBuffer, dwBytes, &ReturnLength);
        i == -1073741820;
        i = NtQuerySystemInformation(SystemProcessInformation, v18, v17, &ReturnLength) )
  {
    v17 = ReturnLength + 0x2000;
    v18 = HeapReAlloc(hLibHeap, 0, pProcessBuffer, ReturnLength + 0x2000);
    if ( !v18 )
    {
      v14 = 14;
      goto LABEL_20;
    }
    dwBytes = v17;
    pProcessBuffer = v18;
  }
  if ( i < 0
    || (i = NtQuerySystemInformation(SystemTimeOfDayInformation, &SysTimeInfo, 0x30u, &ReturnLength), v14 = i, i < 0) )
  {
    v14 = RtlNtStatusToDosError(i);
  }
  if ( v14 )
  {
LABEL_20:
    v19 = "PERFTS: GetSystemProcessData FAILED with error 0x%x";
LABEL_21:
    DbgPrintMessage(v19);
    goto LABEL_80;
  }
  v20 = WinStationEnumerateExW(0, &v80, &v78);
  v21 = 0;
  if ( !v20 )
  {
    GetLastError();
    v19 = "PERFTS: WinStationEnumerateEx FAILED with error 0x%x";
    goto LABEL_21;
  }
  v22 = 0;
  v23 = &WinStationDataDefinition;
  v24 = (_OWORD *)v8;
  do
  {
    *v24 = *v23;
    v24[1] = v23[1];
    v24[2] = v23[2];
    v24[3] = v23[3];
    v24[4] = v23[4];
    v24[5] = v23[5];
    v24[6] = v23[6];
    v25 = v23[7];
    v23 += 8;
    v24[7] = v25;
    v24 += 8;
    --v15;
  }
  while ( v15 );
  *v24 = *v23;
  *((_QWORD *)v24 + 2) = *((_QWORD *)v23 + 2);
  *(_QWORD *)(v8 + 48) = qword_180012A78;
  v26 = (_QWORD *)*((_QWORD *)&UsedList + 1);
  *(_QWORD *)(UsedList + 8) = &UnusedList;
  *v26 = &UnusedList;
  v27 = UsedList;
  *((_QWORD *)&UsedList + 1) = &UsedList;
  *(_QWORD *)&UsedList = &UsedList;
  UnusedList = v27;
  for ( j = (__int128 *)v27; j != &UnusedList; j = *(__int128 **)j )
  {
    v22 = j - 1;
    *((_QWORD *)j + 3) = 0;
  }
  v29 = (char *)pProcessBuffer;
  *(_QWORD *)v83 = v8 + 664;
  v30 = 0;
  v76 = 0;
  for ( k = 0; ; v29 = (char *)pProcessBuffer + k )
  {
    ReturnLength = k;
    if ( *((_QWORD *)v29 + 8) != v21 && *((_DWORD *)v29 + 1) != (_DWORD)v21 && *((_QWORD *)v29 + 10) != v21 )
      break;
LABEL_71:
    if ( *(_DWORD *)v29 == (_DWORD)v21 )
    {
      while ( 1 )
      {
        v62 = UnusedList;
        if ( (__int128 *)UnusedList == &UnusedList )
          break;
        if ( *(__int128 **)(UnusedList + 8) != &UnusedList )
          goto LABEL_95;
        v63 = *(_QWORD *)UnusedList;
        if ( *(_QWORD *)(*(_QWORD *)UnusedList + 8LL) != (_QWORD)UnusedList )
          goto LABEL_95;
        *(_QWORD *)&UnusedList = *(_QWORD *)UnusedList;
        v64 = (void *)(v62 - 16);
        *(_QWORD *)(v63 + 8) = &UnusedList;
        v65 = *(_QWORD **)(v62 - 16);
        if ( v65[1] != v62 - 16 )
          goto LABEL_95;
        v66 = *(void ***)(v62 - 8);
        if ( *v66 != v64 )
          goto LABEL_95;
        v67 = NumCachedWinStations - 1;
        *v66 = v65;
        NumCachedWinStations = v67;
        v65[1] = v66;
        v68 = v21;
        for ( m = 4 * v67; m > 1; m >>= 1 )
          ++v68;
        if ( NumWinStationHashBuckets < (unsigned int)(1 << v68) && (unsigned int)NumWinStationHashBuckets >= 4 )
          CreateNewHashBuckets((unsigned int)(1 << v68));
        HeapFree(hLibHeap, 0, v64);
        LOBYTE(v21) = 0;
      }
      v70 = *(_QWORD *)v83;
      v71 = v83[0];
      *(_DWORD *)(v8 + 40) = v30;
      *(_DWORD *)v8 = v71 - v8;
      v72 = (v70 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      *v86 = v72;
      v73 = v80;
      *v4 = v72 - v8;
      *v84 = 1;
      if ( v73 )
        WinStationFreeMemory();
      return 0;
    }
    k += *(_DWORD *)v29;
  }
  v32 = *((_DWORD *)v29 + 25);
  v33 = (__int128 *)((char *)pWinStationHashBuckets + 16 * (v32 & (unsigned int)WinStationHashMask));
  v77 = v32;
  v85 = v33;
  for ( n = *(__int128 **)v33; ; n = *(__int128 **)n )
  {
    if ( n == v33 )
      goto LABEL_38;
    v22 = n;
    if ( *((_DWORD *)n + 8) == v32 )
      break;
  }
  v50 = *((_QWORD *)n + 5);
  if ( v50 )
  {
    *(_QWORD *)v81 = *((_QWORD *)n + 5);
    UpdateWSProcessCounterBlock(v50, v29);
LABEL_69:
    v30 = v76;
    goto LABEL_70;
  }
LABEL_38:
  v35 = v80;
  memset_0(&v87, 0, 0x4C0u);
  if ( v35 )
  {
    v36 = v78;
    v37 = 1168;
    v38 = 0;
    if ( v78 )
    {
      v39 = v87;
      v40 = v77;
      do
      {
        v41 = *v35;
        if ( v77 == *v35 )
        {
          v42 = *((_WORD *)v35 + 48);
          v43 = *((_OWORD *)v35 + 3);
          v39 = v35[1];
          v88 = *((_OWORD *)v35 + 2);
          v92 = v42;
          v37 = 0;
          v44 = *((_OWORD *)v35 + 4);
          v93 = v41;
          v89 = v43;
          v45 = *((_OWORD *)v35 + 5);
          v90 = v44;
          v91 = v45;
        }
        ++v38;
        v35 += 278;
      }
      while ( v38 < v78 );
      v87 = v39;
      if ( !v37 )
      {
        if ( n != v85 )
        {
          if ( *((_DWORD *)v22 + 9) != v39 )
          {
            *((_DWORD *)v22 + 9) = v39;
            ConstructSessionName(v22, &v87);
          }
          v46 = v22 + 1;
          v47 = *((_QWORD *)v22 + 2);
          if ( *(__int128 **)(v47 + 8) != v22 + 1
            || (v48 = (_QWORD *)*((_QWORD *)v22 + 3), (_QWORD *)*v48 != v46)
            || (*v48 = v47, *(_QWORD *)(v47 + 8) = v48, v49 = UsedList, *(__int128 **)(UsedList + 8) != &UsedList) )
          {
LABEL_95:
            __fastfail(3u);
          }
          *v46 = UsedList;
          *((_QWORD *)v22 + 3) = &UsedList;
          *(_QWORD *)(v49 + 8) = v46;
          *(_QWORD *)&UsedList = v22 + 1;
          goto LABEL_57;
        }
        v51 = (__int128 *)HeapAlloc(hLibHeap, 0, 0x78u);
        v21 = 0;
        v22 = v51;
        if ( v51 )
        {
          *((_DWORD *)v51 + 8) = v77;
          *((_DWORD *)v51 + 9) = v39;
          *((_QWORD *)v51 + 5) = 0;
          ConstructSessionName(v51, &v87);
          v52 = UsedList;
          if ( *(__int128 **)(UsedList + 8) != &UsedList )
            goto LABEL_95;
          *((_QWORD *)v22 + 2) = UsedList;
          *((_QWORD *)v22 + 3) = &UsedList;
          *(_QWORD *)(v52 + 8) = v22 + 1;
          *(_QWORD *)&UsedList = v22 + 1;
          AddWinStationInfoToCache(v22);
LABEL_57:
          Src = (wchar_t *)(v22 + 3);
          goto LABEL_66;
        }
LABEL_68:
        v4 = v82;
        goto LABEL_69;
      }
      v32 = v77;
    }
  }
  _ltow(v32, Buffer, 10);
  wcsncat_s(Buffer, 0x32u, L" ", 1u);
  v54 = (const wchar_t *)StrConnectState(0xFFFFFFFFLL, 1);
  if ( v54 )
  {
    v55 = -1;
    do
      ++v55;
    while ( Buffer[v55] );
    wcsncat_s(Buffer, 0x32u, v54, 49 - v55);
  }
  v56 = HeapAlloc(hLibHeap, 0, 0x78u);
  v21 = 0;
  v22 = (__int128 *)v56;
  if ( !v56 )
    goto LABEL_68;
  *((_DWORD *)v56 + 8) = v32;
  *((_DWORD *)v56 + 9) = -1;
  *((_QWORD *)v56 + 5) = 0;
  wcsncpy_s((wchar_t *)v56 + 24, 0x21u, Buffer, 0x20u);
  v57 = UsedList;
  if ( *(__int128 **)(UsedList + 8) != &UsedList )
    goto LABEL_95;
  *((_QWORD *)v22 + 2) = UsedList;
  *((_QWORD *)v22 + 3) = &UsedList;
  *(_QWORD *)(v57 + 8) = v22 + 1;
  *(_QWORD *)&UsedList = v22 + 1;
  AddWinStationInfoToCache(v22);
  Src = Buffer;
LABEL_66:
  v4 = v82;
  v79 += 1266;
  if ( *v82 >= v79 )
  {
    v30 = ++v76;
    MonBuildInstanceDefinition(v83[0], (int)v81, v36, v40, v74, Src);
    v58 = *(_DWORD **)v81;
    memset_0((void *)(*(_QWORD *)v81 + 4LL), 0, 0xBCu);
    *v58 = 192;
    *((_QWORD *)v22 + 5) = v58;
    UpdateWSProcessCounterBlock(v58, v29);
    v21 = 0;
    *(_QWORD *)v83 = v58 + 48;
LABEL_70:
    k = ReturnLength;
    goto LABEL_71;
  }
  v14 = 234;
  while ( 1 )
  {
    v59 = (_QWORD *)UnusedList;
    if ( (__int128 *)UnusedList == &UnusedList )
      break;
    if ( *(__int128 **)(UnusedList + 8) != &UnusedList )
      goto LABEL_95;
    v60 = *(_QWORD *)UnusedList;
    if ( *(_QWORD *)(*(_QWORD *)UnusedList + 8LL) != (_QWORD)UnusedList )
      goto LABEL_95;
    *(_QWORD *)&UnusedList = *(_QWORD *)UnusedList;
    *(_QWORD *)(v60 + 8) = &UnusedList;
    v61 = UsedList;
    if ( *(__int128 **)(UsedList + 8) != &UsedList )
      goto LABEL_95;
    *v59 = UsedList;
    v59[1] = &UsedList;
    *(_QWORD *)(v61 + 8) = v59;
    *(_QWORD *)&UsedList = v59;
  }
  v7 = v84;
LABEL_80:
  if ( v80 )
    WinStationFreeMemory();
LABEL_82:
  *v7 = 0;
  result = v14;
  *v4 = 0;
  return result;
}

```

## disassembly

```asm
0x180002990  mov     [rsp-8+arg_0], rbx
0x180002995  push    rbp
0x180002996  push    rsi
0x180002997  push    rdi
0x180002998  push    r12
0x18000299a  push    r13
0x18000299c  push    r14
0x18000299e  push    r15
0x1800029a0  lea     rbp, [rsp-4C0h]
0x1800029a8  sub     rsp, 5C0h
0x1800029af  mov     rax, cs:__security_cookie
0x1800029b6  xor     rax, rsp
0x1800029b9  mov     [rbp+4F0h+var_40], rax
0x1800029c0  mov     r15, r8
0x1800029c3  mov     [rsp+5F0h+var_598], r8
0x1800029c8  mov     r12, rdx
0x1800029cb  mov     [rsp+5F0h+var_578], rdx
0x1800029d0  mov     rbx, rcx
0x1800029d3  mov     [rsp+5F0h+var_588], r9
0x1800029d8  xor     esi, esi
0x1800029da  lea     rcx, [rbp+4F0h+var_570]; void *
0x1800029de  xor     edx, edx; Val
0x1800029e0  mov     qword ptr [rsp+5F0h+var_5A0], rsi
0x1800029e5  mov     r8d, 4C0h; Size
0x1800029eb  mov     rdi, r9
0x1800029ee  call    memset_0
0x1800029f3  mov     r14, [r12]
0x1800029f7  lea     rdx, aCostly; "Costly"
0x1800029fe  mov     rcx, rbx; String1
0x180002a01  mov     [rsp+5F0h+var_5A8], rsi
0x180002a06  mov     [rsp+5F0h+var_5B4], esi
0x180002a0a  call    wcscmp_0
0x180002a0f  test    eax, eax
0x180002a11  jz      loc_180003217
0x180002a17  lea     rdx, aMetadatacostly; "MetadataCostly"
0x180002a1e  mov     rcx, rbx; String1
0x180002a21  call    wcscmp_0
0x180002a26  test    eax, eax
0x180002a28  jz      loc_180003217
0x180002a2e  lea     rdx, aMetadataglobal; "MetadataGlobal"
0x180002a35  mov     rcx, rbx; String1
0x180002a38  call    wcscmp_0
0x180002a3d  test    eax, eax
0x180002a3f  jnz     loc_180002AEA
0x180002a45  mov     r8d, 298h
0x180002a4b  cmp     [r15], r8d
0x180002a4e  jnb     short loc_180002A5A
0x180002a50  mov     eax, 0EAh
0x180002a55  jmp     loc_180003219
0x180002a5a  mov     esi, 5
0x180002a5f  lea     rax, WinStationDataDefinition
0x180002a66  mov     rcx, r14
0x180002a69  lea     edx, [rsi+7Bh]
0x180002a6c  movups  xmm0, xmmword ptr [rax]
0x180002a6f  movups  xmmword ptr [rcx], xmm0
0x180002a72  movups  xmm1, xmmword ptr [rax+10h]
0x180002a76  movups  xmmword ptr [rcx+10h], xmm1
0x180002a7a  movups  xmm0, xmmword ptr [rax+20h]
0x180002a7e  movups  xmmword ptr [rcx+20h], xmm0
0x180002a82  movups  xmm1, xmmword ptr [rax+30h]
0x180002a86  movups  xmmword ptr [rcx+30h], xmm1
0x180002a8a  movups  xmm0, xmmword ptr [rax+40h]
0x180002a8e  movups  xmmword ptr [rcx+40h], xmm0
0x180002a92  movups  xmm1, xmmword ptr [rax+50h]
0x180002a96  movups  xmmword ptr [rcx+50h], xmm1
0x180002a9a  movups  xmm0, xmmword ptr [rax+60h]
0x180002a9e  movups  xmmword ptr [rcx+60h], xmm0
0x180002aa2  movups  xmm1, xmmword ptr [rax+70h]
0x180002aa6  add     rax, rdx
0x180002aa9  movups  xmmword ptr [rcx+70h], xmm1
0x180002aad  add     rcx, rdx
0x180002ab0  sub     rsi, 1
0x180002ab4  jnz     short loc_180002A6C
0x180002ab6  movups  xmm0, xmmword ptr [rax]
0x180002ab9  movups  xmmword ptr [rcx], xmm0
0x180002abc  mov     rax, [rax+10h]
0x180002ac0  mov     [rcx+10h], rax
0x180002ac4  lea     rax, [r14+298h]
0x180002acb  mov     [r14], r8d
0x180002ace  mov     dword ptr [r14+28h], 0FFFFFFFEh
0x180002ad6  mov     [r12], rax
0x180002ada  mov     [r15], r8d
0x180002add  mov     dword ptr [rdi], 1
0x180002ae3  xor     eax, eax
0x180002ae5  jmp     loc_18000321E
0x180002aea  imul    r13d, cs:NumCachedWinStations, 4F2h
0x180002af5  add     r13d, 29Ch
0x180002afc  mov     [rsp+5F0h+var_5B0], r13d
0x180002b01  cmp     [r15], r13d
0x180002b04  jnb     short loc_180002B10
0x180002b06  mov     ebx, 0EAh
0x180002b0b  jmp     loc_180003119
0x180002b10  mov     r8d, cs:dwBytes; SystemInformationLength
0x180002b17  lea     r9, [rsp+5F0h+ReturnLength]; ReturnLength
0x180002b1c  mov     rdx, cs:pProcessBuffer; SystemInformation
0x180002b23  mov     [rsp+5F0h+ReturnLength], esi
0x180002b27  mov     esi, 5
0x180002b2c  mov     ecx, esi; SystemInformationClass
0x180002b2e  call    cs:__imp_NtQuerySystemInformation
0x180002b34  mov     r13d, 0C0000004h
0x180002b3a  jmp     short loc_180002B84
0x180002b3c  mov     ebx, [rsp+5F0h+ReturnLength]
0x180002b40  xor     edx, edx; dwFlags
0x180002b42  mov     r8, cs:pProcessBuffer; lpMem
0x180002b49  add     ebx, 2000h
0x180002b4f  mov     rcx, cs:hLibHeap; hHeap
0x180002b56  mov     r9d, ebx; dwBytes
0x180002b59  call    cs:__imp_HeapReAlloc
0x180002b5f  test    rax, rax
0x180002b62  jz      short loc_180002BD0
0x180002b64  lea     r9, [rsp+5F0h+ReturnLength]; ReturnLength
0x180002b69  mov     cs:dwBytes, ebx
0x180002b6f  mov     r8d, ebx; SystemInformationLength
0x180002b72  mov     cs:pProcessBuffer, rax
0x180002b79  mov     rdx, rax; SystemInformation
0x180002b7c  mov     ecx, esi; SystemInformationClass
0x180002b7e  call    cs:__imp_NtQuerySystemInformation
0x180002b84  cmp     eax, r13d
0x180002b87  jz      short loc_180002B3C
0x180002b89  test    eax, eax
0x180002b8b  js      short loc_180002BAF
0x180002b8d  mov     r8d, 30h ; '0'; SystemInformationLength
0x180002b93  lea     r9, [rsp+5F0h+ReturnLength]; ReturnLength
0x180002b98  lea     rdx, SysTimeInfo; SystemInformation
0x180002b9f  lea     ecx, [r8-2Dh]; SystemInformationClass
0x180002ba3  call    cs:__imp_NtQuerySystemInformation
0x180002ba9  mov     ebx, eax
0x180002bab  test    eax, eax
0x180002bad  jns     short loc_180002BB9
0x180002baf  mov     ecx, eax; Status
0x180002bb1  call    cs:__imp_RtlNtStatusToDosError
0x180002bb7  mov     ebx, eax
0x180002bb9  test    ebx, ebx
0x180002bbb  jz      short loc_180002BD7
0x180002bbd  mov     edx, ebx
0x180002bbf  lea     rcx, Format; "PERFTS: GetSystemProcessData FAILED wit"...
0x180002bc6  call    _DbgPrintMessage
0x180002bcb  jmp     loc_180003107
0x180002bd0  mov     ebx, 0Eh
0x180002bd5  jmp     short loc_180002BBD
0x180002bd7  lea     r8, [rsp+5F0h+var_5B4]
0x180002bdc  xor     ecx, ecx
0x180002bde  lea     rdx, [rsp+5F0h+var_5A8]
0x180002be3  call    cs:__imp_WinStationEnumerateExW
0x180002be9  xor     r10d, r10d
0x180002bec  test    al, al
0x180002bee  jnz     short loc_180002C01
0x180002bf0  call    cs:__imp_GetLastError
0x180002bf6  mov     edx, eax
0x180002bf8  lea     rcx, aPerftsWinstati; "PERFTS: WinStationEnumerateEx FAILED wi"...
0x180002bff  jmp     short loc_180002BC6
0x180002c01  mov     rdi, r10
0x180002c04  lea     rax, WinStationDataDefinition
0x180002c0b  mov     rcx, r14
0x180002c0e  mov     edx, 80h
0x180002c13  movups  xmm0, xmmword ptr [rax]
0x180002c16  movups  xmmword ptr [rcx], xmm0
0x180002c19  movups  xmm1, xmmword ptr [rax+10h]
0x180002c1d  movups  xmmword ptr [rcx+10h], xmm1
0x180002c21  movups  xmm0, xmmword ptr [rax+20h]
0x180002c25  movups  xmmword ptr [rcx+20h], xmm0
0x180002c29  movups  xmm1, xmmword ptr [rax+30h]
0x180002c2d  movups  xmmword ptr [rcx+30h], xmm1
0x180002c31  movups  xmm0, xmmword ptr [rax+40h]
0x180002c35  movups  xmmword ptr [rcx+40h], xmm0
0x180002c39  movups  xmm1, xmmword ptr [rax+50h]
0x180002c3d  movups  xmmword ptr [rcx+50h], xmm1
0x180002c41  movups  xmm0, xmmword ptr [rax+60h]
0x180002c45  movups  xmmword ptr [rcx+60h], xmm0
0x180002c49  movups  xmm1, xmmword ptr [rax+70h]
0x180002c4d  add     rax, rdx
0x180002c50  movups  xmmword ptr [rcx+70h], xmm1
0x180002c54  add     rcx, rdx
0x180002c57  sub     rsi, 1
0x180002c5b  jnz     short loc_180002C13
0x180002c5d  movups  xmm0, xmmword ptr [rax]
0x180002c60  lea     rdx, UnusedList
0x180002c67  movups  xmmword ptr [rcx], xmm0
0x180002c6a  mov     rax, [rax+10h]
0x180002c6e  mov     [rcx+10h], rax
0x180002c72  mov     rax, cs:qword_180012A78
0x180002c79  mov     [r14+30h], rax
0x180002c7d  mov     rax, qword ptr cs:UsedList
0x180002c84  mov     rcx, qword ptr cs:UsedList+8
0x180002c8b  mov     [rax+8], rdx
0x180002c8f  lea     rax, UsedList
0x180002c96  mov     [rcx], rdx
0x180002c99  movups  xmm0, cs:UsedList
0x180002ca0  mov     qword ptr cs:UsedList+8, rax
0x180002ca7  mov     qword ptr cs:UsedList, rax
0x180002cae  movups  cs:UnusedList, xmm0
0x180002cb5  movq    rax, xmm0
0x180002cba  jmp     short loc_180002CC7
0x180002cbc  lea     rdi, [rax-10h]
0x180002cc0  mov     [rdi+28h], r10
0x180002cc4  mov     rax, [rax]
0x180002cc7  cmp     rax, rdx
0x180002cca  jnz     short loc_180002CBC
0x180002ccc  mov     r12, cs:pProcessBuffer
0x180002cd3  lea     rcx, [r14+298h]
0x180002cda  mov     qword ptr [rsp+5F0h+var_590], rcx
0x180002cdf  mov     r13d, r10d
0x180002ce2  mov     [rsp+5F0h+var_5BC], r10d
0x180002ce7  mov     eax, r10d
0x180002cea  mov     esi, 1
0x180002cef  mov     [rsp+5F0h+ReturnLength], eax
0x180002cf3  cmp     [r12+40h], r10
0x180002cf8  jz      loc_180003086
0x180002cfe  cmp     [r12+4], r10d
0x180002d03  jz      loc_180003086
0x180002d09  cmp     [r12+50h], r10
0x180002d0e  jz      loc_180003086
0x180002d14  mov     r13d, [r12+64h]
0x180002d19  mov     ecx, cs:WinStationHashMask
0x180002d1f  mov     rax, cs:pWinStationHashBuckets
0x180002d26  and     rcx, r13
0x180002d29  shl     rcx, 4
0x180002d2d  add     rax, rcx
0x180002d30  mov     [rsp+5F0h+var_5B8], r13d
0x180002d35  mov     [rsp+5F0h+var_580], rax
0x180002d3a  mov     rbx, [rax]
0x180002d3d  jmp     short loc_180002D4F
0x180002d3f  mov     rdi, rbx
0x180002d42  cmp     [rbx+20h], r13d
0x180002d46  jz      loc_180002E63
0x180002d4c  mov     rbx, [rbx]
0x180002d4f  cmp     rbx, rax
0x180002d52  jnz     short loc_180002D3F
0x180002d54  mov     r15, [rsp+5F0h+var_5A8]
0x180002d59  lea     rcx, [rbp+4F0h+var_570]; void *
0x180002d5d  xor     edx, edx; Val
0x180002d5f  mov     r8d, 4C0h; Size
0x180002d65  call    memset_0
0x180002d6a  xor     r10d, r10d
0x180002d6d  test    r15, r15
0x180002d70  jz      loc_180002F01
0x180002d76  mov     r8d, [rsp+5F0h+var_5B4]
0x180002d7b  mov     eax, 490h
0x180002d80  mov     ecx, r10d
0x180002d83  test    r8d, r8d
0x180002d86  jz      loc_180002F01
0x180002d8c  mov     r13d, [rbp+4F0h+var_570]
0x180002d90  mov     r9d, [rsp+5F0h+var_5B8]
0x180002d95  mov     edx, [r15]
0x180002d98  cmp     r9d, edx
0x180002d9b  jnz     short loc_180002DD4
0x180002d9d  movups  xmm0, xmmword ptr [r15+20h]
0x180002da2  movzx   eax, word ptr [r15+60h]
0x180002da7  movups  xmm1, xmmword ptr [r15+30h]
0x180002dac  mov     r13d, [r15+4]
0x180002db0  movups  [rbp+4F0h+var_56C], xmm0
0x180002db4  mov     [rbp+4F0h+var_52C], ax
0x180002db8  mov     eax, r10d
0x180002dbb  movups  xmm0, xmmword ptr [r15+40h]
0x180002dc0  mov     [rbp+4F0h+var_528], edx
0x180002dc3  movups  [rbp+4F0h+var_55C], xmm1
0x180002dc7  movups  xmm1, xmmword ptr [r15+50h]
0x180002dcc  movups  [rbp+4F0h+var_54C], xmm0
0x180002dd0  movups  [rbp+4F0h+var_53C], xmm1
0x180002dd4  add     ecx, esi
0x180002dd6  add     r15, 458h
0x180002ddd  cmp     ecx, r8d
0x180002de0  jb      short loc_180002D95
0x180002de2  mov     [rbp+4F0h+var_570], r13d
0x180002de6  test    eax, eax
0x180002de8  jnz     loc_180002EFE
0x180002dee  cmp     rbx, [rsp+5F0h+var_580]
0x180002df3  jz      loc_180002E82
0x180002df9  cmp     [rdi+24h], r13d
0x180002dfd  jz      short loc_180002E0F
0x180002dff  lea     rdx, [rbp+4F0h+var_570]
0x180002e03  mov     [rdi+24h], r13d
0x180002e07  mov     rcx, rdi
0x180002e0a  call    ConstructSessionName
0x180002e0f  lea     rax, [rdi+10h]
0x180002e13  mov     rdx, [rax]
0x180002e16  cmp     [rdx+8], rax
0x180002e1a  jnz     loc_1800031C9
0x180002e20  mov     rcx, [rdi+18h]
0x180002e24  cmp     [rcx], rax
0x180002e27  jnz     loc_1800031C9
0x180002e2d  mov     [rcx], rdx
0x180002e30  lea     r13, UsedList
0x180002e37  mov     [rdx+8], rcx
0x180002e3b  mov     rcx, qword ptr cs:UsedList
0x180002e42  cmp     [rcx+8], r13
0x180002e46  jnz     loc_1800031C9
0x180002e4c  mov     [rax], rcx
0x180002e4f  mov     [rax+8], r13
0x180002e53  mov     [rcx+8], rax
0x180002e57  mov     qword ptr cs:UsedList, rax
0x180002e5e  jmp     loc_180002EF5
0x180002e63  mov     rcx, [rbx+28h]
0x180002e67  test    rcx, rcx
0x180002e6a  jz      loc_180002D54
0x180002e70  mov     rdx, r12
0x180002e73  mov     qword ptr [rsp+5F0h+var_5A0], rcx
0x180002e78  call    UpdateWSProcessCounterBlock
0x180002e7d  jmp     loc_18000307D
0x180002e82  mov     rcx, cs:hLibHeap; hHeap
  ... truncated ...
```
