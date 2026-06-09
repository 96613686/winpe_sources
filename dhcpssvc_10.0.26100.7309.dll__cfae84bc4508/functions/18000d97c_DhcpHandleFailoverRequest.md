# DhcpHandleFailoverRequest

- ea: `0x18000d97c`
- end: `0x18000df91`
- name: `DhcpHandleFailoverRequest`
- size: `1557`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800083d0`
- `0x1800093a0`
- `0x180021b20`
- `0x1800220e4`
- `0x180050708`
- `0x180058034`
- `0x180058f38`
- `0x18005ad38`

## callees

- `0x180002854`
- `0x180007be4`
- `0x18000d97c`
- `0x18000eb58`
- `0x18000ebd4`
- `0x18000ef84`
- `0x18000f0f8`
- `0x18000f2ac`
- `0x180011680`
- `0x180031e80`
- `0x1800808e0`
- `0x18008eea8`
- `0x18009f06c`
- `0x18009f738`
- `0x18009f760`
- `0x18009f8f4`
- `0x18009fac4`
- `0x18009fe78`
- `0x18009fee0`
- `0x1800a9270`
- `0x1800bfdec`
- `0x1800c9058`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetDelete` at `0x18000ddef`
- `ESENT!JetDelete` at `0x18000ddef`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000db42`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000db42`
- `KERNEL32!AcquireSRWLockShared` at `0x18000db2c`
- `KERNEL32!AcquireSRWLockShared` at `0x18000db2c`
- `KERNEL32!LocalFree` at `0x18000dcc7`
- `KERNEL32!LocalFree` at `0x18000df5a`
- `KERNEL32!LocalFree` at `0x18000dcc7`
- `KERNEL32!LocalFree` at `0x18000df5a`
- `KERNEL32!EnterCriticalSection` at `0x18000dab5`
- `KERNEL32!EnterCriticalSection` at `0x18000dab5`
- `KERNEL32!LeaveCriticalSection` at `0x18000db13`
- `KERNEL32!LeaveCriticalSection` at `0x18000db55`
- `KERNEL32!LeaveCriticalSection` at `0x18000db13`
- `KERNEL32!LeaveCriticalSection` at `0x18000db55`

## string_xrefs

- `0x18000ddfd`: `DhcpDALJetDeleteCurrentRecord`

## pseudocode

```c
__int64 __fastcall DhcpHandleFailoverRequest(__int64 a1, int a2, __int64 a3, int a4)
{
  __int64 v6; // rcx
  int v7; // r12d
  unsigned int CurrentFailoverClientInfo; // ebx
  unsigned int Value; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  char v13; // dl
  unsigned int v14; // eax
  __int64 *v15; // rsi
  int v16; // edi
  bool v17; // zf
  JET_COLUMNID v18; // edi
  HLOCAL v19; // rcx
  int v20; // eax
  __int64 result; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // eax
  unsigned int v26; // eax
  int v27; // r8d
  unsigned int v28; // eax
  int v29; // r8d
  _QWORD *v30; // rcx
  int v31; // edx
  int v32; // eax
  int v33; // r8d
  JET_SESID v34; // rsi
  HLOCAL v35; // rdi
  char v36; // [rsp+30h] [rbp-50h]
  HLOCAL pvData; // [rsp+34h] [rbp-4Ch] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-40h] BYREF
  unsigned int pcbActual; // [rsp+48h] [rbp-38h] BYREF
  _DWORD v40[5]; // [rsp+4Ch] [rbp-34h] BYREF
  int v41; // [rsp+60h] [rbp-20h] BYREF
  __int64 v42; // [rsp+68h] [rbp-18h] BYREF
  int v43; // [rsp+70h] [rbp-10h]

  HIDWORD(pvData) = a2;
  v36 = 0;
  v40[0] = 0;
  hMem = 0;
  v42 = 0;
  v6 = *(_QWORD *)DhcpGlobalClientTable;
  v7 = a3;
  v43 = 0;
  v41 = 0;
  *(_QWORD *)&v40[1] = 0;
  CurrentFailoverClientInfo = DhcpJetPrepareUpdate(v6, (char *)&pvData + 4, a3, 0);
  if ( CurrentFailoverClientInfo )
    goto LABEL_76;
  if ( v7 == 1 || a4 == 1 )
  {
    v40[0] = 1;
    Value = DhcpDALJetGetValue(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableHandle,
              *(_DWORD *)(DhcpGlobalClientTable + 312),
              (__int64)v40);
    CurrentFailoverClientInfo = Value;
    if ( Value )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        v11 = 120;
LABEL_8:
        v12 = Value;
LABEL_9:
        WPP_SF_D(v10[2], v11, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, v12);
        goto LABEL_76;
      }
      goto LABEL_76;
    }
    v13 = 0;
    if ( v7 )
    {
      v13 = 1;
      v36 = 1;
    }
    if ( a4 )
      v36 = v13 | 2;
    CurrentFailoverClientInfo = DhcpMarkFailoverLease(*(_DWORD *)(DhcpGlobalClientTable + 312));
    if ( CurrentFailoverClientInfo )
      goto LABEL_76;
  }
  EnterCriticalSection(g_FailoverEndpoints);
  v14 = FSMGetElement(*(_QWORD *)(a1 + 4352), &v40[1], &v41);
  CurrentFailoverClientInfo = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, v14);
    LeaveCriticalSection(g_FailoverEndpoints);
    goto LABEL_76;
  }
  v15 = *(__int64 **)&v40[1];
  AcquireSRWLockShared((PSRWLOCK)(*(_QWORD *)&v40[1] + 72LL));
  v16 = *((_DWORD *)v15 + 40);
  ReleaseSRWLockShared((PSRWLOCK)v15 + 9);
  LeaveCriticalSection(g_FailoverEndpoints);
  v17 = v16 == 0;
  LODWORD(pvData) = 0;
  pcbActual = 4;
  v18 = *(_DWORD *)(DhcpGlobalClientTable + 328);
  if ( v17 )
  {
    CurrentFailoverClientInfo = DhcpJetGetValue(v18, &pvData, &pcbActual);
    if ( !CurrentFailoverClientInfo )
    {
      LODWORD(pvData) = (_DWORD)pvData + 1;
      CurrentFailoverClientInfo = DhcpJetSetValue(v18, &pvData, 4u);
    }
    if ( !CurrentFailoverClientInfo )
    {
      CurrentFailoverClientInfo = DhcpJetCommitUpdate();
      v25 = *(_DWORD *)(a1 + 4308);
      if ( v25 != 5 && (!*(_DWORD *)&gFailoverEnableCommInt || v25 != 4) )
        goto LABEL_76;
      if ( v7 != 1 )
        goto LABEL_76;
      if ( CurrentFailoverClientInfo )
        goto LABEL_76;
      CurrentFailoverClientInfo = DhcpGetCurrentFailoverClientInfo(&hMem, 0, 0, 0, 1);
      if ( CurrentFailoverClientInfo )
        goto LABEL_76;
      v26 = DhcpDALJetBeginTransaction(DhcpGlobalJetServerSession);
      CurrentFailoverClientInfo = v26;
      if ( v26 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          WPP_SF_dSl(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, v27, HIDWORD(pvData), *(_QWORD *)(a1 + 4352), v26);
        }
        goto LABEL_76;
      }
      v28 = JetDelete(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
      CurrentFailoverClientInfo = DhcpDALMapJetError(v28, "DhcpDALJetDeleteCurrentRecord");
      if ( CurrentFailoverClientInfo )
      {
        DhcpDALJetRollback(DhcpGlobalJetServerSession);
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_76;
        }
        v31 = 126;
      }
      else
      {
        v32 = DhcpReleaseAddress(HIDWORD(pvData));
        if ( v32
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          WPP_SF_dSl(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, v33, HIDWORD(pvData), *(_QWORD *)(a1 + 4352), v32);
        }
        v34 = DhcpGlobalJetServerSession;
        LODWORD(v42) = HIDWORD(pvData);
        LOBYTE(v43) = *((_BYTE *)hMem + 73);
        HIDWORD(v42) = *((_DWORD *)hMem + 27);
        BYTE1(v43) = v36;
        *(_QWORD *)&v40[1] = &v42;
        *(_QWORD *)&v40[3] = 0x100000004LL;
        CurrentFailoverClientInfo = DhcpDALJetOpenKey(DhcpGlobalJetServerSession, DeletedAddressTableHandle, 1);
        if ( (CurrentFailoverClientInfo & 0xFFFFFFFD) == 0 )
          CurrentFailoverClientInfo = FailoverDeletedAddressSetConfig(v34);
        if ( !CurrentFailoverClientInfo )
        {
          DhcpDALJetCommitTransaction(DhcpGlobalJetServerSession);
          goto LABEL_76;
        }
        DhcpDALJetRollback(DhcpGlobalJetServerSession);
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_76;
        }
        v31 = 128;
      }
      WPP_SF_dSl(v30[2], v31, v29, HIDWORD(pvData), *(_QWORD *)(a1 + 4352), CurrentFailoverClientInfo);
      goto LABEL_76;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_76;
    v11 = 124;
LABEL_27:
    v12 = CurrentFailoverClientInfo;
    goto LABEL_9;
  }
  CurrentFailoverClientInfo = DhcpJetGetValue(v18, &pvData, &pcbActual);
  if ( !CurrentFailoverClientInfo )
  {
    LODWORD(pvData) = (_DWORD)pvData + 1;
    CurrentFailoverClientInfo = DhcpJetSetValue(v18, &pvData, 4u);
  }
  if ( CurrentFailoverClientInfo )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_76;
    v11 = 122;
    goto LABEL_27;
  }
  Value = DhcpJetCommitUpdate();
  CurrentFailoverClientInfo = Value;
  if ( Value )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v11 = 123;
      goto LABEL_8;
    }
LABEL_76:
    v35 = hMem;
    if ( hMem )
    {
      fgs__DHCP_CLIENT_INFO_FO_EX(hMem);
      LocalFree(v35);
    }
    return CurrentFailoverClientInfo;
  }
  CurrentFailoverClientInfo = DhcpGetCurrentFailoverClientInfo(&hMem, 0, 0, 0, 1);
  if ( CurrentFailoverClientInfo )
    goto LABEL_76;
  v19 = hMem;
  if ( (*((_DWORD *)hMem + 10) != -1 || *((_DWORD *)hMem + 11) != 0x7FFFFFFF)
    && (*((_DWORD *)hMem + 10) || *((_DWORD *)hMem + 11)) )
  {
    v20 = DhcpCalculateUTCTime((char *)hMem + 40);
    *((_DWORD *)hMem + 10) = v20;
    *((_DWORD *)hMem + 11) = 0;
    v19 = hMem;
  }
  result = DhcpBNDInsertInDbBndQ(v19, 0, v15);
  if ( (_DWORD)result )
  {
    if ( *((_DWORD *)v15 + 2) )
      v22 = v15[3];
    else
      v22 = v15[4];
    v23 = *v15;
    v24 = *(unsigned int *)hMem;
    *(_OWORD *)&v40[1] = FailoverClientLeaseDropped;
    LogETWFailoverAdminEvent(&v40[1], v22, v23, v24, 0, 0);
    _InterlockedIncrement(&DhcpGlobalFailoverDroppedLeases);
    LocalFree(hMem);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000d97c  mov     [rsp-28h+arg_10], rbx
0x18000d981  mov     [rsp-28h+arg_18], rsi
0x18000d986  push    rbp
0x18000d987  push    rdi
0x18000d988  push    r12
0x18000d98a  push    r13
0x18000d98c  push    r15
0x18000d98e  mov     rbp, rsp
0x18000d991  sub     rsp, 80h
0x18000d998  mov     rax, cs:__security_cookie
0x18000d99f  xor     rax, rsp
0x18000d9a2  mov     [rbp+var_8], rax
0x18000d9a6  xor     r13d, r13d
0x18000d9a9  mov     [rbp+var_48], edx
0x18000d9ac  mov     r15, rcx
0x18000d9af  mov     [rbp+var_50], r13b
0x18000d9b3  mov     rcx, cs:DhcpGlobalClientTable
0x18000d9ba  lea     rdx, [rbp+var_48]
0x18000d9be  xor     eax, eax
0x18000d9c0  mov     dword ptr [rbp+var_34], r13d
0x18000d9c4  mov     edi, r9d
0x18000d9c7  mov     [rbp+hMem], r13
0x18000d9cb  xor     r9d, r9d
0x18000d9ce  mov     [rbp+var_18], rax
0x18000d9d2  mov     rcx, [rcx]
0x18000d9d5  mov     r12d, r8d
0x18000d9d8  mov     [rbp+var_10], eax
0x18000d9db  mov     [rbp+var_20], r13d
0x18000d9df  mov     qword ptr [rbp+var_34+4], r13
0x18000d9e3  call    DhcpJetPrepareUpdate
0x18000d9e8  mov     ebx, eax
0x18000d9ea  test    eax, eax
0x18000d9ec  jnz     loc_18000DF46
0x18000d9f2  lea     esi, [rax+1]
0x18000d9f5  cmp     r12d, esi
0x18000d9f8  jz      short loc_18000DA02
0x18000d9fa  cmp     edi, esi
0x18000d9fc  jnz     loc_18000DAAE
0x18000da02  mov     r8, cs:DhcpGlobalClientTable
0x18000da09  lea     rax, [rbp+var_34]
0x18000da0d  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000da14  lea     r9, [rbp+var_50]
0x18000da18  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000da1f  mov     dword ptr [rbp+var_34], esi
0x18000da22  mov     r8d, [r8+138h]; columnid
0x18000da29  mov     [rsp+80h+var_60], rax; __int64
0x18000da2e  call    DhcpDALJetGetValue
0x18000da33  mov     ebx, eax
0x18000da35  test    eax, eax
0x18000da37  jz      short loc_18000DA7A
0x18000da39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da40  lea     rdi, WPP_GLOBAL_Control
0x18000da47  cmp     rcx, rdi
0x18000da4a  jz      loc_18000DF46
0x18000da50  test    dword ptr [rcx+1Ch], 800000h
0x18000da57  jz      loc_18000DF46
0x18000da5d  mov     edx, 78h ; 'x'
0x18000da62  mov     r9d, eax
0x18000da65  mov     rcx, [rcx+10h]
0x18000da69  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000da70  call    WPP_SF_D
0x18000da75  jmp     loc_18000DF46
0x18000da7a  mov     dl, [rbp+var_50]
0x18000da7d  test    r12d, r12d
0x18000da80  jz      short loc_18000DA88
0x18000da82  or      dl, sil
0x18000da85  mov     [rbp+var_50], dl
0x18000da88  test    edi, edi
0x18000da8a  jz      short loc_18000DA92
0x18000da8c  or      dl, 2
0x18000da8f  mov     [rbp+var_50], dl
0x18000da92  mov     rcx, cs:DhcpGlobalClientTable
0x18000da99  mov     ecx, [rcx+138h]; columnid
0x18000da9f  call    DhcpMarkFailoverLease
0x18000daa4  mov     ebx, eax
0x18000daa6  test    eax, eax
0x18000daa8  jnz     loc_18000DF46
0x18000daae  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x18000dab5  call    cs:__imp_EnterCriticalSection
0x18000dabc  nop     dword ptr [rax+rax+00h]
0x18000dac1  mov     rcx, [r15+1100h]
0x18000dac8  lea     r8, [rbp+var_20]
0x18000dacc  lea     rdx, [rbp+var_34+4]
0x18000dad0  call    FSMGetElement
0x18000dad5  mov     ebx, eax
0x18000dad7  test    eax, eax
0x18000dad9  jz      short loc_18000DB24
0x18000dadb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dae2  lea     rdi, WPP_GLOBAL_Control
0x18000dae9  cmp     rcx, rdi
0x18000daec  jz      short loc_18000DB0C
0x18000daee  test    byte ptr [rcx+1Ch], 10h
0x18000daf2  jz      short loc_18000DB0C
0x18000daf4  mov     rcx, [rcx+10h]
0x18000daf8  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000daff  mov     edx, 79h ; 'y'
0x18000db04  mov     r9d, eax
0x18000db07  call    WPP_SF_D
0x18000db0c  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x18000db13  call    cs:__imp_LeaveCriticalSection
0x18000db1a  nop     dword ptr [rax+rax+00h]
0x18000db1f  jmp     loc_18000DF46
0x18000db24  mov     rsi, qword ptr [rbp+var_34+4]
0x18000db28  lea     rcx, [rsi+48h]; SRWLock
0x18000db2c  call    cs:__imp_AcquireSRWLockShared
0x18000db33  nop     dword ptr [rax+rax+00h]
0x18000db38  mov     edi, [rsi+0A0h]
0x18000db3e  lea     rcx, [rsi+48h]; SRWLock
0x18000db42  call    cs:__imp_ReleaseSRWLockShared
0x18000db49  nop     dword ptr [rax+rax+00h]
0x18000db4e  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x18000db55  call    cs:__imp_LeaveCriticalSection
0x18000db5c  nop     dword ptr [rax+rax+00h]
0x18000db61  mov     rax, cs:DhcpGlobalClientTable
0x18000db68  lea     r8, [rbp+pcbActual]; pcbActual
0x18000db6c  test    edi, edi
0x18000db6e  mov     [rbp+pvData], r13d
0x18000db72  mov     [rbp+pcbActual], 4
0x18000db79  lea     rdx, [rbp+pvData]; pvData
0x18000db7d  mov     edi, [rax+148h]
0x18000db83  mov     ecx, edi; columnid
0x18000db85  jz      loc_18000DCDB
0x18000db8b  call    DhcpJetGetValue
0x18000db90  mov     ebx, eax
0x18000db92  test    eax, eax
0x18000db94  jnz     short loc_18000DBAA
0x18000db96  inc     [rbp+pvData]
0x18000db99  lea     r8d, [rax+4]; cbData
0x18000db9d  lea     rdx, [rbp+pvData]; pvData
0x18000dba1  mov     ecx, edi; columnid
0x18000dba3  call    DhcpJetSetValue
0x18000dba8  mov     ebx, eax
0x18000dbaa  test    ebx, ebx
0x18000dbac  jz      short loc_18000DBDC
0x18000dbae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbb5  lea     rdi, WPP_GLOBAL_Control
0x18000dbbc  cmp     rcx, rdi
0x18000dbbf  jz      loc_18000DF46
0x18000dbc5  test    byte ptr [rcx+1Ch], 10h
0x18000dbc9  jz      loc_18000DF46
0x18000dbcf  mov     edx, 7Ah ; 'z'
0x18000dbd4  mov     r9d, ebx
0x18000dbd7  jmp     loc_18000DA65
0x18000dbdc  call    DhcpJetCommitUpdate
0x18000dbe1  mov     ebx, eax
0x18000dbe3  test    eax, eax
0x18000dbe5  jz      short loc_18000DC12
0x18000dbe7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbee  lea     rdi, WPP_GLOBAL_Control
0x18000dbf5  cmp     rcx, rdi
0x18000dbf8  jz      loc_18000DF46
0x18000dbfe  test    byte ptr [rcx+1Ch], 10h
0x18000dc02  jz      loc_18000DF46
0x18000dc08  mov     edx, 7Bh ; '{'
0x18000dc0d  jmp     loc_18000DA62
0x18000dc12  xor     r9d, r9d
0x18000dc15  mov     dword ptr [rsp+80h+var_60], 1
0x18000dc1d  xor     r8d, r8d
0x18000dc20  lea     rcx, [rbp+hMem]
0x18000dc24  xor     edx, edx
0x18000dc26  call    DhcpGetCurrentFailoverClientInfo
0x18000dc2b  mov     ebx, eax
0x18000dc2d  test    eax, eax
0x18000dc2f  jnz     loc_18000DF46
0x18000dc35  mov     rcx, [rbp+hMem]
0x18000dc39  lea     rax, [rcx+28h]
0x18000dc3d  cmp     dword ptr [rax], 0FFFFFFFFh
0x18000dc40  jnz     short loc_18000DC4B
0x18000dc42  cmp     dword ptr [rcx+2Ch], 7FFFFFFFh
0x18000dc49  jz      short loc_18000DC71
0x18000dc4b  cmp     [rax], r13d
0x18000dc4e  jnz     short loc_18000DC56
0x18000dc50  cmp     [rcx+2Ch], r13d
0x18000dc54  jz      short loc_18000DC71
0x18000dc56  mov     rcx, rax
0x18000dc59  call    DhcpCalculateUTCTime
0x18000dc5e  mov     rcx, [rbp+hMem]
0x18000dc62  mov     [rcx+28h], eax
0x18000dc65  mov     rax, [rbp+hMem]
0x18000dc69  mov     [rax+2Ch], r13d
0x18000dc6d  mov     rcx, [rbp+hMem]
0x18000dc71  mov     r8, rsi
0x18000dc74  xor     edx, edx
0x18000dc76  call    DhcpBNDInsertInDbBndQ
0x18000dc7b  test    eax, eax
0x18000dc7d  jz      loc_18000DF68
0x18000dc83  cmp     [rsi+8], r13d
0x18000dc87  jnz     short loc_18000DC8F
0x18000dc89  mov     rdx, [rsi+20h]
0x18000dc8d  jmp     short loc_18000DC93
0x18000dc8f  mov     rdx, [rsi+18h]
0x18000dc93  mov     r9, [rbp+hMem]
0x18000dc97  lea     rcx, [rbp+var_34+4]
0x18000dc9b  movups  xmm0, cs:FailoverClientLeaseDropped
0x18000dca2  mov     r8, [rsi]
0x18000dca5  mov     [rsp+80h+var_58], r13
0x18000dcaa  mov     r9d, [r9]
0x18000dcad  movdqu  xmmword ptr [rbp+var_34+4], xmm0
0x18000dcb2  mov     [rsp+80h+var_60], r13
0x18000dcb7  call    LogETWFailoverAdminEvent
0x18000dcbc  lock inc cs:DhcpGlobalFailoverDroppedLeases
0x18000dcc3  mov     rcx, [rbp+hMem]; hMem
0x18000dcc7  call    cs:__imp_LocalFree
0x18000dcce  nop     dword ptr [rax+rax+00h]
0x18000dcd3  mov     eax, r13d
0x18000dcd6  jmp     loc_18000DF68
0x18000dcdb  call    DhcpJetGetValue
0x18000dce0  mov     ebx, eax
0x18000dce2  test    eax, eax
0x18000dce4  jnz     short loc_18000DCFA
0x18000dce6  inc     [rbp+pvData]
0x18000dce9  lea     r8d, [rax+4]; cbData
0x18000dced  lea     rdx, [rbp+pvData]; pvData
0x18000dcf1  mov     ecx, edi; columnid
0x18000dcf3  call    DhcpJetSetValue
0x18000dcf8  mov     ebx, eax
0x18000dcfa  test    ebx, ebx
0x18000dcfc  jz      short loc_18000DD29
0x18000dcfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd05  lea     rdi, WPP_GLOBAL_Control
0x18000dd0c  cmp     rcx, rdi
0x18000dd0f  jz      loc_18000DF46
0x18000dd15  test    byte ptr [rcx+1Ch], 10h
0x18000dd19  jz      loc_18000DF46
0x18000dd1f  mov     edx, 7Ch ; '|'
0x18000dd24  jmp     loc_18000DBD4
0x18000dd29  call    DhcpJetCommitUpdate
0x18000dd2e  mov     ebx, eax
0x18000dd30  mov     eax, [r15+10D4h]
0x18000dd37  cmp     eax, 5
0x18000dd3a  jz      short loc_18000DD52
0x18000dd3c  cmp     cs:gFailoverEnableCommInt, r13d
0x18000dd43  jz      loc_18000DF46
0x18000dd49  cmp     eax, 4
0x18000dd4c  jnz     loc_18000DF46
0x18000dd52  cmp     r12d, 1
0x18000dd56  jnz     loc_18000DF46
0x18000dd5c  test    ebx, ebx
0x18000dd5e  jnz     loc_18000DF46
0x18000dd64  xor     r9d, r9d
0x18000dd67  mov     dword ptr [rsp+80h+var_60], r12d
0x18000dd6c  xor     r8d, r8d
0x18000dd6f  lea     rcx, [rbp+hMem]
0x18000dd73  xor     edx, edx
0x18000dd75  call    DhcpGetCurrentFailoverClientInfo
0x18000dd7a  mov     ebx, eax
0x18000dd7c  test    eax, eax
0x18000dd7e  jnz     loc_18000DF46
0x18000dd84  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000dd8b  call    DhcpDALJetBeginTransaction
0x18000dd90  mov     ebx, eax
0x18000dd92  test    eax, eax
0x18000dd94  jz      short loc_18000DDE1
0x18000dd96  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd9d  lea     rdi, WPP_GLOBAL_Control
0x18000dda4  cmp     rcx, rdi
0x18000dda7  jz      loc_18000DF46
0x18000ddad  test    dword ptr [rcx+1Ch], 800000h
0x18000ddb4  jz      loc_18000DF46
0x18000ddba  lea     edx, [r12+7Ch]
0x18000ddbf  mov     dword ptr [rsp+80h+var_58], eax
0x18000ddc3  mov     rax, [r15+1100h]
0x18000ddca  mov     r9d, [rbp+var_48]
0x18000ddce  mov     rcx, [rcx+10h]
0x18000ddd2  mov     [rsp+80h+var_60], rax
0x18000ddd7  call    WPP_SF_dSl
0x18000dddc  jmp     loc_18000DF46
0x18000dde1  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000dde8  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000ddef  call    cs:__imp_JetDelete
0x18000ddf6  nop     dword ptr [rax+rax+00h]
0x18000ddfb  mov     ecx, eax
0x18000ddfd  lea     rdx, aDhcpdaljetdele; "DhcpDALJetDeleteCurrentRecord"
0x18000de04  call    DhcpDALMapJetError
0x18000de09  mov     ebx, eax
0x18000de0b  test    eax, eax
0x18000de0d  jz      short loc_18000DE4D
0x18000de0f  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000de16  call    DhcpDALJetRollback
0x18000de1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de22  lea     rdi, WPP_GLOBAL_Control
0x18000de29  cmp     rcx, rdi
0x18000de2c  jz      loc_18000DF46
0x18000de32  test    dword ptr [rcx+1Ch], 800000h
0x18000de39  jz      loc_18000DF46
0x18000de3f  mov     edx, 7Eh ; '~'
0x18000de44  mov     dword ptr [rsp+80h+var_58], ebx
0x18000de48  jmp     loc_18000DDC3
0x18000de4d  mov     ecx, [rbp+var_48]
0x18000de50  call    DhcpReleaseAddress
0x18000de55  lea     rdi, WPP_GLOBAL_Control
0x18000de5c  test    eax, eax
0x18000de5e  jz      short loc_18000DE97
0x18000de60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de67  cmp     rcx, rdi
0x18000de6a  jz      short loc_18000DE97
0x18000de6c  test    dword ptr [rcx+1Ch], 800000h
0x18000de73  jz      short loc_18000DE97
0x18000de75  mov     r9d, [rbp+var_48]
0x18000de79  mov     edx, 7Fh
  ... truncated ...
```
