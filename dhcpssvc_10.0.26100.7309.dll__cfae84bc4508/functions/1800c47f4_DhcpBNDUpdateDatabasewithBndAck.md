# DhcpBNDUpdateDatabasewithBndAck

- ea: `0x1800c47f4`
- end: `0x1800c4f71`
- name: `DhcpBNDUpdateDatabasewithBndAck`
- size: `1917`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c0a64`

## callees

- `0x180002854`
- `0x1800057f4`
- `0x1800251e4`
- `0x180025424`
- `0x18009877c`
- `0x18009f738`
- `0x18009f760`
- `0x18009f790`
- `0x18009f8f4`
- `0x18009fac4`
- `0x18009fe04`
- `0x18009fe78`
- `0x18009fea4`
- `0x18009fee0`
- `0x1800bdd88`
- `0x1800c47f4`
- `0x1800c56b0`
- `0x1800c5fa4`
- `0x1800cd010`

## import_xrefs

- `ESENT!JetDelete` at `0x1800c4974`
- `ESENT!JetDelete` at `0x1800c4974`
- `KERNEL32!EnterCriticalSection` at `0x1800c488f`
- `KERNEL32!EnterCriticalSection` at `0x1800c49c3`
- `KERNEL32!EnterCriticalSection` at `0x1800c4bed`
- `KERNEL32!EnterCriticalSection` at `0x1800c488f`
- `KERNEL32!EnterCriticalSection` at `0x1800c49c3`
- `KERNEL32!EnterCriticalSection` at `0x1800c4bed`
- `KERNEL32!LeaveCriticalSection` at `0x1800c48e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800c4b27`
- `KERNEL32!LeaveCriticalSection` at `0x1800c48e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800c4b27`

## string_xrefs

- `0x1800c4907`: `DeletedIPAddress`
- `0x1800c4982`: `DhcpDALJetDeleteCurrentRecord`

## pseudocode

```c
__int64 __fastcall DhcpBNDUpdateDatabasewithBndAck(unsigned int *a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v4; // r13
  unsigned int v6; // esi
  _BYTE *v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  unsigned __int8 v10; // dl
  char v11; // r8
  int v12; // edi
  unsigned int Value; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // eax
  char v19; // al
  __int64 v20; // rdx
  unsigned int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  unsigned __int8 *v24; // rax
  unsigned __int8 *v25; // rax
  unsigned __int8 v26; // cl
  _BYTE *v27; // rax
  __int64 v29; // [rsp+30h] [rbp-20h] BYREF
  unsigned int *v30; // [rsp+38h] [rbp-18h]
  int v31; // [rsp+40h] [rbp-10h]
  int v32; // [rsp+44h] [rbp-Ch]
  int v33; // [rsp+90h] [rbp+40h] BYREF
  int v34; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v35; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = a2;
  LODWORD(v35) = 0;
  v29 = 0;
  v6 = 0;
  v33 = 0;
  v34 = 0;
  if ( a1 && a2 )
  {
    v7 = (_BYTE *)(a2 + 12);
    if ( *(_QWORD *)(a2 + 24) || (v8 = 1, (*v7 & 4) != 0) )
      v8 = 0;
    LOBYTE(a3) = *v7;
    LOBYTE(a2) = *(_BYTE *)(a2 + 13);
    v9 = MapOldStateToNewState(v8, a2, a3);
    v12 = v9;
    if ( !v9 || v9 == 6 )
    {
      v25 = (unsigned __int8 *)*((_QWORD *)a1 + 1);
      v26 = v10;
      if ( v25
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, *a1, *v25);
        v26 = *(_BYTE *)(v4 + 13);
      }
      v27 = (_BYTE *)*((_QWORD *)a1 + 1);
      if ( v27 )
      {
        if ( *v27 == 22 )
          v34 = 1;
        if ( *v27 == 23 )
          v34 = 0;
        v3 = (unsigned __int8)*v27;
      }
      v20 = v26;
LABEL_95:
      ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, int *))gAAUpdateBitMask)(*a1, v20, 1, v3, &v34);
      return v6;
    }
    if ( (v11 & 4) != 0 )
    {
      v30 = a1;
      v31 = 4;
      v32 = 1;
      EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      Value = DhcpDALJetBeginTransaction(DhcpGlobalJetServerSession);
      v6 = Value;
      if ( Value )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_14;
        }
        v15 = 71;
        goto LABEL_13;
      }
      v6 = DhcpDALJetOpenKey(DhcpGlobalJetServerSession, DeletedAddressTableHandle, 1);
      if ( v6 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_82;
        }
        v17 = 72;
        goto LABEL_19;
      }
      v18 = JetDelete(DhcpGlobalJetServerSession, DeletedAddressTableHandle);
      v6 = DhcpDALMapJetError(v18, "DhcpDALJetDeleteCurrentRecord");
      if ( v6 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_82;
        }
        v17 = 73;
        goto LABEL_19;
      }
LABEL_83:
      DhcpDALJetCommitTransaction(DhcpGlobalJetServerSession);
      goto LABEL_14;
    }
    EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    v30 = a1;
    v31 = 4;
    v32 = 1;
    v6 = DhcpDALJetOpenKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 1);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, v6, *a1);
      }
      goto LABEL_14;
    }
    LODWORD(v35) = 4;
    Value = DhcpDALJetGetValue(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableHandle,
              *(_DWORD *)(DhcpGlobalClientTable + 328),
              (__int64)&v35);
    v6 = Value;
    if ( Value )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_14;
      }
      v15 = 75;
      goto LABEL_13;
    }
    LODWORD(v29) = 4;
    Value = DhcpDALJetGetValue(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableHandle,
              *(_DWORD *)(DhcpGlobalClientTable + 312),
              (__int64)&v29);
    v6 = Value;
    if ( Value )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_14;
      }
      v15 = 76;
      goto LABEL_13;
    }
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    if ( !v33 )
      return 0;
    v19 = *(_BYTE *)(v4 + 12);
    if ( (v19 & 1) != 0 )
    {
      if ( (v29 & 0x100000000LL) == 0 )
        return v6;
      v6 = DeleteFailoverClientInfo(*a1);
      if ( v6 )
        return v6;
      v20 = 3;
      LOBYTE(v3) = *((_QWORD *)a1 + 1) != 0;
      goto LABEL_95;
    }
    if ( (v19 & 2) != 0 )
    {
      RwLockAcquireForRead(&DhcpGlobalReadWriteLock);
      if ( (unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, *(unsigned int *)(v4 + 8)) )
      {
        RwLockRelease(&DhcpGlobalReadWriteLock);
        v6 = SetFailoverClientInfoToReservation(v4);
        if ( v6 )
          return v6;
      }
      else
      {
        RwLockRelease(&DhcpGlobalReadWriteLock);
        ((void (__fastcall *)(_QWORD, __int64, __int64, bool, int *))gAAUpdateBitMask)(
          *a1,
          3,
          1,
          *((_QWORD *)a1 + 1) != 0,
          &v34);
      }
    }
    EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    Value = DhcpDALJetBeginTransaction(DhcpGlobalJetServerSession);
    v6 = Value;
    if ( Value )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_14;
      }
      v15 = 77;
LABEL_13:
      WPP_SF_D(v14[2], v15, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, Value);
LABEL_14:
      LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
      return v6;
    }
    v6 = DhcpDALJetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 1, 0);
    if ( v6 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_82;
      }
      v17 = 78;
LABEL_19:
      WPP_SF_dD(v16[2], v17, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, v6, *a1);
LABEL_82:
      DhcpDALJetRollback(DhcpGlobalJetServerSession);
      goto LABEL_14;
    }
    --v33;
    v21 = DhcpDALJetSetValue(
            DhcpGlobalJetServerSession,
            DhcpGlobalClientTableHandle,
            *(_DWORD *)(DhcpGlobalClientTable + 328),
            (unsigned int)&v33,
            4u);
    v6 = v21;
    if ( v21 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_82;
      }
      v23 = 79;
      goto LABEL_81;
    }
    v24 = (unsigned __int8 *)*((_QWORD *)a1 + 1);
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, *a1, *v24);
      }
      v21 = DhcpDALJetCommitUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
      v6 = v21;
      if ( !v21 )
        goto LABEL_83;
      if ( v21 == 80 )
        goto LABEL_82;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_82;
      }
      v23 = 81;
    }
    else
    {
      if ( ((v12 - 1) & 0xFFFFFFFD) != 0 )
        goto LABEL_76;
      v21 = DhcpDALJetSetValue(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableHandle,
              *(_DWORD *)(DhcpGlobalClientTable + 232),
              (int)v4 + 36,
              4u);
      v6 = v21;
      if ( v21 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_82;
        }
        v23 = 82;
        goto LABEL_81;
      }
      v21 = DhcpDALJetSetValue(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableHandle,
              *(_DWORD *)(DhcpGlobalClientTable + 248),
              (int)v4 + 36,
              4u);
      v6 = v21;
      if ( !v21 )
      {
LABEL_76:
        v21 = DhcpDALJetCommitUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
        v6 = v21;
        if ( !v21 )
          goto LABEL_83;
        if ( v21 == 80 )
          goto LABEL_82;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_82;
        }
        v23 = 84;
      }
      else
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_82;
        }
        v23 = 83;
      }
    }
LABEL_81:
    WPP_SF_D(v22[2], v23, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids, v21);
    goto LABEL_82;
  }
  return 87;
}

```

## disassembly

```asm
0x1800c47f4  mov     [rsp-38h+arg_8], rbx
0x1800c47f9  push    rbp
0x1800c47fa  push    rsi
0x1800c47fb  push    rdi
0x1800c47fc  push    r12
0x1800c47fe  push    r13
0x1800c4800  push    r14
0x1800c4802  push    r15
0x1800c4804  mov     rbp, rsp
0x1800c4807  sub     rsp, 50h
0x1800c480b  xor     ebx, ebx
0x1800c480d  mov     r13, rdx
0x1800c4810  mov     dword ptr [rbp+arg_18], ebx
0x1800c4813  mov     r14, rcx
0x1800c4816  mov     dword ptr [rbp+var_20], ebx
0x1800c4819  mov     esi, ebx
0x1800c481b  mov     [rbp+arg_0], ebx
0x1800c481e  mov     dword ptr [rbp+var_20+4], ebx
0x1800c4821  mov     [rbp+arg_10], ebx
0x1800c4824  test    rcx, rcx
0x1800c4827  jz      loc_1800C4F53
0x1800c482d  test    rdx, rdx
0x1800c4830  jz      loc_1800C4F53
0x1800c4836  lea     r12d, [rbx+1]
0x1800c483a  lea     rax, [rdx+0Ch]
0x1800c483e  cmp     [rdx+18h], rbx
0x1800c4842  jnz     short loc_1800C484C
0x1800c4844  test    byte ptr [rax], 4
0x1800c4847  mov     ecx, r12d
0x1800c484a  jz      short loc_1800C484E
0x1800c484c  mov     ecx, ebx
0x1800c484e  mov     r8b, [rax]
0x1800c4851  mov     dl, [rdx+0Dh]
0x1800c4854  call    MapOldStateToNewState
0x1800c4859  mov     edi, eax
0x1800c485b  test    eax, eax
0x1800c485d  jz      loc_1800C4EC6
0x1800c4863  cmp     eax, 6
0x1800c4866  jz      loc_1800C4EC6
0x1800c486c  lea     r15, DhcpGlobalJetDatabaseCritSect
0x1800c4873  mov     rcx, r15; lpCriticalSection
0x1800c4876  test    r8b, 4
0x1800c487a  jz      loc_1800C49C3
0x1800c4880  mov     [rbp+var_18], r14
0x1800c4884  mov     [rbp+var_10], 4
0x1800c488b  mov     [rbp+var_C], r12d
0x1800c488f  call    cs:__imp_EnterCriticalSection
0x1800c4896  nop     dword ptr [rax+rax+00h]
0x1800c489b  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800c48a2  call    DhcpDALJetBeginTransaction
0x1800c48a7  mov     esi, eax
0x1800c48a9  test    eax, eax
0x1800c48ab  jz      short loc_1800C48F5
0x1800c48ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c48b4  lea     rdi, WPP_GLOBAL_Control
0x1800c48bb  cmp     rcx, rdi
0x1800c48be  jz      short loc_1800C48E1
0x1800c48c0  test    dword ptr [rcx+1Ch], 800000h
0x1800c48c7  jz      short loc_1800C48E1
0x1800c48c9  mov     edx, 47h ; 'G'
0x1800c48ce  mov     rcx, [rcx+10h]
0x1800c48d2  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c48d9  mov     r9d, eax
0x1800c48dc  call    WPP_SF_D
0x1800c48e1  mov     rcx, r15; lpCriticalSection
0x1800c48e4  call    cs:__imp_LeaveCriticalSection
0x1800c48eb  nop     dword ptr [rax+rax+00h]
0x1800c48f0  jmp     loc_1800C4F4F
0x1800c48f5  mov     rdx, cs:DeletedAddressTableHandle; tableid
0x1800c48fc  lea     r9, [rbp+var_18]
0x1800c4900  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c4907  lea     r8, aDeletedipaddre_0; "DeletedIPAddress"
0x1800c490e  mov     dword ptr [rsp+50h+var_30], r12d; int
0x1800c4913  call    DhcpDALJetOpenKey
0x1800c4918  mov     esi, eax
0x1800c491a  test    eax, eax
0x1800c491c  jz      short loc_1800C4966
0x1800c491e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4925  lea     rdi, WPP_GLOBAL_Control
0x1800c492c  cmp     rcx, rdi
0x1800c492f  jz      loc_1800C4EA4
0x1800c4935  test    dword ptr [rcx+1Ch], 800000h
0x1800c493c  jz      loc_1800C4EA4
0x1800c4942  mov     edx, 48h ; 'H'
0x1800c4947  mov     eax, [r14]
0x1800c494a  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c4951  mov     rcx, [rcx+10h]
0x1800c4955  mov     r9d, esi
0x1800c4958  mov     dword ptr [rsp+50h+var_30], eax
0x1800c495c  call    WPP_SF_dD
0x1800c4961  jmp     loc_1800C4EA4
0x1800c4966  mov     rdx, cs:DeletedAddressTableHandle; tableid
0x1800c496d  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c4974  call    cs:__imp_JetDelete
0x1800c497b  nop     dword ptr [rax+rax+00h]
0x1800c4980  mov     ecx, eax
0x1800c4982  lea     rdx, aDhcpdaljetdele; "DhcpDALJetDeleteCurrentRecord"
0x1800c4989  call    DhcpDALMapJetError
0x1800c498e  mov     esi, eax
0x1800c4990  test    eax, eax
0x1800c4992  jz      loc_1800C4EB5
0x1800c4998  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c499f  lea     rdi, WPP_GLOBAL_Control
0x1800c49a6  cmp     rcx, rdi
0x1800c49a9  jz      loc_1800C4EA4
0x1800c49af  test    dword ptr [rcx+1Ch], 800000h
0x1800c49b6  jz      loc_1800C4EA4
0x1800c49bc  mov     edx, 49h ; 'I'
0x1800c49c1  jmp     short loc_1800C4947
0x1800c49c3  call    cs:__imp_EnterCriticalSection
0x1800c49ca  nop     dword ptr [rax+rax+00h]
0x1800c49cf  mov     r8, cs:DhcpGlobalClientTable
0x1800c49d6  lea     r9, [rbp+var_18]
0x1800c49da  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800c49e1  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c49e8  mov     [rbp+var_18], r14
0x1800c49ec  mov     r8, [r8]
0x1800c49ef  mov     [rbp+var_10], 4
0x1800c49f6  mov     [rbp+var_C], r12d
0x1800c49fa  mov     dword ptr [rsp+50h+var_30], r12d; int
0x1800c49ff  call    DhcpDALJetOpenKey
0x1800c4a04  mov     esi, eax
0x1800c4a06  test    eax, eax
0x1800c4a08  jz      short loc_1800C4A52
0x1800c4a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4a11  lea     rdi, WPP_GLOBAL_Control
0x1800c4a18  cmp     rcx, rdi
0x1800c4a1b  jz      loc_1800C48E1
0x1800c4a21  test    dword ptr [rcx+1Ch], 800000h
0x1800c4a28  jz      loc_1800C48E1
0x1800c4a2e  mov     eax, [r14]
0x1800c4a31  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c4a38  mov     rcx, [rcx+10h]
0x1800c4a3c  mov     edx, 4Ah ; 'J'
0x1800c4a41  mov     r9d, esi
0x1800c4a44  mov     dword ptr [rsp+50h+var_30], eax
0x1800c4a48  call    WPP_SF_dD
0x1800c4a4d  jmp     loc_1800C48E1
0x1800c4a52  mov     r8, cs:DhcpGlobalClientTable
0x1800c4a59  lea     rax, [rbp+arg_18]
0x1800c4a5d  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800c4a64  lea     r9, [rbp+arg_0]
0x1800c4a68  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c4a6f  mov     dword ptr [rbp+arg_18], 4
0x1800c4a76  mov     r8d, [r8+148h]; columnid
0x1800c4a7d  mov     [rsp+50h+var_30], rax; __int64
0x1800c4a82  call    DhcpDALJetGetValue
0x1800c4a87  mov     esi, eax
0x1800c4a89  test    eax, eax
0x1800c4a8b  jz      short loc_1800C4ABB
0x1800c4a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4a94  lea     rdi, WPP_GLOBAL_Control
0x1800c4a9b  cmp     rcx, rdi
0x1800c4a9e  jz      loc_1800C48E1
0x1800c4aa4  test    dword ptr [rcx+1Ch], 800000h
0x1800c4aab  jz      loc_1800C48E1
0x1800c4ab1  mov     edx, 4Bh ; 'K'
0x1800c4ab6  jmp     loc_1800C48CE
0x1800c4abb  mov     r8, cs:DhcpGlobalClientTable
0x1800c4ac2  lea     rax, [rbp+var_20]
0x1800c4ac6  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800c4acd  lea     r9, [rbp+var_20+4]
0x1800c4ad1  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c4ad8  mov     dword ptr [rbp+var_20], 4
0x1800c4adf  mov     r8d, [r8+138h]; columnid
0x1800c4ae6  mov     [rsp+50h+var_30], rax; __int64
0x1800c4aeb  call    DhcpDALJetGetValue
0x1800c4af0  mov     esi, eax
0x1800c4af2  test    eax, eax
0x1800c4af4  jz      short loc_1800C4B24
0x1800c4af6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4afd  lea     rdi, WPP_GLOBAL_Control
0x1800c4b04  cmp     rcx, rdi
0x1800c4b07  jz      loc_1800C48E1
0x1800c4b0d  test    dword ptr [rcx+1Ch], 800000h
0x1800c4b14  jz      loc_1800C48E1
0x1800c4b1a  mov     edx, 4Ch ; 'L'
0x1800c4b1f  jmp     loc_1800C48CE
0x1800c4b24  mov     rcx, r15; lpCriticalSection
0x1800c4b27  call    cs:__imp_LeaveCriticalSection
0x1800c4b2e  nop     dword ptr [rax+rax+00h]
0x1800c4b33  cmp     [rbp+arg_0], ebx
0x1800c4b36  jnz     short loc_1800C4B3F
0x1800c4b38  mov     esi, ebx
0x1800c4b3a  jmp     loc_1800C4F4F
0x1800c4b3f  mov     al, [r13+0Ch]
0x1800c4b43  test    r12b, al
0x1800c4b46  jz      short loc_1800C4B77
0x1800c4b48  mov     eax, dword ptr [rbp+var_20+4]
0x1800c4b4b  and     eax, r12d
0x1800c4b4e  test    al, al
0x1800c4b50  jz      loc_1800C4F4F
0x1800c4b56  mov     ecx, [r14]
0x1800c4b59  call    DeleteFailoverClientInfo
0x1800c4b5e  mov     esi, eax
0x1800c4b60  test    eax, eax
0x1800c4b62  jnz     loc_1800C4F4F
0x1800c4b68  cmp     [r14+8], rbx
0x1800c4b6c  lea     edx, [rax+3]
0x1800c4b6f  setnz   bl
0x1800c4b72  jmp     loc_1800C4F31
0x1800c4b77  test    al, 2
0x1800c4b79  jz      short loc_1800C4BEA
0x1800c4b7b  lea     rsi, DhcpGlobalReadWriteLock
0x1800c4b82  mov     rcx, rsi
0x1800c4b85  call    RwLockAcquireForRead
0x1800c4b8a  mov     edx, [r13+8]
0x1800c4b8e  mov     rcx, cs:DhcpGlobalThisServer
0x1800c4b95  call    MemServerIsReservedAddress
0x1800c4b9a  mov     rcx, rsi
0x1800c4b9d  test    eax, eax
0x1800c4b9f  jnz     short loc_1800C4BD3
0x1800c4ba1  call    RwLockRelease
0x1800c4ba6  cmp     [r14+8], rbx
0x1800c4baa  lea     rax, [rbp+arg_10]
0x1800c4bae  mov     ecx, [r14]
0x1800c4bb1  mov     r9d, ebx
0x1800c4bb4  mov     [rsp+50h+var_30], rax
0x1800c4bb9  setnz   r9b
0x1800c4bbd  mov     rax, cs:gAAUpdateBitMask
0x1800c4bc4  mov     r8d, r12d
0x1800c4bc7  mov     edx, 3
0x1800c4bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4bd1  jmp     short loc_1800C4BEA
0x1800c4bd3  call    RwLockRelease
0x1800c4bd8  mov     rcx, r13
0x1800c4bdb  call    SetFailoverClientInfoToReservation
0x1800c4be0  mov     esi, eax
0x1800c4be2  test    eax, eax
0x1800c4be4  jnz     loc_1800C4F4F
0x1800c4bea  mov     rcx, r15; lpCriticalSection
0x1800c4bed  call    cs:__imp_EnterCriticalSection
0x1800c4bf4  nop     dword ptr [rax+rax+00h]
0x1800c4bf9  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800c4c00  call    DhcpDALJetBeginTransaction
0x1800c4c05  mov     esi, eax
0x1800c4c07  test    eax, eax
0x1800c4c09  jz      short loc_1800C4C39
0x1800c4c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4c12  lea     rdi, WPP_GLOBAL_Control
0x1800c4c19  cmp     rcx, rdi
0x1800c4c1c  jz      loc_1800C48E1
0x1800c4c22  test    dword ptr [rcx+1Ch], 800000h
0x1800c4c29  jz      loc_1800C48E1
0x1800c4c2f  mov     edx, 4Dh ; 'M'
0x1800c4c34  jmp     loc_1800C48CE
0x1800c4c39  mov     r8, cs:DhcpGlobalClientTable
0x1800c4c40  lea     r9, [rbp+var_18]
0x1800c4c44  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800c4c4b  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c4c52  mov     [rsp+50h+var_28], ebx; int
0x1800c4c56  mov     r8, [r8]
0x1800c4c59  mov     dword ptr [rsp+50h+var_30], r12d; int
0x1800c4c5e  call    DhcpDALJetPrepareUpdate
0x1800c4c63  mov     esi, eax
0x1800c4c65  test    eax, eax
0x1800c4c67  jz      short loc_1800C4C97
0x1800c4c69  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4c70  lea     rdi, WPP_GLOBAL_Control
0x1800c4c77  cmp     rcx, rdi
0x1800c4c7a  jz      loc_1800C4EA4
0x1800c4c80  test    dword ptr [rcx+1Ch], 800000h
0x1800c4c87  jz      loc_1800C4EA4
0x1800c4c8d  mov     edx, 4Eh ; 'N'
0x1800c4c92  jmp     loc_1800C4947
0x1800c4c97  mov     r8, cs:DhcpGlobalClientTable
0x1800c4c9e  lea     r9, [rbp+arg_0]
0x1800c4ca2  dec     [rbp+arg_0]
0x1800c4ca5  mov     r12d, 4
0x1800c4cab  mov     rdx, cs:DhcpGlobalClientTableHandle
0x1800c4cb2  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800c4cb9  mov     r8d, [r8+148h]
0x1800c4cc0  mov     dword ptr [rsp+50h+var_30], r12d
0x1800c4cc5  call    DhcpDALJetSetValue
0x1800c4cca  mov     esi, eax
0x1800c4ccc  test    eax, eax
0x1800c4cce  jz      short loc_1800C4CFE
0x1800c4cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4cd7  lea     rdi, WPP_GLOBAL_Control
0x1800c4cde  cmp     rcx, rdi
0x1800c4ce1  jz      loc_1800C4EA4
0x1800c4ce7  test    dword ptr [rcx+1Ch], 800000h
0x1800c4cee  jz      loc_1800C4EA4
0x1800c4cf4  lea     edx, [r12+4Bh]
0x1800c4cf9  jmp     loc_1800C4E91
0x1800c4cfe  mov     rax, [r14+8]
0x1800c4d02  test    rax, rax
0x1800c4d05  jz      loc_1800C4D93
0x1800c4d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4d12  lea     rdi, WPP_GLOBAL_Control
0x1800c4d19  cmp     rcx, rdi
0x1800c4d1c  jz      short loc_1800C4D46
0x1800c4d1e  test    dword ptr [rcx+1Ch], 800000h
0x1800c4d25  jz      short loc_1800C4D46
0x1800c4d27  movzx   eax, byte ptr [rax]
0x1800c4d2a  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c4d31  mov     r9d, [r14]
0x1800c4d34  mov     edx, 50h ; 'P'
0x1800c4d39  mov     rcx, [rcx+10h]
0x1800c4d3d  mov     dword ptr [rsp+50h+var_30], eax
  ... truncated ...
```
