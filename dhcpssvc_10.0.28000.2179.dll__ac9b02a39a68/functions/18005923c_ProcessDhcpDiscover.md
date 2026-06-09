# ProcessDhcpDiscover

- ea: `0x18005923c`
- end: `0x180059f2d`
- name: `ProcessDhcpDiscover`
- size: `3313`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `38`
- tags: `broker_com_uri`

## callers

- `0x180057cf8`
- `0x18005cbfc`

## callees

- `0x180001838`
- `0x18000282c`
- `0x180003228`
- `0x180003258`
- `0x180005410`
- `0x180006234`
- `0x1800083cc`
- `0x18000cfc0`
- `0x180030e78`
- `0x180030f3c`
- `0x180030fb0`
- `0x180031178`
- `0x180031520`
- `0x180031b08`
- `0x180031b6c`
- `0x180032db8`
- `0x1800330c4`
- `0x1800331c0`
- `0x1800332a8`
- `0x1800539dc`
- `0x180054510`
- `0x180054bd8`
- `0x18005518c`
- `0x180055590`
- `0x180055640`
- `0x1800556d0`
- `0x180055ae8`
- `0x180057a90`
- `0x180057cf8`
- `0x180058208`
- `0x18005923c`
- `0x18008ef8c`
- `0x18008f5b4`
- `0x180098658`
- `0x1800c747c`
- `0x1800c8fd4`
- `0x1800cdac0`
- `0x1800cf010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180059445`
- `msvcrt!_wcsicmp` at `0x180059445`
- `msvcrt!time` at `0x180059de8`
- `msvcrt!time` at `0x180059de8`
- `WS2_32!__imp_htons` at `0x180059554`
- `WS2_32!__imp_htons` at `0x180059554`
- `KERNEL32!GetComputerNameW` at `0x1800593b4`
- `KERNEL32!GetComputerNameW` at `0x1800593b4`
- `KERNEL32!HeapAlloc` at `0x180059cf2`
- `KERNEL32!HeapAlloc` at `0x180059cf2`
- `KERNEL32!GetLastError` at `0x1800593c4`
- `KERNEL32!GetLastError` at `0x1800593c4`
- `KERNEL32!EnterCriticalSection` at `0x18005960a`
- `KERNEL32!EnterCriticalSection` at `0x180059759`
- `KERNEL32!EnterCriticalSection` at `0x180059871`
- `KERNEL32!EnterCriticalSection` at `0x1800598d6`
- `KERNEL32!EnterCriticalSection` at `0x180059aea`
- `KERNEL32!EnterCriticalSection` at `0x18005960a`
- `KERNEL32!EnterCriticalSection` at `0x180059759`
- `KERNEL32!EnterCriticalSection` at `0x180059871`
- `KERNEL32!EnterCriticalSection` at `0x1800598d6`
- `KERNEL32!EnterCriticalSection` at `0x180059aea`
- `KERNEL32!LeaveCriticalSection` at `0x18005964f`
- `KERNEL32!LeaveCriticalSection` at `0x18005966d`
- `KERNEL32!LeaveCriticalSection` at `0x1800597be`
- `KERNEL32!LeaveCriticalSection` at `0x18005980d`
- `KERNEL32!LeaveCriticalSection` at `0x180059840`
- `KERNEL32!LeaveCriticalSection` at `0x180059893`
- `KERNEL32!LeaveCriticalSection` at `0x1800598b0`
- `KERNEL32!LeaveCriticalSection` at `0x18005991f`
- `KERNEL32!LeaveCriticalSection` at `0x180059b12`
- `KERNEL32!LeaveCriticalSection` at `0x180059ee1`
- `KERNEL32!LeaveCriticalSection` at `0x18005964f`
- `KERNEL32!LeaveCriticalSection` at `0x18005966d`
- `KERNEL32!LeaveCriticalSection` at `0x1800597be`
- `KERNEL32!LeaveCriticalSection` at `0x18005980d`
- `KERNEL32!LeaveCriticalSection` at `0x180059840`
- `KERNEL32!LeaveCriticalSection` at `0x180059893`
- `KERNEL32!LeaveCriticalSection` at `0x1800598b0`
- `KERNEL32!LeaveCriticalSection` at `0x18005991f`
- `KERNEL32!LeaveCriticalSection` at `0x180059b12`
- `KERNEL32!LeaveCriticalSection` at `0x180059ee1`
- `KERNEL32!HeapFree` at `0x1800597db`
- `KERNEL32!HeapFree` at `0x180059da4`
- `KERNEL32!HeapFree` at `0x180059ea5`
- `KERNEL32!HeapFree` at `0x1800597db`
- `KERNEL32!HeapFree` at `0x180059da4`
- `KERNEL32!HeapFree` at `0x180059ea5`

## pseudocode

```c
__int64 __fastcall ProcessDhcpDiscover(__int64 a1, _QWORD *a2, __int64 a3, _DWORD *a4)
{
  __int64 v8; // r15
  __int64 v9; // rbx
  DWORD LastError; // edi
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  unsigned int v13; // r15d
  int v14; // edx
  int v15; // r9d
  __int64 v16; // rcx
  DWORD v17; // r12d
  void *v18; // r13
  u_short v19; // ax
  unsigned int v20; // ecx
  int v21; // eax
  DWORD v22; // eax
  int *v23; // rbx
  unsigned int v24; // edi
  __int64 v25; // rdx
  void *v26; // rbx
  DWORD v27; // eax
  __int64 v28; // rax
  int v29; // edx
  int v30; // ebx
  unsigned __int16 v31; // r15
  bool v32; // zf
  __int64 v33; // r8
  BOOL v34; // ebx
  DWORD v35; // eax
  __int64 v36; // rbx
  wchar_t *v37; // rax
  __int64 v38; // rcx
  wchar_t *v39; // rbx
  int v40; // r15d
  u_long v41; // eax
  _DWORD *v42; // rax
  unsigned int v43; // ebx
  __int64 v44; // rax
  DWORD dwFlags[2]; // [rsp+20h] [rbp-1A8h]
  STRSAFE_LPCWSTR pszFormat; // [rsp+28h] [rbp-1A0h]
  STRSAFE_LPCWSTR pszFormatb; // [rsp+28h] [rbp-1A0h]
  STRSAFE_LPCWSTR pszFormata; // [rsp+28h] [rbp-1A0h]
  u_long v50[2]; // [rsp+30h] [rbp-198h]
  int v51; // [rsp+50h] [rbp-178h] BYREF
  size_t Size; // [rsp+54h] [rbp-174h] BYREF
  int v53; // [rsp+5Ch] [rbp-16Ch] BYREF
  BOOL v54; // [rsp+60h] [rbp-168h]
  DWORD nSize; // [rsp+64h] [rbp-164h] BYREF
  size_t cbDest; // [rsp+68h] [rbp-160h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-158h] BYREF
  u_long v58[2]; // [rsp+78h] [rbp-150h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+80h] [rbp-148h] BYREF
  _QWORD *v60; // [rsp+88h] [rbp-140h]
  unsigned int v61; // [rsp+90h] [rbp-138h] BYREF
  _QWORD v62[2]; // [rsp+98h] [rbp-130h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-120h]
  __int64 v64; // [rsp+B0h] [rbp-118h]
  __int64 v65; // [rsp+B8h] [rbp-110h]
  WCHAR Buffer[32]; // [rsp+C0h] [rbp-108h] BYREF
  wchar_t String1[64]; // [rsp+100h] [rbp-C8h] BYREF

  v63 = (__int64)a4;
  v60 = a2;
  nSize = 0;
  cbDest = 0;
  Size = 0;
  v51 = -1;
  v61 = 0;
  lpMem = 0;
  v58[1] = 0;
  v58[0] = 0;
  v53 = 0;
  LODWORD(pszDest) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids);
  *(_DWORD *)(a1 + 200) = 1;
  if ( a4 )
    *a4 = 0;
  if ( !a3 || !*(_DWORD *)(a3 + 76) && *(_BYTE *)(a3 + 73) != 6 )
    _InterlockedAdd(&DhcpGlobalNumDiscovers, 1u);
  v8 = *a2;
  v65 = v8;
  v54 = v8 == 0;
  v62[0] = 0;
  v62[1] = 0;
  v9 = *(_QWORD *)a1;
  v64 = v9;
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
        goto LABEL_129;
      }
      nSize = 25;
      if ( !GetComputerNameW(Buffer, &nSize) )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids, LastError);
        goto LABEL_129;
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
      goto LABEL_129;
    }
    LastError = DhcpDetermineInfoFromMessage(a1, (_DWORD)a2, (unsigned int)&cbDest, (unsigned int)&Size, (__int64)&v61);
    if ( LastError )
      goto LABEL_129;
    v13 = v61;
    DhcpGetSubnetForAddress(v61, a1);
    v16 = *(_QWORD *)(a1 + 88);
    if ( *(_DWORD *)(v16 + 4292) == 1 )
    {
      if ( *(_DWORD *)(v16 + 4308) != 3 )
        goto LABEL_38;
      if ( !*(_QWORD *)(v16 + 4296) )
      {
        AuditLogPacketDropDueToFailover(*(unsigned int *)(v16 + 8), cbDest, (unsigned int)Size);
LABEL_31:
        LastError = 6;
        goto LABEL_129;
      }
      if ( *(_DWORD *)(v16 + 4300) == 1 )
      {
        v17 = Size;
        LOBYTE(v15) = Size;
        v18 = (void *)cbDest;
        DhcpFailoverVerifyHash(v16 + 4320, v14, cbDest, v15, (__int64)&pszDest);
        if ( !(_DWORD)pszDest )
        {
          v19 = *(_WORD *)(*(_QWORD *)(a1 + 144) + 608LL);
          if ( *(_DWORD *)(a1 + 128) == 1 )
            v19 = htons(v19);
          if ( v19 < (unsigned int)DhcpGlobalMaxPacketElapsedTime )
          {
            LastError = 87;
            AuditLogPacketDropDueToFailover(*(unsigned int *)(*(_QWORD *)(a1 + 88) + 8LL), v18, v17);
            goto LABEL_129;
          }
        }
      }
      else
      {
LABEL_38:
        v18 = (void *)cbDest;
        v17 = Size;
      }
      v20 = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 4308LL);
      if ( v20 != 4 )
      {
        if ( v20 > 8 )
          goto LABEL_31;
        v21 = 424;
        if ( !_bittest(&v21, v20) )
          goto LABEL_31;
      }
    }
    else
    {
      v18 = (void *)cbDest;
      v17 = Size;
    }
    if ( a3 && *(_DWORD *)(a3 + 76) )
    {
      v50[0] = v17;
      v22 = HandlePingCallback(a1, v63, v18, *(size_t *)v50);
      goto LABEL_47;
    }
    EnterCriticalSection(&DhcpGlobalInProgressCritSect);
    DhcpFindPendingCtxt(v18, v17);
    v23 = (int *)lpMem;
    if ( !lpMem )
      goto LABEL_65;
    v24 = *((_DWORD *)lpMem + 11);
    if ( (v24 & 0xF0000000) == 0xE0000000 )
    {
LABEL_50:
      LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
      goto LABEL_25;
    }
    if ( *((_DWORD *)lpMem + 18) )
    {
      LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
      if ( a3 && qword_1801577D0 )
        qword_1801577D0(a3 + 88, a3 + 104, 1, *(unsigned int *)(a3 + 116), a3, *(_QWORD *)(a3 + 296));
      LastError = 997;
      goto LABEL_129;
    }
    if ( !(unsigned int)DhcpInSameSuperScope(v24, v13) )
    {
      Size = 0;
      DhcpRemovePendingCtxt(v23);
      DhcpDeletePendingCtxt(v23);
      if ( (unsigned int)DhcpGetSubnetForAddress(v24, a1) )
        goto LABEL_50;
      lpMem = 0;
      LastError = DhcpMakeClientUID(v18, v17, (__int64)&lpMem, (__int64)&Size + 4);
      if ( LastError )
        goto LABEL_128;
      EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      LOBYTE(v25) = BYTE4(Size);
      v26 = lpMem;
      if ( !(unsigned int)DhcpGetIpAddressFromHwAddress(lpMem, v25, &Size) )
        LODWORD(Size) = 0;
      if ( (_DWORD)Size )
        DhcpRemoveClientEntry((struct in_addr)Size, (__int64)v26, HIDWORD(Size), 1, 0, 1u, 0, *(_QWORD *)(a1 + 88));
      LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      if ( v26 )
        HeapFree(gDhcpHeap, 0, v26);
LABEL_65:
      v51 = 0;
      v27 = DhcpLookupReservationByHardwareAddress(v13, v18, v17, a1);
      LastError = v27;
      if ( !v27 )
      {
        LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
        v28 = *(_QWORD *)(a1 + 112);
        if ( v28 )
        {
          v29 = *(_DWORD *)(v28 + 8);
          v51 = v29;
          LOBYTE(v28) = *(_BYTE *)(v28 + 12);
        }
        else
        {
          v29 = v51;
        }
        if ( v65 )
          v32 = (v28 & 1) == 0;
        else
          v32 = (v28 & 2) == 0;
        if ( v32 )
          goto LABEL_25;
        v33 = *(_QWORD *)(a1 + 88);
        if ( *(_DWORD *)(v33 + 36) == 1 || *(_DWORD *)(v33 + 36) == 3 )
          goto LABEL_25;
        ValidateSubRangeForAddress(a1 + 168, v29, v33, a1 + 152, (__int64)&v53, (__int64)v62, a1 + 168, a1 + 184);
        LODWORD(pszFormatb) = v17;
        v22 = DhcpProcessDiscoverForValidatedAddress(v51, a1, v18, (size_t)pszFormatb, 0);
        goto LABEL_47;
      }
      if ( v27 == 2 )
      {
        if ( (unsigned int)DhcpGetSubnetForAddress(v13, a1) )
          goto LABEL_50;
        EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
        LastError = DhcpLookupDatabaseByHardwareAddress(a1, v18, v17, &v51);
        LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
        v34 = v54;
        if ( !LastError )
        {
          if ( !(unsigned int)DhcpSubnetIsDisabled(*(_QWORD *)(a1 + 88), v54) )
          {
            LastError = ValidateSubRangeForAddress(
                          (int)a1 + 168,
                          v51,
                          *(_QWORD *)(a1 + 88),
                          (int)a1 + 152,
                          (__int64)&v53,
                          (__int64)v62,
                          a1 + 168,
                          a1 + 184);
            if ( !LastError )
            {
              if ( v53 )
              {
                LODWORD(pszFormata) = v17;
                LastError = DhcpProcessDiscoverForValidatedAddress(v51, a1, v18, (size_t)pszFormata, 1);
                if ( LastError != 20016 )
                  goto LABEL_128;
              }
            }
            if ( LastError && LastError != 20016 )
              goto LABEL_128;
          }
          DhcpRemoveClientEntry((struct in_addr)v51, 0, 0, 1, 0, 1u, 0, *(_QWORD *)(a1 + 88));
          LastError = 2;
        }
        if ( LastError == 2 )
        {
          v35 = DhcpDiscoverValidateRequestedAddress(a1, v60[2], v34, (unsigned int)&v51, (__int64)v62);
          LastError = v35;
          if ( !v35 )
          {
LABEL_102:
            v36 = *(_QWORD *)(a1 + 88);
            if ( v36 )
              LODWORD(v36) = *(_DWORD *)(v36 + 8);
            if ( v51 != (_DWORD)v36 )
            {
              LODWORD(pszFormat) = v17;
              LastError = DhcpProcessDiscoverForValidatedAddress(v51, a1, v18, (size_t)pszFormat, 1);
              if ( LastError != 20016 )
                goto LABEL_128;
            }
            v51 = v36;
            LastError = DhcpRequestSomeAddress(a1, (unsigned int)&v51, v54, (unsigned int)v62, 0);
            if ( LastError == 20012 )
            {
              cbDest = 4LL * v17 + 2;
              lpMem = v18;
              v37 = (wchar_t *)HeapAlloc(gDhcpHeap, 8u, cbDest);
              v39 = v37;
              if ( !v37 )
              {
                LastError = 8;
                goto LABEL_128;
              }
              pszDest = v37;
              v40 = 0;
              if ( v17 )
              {
                while ( 1 )
                {
                  v41 = *(unsigned __int8 *)lpMem;
                  lpMem = (char *)lpMem + 1;
                  v50[0] = v41;
                  if ( StringCbPrintfExW(pszDest, cbDest, &pszDest, &cbDest, 0x1200u, L"%.2X", *(_QWORD *)v50) < 0 )
                    break;
                  if ( ++v40 >= v17 )
                    goto LABEL_112;
                }
                HeapFree(gDhcpHeap, 0, v39);
                LastError = 13;
                goto LABEL_128;
              }
LABEL_112:
              if ( (Microsoft_Windows_DHCP_ServerEnableBits & 0x40) != 0 )
                McTemplateU0zz_EventWriteTransfer(
                  v38,
                  &ClientRequestDropped,
                  v39,
                  *(_QWORD *)(*(_QWORD *)(a1 + 88) + 136LL));
              HeapFree(gDhcpHeap, 0, v39);
            }
            if ( LastError == 20012 )
            {
              v42 = *(_DWORD **)(a1 + 88);
              if ( v42[1073] == 1 && v42[1077] == 5 )
              {
                v43 = v42[1076] + v42[1078];
                if ( v43 < (unsigned int)time(0) )
                  LastError = DhcpRequestSomeAddress(a1, (unsigned int)&v51, v54, (unsigned int)v62, 1);
              }
              if ( LastError == 20012 )
                DhcpGlobalScavengeIpAddress = 1;
            }
            if ( LastError )
              goto LABEL_128;
            if ( !DhcpGlobalDetectConflictRetries )
            {
              LODWORD(pszFormat) = v17;
              LastError = DhcpProcessDiscoverForValidatedAddress(v51, a1, v18, (size_t)pszFormat, 1);
              goto LABEL_128;
            }
LABEL_124:
            v44 = DhcpCalculateTime(600);
            LastError = DhcpAddPendingCtxt(v18, v17, 0, 0, 0, v44, 1);
            if ( !LastError )
            {
              *(_DWORD *)(a3 + 76) = v51;
              *(_DWORD *)(a3 + 80) = 0;
              *(_DWORD *)v63 = 997;
            }
            goto LABEL_128;
          }
          if ( v35 == 997 )
          {
            if ( DhcpGlobalDetectConflictRetries )
              goto LABEL_124;
            goto LABEL_102;
          }
        }
      }
LABEL_128:
      LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
      goto LABEL_129;
    }
    v51 = v23[11];
    v30 = v23[19];
    LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
    LastError = DhcpGetSubnetForAddress((unsigned int)v51, a1);
    v31 = *(_WORD *)(*(_QWORD *)(a1 + 88) + 156LL) - 1;
    EnterCriticalSection(&DhcpGlobalInProgressCritSect);
    if ( !v30 && v31 <= 0x3E7u )
    {
      LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
      LastError = 20014;
      goto LABEL_129;
    }
    LeaveCriticalSection(&DhcpGlobalInProgressCritSect);
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 88) + 4292LL) == 1 )
    {
      EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      DhcpGetFailoverLeaseDuration(a1, v51, &v58[1], (int *)&pszDest, v58, (int *)&Size + 1, 0);
      LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    }
    else if ( *(_QWORD *)(a1 + 144) )
    {
      GetLeaseInfo(a1, 0);
    }
    if ( !LastError )
    {
      if ( (unsigned int)DhcpSubnetIsAddressOutOfRange(*(_QWORD *)(a1 + 88), (unsigned int)v51, v54)
        || (unsigned int)ValidateSubRangeForAddress(
                           (int)a1 + 168,
                           v51,
                           *(_QWORD *)(a1 + 88),
                           (int)a1 + 152,
                           (__int64)&v53,
                           (__int64)v62,
                           a1 + 168,
                           a1 + 184)
        || !v53 )
      {
        goto LABEL_25;
      }
      dwFlags[0] = v17;
      v22 = DhcpRespondToDiscover(a1, *(size_t *)dwFlags, v51, v58[1], v58[0], HIDWORD(Size));
LABEL_47:
      LastError = v22;
    }
  }
LABEL_129:
  MemArrayFree(v62, MemFreeSubnetSatisfiedPolicies);
  return LastError;
}

```

## disassembly

```asm
0x18005923c  push    rbx
0x18005923e  push    rsi
0x18005923f  push    rdi
0x180059240  push    r12
0x180059242  push    r13
0x180059244  push    r14
0x180059246  push    r15
0x180059248  sub     rsp, 190h
0x18005924f  mov     rax, cs:__security_cookie
0x180059256  xor     rax, rsp
0x180059259  mov     [rsp+1C8h+var_48], rax
0x180059261  mov     rbx, r9
0x180059264  mov     [rsp+1C8h+var_120], rbx
0x18005926c  mov     r14, r8
0x18005926f  mov     r12, rdx
0x180059272  mov     [rsp+1C8h+var_140], rdx
0x18005927a  mov     rsi, rcx
0x18005927d  xor     r13d, r13d
0x180059280  mov     [rsp+1C8h+nSize], r13d
0x180059285  mov     [rsp+1C8h+cbDest], r13
0x18005928a  mov     dword ptr [rsp+1C8h+Size], r13d
0x18005928f  mov     [rsp+1C8h+var_178], 0FFFFFFFFh
0x180059297  mov     [rsp+1C8h+var_138], r13d
0x18005929f  mov     [rsp+1C8h+lpMem], r13
0x1800592a4  mov     [rsp+1C8h+var_150+4], r13d
0x1800592a9  mov     [rsp+1C8h+var_150], r13d
0x1800592ae  mov     dword ptr [rsp+1C8h+Size+4], r13d
0x1800592b3  mov     [rsp+1C8h+var_16C], r13d
0x1800592b8  mov     dword ptr [rsp+1C8h+pszDest], r13d
0x1800592c0  lea     rax, WPP_GLOBAL_Control
0x1800592c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800592ce  cmp     rcx, rax
0x1800592d1  jz      short loc_1800592ED
0x1800592d3  test    byte ptr [rcx+1Ch], 20h
0x1800592d7  jz      short loc_1800592ED
0x1800592d9  lea     edx, [r13+2Eh]
0x1800592dd  lea     r8, WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids
0x1800592e4  mov     rcx, [rcx+10h]
0x1800592e8  call    WPP_SF_
0x1800592ed  mov     eax, 1
0x1800592f2  mov     [rsi+0C8h], eax
0x1800592f8  test    rbx, rbx
0x1800592fb  jz      short loc_180059300
0x1800592fd  mov     [rbx], r13d
0x180059300  test    r14, r14
0x180059303  jz      short loc_180059312
0x180059305  cmp     [r14+4Ch], r13d
0x180059309  jnz     short loc_180059319
0x18005930b  cmp     byte ptr [r14+49h], 6
0x180059310  jz      short loc_180059319
0x180059312  lock add cs:DhcpGlobalNumDiscovers, eax
0x180059319  mov     r15, [r12]
0x18005931d  mov     [rsp+1C8h+var_110], r15
0x180059325  mov     eax, r13d
0x180059328  test    r15, r15
0x18005932b  setz    al
0x18005932e  mov     [rsp+1C8h+var_168], eax
0x180059332  mov     [rsp+1C8h+var_130], r13
0x18005933a  mov     [rsp+1C8h+var_128], r13
0x180059342  mov     rbx, [rsi]
0x180059345  mov     [rsp+1C8h+var_118], rbx
0x18005934d  mov     [rbx+6Bh], r13b
0x180059351  mov     [rbx+0EBh], r13b
0x180059358  mov     rdx, r12
0x18005935b  mov     rcx, rsi
0x18005935e  call    DhcpMessageCheckFilter
0x180059363  mov     edi, eax
0x180059365  test    eax, eax
0x180059367  jnz     loc_180059EED
0x18005936d  test    r15, r15
0x180059370  jnz     loc_180059459
0x180059376  lea     rcx, [rbx+2Ch]; SourceString
0x18005937a  cmp     [rcx], r13b
0x18005937d  jz      loc_180059459
0x180059383  lea     rdx, [rsp+1C8h+String1]
0x18005938b  call    DhcpOemToUnicode
0x180059390  test    rax, rax
0x180059393  jnz     short loc_18005939F
0x180059395  mov     edi, 4E2Fh
0x18005939a  jmp     loc_180059EED
0x18005939f  mov     [rsp+1C8h+nSize], 19h
0x1800593a7  lea     rdx, [rsp+1C8h+nSize]; nSize
0x1800593ac  lea     rcx, [rsp+1C8h+Buffer]; lpBuffer
0x1800593b4  call    cs:__imp_GetComputerNameW
0x1800593bb  nop     dword ptr [rax+rax+00h]
0x1800593c0  test    eax, eax
0x1800593c2  jnz     short loc_180059410
0x1800593c4  call    cs:__imp_GetLastError
0x1800593cb  nop     dword ptr [rax+rax+00h]
0x1800593d0  mov     edi, eax
0x1800593d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800593d9  lea     rax, WPP_GLOBAL_Control
0x1800593e0  cmp     rcx, rax
0x1800593e3  jz      loc_180059EED
0x1800593e9  test    byte ptr [rcx+1Ch], 10h
0x1800593ed  jz      loc_180059EED
0x1800593f3  mov     edx, 2Fh ; '/'
0x1800593f8  mov     r9d, edi
0x1800593fb  lea     r8, WPP_8d34d085f3b73e207e43a51a56ca0bcb_Traceguids
0x180059402  mov     rcx, [rcx+10h]
0x180059406  call    WPP_SF_D
0x18005940b  jmp     loc_180059EED
0x180059410  mov     eax, 18h
0x180059415  cmp     [rsp+1C8h+nSize], 19h
0x18005941a  cmovb   eax, [rsp+1C8h+nSize]
0x18005941f  add     rax, rax
0x180059422  cmp     rax, 32h ; '2'
0x180059426  jnb     loc_180059F27
0x18005942c  mov     [rsp+rax+1C8h+Buffer], r13w
0x180059435  lea     rdx, [rsp+1C8h+Buffer]; String2
0x18005943d  lea     rcx, [rsp+1C8h+String1]; String1
0x180059445  call    cs:__imp__wcsicmp
0x18005944c  nop     dword ptr [rax+rax+00h]
0x180059451  test    eax, eax
0x180059453  jnz     loc_180059395
0x180059459  cmp     [r12+30h], r13
0x18005945e  jz      short loc_180059476
0x180059460  mov     rcx, rsi
0x180059463  call    CheckMessageDirectedToThisServer
0x180059468  test    eax, eax
0x18005946a  jnz     short loc_180059476
0x18005946c  mov     edi, 4E30h
0x180059471  jmp     loc_180059EED
0x180059476  lea     rax, [rsp+1C8h+var_138]
0x18005947e  mov     qword ptr [rsp+1C8h+dwFlags], rax
0x180059483  lea     r9, [rsp+1C8h+Size]
0x180059488  lea     r8, [rsp+1C8h+cbDest]
0x18005948d  mov     rdx, r12
0x180059490  mov     rcx, rsi
0x180059493  call    DhcpDetermineInfoFromMessage
0x180059498  mov     edi, eax
0x18005949a  test    eax, eax
0x18005949c  jnz     loc_180059EED
0x1800594a2  mov     rdx, rsi
0x1800594a5  mov     r15d, [rsp+1C8h+var_138]
0x1800594ad  mov     ecx, r15d
0x1800594b0  call    DhcpGetSubnetForAddress
0x1800594b5  mov     rcx, [rsi+58h]
0x1800594b9  lea     ebx, [rdi+1]
0x1800594bc  cmp     [rcx+10C4h], ebx
0x1800594c2  jnz     loc_1800595B8
0x1800594c8  cmp     dword ptr [rcx+10D4h], 3
0x1800594cf  jnz     loc_180059587
0x1800594d5  mov     eax, [rcx+10CCh]
0x1800594db  test    eax, eax
0x1800594dd  jnz     short loc_180059504
0x1800594df  cmp     [rcx+10C8h], r13d
0x1800594e6  jnz     short loc_180059504
0x1800594e8  mov     r8d, dword ptr [rsp+1C8h+Size]
0x1800594ed  mov     rdx, [rsp+1C8h+cbDest]
0x1800594f2  mov     ecx, [rcx+8]
0x1800594f5  call    AuditLogPacketDropDueToFailover
0x1800594fa  mov     edi, 6
0x1800594ff  jmp     loc_180059EED
0x180059504  cmp     eax, ebx
0x180059506  jnz     short loc_180059587
0x180059508  add     rcx, 10E0h
0x18005950f  lea     rax, [rsp+1C8h+pszDest]
0x180059517  mov     qword ptr [rsp+1C8h+dwFlags], rax
0x18005951c  mov     r12d, dword ptr [rsp+1C8h+Size]
0x180059521  mov     r9b, r12b
0x180059524  mov     r13, [rsp+1C8h+cbDest]
0x180059529  mov     r8, r13
0x18005952c  call    DhcpFailoverVerifyHash
0x180059531  cmp     dword ptr [rsp+1C8h+pszDest], 0
0x180059539  jnz     short loc_180059591
0x18005953b  mov     rax, [rsi+90h]
0x180059542  movzx   eax, word ptr [rax+260h]
0x180059549  cmp     [rsi+80h], ebx
0x18005954f  jnz     short loc_180059560
0x180059551  movzx   ecx, ax; hostshort
0x180059554  call    cs:__imp_htons
0x18005955b  nop     dword ptr [rax+rax+00h]
0x180059560  movzx   eax, ax
0x180059563  cmp     eax, cs:DhcpGlobalMaxPacketElapsedTime
0x180059569  jnb     short loc_180059591
0x18005956b  mov     edi, 57h ; 'W'
0x180059570  mov     rcx, [rsi+58h]
0x180059574  mov     r8d, r12d
0x180059577  mov     rdx, r13
0x18005957a  mov     ecx, [rcx+8]
0x18005957d  call    AuditLogPacketDropDueToFailover
0x180059582  jmp     loc_180059EED
0x180059587  mov     r13, [rsp+1C8h+cbDest]
0x18005958c  mov     r12d, dword ptr [rsp+1C8h+Size]
0x180059591  mov     rax, [rsi+58h]
0x180059595  mov     ecx, [rax+10D4h]
0x18005959b  cmp     ecx, 4
0x18005959e  jz      short loc_1800595C2
0x1800595a0  cmp     ecx, 8
0x1800595a3  ja      loc_1800594FA
0x1800595a9  mov     eax, 1A8h
0x1800595ae  bt      eax, ecx
0x1800595b1  jb      short loc_1800595C2
0x1800595b3  jmp     loc_1800594FA
0x1800595b8  mov     r13, [rsp+1C8h+cbDest]
0x1800595bd  mov     r12d, dword ptr [rsp+1C8h+Size]
0x1800595c2  xor     edi, edi
0x1800595c4  test    r14, r14
0x1800595c7  jz      short loc_180059603
0x1800595c9  cmp     [r14+4Ch], edi
0x1800595cd  jz      short loc_180059603
0x1800595cf  mov     [rsp+1C8h+var_198], r12d; Size
0x1800595d4  mov     [rsp+1C8h+pszFormat], r13; Buf1
0x1800595d9  mov     rax, [rsp+1C8h+var_120]
0x1800595e1  mov     qword ptr [rsp+1C8h+dwFlags], rax; __int64
0x1800595e6  mov     r9, r14
0x1800595e9  mov     r8, [rsp+1C8h+var_140]
0x1800595f1  mov     rdx, r14
0x1800595f4  mov     rcx, rsi; int
0x1800595f7  call    HandlePingCallback
0x1800595fc  mov     edi, eax
0x1800595fe  jmp     loc_180059EED
0x180059603  lea     rcx, DhcpGlobalInProgressCritSect; lpCriticalSection
0x18005960a  call    cs:__imp_EnterCriticalSection
0x180059611  nop     dword ptr [rax+rax+00h]
0x180059616  lea     r9, [rsp+1C8h+lpMem]
0x18005961b  xor     r8d, r8d
0x18005961e  mov     edx, r12d; Size
0x180059621  mov     rcx, r13; Buf1
0x180059624  call    DhcpFindPendingCtxt
0x180059629  mov     rbx, [rsp+1C8h+lpMem]
0x18005962e  test    rbx, rbx
0x180059631  jz      loc_1800597E7
0x180059637  mov     edi, [rbx+2Ch]
0x18005963a  mov     eax, edi
0x18005963c  and     eax, 0F0000000h
0x180059641  cmp     eax, 0E0000000h
0x180059646  jnz     short loc_180059660
0x180059648  lea     rcx, DhcpGlobalInProgressCritSect; lpCriticalSection
0x18005964f  call    cs:__imp_LeaveCriticalSection
0x180059656  nop     dword ptr [rax+rax+00h]
0x18005965b  jmp     loc_18005946C
0x180059660  cmp     dword ptr [rbx+48h], 0
0x180059664  jz      short loc_1800596C6
0x180059666  lea     rcx, DhcpGlobalInProgressCritSect; lpCriticalSection
0x18005966d  call    cs:__imp_LeaveCriticalSection
0x180059674  nop     dword ptr [rax+rax+00h]
0x180059679  test    r14, r14
0x18005967c  jz      short loc_1800596BC
0x18005967e  mov     rax, cs:qword_1801577D0
0x180059685  test    rax, rax
0x180059688  jz      short loc_1800596B2
0x18005968a  lea     rdx, [r14+68h]
0x18005968e  lea     rcx, [r14+58h]
0x180059692  mov     r9, [r14+128h]
0x180059699  mov     [rsp+1C8h+pszFormat], r9
0x18005969e  mov     qword ptr [rsp+1C8h+dwFlags], r14
0x1800596a3  mov     r9d, [r14+74h]
0x1800596a7  mov     r8d, 1
0x1800596ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596b2  jmp     short loc_1800596BC
0x1800596b4  mov     ecx, eax
0x1800596b6  call    DhcpCalloutLogAV
0x1800596bb  nop
0x1800596bc  mov     edi, 3E5h
0x1800596c1  jmp     loc_180059EED
0x1800596c6  mov     edx, r15d
0x1800596c9  mov     ecx, edi
0x1800596cb  call    DhcpInSameSuperScope
0x1800596d0  test    eax, eax
0x1800596d2  jnz     loc_18005982F
0x1800596d8  mov     dword ptr [rsp+1C8h+Size+4], eax
0x1800596dc  mov     dword ptr [rsp+1C8h+Size], eax
0x1800596e0  mov     rcx, rbx
0x1800596e3  call    DhcpRemovePendingCtxt
0x1800596e8  mov     rcx, rbx; lpMem
0x1800596eb  call    DhcpDeletePendingCtxt
0x1800596f0  mov     rdx, rsi
0x1800596f3  mov     ecx, edi
0x1800596f5  call    DhcpGetSubnetForAddress
0x1800596fa  test    eax, eax
0x1800596fc  jnz     loc_180059648
0x180059702  mov     rax, [rsi+58h]
0x180059706  test    rax, rax
0x180059709  jnz     short loc_180059710
0x18005970b  xor     r9d, r9d
0x18005970e  jmp     short loc_180059714
0x180059710  mov     r9d, [rax+8]
0x180059714  mov     [rsp+1C8h+lpMem], 0
0x18005971d  lea     rax, [rsp+1C8h+Size+4]
0x180059722  mov     [rsp+1C8h+pszFormat], rax; __int64
0x180059727  lea     rax, [rsp+1C8h+lpMem]
0x18005972c  mov     qword ptr [rsp+1C8h+dwFlags], rax; __int64
0x180059731  mov     r8, [rsp+1C8h+var_118]
0x180059739  mov     r8b, [r8+1]
0x18005973d  mov     edx, r12d; Size
0x180059740  mov     rcx, r13; Src
0x180059743  call    DhcpMakeClientUID
0x180059748  mov     edi, eax
0x18005974a  test    eax, eax
0x18005974c  jnz     loc_180059EDA
0x180059752  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180059759  call    cs:__imp_EnterCriticalSection
0x180059760  nop     dword ptr [rax+rax+00h]
0x180059765  lea     r8, [rsp+1C8h+Size]
0x18005976a  mov     dl, byte ptr [rsp+1C8h+Size+4]
0x18005976e  mov     rbx, [rsp+1C8h+lpMem]
0x180059773  mov     rcx, rbx
0x180059776  call    DhcpGetIpAddressFromHwAddress
  ... truncated ...
```
