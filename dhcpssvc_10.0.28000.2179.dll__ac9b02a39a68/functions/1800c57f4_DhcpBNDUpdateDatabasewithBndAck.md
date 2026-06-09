# DhcpBNDUpdateDatabasewithBndAck

- ea: `0x1800c57f4`
- end: `0x1800c5f71`
- name: `DhcpBNDUpdateDatabasewithBndAck`
- size: `1917`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c1a80`

## callees

- `0x18000282c`
- `0x1800057e0`
- `0x180024720`
- `0x180024960`
- `0x180098a40`
- `0x1800a03f0`
- `0x1800a0418`
- `0x1800a0448`
- `0x1800a05b8`
- `0x1800a0788`
- `0x1800a0ac8`
- `0x1800a0b3c`
- `0x1800a0b68`
- `0x1800a0bac`
- `0x1800bed5c`
- `0x1800c57f4`
- `0x1800c66c8`
- `0x1800c6fbc`
- `0x1800cf010`

## import_xrefs

- `ESENT!JetDelete` at `0x1800c5974`
- `ESENT!JetDelete` at `0x1800c5974`
- `KERNEL32!EnterCriticalSection` at `0x1800c588f`
- `KERNEL32!EnterCriticalSection` at `0x1800c59c3`
- `KERNEL32!EnterCriticalSection` at `0x1800c5bed`
- `KERNEL32!EnterCriticalSection` at `0x1800c588f`
- `KERNEL32!EnterCriticalSection` at `0x1800c59c3`
- `KERNEL32!EnterCriticalSection` at `0x1800c5bed`
- `KERNEL32!LeaveCriticalSection` at `0x1800c58e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800c5b27`
- `KERNEL32!LeaveCriticalSection` at `0x1800c58e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800c5b27`

## string_xrefs

- `0x1800c5907`: `DeletedIPAddress`
- `0x1800c5982`: `DhcpDALJetDeleteCurrentRecord`

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
0x1800c57f4  mov     [rsp-38h+arg_8], rbx
0x1800c57f9  push    rbp
0x1800c57fa  push    rsi
0x1800c57fb  push    rdi
0x1800c57fc  push    r12
0x1800c57fe  push    r13
0x1800c5800  push    r14
0x1800c5802  push    r15
0x1800c5804  mov     rbp, rsp
0x1800c5807  sub     rsp, 50h
0x1800c580b  xor     ebx, ebx
0x1800c580d  mov     r13, rdx
0x1800c5810  mov     dword ptr [rbp+arg_18], ebx
0x1800c5813  mov     r14, rcx
0x1800c5816  mov     dword ptr [rbp+var_20], ebx
0x1800c5819  mov     esi, ebx
0x1800c581b  mov     [rbp+arg_0], ebx
0x1800c581e  mov     dword ptr [rbp+var_20+4], ebx
0x1800c5821  mov     [rbp+arg_10], ebx
0x1800c5824  test    rcx, rcx
0x1800c5827  jz      loc_1800C5F53
0x1800c582d  test    rdx, rdx
0x1800c5830  jz      loc_1800C5F53
0x1800c5836  lea     r12d, [rbx+1]
0x1800c583a  lea     rax, [rdx+0Ch]
0x1800c583e  cmp     [rdx+18h], rbx
0x1800c5842  jnz     short loc_1800C584C
0x1800c5844  test    byte ptr [rax], 4
0x1800c5847  mov     ecx, r12d
0x1800c584a  jz      short loc_1800C584E
0x1800c584c  mov     ecx, ebx
0x1800c584e  mov     r8b, [rax]
0x1800c5851  mov     dl, [rdx+0Dh]
0x1800c5854  call    MapOldStateToNewState
0x1800c5859  mov     edi, eax
0x1800c585b  test    eax, eax
0x1800c585d  jz      loc_1800C5EC6
0x1800c5863  cmp     eax, 6
0x1800c5866  jz      loc_1800C5EC6
0x1800c586c  lea     r15, DhcpGlobalJetDatabaseCritSect
0x1800c5873  mov     rcx, r15; lpCriticalSection
0x1800c5876  test    r8b, 4
0x1800c587a  jz      loc_1800C59C3
0x1800c5880  mov     [rbp+var_18], r14
0x1800c5884  mov     [rbp+var_10], 4
0x1800c588b  mov     [rbp+var_C], r12d
0x1800c588f  call    cs:__imp_EnterCriticalSection
0x1800c5896  nop     dword ptr [rax+rax+00h]
0x1800c589b  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800c58a2  call    DhcpDALJetBeginTransaction
0x1800c58a7  mov     esi, eax
0x1800c58a9  test    eax, eax
0x1800c58ab  jz      short loc_1800C58F5
0x1800c58ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c58b4  lea     rdi, WPP_GLOBAL_Control
0x1800c58bb  cmp     rcx, rdi
0x1800c58be  jz      short loc_1800C58E1
0x1800c58c0  test    dword ptr [rcx+1Ch], 800000h
0x1800c58c7  jz      short loc_1800C58E1
0x1800c58c9  mov     edx, 47h ; 'G'
0x1800c58ce  mov     rcx, [rcx+10h]
0x1800c58d2  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c58d9  mov     r9d, eax
0x1800c58dc  call    WPP_SF_D
0x1800c58e1  mov     rcx, r15; lpCriticalSection
0x1800c58e4  call    cs:__imp_LeaveCriticalSection
0x1800c58eb  nop     dword ptr [rax+rax+00h]
0x1800c58f0  jmp     loc_1800C5F4F
0x1800c58f5  mov     rdx, cs:DeletedAddressTableHandle; tableid
0x1800c58fc  lea     r9, [rbp+var_18]
0x1800c5900  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c5907  lea     r8, aDeletedipaddre_0; "DeletedIPAddress"
0x1800c590e  mov     dword ptr [rsp+50h+var_30], r12d; int
0x1800c5913  call    DhcpDALJetOpenKey
0x1800c5918  mov     esi, eax
0x1800c591a  test    eax, eax
0x1800c591c  jz      short loc_1800C5966
0x1800c591e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5925  lea     rdi, WPP_GLOBAL_Control
0x1800c592c  cmp     rcx, rdi
0x1800c592f  jz      loc_1800C5EA4
0x1800c5935  test    dword ptr [rcx+1Ch], 800000h
0x1800c593c  jz      loc_1800C5EA4
0x1800c5942  mov     edx, 48h ; 'H'
0x1800c5947  mov     eax, [r14]
0x1800c594a  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c5951  mov     rcx, [rcx+10h]
0x1800c5955  mov     r9d, esi
0x1800c5958  mov     dword ptr [rsp+50h+var_30], eax
0x1800c595c  call    WPP_SF_dD
0x1800c5961  jmp     loc_1800C5EA4
0x1800c5966  mov     rdx, cs:DeletedAddressTableHandle; tableid
0x1800c596d  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c5974  call    cs:__imp_JetDelete
0x1800c597b  nop     dword ptr [rax+rax+00h]
0x1800c5980  mov     ecx, eax
0x1800c5982  lea     rdx, aDhcpdaljetdele; "DhcpDALJetDeleteCurrentRecord"
0x1800c5989  call    DhcpDALMapJetError
0x1800c598e  mov     esi, eax
0x1800c5990  test    eax, eax
0x1800c5992  jz      loc_1800C5EB5
0x1800c5998  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c599f  lea     rdi, WPP_GLOBAL_Control
0x1800c59a6  cmp     rcx, rdi
0x1800c59a9  jz      loc_1800C5EA4
0x1800c59af  test    dword ptr [rcx+1Ch], 800000h
0x1800c59b6  jz      loc_1800C5EA4
0x1800c59bc  mov     edx, 49h ; 'I'
0x1800c59c1  jmp     short loc_1800C5947
0x1800c59c3  call    cs:__imp_EnterCriticalSection
0x1800c59ca  nop     dword ptr [rax+rax+00h]
0x1800c59cf  mov     r8, cs:DhcpGlobalClientTable
0x1800c59d6  lea     r9, [rbp+var_18]
0x1800c59da  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800c59e1  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c59e8  mov     [rbp+var_18], r14
0x1800c59ec  mov     r8, [r8]
0x1800c59ef  mov     [rbp+var_10], 4
0x1800c59f6  mov     [rbp+var_C], r12d
0x1800c59fa  mov     dword ptr [rsp+50h+var_30], r12d; int
0x1800c59ff  call    DhcpDALJetOpenKey
0x1800c5a04  mov     esi, eax
0x1800c5a06  test    eax, eax
0x1800c5a08  jz      short loc_1800C5A52
0x1800c5a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5a11  lea     rdi, WPP_GLOBAL_Control
0x1800c5a18  cmp     rcx, rdi
0x1800c5a1b  jz      loc_1800C58E1
0x1800c5a21  test    dword ptr [rcx+1Ch], 800000h
0x1800c5a28  jz      loc_1800C58E1
0x1800c5a2e  mov     eax, [r14]
0x1800c5a31  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c5a38  mov     rcx, [rcx+10h]
0x1800c5a3c  mov     edx, 4Ah ; 'J'
0x1800c5a41  mov     r9d, esi
0x1800c5a44  mov     dword ptr [rsp+50h+var_30], eax
0x1800c5a48  call    WPP_SF_dD
0x1800c5a4d  jmp     loc_1800C58E1
0x1800c5a52  mov     r8, cs:DhcpGlobalClientTable
0x1800c5a59  lea     rax, [rbp+arg_18]
0x1800c5a5d  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800c5a64  lea     r9, [rbp+arg_0]
0x1800c5a68  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c5a6f  mov     dword ptr [rbp+arg_18], 4
0x1800c5a76  mov     r8d, [r8+148h]; columnid
0x1800c5a7d  mov     [rsp+50h+var_30], rax; __int64
0x1800c5a82  call    DhcpDALJetGetValue
0x1800c5a87  mov     esi, eax
0x1800c5a89  test    eax, eax
0x1800c5a8b  jz      short loc_1800C5ABB
0x1800c5a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5a94  lea     rdi, WPP_GLOBAL_Control
0x1800c5a9b  cmp     rcx, rdi
0x1800c5a9e  jz      loc_1800C58E1
0x1800c5aa4  test    dword ptr [rcx+1Ch], 800000h
0x1800c5aab  jz      loc_1800C58E1
0x1800c5ab1  mov     edx, 4Bh ; 'K'
0x1800c5ab6  jmp     loc_1800C58CE
0x1800c5abb  mov     r8, cs:DhcpGlobalClientTable
0x1800c5ac2  lea     rax, [rbp+var_20]
0x1800c5ac6  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800c5acd  lea     r9, [rbp+var_20+4]
0x1800c5ad1  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c5ad8  mov     dword ptr [rbp+var_20], 4
0x1800c5adf  mov     r8d, [r8+138h]; columnid
0x1800c5ae6  mov     [rsp+50h+var_30], rax; __int64
0x1800c5aeb  call    DhcpDALJetGetValue
0x1800c5af0  mov     esi, eax
0x1800c5af2  test    eax, eax
0x1800c5af4  jz      short loc_1800C5B24
0x1800c5af6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5afd  lea     rdi, WPP_GLOBAL_Control
0x1800c5b04  cmp     rcx, rdi
0x1800c5b07  jz      loc_1800C58E1
0x1800c5b0d  test    dword ptr [rcx+1Ch], 800000h
0x1800c5b14  jz      loc_1800C58E1
0x1800c5b1a  mov     edx, 4Ch ; 'L'
0x1800c5b1f  jmp     loc_1800C58CE
0x1800c5b24  mov     rcx, r15; lpCriticalSection
0x1800c5b27  call    cs:__imp_LeaveCriticalSection
0x1800c5b2e  nop     dword ptr [rax+rax+00h]
0x1800c5b33  cmp     [rbp+arg_0], ebx
0x1800c5b36  jnz     short loc_1800C5B3F
0x1800c5b38  mov     esi, ebx
0x1800c5b3a  jmp     loc_1800C5F4F
0x1800c5b3f  mov     al, [r13+0Ch]
0x1800c5b43  test    r12b, al
0x1800c5b46  jz      short loc_1800C5B77
0x1800c5b48  mov     eax, dword ptr [rbp+var_20+4]
0x1800c5b4b  and     eax, r12d
0x1800c5b4e  test    al, al
0x1800c5b50  jz      loc_1800C5F4F
0x1800c5b56  mov     ecx, [r14]
0x1800c5b59  call    DeleteFailoverClientInfo
0x1800c5b5e  mov     esi, eax
0x1800c5b60  test    eax, eax
0x1800c5b62  jnz     loc_1800C5F4F
0x1800c5b68  cmp     [r14+8], rbx
0x1800c5b6c  lea     edx, [rax+3]
0x1800c5b6f  setnz   bl
0x1800c5b72  jmp     loc_1800C5F31
0x1800c5b77  test    al, 2
0x1800c5b79  jz      short loc_1800C5BEA
0x1800c5b7b  lea     rsi, DhcpGlobalReadWriteLock
0x1800c5b82  mov     rcx, rsi
0x1800c5b85  call    RwLockAcquireForRead
0x1800c5b8a  mov     edx, [r13+8]
0x1800c5b8e  mov     rcx, cs:DhcpGlobalThisServer
0x1800c5b95  call    MemServerIsReservedAddress
0x1800c5b9a  mov     rcx, rsi
0x1800c5b9d  test    eax, eax
0x1800c5b9f  jnz     short loc_1800C5BD3
0x1800c5ba1  call    RwLockRelease
0x1800c5ba6  cmp     [r14+8], rbx
0x1800c5baa  lea     rax, [rbp+arg_10]
0x1800c5bae  mov     ecx, [r14]
0x1800c5bb1  mov     r9d, ebx
0x1800c5bb4  mov     [rsp+50h+var_30], rax
0x1800c5bb9  setnz   r9b
0x1800c5bbd  mov     rax, cs:gAAUpdateBitMask
0x1800c5bc4  mov     r8d, r12d
0x1800c5bc7  mov     edx, 3
0x1800c5bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5bd1  jmp     short loc_1800C5BEA
0x1800c5bd3  call    RwLockRelease
0x1800c5bd8  mov     rcx, r13
0x1800c5bdb  call    SetFailoverClientInfoToReservation
0x1800c5be0  mov     esi, eax
0x1800c5be2  test    eax, eax
0x1800c5be4  jnz     loc_1800C5F4F
0x1800c5bea  mov     rcx, r15; lpCriticalSection
0x1800c5bed  call    cs:__imp_EnterCriticalSection
0x1800c5bf4  nop     dword ptr [rax+rax+00h]
0x1800c5bf9  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800c5c00  call    DhcpDALJetBeginTransaction
0x1800c5c05  mov     esi, eax
0x1800c5c07  test    eax, eax
0x1800c5c09  jz      short loc_1800C5C39
0x1800c5c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5c12  lea     rdi, WPP_GLOBAL_Control
0x1800c5c19  cmp     rcx, rdi
0x1800c5c1c  jz      loc_1800C58E1
0x1800c5c22  test    dword ptr [rcx+1Ch], 800000h
0x1800c5c29  jz      loc_1800C58E1
0x1800c5c2f  mov     edx, 4Dh ; 'M'
0x1800c5c34  jmp     loc_1800C58CE
0x1800c5c39  mov     r8, cs:DhcpGlobalClientTable
0x1800c5c40  lea     r9, [rbp+var_18]
0x1800c5c44  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800c5c4b  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800c5c52  mov     [rsp+50h+var_28], ebx; int
0x1800c5c56  mov     r8, [r8]
0x1800c5c59  mov     dword ptr [rsp+50h+var_30], r12d; int
0x1800c5c5e  call    DhcpDALJetPrepareUpdate
0x1800c5c63  mov     esi, eax
0x1800c5c65  test    eax, eax
0x1800c5c67  jz      short loc_1800C5C97
0x1800c5c69  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5c70  lea     rdi, WPP_GLOBAL_Control
0x1800c5c77  cmp     rcx, rdi
0x1800c5c7a  jz      loc_1800C5EA4
0x1800c5c80  test    dword ptr [rcx+1Ch], 800000h
0x1800c5c87  jz      loc_1800C5EA4
0x1800c5c8d  mov     edx, 4Eh ; 'N'
0x1800c5c92  jmp     loc_1800C5947
0x1800c5c97  mov     r8, cs:DhcpGlobalClientTable
0x1800c5c9e  lea     r9, [rbp+arg_0]
0x1800c5ca2  dec     [rbp+arg_0]
0x1800c5ca5  mov     r12d, 4
0x1800c5cab  mov     rdx, cs:DhcpGlobalClientTableHandle
0x1800c5cb2  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800c5cb9  mov     r8d, [r8+148h]
0x1800c5cc0  mov     dword ptr [rsp+50h+var_30], r12d
0x1800c5cc5  call    DhcpDALJetSetValue
0x1800c5cca  mov     esi, eax
0x1800c5ccc  test    eax, eax
0x1800c5cce  jz      short loc_1800C5CFE
0x1800c5cd0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5cd7  lea     rdi, WPP_GLOBAL_Control
0x1800c5cde  cmp     rcx, rdi
0x1800c5ce1  jz      loc_1800C5EA4
0x1800c5ce7  test    dword ptr [rcx+1Ch], 800000h
0x1800c5cee  jz      loc_1800C5EA4
0x1800c5cf4  lea     edx, [r12+4Bh]
0x1800c5cf9  jmp     loc_1800C5E91
0x1800c5cfe  mov     rax, [r14+8]
0x1800c5d02  test    rax, rax
0x1800c5d05  jz      loc_1800C5D93
0x1800c5d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5d12  lea     rdi, WPP_GLOBAL_Control
0x1800c5d19  cmp     rcx, rdi
0x1800c5d1c  jz      short loc_1800C5D46
0x1800c5d1e  test    dword ptr [rcx+1Ch], 800000h
0x1800c5d25  jz      short loc_1800C5D46
0x1800c5d27  movzx   eax, byte ptr [rax]
0x1800c5d2a  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c5d31  mov     r9d, [r14]
0x1800c5d34  mov     edx, 50h ; 'P'
0x1800c5d39  mov     rcx, [rcx+10h]
0x1800c5d3d  mov     dword ptr [rsp+50h+var_30], eax
  ... truncated ...
```
