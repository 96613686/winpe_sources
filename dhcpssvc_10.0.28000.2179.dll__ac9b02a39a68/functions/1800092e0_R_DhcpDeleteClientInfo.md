# R_DhcpDeleteClientInfo

- ea: `0x1800092e0`
- end: `0x180009afa`
- name: `R_DhcpDeleteClientInfo`
- size: `2074`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18004a4a4`

## callees

- `0x180002030`
- `0x18000282c`
- `0x180003228`
- `0x180003c90`
- `0x1800058bc`
- `0x180006234`
- `0x1800092e0`
- `0x18000c164`
- `0x18000d028`
- `0x18000e1a0`
- `0x18000e1d0`
- `0x18000e204`
- `0x18000e284`
- `0x18000e450`
- `0x18000e64c`
- `0x18000e78c`
- `0x18000e814`
- `0x18000e97c`
- `0x18000fa40`
- `0x180020094`
- `0x1800250e8`
- `0x180030ed4`
- `0x18003147c`
- `0x1800314cc`
- `0x18008f58c`
- `0x1800932a8`
- `0x180098a40`
- `0x1800cf010`

## import_xrefs

- `ESENT!JetDelete` at `0x1800099d5`
- `ESENT!JetDelete` at `0x1800099d5`
- `WS2_32!__imp_inet_ntoa` at `0x180009661`
- `WS2_32!__imp_inet_ntoa` at `0x180009661`
- `KERNEL32!LocalFree` at `0x180009a29`
- `KERNEL32!LocalFree` at `0x180009a29`
- `KERNEL32!EnterCriticalSection` at `0x180009335`
- `KERNEL32!EnterCriticalSection` at `0x180009335`
- `KERNEL32!LeaveCriticalSection` at `0x180009a13`
- `KERNEL32!LeaveCriticalSection` at `0x180009a13`

## string_xrefs

- `0x1800099e3`: `DeleteClientInfo:Delete`

## pseudocode

```c
__int64 __fastcall R_DhcpDeleteClientInfo(__int64 a1, __int64 a2)
{
  int v3; // r13d
  int v4; // r12d
  __int64 result; // rax
  unsigned int Value; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rax
  int String; // eax
  unsigned int v15; // ebx
  unsigned int v16; // ecx
  char *v17; // rax
  __int64 v18; // r8
  __int64 v19; // rbx
  char *v20; // rax
  __int64 v21; // r14
  int v22; // eax
  __int64 v23; // r8
  int v24; // eax
  unsigned int updated; // eax
  __int64 v26; // rdx
  __int64 v27; // r9
  unsigned int v28; // eax
  __int64 v29; // r8
  int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  struct in_addr in; // [rsp+30h] [rbp-58h] BYREF
  unsigned int pcbActual; // [rsp+34h] [rbp-54h] BYREF
  unsigned int v35[4]; // [rsp+38h] [rbp-50h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-40h] BYREF
  __int64 v37; // [rsp+50h] [rbp-38h] BYREF
  char v38; // [rsp+A0h] [rbp+18h] BYREF
  char pvData; // [rsp+A8h] [rbp+20h] BYREF

  in = 0;
  pcbActual = 0;
  hMem = 0;
  v35[0] = 0;
  v3 = 0;
  pvData = 0;
  v38 = 0;
  v4 = 0;
  v37 = 0;
  result = DhcpApiAccessCheck(0xA0000000);
  if ( (_DWORD)result )
    return result;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  Value = DhcpJetBeginTransaction();
  if ( Value )
    goto LABEL_118;
  v3 = 1;
  switch ( *(_DWORD *)a2 )
  {
    case 0:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v13 = DhcpIpAddressToDottedString(*(unsigned int *)(a2 + 8));
        WPP_SF_s(v12, 52, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, v13);
      }
      v8 = a2 + 8;
      v10 = 4;
      v11 = *(_QWORD *)DhcpGlobalClientTable;
      goto LABEL_23;
    case 1:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids);
      v10 = *(unsigned int *)(a2 + 8);
      v8 = *(_QWORD *)(a2 + 16);
      v11 = *(_QWORD *)(DhcpGlobalClientTable + 16);
LABEL_23:
      Value = DhcpJetOpenKey(v11, v8, v10);
      break;
    case 2:
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids,
          *(_QWORD *)(a2 + 8));
        v7 = WPP_GLOBAL_Control;
      }
      v8 = *(_QWORD *)(a2 + 8);
      if ( !v8 )
      {
        Value = 87;
LABEL_120:
        if ( v3 == 1 )
        {
          DhcpJetRollBack();
          v7 = WPP_GLOBAL_Control;
        }
        if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x200) != 0 )
          WPP_SF_D(v7[2], 67, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, Value);
        goto LABEL_105;
      }
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      v10 = (unsigned int)(2 * v9 + 2);
      v11 = *(_QWORD *)(DhcpGlobalClientTable + 64);
      goto LABEL_23;
  }
  if ( Value )
    goto LABEL_118;
  pcbActual = 4;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 8), &in, &pcbActual);
  if ( Value )
    goto LABEL_118;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &hMem, v35);
  if ( Value )
    goto LABEL_118;
  if ( (unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, in.S_un.S_addr) )
  {
    Value = 20019;
    v7 = WPP_GLOBAL_Control;
    goto LABEL_120;
  }
  pcbActual = 1;
  if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 152), &pvData, &pcbActual) )
    pvData = 1;
  pcbActual = 1;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), &v38, &pcbActual);
  if ( Value )
    goto LABEL_118;
  String = GetString(1083);
  ((void (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, _DWORD, __int64))DhcpUpdateAuditLog)(
    16,
    String,
    in,
    (_DWORD)hMem,
    v35[0],
    0);
  v15 = in.S_un.S_addr & DhcpGetSubnetMaskForAddress(in.S_un.S_addr);
  v35[1] = v15;
  v16 = v35[0];
  if ( v35[0] > 4 && v15 == *(_DWORD *)hMem )
  {
    v17 = (char *)hMem + 4;
    v16 = v35[0] - 4;
  }
  else
  {
    v17 = (char *)hMem;
  }
  v18 = v16 - 1;
  if ( !v16 )
    v18 = 0;
  if ( qword_1801577F8 )
    qword_1801577F8(in.S_un.S_addr, (unsigned __int64)(v17 + 1) & -(__int64)(v16 != 0), v18, 0, 0);
  MemServerGetUAddressInfo((_DWORD)DhcpGlobalThisServer, v15, (unsigned int)&v37, 0, 0, 0);
  if ( v38 >= 0 )
  {
    v22 = DhcpDoDynDnsCheckDelete(in.S_un.S_addr);
    v21 = v37;
    if ( v22 )
    {
      if ( v37 && *(_DWORD *)(v37 + 4292) )
      {
        updated = DhcpUpdateClientTransactionTime(in.S_un.S_addr);
        Value = updated;
        if ( updated )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
          {
            goto LABEL_119;
          }
          v26 = 62;
          goto LABEL_54;
        }
        v30 = *(_DWORD *)(v21 + 4308);
        if ( v30 == 4 || v30 == 5 )
        {
          updated = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &in, v29, 0);
          Value = updated;
          if ( updated )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_119;
            }
            v26 = 63;
            goto LABEL_54;
          }
          v31 = DhcpMarkFailoverLease(*(_DWORD *)(DhcpGlobalClientTable + 312));
          if ( v31
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, v31);
          }
          updated = DhcpJetCommitUpdate();
          Value = updated;
          if ( updated )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
            {
              goto LABEL_119;
            }
            v26 = 65;
            goto LABEL_54;
          }
        }
        Value = DhcpHandleFailoverRequest(v21, in.S_un.S_addr, 1, (v38 & 3) != 2);
        if ( Value )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
          {
            goto LABEL_119;
          }
          v26 = 66;
          goto LABEL_72;
        }
      }
      else
      {
        v32 = JetDelete(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
        Value = DhcpMapJetError(v32, "DeleteClientInfo:Delete");
        if ( Value )
          goto LABEL_118;
      }
    }
    else if ( v37 && *(_DWORD *)(v37 + 4292) == 1 )
    {
      v24 = *(_DWORD *)(v37 + 4308);
      if ( v24 == 4 || v24 == 5 )
      {
        updated = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &in, v23, 0);
        Value = updated;
        if ( updated )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_119;
          }
          v26 = 56;
LABEL_54:
          v27 = updated;
LABEL_55:
          WPP_SF_D(v7[2], v26, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, v27);
LABEL_118:
          v7 = WPP_GLOBAL_Control;
          goto LABEL_119;
        }
        v28 = DhcpMarkFailoverLease(*(_DWORD *)(DhcpGlobalClientTable + 312));
        if ( v28
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, v28);
        }
        updated = DhcpJetCommitUpdate();
        Value = updated;
        if ( updated )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            goto LABEL_119;
          }
          v26 = 58;
          goto LABEL_54;
        }
      }
      updated = DhcpUpdateClientTransactionTime(in.S_un.S_addr);
      Value = updated;
      if ( updated )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_119;
        }
        v26 = 59;
        goto LABEL_54;
      }
      Value = DhcpHandleFailoverRequest(v21, in.S_un.S_addr, 0, (v38 & 3) != 2);
      if ( Value )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
        {
          goto LABEL_119;
        }
        v26 = 60;
LABEL_72:
        v27 = Value;
        goto LABEL_55;
      }
    }
    else
    {
      Value = 0;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_102;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_102;
  }
  DhcpDoDynDnsCheckDelete(in.S_un.S_addr);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v20 = inet_ntoa(in);
    WPP_SF_s(v19, 55, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, v20);
    v7 = WPP_GLOBAL_Control;
  }
  v4 = 1;
  Value = 0;
  v21 = v37;
LABEL_102:
  if ( v4 )
  {
    Value = 0;
    goto LABEL_104;
  }
  if ( !v21 || *(_DWORD *)(v21 + 4292) != 1 )
  {
    if ( pvData == 2 )
    {
      Value = DhcpReleaseBootpAddress(in.S_un.S_addr);
      if ( Value )
        DhcpReleaseAddress(in.S_un.S_addr);
    }
    else
    {
      Value = DhcpReleaseAddress(in.S_un.S_addr);
      if ( Value )
        DhcpReleaseBootpAddress(in.S_un.S_addr);
    }
    if ( Value == 2 )
      Value = 0;
    goto LABEL_118;
  }
LABEL_119:
  if ( Value )
    goto LABEL_120;
LABEL_104:
  DhcpJetCommitTransaction();
LABEL_105:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( hMem )
    LocalFree(hMem);
  return Value;
}

```

## disassembly

```asm
0x1800092e0  mov     rax, rsp
0x1800092e3  mov     [rax+8], rbx
0x1800092e7  mov     [rax+10h], rsi
0x1800092eb  push    rdi
0x1800092ec  push    r12
0x1800092ee  push    r13
0x1800092f0  push    r14
0x1800092f2  push    r15
0x1800092f4  sub     rsp, 60h
0x1800092f8  mov     r14, rdx
0x1800092fb  xor     edi, edi
0x1800092fd  mov     [rax-58h], edi
0x180009300  mov     [rax-54h], edi
0x180009303  mov     [rax-40h], rdi
0x180009307  mov     [rax-50h], edi
0x18000930a  mov     r13d, edi
0x18000930d  mov     [rax+20h], dil
0x180009311  mov     [rax+18h], dil
0x180009315  mov     r12d, edi
0x180009318  mov     [rax-38h], rdi
0x18000931c  mov     ecx, 0A0000000h
0x180009321  call    DhcpApiAccessCheck
0x180009326  test    eax, eax
0x180009328  jnz     loc_180009A37
0x18000932e  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180009335  call    cs:__imp_EnterCriticalSection
0x18000933c  nop     dword ptr [rax+rax+00h]
0x180009341  call    DhcpJetBeginTransaction
0x180009346  mov     ebx, eax
0x180009348  lea     r15d, [rdi+1]
0x18000934c  test    eax, eax
0x18000934e  jnz     loc_180009AA0
0x180009354  mov     r13d, r15d
0x180009357  mov     eax, [r14]
0x18000935a  test    eax, eax
0x18000935c  jz      loc_180009433
0x180009362  sub     eax, r15d
0x180009365  jz      loc_1800093ED
0x18000936b  cmp     eax, r15d
0x18000936e  jnz     short loc_1800093E1
0x180009370  lea     rsi, WPP_GLOBAL_Control
0x180009377  mov     rcx, cs:WPP_GLOBAL_Control
0x18000937e  cmp     rcx, rsi
0x180009381  jz      short loc_1800093AA
0x180009383  test    dword ptr [rcx+1Ch], 200h
0x18000938a  jz      short loc_1800093AA
0x18000938c  lea     edx, [rdi+36h]
0x18000938f  mov     r9, [r14+8]
0x180009393  lea     r8, WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids
0x18000939a  mov     rcx, [rcx+10h]
0x18000939e  call    WPP_SF_S
0x1800093a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093aa  mov     rdx, [r14+8]
0x1800093ae  test    rdx, rdx
0x1800093b1  jnz     short loc_1800093BB
0x1800093b3  lea     ebx, [rdx+57h]
0x1800093b6  jmp     loc_180009AB6
0x1800093bb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800093bf  inc     r8
0x1800093c2  cmp     [rdx+r8*2], di
0x1800093c7  jnz     short loc_1800093BF
0x1800093c9  lea     r8d, ds:2[r8*2]
0x1800093d1  mov     rcx, cs:DhcpGlobalClientTable
0x1800093d8  mov     rcx, [rcx+40h]
0x1800093dc  jmp     loc_180009487
0x1800093e1  lea     rsi, WPP_GLOBAL_Control
0x1800093e8  jmp     loc_18000948E
0x1800093ed  lea     rsi, WPP_GLOBAL_Control
0x1800093f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093fb  cmp     rcx, rsi
0x1800093fe  jz      short loc_18000941E
0x180009400  test    dword ptr [rcx+1Ch], 200h
0x180009407  jz      short loc_18000941E
0x180009409  mov     edx, 35h ; '5'
0x18000940e  lea     r8, WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids
0x180009415  mov     rcx, [rcx+10h]
0x180009419  call    WPP_SF_
0x18000941e  mov     r8d, [r14+8]
0x180009422  mov     rdx, [r14+10h]
0x180009426  mov     rcx, cs:DhcpGlobalClientTable
0x18000942d  mov     rcx, [rcx+10h]
0x180009431  jmp     short loc_180009487
0x180009433  lea     rsi, WPP_GLOBAL_Control
0x18000943a  mov     rbx, cs:WPP_GLOBAL_Control
0x180009441  cmp     rbx, rsi
0x180009444  jz      short loc_180009473
0x180009446  test    dword ptr [rbx+1Ch], 200h
0x18000944d  jz      short loc_180009473
0x18000944f  mov     rbx, [rbx+10h]
0x180009453  mov     ecx, [r14+8]
0x180009457  call    DhcpIpAddressToDottedString
0x18000945c  mov     r9, rax
0x18000945f  mov     edx, 34h ; '4'
0x180009464  lea     r8, WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids
0x18000946b  mov     rcx, rbx
0x18000946e  call    WPP_SF_s
0x180009473  lea     rdx, [r14+8]
0x180009477  mov     r8d, 4
0x18000947d  mov     rcx, cs:DhcpGlobalClientTable
0x180009484  mov     rcx, [rcx]
0x180009487  call    DhcpJetOpenKey
0x18000948c  mov     ebx, eax
0x18000948e  test    ebx, ebx
0x180009490  jnz     loc_180009AA7
0x180009496  mov     [rsp+88h+pcbActual], 4
0x18000949e  lea     r8, [rsp+88h+pcbActual]; pcbActual
0x1800094a3  lea     rdx, [rsp+88h+in]; pvData
0x1800094a8  mov     rcx, cs:DhcpGlobalClientTable
0x1800094af  mov     ecx, [rcx+8]; columnid
0x1800094b2  call    DhcpJetGetValue
0x1800094b7  mov     ebx, eax
0x1800094b9  test    eax, eax
0x1800094bb  jnz     loc_180009AA7
0x1800094c1  lea     r8, [rsp+88h+var_50]; pcbActual
0x1800094c6  lea     rdx, [rsp+88h+hMem]; pvData
0x1800094cb  mov     rcx, cs:DhcpGlobalClientTable
0x1800094d2  mov     ecx, [rcx+18h]; columnid
0x1800094d5  call    DhcpJetGetValue
0x1800094da  mov     ebx, eax
0x1800094dc  test    eax, eax
0x1800094de  jnz     loc_180009AA7
0x1800094e4  mov     edx, dword ptr [rsp+88h+in.S_un]
0x1800094e8  mov     rcx, cs:DhcpGlobalThisServer
0x1800094ef  call    MemServerIsReservedAddress
0x1800094f4  test    eax, eax
0x1800094f6  jz      short loc_180009509
0x1800094f8  mov     ebx, 4E33h
0x1800094fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009504  jmp     loc_180009AB6
0x180009509  mov     [rsp+88h+pcbActual], r15d
0x18000950e  lea     r8, [rsp+88h+pcbActual]; pcbActual
0x180009513  lea     rdx, [rsp+88h+pvData]; pvData
0x18000951b  mov     rcx, cs:DhcpGlobalClientTable
0x180009522  mov     ecx, [rcx+98h]; columnid
0x180009528  call    DhcpJetGetValue
0x18000952d  test    eax, eax
0x18000952f  jz      short loc_180009539
0x180009531  mov     [rsp+88h+pvData], r15b
0x180009539  mov     [rsp+88h+pcbActual], r15d
0x18000953e  lea     r8, [rsp+88h+pcbActual]; pcbActual
0x180009543  lea     rdx, [rsp+88h+arg_10]; pvData
0x18000954b  mov     rcx, cs:DhcpGlobalClientTable
0x180009552  mov     ecx, [rcx+28h]; columnid
0x180009555  call    DhcpJetGetValue
0x18000955a  mov     ebx, eax
0x18000955c  test    eax, eax
0x18000955e  jnz     loc_180009AA7
0x180009564  mov     ecx, 43Bh
0x180009569  call    GetString
0x18000956e  mov     rdx, rax
0x180009571  mov     [rsp+88h+var_60], rdi
0x180009576  mov     eax, [rsp+88h+var_50]
0x18000957a  mov     dword ptr [rsp+88h+var_68], eax
0x18000957e  mov     r9, [rsp+88h+hMem]
0x180009583  mov     r8d, dword ptr [rsp+88h+in.S_un]
0x180009588  lea     ecx, [rbx+10h]
0x18000958b  call    DhcpUpdateAuditLog
0x180009590  mov     ecx, dword ptr [rsp+88h+in.S_un]
0x180009594  call    DhcpGetSubnetMaskForAddress
0x180009599  mov     ebx, eax
0x18000959b  and     ebx, dword ptr [rsp+88h+in.S_un]
0x18000959f  mov     [rsp+88h+var_4C], ebx
0x1800095a3  mov     ecx, [rsp+88h+var_50]
0x1800095a7  cmp     ecx, 4
0x1800095aa  jbe     short loc_1800095BE
0x1800095ac  mov     rax, [rsp+88h+hMem]
0x1800095b1  cmp     ebx, [rax]
0x1800095b3  jnz     short loc_1800095BE
0x1800095b5  add     rax, 4
0x1800095b9  add     ecx, 0FFFFFFFCh
0x1800095bc  jmp     short loc_1800095C3
0x1800095be  mov     rax, [rsp+88h+hMem]
0x1800095c3  lea     r8d, [rcx-1]
0x1800095c7  test    ecx, ecx
0x1800095c9  cmovz   r8d, ecx
0x1800095cd  inc     rax
0x1800095d0  neg     ecx
0x1800095d2  sbb     rdx, rdx
0x1800095d5  and     rdx, rax
0x1800095d8  mov     rax, cs:qword_1801577F8
0x1800095df  test    rax, rax
0x1800095e2  jz      short loc_1800095F4
0x1800095e4  mov     dword ptr [rsp+88h+var_68], edi
0x1800095e8  xor     r9d, r9d
0x1800095eb  mov     ecx, dword ptr [rsp+88h+in.S_un]
0x1800095ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095f4  jmp     short loc_180009614
0x1800095f6  mov     ecx, eax
0x1800095f8  call    DhcpCalloutLogAV
0x1800095fd  xor     edi, edi
0x1800095ff  lea     r15d, [rdi+1]
0x180009603  lea     rsi, WPP_GLOBAL_Control
0x18000960a  mov     ebx, [rsp+88h+var_4C]
0x18000960e  mov     r13d, r15d
0x180009611  mov     r12d, edi
0x180009614  mov     [rsp+88h+var_60], rdi
0x180009619  mov     [rsp+88h+var_68], rdi
0x18000961e  xor     r9d, r9d
0x180009621  lea     r8, [rsp+88h+var_38]
0x180009626  mov     edx, ebx
0x180009628  mov     rcx, cs:DhcpGlobalThisServer
0x18000962f  call    MemServerGetUAddressInfo
0x180009634  mov     ecx, dword ptr [rsp+88h+in.S_un]
0x180009638  test    [rsp+88h+arg_10], 80h
0x180009640  jz      short loc_18000969A
0x180009642  call    DhcpDoDynDnsCheckDelete
0x180009647  mov     rcx, cs:WPP_GLOBAL_Control
0x18000964e  cmp     rcx, rsi
0x180009651  jz      short loc_18000968B
0x180009653  test    byte ptr [rcx+1Ch], 10h
0x180009657  jz      short loc_18000968B
0x180009659  mov     rbx, [rcx+10h]
0x18000965d  mov     ecx, dword ptr [rsp+88h+in.S_un]; in
0x180009661  call    cs:__imp_inet_ntoa
0x180009668  nop     dword ptr [rax+rax+00h]
0x18000966d  mov     r9, rax
0x180009670  mov     edx, 37h ; '7'
0x180009675  lea     r8, WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids
0x18000967c  mov     rcx, rbx
0x18000967f  call    WPP_SF_s
0x180009684  mov     rcx, cs:WPP_GLOBAL_Control
0x18000968b  mov     r12d, r15d
0x18000968e  mov     ebx, edi
0x180009690  mov     r14, [rsp+88h+var_38]
0x180009695  jmp     loc_180009A00
0x18000969a  call    DhcpDoDynDnsCheckDelete
0x18000969f  mov     r14, [rsp+88h+var_38]
0x1800096a4  test    eax, eax
0x1800096a6  jnz     loc_180009863
0x1800096ac  test    r14, r14
0x1800096af  jz      loc_18000982A
0x1800096b5  cmp     [r14+10C4h], r15d
0x1800096bc  jnz     loc_18000982A
0x1800096c2  mov     eax, [r14+10D4h]
0x1800096c9  cmp     eax, 4
0x1800096cc  jz      short loc_1800096D7
0x1800096ce  cmp     eax, 5
0x1800096d1  jnz     loc_18000979C
0x1800096d7  xor     r9d, r9d
0x1800096da  lea     rdx, [rsp+88h+in]
0x1800096df  mov     rcx, cs:DhcpGlobalClientTable
0x1800096e6  mov     rcx, [rcx]
0x1800096e9  call    DhcpJetPrepareUpdate
0x1800096ee  mov     ebx, eax
0x1800096f0  test    eax, eax
0x1800096f2  jz      short loc_18000972B
0x1800096f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096fb  cmp     rcx, rsi
0x1800096fe  jz      loc_180009AAE
0x180009704  test    byte ptr [rcx+1Ch], 10h
0x180009708  jz      loc_180009AAE
0x18000970e  mov     edx, 38h ; '8'
0x180009713  mov     r9d, eax
0x180009716  lea     r8, WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids
0x18000971d  mov     rcx, [rcx+10h]
0x180009721  call    WPP_SF_D
0x180009726  jmp     loc_180009AA7
0x18000972b  mov     dl, 10h
0x18000972d  mov     rcx, cs:DhcpGlobalClientTable
0x180009734  mov     ecx, [rcx+138h]; columnid
0x18000973a  call    DhcpMarkFailoverLease
0x18000973f  test    eax, eax
0x180009741  jz      short loc_18000976D
0x180009743  mov     rcx, cs:WPP_GLOBAL_Control
0x18000974a  cmp     rcx, rsi
0x18000974d  jz      short loc_18000976D
0x18000974f  test    byte ptr [rcx+1Ch], 10h
0x180009753  jz      short loc_18000976D
0x180009755  mov     edx, 39h ; '9'
0x18000975a  mov     r9d, eax
0x18000975d  lea     r8, WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids
0x180009764  mov     rcx, [rcx+10h]
0x180009768  call    WPP_SF_D
0x18000976d  call    DhcpJetCommitUpdate
0x180009772  mov     ebx, eax
0x180009774  test    eax, eax
0x180009776  jz      short loc_18000979C
0x180009778  mov     rcx, cs:WPP_GLOBAL_Control
0x18000977f  cmp     rcx, rsi
0x180009782  jz      loc_180009AAE
0x180009788  test    byte ptr [rcx+1Ch], 10h
0x18000978c  jz      loc_180009AAE
0x180009792  mov     edx, 3Ah ; ':'
0x180009797  jmp     loc_180009713
0x18000979c  mov     ecx, dword ptr [rsp+88h+in.S_un]
0x1800097a0  call    DhcpUpdateClientTransactionTime
0x1800097a5  mov     ebx, eax
0x1800097a7  test    eax, eax
0x1800097a9  jz      short loc_1800097D2
0x1800097ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800097b2  cmp     rcx, rsi
0x1800097b5  jz      loc_180009AAE
0x1800097bb  test    dword ptr [rcx+1Ch], 800000h
0x1800097c2  jz      loc_180009AAE
0x1800097c8  mov     edx, 3Bh ; ';'
0x1800097cd  jmp     loc_180009713
0x1800097d2  mov     al, [rsp+88h+arg_10]
0x1800097d9  and     al, 3
0x1800097db  xor     r8d, r8d
0x1800097de  mov     edx, dword ptr [rsp+88h+in.S_un]
  ... truncated ...
```
