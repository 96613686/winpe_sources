# DhcpBNDGetPendingBndUpdates

- ea: `0x1800bf964`
- end: `0x1800c026a`
- name: `DhcpBNDGetPendingBndUpdates`
- size: `2310`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c3294`

## callees

- `0x18000282c`
- `0x1800057e0`
- `0x180007bf8`
- `0x18001c45c`
- `0x180024720`
- `0x180024960`
- `0x18008f020`
- `0x180093144`
- `0x1800932a8`
- `0x1800a03f0`
- `0x1800a0418`
- `0x1800a0448`
- `0x1800a05b8`
- `0x1800a0758`
- `0x1800a08f4`
- `0x1800a0b3c`
- `0x1800a0b68`
- `0x1800a0bac`
- `0x1800bf854`
- `0x1800bf964`
- `0x1800c66c8`
- `0x1800ca0c8`
- `0x1800caad8`
- `0x1800cda7a`

## import_xrefs

- `ESENT!JetSetIndexRange` at `0x1800bfbfd`
- `ESENT!JetSetIndexRange` at `0x1800bfbfd`
- `ESENT!JetMakeKey` at `0x1800bfbc7`
- `ESENT!JetMakeKey` at `0x1800bfbc7`
- `ESENT!JetPrepareUpdate` at `0x1800bfcf4`
- `ESENT!JetPrepareUpdate` at `0x1800bfcf4`
- `KERNEL32!HeapAlloc` at `0x1800bfb1b`
- `KERNEL32!HeapAlloc` at `0x1800bfb1b`
- `KERNEL32!LocalFree` at `0x1800c0105`
- `KERNEL32!LocalFree` at `0x1800c01fa`
- `KERNEL32!LocalFree` at `0x1800c0105`
- `KERNEL32!LocalFree` at `0x1800c01fa`
- `KERNEL32!EnterCriticalSection` at `0x1800bfb50`
- `KERNEL32!EnterCriticalSection` at `0x1800bfb50`
- `KERNEL32!LeaveCriticalSection` at `0x1800c01d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800c01d6`
- `KERNEL32!HeapFree` at `0x1800bfb98`
- `KERNEL32!HeapFree` at `0x1800bfb98`

## string_xrefs

- `0x1800bfd02`: `DhcpDALJetPrepareUpdate`
- `0x1800bfbd5`: `DhcpBNDGetPendingBndUpdates`
- `0x1800bfc0b`: `DhcpBNDGetPendingBndUpdates`
- `0x1800c01c1`: `DhcpBNDGetPendingBndUpdates`

## pseudocode

```c
__int64 __fastcall DhcpBNDGetPendingBndUpdates(
        __int64 a1,
        unsigned int a2,
        int *a3,
        __int64 a4,
        int a5,
        _DWORD *a6,
        _DWORD *a7,
        _DWORD *a8)
{
  int *v8; // r12
  _DWORD *v11; // r13
  int v12; // r15d
  unsigned int MAddressInfo; // eax
  unsigned int Value; // ebx
  int *v16; // rcx
  _DWORD *v17; // rdi
  int *v18; // rax
  unsigned int Key; // eax
  unsigned int v20; // eax
  unsigned int Record; // edi
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  unsigned int CurrentFailoverClientInfo; // eax
  unsigned __int16 *v28; // rdi
  __int64 v29; // rbx
  _DWORD *v30; // rcx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  int v34; // eax
  bool v35; // zf
  int v36; // edx
  __int64 v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  int v45; // r13d
  __int64 v46; // r15
  __int64 v47; // r12
  unsigned int v48; // eax
  __int64 v49; // r9
  char v50; // cl
  HLOCAL v51; // rbx
  HLOCAL v52; // rdi
  int v53; // [rsp+50h] [rbp-128h]
  int v54; // [rsp+58h] [rbp-120h]
  bool v55[8]; // [rsp+F8h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+100h] [rbp-78h] BYREF
  int v57; // [rsp+108h] [rbp-70h]
  __int64 v58; // [rsp+10Ch] [rbp-6Ch] BYREF
  int v59; // [rsp+114h] [rbp-64h] BYREF
  unsigned int v60; // [rsp+118h] [rbp-60h] BYREF
  int v61; // [rsp+11Ch] [rbp-5Ch]
  int v62; // [rsp+120h] [rbp-58h]
  int v63; // [rsp+124h] [rbp-54h]
  int v64; // [rsp+128h] [rbp-50h] BYREF
  __int64 v65; // [rsp+130h] [rbp-48h] BYREF
  int v66; // [rsp+138h] [rbp-40h]
  __int64 v67; // [rsp+140h] [rbp-38h]
  int v68; // [rsp+158h] [rbp-20h] BYREF
  _DWORD pvData[31]; // [rsp+15Ch] [rbp-1Ch] BYREF

  v8 = a3;
  v65 = 0;
  v59 = 0;
  memset_0(&v68, 0, 0x50u);
  hMem = 0;
  v64 = 0;
  v58 = 0x100000000LL;
  *a8 = 0;
  v60 = 0;
  *a6 = 0;
  if ( !a4 )
    return 87;
  if ( !v8 )
    return 87;
  v11 = a7;
  if ( !a7 )
    return 87;
  v67 = a4;
  v12 = 0;
  v57 = 0;
  RwLockAcquireForRead(&DhcpGlobalReadWriteLock);
  if ( (a2 & 0xF0000000) == 0xE0000000 )
    MAddressInfo = MemServerGetMAddressInfo((_DWORD)DhcpGlobalThisServer, a2, (unsigned int)&v65, 0, 0, 0);
  else
    MAddressInfo = MemServerGetUAddressInfo((_DWORD)DhcpGlobalThisServer, a2, (unsigned int)&v65, 0, 0, 0);
  Value = MAddressInfo;
  if ( MAddressInfo == 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, a2);
    Value = 20005;
LABEL_16:
    RwLockRelease(&DhcpGlobalReadWriteLock);
    return Value;
  }
  if ( MAddressInfo )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      WPP_SF_dD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids,
        MAddressInfo,
        a2);
    goto LABEL_16;
  }
  if ( v65 != -72 && *(_DWORD *)(v65 + 72) )
  {
    v16 = **(int ***)(v65 + 80);
    v68 = *v16;
    pvData[0] = v16[1];
    RwLockRelease(&DhcpGlobalReadWriteLock);
    Value = 8;
    v17 = HeapAlloc(gDhcpHeap, 8u, 0x10u);
    if ( !v17 )
      return Value;
    v18 = &v68;
    if ( *v8 )
      v18 = v8;
    *(_QWORD *)v17 = v18;
    v17[2] = 4;
    v17[3] = 1;
    EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    Value = DhcpDALJetPrepareSearchEx(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, (__int64)v17, 1, 8u);
    HeapFree(gDhcpHeap, 0, v17);
    if ( Value
      || (Key = JetMakeKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, pvData, 4u, 1u),
          (Value = DhcpDALMapJetError(Key, "DhcpBNDGetPendingBndUpdates")) != 0)
      || (v20 = JetSetIndexRange(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 3u),
          (Value = DhcpDALMapJetError(v20, "DhcpBNDGetPendingBndUpdates")) != 0) )
    {
LABEL_106:
      LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      v52 = hMem;
      if ( hMem )
      {
        fgs__DHCP_CLIENT_INFO_FO_EX(hMem);
        LocalFree(v52);
      }
      return Value;
    }
    while ( 1 )
    {
      LODWORD(v58) = 4;
      Value = DhcpDALJetGetValue(
                DhcpGlobalJetServerSession,
                DhcpGlobalClientTableHandle,
                *(_DWORD *)(DhcpGlobalClientTable + 328),
                (__int64)&v58);
      if ( Value )
        goto LABEL_106;
      if ( HIDWORD(v58) )
        break;
      Record = DhcpDALJetNextRecord(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
LABEL_96:
      if ( Record )
      {
        Value = 0;
        *a6 += v12;
        if ( Record != 259 )
          Value = Record;
        goto LABEL_106;
      }
    }
    if ( HIDWORD(v58) <= 1 )
    {
LABEL_49:
      CurrentFailoverClientInfo = DhcpGetCurrentFailoverClientInfo((unsigned int)&hMem, 0, 0, 0, 1);
      Value = CurrentFailoverClientInfo;
      if ( CurrentFailoverClientInfo )
      {
        DhcpPrintFOErrorEx(
          CurrentFailoverClientInfo,
          "DhcpBNDGetPendingBndUpdates",
          "DhcpGetCurrentFailoverClientInfo",
          1866);
        goto LABEL_106;
      }
      v28 = (unsigned __int16 *)hMem;
      v29 = 0;
      v30 = (char *)hMem + 40;
      if ( !*((_DWORD *)hMem + 10) && !*((_DWORD *)hMem + 11) )
      {
LABEL_91:
        Record = DhcpDALJetNextRecord(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
        if ( Record == 259 )
          *v8 = 0;
        v51 = hMem;
        if ( hMem )
        {
          fgs__DHCP_CLIENT_INFO_FO_EX(hMem);
          LocalFree(v51);
        }
        hMem = 0;
        goto LABEL_96;
      }
      if ( *v30 != -1 || *((_DWORD *)hMem + 11) != 0x7FFFFFFF )
      {
        v31 = DhcpCalculateUTCTime(v30);
        *((_DWORD *)hMem + 10) = v31;
        *((_DWORD *)hMem + 11) = 0;
        v28 = (unsigned __int16 *)hMem;
      }
      DhcpBNDGetMessageSize(v28, &v60);
      if ( *v11 >= *(_DWORD *)&gFailoverMaxBndRecordsperPacket || (v66 = a5 - v12, a5 - v12 < v60) )
      {
        Value = 234;
        *v8 = *(_DWORD *)v28;
        *a6 += v12;
        *a8 = 1;
        goto LABEL_106;
      }
      LOBYTE(v33) = *((_BYTE *)v28 + 128);
      LOBYTE(v32) = *((_BYTE *)v28 + 73);
      v34 = MapOldStateToNewState(*((_QWORD *)v28 + 2) == 0, v32, v33);
      v35 = *((_DWORD *)v28 + 22) == 0;
      v36 = v34;
      LODWORD(v65) = v34;
      v37 = *((_QWORD *)v28 + 15);
      v55[0] = !v35;
      if ( v37 )
      {
        v38 = -1;
        do
          ++v38;
        while ( *(_WORD *)(v37 + 2 * v38) );
        v61 = 2 * v38 + 2;
      }
      else
      {
        v61 = 0;
      }
      v39 = *((_QWORD *)v28 + 7);
      if ( v39 )
      {
        v40 = -1;
        do
          ++v40;
        while ( *(_WORD *)(v39 + 2 * v40) );
        v62 = 2 * v40 + 2;
      }
      else
      {
        v62 = 0;
      }
      v41 = *((_QWORD *)v28 + 4);
      if ( v41 )
      {
        v42 = -1;
        do
          ++v42;
        while ( *(_WORD *)(v41 + 2 * v42) );
        v63 = 2 * v42 + 2;
      }
      else
      {
        v63 = 0;
      }
      v43 = *((_QWORD *)v28 + 3);
      if ( v43 )
      {
        v44 = -1;
        do
          ++v44;
        while ( *(_WORD *)(v43 + 2 * v44) );
        v45 = 2 * v44 + 2;
      }
      else
      {
        v45 = 0;
      }
      if ( (unsigned int)(v36 - 1) <= 2 && ((v29 = (__int64)(v28 + 54), v36 == 1) || v36 == 3) )
      {
        v46 = (__int64)(v28 + 46);
        if ( v36 == 1 )
          goto LABEL_84;
      }
      else
      {
        v46 = 0;
      }
      if ( (unsigned int)(v36 - 2) > 2 )
      {
        v47 = 0;
LABEL_85:
        v48 = MFFormatBndUpdRecord(
                (_DWORD)v28,
                (int)v28 + 128,
                (int)v28 + 73,
                v28[4],
                *((_QWORD *)v28 + 2),
                v47,
                v46,
                (__int64)(v28 + 52),
                v29,
                v53,
                v54,
                v45,
                *((_QWORD *)v28 + 3),
                v63,
                *((_QWORD *)v28 + 4),
                (__int64)(v28 + 2),
                (__int64)(v28 + 24),
                v62,
                *((_QWORD *)v28 + 7),
                (__int64)(v28 + 36),
                (__int64)(v28 + 38),
                (__int64)(v28 + 40),
                (__int64)v55,
                v61,
                *((_QWORD *)v28 + 15),
                v67,
                v66,
                (__int64)&v64,
                (__int64)(v28 + 66));
        Value = 0;
        if ( v48 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
          {
            WPP_SF_dD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids,
              v48,
              *(_DWORD *)hMem);
          }
          *a3 = *(_DWORD *)hMem;
          *a6 = v57;
          goto LABEL_106;
        }
        v11 = a7;
        v49 = (unsigned int)*a7;
        if ( (unsigned int)v49 < *(_DWORD *)&gFailoverMaxBndRecordsperPacket )
        {
          *(_DWORD *)(*(_QWORD *)(a1 + 16) + 152 * v49 + 56) = *(_DWORD *)hMem;
          v50 = v65;
          if ( *((_BYTE *)hMem + 73) == 4 )
            v50 = 7;
          *(_BYTE *)(*(_QWORD *)(a1 + 16) + 152 * v49 + 61) = v50;
          ++*(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
        }
        v12 = v64 + v57;
        v8 = a3;
        v67 = a4 + (unsigned int)(v64 + v57);
        *a7 = v49 + 1;
        v57 = v12;
        goto LABEL_91;
      }
LABEL_84:
      v47 = (__int64)(v28 + 20);
      goto LABEL_85;
    }
    v22 = DhcpDALJetBeginTransaction(DhcpGlobalJetServerSession);
    if ( v22 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, v22);
      }
      goto LABEL_49;
    }
    v23 = JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 2u);
    v24 = DhcpDALMapJetError(v23, "DhcpDALJetPrepareUpdate");
    if ( v24 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_47;
      }
      v26 = 45;
    }
    else
    {
      v59 = 1;
      v24 = DhcpDALJetSetValue(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableHandle,
              *(_DWORD *)(DhcpGlobalClientTable + 328),
              (unsigned int)&v59,
              4u);
      if ( v24 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_47;
        }
        v26 = 46;
      }
      else
      {
        v24 = DhcpDALJetCommitUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
        if ( !v24 )
        {
          DhcpDALJetCommitTransaction(DhcpGlobalJetServerSession);
          goto LABEL_49;
        }
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
LABEL_47:
          DhcpDALJetRollback(DhcpGlobalJetServerSession);
          goto LABEL_49;
        }
        v26 = 47;
      }
    }
    WPP_SF_D(v25[2], v26, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, v24);
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, a2);
  return 2;
}

```

## disassembly

```asm
0x1800bf964  mov     rax, rsp
0x1800bf967  mov     [rax+10h], rbx
0x1800bf96b  mov     [rax+20h], r9
0x1800bf96f  mov     [rax+18h], r8
0x1800bf973  mov     [rax+8], rcx
0x1800bf977  push    rbp
0x1800bf978  push    rsi
0x1800bf979  push    rdi
0x1800bf97a  push    r12
0x1800bf97c  push    r13
0x1800bf97e  push    r14
0x1800bf980  push    r15
0x1800bf982  lea     rbp, [rax-68h]
0x1800bf986  sub     rsp, 1A0h
0x1800bf98d  xor     esi, esi
0x1800bf98f  lea     rcx, [rbp+60h+var_80]; void *
0x1800bf993  mov     r12, r8
0x1800bf996  mov     [rbp+60h+var_A8], rsi
0x1800bf99a  mov     edi, edx
0x1800bf99c  mov     [rbp+60h+var_C4], esi
0x1800bf99f  xor     edx, edx; Val
0x1800bf9a1  mov     rbx, r9
0x1800bf9a4  lea     r14d, [rsi+1]
0x1800bf9a8  lea     r8d, [rsi+50h]; Size
0x1800bf9ac  mov     dword ptr [rbp+60h+var_CC+4], r14d
0x1800bf9b0  call    memset_0
0x1800bf9b5  mov     rax, [rbp+60h+arg_38]
0x1800bf9bc  mov     [rbp+60h+hMem], rsi
0x1800bf9c0  mov     [rbp+60h+var_B0], esi
0x1800bf9c3  mov     dword ptr [rbp+60h+var_CC], esi
0x1800bf9c6  mov     [rax], esi
0x1800bf9c8  mov     rax, [rbp+60h+arg_28]
0x1800bf9cf  mov     [rbp+60h+var_C0], esi
0x1800bf9d2  mov     [rax], esi
0x1800bf9d4  test    rbx, rbx
0x1800bf9d7  jz      loc_1800C0249
0x1800bf9dd  test    r12, r12
0x1800bf9e0  jz      loc_1800C0249
0x1800bf9e6  mov     r13, [rbp+60h+arg_30]
0x1800bf9ed  test    r13, r13
0x1800bf9f0  jz      loc_1800C0249
0x1800bf9f6  lea     rcx, DhcpGlobalReadWriteLock
0x1800bf9fd  mov     [rbp+60h+var_98], rbx
0x1800bfa01  mov     r15d, esi
0x1800bfa04  mov     [rbp+60h+var_D0], esi
0x1800bfa07  call    RwLockAcquireForRead
0x1800bfa0c  mov     rcx, cs:DhcpGlobalThisServer
0x1800bfa13  lea     r8, [rbp+60h+var_A8]
0x1800bfa17  mov     eax, edi
0x1800bfa19  mov     qword ptr [rsp+1D0h+var_1A8], rsi
0x1800bfa1e  and     eax, 0F0000000h
0x1800bfa23  mov     qword ptr [rsp+1D0h+grbit], rsi
0x1800bfa28  xor     r9d, r9d
0x1800bfa2b  mov     edx, edi
0x1800bfa2d  cmp     eax, 0E0000000h
0x1800bfa32  jnz     short loc_1800BFA3B
0x1800bfa34  call    MemServerGetMAddressInfo
0x1800bfa39  jmp     short loc_1800BFA40
0x1800bfa3b  call    MemServerGetUAddressInfo
0x1800bfa40  mov     ebx, eax
0x1800bfa42  cmp     eax, 2
0x1800bfa45  jnz     short loc_1800BFA83
0x1800bfa47  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfa4e  lea     rsi, WPP_GLOBAL_Control
0x1800bfa55  cmp     rcx, rsi
0x1800bfa58  jz      short loc_1800BFA7C
0x1800bfa5a  mov     r14d, 800000h
0x1800bfa60  test    [rcx+1Ch], r14d
0x1800bfa64  jz      short loc_1800BFA7C
0x1800bfa66  mov     rcx, [rcx+10h]
0x1800bfa6a  lea     edx, [rax+27h]
0x1800bfa6d  mov     r9d, edi
0x1800bfa70  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800bfa77  call    WPP_SF_D
0x1800bfa7c  mov     ebx, 4E25h
0x1800bfa81  jmp     short loc_1800BFAC2
0x1800bfa83  test    ebx, ebx
0x1800bfa85  jz      short loc_1800BFAD5
0x1800bfa87  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfa8e  lea     rsi, WPP_GLOBAL_Control
0x1800bfa95  cmp     rcx, rsi
0x1800bfa98  jz      short loc_1800BFAC2
0x1800bfa9a  mov     r14d, 800000h
0x1800bfaa0  test    [rcx+1Ch], r14d
0x1800bfaa4  jz      short loc_1800BFAC2
0x1800bfaa6  mov     rcx, [rcx+10h]
0x1800bfaaa  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800bfab1  mov     edx, 2Ah ; '*'
0x1800bfab6  mov     [rsp+1D0h+grbit], edi
0x1800bfaba  mov     r9d, ebx
0x1800bfabd  call    WPP_SF_dD
0x1800bfac2  lea     rcx, DhcpGlobalReadWriteLock
0x1800bfac9  call    RwLockRelease
0x1800bface  mov     eax, ebx
0x1800bfad0  jmp     loc_1800C024E
0x1800bfad5  mov     rax, [rbp+60h+var_A8]
0x1800bfad9  add     rax, 48h ; 'H'
0x1800bfadd  jz      loc_1800C020B
0x1800bfae3  cmp     [rax], esi
0x1800bfae5  jz      loc_1800C020B
0x1800bfaeb  mov     rax, [rax+8]
0x1800bfaef  mov     rcx, [rax]
0x1800bfaf2  mov     eax, [rcx]
0x1800bfaf4  mov     [rbp+60h+var_80], eax
0x1800bfaf7  mov     eax, [rcx+4]
0x1800bfafa  lea     rcx, DhcpGlobalReadWriteLock
0x1800bfb01  mov     [rbp+60h+pvData], eax
0x1800bfb04  call    RwLockRelease
0x1800bfb09  mov     rcx, cs:gDhcpHeap; hHeap
0x1800bfb10  mov     ebx, 8
0x1800bfb15  mov     edx, ebx; dwFlags
0x1800bfb17  lea     r8d, [rbx+8]; dwBytes
0x1800bfb1b  call    cs:__imp_HeapAlloc
0x1800bfb22  nop     dword ptr [rax+rax+00h]
0x1800bfb27  mov     rdi, rax
0x1800bfb2a  test    rax, rax
0x1800bfb2d  jz      short loc_1800BFACE
0x1800bfb2f  cmp     [r12], esi
0x1800bfb33  lea     rax, [rbp+60h+var_80]
0x1800bfb37  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800bfb3e  cmovnz  rax, r12
0x1800bfb42  mov     [rdi], rax
0x1800bfb45  mov     dword ptr [rdi+8], 4
0x1800bfb4c  mov     [rdi+0Ch], r14d
0x1800bfb50  call    cs:__imp_EnterCriticalSection
0x1800bfb57  nop     dword ptr [rax+rax+00h]
0x1800bfb5c  mov     r8, cs:DhcpGlobalClientTable
0x1800bfb63  xor     r9d, r9d
0x1800bfb66  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800bfb6d  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800bfb74  mov     [rsp+1D0h+var_1A0], ebx; JET_GRBIT
0x1800bfb78  mov     r8, [r8]
0x1800bfb7b  mov     [rsp+1D0h+var_1A8], r14d; int
0x1800bfb80  mov     qword ptr [rsp+1D0h+grbit], rdi; __int64
0x1800bfb85  call    DhcpDALJetPrepareSearchEx
0x1800bfb8a  mov     rcx, cs:gDhcpHeap; hHeap
0x1800bfb91  mov     r8, rdi; lpMem
0x1800bfb94  xor     edx, edx; dwFlags
0x1800bfb96  mov     ebx, eax
0x1800bfb98  call    cs:__imp_HeapFree
0x1800bfb9f  nop     dword ptr [rax+rax+00h]
0x1800bfba4  test    ebx, ebx
0x1800bfba6  jnz     loc_1800C01CF
0x1800bfbac  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800bfbb3  lea     r9d, [rbx+4]; cbData
0x1800bfbb7  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800bfbbe  lea     r8, [rbp+60h+pvData]; pvData
0x1800bfbc2  mov     [rsp+1D0h+grbit], r14d; grbit
0x1800bfbc7  call    cs:__imp_JetMakeKey
0x1800bfbce  nop     dword ptr [rax+rax+00h]
0x1800bfbd3  mov     ecx, eax
0x1800bfbd5  lea     rdx, aDhcpbndgetpend; "DhcpBNDGetPendingBndUpdates"
0x1800bfbdc  call    DhcpDALMapJetError
0x1800bfbe1  mov     ebx, eax
0x1800bfbe3  test    eax, eax
0x1800bfbe5  jnz     loc_1800C01CF
0x1800bfbeb  mov     rdx, cs:DhcpGlobalClientTableHandle; tableidSrc
0x1800bfbf2  lea     r8d, [rax+3]; grbit
0x1800bfbf6  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800bfbfd  call    cs:__imp_JetSetIndexRange
0x1800bfc04  nop     dword ptr [rax+rax+00h]
0x1800bfc09  mov     ecx, eax
0x1800bfc0b  lea     rdx, aDhcpbndgetpend; "DhcpBNDGetPendingBndUpdates"
0x1800bfc12  call    DhcpDALMapJetError
0x1800bfc17  mov     ebx, eax
0x1800bfc19  test    eax, eax
0x1800bfc1b  jnz     loc_1800C01CF
0x1800bfc21  lea     rsi, WPP_GLOBAL_Control
0x1800bfc28  mov     r14d, 800000h
0x1800bfc2e  mov     r8, cs:DhcpGlobalClientTable
0x1800bfc35  lea     rax, [rbp+60h+var_CC]
0x1800bfc39  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800bfc40  lea     r9, [rbp+60h+var_CC+4]
0x1800bfc44  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800bfc4b  mov     dword ptr [rbp+60h+var_CC], 4
0x1800bfc52  mov     r8d, [r8+148h]; columnid
0x1800bfc59  mov     qword ptr [rsp+1D0h+grbit], rax; __int64
0x1800bfc5e  call    DhcpDALJetGetValue
0x1800bfc63  mov     ebx, eax
0x1800bfc65  test    eax, eax
0x1800bfc67  jnz     loc_1800C01CF
0x1800bfc6d  mov     eax, dword ptr [rbp+60h+var_CC+4]
0x1800bfc70  test    eax, eax
0x1800bfc72  jnz     short loc_1800BFC8E
0x1800bfc74  mov     rdx, cs:DhcpGlobalClientTableHandle
0x1800bfc7b  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bfc82  call    DhcpDALJetNextRecord
0x1800bfc87  mov     edi, eax
0x1800bfc89  jmp     loc_1800C0119
0x1800bfc8e  mov     ebx, 1
0x1800bfc93  cmp     eax, ebx
0x1800bfc95  jbe     loc_1800BFDDB
0x1800bfc9b  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bfca2  call    DhcpDALJetBeginTransaction
0x1800bfca7  test    eax, eax
0x1800bfca9  jz      short loc_1800BFCE0
0x1800bfcab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfcb2  cmp     rcx, rsi
0x1800bfcb5  jz      loc_1800BFDDB
0x1800bfcbb  test    [rcx+1Ch], r14d
0x1800bfcbf  jz      loc_1800BFDDB
0x1800bfcc5  mov     rcx, [rcx+10h]
0x1800bfcc9  lea     edx, [rbx+2Bh]
0x1800bfccc  mov     r9d, eax
0x1800bfccf  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800bfcd6  call    WPP_SF_D
0x1800bfcdb  jmp     loc_1800BFDDB
0x1800bfce0  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800bfce7  mov     r8d, 2; prep
0x1800bfced  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800bfcf4  call    cs:__imp_JetPrepareUpdate
0x1800bfcfb  nop     dword ptr [rax+rax+00h]
0x1800bfd00  mov     ecx, eax
0x1800bfd02  lea     rdx, aDhcpdaljetprep_4; "DhcpDALJetPrepareUpdate"
0x1800bfd09  call    DhcpDALMapJetError
0x1800bfd0e  test    eax, eax
0x1800bfd10  jz      short loc_1800BFD33
0x1800bfd12  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfd19  cmp     rcx, rsi
0x1800bfd1c  jz      loc_1800BFDC1
0x1800bfd22  test    [rcx+1Ch], r14d
0x1800bfd26  jz      loc_1800BFDC1
0x1800bfd2c  mov     edx, 2Dh ; '-'
0x1800bfd31  jmp     short loc_1800BFDAE
0x1800bfd33  mov     r8, cs:DhcpGlobalClientTable
0x1800bfd3a  lea     r9, [rbp+60h+var_C4]
0x1800bfd3e  mov     rdx, cs:DhcpGlobalClientTableHandle
0x1800bfd45  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bfd4c  mov     [rbp+60h+var_C4], ebx
0x1800bfd4f  mov     r8d, [r8+148h]
0x1800bfd56  mov     [rsp+1D0h+grbit], 4
0x1800bfd5e  call    DhcpDALJetSetValue
0x1800bfd63  test    eax, eax
0x1800bfd65  jz      short loc_1800BFD80
0x1800bfd67  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfd6e  cmp     rcx, rsi
0x1800bfd71  jz      short loc_1800BFDC1
0x1800bfd73  test    [rcx+1Ch], r14d
0x1800bfd77  jz      short loc_1800BFDC1
0x1800bfd79  mov     edx, 2Eh ; '.'
0x1800bfd7e  jmp     short loc_1800BFDAE
0x1800bfd80  mov     rdx, cs:DhcpGlobalClientTableHandle
0x1800bfd87  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bfd8e  call    DhcpDALJetCommitUpdate
0x1800bfd93  test    eax, eax
0x1800bfd95  jz      short loc_1800BFDCF
0x1800bfd97  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bfd9e  cmp     rcx, rsi
0x1800bfda1  jz      short loc_1800BFDC1
0x1800bfda3  test    [rcx+1Ch], r14d
0x1800bfda7  jz      short loc_1800BFDC1
0x1800bfda9  mov     edx, 2Fh ; '/'
0x1800bfdae  mov     rcx, [rcx+10h]
0x1800bfdb2  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800bfdb9  mov     r9d, eax
0x1800bfdbc  call    WPP_SF_D
0x1800bfdc1  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bfdc8  call    DhcpDALJetRollback
0x1800bfdcd  jmp     short loc_1800BFDDB
0x1800bfdcf  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bfdd6  call    DhcpDALJetCommitTransaction
0x1800bfddb  xor     r9d, r9d
0x1800bfdde  mov     [rsp+1D0h+grbit], ebx
0x1800bfde2  xor     r8d, r8d
0x1800bfde5  lea     rcx, [rbp+60h+hMem]
0x1800bfde9  xor     edx, edx
0x1800bfdeb  call    DhcpGetCurrentFailoverClientInfo
0x1800bfdf0  mov     ebx, eax
0x1800bfdf2  test    eax, eax
0x1800bfdf4  jnz     loc_1800C01B4
0x1800bfdfa  mov     rdi, [rbp+60h+hMem]
0x1800bfdfe  xor     ebx, ebx
0x1800bfe00  lea     rcx, [rdi+28h]
0x1800bfe04  cmp     [rcx], ebx
0x1800bfe06  jnz     short loc_1800BFE11
0x1800bfe08  cmp     [rdi+2Ch], ebx
0x1800bfe0b  jz      loc_1800C00D1
0x1800bfe11  cmp     dword ptr [rcx], 0FFFFFFFFh
0x1800bfe14  jnz     short loc_1800BFE1F
0x1800bfe16  cmp     dword ptr [rdi+2Ch], 7FFFFFFFh
0x1800bfe1d  jz      short loc_1800BFE36
0x1800bfe1f  call    DhcpCalculateUTCTime
0x1800bfe24  mov     rcx, [rbp+60h+hMem]
0x1800bfe28  mov     [rcx+28h], eax
0x1800bfe2b  mov     rax, [rbp+60h+hMem]
0x1800bfe2f  mov     [rax+2Ch], ebx
0x1800bfe32  mov     rdi, [rbp+60h+hMem]
0x1800bfe36  lea     rdx, [rbp+60h+var_C0]
0x1800bfe3a  mov     rcx, rdi
0x1800bfe3d  call    DhcpBNDGetMessageSize
0x1800bfe42  mov     eax, cs:gFailoverMaxBndRecordsperPacket
0x1800bfe48  cmp     [r13+0], eax
0x1800bfe4c  jnb     loc_1800C018F
0x1800bfe52  mov     eax, [rbp+60h+arg_20]
0x1800bfe58  sub     eax, r15d
0x1800bfe5b  mov     [rbp+60h+var_A0], eax
0x1800bfe5e  cmp     eax, [rbp+60h+var_C0]
0x1800bfe61  jb      loc_1800C018F
0x1800bfe67  mov     r8b, [rdi+80h]
0x1800bfe6e  mov     ecx, ebx
  ... truncated ...
```
