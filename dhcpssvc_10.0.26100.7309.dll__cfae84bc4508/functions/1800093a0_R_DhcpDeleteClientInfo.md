# R_DhcpDeleteClientInfo

- ea: `0x1800093a0`
- end: `0x180009b97`
- name: `R_DhcpDeleteClientInfo`
- size: `2039`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004a744`

## callees

- `0x180002040`
- `0x180002854`
- `0x18000323c`
- `0x180003c9c`
- `0x1800058cc`
- `0x180006250`
- `0x1800093a0`
- `0x18000c180`
- `0x18000d97c`
- `0x18000eaf4`
- `0x18000eb24`
- `0x18000eb58`
- `0x18000ebd4`
- `0x18000ed88`
- `0x18000ef84`
- `0x18000f0c4`
- `0x18000f144`
- `0x18000f2ac`
- `0x180010360`
- `0x180020bb4`
- `0x180025b98`
- `0x180031918`
- `0x180031e80`
- `0x180031ed0`
- `0x18008f3f0`
- `0x1800930bc`
- `0x18009877c`
- `0x1800cd010`

## import_xrefs

- `ESENT!JetDelete` at `0x180009a80`
- `ESENT!JetDelete` at `0x180009a80`
- `WS2_32!__imp_inet_ntoa` at `0x18000970f`
- `WS2_32!__imp_inet_ntoa` at `0x18000970f`
- `KERNEL32!LocalFree` at `0x180009acd`
- `KERNEL32!LocalFree` at `0x180009acd`
- `KERNEL32!EnterCriticalSection` at `0x1800093f5`
- `KERNEL32!EnterCriticalSection` at `0x1800093f5`
- `KERNEL32!LeaveCriticalSection` at `0x180009ab7`
- `KERNEL32!LeaveCriticalSection` at `0x180009ab7`

## string_xrefs

- `0x180009a8e`: `DeleteClientInfo:Delete`

## pseudocode

```c
__int64 __fastcall R_DhcpDeleteClientInfo(__int64 a1, __int64 a2)
{
  int v3; // r13d
  int v4; // r12d
  __int64 result; // rax
  unsigned int Value; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  int String; // eax
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  char *v17; // rax
  __int64 v18; // r8
  char *v19; // rax
  __int64 v20; // r14
  int v21; // eax
  __int64 v22; // r8
  unsigned int updated; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  unsigned int v27; // eax
  __int64 v28; // r8
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 in; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v32[4]; // [rsp+38h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-40h] BYREF
  __int64 v34; // [rsp+50h] [rbp-38h] BYREF
  __int64 v35; // [rsp+A0h] [rbp+18h] BYREF
  __int64 pvData; // [rsp+A8h] [rbp+20h] BYREF

  in = 0;
  hMem = 0;
  v32[0] = 0;
  v3 = 0;
  LOBYTE(pvData) = 0;
  LOBYTE(v35) = 0;
  v4 = 0;
  v34 = 0;
  result = DhcpApiAccessCheck(0xA0000000);
  if ( (_DWORD)result )
    return result;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  Value = DhcpJetBeginTransaction();
  if ( Value )
    goto LABEL_115;
  v3 = 1;
  switch ( *(_DWORD *)a2 )
  {
    case 0:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v11 = DhcpIpAddressToDottedString(*(unsigned int *)(a2 + 8));
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, v11);
      }
      v7 = a2 + 8;
      v9 = 4;
      v10 = *(_QWORD *)DhcpGlobalClientTable;
      goto LABEL_23;
    case 1:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids);
      v9 = *(unsigned int *)(a2 + 8);
      v7 = *(_QWORD *)(a2 + 16);
      v10 = *(_QWORD *)(DhcpGlobalClientTable + 16);
LABEL_23:
      Value = DhcpJetOpenKey(v10, v7, v9);
      break;
    case 2:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids,
          *(_QWORD *)(a2 + 8));
      v7 = *(_QWORD *)(a2 + 8);
      if ( !v7 )
      {
        Value = 87;
LABEL_116:
        if ( v3 == 1 )
          DhcpJetRollBack();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, Value);
        goto LABEL_102;
      }
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(v7 + 2 * v8) );
      v9 = (unsigned int)(2 * v8 + 2);
      v10 = *(_QWORD *)(DhcpGlobalClientTable + 64);
      goto LABEL_23;
  }
  if ( Value )
    goto LABEL_116;
  HIDWORD(in) = 4;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 8), &in, (unsigned int *)&in + 1);
  if ( Value )
    goto LABEL_115;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &hMem, v32);
  if ( Value )
    goto LABEL_115;
  if ( (unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, (unsigned int)in) )
  {
    Value = 20019;
    goto LABEL_116;
  }
  HIDWORD(in) = 1;
  if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 152), &pvData, (unsigned int *)&in + 1) )
    LOBYTE(pvData) = 1;
  HIDWORD(in) = 1;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), &v35, (unsigned int *)&in + 1);
  if ( Value )
    goto LABEL_115;
  String = GetString(1083, v12, v13);
  DhcpUpdateAuditLog(16, String, in, (_DWORD)hMem, v32[0], 0);
  v15 = in & DhcpGetSubnetMaskForAddress((unsigned int)in);
  v32[1] = v15;
  v16 = v32[0];
  if ( v32[0] > 4 && v15 == *(_DWORD *)hMem )
  {
    v17 = (char *)hMem + 4;
    v16 = v32[0] - 4;
  }
  else
  {
    v17 = (char *)hMem;
  }
  v18 = v16 - 1;
  if ( !v16 )
    v18 = 0;
  if ( qword_180155858 )
    qword_180155858((unsigned int)in, (unsigned __int64)(v17 + 1) & -(__int64)(v16 != 0), v18, 0, 0);
  MemServerGetUAddressInfo((_DWORD)DhcpGlobalThisServer, v15, (unsigned int)&v34, 0, 0, 0);
  if ( (v35 & 0x80u) != 0LL )
  {
    DhcpDoDynDnsCheckDelete((struct in_addr)in);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v19 = inet_ntoa((struct in_addr)in);
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, v19);
    }
    v4 = 1;
    Value = 0;
    v20 = v34;
    goto LABEL_99;
  }
  v21 = DhcpDoDynDnsCheckDelete((struct in_addr)in);
  v20 = v34;
  if ( v21 )
  {
    if ( !v34 || !*(_DWORD *)(v34 + 4292) )
    {
      v30 = JetDelete(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
      Value = DhcpMapJetError(v30, "DeleteClientInfo:Delete");
      if ( Value )
        goto LABEL_115;
      goto LABEL_99;
    }
    updated = DhcpUpdateClientTransactionTime((unsigned int)in);
    Value = updated;
    if ( updated )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_115;
      }
      v25 = 62;
      goto LABEL_53;
    }
    if ( (unsigned int)(*(_DWORD *)(v20 + 4308) - 4) <= 1 )
    {
      updated = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &in, v28, 0);
      Value = updated;
      if ( updated )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_115;
        v25 = 63;
        goto LABEL_53;
      }
      v29 = DhcpMarkFailoverLease(*(_DWORD *)(DhcpGlobalClientTable + 312));
      if ( v29
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, v29);
      }
      updated = DhcpJetCommitUpdate();
      Value = updated;
      if ( updated )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_115;
        v25 = 65;
        goto LABEL_53;
      }
    }
    Value = DhcpHandleFailoverRequest(v20, (unsigned int)in, 1, (v35 & 3) != 2);
    if ( Value )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_115;
      }
      v25 = 66;
      goto LABEL_71;
    }
  }
  else
  {
    if ( !v34 || *(_DWORD *)(v34 + 4292) != 1 )
    {
      Value = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids);
      }
      goto LABEL_99;
    }
    if ( (unsigned int)(*(_DWORD *)(v34 + 4308) - 4) <= 1 )
    {
      updated = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &in, v22, 0);
      Value = updated;
      if ( updated )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_115;
        v25 = 56;
LABEL_53:
        v26 = updated;
LABEL_54:
        WPP_SF_D(v24[2], v25, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, v26);
        goto LABEL_115;
      }
      v27 = DhcpMarkFailoverLease(*(_DWORD *)(DhcpGlobalClientTable + 312));
      if ( v27
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, v27);
      }
      updated = DhcpJetCommitUpdate();
      Value = updated;
      if ( updated )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_115;
        v25 = 58;
        goto LABEL_53;
      }
    }
    updated = DhcpUpdateClientTransactionTime((unsigned int)in);
    Value = updated;
    if ( updated )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_115;
      }
      v25 = 59;
      goto LABEL_53;
    }
    Value = DhcpHandleFailoverRequest(v20, (unsigned int)in, 0, (v35 & 3) != 2);
    if ( Value )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_115;
      }
      v25 = 60;
LABEL_71:
      v26 = Value;
      goto LABEL_54;
    }
  }
LABEL_99:
  if ( v4 )
  {
    Value = 0;
    goto LABEL_101;
  }
  if ( !v20 || *(_DWORD *)(v20 + 4292) != 1 )
  {
    if ( (_BYTE)pvData == 2 )
    {
      Value = DhcpReleaseBootpAddress((unsigned int)in);
      if ( Value )
        DhcpReleaseAddress((unsigned int)in);
    }
    else
    {
      Value = DhcpReleaseAddress((unsigned int)in);
      if ( Value )
        DhcpReleaseBootpAddress((unsigned int)in);
    }
    if ( Value == 2 )
      Value = 0;
  }
LABEL_115:
  if ( Value )
    goto LABEL_116;
LABEL_101:
  DhcpJetCommitTransaction();
LABEL_102:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( hMem )
    LocalFree(hMem);
  return Value;
}

```

## disassembly

```asm
0x1800093a0  mov     rax, rsp
0x1800093a3  mov     [rax+8], rbx
0x1800093a7  mov     [rax+10h], rsi
0x1800093ab  push    rdi
0x1800093ac  push    r12
0x1800093ae  push    r13
0x1800093b0  push    r14
0x1800093b2  push    r15
0x1800093b4  sub     rsp, 60h
0x1800093b8  mov     r14, rdx
0x1800093bb  xor     edi, edi
0x1800093bd  mov     [rax-58h], edi
0x1800093c0  mov     [rax-54h], edi
0x1800093c3  mov     [rax-40h], rdi
0x1800093c7  mov     [rax-50h], edi
0x1800093ca  mov     r13d, edi
0x1800093cd  mov     [rax+20h], dil
0x1800093d1  mov     [rax+18h], dil
0x1800093d5  mov     r12d, edi
0x1800093d8  mov     [rax-38h], rdi
0x1800093dc  mov     ecx, 0A0000000h
0x1800093e1  call    DhcpApiAccessCheck
0x1800093e6  test    eax, eax
0x1800093e8  jnz     loc_180009ADB
0x1800093ee  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800093f5  call    cs:__imp_EnterCriticalSection
0x1800093fc  nop     dword ptr [rax+rax+00h]
0x180009401  call    DhcpJetBeginTransaction
0x180009406  mov     ebx, eax
0x180009408  lea     r15d, [rdi+1]
0x18000940c  test    eax, eax
0x18000940e  jnz     loc_180009B44
0x180009414  mov     r13d, r15d
0x180009417  mov     eax, [r14]
0x18000941a  test    eax, eax
0x18000941c  jz      loc_1800094E8
0x180009422  sub     eax, r15d
0x180009425  jz      short loc_1800094A2
0x180009427  cmp     eax, r15d
0x18000942a  jnz     short loc_180009496
0x18000942c  lea     rsi, WPP_GLOBAL_Control
0x180009433  mov     rcx, cs:WPP_GLOBAL_Control
0x18000943a  cmp     rcx, rsi
0x18000943d  jz      short loc_18000945F
0x18000943f  test    dword ptr [rcx+1Ch], 200h
0x180009446  jz      short loc_18000945F
0x180009448  lea     edx, [rdi+36h]
0x18000944b  mov     r9, [r14+8]
0x18000944f  lea     r8, WPP_804ae326f0e43eade3e1b627638912e9_Traceguids
0x180009456  mov     rcx, [rcx+10h]
0x18000945a  call    WPP_SF_S
0x18000945f  mov     rdx, [r14+8]
0x180009463  test    rdx, rdx
0x180009466  jnz     short loc_180009470
0x180009468  lea     ebx, [rdx+57h]
0x18000946b  jmp     loc_180009B53
0x180009470  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009474  inc     r8
0x180009477  cmp     [rdx+r8*2], di
0x18000947c  jnz     short loc_180009474
0x18000947e  lea     r8d, ds:2[r8*2]
0x180009486  mov     rcx, cs:DhcpGlobalClientTable
0x18000948d  mov     rcx, [rcx+40h]
0x180009491  jmp     loc_180009540
0x180009496  lea     rsi, WPP_GLOBAL_Control
0x18000949d  jmp     loc_180009547
0x1800094a2  lea     rsi, WPP_GLOBAL_Control
0x1800094a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094b0  cmp     rcx, rsi
0x1800094b3  jz      short loc_1800094D3
0x1800094b5  test    dword ptr [rcx+1Ch], 200h
0x1800094bc  jz      short loc_1800094D3
0x1800094be  mov     edx, 35h ; '5'
0x1800094c3  lea     r8, WPP_804ae326f0e43eade3e1b627638912e9_Traceguids
0x1800094ca  mov     rcx, [rcx+10h]
0x1800094ce  call    WPP_SF_
0x1800094d3  mov     r8d, [r14+8]
0x1800094d7  mov     rdx, [r14+10h]
0x1800094db  mov     rcx, cs:DhcpGlobalClientTable
0x1800094e2  mov     rcx, [rcx+10h]
0x1800094e6  jmp     short loc_180009540
0x1800094e8  lea     rsi, WPP_GLOBAL_Control
0x1800094ef  mov     rax, cs:WPP_GLOBAL_Control
0x1800094f6  cmp     rax, rsi
0x1800094f9  jz      short loc_18000952C
0x1800094fb  test    dword ptr [rax+1Ch], 200h
0x180009502  jz      short loc_18000952C
0x180009504  mov     ecx, [r14+8]
0x180009508  call    DhcpIpAddressToDottedString
0x18000950d  mov     r9, rax
0x180009510  mov     edx, 34h ; '4'
0x180009515  lea     r8, WPP_804ae326f0e43eade3e1b627638912e9_Traceguids
0x18000951c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009523  mov     rcx, [rcx+10h]
0x180009527  call    WPP_SF_s
0x18000952c  lea     rdx, [r14+8]
0x180009530  mov     r8d, 4
0x180009536  mov     rcx, cs:DhcpGlobalClientTable
0x18000953d  mov     rcx, [rcx]
0x180009540  call    DhcpJetOpenKey
0x180009545  mov     ebx, eax
0x180009547  test    ebx, ebx
0x180009549  jnz     loc_180009B53
0x18000954f  mov     [rsp+88h+pcbActual], 4
0x180009557  lea     r8, [rsp+88h+pcbActual]; pcbActual
0x18000955c  lea     rdx, [rsp+88h+in]; pvData
0x180009561  mov     rcx, cs:DhcpGlobalClientTable
0x180009568  mov     ecx, [rcx+8]; columnid
0x18000956b  call    DhcpJetGetValue
0x180009570  mov     ebx, eax
0x180009572  test    eax, eax
0x180009574  jnz     loc_180009B4B
0x18000957a  lea     r8, [rsp+88h+var_50]; pcbActual
0x18000957f  lea     rdx, [rsp+88h+hMem]; pvData
0x180009584  mov     rcx, cs:DhcpGlobalClientTable
0x18000958b  mov     ecx, [rcx+18h]; columnid
0x18000958e  call    DhcpJetGetValue
0x180009593  mov     ebx, eax
0x180009595  test    eax, eax
0x180009597  jnz     loc_180009B4B
0x18000959d  mov     edx, dword ptr [rsp+88h+in.S_un]
0x1800095a1  mov     rcx, cs:DhcpGlobalThisServer
0x1800095a8  call    MemServerIsReservedAddress
0x1800095ad  test    eax, eax
0x1800095af  jz      short loc_1800095BB
0x1800095b1  mov     ebx, 4E33h
0x1800095b6  jmp     loc_180009B53
0x1800095bb  mov     [rsp+88h+pcbActual], r15d
0x1800095c0  lea     r8, [rsp+88h+pcbActual]; pcbActual
0x1800095c5  lea     rdx, [rsp+88h+pvData]; pvData
0x1800095cd  mov     rcx, cs:DhcpGlobalClientTable
0x1800095d4  mov     ecx, [rcx+98h]; columnid
0x1800095da  call    DhcpJetGetValue
0x1800095df  test    eax, eax
0x1800095e1  jz      short loc_1800095EB
0x1800095e3  mov     byte ptr [rsp+88h+pvData], r15b
0x1800095eb  mov     [rsp+88h+pcbActual], r15d
0x1800095f0  lea     r8, [rsp+88h+pcbActual]; pcbActual
0x1800095f5  lea     rdx, [rsp+88h+arg_10]; pvData
0x1800095fd  mov     rcx, cs:DhcpGlobalClientTable
0x180009604  mov     ecx, [rcx+28h]; columnid
0x180009607  call    DhcpJetGetValue
0x18000960c  mov     ebx, eax
0x18000960e  test    eax, eax
0x180009610  jnz     loc_180009B4B
0x180009616  mov     ecx, 43Bh
0x18000961b  call    GetString
0x180009620  mov     rdx, rax
0x180009623  mov     [rsp+88h+var_60], rdi
0x180009628  mov     eax, [rsp+88h+var_50]
0x18000962c  mov     dword ptr [rsp+88h+var_68], eax
0x180009630  mov     r9, [rsp+88h+hMem]
0x180009635  mov     r8d, dword ptr [rsp+88h+in.S_un]
0x18000963a  lea     ecx, [rbx+10h]
0x18000963d  call    DhcpUpdateAuditLog
0x180009642  mov     ecx, dword ptr [rsp+88h+in.S_un]
0x180009646  call    DhcpGetSubnetMaskForAddress
0x18000964b  mov     ebx, eax
0x18000964d  and     ebx, dword ptr [rsp+88h+in.S_un]
0x180009651  mov     [rsp+88h+var_4C], ebx
0x180009655  mov     ecx, [rsp+88h+var_50]
0x180009659  cmp     ecx, 4
0x18000965c  jbe     short loc_180009670
0x18000965e  mov     rax, [rsp+88h+hMem]
0x180009663  cmp     ebx, [rax]
0x180009665  jnz     short loc_180009670
0x180009667  add     rax, 4
0x18000966b  add     ecx, 0FFFFFFFCh
0x18000966e  jmp     short loc_180009675
0x180009670  mov     rax, [rsp+88h+hMem]
0x180009675  lea     r8d, [rcx-1]
0x180009679  test    ecx, ecx
0x18000967b  cmovz   r8d, ecx
0x18000967f  inc     rax
0x180009682  neg     ecx
0x180009684  sbb     rdx, rdx
0x180009687  and     rdx, rax
0x18000968a  mov     rax, cs:qword_180155858
0x180009691  test    rax, rax
0x180009694  jz      short loc_1800096A6
0x180009696  mov     dword ptr [rsp+88h+var_68], edi
0x18000969a  xor     r9d, r9d
0x18000969d  mov     ecx, dword ptr [rsp+88h+in.S_un]
0x1800096a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a6  jmp     short loc_1800096C6
0x1800096a8  mov     ecx, eax
0x1800096aa  call    DhcpCalloutLogAV
0x1800096af  xor     edi, edi
0x1800096b1  lea     r15d, [rdi+1]
0x1800096b5  lea     rsi, WPP_GLOBAL_Control
0x1800096bc  mov     ebx, [rsp+88h+var_4C]
0x1800096c0  mov     r13d, r15d
0x1800096c3  mov     r12d, edi
0x1800096c6  mov     [rsp+88h+var_60], rdi
0x1800096cb  mov     [rsp+88h+var_68], rdi
0x1800096d0  xor     r9d, r9d
0x1800096d3  lea     r8, [rsp+88h+var_38]
0x1800096d8  mov     edx, ebx
0x1800096da  mov     rcx, cs:DhcpGlobalThisServer
0x1800096e1  call    MemServerGetUAddressInfo
0x1800096e6  mov     ecx, dword ptr [rsp+88h+in.S_un]
0x1800096ea  test    byte ptr [rsp+88h+arg_10], 80h
0x1800096f2  jz      short loc_180009749
0x1800096f4  call    DhcpDoDynDnsCheckDelete
0x1800096f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009700  cmp     rcx, rsi
0x180009703  jz      short loc_18000973A
0x180009705  test    byte ptr [rcx+1Ch], 10h
0x180009709  jz      short loc_18000973A
0x18000970b  mov     ecx, dword ptr [rsp+88h+in.S_un]; in
0x18000970f  call    cs:__imp_inet_ntoa
0x180009716  nop     dword ptr [rax+rax+00h]
0x18000971b  mov     r9, rax
0x18000971e  mov     edx, 37h ; '7'
0x180009723  lea     r8, WPP_804ae326f0e43eade3e1b627638912e9_Traceguids
0x18000972a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009731  mov     rcx, [rcx+10h]
0x180009735  call    WPP_SF_s
0x18000973a  mov     r12d, r15d
0x18000973d  mov     ebx, edi
0x18000973f  mov     r14, [rsp+88h+var_38]
0x180009744  jmp     loc_180009AA4
0x180009749  call    DhcpDoDynDnsCheckDelete
0x18000974e  mov     r14, [rsp+88h+var_38]
0x180009753  test    eax, eax
0x180009755  jnz     loc_180009910
0x18000975b  test    r14, r14
0x18000975e  jz      loc_1800098D7
0x180009764  cmp     [r14+10C4h], r15d
0x18000976b  jnz     loc_1800098D7
0x180009771  mov     eax, [r14+10D4h]
0x180009778  sub     eax, 4
0x18000977b  cmp     eax, r15d
0x18000977e  ja      loc_180009849
0x180009784  xor     r9d, r9d
0x180009787  lea     rdx, [rsp+88h+in]
0x18000978c  mov     rcx, cs:DhcpGlobalClientTable
0x180009793  mov     rcx, [rcx]
0x180009796  call    DhcpJetPrepareUpdate
0x18000979b  mov     ebx, eax
0x18000979d  test    eax, eax
0x18000979f  jz      short loc_1800097D8
0x1800097a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097a8  cmp     rcx, rsi
0x1800097ab  jz      loc_180009B4B
0x1800097b1  test    byte ptr [rcx+1Ch], 10h
0x1800097b5  jz      loc_180009B4B
0x1800097bb  mov     edx, 38h ; '8'
0x1800097c0  mov     r9d, eax
0x1800097c3  lea     r8, WPP_804ae326f0e43eade3e1b627638912e9_Traceguids
0x1800097ca  mov     rcx, [rcx+10h]
0x1800097ce  call    WPP_SF_D
0x1800097d3  jmp     loc_180009B4B
0x1800097d8  mov     dl, 10h
0x1800097da  mov     rcx, cs:DhcpGlobalClientTable
0x1800097e1  mov     ecx, [rcx+138h]; columnid
0x1800097e7  call    DhcpMarkFailoverLease
0x1800097ec  test    eax, eax
0x1800097ee  jz      short loc_18000981A
0x1800097f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097f7  cmp     rcx, rsi
0x1800097fa  jz      short loc_18000981A
0x1800097fc  test    byte ptr [rcx+1Ch], 10h
0x180009800  jz      short loc_18000981A
0x180009802  mov     edx, 39h ; '9'
0x180009807  mov     r9d, eax
0x18000980a  lea     r8, WPP_804ae326f0e43eade3e1b627638912e9_Traceguids
0x180009811  mov     rcx, [rcx+10h]
0x180009815  call    WPP_SF_D
0x18000981a  call    DhcpJetCommitUpdate
0x18000981f  mov     ebx, eax
0x180009821  test    eax, eax
0x180009823  jz      short loc_180009849
0x180009825  mov     rcx, cs:WPP_GLOBAL_Control
0x18000982c  cmp     rcx, rsi
0x18000982f  jz      loc_180009B4B
0x180009835  test    byte ptr [rcx+1Ch], 10h
0x180009839  jz      loc_180009B4B
0x18000983f  mov     edx, 3Ah ; ':'
0x180009844  jmp     loc_1800097C0
0x180009849  mov     ecx, dword ptr [rsp+88h+in.S_un]
0x18000984d  call    DhcpUpdateClientTransactionTime
0x180009852  mov     ebx, eax
0x180009854  test    eax, eax
0x180009856  jz      short loc_18000987F
0x180009858  mov     rcx, cs:WPP_GLOBAL_Control
0x18000985f  cmp     rcx, rsi
0x180009862  jz      loc_180009B4B
0x180009868  test    dword ptr [rcx+1Ch], 800000h
0x18000986f  jz      loc_180009B4B
0x180009875  mov     edx, 3Bh ; ';'
0x18000987a  jmp     loc_1800097C0
0x18000987f  mov     al, byte ptr [rsp+88h+arg_10]
0x180009886  and     al, 3
0x180009888  xor     r8d, r8d
0x18000988b  mov     edx, dword ptr [rsp+88h+in.S_un]
0x18000988f  mov     rcx, r14
0x180009892  cmp     al, 2
0x180009894  jnz     short loc_18000989B
0x180009896  xor     r9d, r9d
  ... truncated ...
```
