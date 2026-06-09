# DhcpRemoveClientEntry

- ea: `0x1800083d0`
- end: `0x180008c75`
- name: `DhcpRemoveClientEntry`
- size: `2213`
- prototype: ``
- caller_count: `7`
- callee_count: `21`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18004a744`
- `0x18004b040`
- `0x180056a5c`
- `0x180058f38`
- `0x180059550`
- `0x18005a8f4`
- `0x18005ad38`

## callees

- `0x180002854`
- `0x1800083d0`
- `0x18000d97c`
- `0x18000eaf4`
- `0x18000eb24`
- `0x18000eb58`
- `0x18000ebd4`
- `0x18000ef84`
- `0x18000f0c4`
- `0x18000f0f8`
- `0x18000f144`
- `0x18000f2ac`
- `0x180020bb4`
- `0x180021a4c`
- `0x180031e80`
- `0x180031ed0`
- `0x180057dcc`
- `0x18008ee18`
- `0x18009877c`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!time` at `0x180008848`
- `msvcrt!time` at `0x180008ab6`
- `msvcrt!time` at `0x180008848`
- `msvcrt!time` at `0x180008ab6`
- `ESENT!JetSetCurrentIndex` at `0x180008480`
- `ESENT!JetSetCurrentIndex` at `0x180008480`
- `ESENT!JetMakeKey` at `0x1800084c0`
- `ESENT!JetMakeKey` at `0x1800084c0`
- `ESENT!JetSeek` at `0x1800084f5`
- `ESENT!JetSeek` at `0x1800084f5`
- `ESENT!JetDelete` at `0x180008644`
- `ESENT!JetDelete` at `0x1800089cc`
- `ESENT!JetDelete` at `0x180008644`
- `ESENT!JetDelete` at `0x1800089cc`
- `KERNEL32!EnterCriticalSection` at `0x180008449`
- `KERNEL32!EnterCriticalSection` at `0x180008449`
- `KERNEL32!LeaveCriticalSection` at `0x180008bfb`
- `KERNEL32!LeaveCriticalSection` at `0x180008bfb`
- `KERNEL32!HeapFree` at `0x180008c1a`
- `KERNEL32!HeapFree` at `0x180008c39`
- `KERNEL32!HeapFree` at `0x180008c1a`
- `KERNEL32!HeapFree` at `0x180008c39`

## string_xrefs

- `0x18000848e`: `RemoveClientEntry:SetCurrentIndex`
- `0x1800084ce`: `RemoveClientEntry:MakeKey`
- `0x180008503`: `RemoveClientEntry:Seek`
- `0x180008652`: `RemoveClientEntry:Delete`
- `0x1800089da`: `RemoveClientEntry:Delete`

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
  unsigned int v26; // eax
  __int64 v28; // [rsp+38h] [rbp-D0h] BYREF
  struct in_addr pvData; // [rsp+40h] [rbp-C8h] BYREF
  int v30; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int pcbActual; // [rsp+4Ch] [rbp-BCh] BYREF
  unsigned int v32[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v34[2]; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID v36; // [rsp+70h] [rbp-98h] BYREF
  int v37[20]; // [rsp+78h] [rbp-90h] BYREF
  LPVOID v38; // [rsp+C8h] [rbp-40h]
  __int64 v39; // [rsp+D0h] [rbp-38h]

  pvData = a1;
  v8 = 0;
  LOWORD(v28) = 0;
  lpMem = 0;
  v9 = 0;
  v10 = 0;
  v34[1] = 0;
  v36 = 0;
  v30 = 0;
  v34[0] = 0;
  pcbActual = 1;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  Value = DhcpJetBeginTransaction();
  if ( Value )
    goto LABEL_96;
  v8 = 1;
  v13 = JetSetCurrentIndex(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, *(_QWORD *)DhcpGlobalClientTable);
  Value = DhcpMapJetError(v13, "RemoveClientEntry:SetCurrentIndex");
  if ( Value )
    goto LABEL_96;
  Key = JetMakeKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, &pvData, 4u, 1u);
  Value = DhcpMapJetError(Key, "RemoveClientEntry:MakeKey");
  if ( Value )
    goto LABEL_96;
  v15 = JetSeek(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 1u);
  Value = DhcpMapJetError(v15, "RemoveClientEntry:Seek");
  if ( Value )
    goto LABEL_96;
  if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 152), &v28, &pcbActual) )
    LOBYTE(v28) = 1;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), (__int64 *)((char *)&v28 + 1), &pcbActual);
  if ( Value )
    goto LABEL_96;
  pcbActual = 4;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 360), v34, &pcbActual);
  if ( Value )
    goto LABEL_96;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &v36, &v34[1]);
  if ( Value )
    goto LABEL_96;
  v32[0] = 0;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 72), &lpMem, v32);
  if ( Value )
    goto LABEL_96;
  if ( !(unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, pvData.S_un.S_addr) )
  {
    if ( a5 || (unsigned int)DhcpDoDynDnsCheckDelete(pvData) )
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
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, v25);
            v23 = WPP_GLOBAL_Control;
          }
          goto LABEL_66;
        }
        if ( *(_DWORD *)(a8 + 4292) != 1 )
          goto LABEL_89;
      }
      v10 = 1;
    }
    else
    {
      Value = 0;
      if ( *(_DWORD *)(a8 + 4292) != 1 )
        goto LABEL_89;
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
      if ( (unsigned int)(*(_DWORD *)(a8 + 4308) - 4) <= 1 )
        DhcpMarkFailoverLease(*(_DWORD *)(DhcpGlobalClientTable + 312));
      v30 = time(0);
      v22 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 280), &v30, 4u);
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
      v30 = 0;
      v22 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 216), &v30, 4u);
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
LABEL_95:
      if ( !Value )
        goto LABEL_25;
      goto LABEL_96;
    }
LABEL_89:
    if ( a4 == 1 )
    {
      if ( (_BYTE)v28 == 2 )
        v26 = DhcpReleaseBootpAddress(pvData.S_un.S_addr);
      else
        v26 = DhcpReleaseAddress(pvData.S_un.S_addr);
      Value = v26;
      if ( v26 )
        Value = 0;
      goto LABEL_25;
    }
    goto LABEL_95;
  }
  v33 = 0;
  v32[1] = 8;
  if ( !(unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &v33, &v32[1]) && !v33 )
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
  memset_0(v37, 0, 0xD0u);
  v32[0] = 0;
  if ( !a4 )
  {
    v38 = DhcpGlobalThisServer;
    v39 = a8;
    GetLeaseInfo((int)v37, 0);
    v33 = DhcpCalculateTime(v32[0]);
    v9 = 1;
LABEL_18:
    Value = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, &pvData, v19, 0);
    if ( !Value )
    {
      Value = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), &v33, 8u);
      if ( a4 )
        DhcpDoDynDnsReservationWork(pvData.S_un.S_addr, (LPCWSTR)lpMem, (__int64)v36, v34[0] & 1);
      if ( !Value )
      {
        v18 = DhcpJetCommitUpdate();
LABEL_23:
        Value = v18;
        if ( !v18 )
          goto LABEL_24;
      }
    }
LABEL_96:
    v23 = WPP_GLOBAL_Control;
    goto LABEL_66;
  }
  v33 = 0;
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
      WPP_SF_D(v23[2], v24, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, v22);
      v23 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v30 = time(0);
    v22 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 280), &v30, 4u);
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
      v30 = 0;
      v22 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 216), &v30, 4u);
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
    WPP_SF_D(v23[2], 31, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, Value);
LABEL_26:
  if ( *(_DWORD *)(a8 + 4292) == 1 && (!Value || Value == 20019) && !v9 )
  {
    DhcpJetBeginTransaction();
    v20 = DhcpHandleFailoverRequest(a8, pvData.S_un.S_addr, v10, a6);
    v21 = v20;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_804ae326f0e43eade3e1b627638912e9_Traceguids, v20);
    if ( v21 )
      DhcpJetRollBack();
    else
      DhcpJetCommitTransaction();
    Value = 0;
  }
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( lpMem )
    HeapFree(gDhcpHeap, 0, lpMem);
  if ( v36 )
    HeapFree(gDhcpHeap, 0, v36);
  return Value;
}

```

## disassembly

```asm
0x1800083d0  mov     rax, rsp
0x1800083d3  mov     [rax+10h], rbx
0x1800083d7  mov     [rax+18h], rsi
0x1800083db  mov     [rax+20h], rdi
0x1800083df  push    rbp
0x1800083e0  push    r12
0x1800083e2  push    r13
0x1800083e4  push    r14
0x1800083e6  push    r15
0x1800083e8  lea     rbp, [rax-78h]
0x1800083ec  sub     rsp, 150h
0x1800083f3  mov     rax, cs:__security_cookie
0x1800083fa  xor     rax, rsp
0x1800083fd  mov     [rbp+70h+var_30], rax
0x180008401  mov     r14, [rbp+70h+arg_38]
0x180008408  xor     edi, edi
0x18000840a  mov     [rsp+170h+pvData], ecx
0x18000840e  mov     r13d, edi
0x180008411  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180008418  mov     byte ptr [rsp+170h+var_140], dil
0x18000841d  mov     [rsp+170h+lpMem], rdi
0x180008422  mov     r12d, edi
0x180008425  mov     byte ptr [rsp+170h+var_140+1], dil
0x18000842a  mov     r15d, edi
0x18000842d  mov     [rsp+170h+var_118+4], edi
0x180008431  mov     esi, r9d
0x180008434  mov     [rsp+170h+var_108], rdi
0x180008439  mov     [rsp+170h+var_130], edi
0x18000843d  mov     [rsp+170h+var_118], edi
0x180008441  mov     [rsp+170h+pcbActual], 1
0x180008449  call    cs:__imp_EnterCriticalSection
0x180008450  nop     dword ptr [rax+rax+00h]
0x180008455  call    DhcpJetBeginTransaction
0x18000845a  mov     ebx, eax
0x18000845c  test    eax, eax
0x18000845e  jnz     loc_180008BDA
0x180008464  mov     r8, cs:DhcpGlobalClientTable
0x18000846b  lea     r13d, [rdi+1]
0x18000846f  mov     rdx, cs:DhcpGlobalClientTableHandle
0x180008476  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000847d  mov     r8, [r8]
0x180008480  call    cs:__imp_JetSetCurrentIndex
0x180008487  nop     dword ptr [rax+rax+00h]
0x18000848c  mov     ecx, eax
0x18000848e  lea     rdx, aRemoveclienten; "RemoveClientEntry:SetCurrentIndex"
0x180008495  call    DhcpMapJetError
0x18000849a  mov     ebx, eax
0x18000849c  test    eax, eax
0x18000849e  jnz     loc_180008BDA
0x1800084a4  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800084ab  lea     r9d, [rdi+4]; cbData
0x1800084af  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800084b6  lea     r8, [rsp+170h+pvData]; pvData
0x1800084bb  mov     [rsp+170h+grbit], r13d; grbit
0x1800084c0  call    cs:__imp_JetMakeKey
0x1800084c7  nop     dword ptr [rax+rax+00h]
0x1800084cc  mov     ecx, eax
0x1800084ce  lea     rdx, aRemoveclienten_1; "RemoveClientEntry:MakeKey"
0x1800084d5  call    DhcpMapJetError
0x1800084da  mov     ebx, eax
0x1800084dc  test    eax, eax
0x1800084de  jnz     loc_180008BDA
0x1800084e4  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800084eb  mov     r8d, r13d; grbit
0x1800084ee  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800084f5  call    cs:__imp_JetSeek
0x1800084fc  nop     dword ptr [rax+rax+00h]
0x180008501  mov     ecx, eax
0x180008503  lea     rdx, aRemoveclienten_0; "RemoveClientEntry:Seek"
0x18000850a  call    DhcpMapJetError
0x18000850f  mov     ebx, eax
0x180008511  test    eax, eax
0x180008513  jnz     loc_180008BDA
0x180008519  mov     rcx, cs:DhcpGlobalClientTable
0x180008520  lea     r8, [rsp+170h+pcbActual]; pcbActual
0x180008525  lea     rdx, [rsp+170h+var_140]; pvData
0x18000852a  mov     ecx, [rcx+98h]; columnid
0x180008530  call    DhcpJetGetValue
0x180008535  test    eax, eax
0x180008537  jz      short loc_18000853E
0x180008539  mov     byte ptr [rsp+170h+var_140], r13b
0x18000853e  mov     rcx, cs:DhcpGlobalClientTable
0x180008545  lea     r8, [rsp+170h+pcbActual]; pcbActual
0x18000854a  lea     rdx, [rsp+170h+var_140+1]; pvData
0x18000854f  mov     ecx, [rcx+28h]; columnid
0x180008552  call    DhcpJetGetValue
0x180008557  mov     ebx, eax
0x180008559  test    eax, eax
0x18000855b  jnz     loc_180008BDA
0x180008561  mov     rcx, cs:DhcpGlobalClientTable
0x180008568  lea     r8, [rsp+170h+pcbActual]; pcbActual
0x18000856d  mov     [rsp+170h+pcbActual], 4
0x180008575  lea     rdx, [rsp+170h+var_118]; pvData
0x18000857a  mov     ecx, [rcx+168h]; columnid
0x180008580  call    DhcpJetGetValue
0x180008585  mov     ebx, eax
0x180008587  test    eax, eax
0x180008589  jnz     loc_180008BDA
0x18000858f  mov     rcx, cs:DhcpGlobalClientTable
0x180008596  lea     r8, [rsp+170h+var_118+4]; pcbActual
0x18000859b  lea     rdx, [rsp+170h+var_108]; pvData
0x1800085a0  mov     ecx, [rcx+18h]; columnid
0x1800085a3  call    DhcpJetGetValue
0x1800085a8  mov     ebx, eax
0x1800085aa  test    eax, eax
0x1800085ac  jnz     loc_180008BDA
0x1800085b2  mov     rcx, cs:DhcpGlobalClientTable
0x1800085b9  lea     r8, [rsp+170h+var_128]; pcbActual
0x1800085be  lea     rdx, [rsp+170h+lpMem]; pvData
0x1800085c3  mov     [rsp+170h+var_128], edi
0x1800085c7  mov     ecx, [rcx+48h]; columnid
0x1800085ca  call    DhcpJetGetValue
0x1800085cf  mov     ebx, eax
0x1800085d1  test    eax, eax
0x1800085d3  jnz     loc_180008BDA
0x1800085d9  mov     edx, [rsp+170h+pvData]
0x1800085dd  mov     rcx, cs:DhcpGlobalThisServer
0x1800085e4  call    MemServerIsReservedAddress
0x1800085e9  test    eax, eax
0x1800085eb  jz      loc_180008938
0x1800085f1  mov     rcx, cs:DhcpGlobalClientTable
0x1800085f8  lea     r8, [rsp+170h+var_128+4]; pcbActual
0x1800085fd  lea     rdx, [rsp+170h+var_120]; pvData
0x180008602  mov     qword ptr [rsp+170h+var_120], rdi
0x180008607  mov     [rsp+170h+var_128+4], 8
0x18000860f  mov     ecx, [rcx+58h]; columnid
0x180008612  call    DhcpJetGetValue
0x180008617  test    eax, eax
0x180008619  jnz     short loc_180008663
0x18000861b  cmp     [rsp+170h+var_120], edi
0x18000861f  jnz     short loc_180008663
0x180008621  cmp     [rsp+170h+var_11C], edi
0x180008625  jnz     short loc_180008663
0x180008627  mov     r12d, r13d
0x18000862a  cmp     [rbp+70h+arg_30], edi
0x180008630  jz      loc_18000873E
0x180008636  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000863d  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180008644  call    cs:__imp_JetDelete
0x18000864b  nop     dword ptr [rax+rax+00h]
0x180008650  mov     ecx, eax
0x180008652  lea     rdx, aRemoveclienten_2; "RemoveClientEntry:Delete"
0x180008659  call    DhcpMapJetError
0x18000865e  jmp     loc_180008734
0x180008663  xor     edx, edx; Val
0x180008665  lea     rcx, [rsp+170h+var_100]; void *
0x18000866a  mov     r8d, 0D0h; Size
0x180008670  call    memset_0
0x180008675  mov     [rsp+170h+var_128], edi
0x180008679  test    esi, esi
0x18000867b  jnz     loc_1800087CF
0x180008681  mov     rax, cs:DhcpGlobalThisServer
0x180008688  lea     rdx, [rsp+170h+var_128]
0x18000868d  xor     r9d, r9d
0x180008690  mov     [rbp+70h+var_B0], rax
0x180008694  xor     r8d, r8d
0x180008697  mov     [rbp+70h+var_A8], r14
0x18000869b  lea     rcx, [rsp+170h+var_100]; int
0x1800086a0  mov     qword ptr [rsp+170h+grbit], rdi; __int64
0x1800086a5  call    GetLeaseInfo
0x1800086aa  mov     ecx, [rsp+170h+var_128]
0x1800086ae  call    DhcpCalculateTime
0x1800086b3  mov     qword ptr [rsp+170h+var_120], rax
0x1800086b8  mov     r12d, r13d
0x1800086bb  mov     rcx, cs:DhcpGlobalClientTable
0x1800086c2  lea     rdx, [rsp+170h+pvData]
0x1800086c7  xor     r9d, r9d
0x1800086ca  mov     rcx, [rcx]
0x1800086cd  call    DhcpJetPrepareUpdate
0x1800086d2  mov     ebx, eax
0x1800086d4  test    eax, eax
0x1800086d6  jnz     loc_180008BDA
0x1800086dc  mov     rcx, cs:DhcpGlobalClientTable
0x1800086e3  lea     r8d, [rax+8]; cbData
0x1800086e7  lea     rdx, [rsp+170h+var_120]; pvData
0x1800086ec  mov     ecx, [rcx+58h]; columnid
0x1800086ef  call    DhcpJetSetValue
0x1800086f4  mov     ebx, eax
0x1800086f6  test    esi, esi
0x1800086f8  jz      short loc_180008727
0x1800086fa  mov     eax, [rsp+170h+var_118]
0x1800086fe  mov     r9d, [rsp+170h+var_118+4]
0x180008703  and     eax, r13d
0x180008706  mov     r8b, byte ptr [rsp+170h+var_140+1]
0x18000870b  mov     rdx, [rsp+170h+lpMem]; lpSrcStr
0x180008710  mov     ecx, [rsp+170h+pvData]; hostlong
0x180008714  mov     [rsp+170h+var_148], eax; int
0x180008718  mov     rax, [rsp+170h+var_108]
0x18000871d  mov     qword ptr [rsp+170h+grbit], rax; __int64
0x180008722  call    DhcpDoDynDnsReservationWork
0x180008727  test    ebx, ebx
0x180008729  jnz     loc_180008BDA
0x18000872f  call    DhcpJetCommitUpdate
0x180008734  mov     ebx, eax
0x180008736  test    eax, eax
0x180008738  jnz     loc_180008BDA
0x18000873e  mov     ebx, 4E33h
0x180008743  call    DhcpJetCommitTransaction
0x180008748  lea     rsi, WPP_GLOBAL_Control
0x18000874f  cmp     dword ptr [r14+10C4h], 1
0x180008757  jnz     loc_180008BF4
0x18000875d  test    ebx, ebx
0x18000875f  jz      short loc_18000876D
0x180008761  cmp     ebx, 4E33h
0x180008767  jnz     loc_180008BF4
0x18000876d  test    r12d, r12d
0x180008770  jnz     loc_180008BF4
0x180008776  call    DhcpJetBeginTransaction
0x18000877b  mov     r9d, [rbp+70h+arg_28]
0x180008782  mov     r8d, r15d
0x180008785  mov     edx, [rsp+170h+pvData]
0x180008789  mov     rcx, r14
0x18000878c  call    DhcpHandleFailoverRequest
0x180008791  mov     ebx, eax
0x180008793  mov     rcx, cs:WPP_GLOBAL_Control
0x18000879a  cmp     rcx, rsi
0x18000879d  jz      short loc_1800087BD
0x18000879f  test    byte ptr [rcx+1Ch], 10h
0x1800087a3  jz      short loc_1800087BD
0x1800087a5  mov     rcx, [rcx+10h]
0x1800087a9  lea     edx, [r12+20h]
0x1800087ae  mov     r9d, eax
0x1800087b1  lea     r8, WPP_804ae326f0e43eade3e1b627638912e9_Traceguids
0x1800087b8  call    WPP_SF_D
0x1800087bd  test    ebx, ebx
0x1800087bf  jnz     loc_180008BED
0x1800087c5  call    DhcpJetCommitTransaction
0x1800087ca  jmp     loc_180008BF2
0x1800087cf  mov     qword ptr [rsp+170h+var_120], rdi
0x1800087d4  cmp     [r14+10C4h], r13d
0x1800087db  jnz     loc_1800086BB
0x1800087e1  mov     rcx, cs:DhcpGlobalClientTable
0x1800087e8  lea     rdx, [rsp+170h+pvData]
0x1800087ed  xor     r9d, r9d
0x1800087f0  mov     rcx, [rcx]
0x1800087f3  call    DhcpJetPrepareUpdate
0x1800087f8  mov     ebx, eax
0x1800087fa  test    eax, eax
0x1800087fc  jz      short loc_180008846
0x1800087fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180008805  lea     rsi, WPP_GLOBAL_Control
0x18000880c  cmp     rcx, rsi
0x18000880f  jz      loc_180008A2C
0x180008815  test    dword ptr [rcx+1Ch], 800000h
0x18000881c  jz      loc_180008A2C
0x180008822  mov     edx, 16h
0x180008827  mov     rcx, [rcx+10h]
0x18000882b  lea     r8, WPP_804ae326f0e43eade3e1b627638912e9_Traceguids
0x180008832  mov     r9d, eax
0x180008835  call    WPP_SF_D
0x18000883a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008841  jmp     loc_180008A2C
0x180008846  xor     ecx, ecx; Time
0x180008848  call    cs:__imp_time
0x18000884f  nop     dword ptr [rax+rax+00h]
0x180008854  mov     rcx, cs:DhcpGlobalClientTable
0x18000885b  lea     rdx, [rsp+170h+var_130]; pvData
0x180008860  mov     [rsp+170h+var_130], eax
0x180008864  mov     r8d, 4; cbData
0x18000886a  mov     ecx, [rcx+118h]; columnid
0x180008870  call    DhcpJetSetValue
0x180008875  mov     ebx, eax
0x180008877  test    eax, eax
0x180008879  jz      short loc_1800088A6
0x18000887b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008882  lea     rsi, WPP_GLOBAL_Control
0x180008889  cmp     rcx, rsi
0x18000888c  jz      loc_180008A2C
0x180008892  test    dword ptr [rcx+1Ch], 800000h
0x180008899  jz      loc_180008A2C
0x18000889f  mov     edx, 17h
0x1800088a4  jmp     short loc_180008827
0x1800088a6  mov     rcx, cs:DhcpGlobalClientTable
0x1800088ad  lea     rdx, [rsp+170h+var_130]; pvData
0x1800088b2  mov     [rsp+170h+var_130], edi
0x1800088b6  mov     r8d, 4; cbData
0x1800088bc  mov     ecx, [rcx+0D8h]; columnid
0x1800088c2  call    DhcpJetSetValue
0x1800088c7  mov     ebx, eax
0x1800088c9  test    eax, eax
0x1800088cb  jz      short loc_1800088FB
0x1800088cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088d4  lea     rsi, WPP_GLOBAL_Control
0x1800088db  cmp     rcx, rsi
0x1800088de  jz      loc_180008A2C
0x1800088e4  test    dword ptr [rcx+1Ch], 800000h
0x1800088eb  jz      loc_180008A2C
0x1800088f1  mov     edx, 18h
0x1800088f6  jmp     loc_180008827
0x1800088fb  call    DhcpJetCommitUpdate
0x180008900  mov     ebx, eax
0x180008902  test    eax, eax
0x180008904  jz      loc_1800086BB
0x18000890a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008911  lea     rsi, WPP_GLOBAL_Control
0x180008918  cmp     rcx, rsi
0x18000891b  jz      loc_180008A2C
0x180008921  test    dword ptr [rcx+1Ch], 800000h
0x180008928  jz      loc_180008A2C
0x18000892e  mov     edx, 19h
  ... truncated ...
```
