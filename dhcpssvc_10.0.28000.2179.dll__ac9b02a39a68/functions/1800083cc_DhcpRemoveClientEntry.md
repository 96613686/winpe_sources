# DhcpRemoveClientEntry

- ea: `0x1800083cc`
- end: `0x180008c73`
- name: `DhcpRemoveClientEntry`
- size: `2215`
- prototype: ``
- caller_count: `7`
- callee_count: `21`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18004a4a4`
- `0x18004ad58`
- `0x18005675c`
- `0x180058c00`
- `0x18005923c`
- `0x18005a5cc`
- `0x18005a9ec`

## callees

- `0x18000282c`
- `0x1800083cc`
- `0x18000d028`
- `0x18000e1a0`
- `0x18000e1d0`
- `0x18000e204`
- `0x18000e284`
- `0x18000e64c`
- `0x18000e78c`
- `0x18000e7c0`
- `0x18000e814`
- `0x18000e97c`
- `0x180020094`
- `0x180020f08`
- `0x18003147c`
- `0x1800314cc`
- `0x180057a90`
- `0x18008ef8c`
- `0x180098a40`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!time` at `0x180008844`
- `msvcrt!time` at `0x180008ab4`
- `msvcrt!time` at `0x180008844`
- `msvcrt!time` at `0x180008ab4`
- `ESENT!JetSetCurrentIndex` at `0x18000847c`
- `ESENT!JetSetCurrentIndex` at `0x18000847c`
- `ESENT!JetMakeKey` at `0x1800084bc`
- `ESENT!JetMakeKey` at `0x1800084bc`
- `ESENT!JetSeek` at `0x1800084f1`
- `ESENT!JetSeek` at `0x1800084f1`
- `ESENT!JetDelete` at `0x180008640`
- `ESENT!JetDelete` at `0x1800089c8`
- `ESENT!JetDelete` at `0x180008640`
- `ESENT!JetDelete` at `0x1800089c8`
- `KERNEL32!EnterCriticalSection` at `0x180008445`
- `KERNEL32!EnterCriticalSection` at `0x180008445`
- `KERNEL32!LeaveCriticalSection` at `0x180008bf9`
- `KERNEL32!LeaveCriticalSection` at `0x180008bf9`
- `KERNEL32!HeapFree` at `0x180008c18`
- `KERNEL32!HeapFree` at `0x180008c37`
- `KERNEL32!HeapFree` at `0x180008c18`
- `KERNEL32!HeapFree` at `0x180008c37`

## string_xrefs

- `0x18000848a`: `RemoveClientEntry:SetCurrentIndex`
- `0x1800084ca`: `RemoveClientEntry:MakeKey`
- `0x1800084ff`: `RemoveClientEntry:Seek`
- `0x18000864e`: `RemoveClientEntry:Delete`
- `0x1800089d6`: `RemoveClientEntry:Delete`

## pseudocode

```c
__int64 __fastcall DhcpRemoveClientEntry(
        struct in_addr a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        unsigned int a6,
        int a7,
        __int64 a8)
{
  int v8; // r13d
  int v9; // r12d
  unsigned int v10; // r15d
  unsigned int Value; // ebx
  unsigned int v13; // eax
  unsigned int Key; // eax
  unsigned int v15; // eax
  __int64 v16; // r8
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // r8
  unsigned int v20; // eax
  unsigned int v21; // ebx
  unsigned int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // edi
  int v26; // eax
  unsigned int v27; // eax
  int v29; // [rsp+38h] [rbp-D0h] BYREF
  struct in_addr pvData; // [rsp+40h] [rbp-C8h] BYREF
  int v31; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int pcbActual; // [rsp+4Ch] [rbp-BCh] BYREF
  unsigned int v33[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v35[2]; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID v37; // [rsp+70h] [rbp-98h] BYREF
  int v38[20]; // [rsp+78h] [rbp-90h] BYREF
  LPVOID v39; // [rsp+C8h] [rbp-40h]
  __int64 v40; // [rsp+D0h] [rbp-38h]

  pvData = a1;
  v8 = 0;
  LOWORD(v29) = 0;
  lpMem = 0;
  v9 = 0;
  v10 = 0;
  v35[1] = 0;
  v37 = 0;
  v31 = 0;
  v35[0] = 0;
  pcbActual = 1;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  Value = DhcpJetBeginTransaction();
  if ( Value )
    goto LABEL_97;
  v8 = 1;
  v13 = JetSetCurrentIndex(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, *(_QWORD *)DhcpGlobalClientTable);
  Value = DhcpMapJetError(v13, "RemoveClientEntry:SetCurrentIndex");
  if ( Value )
    goto LABEL_97;
  Key = JetMakeKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, &pvData, 4u, 1u);
  Value = DhcpMapJetError(Key, "RemoveClientEntry:MakeKey");
  if ( Value )
    goto LABEL_97;
  v15 = JetSeek(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 1u);
  Value = DhcpMapJetError(v15, "RemoveClientEntry:Seek");
  if ( Value )
    goto LABEL_97;
  if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 152), &v29, &pcbActual) )
    LOBYTE(v29) = 1;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), (char *)&v29 + 1, &pcbActual);
  if ( Value )
    goto LABEL_97;
  pcbActual = 4;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 360), v35, &pcbActual);
  if ( Value )
    goto LABEL_97;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &v37, &v35[1]);
  if ( Value )
    goto LABEL_97;
  v33[0] = 0;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 72), &lpMem, v33);
  if ( Value )
    goto LABEL_97;
  if ( !(unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, pvData.S_un.S_addr) )
  {
    if ( a5 || (unsigned int)DhcpDoDynDnsCheckDelete(pvData.S_un.S_addr) )
    {
      if ( *(_DWORD *)(a8 + 4292) != 1 )
      {
        v25 = JetDelete(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
        Value = DhcpMapJetError(v25, "RemoveClientEntry:Delete");
        if ( Value )
        {
          v23 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, v25);
            v23 = WPP_GLOBAL_Control;
          }
          goto LABEL_66;
        }
        if ( *(_DWORD *)(a8 + 4292) != 1 )
          goto LABEL_90;
      }
      v10 = 1;
    }
    else
    {
      Value = 0;
      if ( *(_DWORD *)(a8 + 4292) != 1 )
        goto LABEL_90;
    }
    if ( a4 == 1 )
    {
      v22 = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &pvData, v16, 0);
      Value = v22;
      if ( v22 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v24 = 27;
          goto LABEL_40;
        }
        goto LABEL_66;
      }
      v26 = *(_DWORD *)(a8 + 4308);
      if ( v26 == 4 || v26 == 5 )
        DhcpMarkFailoverLease(*(_DWORD *)(DhcpGlobalClientTable + 312));
      v31 = time(0);
      v22 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 280), &v31, 4u);
      Value = v22;
      if ( v22 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v24 = 28;
          goto LABEL_40;
        }
        goto LABEL_66;
      }
      v31 = 0;
      v22 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 216), &v31, 4u);
      Value = v22;
      if ( v22 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v24 = 29;
          goto LABEL_40;
        }
        goto LABEL_66;
      }
      v22 = DhcpJetCommitUpdate();
      Value = v22;
      if ( v22 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v24 = 30;
          goto LABEL_40;
        }
        goto LABEL_66;
      }
    }
    if ( *(_DWORD *)(a8 + 4292) == 1 )
    {
LABEL_96:
      if ( !Value )
        goto LABEL_25;
      goto LABEL_97;
    }
LABEL_90:
    if ( a4 == 1 )
    {
      if ( (_BYTE)v29 == 2 )
        v27 = DhcpReleaseBootpAddress(pvData.S_un.S_addr);
      else
        v27 = DhcpReleaseAddress(pvData.S_un.S_addr);
      Value = v27;
      if ( v27 )
        Value = 0;
      goto LABEL_25;
    }
    goto LABEL_96;
  }
  v34 = 0;
  v33[1] = 8;
  if ( !(unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &v34, &v33[1]) && !v34 )
  {
    v9 = 1;
    if ( !a7 )
    {
LABEL_24:
      Value = 20019;
LABEL_25:
      DhcpJetCommitTransaction();
      goto LABEL_26;
    }
    v17 = JetDelete(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
    v18 = DhcpMapJetError(v17, "RemoveClientEntry:Delete");
    goto LABEL_23;
  }
  memset_0(v38, 0, 0xD0u);
  v33[0] = 0;
  if ( !a4 )
  {
    v39 = DhcpGlobalThisServer;
    v40 = a8;
    GetLeaseInfo((int)v38, 0);
    v34 = DhcpCalculateTime(v33[0]);
    v9 = 1;
LABEL_18:
    Value = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &pvData, v19, 0);
    if ( !Value )
    {
      Value = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &v34, 8u);
      if ( a4 )
        DhcpDoDynDnsReservationWork(pvData, (STRSAFE_LPCWSTR)lpMem, (__int64)v37, v35[0] & 1);
      if ( !Value )
      {
        v18 = DhcpJetCommitUpdate();
LABEL_23:
        Value = v18;
        if ( !v18 )
          goto LABEL_24;
      }
    }
LABEL_97:
    v23 = WPP_GLOBAL_Control;
    goto LABEL_66;
  }
  v34 = 0;
  if ( *(_DWORD *)(a8 + 4292) != 1 )
    goto LABEL_18;
  v22 = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &pvData, v19, 0);
  Value = v22;
  if ( v22 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    {
      v24 = 22;
LABEL_40:
      WPP_SF_D(v23[2], v24, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, v22);
      v23 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v31 = time(0);
    v22 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 280), &v31, 4u);
    Value = v22;
    if ( v22 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        v24 = 23;
        goto LABEL_40;
      }
    }
    else
    {
      v31 = 0;
      v22 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 216), &v31, 4u);
      Value = v22;
      if ( v22 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          v24 = 24;
          goto LABEL_40;
        }
      }
      else
      {
        v22 = DhcpJetCommitUpdate();
        Value = v22;
        if ( !v22 )
          goto LABEL_18;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          v24 = 25;
          goto LABEL_40;
        }
      }
    }
  }
LABEL_66:
  if ( Value == 20019 )
    goto LABEL_25;
  if ( v8 == 1 )
  {
    DhcpJetRollBack();
    v23 = WPP_GLOBAL_Control;
  }
  if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 0x10) != 0 )
    WPP_SF_D(v23[2], 31, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, Value);
LABEL_26:
  if ( *(_DWORD *)(a8 + 4292) == 1 && (!Value || Value == 20019) && !v9 )
  {
    DhcpJetBeginTransaction();
    v20 = DhcpHandleFailoverRequest(a8, pvData.S_un.S_addr, v10, a6);
    v21 = v20;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids, v20);
    if ( v21 )
      DhcpJetRollBack();
    else
      DhcpJetCommitTransaction();
    Value = 0;
  }
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( lpMem )
    HeapFree(gDhcpHeap, 0, lpMem);
  if ( v37 )
    HeapFree(gDhcpHeap, 0, v37);
  return Value;
}

```

## disassembly

```asm
0x1800083cc  mov     rax, rsp
0x1800083cf  mov     [rax+10h], rbx
0x1800083d3  mov     [rax+18h], rsi
0x1800083d7  mov     [rax+20h], rdi
0x1800083db  push    rbp
0x1800083dc  push    r12
0x1800083de  push    r13
0x1800083e0  push    r14
0x1800083e2  push    r15
0x1800083e4  lea     rbp, [rax-78h]
0x1800083e8  sub     rsp, 150h
0x1800083ef  mov     rax, cs:__security_cookie
0x1800083f6  xor     rax, rsp
0x1800083f9  mov     [rbp+70h+var_30], rax
0x1800083fd  mov     r14, [rbp+70h+arg_38]
0x180008404  xor     edi, edi
0x180008406  mov     [rsp+170h+pvData], ecx
0x18000840a  mov     r13d, edi
0x18000840d  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180008414  mov     byte ptr [rsp+170h+var_140], dil
0x180008419  mov     [rsp+170h+lpMem], rdi
0x18000841e  mov     r12d, edi
0x180008421  mov     byte ptr [rsp+170h+var_140+1], dil
0x180008426  mov     r15d, edi
0x180008429  mov     [rsp+170h+var_118+4], edi
0x18000842d  mov     esi, r9d
0x180008430  mov     [rsp+170h+var_108], rdi
0x180008435  mov     [rsp+170h+var_130], edi
0x180008439  mov     [rsp+170h+var_118], edi
0x18000843d  mov     [rsp+170h+pcbActual], 1
0x180008445  call    cs:__imp_EnterCriticalSection
0x18000844c  nop     dword ptr [rax+rax+00h]
0x180008451  call    DhcpJetBeginTransaction
0x180008456  mov     ebx, eax
0x180008458  test    eax, eax
0x18000845a  jnz     loc_180008BD8
0x180008460  mov     r8, cs:DhcpGlobalClientTable
0x180008467  lea     r13d, [rdi+1]
0x18000846b  mov     rdx, cs:DhcpGlobalClientTableHandle
0x180008472  mov     rcx, cs:DhcpGlobalJetServerSession
0x180008479  mov     r8, [r8]
0x18000847c  call    cs:__imp_JetSetCurrentIndex
0x180008483  nop     dword ptr [rax+rax+00h]
0x180008488  mov     ecx, eax
0x18000848a  lea     rdx, aRemoveclienten; "RemoveClientEntry:SetCurrentIndex"
0x180008491  call    DhcpMapJetError
0x180008496  mov     ebx, eax
0x180008498  test    eax, eax
0x18000849a  jnz     loc_180008BD8
0x1800084a0  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800084a7  lea     r9d, [rdi+4]; cbData
0x1800084ab  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800084b2  lea     r8, [rsp+170h+pvData]; pvData
0x1800084b7  mov     [rsp+170h+grbit], r13d; grbit
0x1800084bc  call    cs:__imp_JetMakeKey
0x1800084c3  nop     dword ptr [rax+rax+00h]
0x1800084c8  mov     ecx, eax
0x1800084ca  lea     rdx, aRemoveclienten_1; "RemoveClientEntry:MakeKey"
0x1800084d1  call    DhcpMapJetError
0x1800084d6  mov     ebx, eax
0x1800084d8  test    eax, eax
0x1800084da  jnz     loc_180008BD8
0x1800084e0  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800084e7  mov     r8d, r13d; grbit
0x1800084ea  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800084f1  call    cs:__imp_JetSeek
0x1800084f8  nop     dword ptr [rax+rax+00h]
0x1800084fd  mov     ecx, eax
0x1800084ff  lea     rdx, aRemoveclienten_0; "RemoveClientEntry:Seek"
0x180008506  call    DhcpMapJetError
0x18000850b  mov     ebx, eax
0x18000850d  test    eax, eax
0x18000850f  jnz     loc_180008BD8
0x180008515  mov     rcx, cs:DhcpGlobalClientTable
0x18000851c  lea     r8, [rsp+170h+pcbActual]; pcbActual
0x180008521  lea     rdx, [rsp+170h+var_140]; pvData
0x180008526  mov     ecx, [rcx+98h]; columnid
0x18000852c  call    DhcpJetGetValue
0x180008531  test    eax, eax
0x180008533  jz      short loc_18000853A
0x180008535  mov     byte ptr [rsp+170h+var_140], r13b
0x18000853a  mov     rcx, cs:DhcpGlobalClientTable
0x180008541  lea     r8, [rsp+170h+pcbActual]; pcbActual
0x180008546  lea     rdx, [rsp+170h+var_140+1]; pvData
0x18000854b  mov     ecx, [rcx+28h]; columnid
0x18000854e  call    DhcpJetGetValue
0x180008553  mov     ebx, eax
0x180008555  test    eax, eax
0x180008557  jnz     loc_180008BD8
0x18000855d  mov     rcx, cs:DhcpGlobalClientTable
0x180008564  lea     r8, [rsp+170h+pcbActual]; pcbActual
0x180008569  mov     [rsp+170h+pcbActual], 4
0x180008571  lea     rdx, [rsp+170h+var_118]; pvData
0x180008576  mov     ecx, [rcx+168h]; columnid
0x18000857c  call    DhcpJetGetValue
0x180008581  mov     ebx, eax
0x180008583  test    eax, eax
0x180008585  jnz     loc_180008BD8
0x18000858b  mov     rcx, cs:DhcpGlobalClientTable
0x180008592  lea     r8, [rsp+170h+var_118+4]; pcbActual
0x180008597  lea     rdx, [rsp+170h+var_108]; pvData
0x18000859c  mov     ecx, [rcx+18h]; columnid
0x18000859f  call    DhcpJetGetValue
0x1800085a4  mov     ebx, eax
0x1800085a6  test    eax, eax
0x1800085a8  jnz     loc_180008BD8
0x1800085ae  mov     rcx, cs:DhcpGlobalClientTable
0x1800085b5  lea     r8, [rsp+170h+var_128]; pcbActual
0x1800085ba  lea     rdx, [rsp+170h+lpMem]; pvData
0x1800085bf  mov     [rsp+170h+var_128], edi
0x1800085c3  mov     ecx, [rcx+48h]; columnid
0x1800085c6  call    DhcpJetGetValue
0x1800085cb  mov     ebx, eax
0x1800085cd  test    eax, eax
0x1800085cf  jnz     loc_180008BD8
0x1800085d5  mov     edx, [rsp+170h+pvData]
0x1800085d9  mov     rcx, cs:DhcpGlobalThisServer
0x1800085e0  call    MemServerIsReservedAddress
0x1800085e5  test    eax, eax
0x1800085e7  jz      loc_180008934
0x1800085ed  mov     rcx, cs:DhcpGlobalClientTable
0x1800085f4  lea     r8, [rsp+170h+var_128+4]; pcbActual
0x1800085f9  lea     rdx, [rsp+170h+var_120]; pvData
0x1800085fe  mov     qword ptr [rsp+170h+var_120], rdi
0x180008603  mov     [rsp+170h+var_128+4], 8
0x18000860b  mov     ecx, [rcx+58h]; columnid
0x18000860e  call    DhcpJetGetValue
0x180008613  test    eax, eax
0x180008615  jnz     short loc_18000865F
0x180008617  cmp     [rsp+170h+var_120], edi
0x18000861b  jnz     short loc_18000865F
0x18000861d  cmp     [rsp+170h+var_11C], edi
0x180008621  jnz     short loc_18000865F
0x180008623  mov     r12d, r13d
0x180008626  cmp     [rbp+70h+arg_30], edi
0x18000862c  jz      loc_18000873A
0x180008632  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x180008639  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180008640  call    cs:__imp_JetDelete
0x180008647  nop     dword ptr [rax+rax+00h]
0x18000864c  mov     ecx, eax
0x18000864e  lea     rdx, aRemoveclienten_2; "RemoveClientEntry:Delete"
0x180008655  call    DhcpMapJetError
0x18000865a  jmp     loc_180008730
0x18000865f  xor     edx, edx; Val
0x180008661  lea     rcx, [rsp+170h+var_100]; void *
0x180008666  mov     r8d, 0D0h; Size
0x18000866c  call    memset_0
0x180008671  mov     [rsp+170h+var_128], edi
0x180008675  test    esi, esi
0x180008677  jnz     loc_1800087CB
0x18000867d  mov     rax, cs:DhcpGlobalThisServer
0x180008684  lea     rdx, [rsp+170h+var_128]
0x180008689  xor     r9d, r9d
0x18000868c  mov     [rbp+70h+var_B0], rax
0x180008690  xor     r8d, r8d
0x180008693  mov     [rbp+70h+var_A8], r14
0x180008697  lea     rcx, [rsp+170h+var_100]; int
0x18000869c  mov     qword ptr [rsp+170h+grbit], rdi; __int64
0x1800086a1  call    GetLeaseInfo
0x1800086a6  mov     ecx, [rsp+170h+var_128]
0x1800086aa  call    DhcpCalculateTime
0x1800086af  mov     qword ptr [rsp+170h+var_120], rax
0x1800086b4  mov     r12d, r13d
0x1800086b7  mov     rcx, cs:DhcpGlobalClientTable
0x1800086be  lea     rdx, [rsp+170h+pvData]
0x1800086c3  xor     r9d, r9d
0x1800086c6  mov     rcx, [rcx]
0x1800086c9  call    DhcpJetPrepareUpdate
0x1800086ce  mov     ebx, eax
0x1800086d0  test    eax, eax
0x1800086d2  jnz     loc_180008BD8
0x1800086d8  mov     rcx, cs:DhcpGlobalClientTable
0x1800086df  lea     r8d, [rax+8]; cbData
0x1800086e3  lea     rdx, [rsp+170h+var_120]; pvData
0x1800086e8  mov     ecx, [rcx+58h]; columnid
0x1800086eb  call    DhcpJetSetValue
0x1800086f0  mov     ebx, eax
0x1800086f2  test    esi, esi
0x1800086f4  jz      short loc_180008723
0x1800086f6  mov     eax, [rsp+170h+var_118]
0x1800086fa  mov     r9d, [rsp+170h+var_118+4]
0x1800086ff  and     eax, r13d
0x180008702  mov     r8b, byte ptr [rsp+170h+var_140+1]
0x180008707  mov     rdx, [rsp+170h+lpMem]; pszSrc
0x18000870c  mov     ecx, [rsp+170h+pvData]; in
0x180008710  mov     [rsp+170h+var_148], eax; int
0x180008714  mov     rax, [rsp+170h+var_108]
0x180008719  mov     qword ptr [rsp+170h+grbit], rax; __int64
0x18000871e  call    DhcpDoDynDnsReservationWork
0x180008723  test    ebx, ebx
0x180008725  jnz     loc_180008BD8
0x18000872b  call    DhcpJetCommitUpdate
0x180008730  mov     ebx, eax
0x180008732  test    eax, eax
0x180008734  jnz     loc_180008BD8
0x18000873a  mov     ebx, 4E33h
0x18000873f  call    DhcpJetCommitTransaction
0x180008744  lea     rsi, WPP_GLOBAL_Control
0x18000874b  cmp     dword ptr [r14+10C4h], 1
0x180008753  jnz     loc_180008BF2
0x180008759  test    ebx, ebx
0x18000875b  jz      short loc_180008769
0x18000875d  cmp     ebx, 4E33h
0x180008763  jnz     loc_180008BF2
0x180008769  test    r12d, r12d
0x18000876c  jnz     loc_180008BF2
0x180008772  call    DhcpJetBeginTransaction
0x180008777  mov     r9d, [rbp+70h+arg_28]
0x18000877e  mov     r8d, r15d
0x180008781  mov     edx, [rsp+170h+pvData]
0x180008785  mov     rcx, r14
0x180008788  call    DhcpHandleFailoverRequest
0x18000878d  mov     ebx, eax
0x18000878f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008796  cmp     rcx, rsi
0x180008799  jz      short loc_1800087B9
0x18000879b  test    byte ptr [rcx+1Ch], 10h
0x18000879f  jz      short loc_1800087B9
0x1800087a1  mov     rcx, [rcx+10h]
0x1800087a5  lea     edx, [r12+20h]
0x1800087aa  mov     r9d, eax
0x1800087ad  lea     r8, WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids
0x1800087b4  call    WPP_SF_D
0x1800087b9  test    ebx, ebx
0x1800087bb  jnz     loc_180008BEB
0x1800087c1  call    DhcpJetCommitTransaction
0x1800087c6  jmp     loc_180008BF0
0x1800087cb  mov     qword ptr [rsp+170h+var_120], rdi
0x1800087d0  cmp     [r14+10C4h], r13d
0x1800087d7  jnz     loc_1800086B7
0x1800087dd  mov     rcx, cs:DhcpGlobalClientTable
0x1800087e4  lea     rdx, [rsp+170h+pvData]
0x1800087e9  xor     r9d, r9d
0x1800087ec  mov     rcx, [rcx]
0x1800087ef  call    DhcpJetPrepareUpdate
0x1800087f4  mov     ebx, eax
0x1800087f6  test    eax, eax
0x1800087f8  jz      short loc_180008842
0x1800087fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180008801  lea     rsi, WPP_GLOBAL_Control
0x180008808  cmp     rcx, rsi
0x18000880b  jz      loc_180008A28
0x180008811  test    dword ptr [rcx+1Ch], 800000h
0x180008818  jz      loc_180008A28
0x18000881e  mov     edx, 16h
0x180008823  mov     rcx, [rcx+10h]
0x180008827  lea     r8, WPP_953f70470c1b3eb34ff336a09a4dcc29_Traceguids
0x18000882e  mov     r9d, eax
0x180008831  call    WPP_SF_D
0x180008836  mov     rcx, cs:WPP_GLOBAL_Control
0x18000883d  jmp     loc_180008A28
0x180008842  xor     ecx, ecx; Time
0x180008844  call    cs:__imp_time
0x18000884b  nop     dword ptr [rax+rax+00h]
0x180008850  mov     rcx, cs:DhcpGlobalClientTable
0x180008857  lea     rdx, [rsp+170h+var_130]; pvData
0x18000885c  mov     [rsp+170h+var_130], eax
0x180008860  mov     r8d, 4; cbData
0x180008866  mov     ecx, [rcx+118h]; columnid
0x18000886c  call    DhcpJetSetValue
0x180008871  mov     ebx, eax
0x180008873  test    eax, eax
0x180008875  jz      short loc_1800088A2
0x180008877  mov     rcx, cs:WPP_GLOBAL_Control
0x18000887e  lea     rsi, WPP_GLOBAL_Control
0x180008885  cmp     rcx, rsi
0x180008888  jz      loc_180008A28
0x18000888e  test    dword ptr [rcx+1Ch], 800000h
0x180008895  jz      loc_180008A28
0x18000889b  mov     edx, 17h
0x1800088a0  jmp     short loc_180008823
0x1800088a2  mov     rcx, cs:DhcpGlobalClientTable
0x1800088a9  lea     rdx, [rsp+170h+var_130]; pvData
0x1800088ae  mov     [rsp+170h+var_130], edi
0x1800088b2  mov     r8d, 4; cbData
0x1800088b8  mov     ecx, [rcx+0D8h]; columnid
0x1800088be  call    DhcpJetSetValue
0x1800088c3  mov     ebx, eax
0x1800088c5  test    eax, eax
0x1800088c7  jz      short loc_1800088F7
0x1800088c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088d0  lea     rsi, WPP_GLOBAL_Control
0x1800088d7  cmp     rcx, rsi
0x1800088da  jz      loc_180008A28
0x1800088e0  test    dword ptr [rcx+1Ch], 800000h
0x1800088e7  jz      loc_180008A28
0x1800088ed  mov     edx, 18h
0x1800088f2  jmp     loc_180008823
0x1800088f7  call    DhcpJetCommitUpdate
0x1800088fc  mov     ebx, eax
0x1800088fe  test    eax, eax
0x180008900  jz      loc_1800086B7
0x180008906  mov     rcx, cs:WPP_GLOBAL_Control
0x18000890d  lea     rsi, WPP_GLOBAL_Control
0x180008914  cmp     rcx, rsi
0x180008917  jz      loc_180008A28
0x18000891d  test    dword ptr [rcx+1Ch], 800000h
0x180008924  jz      loc_180008A28
0x18000892a  mov     edx, 19h
  ... truncated ...
```
