# DhcpBNDGetPendingBndUpdates

- ea: `0x1800be94c`
- end: `0x1800bf251`
- name: `DhcpBNDGetPendingBndUpdates`
- size: `2309`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c227c`

## callees

- `0x180002854`
- `0x1800057f4`
- `0x180007be4`
- `0x18001ceb4`
- `0x1800251e4`
- `0x180025424`
- `0x18008eea8`
- `0x180092f64`
- `0x1800930bc`
- `0x18009f738`
- `0x18009f760`
- `0x18009f790`
- `0x18009f8f4`
- `0x18009fa94`
- `0x18009fc30`
- `0x18009fe78`
- `0x18009fea4`
- `0x18009fee0`
- `0x1800be840`
- `0x1800be94c`
- `0x1800c56b0`
- `0x1800c9058`
- `0x1800c9a6c`
- `0x1800cc99a`

## import_xrefs

- `ESENT!JetSetIndexRange` at `0x1800bebe5`
- `ESENT!JetSetIndexRange` at `0x1800bebe5`
- `ESENT!JetMakeKey` at `0x1800bebaf`
- `ESENT!JetMakeKey` at `0x1800bebaf`
- `ESENT!JetPrepareUpdate` at `0x1800becdc`
- `ESENT!JetPrepareUpdate` at `0x1800becdc`
- `KERNEL32!HeapAlloc` at `0x1800beb03`
- `KERNEL32!HeapAlloc` at `0x1800beb03`
- `KERNEL32!LocalFree` at `0x1800bf0ef`
- `KERNEL32!LocalFree` at `0x1800bf1e1`
- `KERNEL32!LocalFree` at `0x1800bf0ef`
- `KERNEL32!LocalFree` at `0x1800bf1e1`
- `KERNEL32!EnterCriticalSection` at `0x1800beb38`
- `KERNEL32!EnterCriticalSection` at `0x1800beb38`
- `KERNEL32!LeaveCriticalSection` at `0x1800bf1bd`
- `KERNEL32!LeaveCriticalSection` at `0x1800bf1bd`
- `KERNEL32!HeapFree` at `0x1800beb80`
- `KERNEL32!HeapFree` at `0x1800beb80`

## string_xrefs

- `0x1800becea`: `DhcpDALJetPrepareUpdate`
- `0x1800bebbd`: `DhcpBNDGetPendingBndUpdates`
- `0x1800bebf3`: `DhcpBNDGetPendingBndUpdates`
- `0x1800bf1a8`: `DhcpBNDGetPendingBndUpdates`

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
  __int64 v43; // r13
  __int64 v44; // rax
  __int64 v45; // r12
  __int64 v46; // r15
  unsigned int v47; // eax
  __int64 v48; // r9
  char v49; // cl
  HLOCAL v50; // rbx
  HLOCAL v51; // rdi
  int v52; // [rsp+50h] [rbp-128h]
  int v53; // [rsp+58h] [rbp-120h]
  bool v54[8]; // [rsp+F8h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+100h] [rbp-78h] BYREF
  int v56; // [rsp+108h] [rbp-70h]
  __int64 v57; // [rsp+10Ch] [rbp-6Ch] BYREF
  int v58; // [rsp+114h] [rbp-64h] BYREF
  unsigned int v59; // [rsp+118h] [rbp-60h] BYREF
  int v60; // [rsp+11Ch] [rbp-5Ch]
  int v61; // [rsp+120h] [rbp-58h]
  int v62; // [rsp+124h] [rbp-54h]
  int v63; // [rsp+128h] [rbp-50h]
  int v64; // [rsp+12Ch] [rbp-4Ch] BYREF
  __int64 v65; // [rsp+130h] [rbp-48h] BYREF
  int v66; // [rsp+138h] [rbp-40h]
  __int64 v67; // [rsp+140h] [rbp-38h]
  int v68; // [rsp+158h] [rbp-20h] BYREF
  _DWORD pvData[31]; // [rsp+15Ch] [rbp-1Ch] BYREF

  v8 = a3;
  v65 = 0;
  v58 = 0;
  memset_0(&v68, 0, 0x50u);
  hMem = 0;
  v64 = 0;
  v57 = 0x100000000LL;
  *a8 = 0;
  v59 = 0;
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
  v56 = 0;
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
      v51 = hMem;
      if ( hMem )
      {
        fgs__DHCP_CLIENT_INFO_FO_EX(hMem);
        LocalFree(v51);
      }
      return Value;
    }
    while ( 1 )
    {
      LODWORD(v57) = 4;
      Value = DhcpDALJetGetValue(
                DhcpGlobalJetServerSession,
                DhcpGlobalClientTableHandle,
                *(_DWORD *)(DhcpGlobalClientTable + 328),
                (__int64)&v57);
      if ( Value )
        goto LABEL_106;
      if ( HIDWORD(v57) )
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
    if ( HIDWORD(v57) <= 1 )
    {
LABEL_49:
      CurrentFailoverClientInfo = DhcpGetCurrentFailoverClientInfo(&hMem, 0, 0, 0, 1);
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
        v50 = hMem;
        if ( hMem )
        {
          fgs__DHCP_CLIENT_INFO_FO_EX(hMem);
          LocalFree(v50);
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
      DhcpBNDGetMessageSize(v28, &v59);
      if ( *v11 >= *(_DWORD *)&gFailoverMaxBndRecordsperPacket || (v66 = a5 - v12, a5 - v12 < v59) )
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
      v54[0] = !v35;
      if ( v37 )
      {
        v38 = -1;
        do
          ++v38;
        while ( *(_WORD *)(v37 + 2 * v38) );
        v60 = 2 * v38 + 2;
      }
      else
      {
        v60 = 0;
      }
      v39 = *((_QWORD *)v28 + 7);
      if ( v39 )
      {
        v40 = -1;
        do
          ++v40;
        while ( *(_WORD *)(v39 + 2 * v40) );
        v61 = 2 * v40 + 2;
      }
      else
      {
        v61 = 0;
      }
      v41 = *((_QWORD *)v28 + 4);
      if ( v41 )
      {
        v42 = -1;
        do
          ++v42;
        while ( *(_WORD *)(v41 + 2 * v42) );
        v62 = 2 * v42 + 2;
      }
      else
      {
        v62 = 0;
      }
      v43 = *((_QWORD *)v28 + 3);
      if ( v43 )
      {
        v44 = -1;
        do
          ++v44;
        while ( *(_WORD *)(v43 + 2 * v44) );
        v63 = 2 * v44 + 2;
      }
      else
      {
        v63 = 0;
      }
      if ( (unsigned int)(v36 - 1) <= 2 && ((v29 = (__int64)(v28 + 54), v36 == 1) || v36 == 3) )
      {
        v45 = (__int64)(v28 + 46);
        if ( v36 == 1 )
          goto LABEL_84;
      }
      else
      {
        v45 = 0;
      }
      if ( (unsigned int)(v36 - 2) > 2 )
      {
        v46 = 0;
LABEL_85:
        v47 = MFFormatBndUpdRecord(
                (_DWORD)v28,
                (int)v28 + 128,
                (int)v28 + 73,
                v28[4],
                *((_QWORD *)v28 + 2),
                v46,
                v45,
                (__int64)(v28 + 52),
                v29,
                v52,
                v53,
                v63,
                v43,
                v62,
                *((_QWORD *)v28 + 4),
                (__int64)(v28 + 2),
                (__int64)(v28 + 24),
                v61,
                *((_QWORD *)v28 + 7),
                (__int64)(v28 + 36),
                (__int64)(v28 + 38),
                (__int64)(v28 + 40),
                (__int64)v54,
                v60,
                *((_QWORD *)v28 + 15),
                v67,
                v66,
                (__int64)&v64,
                (__int64)(v28 + 66));
        Value = 0;
        if ( v47 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
          {
            WPP_SF_dD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              48,
              &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids,
              v47,
              *(_DWORD *)hMem);
          }
          *a3 = *(_DWORD *)hMem;
          *a6 = v56;
          goto LABEL_106;
        }
        v11 = a7;
        v48 = (unsigned int)*a7;
        if ( (unsigned int)v48 < *(_DWORD *)&gFailoverMaxBndRecordsperPacket )
        {
          *(_DWORD *)(*(_QWORD *)(a1 + 16) + 152 * v48 + 56) = *(_DWORD *)hMem;
          v49 = v65;
          if ( *((_BYTE *)hMem + 73) == 4 )
            v49 = 7;
          *(_BYTE *)(152 * v48 + *(_QWORD *)(a1 + 16) + 61) = v49;
          ++*(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
        }
        v12 = v64 + v56;
        v8 = a3;
        v67 = a4 + (unsigned int)(v64 + v56);
        *a7 = v48 + 1;
        v56 = v12;
        goto LABEL_91;
      }
LABEL_84:
      v46 = (__int64)(v28 + 20);
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
      v58 = 1;
      v24 = DhcpDALJetSetValue(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableHandle,
              *(_DWORD *)(DhcpGlobalClientTable + 328),
              (unsigned int)&v58,
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
0x1800be94c  mov     rax, rsp
0x1800be94f  mov     [rax+10h], rbx
0x1800be953  mov     [rax+20h], r9
0x1800be957  mov     [rax+18h], r8
0x1800be95b  mov     [rax+8], rcx
0x1800be95f  push    rbp
0x1800be960  push    rsi
0x1800be961  push    rdi
0x1800be962  push    r12
0x1800be964  push    r13
0x1800be966  push    r14
0x1800be968  push    r15
0x1800be96a  lea     rbp, [rax-68h]
0x1800be96e  sub     rsp, 1A0h
0x1800be975  xor     esi, esi
0x1800be977  lea     rcx, [rbp+60h+var_80]; void *
0x1800be97b  mov     r12, r8
0x1800be97e  mov     [rbp+60h+var_A8], rsi
0x1800be982  mov     edi, edx
0x1800be984  mov     [rbp+60h+var_C4], esi
0x1800be987  xor     edx, edx; Val
0x1800be989  mov     rbx, r9
0x1800be98c  lea     r14d, [rsi+1]
0x1800be990  lea     r8d, [rsi+50h]; Size
0x1800be994  mov     dword ptr [rbp+60h+var_CC+4], r14d
0x1800be998  call    memset_0
0x1800be99d  mov     rax, [rbp+60h+arg_38]
0x1800be9a4  mov     [rbp+60h+hMem], rsi
0x1800be9a8  mov     [rbp+60h+var_AC], esi
0x1800be9ab  mov     dword ptr [rbp+60h+var_CC], esi
0x1800be9ae  mov     [rax], esi
0x1800be9b0  mov     rax, [rbp+60h+arg_28]
0x1800be9b7  mov     [rbp+60h+var_C0], esi
0x1800be9ba  mov     [rax], esi
0x1800be9bc  test    rbx, rbx
0x1800be9bf  jz      loc_1800BF230
0x1800be9c5  test    r12, r12
0x1800be9c8  jz      loc_1800BF230
0x1800be9ce  mov     r13, [rbp+60h+arg_30]
0x1800be9d5  test    r13, r13
0x1800be9d8  jz      loc_1800BF230
0x1800be9de  lea     rcx, DhcpGlobalReadWriteLock
0x1800be9e5  mov     [rbp+60h+var_98], rbx
0x1800be9e9  mov     r15d, esi
0x1800be9ec  mov     [rbp+60h+var_D0], esi
0x1800be9ef  call    RwLockAcquireForRead
0x1800be9f4  mov     rcx, cs:DhcpGlobalThisServer
0x1800be9fb  lea     r8, [rbp+60h+var_A8]
0x1800be9ff  mov     eax, edi
0x1800bea01  mov     qword ptr [rsp+1D0h+var_1A8], rsi
0x1800bea06  and     eax, 0F0000000h
0x1800bea0b  mov     qword ptr [rsp+1D0h+grbit], rsi
0x1800bea10  xor     r9d, r9d
0x1800bea13  mov     edx, edi
0x1800bea15  cmp     eax, 0E0000000h
0x1800bea1a  jnz     short loc_1800BEA23
0x1800bea1c  call    MemServerGetMAddressInfo
0x1800bea21  jmp     short loc_1800BEA28
0x1800bea23  call    MemServerGetUAddressInfo
0x1800bea28  mov     ebx, eax
0x1800bea2a  cmp     eax, 2
0x1800bea2d  jnz     short loc_1800BEA6B
0x1800bea2f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bea36  lea     rsi, WPP_GLOBAL_Control
0x1800bea3d  cmp     rcx, rsi
0x1800bea40  jz      short loc_1800BEA64
0x1800bea42  mov     r14d, 800000h
0x1800bea48  test    [rcx+1Ch], r14d
0x1800bea4c  jz      short loc_1800BEA64
0x1800bea4e  mov     rcx, [rcx+10h]
0x1800bea52  lea     edx, [rax+27h]
0x1800bea55  mov     r9d, edi
0x1800bea58  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800bea5f  call    WPP_SF_D
0x1800bea64  mov     ebx, 4E25h
0x1800bea69  jmp     short loc_1800BEAAA
0x1800bea6b  test    ebx, ebx
0x1800bea6d  jz      short loc_1800BEABD
0x1800bea6f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bea76  lea     rsi, WPP_GLOBAL_Control
0x1800bea7d  cmp     rcx, rsi
0x1800bea80  jz      short loc_1800BEAAA
0x1800bea82  mov     r14d, 800000h
0x1800bea88  test    [rcx+1Ch], r14d
0x1800bea8c  jz      short loc_1800BEAAA
0x1800bea8e  mov     rcx, [rcx+10h]
0x1800bea92  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800bea99  mov     edx, 2Ah ; '*'
0x1800bea9e  mov     [rsp+1D0h+grbit], edi
0x1800beaa2  mov     r9d, ebx
0x1800beaa5  call    WPP_SF_dD
0x1800beaaa  lea     rcx, DhcpGlobalReadWriteLock
0x1800beab1  call    RwLockRelease
0x1800beab6  mov     eax, ebx
0x1800beab8  jmp     loc_1800BF235
0x1800beabd  mov     rax, [rbp+60h+var_A8]
0x1800beac1  add     rax, 48h ; 'H'
0x1800beac5  jz      loc_1800BF1F2
0x1800beacb  cmp     [rax], esi
0x1800beacd  jz      loc_1800BF1F2
0x1800bead3  mov     rax, [rax+8]
0x1800bead7  mov     rcx, [rax]
0x1800beada  mov     eax, [rcx]
0x1800beadc  mov     [rbp+60h+var_80], eax
0x1800beadf  mov     eax, [rcx+4]
0x1800beae2  lea     rcx, DhcpGlobalReadWriteLock
0x1800beae9  mov     [rbp+60h+pvData], eax
0x1800beaec  call    RwLockRelease
0x1800beaf1  mov     rcx, cs:gDhcpHeap; hHeap
0x1800beaf8  mov     ebx, 8
0x1800beafd  mov     edx, ebx; dwFlags
0x1800beaff  lea     r8d, [rbx+8]; dwBytes
0x1800beb03  call    cs:__imp_HeapAlloc
0x1800beb0a  nop     dword ptr [rax+rax+00h]
0x1800beb0f  mov     rdi, rax
0x1800beb12  test    rax, rax
0x1800beb15  jz      short loc_1800BEAB6
0x1800beb17  cmp     [r12], esi
0x1800beb1b  lea     rax, [rbp+60h+var_80]
0x1800beb1f  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800beb26  cmovnz  rax, r12
0x1800beb2a  mov     [rdi], rax
0x1800beb2d  mov     dword ptr [rdi+8], 4
0x1800beb34  mov     [rdi+0Ch], r14d
0x1800beb38  call    cs:__imp_EnterCriticalSection
0x1800beb3f  nop     dword ptr [rax+rax+00h]
0x1800beb44  mov     rax, cs:DhcpGlobalClientTable
0x1800beb4b  xor     r9d, r9d
0x1800beb4e  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800beb55  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800beb5c  mov     [rsp+1D0h+var_1A0], ebx; JET_GRBIT
0x1800beb60  mov     r8, [rax]
0x1800beb63  mov     [rsp+1D0h+var_1A8], r14d; int
0x1800beb68  mov     qword ptr [rsp+1D0h+grbit], rdi; __int64
0x1800beb6d  call    DhcpDALJetPrepareSearchEx
0x1800beb72  mov     rcx, cs:gDhcpHeap; hHeap
0x1800beb79  mov     r8, rdi; lpMem
0x1800beb7c  xor     edx, edx; dwFlags
0x1800beb7e  mov     ebx, eax
0x1800beb80  call    cs:__imp_HeapFree
0x1800beb87  nop     dword ptr [rax+rax+00h]
0x1800beb8c  test    ebx, ebx
0x1800beb8e  jnz     loc_1800BF1B6
0x1800beb94  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800beb9b  lea     r9d, [rbx+4]; cbData
0x1800beb9f  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800beba6  lea     r8, [rbp+60h+pvData]; pvData
0x1800bebaa  mov     [rsp+1D0h+grbit], r14d; grbit
0x1800bebaf  call    cs:__imp_JetMakeKey
0x1800bebb6  nop     dword ptr [rax+rax+00h]
0x1800bebbb  mov     ecx, eax
0x1800bebbd  lea     rdx, aDhcpbndgetpend; "DhcpBNDGetPendingBndUpdates"
0x1800bebc4  call    DhcpDALMapJetError
0x1800bebc9  mov     ebx, eax
0x1800bebcb  test    eax, eax
0x1800bebcd  jnz     loc_1800BF1B6
0x1800bebd3  mov     rdx, cs:DhcpGlobalClientTableHandle; tableidSrc
0x1800bebda  lea     r8d, [rax+3]; grbit
0x1800bebde  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800bebe5  call    cs:__imp_JetSetIndexRange
0x1800bebec  nop     dword ptr [rax+rax+00h]
0x1800bebf1  mov     ecx, eax
0x1800bebf3  lea     rdx, aDhcpbndgetpend; "DhcpBNDGetPendingBndUpdates"
0x1800bebfa  call    DhcpDALMapJetError
0x1800bebff  mov     ebx, eax
0x1800bec01  test    eax, eax
0x1800bec03  jnz     loc_1800BF1B6
0x1800bec09  lea     rsi, WPP_GLOBAL_Control
0x1800bec10  mov     r14d, 800000h
0x1800bec16  mov     r8, cs:DhcpGlobalClientTable
0x1800bec1d  lea     rax, [rbp+60h+var_CC]
0x1800bec21  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800bec28  lea     r9, [rbp+60h+var_CC+4]
0x1800bec2c  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800bec33  mov     dword ptr [rbp+60h+var_CC], 4
0x1800bec3a  mov     r8d, [r8+148h]; columnid
0x1800bec41  mov     qword ptr [rsp+1D0h+grbit], rax; __int64
0x1800bec46  call    DhcpDALJetGetValue
0x1800bec4b  mov     ebx, eax
0x1800bec4d  test    eax, eax
0x1800bec4f  jnz     loc_1800BF1B6
0x1800bec55  mov     eax, dword ptr [rbp+60h+var_CC+4]
0x1800bec58  test    eax, eax
0x1800bec5a  jnz     short loc_1800BEC76
0x1800bec5c  mov     rdx, cs:DhcpGlobalClientTableHandle
0x1800bec63  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bec6a  call    DhcpDALJetNextRecord
0x1800bec6f  mov     edi, eax
0x1800bec71  jmp     loc_1800BF100
0x1800bec76  mov     ebx, 1
0x1800bec7b  cmp     eax, ebx
0x1800bec7d  jbe     loc_1800BEDC3
0x1800bec83  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bec8a  call    DhcpDALJetBeginTransaction
0x1800bec8f  test    eax, eax
0x1800bec91  jz      short loc_1800BECC8
0x1800bec93  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bec9a  cmp     rcx, rsi
0x1800bec9d  jz      loc_1800BEDC3
0x1800beca3  test    [rcx+1Ch], r14d
0x1800beca7  jz      loc_1800BEDC3
0x1800becad  mov     rcx, [rcx+10h]
0x1800becb1  lea     edx, [rbx+2Bh]
0x1800becb4  mov     r9d, eax
0x1800becb7  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800becbe  call    WPP_SF_D
0x1800becc3  jmp     loc_1800BEDC3
0x1800becc8  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800beccf  mov     r8d, 2; prep
0x1800becd5  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800becdc  call    cs:__imp_JetPrepareUpdate
0x1800bece3  nop     dword ptr [rax+rax+00h]
0x1800bece8  mov     ecx, eax
0x1800becea  lea     rdx, aDhcpdaljetprep_4; "DhcpDALJetPrepareUpdate"
0x1800becf1  call    DhcpDALMapJetError
0x1800becf6  test    eax, eax
0x1800becf8  jz      short loc_1800BED1B
0x1800becfa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bed01  cmp     rcx, rsi
0x1800bed04  jz      loc_1800BEDA9
0x1800bed0a  test    [rcx+1Ch], r14d
0x1800bed0e  jz      loc_1800BEDA9
0x1800bed14  mov     edx, 2Dh ; '-'
0x1800bed19  jmp     short loc_1800BED96
0x1800bed1b  mov     r8, cs:DhcpGlobalClientTable
0x1800bed22  lea     r9, [rbp+60h+var_C4]
0x1800bed26  mov     rdx, cs:DhcpGlobalClientTableHandle
0x1800bed2d  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bed34  mov     [rbp+60h+var_C4], ebx
0x1800bed37  mov     r8d, [r8+148h]
0x1800bed3e  mov     [rsp+1D0h+grbit], 4
0x1800bed46  call    DhcpDALJetSetValue
0x1800bed4b  test    eax, eax
0x1800bed4d  jz      short loc_1800BED68
0x1800bed4f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bed56  cmp     rcx, rsi
0x1800bed59  jz      short loc_1800BEDA9
0x1800bed5b  test    [rcx+1Ch], r14d
0x1800bed5f  jz      short loc_1800BEDA9
0x1800bed61  mov     edx, 2Eh ; '.'
0x1800bed66  jmp     short loc_1800BED96
0x1800bed68  mov     rdx, cs:DhcpGlobalClientTableHandle
0x1800bed6f  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bed76  call    DhcpDALJetCommitUpdate
0x1800bed7b  test    eax, eax
0x1800bed7d  jz      short loc_1800BEDB7
0x1800bed7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bed86  cmp     rcx, rsi
0x1800bed89  jz      short loc_1800BEDA9
0x1800bed8b  test    [rcx+1Ch], r14d
0x1800bed8f  jz      short loc_1800BEDA9
0x1800bed91  mov     edx, 2Fh ; '/'
0x1800bed96  mov     rcx, [rcx+10h]
0x1800bed9a  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800beda1  mov     r9d, eax
0x1800beda4  call    WPP_SF_D
0x1800beda9  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bedb0  call    DhcpDALJetRollback
0x1800bedb5  jmp     short loc_1800BEDC3
0x1800bedb7  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800bedbe  call    DhcpDALJetCommitTransaction
0x1800bedc3  xor     r9d, r9d
0x1800bedc6  mov     [rsp+1D0h+grbit], ebx
0x1800bedca  xor     r8d, r8d
0x1800bedcd  lea     rcx, [rbp+60h+hMem]
0x1800bedd1  xor     edx, edx
0x1800bedd3  call    DhcpGetCurrentFailoverClientInfo
0x1800bedd8  mov     ebx, eax
0x1800bedda  test    eax, eax
0x1800beddc  jnz     loc_1800BF19B
0x1800bede2  mov     rdi, [rbp+60h+hMem]
0x1800bede6  xor     ebx, ebx
0x1800bede8  lea     rcx, [rdi+28h]
0x1800bedec  cmp     [rcx], ebx
0x1800bedee  jnz     short loc_1800BEDF9
0x1800bedf0  cmp     [rdi+2Ch], ebx
0x1800bedf3  jz      loc_1800BF0BB
0x1800bedf9  cmp     dword ptr [rcx], 0FFFFFFFFh
0x1800bedfc  jnz     short loc_1800BEE07
0x1800bedfe  cmp     dword ptr [rdi+2Ch], 7FFFFFFFh
0x1800bee05  jz      short loc_1800BEE1E
0x1800bee07  call    DhcpCalculateUTCTime
0x1800bee0c  mov     rcx, [rbp+60h+hMem]
0x1800bee10  mov     [rcx+28h], eax
0x1800bee13  mov     rax, [rbp+60h+hMem]
0x1800bee17  mov     [rax+2Ch], ebx
0x1800bee1a  mov     rdi, [rbp+60h+hMem]
0x1800bee1e  lea     rdx, [rbp+60h+var_C0]
0x1800bee22  mov     rcx, rdi
0x1800bee25  call    DhcpBNDGetMessageSize
0x1800bee2a  mov     eax, cs:gFailoverMaxBndRecordsperPacket
0x1800bee30  cmp     [r13+0], eax
0x1800bee34  jnb     loc_1800BF176
0x1800bee3a  mov     eax, [rbp+60h+arg_20]
0x1800bee40  sub     eax, r15d
0x1800bee43  mov     [rbp+60h+var_A0], eax
0x1800bee46  cmp     eax, [rbp+60h+var_C0]
0x1800bee49  jb      loc_1800BF176
0x1800bee4f  mov     r8b, [rdi+80h]
0x1800bee56  mov     ecx, ebx
  ... truncated ...
```
