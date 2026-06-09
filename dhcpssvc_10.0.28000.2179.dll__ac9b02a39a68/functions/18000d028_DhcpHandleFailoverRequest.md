# DhcpHandleFailoverRequest

- ea: `0x18000d028`
- end: `0x18000d63d`
- name: `DhcpHandleFailoverRequest`
- size: `1557`
- prototype: ``
- caller_count: `8`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800083cc`
- `0x1800092e0`
- `0x180020fdc`
- `0x1800215c0`
- `0x1800503c8`
- `0x180057cf8`
- `0x180058c00`
- `0x18005a9ec`

## callees

- `0x18000282c`
- `0x180007bf8`
- `0x18000d028`
- `0x18000e204`
- `0x18000e284`
- `0x18000e64c`
- `0x18000e7c0`
- `0x18000e97c`
- `0x180010d98`
- `0x18003147c`
- `0x1800807a0`
- `0x18008f020`
- `0x18009fd18`
- `0x1800a03f0`
- `0x1800a0418`
- `0x1800a05b8`
- `0x1800a0788`
- `0x1800a0b3c`
- `0x1800a0bac`
- `0x1800a9f84`
- `0x1800c0e08`
- `0x1800ca0c8`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetDelete` at `0x18000d49b`
- `ESENT!JetDelete` at `0x18000d49b`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000d1ee`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000d1ee`
- `KERNEL32!AcquireSRWLockShared` at `0x18000d1d8`
- `KERNEL32!AcquireSRWLockShared` at `0x18000d1d8`
- `KERNEL32!LocalFree` at `0x18000d373`
- `KERNEL32!LocalFree` at `0x18000d606`
- `KERNEL32!LocalFree` at `0x18000d373`
- `KERNEL32!LocalFree` at `0x18000d606`
- `KERNEL32!EnterCriticalSection` at `0x18000d161`
- `KERNEL32!EnterCriticalSection` at `0x18000d161`
- `KERNEL32!LeaveCriticalSection` at `0x18000d1bf`
- `KERNEL32!LeaveCriticalSection` at `0x18000d201`
- `KERNEL32!LeaveCriticalSection` at `0x18000d1bf`
- `KERNEL32!LeaveCriticalSection` at `0x18000d201`

## string_xrefs

- `0x18000d4a9`: `DhcpDALJetDeleteCurrentRecord`

## pseudocode

```c
__int64 __fastcall DhcpHandleFailoverRequest(__int64 a1, unsigned int a2, __int64 a3, int a4)
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
  int pvData; // [rsp+34h] [rbp-4Ch] BYREF
  unsigned int v38; // [rsp+38h] [rbp-48h] BYREF
  HLOCAL hMem[2]; // [rsp+40h] [rbp-40h] BYREF
  unsigned int pcbActual[4]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v41; // [rsp+60h] [rbp-20h] BYREF
  __int64 v42; // [rsp+68h] [rbp-18h] BYREF
  int v43; // [rsp+70h] [rbp-10h]

  v38 = a2;
  v36 = 0;
  LODWORD(v41) = 0;
  hMem[0] = 0;
  v42 = 0;
  v6 = *(_QWORD *)DhcpGlobalClientTable;
  v7 = a3;
  v43 = 0;
  pvData = 0;
  *(_QWORD *)pcbActual = 0;
  CurrentFailoverClientInfo = DhcpJetPrepareUpdate(v6, &v38, a3, 0);
  if ( CurrentFailoverClientInfo )
    goto LABEL_76;
  if ( v7 == 1 || a4 == 1 )
  {
    LODWORD(v41) = 1;
    Value = DhcpDALJetGetValue(
              DhcpGlobalJetServerSession,
              DhcpGlobalClientTableHandle,
              *(_DWORD *)(DhcpGlobalClientTable + 312),
              (__int64)&v41);
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
  v14 = FSMGetElement(*(_QWORD *)(a1 + 4352), pcbActual, &pvData);
  CurrentFailoverClientInfo = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, v14);
    LeaveCriticalSection(g_FailoverEndpoints);
    goto LABEL_76;
  }
  v15 = *(__int64 **)pcbActual;
  AcquireSRWLockShared((PSRWLOCK)(*(_QWORD *)pcbActual + 72LL));
  v16 = *((_DWORD *)v15 + 40);
  ReleaseSRWLockShared((PSRWLOCK)v15 + 9);
  LeaveCriticalSection(g_FailoverEndpoints);
  v17 = v16 == 0;
  pvData = 0;
  pcbActual[0] = 4;
  v18 = *(_DWORD *)(DhcpGlobalClientTable + 328);
  if ( v17 )
  {
    CurrentFailoverClientInfo = DhcpJetGetValue(v18, &pvData, pcbActual);
    if ( !CurrentFailoverClientInfo )
    {
      ++pvData;
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
      CurrentFailoverClientInfo = DhcpGetCurrentFailoverClientInfo((unsigned int)hMem, 0, 0, 0, 1);
      if ( CurrentFailoverClientInfo )
        goto LABEL_76;
      v26 = DhcpDALJetBeginTransaction(DhcpGlobalJetServerSession);
      CurrentFailoverClientInfo = v26;
      if ( v26 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          WPP_SF_dSl(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, v27, v38, *(_QWORD *)(a1 + 4352), v26);
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
        v32 = DhcpReleaseAddress(v38);
        if ( v32
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          WPP_SF_dSl(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, v33, v38, *(_QWORD *)(a1 + 4352), v32);
        }
        v34 = DhcpGlobalJetServerSession;
        LODWORD(v42) = v38;
        LOBYTE(v43) = *((_BYTE *)hMem[0] + 73);
        HIDWORD(v42) = *((_DWORD *)hMem[0] + 27);
        BYTE1(v43) = v36;
        *(_QWORD *)pcbActual = &v42;
        pcbActual[2] = 4;
        pcbActual[3] = 1;
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
      WPP_SF_dSl(v30[2], v31, v29, v38, *(_QWORD *)(a1 + 4352), CurrentFailoverClientInfo);
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
  CurrentFailoverClientInfo = DhcpJetGetValue(v18, &pvData, pcbActual);
  if ( !CurrentFailoverClientInfo )
  {
    ++pvData;
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
    v35 = hMem[0];
    if ( hMem[0] )
    {
      fgs__DHCP_CLIENT_INFO_FO_EX(hMem[0]);
      LocalFree(v35);
    }
    return CurrentFailoverClientInfo;
  }
  CurrentFailoverClientInfo = DhcpGetCurrentFailoverClientInfo((unsigned int)hMem, 0, 0, 0, 1);
  if ( CurrentFailoverClientInfo )
    goto LABEL_76;
  v19 = hMem[0];
  if ( (*((_DWORD *)hMem[0] + 10) != -1 || *((_DWORD *)hMem[0] + 11) != 0x7FFFFFFF)
    && (*((_DWORD *)hMem[0] + 10) || *((_DWORD *)hMem[0] + 11)) )
  {
    v20 = DhcpCalculateUTCTime((char *)hMem[0] + 40);
    *((_DWORD *)hMem[0] + 10) = v20;
    *((_DWORD *)hMem[0] + 11) = 0;
    v19 = hMem[0];
  }
  result = DhcpBNDInsertInDbBndQ(v19, 0, v15);
  if ( (_DWORD)result )
  {
    if ( *((_DWORD *)v15 + 2) )
      v22 = v15[3];
    else
      v22 = v15[4];
    v23 = *v15;
    v24 = *(unsigned int *)hMem[0];
    *(_OWORD *)pcbActual = FailoverClientLeaseDropped;
    LogETWFailoverAdminEvent(pcbActual, v22, v23, v24, 0, 0);
    _InterlockedIncrement(&DhcpGlobalFailoverDroppedLeases);
    LocalFree(hMem[0]);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000d028  mov     [rsp-28h+arg_10], rbx
0x18000d02d  mov     [rsp-28h+arg_18], rsi
0x18000d032  push    rbp
0x18000d033  push    rdi
0x18000d034  push    r12
0x18000d036  push    r13
0x18000d038  push    r15
0x18000d03a  mov     rbp, rsp
0x18000d03d  sub     rsp, 80h
0x18000d044  mov     rax, cs:__security_cookie
0x18000d04b  xor     rax, rsp
0x18000d04e  mov     [rbp+var_8], rax
0x18000d052  xor     r13d, r13d
0x18000d055  mov     [rbp+var_48], edx
0x18000d058  mov     r15, rcx
0x18000d05b  mov     [rbp+var_50], r13b
0x18000d05f  mov     rcx, cs:DhcpGlobalClientTable
0x18000d066  lea     rdx, [rbp+var_48]
0x18000d06a  xor     eax, eax
0x18000d06c  mov     dword ptr [rbp+var_20], r13d
0x18000d070  mov     edi, r9d
0x18000d073  mov     [rbp+hMem], r13
0x18000d077  xor     r9d, r9d
0x18000d07a  mov     [rbp+var_18], rax
0x18000d07e  mov     rcx, [rcx]
0x18000d081  mov     r12d, r8d
0x18000d084  mov     [rbp+var_10], eax
0x18000d087  mov     [rbp+pvData], r13d
0x18000d08b  mov     qword ptr [rbp+pcbActual], r13
0x18000d08f  call    DhcpJetPrepareUpdate
0x18000d094  mov     ebx, eax
0x18000d096  test    eax, eax
0x18000d098  jnz     loc_18000D5F2
0x18000d09e  lea     esi, [rax+1]
0x18000d0a1  cmp     r12d, esi
0x18000d0a4  jz      short loc_18000D0AE
0x18000d0a6  cmp     edi, esi
0x18000d0a8  jnz     loc_18000D15A
0x18000d0ae  mov     r8, cs:DhcpGlobalClientTable
0x18000d0b5  lea     rax, [rbp+var_20]
0x18000d0b9  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000d0c0  lea     r9, [rbp+var_50]
0x18000d0c4  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000d0cb  mov     dword ptr [rbp+var_20], esi
0x18000d0ce  mov     r8d, [r8+138h]; columnid
0x18000d0d5  mov     [rsp+80h+var_60], rax; __int64
0x18000d0da  call    DhcpDALJetGetValue
0x18000d0df  mov     ebx, eax
0x18000d0e1  test    eax, eax
0x18000d0e3  jz      short loc_18000D126
0x18000d0e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0ec  lea     rdi, WPP_GLOBAL_Control
0x18000d0f3  cmp     rcx, rdi
0x18000d0f6  jz      loc_18000D5F2
0x18000d0fc  test    dword ptr [rcx+1Ch], 800000h
0x18000d103  jz      loc_18000D5F2
0x18000d109  mov     edx, 78h ; 'x'
0x18000d10e  mov     r9d, eax
0x18000d111  mov     rcx, [rcx+10h]
0x18000d115  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d11c  call    WPP_SF_D
0x18000d121  jmp     loc_18000D5F2
0x18000d126  mov     dl, [rbp+var_50]
0x18000d129  test    r12d, r12d
0x18000d12c  jz      short loc_18000D134
0x18000d12e  or      dl, sil
0x18000d131  mov     [rbp+var_50], dl
0x18000d134  test    edi, edi
0x18000d136  jz      short loc_18000D13E
0x18000d138  or      dl, 2
0x18000d13b  mov     [rbp+var_50], dl
0x18000d13e  mov     rcx, cs:DhcpGlobalClientTable
0x18000d145  mov     ecx, [rcx+138h]; columnid
0x18000d14b  call    DhcpMarkFailoverLease
0x18000d150  mov     ebx, eax
0x18000d152  test    eax, eax
0x18000d154  jnz     loc_18000D5F2
0x18000d15a  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x18000d161  call    cs:__imp_EnterCriticalSection
0x18000d168  nop     dword ptr [rax+rax+00h]
0x18000d16d  mov     rcx, [r15+1100h]
0x18000d174  lea     r8, [rbp+pvData]
0x18000d178  lea     rdx, [rbp+pcbActual]
0x18000d17c  call    FSMGetElement
0x18000d181  mov     ebx, eax
0x18000d183  test    eax, eax
0x18000d185  jz      short loc_18000D1D0
0x18000d187  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d18e  lea     rdi, WPP_GLOBAL_Control
0x18000d195  cmp     rcx, rdi
0x18000d198  jz      short loc_18000D1B8
0x18000d19a  test    byte ptr [rcx+1Ch], 10h
0x18000d19e  jz      short loc_18000D1B8
0x18000d1a0  mov     rcx, [rcx+10h]
0x18000d1a4  lea     r8, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000d1ab  mov     edx, 79h ; 'y'
0x18000d1b0  mov     r9d, eax
0x18000d1b3  call    WPP_SF_D
0x18000d1b8  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x18000d1bf  call    cs:__imp_LeaveCriticalSection
0x18000d1c6  nop     dword ptr [rax+rax+00h]
0x18000d1cb  jmp     loc_18000D5F2
0x18000d1d0  mov     rsi, qword ptr [rbp+pcbActual]
0x18000d1d4  lea     rcx, [rsi+48h]; SRWLock
0x18000d1d8  call    cs:__imp_AcquireSRWLockShared
0x18000d1df  nop     dword ptr [rax+rax+00h]
0x18000d1e4  mov     edi, [rsi+0A0h]
0x18000d1ea  lea     rcx, [rsi+48h]; SRWLock
0x18000d1ee  call    cs:__imp_ReleaseSRWLockShared
0x18000d1f5  nop     dword ptr [rax+rax+00h]
0x18000d1fa  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x18000d201  call    cs:__imp_LeaveCriticalSection
0x18000d208  nop     dword ptr [rax+rax+00h]
0x18000d20d  mov     rax, cs:DhcpGlobalClientTable
0x18000d214  lea     r8, [rbp+pcbActual]; pcbActual
0x18000d218  test    edi, edi
0x18000d21a  mov     [rbp+pvData], r13d
0x18000d21e  mov     [rbp+pcbActual], 4
0x18000d225  lea     rdx, [rbp+pvData]; pvData
0x18000d229  mov     edi, [rax+148h]
0x18000d22f  mov     ecx, edi; columnid
0x18000d231  jz      loc_18000D387
0x18000d237  call    DhcpJetGetValue
0x18000d23c  mov     ebx, eax
0x18000d23e  test    eax, eax
0x18000d240  jnz     short loc_18000D256
0x18000d242  inc     [rbp+pvData]
0x18000d245  lea     r8d, [rax+4]; cbData
0x18000d249  lea     rdx, [rbp+pvData]; pvData
0x18000d24d  mov     ecx, edi; columnid
0x18000d24f  call    DhcpJetSetValue
0x18000d254  mov     ebx, eax
0x18000d256  test    ebx, ebx
0x18000d258  jz      short loc_18000D288
0x18000d25a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d261  lea     rdi, WPP_GLOBAL_Control
0x18000d268  cmp     rcx, rdi
0x18000d26b  jz      loc_18000D5F2
0x18000d271  test    byte ptr [rcx+1Ch], 10h
0x18000d275  jz      loc_18000D5F2
0x18000d27b  mov     edx, 7Ah ; 'z'
0x18000d280  mov     r9d, ebx
0x18000d283  jmp     loc_18000D111
0x18000d288  call    DhcpJetCommitUpdate
0x18000d28d  mov     ebx, eax
0x18000d28f  test    eax, eax
0x18000d291  jz      short loc_18000D2BE
0x18000d293  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d29a  lea     rdi, WPP_GLOBAL_Control
0x18000d2a1  cmp     rcx, rdi
0x18000d2a4  jz      loc_18000D5F2
0x18000d2aa  test    byte ptr [rcx+1Ch], 10h
0x18000d2ae  jz      loc_18000D5F2
0x18000d2b4  mov     edx, 7Bh ; '{'
0x18000d2b9  jmp     loc_18000D10E
0x18000d2be  xor     r9d, r9d
0x18000d2c1  mov     dword ptr [rsp+80h+var_60], 1
0x18000d2c9  xor     r8d, r8d
0x18000d2cc  lea     rcx, [rbp+hMem]
0x18000d2d0  xor     edx, edx
0x18000d2d2  call    DhcpGetCurrentFailoverClientInfo
0x18000d2d7  mov     ebx, eax
0x18000d2d9  test    eax, eax
0x18000d2db  jnz     loc_18000D5F2
0x18000d2e1  mov     rcx, [rbp+hMem]
0x18000d2e5  lea     rax, [rcx+28h]
0x18000d2e9  cmp     dword ptr [rax], 0FFFFFFFFh
0x18000d2ec  jnz     short loc_18000D2F7
0x18000d2ee  cmp     dword ptr [rcx+2Ch], 7FFFFFFFh
0x18000d2f5  jz      short loc_18000D31D
0x18000d2f7  cmp     [rax], r13d
0x18000d2fa  jnz     short loc_18000D302
0x18000d2fc  cmp     [rcx+2Ch], r13d
0x18000d300  jz      short loc_18000D31D
0x18000d302  mov     rcx, rax
0x18000d305  call    DhcpCalculateUTCTime
0x18000d30a  mov     rcx, [rbp+hMem]
0x18000d30e  mov     [rcx+28h], eax
0x18000d311  mov     rax, [rbp+hMem]
0x18000d315  mov     [rax+2Ch], r13d
0x18000d319  mov     rcx, [rbp+hMem]
0x18000d31d  mov     r8, rsi
0x18000d320  xor     edx, edx
0x18000d322  call    DhcpBNDInsertInDbBndQ
0x18000d327  test    eax, eax
0x18000d329  jz      loc_18000D614
0x18000d32f  cmp     [rsi+8], r13d
0x18000d333  jnz     short loc_18000D33B
0x18000d335  mov     rdx, [rsi+20h]
0x18000d339  jmp     short loc_18000D33F
0x18000d33b  mov     rdx, [rsi+18h]
0x18000d33f  mov     r9, [rbp+hMem]
0x18000d343  lea     rcx, [rbp+pcbActual]
0x18000d347  movups  xmm0, cs:FailoverClientLeaseDropped
0x18000d34e  mov     r8, [rsi]
0x18000d351  mov     [rsp+80h+var_58], r13
0x18000d356  mov     r9d, [r9]
0x18000d359  movdqu  xmmword ptr [rbp+pcbActual], xmm0
0x18000d35e  mov     [rsp+80h+var_60], r13
0x18000d363  call    LogETWFailoverAdminEvent
0x18000d368  lock inc cs:DhcpGlobalFailoverDroppedLeases
0x18000d36f  mov     rcx, [rbp+hMem]; hMem
0x18000d373  call    cs:__imp_LocalFree
0x18000d37a  nop     dword ptr [rax+rax+00h]
0x18000d37f  mov     eax, r13d
0x18000d382  jmp     loc_18000D614
0x18000d387  call    DhcpJetGetValue
0x18000d38c  mov     ebx, eax
0x18000d38e  test    eax, eax
0x18000d390  jnz     short loc_18000D3A6
0x18000d392  inc     [rbp+pvData]
0x18000d395  lea     r8d, [rax+4]; cbData
0x18000d399  lea     rdx, [rbp+pvData]; pvData
0x18000d39d  mov     ecx, edi; columnid
0x18000d39f  call    DhcpJetSetValue
0x18000d3a4  mov     ebx, eax
0x18000d3a6  test    ebx, ebx
0x18000d3a8  jz      short loc_18000D3D5
0x18000d3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3b1  lea     rdi, WPP_GLOBAL_Control
0x18000d3b8  cmp     rcx, rdi
0x18000d3bb  jz      loc_18000D5F2
0x18000d3c1  test    byte ptr [rcx+1Ch], 10h
0x18000d3c5  jz      loc_18000D5F2
0x18000d3cb  mov     edx, 7Ch ; '|'
0x18000d3d0  jmp     loc_18000D280
0x18000d3d5  call    DhcpJetCommitUpdate
0x18000d3da  mov     ebx, eax
0x18000d3dc  mov     eax, [r15+10D4h]
0x18000d3e3  cmp     eax, 5
0x18000d3e6  jz      short loc_18000D3FE
0x18000d3e8  cmp     cs:gFailoverEnableCommInt, r13d
0x18000d3ef  jz      loc_18000D5F2
0x18000d3f5  cmp     eax, 4
0x18000d3f8  jnz     loc_18000D5F2
0x18000d3fe  cmp     r12d, 1
0x18000d402  jnz     loc_18000D5F2
0x18000d408  test    ebx, ebx
0x18000d40a  jnz     loc_18000D5F2
0x18000d410  xor     r9d, r9d
0x18000d413  mov     dword ptr [rsp+80h+var_60], r12d
0x18000d418  xor     r8d, r8d
0x18000d41b  lea     rcx, [rbp+hMem]
0x18000d41f  xor     edx, edx
0x18000d421  call    DhcpGetCurrentFailoverClientInfo
0x18000d426  mov     ebx, eax
0x18000d428  test    eax, eax
0x18000d42a  jnz     loc_18000D5F2
0x18000d430  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d437  call    DhcpDALJetBeginTransaction
0x18000d43c  mov     ebx, eax
0x18000d43e  test    eax, eax
0x18000d440  jz      short loc_18000D48D
0x18000d442  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d449  lea     rdi, WPP_GLOBAL_Control
0x18000d450  cmp     rcx, rdi
0x18000d453  jz      loc_18000D5F2
0x18000d459  test    dword ptr [rcx+1Ch], 800000h
0x18000d460  jz      loc_18000D5F2
0x18000d466  lea     edx, [r12+7Ch]
0x18000d46b  mov     dword ptr [rsp+80h+var_58], eax
0x18000d46f  mov     rax, [r15+1100h]
0x18000d476  mov     r9d, [rbp+var_48]
0x18000d47a  mov     rcx, [rcx+10h]
0x18000d47e  mov     [rsp+80h+var_60], rax
0x18000d483  call    WPP_SF_dSl
0x18000d488  jmp     loc_18000D5F2
0x18000d48d  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000d494  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000d49b  call    cs:__imp_JetDelete
0x18000d4a2  nop     dword ptr [rax+rax+00h]
0x18000d4a7  mov     ecx, eax
0x18000d4a9  lea     rdx, aDhcpdaljetdele; "DhcpDALJetDeleteCurrentRecord"
0x18000d4b0  call    DhcpDALMapJetError
0x18000d4b5  mov     ebx, eax
0x18000d4b7  test    eax, eax
0x18000d4b9  jz      short loc_18000D4F9
0x18000d4bb  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000d4c2  call    DhcpDALJetRollback
0x18000d4c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4ce  lea     rdi, WPP_GLOBAL_Control
0x18000d4d5  cmp     rcx, rdi
0x18000d4d8  jz      loc_18000D5F2
0x18000d4de  test    dword ptr [rcx+1Ch], 800000h
0x18000d4e5  jz      loc_18000D5F2
0x18000d4eb  mov     edx, 7Eh ; '~'
0x18000d4f0  mov     dword ptr [rsp+80h+var_58], ebx
0x18000d4f4  jmp     loc_18000D46F
0x18000d4f9  mov     ecx, [rbp+var_48]
0x18000d4fc  call    DhcpReleaseAddress
0x18000d501  lea     rdi, WPP_GLOBAL_Control
0x18000d508  test    eax, eax
0x18000d50a  jz      short loc_18000D543
0x18000d50c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d513  cmp     rcx, rdi
0x18000d516  jz      short loc_18000D543
0x18000d518  test    dword ptr [rcx+1Ch], 800000h
0x18000d51f  jz      short loc_18000D543
0x18000d521  mov     r9d, [rbp+var_48]
0x18000d525  mov     edx, 7Fh
  ... truncated ...
```
