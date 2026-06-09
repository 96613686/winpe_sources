# ProcessDhcpDiscover

- ea: `0x180059550`
- end: `0x18005a23d`
- name: `ProcessDhcpDiscover`
- size: `3309`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x180058034`
- `0x18005ced8`

## callees

- `0x180001834`
- `0x180002854`
- `0x18000323c`
- `0x180003268`
- `0x180005408`
- `0x180006250`
- `0x1800083d0`
- `0x18000d914`
- `0x1800318bc`
- `0x180031978`
- `0x1800319e8`
- `0x180031ba4`
- `0x180031f24`
- `0x1800324f8`
- `0x18003255c`
- `0x18003378c`
- `0x180033aa0`
- `0x180033b98`
- `0x180033c80`
- `0x180053cc8`
- `0x1800547f0`
- `0x180054ec4`
- `0x180055478`
- `0x18005585c`
- `0x18005590c`
- `0x1800559a8`
- `0x180055dc0`
- `0x180057dcc`
- `0x180058034`
- `0x180058530`
- `0x180059550`
- `0x18008ee18`
- `0x18008f418`
- `0x1800983b4`
- `0x1800c6458`
- `0x1800c7fa8`
- `0x1800cc9e0`
- `0x1800cd010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180059753`
- `msvcrt!_wcsicmp` at `0x180059753`
- `msvcrt!time` at `0x18005a0ec`
- `msvcrt!time` at `0x18005a0ec`
- `WS2_32!__imp_htons` at `0x180059857`
- `WS2_32!__imp_htons` at `0x180059857`
- `KERNEL32!GetComputerNameW` at `0x1800596c2`
- `KERNEL32!GetComputerNameW` at `0x1800596c2`
- `KERNEL32!HeapAlloc` at `0x180059fff`
- `KERNEL32!HeapAlloc` at `0x180059fff`
- `KERNEL32!GetLastError` at `0x1800596d2`
- `KERNEL32!GetLastError` at `0x1800596d2`
- `KERNEL32!EnterCriticalSection` at `0x18005990b`
- `KERNEL32!EnterCriticalSection` at `0x180059a54`
- `KERNEL32!EnterCriticalSection` at `0x180059b2e`
- `KERNEL32!EnterCriticalSection` at `0x180059b93`
- `KERNEL32!EnterCriticalSection` at `0x180059df5`
- `KERNEL32!EnterCriticalSection` at `0x18005990b`
- `KERNEL32!EnterCriticalSection` at `0x180059a54`
- `KERNEL32!EnterCriticalSection` at `0x180059b2e`
- `KERNEL32!EnterCriticalSection` at `0x180059b93`
- `KERNEL32!EnterCriticalSection` at `0x180059df5`
- `KERNEL32!LeaveCriticalSection` at `0x180059950`
- `KERNEL32!LeaveCriticalSection` at `0x18005996e`
- `KERNEL32!LeaveCriticalSection` at `0x180059aba`
- `KERNEL32!LeaveCriticalSection` at `0x180059afd`
- `KERNEL32!LeaveCriticalSection` at `0x180059b50`
- `KERNEL32!LeaveCriticalSection` at `0x180059b6d`
- `KERNEL32!LeaveCriticalSection` at `0x180059bdf`
- `KERNEL32!LeaveCriticalSection` at `0x180059d02`
- `KERNEL32!LeaveCriticalSection` at `0x180059e1d`
- `KERNEL32!LeaveCriticalSection` at `0x18005a1f1`
- `KERNEL32!LeaveCriticalSection` at `0x180059950`
- `KERNEL32!LeaveCriticalSection` at `0x18005996e`
- `KERNEL32!LeaveCriticalSection` at `0x180059aba`
- `KERNEL32!LeaveCriticalSection` at `0x180059afd`
- `KERNEL32!LeaveCriticalSection` at `0x180059b50`
- `KERNEL32!LeaveCriticalSection` at `0x180059b6d`
- `KERNEL32!LeaveCriticalSection` at `0x180059bdf`
- `KERNEL32!LeaveCriticalSection` at `0x180059d02`
- `KERNEL32!LeaveCriticalSection` at `0x180059e1d`
- `KERNEL32!LeaveCriticalSection` at `0x18005a1f1`
- `KERNEL32!HeapFree` at `0x180059adb`
- `KERNEL32!HeapFree` at `0x18005a0b1`
- `KERNEL32!HeapFree` at `0x18005a1b5`
- `KERNEL32!HeapFree` at `0x180059adb`
- `KERNEL32!HeapFree` at `0x18005a0b1`
- `KERNEL32!HeapFree` at `0x18005a1b5`

## pseudocode

```c
__int64 __fastcall ProcessDhcpDiscover(__int64 *a1, _QWORD *a2, __int64 a3, _DWORD *a4)
{
  __int64 v8; // rbx
  __int64 v9; // r12
  unsigned int LastError; // edi
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  int v13; // edx
  int v14; // r9d
  unsigned int *v15; // rcx
  unsigned int v16; // eax
  DWORD v17; // r15d
  void *v18; // r13
  u_short v19; // ax
  unsigned int v20; // ecx
  unsigned int v21; // eax
  int *v22; // rbx
  unsigned int v23; // edi
  __int64 v24; // r8
  __int64 v25; // rax
  int v26; // r9d
  __int64 v27; // rdx
  void *v28; // rbx
  int v29; // ebx
  unsigned __int16 v30; // r12
  unsigned int v31; // eax
  __int64 v32; // rax
  char v33; // al
  int v34; // edx
  bool v35; // zf
  __int64 v36; // r8
  BOOL v37; // ebx
  unsigned int v38; // eax
  __int64 v39; // rbx
  wchar_t *v40; // rax
  __int64 v41; // rcx
  wchar_t *v42; // rbx
  int v43; // r12d
  u_long v44; // eax
  __int64 v45; // rax
  __int64 v46; // rbx
  __int64 v47; // rax
  DWORD dwFlags[2]; // [rsp+20h] [rbp-198h]
  STRSAFE_LPCWSTR pszFormat; // [rsp+28h] [rbp-190h]
  STRSAFE_LPCWSTR pszFormatb; // [rsp+28h] [rbp-190h]
  STRSAFE_LPCWSTR pszFormata; // [rsp+28h] [rbp-190h]
  u_long v53[2]; // [rsp+30h] [rbp-188h]
  int v54; // [rsp+50h] [rbp-168h] BYREF
  size_t Size; // [rsp+54h] [rbp-164h] BYREF
  __int64 v56; // [rsp+5Ch] [rbp-15Ch] BYREF
  BOOL v57; // [rsp+64h] [rbp-154h]
  DWORD nSize; // [rsp+68h] [rbp-150h] BYREF
  size_t cbDest; // [rsp+70h] [rbp-148h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-140h] BYREF
  u_long v61[2]; // [rsp+80h] [rbp-138h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+88h] [rbp-130h] BYREF
  _QWORD *v63; // [rsp+90h] [rbp-128h]
  _QWORD v64[2]; // [rsp+98h] [rbp-120h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-110h]
  __int64 v66; // [rsp+B0h] [rbp-108h]
  WCHAR Buffer[28]; // [rsp+B8h] [rbp-100h] BYREF
  wchar_t String1[64]; // [rsp+F0h] [rbp-C8h] BYREF

  v65 = (__int64)a4;
  v63 = a2;
  nSize = 0;
  cbDest = 0;
  Size = 0;
  v54 = -1;
  v56 = 0;
  lpMem = 0;
  v61[1] = 0;
  v61[0] = 0;
  LODWORD(pszDest) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_079646765da4361deec0b4ab82b940ea_Traceguids);
  *((_DWORD *)a1 + 50) = 1;
  if ( a4 )
    *a4 = 0;
  if ( !a3 || !*(_DWORD *)(a3 + 76) && *(_BYTE *)(a3 + 73) != 6 )
    _InterlockedAdd(&DhcpGlobalNumDiscovers, 1u);
  v8 = *a2;
  v66 = v8;
  v57 = v8 == 0;
  v64[0] = 0;
  v64[1] = 0;
  v9 = *a1;
  *(_BYTE *)(v9 + 107) = 0;
  *(_BYTE *)(v9 + 235) = 0;
  LastError = DhcpMessageCheckFilter(a1, a2);
  if ( !LastError )
  {
    if ( !v8 && *(_BYTE *)(v9 + 44) )
    {
      if ( !DhcpOemToUnicode((PCSZ)(v9 + 44)) )
      {
LABEL_14:
        LastError = 20015;
        goto LABEL_132;
      }
      nSize = 25;
      if ( !GetComputerNameW(Buffer, &nSize) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_079646765da4361deec0b4ab82b940ea_Traceguids, LastError);
        goto LABEL_132;
      }
      v11 = 24;
      if ( nSize < 0x19 )
        v11 = nSize;
      v12 = v11;
      if ( v12 >= 25 )
        _report_rangecheckfailure();
      Buffer[v12] = 0;
      if ( _wcsicmp(String1, Buffer) )
        goto LABEL_14;
    }
    if ( a2[6] && !(unsigned int)CheckMessageDirectedToThisServer(a1) )
    {
LABEL_25:
      LastError = 20016;
      goto LABEL_132;
    }
    LastError = DhcpDetermineInfoFromMessage(a1, (__int64)a2, &cbDest, &Size, (u_long *)&v56);
    if ( LastError )
      goto LABEL_132;
    DhcpGetSubnetForAddress((unsigned int)v56, a1);
    v15 = (unsigned int *)a1[11];
    if ( v15[1073] == 1 )
    {
      if ( v15[1077] != 3 )
        goto LABEL_39;
      v16 = v15[1075];
      if ( !v16 && !v15[1074] )
      {
        AuditLogPacketDropDueToFailover(v15[2], cbDest, (unsigned int)Size);
LABEL_32:
        LastError = 6;
        goto LABEL_132;
      }
      if ( v16 == 1 )
      {
        v17 = Size;
        LOBYTE(v14) = Size;
        v18 = (void *)cbDest;
        DhcpFailoverVerifyHash((_DWORD)v15 + 4320, v13, cbDest, v14, (__int64)&pszDest);
        if ( !(_DWORD)pszDest )
        {
          v19 = *(_WORD *)(a1[18] + 608);
          if ( *((_DWORD *)a1 + 32) == 1 )
            v19 = htons(v19);
          if ( v19 < (unsigned int)DhcpGlobalMaxPacketElapsedTime )
          {
            LastError = 87;
            AuditLogPacketDropDueToFailover(*(unsigned int *)(a1[11] + 8), v18, v17);
            goto LABEL_132;
          }
        }
      }
      else
      {
LABEL_39:
        v18 = (void *)cbDest;
        v17 = Size;
      }
      v20 = *(_DWORD *)(a1[11] + 4308);
      if ( v20 == 6 || v20 <= 2 || v20 >= 9 )
        goto LABEL_32;
    }
    else
    {
      v18 = (void *)cbDest;
      v17 = Size;
    }
    if ( a3 && *(_DWORD *)(a3 + 76) )
    {
      v53[0] = v17;
      v21 = HandlePingCallback((int)a1, v65, v18, *(size_t *)v53);
      goto LABEL_48;
    }
    EnterCriticalSection(&DhcpGlobalInProgressCritSect);
    DhcpFindPendingCtxt(v18, v17);
    v22 = (int *)lpMem;
    if ( !lpMem )
      goto LABEL_81;
    v23 = *((_DWORD *)lpMem + 11);
    if ( (v23 & 0xF0000000) == 0xE0000000 )
    {
LABEL_51:
      LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
      goto LABEL_25;
    }
    if ( *((_DWORD *)lpMem + 18) )
    {
      LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
      if ( a3 && qword_180155830 )
        qword_180155830(a3 + 88, a3 + 104, 1, *(unsigned int *)(a3 + 116), a3, *(_QWORD *)(a3 + 296));
      LastError = 997;
      goto LABEL_132;
    }
    if ( !(unsigned int)DhcpInSameSuperScope(v23, (unsigned int)v56) )
    {
      Size = 0;
      DhcpRemovePendingCtxt(v22);
      DhcpDeletePendingCtxt(v22);
      if ( (unsigned int)DhcpGetSubnetForAddress(v23, a1) )
        goto LABEL_51;
      v25 = a1[11];
      if ( v25 )
        v26 = *(_DWORD *)(v25 + 8);
      else
        v26 = 0;
      lpMem = 0;
      LOBYTE(v24) = *(_BYTE *)(v9 + 1);
      LastError = DhcpMakeClientUID(v18, v17, v24, v26, &lpMem, (_DWORD *)&Size + 1);
      if ( LastError )
        goto LABEL_131;
      EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      LOBYTE(v27) = BYTE4(Size);
      v28 = lpMem;
      if ( !(unsigned int)DhcpGetIpAddressFromHwAddress(lpMem, v27, &Size) )
        LODWORD(Size) = 0;
      if ( (_DWORD)Size )
        DhcpRemoveClientEntry((struct in_addr)Size, (__int64)v28, HIDWORD(Size), 1, 0, 1u, 0, a1[11]);
      LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      if ( v28 )
        HeapFree(gDhcpHeap, 0, v28);
LABEL_81:
      v54 = 0;
      v31 = DhcpLookupReservationByHardwareAddress((unsigned int)v56, v18, v17, a1);
      LastError = v31;
      if ( !v31 )
      {
        LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
        v32 = a1[14];
        if ( v32 )
        {
          v34 = *(_DWORD *)(v32 + 8);
          v54 = v34;
          v33 = *(_BYTE *)(v32 + 12);
        }
        else
        {
          v33 = 0;
          v34 = v54;
        }
        if ( v66 )
          v35 = (v33 & 1) == 0;
        else
          v35 = (v33 & 2) == 0;
        if ( v35 )
          goto LABEL_25;
        v36 = a1[11];
        if ( ((*(_DWORD *)(v36 + 36) - 1) & 0xFFFFFFFD) == 0 )
          goto LABEL_25;
        ValidateSubRangeForAddress(
          (_DWORD)a1 + 168,
          v34,
          v36,
          (_DWORD)a1 + 152,
          (__int64)&v56 + 4,
          (__int64)v64,
          (__int64)(a1 + 21),
          (__int64)(a1 + 23));
        LODWORD(pszFormatb) = v17;
        v21 = DhcpProcessDiscoverForValidatedAddress(v54, (_DWORD)a1, v18, (size_t)pszFormatb, 0);
        goto LABEL_48;
      }
      if ( v31 == 2 )
      {
        if ( (unsigned int)DhcpGetSubnetForAddress((unsigned int)v56, a1) )
          goto LABEL_51;
        EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
        LastError = DhcpLookupDatabaseByHardwareAddress(a1, v18, v17, &v54);
        LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
        v37 = v57;
        if ( !LastError )
        {
          if ( !(unsigned int)DhcpSubnetIsDisabled(a1[11], v57) )
          {
            LastError = ValidateSubRangeForAddress(
                          (int)a1 + 168,
                          v54,
                          a1[11],
                          (int)a1 + 152,
                          (__int64)&v56 + 4,
                          (__int64)v64,
                          (__int64)(a1 + 21),
                          (__int64)(a1 + 23));
            if ( !LastError )
            {
              if ( HIDWORD(v56) )
              {
                LODWORD(pszFormata) = v17;
                LastError = DhcpProcessDiscoverForValidatedAddress(v54, (_DWORD)a1, v18, (size_t)pszFormata, 1);
                if ( LastError != 20016 )
                  goto LABEL_131;
              }
            }
            if ( LastError && LastError != 20016 )
              goto LABEL_131;
          }
          DhcpRemoveClientEntry((struct in_addr)v54, 0, 0, 1, 0, 1u, 0, a1[11]);
          LastError = 2;
        }
        if ( LastError == 2 )
        {
          v38 = DhcpDiscoverValidateRequestedAddress((_DWORD)a1, v63[2], v37, (unsigned int)&v54, (__int64)v64);
          LastError = v38;
          if ( !v38 )
          {
LABEL_105:
            v39 = a1[11];
            if ( v39 )
              LODWORD(v39) = *(_DWORD *)(v39 + 8);
            if ( v54 != (_DWORD)v39 )
            {
              LODWORD(pszFormat) = v17;
              LastError = DhcpProcessDiscoverForValidatedAddress(v54, (_DWORD)a1, v18, (size_t)pszFormat, 1);
              if ( LastError != 20016 )
                goto LABEL_131;
            }
            v54 = v39;
            LastError = DhcpRequestSomeAddress((_DWORD)a1, (unsigned int)&v54, v57, (unsigned int)v64, 0);
            if ( LastError == 20012 )
            {
              cbDest = 4LL * v17 + 2;
              lpMem = v18;
              v40 = (wchar_t *)HeapAlloc(gDhcpHeap, 8u, cbDest);
              v42 = v40;
              if ( !v40 )
              {
                LastError = 8;
                goto LABEL_131;
              }
              pszDest = v40;
              v43 = 0;
              if ( v17 )
              {
                while ( 1 )
                {
                  v44 = *(unsigned __int8 *)lpMem;
                  lpMem = (char *)lpMem + 1;
                  v53[0] = v44;
                  if ( StringCbPrintfExW(pszDest, cbDest, &pszDest, &cbDest, 0x1200u, L"%.2X", *(_QWORD *)v53) < 0 )
                    break;
                  if ( ++v43 >= v17 )
                    goto LABEL_115;
                }
                HeapFree(gDhcpHeap, 0, v42);
                LastError = 13;
                goto LABEL_131;
              }
LABEL_115:
              if ( (Microsoft_Windows_DHCP_ServerEnableBits & 0x40) != 0 )
                McTemplateU0zz_EventWriteTransfer(v41, &ClientRequestDropped, v42, *(_QWORD *)(a1[11] + 136));
              HeapFree(gDhcpHeap, 0, v42);
            }
            if ( LastError == 20012 )
            {
              v45 = a1[11];
              if ( *(_DWORD *)(v45 + 4292) == 1 && *(_DWORD *)(v45 + 4308) == 5 )
              {
                v46 = a1[11];
                if ( *(_DWORD *)(v46 + 4304) + *(_DWORD *)(v46 + 4312) < (unsigned int)time(0) )
                  LastError = DhcpRequestSomeAddress((_DWORD)a1, (unsigned int)&v54, v57, (unsigned int)v64, 1);
              }
              if ( LastError == 20012 )
                DhcpGlobalScavengeIpAddress = 1;
            }
            if ( LastError )
              goto LABEL_131;
            if ( !DhcpGlobalDetectConflictRetries )
            {
              LODWORD(pszFormat) = v17;
              LastError = DhcpProcessDiscoverForValidatedAddress(v54, (_DWORD)a1, v18, (size_t)pszFormat, 1);
              goto LABEL_131;
            }
LABEL_127:
            v47 = DhcpCalculateTime(600);
            LastError = DhcpAddPendingCtxt(v18, v17, 0, 0, 0, v47, 1);
            if ( !LastError )
            {
              *(_DWORD *)(a3 + 76) = v54;
              *(_DWORD *)(a3 + 80) = 0;
              *(_DWORD *)v65 = 997;
            }
            goto LABEL_131;
          }
          if ( v38 == 997 )
          {
            if ( DhcpGlobalDetectConflictRetries )
              goto LABEL_127;
            goto LABEL_105;
          }
        }
      }
LABEL_131:
      LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
      goto LABEL_132;
    }
    v54 = v22[11];
    v29 = v22[19];
    LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
    LastError = DhcpGetSubnetForAddress((unsigned int)v54, a1);
    v30 = *(_WORD *)(a1[11] + 156) - 1;
    EnterCriticalSection(&DhcpGlobalInProgressCritSect);
    if ( !v29 && v30 <= 0x3E7u )
    {
      LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
      LastError = 20014;
      goto LABEL_132;
    }
    LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
    if ( *(_DWORD *)(a1[11] + 4292) == 1 )
    {
      EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      DhcpGetFailoverLeaseDuration((__int64)a1, v54, &v61[1], (int *)&pszDest, v61, (int *)&Size + 1, 0);
      LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    }
    else if ( a1[18] )
    {
      GetLeaseInfo((int)a1, 0);
    }
    if ( !LastError )
    {
      if ( (unsigned int)DhcpSubnetIsAddressOutOfRange(a1[11], (unsigned int)v54, v57)
        || (unsigned int)ValidateSubRangeForAddress(
                           (int)a1 + 168,
                           v54,
                           a1[11],
                           (int)a1 + 152,
                           (__int64)&v56 + 4,
                           (__int64)v64,
                           (__int64)(a1 + 21),
                           (__int64)(a1 + 23))
        || !HIDWORD(v56) )
      {
        goto LABEL_25;
      }
      dwFlags[0] = v17;
      v21 = DhcpRespondToDiscover(
              (__int64)a1,
              a3,
              (__int64)v63,
              v18,
              *(size_t *)dwFlags,
              v54,
              v61[1],
              v61[0],
              HIDWORD(Size));
LABEL_48:
      LastError = v21;
    }
  }
LABEL_132:
  MemArrayFree(v64, MemFreeSubnetSatisfiedPolicies);
  return LastError;
}

```

## disassembly

```asm
0x180059550  push    rbx
0x180059552  push    rsi
0x180059553  push    rdi
0x180059554  push    r12
0x180059556  push    r13
0x180059558  push    r14
0x18005955a  push    r15
0x18005955c  sub     rsp, 180h
0x180059563  mov     rax, cs:__security_cookie
0x18005956a  xor     rax, rsp
0x18005956d  mov     [rsp+1B8h+var_48], rax
0x180059575  mov     rbx, r9
0x180059578  mov     [rsp+1B8h+var_110], rbx
0x180059580  mov     r14, r8
0x180059583  mov     r15, rdx
0x180059586  mov     [rsp+1B8h+var_128], rdx
0x18005958e  mov     rsi, rcx
0x180059591  xor     r13d, r13d
0x180059594  mov     [rsp+1B8h+nSize], r13d
0x180059599  mov     [rsp+1B8h+cbDest], r13
0x18005959e  mov     dword ptr [rsp+1B8h+Size], r13d
0x1800595a3  or      [rsp+1B8h+var_168], 0FFFFFFFFh
0x1800595a8  mov     dword ptr [rsp+1B8h+var_15C], r13d
0x1800595ad  mov     [rsp+1B8h+lpMem], r13
0x1800595b2  mov     [rsp+1B8h+var_138+4], r13d
0x1800595ba  mov     [rsp+1B8h+var_138], r13d
0x1800595c2  mov     dword ptr [rsp+1B8h+Size+4], r13d
0x1800595c7  mov     dword ptr [rsp+1B8h+var_15C+4], r13d
0x1800595cc  mov     dword ptr [rsp+1B8h+pszDest], r13d
0x1800595d4  lea     rax, WPP_GLOBAL_Control
0x1800595db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800595e2  cmp     rcx, rax
0x1800595e5  jz      short loc_180059601
0x1800595e7  test    byte ptr [rcx+1Ch], 20h
0x1800595eb  jz      short loc_180059601
0x1800595ed  lea     edx, [r13+2Eh]
0x1800595f1  lea     r8, WPP_079646765da4361deec0b4ab82b940ea_Traceguids
0x1800595f8  mov     rcx, [rcx+10h]
0x1800595fc  call    WPP_SF_
0x180059601  mov     eax, 1
0x180059606  mov     [rsi+0C8h], eax
0x18005960c  test    rbx, rbx
0x18005960f  jz      short loc_180059614
0x180059611  mov     [rbx], r13d
0x180059614  test    r14, r14
0x180059617  jz      short loc_180059626
0x180059619  cmp     [r14+4Ch], r13d
0x18005961d  jnz     short loc_18005962D
0x18005961f  cmp     byte ptr [r14+49h], 6
0x180059624  jz      short loc_18005962D
0x180059626  lock add cs:DhcpGlobalNumDiscovers, eax
0x18005962d  mov     rbx, [r15]
0x180059630  mov     [rsp+1B8h+var_108], rbx
0x180059638  mov     eax, r13d
0x18005963b  test    rbx, rbx
0x18005963e  setz    al
0x180059641  mov     [rsp+1B8h+var_154], eax
0x180059645  mov     [rsp+1B8h+var_120], r13
0x18005964d  mov     [rsp+1B8h+var_118], r13
0x180059655  mov     r12, [rsi]
0x180059658  mov     [r12+6Bh], r13b
0x18005965d  mov     [r12+0EBh], r13b
0x180059665  mov     rdx, r15
0x180059668  mov     rcx, rsi
0x18005966b  call    DhcpMessageCheckFilter
0x180059670  mov     edi, eax
0x180059672  test    eax, eax
0x180059674  jnz     loc_18005A1FD
0x18005967a  test    rbx, rbx
0x18005967d  jnz     loc_180059767
0x180059683  lea     rcx, [r12+2Ch]; SourceString
0x180059688  cmp     [rcx], r13b
0x18005968b  jz      loc_180059767
0x180059691  lea     rdx, [rsp+1B8h+String1]
0x180059699  call    DhcpOemToUnicode
0x18005969e  test    rax, rax
0x1800596a1  jnz     short loc_1800596AD
0x1800596a3  mov     edi, 4E2Fh
0x1800596a8  jmp     loc_18005A1FD
0x1800596ad  mov     [rsp+1B8h+nSize], 19h
0x1800596b5  lea     rdx, [rsp+1B8h+nSize]; nSize
0x1800596ba  lea     rcx, [rsp+1B8h+Buffer]; lpBuffer
0x1800596c2  call    cs:__imp_GetComputerNameW
0x1800596c9  nop     dword ptr [rax+rax+00h]
0x1800596ce  test    eax, eax
0x1800596d0  jnz     short loc_18005971E
0x1800596d2  call    cs:__imp_GetLastError
0x1800596d9  nop     dword ptr [rax+rax+00h]
0x1800596de  mov     edi, eax
0x1800596e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800596e7  lea     rax, WPP_GLOBAL_Control
0x1800596ee  cmp     rcx, rax
0x1800596f1  jz      loc_18005A1FD
0x1800596f7  test    byte ptr [rcx+1Ch], 10h
0x1800596fb  jz      loc_18005A1FD
0x180059701  mov     edx, 2Fh ; '/'
0x180059706  mov     r9d, edi
0x180059709  lea     r8, WPP_079646765da4361deec0b4ab82b940ea_Traceguids
0x180059710  mov     rcx, [rcx+10h]
0x180059714  call    WPP_SF_D
0x180059719  jmp     loc_18005A1FD
0x18005971e  mov     eax, 18h
0x180059723  cmp     [rsp+1B8h+nSize], 19h
0x180059728  cmovb   eax, [rsp+1B8h+nSize]
0x18005972d  add     rax, rax
0x180059730  cmp     rax, 32h ; '2'
0x180059734  jnb     loc_18005A237
0x18005973a  mov     [rsp+rax+1B8h+Buffer], r13w
0x180059743  lea     rdx, [rsp+1B8h+Buffer]; String2
0x18005974b  lea     rcx, [rsp+1B8h+String1]; String1
0x180059753  call    cs:__imp__wcsicmp
0x18005975a  nop     dword ptr [rax+rax+00h]
0x18005975f  test    eax, eax
0x180059761  jnz     loc_1800596A3
0x180059767  cmp     [r15+30h], r13
0x18005976b  jz      short loc_180059783
0x18005976d  mov     rcx, rsi
0x180059770  call    CheckMessageDirectedToThisServer
0x180059775  test    eax, eax
0x180059777  jnz     short loc_180059783
0x180059779  mov     edi, 4E30h
0x18005977e  jmp     loc_18005A1FD
0x180059783  lea     rax, [rsp+1B8h+var_15C]
0x180059788  mov     qword ptr [rsp+1B8h+dwFlags], rax; __int64
0x18005978d  lea     r9, [rsp+1B8h+Size]
0x180059792  lea     r8, [rsp+1B8h+cbDest]
0x180059797  mov     rdx, r15
0x18005979a  mov     rcx, rsi
0x18005979d  call    DhcpDetermineInfoFromMessage
0x1800597a2  mov     edi, eax
0x1800597a4  test    eax, eax
0x1800597a6  jnz     loc_18005A1FD
0x1800597ac  mov     rdx, rsi
0x1800597af  mov     ecx, dword ptr [rsp+1B8h+var_15C]
0x1800597b3  call    DhcpGetSubnetForAddress
0x1800597b8  mov     rcx, [rsi+58h]
0x1800597bc  lea     ebx, [rdi+1]
0x1800597bf  cmp     [rcx+10C4h], ebx
0x1800597c5  jnz     loc_1800598BA
0x1800597cb  cmp     dword ptr [rcx+10D4h], 3
0x1800597d2  jnz     loc_18005988A
0x1800597d8  mov     eax, [rcx+10CCh]
0x1800597de  test    eax, eax
0x1800597e0  jnz     short loc_180059807
0x1800597e2  cmp     [rcx+10C8h], r13d
0x1800597e9  jnz     short loc_180059807
0x1800597eb  mov     r8d, dword ptr [rsp+1B8h+Size]
0x1800597f0  mov     rdx, [rsp+1B8h+cbDest]
0x1800597f5  mov     ecx, [rcx+8]
0x1800597f8  call    AuditLogPacketDropDueToFailover
0x1800597fd  mov     edi, 6
0x180059802  jmp     loc_18005A1FD
0x180059807  cmp     eax, ebx
0x180059809  jnz     short loc_18005988A
0x18005980b  add     rcx, 10E0h
0x180059812  lea     rax, [rsp+1B8h+pszDest]
0x18005981a  mov     qword ptr [rsp+1B8h+dwFlags], rax
0x18005981f  mov     r15d, dword ptr [rsp+1B8h+Size]
0x180059824  mov     r9b, r15b
0x180059827  mov     r13, [rsp+1B8h+cbDest]
0x18005982c  mov     r8, r13
0x18005982f  call    DhcpFailoverVerifyHash
0x180059834  cmp     dword ptr [rsp+1B8h+pszDest], 0
0x18005983c  jnz     short loc_180059894
0x18005983e  mov     rax, [rsi+90h]
0x180059845  movzx   eax, word ptr [rax+260h]
0x18005984c  cmp     [rsi+80h], ebx
0x180059852  jnz     short loc_180059863
0x180059854  movzx   ecx, ax; hostshort
0x180059857  call    cs:__imp_htons
0x18005985e  nop     dword ptr [rax+rax+00h]
0x180059863  movzx   eax, ax
0x180059866  cmp     eax, cs:DhcpGlobalMaxPacketElapsedTime
0x18005986c  jnb     short loc_180059894
0x18005986e  mov     edi, 57h ; 'W'
0x180059873  mov     rcx, [rsi+58h]
0x180059877  mov     r8d, r15d
0x18005987a  mov     rdx, r13
0x18005987d  mov     ecx, [rcx+8]
0x180059880  call    AuditLogPacketDropDueToFailover
0x180059885  jmp     loc_18005A1FD
0x18005988a  mov     r13, [rsp+1B8h+cbDest]
0x18005988f  mov     r15d, dword ptr [rsp+1B8h+Size]
0x180059894  mov     rax, [rsi+58h]
0x180059898  mov     ecx, [rax+10D4h]
0x18005989e  cmp     ecx, 6
0x1800598a1  jz      loc_1800597FD
0x1800598a7  cmp     ecx, 2
0x1800598aa  jbe     loc_1800597FD
0x1800598b0  cmp     ecx, 9
0x1800598b3  jb      short loc_1800598C4
0x1800598b5  jmp     loc_1800597FD
0x1800598ba  mov     r13, [rsp+1B8h+cbDest]
0x1800598bf  mov     r15d, dword ptr [rsp+1B8h+Size]
0x1800598c4  test    r14, r14
0x1800598c7  jz      short loc_180059904
0x1800598c9  cmp     dword ptr [r14+4Ch], 0
0x1800598ce  jz      short loc_180059904
0x1800598d0  mov     [rsp+1B8h+var_188], r15d; Size
0x1800598d5  mov     [rsp+1B8h+pszFormat], r13; Buf1
0x1800598da  mov     rax, [rsp+1B8h+var_110]
0x1800598e2  mov     qword ptr [rsp+1B8h+dwFlags], rax; __int64
0x1800598e7  mov     r9, r14
0x1800598ea  mov     r8, [rsp+1B8h+var_128]
0x1800598f2  mov     rdx, r14
0x1800598f5  mov     rcx, rsi; int
0x1800598f8  call    HandlePingCallback
0x1800598fd  mov     edi, eax
0x1800598ff  jmp     loc_18005A1FD
0x180059904  lea     rcx, DhcpGlobalInProgressCritSect; lpCriticalSection
0x18005990b  call    cs:__imp_EnterCriticalSection
0x180059912  nop     dword ptr [rax+rax+00h]
0x180059917  lea     r9, [rsp+1B8h+lpMem]
0x18005991c  xor     r8d, r8d
0x18005991f  mov     edx, r15d; Size
0x180059922  mov     rcx, r13; Buf1
0x180059925  call    DhcpFindPendingCtxt
0x18005992a  mov     rbx, [rsp+1B8h+lpMem]
0x18005992f  test    rbx, rbx
0x180059932  jz      loc_180059CD7
0x180059938  mov     edi, [rbx+2Ch]
0x18005993b  mov     eax, edi
0x18005993d  and     eax, 0F0000000h
0x180059942  cmp     eax, 0E0000000h
0x180059947  jnz     short loc_180059961
0x180059949  lea     rcx, DhcpGlobalInProgressCritSect; lpCriticalSection
0x180059950  call    cs:__imp_LeaveCriticalSection
0x180059957  nop     dword ptr [rax+rax+00h]
0x18005995c  jmp     loc_180059779
0x180059961  cmp     dword ptr [rbx+48h], 0
0x180059965  jz      short loc_1800599C7
0x180059967  lea     rcx, DhcpGlobalInProgressCritSect; lpCriticalSection
0x18005996e  call    cs:__imp_LeaveCriticalSection
0x180059975  nop     dword ptr [rax+rax+00h]
0x18005997a  test    r14, r14
0x18005997d  jz      short loc_1800599BD
0x18005997f  mov     rax, cs:qword_180155830
0x180059986  test    rax, rax
0x180059989  jz      short loc_1800599B3
0x18005998b  lea     rdx, [r14+68h]
0x18005998f  lea     rcx, [r14+58h]
0x180059993  mov     r9, [r14+128h]
0x18005999a  mov     [rsp+1B8h+pszFormat], r9
0x18005999f  mov     qword ptr [rsp+1B8h+dwFlags], r14
0x1800599a4  mov     r9d, [r14+74h]
0x1800599a8  mov     r8d, 1
0x1800599ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800599b3  jmp     short loc_1800599BD
0x1800599b5  mov     ecx, eax
0x1800599b7  call    DhcpCalloutLogAV
0x1800599bc  nop
0x1800599bd  mov     edi, 3E5h
0x1800599c2  jmp     loc_18005A1FD
0x1800599c7  mov     edx, dword ptr [rsp+1B8h+var_15C]
0x1800599cb  mov     ecx, edi
0x1800599cd  call    DhcpInSameSuperScope
0x1800599d2  test    eax, eax
0x1800599d4  jnz     loc_180059AEC
0x1800599da  and     dword ptr [rsp+1B8h+Size+4], eax
0x1800599de  and     dword ptr [rsp+1B8h+Size], eax
0x1800599e2  mov     rcx, rbx
0x1800599e5  call    DhcpRemovePendingCtxt
0x1800599ea  mov     rcx, rbx; lpMem
0x1800599ed  call    DhcpDeletePendingCtxt
0x1800599f2  mov     rdx, rsi
0x1800599f5  mov     ecx, edi
0x1800599f7  call    DhcpGetSubnetForAddress
0x1800599fc  test    eax, eax
0x1800599fe  jnz     loc_180059949
0x180059a04  mov     rax, [rsi+58h]
0x180059a08  test    rax, rax
0x180059a0b  jnz     short loc_180059A12
0x180059a0d  xor     r9d, r9d
0x180059a10  jmp     short loc_180059A16
0x180059a12  mov     r9d, [rax+8]
0x180059a16  and     [rsp+1B8h+lpMem], 0
0x180059a1c  lea     rax, [rsp+1B8h+Size+4]
0x180059a21  mov     [rsp+1B8h+pszFormat], rax; __int64
0x180059a26  lea     rax, [rsp+1B8h+lpMem]
0x180059a2b  mov     qword ptr [rsp+1B8h+dwFlags], rax; __int64
0x180059a30  mov     r8b, [r12+1]
0x180059a35  mov     edx, r15d; Size
0x180059a38  mov     rcx, r13; Src
0x180059a3b  call    DhcpMakeClientUID
0x180059a40  mov     edi, eax
0x180059a42  xor     r12d, r12d
0x180059a45  test    eax, eax
0x180059a47  jnz     loc_18005A1EA
0x180059a4d  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180059a54  call    cs:__imp_EnterCriticalSection
0x180059a5b  nop     dword ptr [rax+rax+00h]
0x180059a60  lea     r8, [rsp+1B8h+Size]
0x180059a65  mov     dl, byte ptr [rsp+1B8h+Size+4]
0x180059a69  mov     rbx, [rsp+1B8h+lpMem]
0x180059a6e  mov     rcx, rbx
0x180059a71  call    DhcpGetIpAddressFromHwAddress
0x180059a76  test    eax, eax
0x180059a78  jnz     short loc_180059A7F
0x180059a7a  mov     dword ptr [rsp+1B8h+Size], r12d
0x180059a7f  mov     ecx, dword ptr [rsp+1B8h+Size]
  ... truncated ...
```
