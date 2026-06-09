# CleanupMCastDatabase

- ea: `0x18002955c`
- end: `0x180029ab0`
- name: `CleanupMCastDatabase`
- size: `1364`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180050260`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000c180`
- `0x18000f144`
- `0x180028df4`
- `0x180028e28`
- `0x180028fac`
- `0x1800290c4`
- `0x1800292f4`
- `0x180029324`
- `0x18002955c`
- `0x180031dc4`
- `0x18008f3f0`

## import_xrefs

- `ESENT!JetUpdate` at `0x1800298e2`
- `ESENT!JetUpdate` at `0x1800298e2`
- `ESENT!JetSetCurrentIndex` at `0x1800296bd`
- `ESENT!JetSetCurrentIndex` at `0x1800296bd`
- `ESENT!JetMakeKey` at `0x1800296fd`
- `ESENT!JetMakeKey` at `0x1800296fd`
- `ESENT!JetSeek` at `0x180029731`
- `ESENT!JetSeek` at `0x180029731`
- `ESENT!JetDelete` at `0x1800299ad`
- `ESENT!JetDelete` at `0x1800299ad`
- `ESENT!JetBeginTransaction` at `0x18002985a`
- `ESENT!JetBeginTransaction` at `0x180029985`
- `ESENT!JetBeginTransaction` at `0x18002985a`
- `ESENT!JetBeginTransaction` at `0x180029985`
- `ESENT!JetPrepareUpdate` at `0x180029890`
- `ESENT!JetPrepareUpdate` at `0x180029890`
- `KERNEL32!WaitForSingleObject` at `0x180029675`
- `KERNEL32!WaitForSingleObject` at `0x180029a71`
- `KERNEL32!WaitForSingleObject` at `0x180029675`
- `KERNEL32!WaitForSingleObject` at `0x180029a71`
- `KERNEL32!CompareFileTime` at `0x1800297df`
- `KERNEL32!CompareFileTime` at `0x180029806`
- `KERNEL32!CompareFileTime` at `0x1800297df`
- `KERNEL32!CompareFileTime` at `0x180029806`
- `KERNEL32!EnterCriticalSection` at `0x1800295fb`
- `KERNEL32!EnterCriticalSection` at `0x180029694`
- `KERNEL32!EnterCriticalSection` at `0x1800295fb`
- `KERNEL32!EnterCriticalSection` at `0x180029694`
- `KERNEL32!LeaveCriticalSection` at `0x18002965e`
- `KERNEL32!LeaveCriticalSection` at `0x180029a5a`
- `KERNEL32!LeaveCriticalSection` at `0x180029a90`
- `KERNEL32!LeaveCriticalSection` at `0x18002965e`
- `KERNEL32!LeaveCriticalSection` at `0x180029a5a`
- `KERNEL32!LeaveCriticalSection` at `0x180029a90`

## string_xrefs

- `0x1800298f0`: `M:CommitUpdate`
- `0x1800299bb`: `M:DeleteCurrentRecord`
- `0x18002989e`: `M:Cleanup:PrepUpdate`

## pseudocode

```c
__int64 __fastcall CleanupMCastDatabase(const FILETIME *a1, const FILETIME *a2, int a3, _DWORD *a4, _DWORD *a5)
{
  unsigned int v6; // esi
  JET_SESID v7; // r14
  JET_TABLEID v8; // r13
  _DWORD *v9; // r12
  int v10; // edi
  unsigned int v11; // eax
  unsigned int Key; // eax
  unsigned int v13; // eax
  unsigned int Value; // ebx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v22; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-34h] BYREF
  int pvData; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v25; // [rsp+3Ch] [rbp-2Ch] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-28h] BYREF
  __int128 v27; // [rsp+48h] [rbp-20h] BYREF
  JET_TABLEID v28; // [rsp+58h] [rbp-10h]
  char v32; // [rsp+C8h] [rbp+60h] BYREF

  FileTime1 = 0;
  LODWORD(v28) = 0;
  v22 = 0;
  v6 = 0;
  v23 = 0;
  pvData = 0;
  v32 = 0;
  v27 = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids);
  v7 = DhcpGlobalJetServerSession;
  v8 = MadcapGlobalClientTableHandle;
  v9 = a5;
  *a4 = 0;
  *((_QWORD *)&v27 + 1) = v7;
  v28 = v8;
  *v9 = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( (unsigned int)MadcapJetPrepareSearch(&v27, *(_QWORD *)MadcapGlobalClientTable, 1)
    || (v22 = 4, (unsigned int)MadcapJetGetValue(&v27, *(unsigned int *)(MadcapGlobalClientTable + 8), &pvData, &v22)) )
  {
LABEL_42:
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  }
  else
  {
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    if ( WaitForSingleObject(DhcpGlobalProcessTerminationEvent, 0) )
    {
      while ( 1 )
      {
        EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
        v10 = 1;
        v11 = JetSetCurrentIndex(
                DhcpGlobalJetServerSession,
                MadcapGlobalClientTableHandle,
                *(_QWORD *)MadcapGlobalClientTable);
        if ( (unsigned int)DhcpMapJetError(v11, "M:Cleanup:SetcurrentIndex") )
          goto LABEL_42;
        Key = JetMakeKey(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle, &pvData, 4u, 1u);
        if ( (unsigned int)DhcpMapJetError(Key, "M:Cleanup:MakeKey")
          || (v13 = JetSeek(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle, 8u),
              (unsigned int)DhcpMapJetError(v13, "M:Cleanup:Seek")) )
        {
LABEL_41:
          if ( !v10 )
            return v6;
          goto LABEL_42;
        }
        v22 = 4;
        Value = MadcapJetGetValue(&v27, *(unsigned int *)(MadcapGlobalClientTable + 8), &v23, &v22);
        if ( Value )
          break;
        v22 = 4;
        Value = MadcapJetGetValue(&v27, *(unsigned int *)(MadcapGlobalClientTable + 88), &v25, &v22);
        if ( Value )
          break;
        v22 = 8;
        Value = MadcapJetGetValue(&v27, *(unsigned int *)(MadcapGlobalClientTable + 120), &FileTime1, &v22);
        if ( Value )
          break;
        if ( CompareFileTime(&FileTime1, a1) < 0 )
        {
          if ( a3 || CompareFileTime(&FileTime1, a2) < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v18 = DhcpIpAddressToDottedString(v23);
              WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, v18);
            }
            if ( !(unsigned int)DhcpMScopeReleaseAddress(v25, v23) )
            {
              v19 = JetBeginTransaction(v7);
              if ( (unsigned int)DhcpMapJetError(v19, "M:BeginTransaction") )
                goto LABEL_41;
              v20 = JetDelete(v7, v8);
              if ( !(unsigned int)DhcpMapJetError(v20, "M:DeleteCurrentRecord") )
              {
                if ( (unsigned int)MadcapJetCommitTransaction(&v27) )
                  goto LABEL_41;
                ++*v9;
                goto LABEL_38;
              }
LABEL_24:
              if ( (unsigned int)MadcapJetRollBack(&v27) )
                goto LABEL_41;
            }
          }
          else
          {
            v22 = 1;
            Value = MadcapJetGetValue(&v27, *(unsigned int *)(MadcapGlobalClientTable + 56), &v32, &v22);
            if ( Value )
              break;
            if ( (v32 & 3) != 3 )
            {
              v15 = JetBeginTransaction(v7);
              if ( (unsigned int)DhcpMapJetError(v15, "M:BeginTransaction") )
                goto LABEL_41;
              v16 = JetPrepareUpdate(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle, 2u);
              if ( (unsigned int)DhcpMapJetError(v16, "M:Cleanup:PrepUpdate") )
                goto LABEL_24;
              v32 |= 3u;
              if ( (unsigned int)MadcapJetSetValue(&v27, *(unsigned int *)(MadcapGlobalClientTable + 56), &v32, 1) )
                goto LABEL_24;
              v17 = JetUpdate(v7, v8, 0, 0, 0);
              if ( (unsigned int)DhcpMapJetError(v17, "M:CommitUpdate") )
                goto LABEL_24;
              if ( (unsigned int)MadcapJetCommitTransaction(&v27) )
                goto LABEL_41;
              ++*a4;
            }
          }
        }
LABEL_38:
        if ( !(unsigned int)MadcapJetNextRecord(&v27) )
        {
          v22 = 4;
          if ( !(unsigned int)MadcapJetGetValue(&v27, *(unsigned int *)(MadcapGlobalClientTable + 8), &pvData, &v22) )
          {
            LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
            v10 = 0;
            if ( WaitForSingleObject(DhcpGlobalProcessTerminationEvent, 0) )
              continue;
          }
        }
        goto LABEL_41;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, Value);
      v6 = Value;
      goto LABEL_38;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18002955c  mov     [rsp-40h+arg_10], r8d
0x180029561  mov     [rsp-40h+arg_8], rdx
0x180029566  mov     [rsp-40h+lpFileTime2], rcx
0x18002956b  push    rbp
0x18002956c  push    rbx
0x18002956d  push    rsi
0x18002956e  push    rdi
0x18002956f  push    r12
0x180029571  push    r13
0x180029573  push    r14
0x180029575  push    r15
0x180029577  mov     rbp, rsp
0x18002957a  sub     rsp, 68h
0x18002957e  xor     ebx, ebx
0x180029580  xorps   xmm0, xmm0
0x180029583  xor     eax, eax
0x180029585  mov     qword ptr [rbp+FileTime1.dwLowDateTime], rbx
0x180029589  mov     dword ptr [rbp+var_10], eax
0x18002958c  mov     r15, r9
0x18002958f  mov     [rbp+var_38], ebx
0x180029592  mov     esi, ebx
0x180029594  mov     [rbp+var_34], ebx
0x180029597  mov     [rbp+pvData], ebx
0x18002959a  mov     [rbp+arg_18], bl
0x18002959d  movups  [rbp+var_20], xmm0
0x1800295a1  mov     [rbp+var_2C], ebx
0x1800295a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800295ab  lea     rax, WPP_GLOBAL_Control
0x1800295b2  cmp     rcx, rax
0x1800295b5  jz      short loc_1800295D3
0x1800295b7  test    dword ptr [rcx+1Ch], 8000h
0x1800295be  jz      short loc_1800295D3
0x1800295c0  mov     rcx, [rcx+10h]
0x1800295c4  lea     edx, [rbx+1Ch]
0x1800295c7  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x1800295ce  call    WPP_SF_
0x1800295d3  mov     r14, cs:DhcpGlobalJetServerSession
0x1800295da  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800295e1  mov     r13, cs:MadcapGlobalClientTableHandle
0x1800295e8  mov     r12, [rbp+arg_20]
0x1800295ec  mov     [r15], ebx
0x1800295ef  mov     qword ptr [rbp+var_20+8], r14
0x1800295f3  mov     [rbp+var_10], r13
0x1800295f7  mov     [r12], ebx
0x1800295fb  call    cs:__imp_EnterCriticalSection
0x180029602  nop     dword ptr [rax+rax+00h]
0x180029607  mov     rdx, cs:MadcapGlobalClientTable
0x18002960e  lea     rcx, [rbp+var_20]
0x180029612  xor     r9d, r9d
0x180029615  mov     [rsp+68h+grbit], ebx
0x180029619  mov     rdx, [rdx]
0x18002961c  lea     r8d, [r9+1]
0x180029620  call    MadcapJetPrepareSearch
0x180029625  test    eax, eax
0x180029627  jnz     loc_180029A89
0x18002962d  mov     rdx, cs:MadcapGlobalClientTable
0x180029634  lea     r9, [rbp+var_38]
0x180029638  mov     [rbp+var_38], 4
0x18002963f  lea     r8, [rbp+pvData]
0x180029643  lea     rcx, [rbp+var_20]
0x180029647  mov     edx, [rdx+8]
0x18002964a  call    MadcapJetGetValue
0x18002964f  test    eax, eax
0x180029651  jnz     loc_180029A89
0x180029657  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18002965e  call    cs:__imp_LeaveCriticalSection
0x180029665  nop     dword ptr [rax+rax+00h]
0x18002966a  mov     rcx, cs:DhcpGlobalProcessTerminationEvent; hHandle
0x180029671  xor     edx, edx; dwMilliseconds
0x180029673  mov     edi, ebx
0x180029675  call    cs:__imp_WaitForSingleObject
0x18002967c  nop     dword ptr [rax+rax+00h]
0x180029681  test    eax, eax
0x180029683  jz      loc_180029A9C
0x180029689  test    edi, edi
0x18002968b  jnz     short loc_1800296A5
0x18002968d  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029694  call    cs:__imp_EnterCriticalSection
0x18002969b  nop     dword ptr [rax+rax+00h]
0x1800296a0  mov     edi, 1
0x1800296a5  mov     r8, cs:MadcapGlobalClientTable
0x1800296ac  mov     rdx, cs:MadcapGlobalClientTableHandle
0x1800296b3  mov     rcx, cs:DhcpGlobalJetServerSession
0x1800296ba  mov     r8, [r8]
0x1800296bd  call    cs:__imp_JetSetCurrentIndex
0x1800296c4  nop     dword ptr [rax+rax+00h]
0x1800296c9  mov     ecx, eax
0x1800296cb  lea     rdx, aMCleanupSetcur; "M:Cleanup:SetcurrentIndex"
0x1800296d2  call    DhcpMapJetError
0x1800296d7  test    eax, eax
0x1800296d9  jnz     loc_180029A89
0x1800296df  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x1800296e6  lea     r9d, [rax+4]; cbData
0x1800296ea  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800296f1  lea     r8, [rbp+pvData]; pvData
0x1800296f5  mov     [rsp+68h+grbit], 1; grbit
0x1800296fd  call    cs:__imp_JetMakeKey
0x180029704  nop     dword ptr [rax+rax+00h]
0x180029709  mov     ecx, eax
0x18002970b  lea     rdx, aMCleanupMakeke; "M:Cleanup:MakeKey"
0x180029712  call    DhcpMapJetError
0x180029717  test    eax, eax
0x180029719  jnz     loc_180029A85
0x18002971f  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x180029726  lea     r8d, [rax+8]; grbit
0x18002972a  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180029731  call    cs:__imp_JetSeek
0x180029738  nop     dword ptr [rax+rax+00h]
0x18002973d  mov     ecx, eax
0x18002973f  lea     rdx, aMCleanupSeek; "M:Cleanup:Seek"
0x180029746  call    DhcpMapJetError
0x18002974b  test    eax, eax
0x18002974d  jnz     loc_180029A85
0x180029753  mov     rdx, cs:MadcapGlobalClientTable
0x18002975a  lea     r9, [rbp+var_38]
0x18002975e  mov     [rbp+var_38], 4
0x180029765  lea     r8, [rbp+var_34]
0x180029769  lea     rcx, [rbp+var_20]
0x18002976d  mov     edx, [rdx+8]
0x180029770  call    MadcapJetGetValue
0x180029775  mov     ebx, eax
0x180029777  test    eax, eax
0x180029779  jnz     loc_1800299E6
0x18002977f  mov     rdx, cs:MadcapGlobalClientTable
0x180029786  lea     r9, [rbp+var_38]
0x18002978a  mov     [rbp+var_38], 4
0x180029791  lea     r8, [rbp+var_2C]
0x180029795  lea     rcx, [rbp+var_20]
0x180029799  mov     edx, [rdx+58h]
0x18002979c  call    MadcapJetGetValue
0x1800297a1  mov     ebx, eax
0x1800297a3  test    eax, eax
0x1800297a5  jnz     loc_1800299E6
0x1800297ab  mov     rdx, cs:MadcapGlobalClientTable
0x1800297b2  lea     r9, [rbp+var_38]
0x1800297b6  mov     [rbp+var_38], 8
0x1800297bd  lea     r8, [rbp+FileTime1]
0x1800297c1  lea     rcx, [rbp+var_20]
0x1800297c5  mov     edx, [rdx+78h]
0x1800297c8  call    MadcapJetGetValue
0x1800297cd  mov     ebx, eax
0x1800297cf  test    eax, eax
0x1800297d1  jnz     loc_1800299E6
0x1800297d7  mov     rdx, [rbp+lpFileTime2]; lpFileTime2
0x1800297db  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800297df  call    cs:__imp_CompareFileTime
0x1800297e6  nop     dword ptr [rax+rax+00h]
0x1800297eb  xor     ebx, ebx
0x1800297ed  test    eax, eax
0x1800297ef  jns     loc_180029A1B
0x1800297f5  cmp     [rbp+arg_10], ebx
0x1800297f8  jnz     loc_18002992F
0x1800297fe  mov     rdx, [rbp+arg_8]; lpFileTime2
0x180029802  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x180029806  call    cs:__imp_CompareFileTime
0x18002980d  nop     dword ptr [rax+rax+00h]
0x180029812  test    eax, eax
0x180029814  js      loc_18002992F
0x18002981a  mov     rdx, cs:MadcapGlobalClientTable
0x180029821  lea     r9, [rbp+var_38]
0x180029825  mov     [rbp+var_38], 1
0x18002982c  lea     r8, [rbp+arg_18]
0x180029830  lea     rcx, [rbp+var_20]
0x180029834  mov     edx, [rdx+38h]
0x180029837  call    MadcapJetGetValue
0x18002983c  mov     ebx, eax
0x18002983e  test    eax, eax
0x180029840  jnz     loc_1800299E6
0x180029846  movzx   eax, [rbp+arg_18]
0x18002984a  and     eax, 0FFFFFF03h
0x18002984f  cmp     al, 3
0x180029851  jz      loc_180029A19
0x180029857  mov     rcx, r14; sesid
0x18002985a  call    cs:__imp_JetBeginTransaction
0x180029861  nop     dword ptr [rax+rax+00h]
0x180029866  mov     ecx, eax
0x180029868  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x18002986f  call    DhcpMapJetError
0x180029874  xor     ebx, ebx
0x180029876  test    eax, eax
0x180029878  jnz     loc_180029A85
0x18002987e  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x180029885  lea     r8d, [rbx+2]; prep
0x180029889  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180029890  call    cs:__imp_JetPrepareUpdate
0x180029897  nop     dword ptr [rax+rax+00h]
0x18002989c  mov     ecx, eax
0x18002989e  lea     rdx, aMCleanupPrepup; "M:Cleanup:PrepUpdate"
0x1800298a5  call    DhcpMapJetError
0x1800298aa  test    eax, eax
0x1800298ac  jnz     short loc_180029919
0x1800298ae  mov     rdx, cs:MadcapGlobalClientTable
0x1800298b5  lea     r9d, [rbx+1]
0x1800298b9  or      [rbp+arg_18], 3
0x1800298bd  lea     r8, [rbp+arg_18]
0x1800298c1  lea     rcx, [rbp+var_20]
0x1800298c5  mov     edx, [rdx+38h]
0x1800298c8  call    MadcapJetSetValue
0x1800298cd  test    eax, eax
0x1800298cf  jnz     short loc_180029919
0x1800298d1  xor     r9d, r9d; cbBookmark
0x1800298d4  mov     qword ptr [rsp+68h+grbit], rbx; pcbActual
0x1800298d9  xor     r8d, r8d; pvBookmark
0x1800298dc  mov     rdx, r13; tableid
0x1800298df  mov     rcx, r14; sesid
0x1800298e2  call    cs:__imp_JetUpdate
0x1800298e9  nop     dword ptr [rax+rax+00h]
0x1800298ee  mov     ecx, eax
0x1800298f0  lea     rdx, aMCommitupdate; "M:CommitUpdate"
0x1800298f7  call    DhcpMapJetError
0x1800298fc  test    eax, eax
0x1800298fe  jnz     short loc_180029919
0x180029900  lea     rcx, [rbp+var_20]
0x180029904  call    MadcapJetCommitTransaction
0x180029909  test    eax, eax
0x18002990b  jnz     loc_180029A85
0x180029911  inc     dword ptr [r15]
0x180029914  jmp     loc_180029A1B
0x180029919  lea     rcx, [rbp+var_20]
0x18002991d  call    MadcapJetRollBack
0x180029922  test    eax, eax
0x180029924  jnz     loc_180029A85
0x18002992a  jmp     loc_180029A1B
0x18002992f  mov     rax, cs:WPP_GLOBAL_Control
0x180029936  lea     rcx, WPP_GLOBAL_Control
0x18002993d  cmp     rax, rcx
0x180029940  jz      short loc_18002996F
0x180029942  test    byte ptr [rax+1Ch], 80h
0x180029946  jz      short loc_18002996F
0x180029948  mov     ecx, [rbp+var_34]
0x18002994b  call    DhcpIpAddressToDottedString
0x180029950  mov     rcx, cs:WPP_GLOBAL_Control
0x180029957  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x18002995e  mov     r9, rax
0x180029961  mov     edx, 1Dh
0x180029966  mov     rcx, [rcx+10h]
0x18002996a  call    WPP_SF_s
0x18002996f  mov     edx, [rbp+var_34]
0x180029972  mov     ecx, [rbp+var_2C]
0x180029975  call    DhcpMScopeReleaseAddress
0x18002997a  test    eax, eax
0x18002997c  jnz     loc_180029A1B
0x180029982  mov     rcx, r14; sesid
0x180029985  call    cs:__imp_JetBeginTransaction
0x18002998c  nop     dword ptr [rax+rax+00h]
0x180029991  mov     ecx, eax
0x180029993  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x18002999a  call    DhcpMapJetError
0x18002999f  test    eax, eax
0x1800299a1  jnz     loc_180029A85
0x1800299a7  mov     rdx, r13; tableid
0x1800299aa  mov     rcx, r14; sesid
0x1800299ad  call    cs:__imp_JetDelete
0x1800299b4  nop     dword ptr [rax+rax+00h]
0x1800299b9  mov     ecx, eax
0x1800299bb  lea     rdx, aMDeletecurrent; "M:DeleteCurrentRecord"
0x1800299c2  call    DhcpMapJetError
0x1800299c7  lea     rcx, [rbp+var_20]
0x1800299cb  test    eax, eax
0x1800299cd  jnz     loc_18002991D
0x1800299d3  call    MadcapJetCommitTransaction
0x1800299d8  test    eax, eax
0x1800299da  jnz     loc_180029A85
0x1800299e0  inc     dword ptr [r12]
0x1800299e4  jmp     short loc_180029A1B
0x1800299e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800299ed  lea     rax, WPP_GLOBAL_Control
0x1800299f4  cmp     rcx, rax
0x1800299f7  jz      short loc_180029A17
0x1800299f9  test    byte ptr [rcx+1Ch], 10h
0x1800299fd  jz      short loc_180029A17
0x1800299ff  mov     rcx, [rcx+10h]
0x180029a03  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029a0a  mov     edx, 1Eh
0x180029a0f  mov     r9d, ebx
0x180029a12  call    WPP_SF_D
0x180029a17  mov     esi, ebx
0x180029a19  xor     ebx, ebx
0x180029a1b  lea     rcx, [rbp+var_20]
0x180029a1f  call    MadcapJetNextRecord
0x180029a24  test    eax, eax
0x180029a26  jnz     short loc_180029A85
0x180029a28  mov     rdx, cs:MadcapGlobalClientTable
0x180029a2f  lea     r9, [rbp+var_38]
0x180029a33  mov     [rbp+var_38], 4
0x180029a3a  lea     r8, [rbp+pvData]
0x180029a3e  lea     rcx, [rbp+var_20]
0x180029a42  mov     edx, [rdx+8]
0x180029a45  call    MadcapJetGetValue
0x180029a4a  test    eax, eax
0x180029a4c  jnz     short loc_180029A85
0x180029a4e  cmp     edi, 1
0x180029a51  jnz     short loc_180029A68
0x180029a53  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029a5a  call    cs:__imp_LeaveCriticalSection
0x180029a61  nop     dword ptr [rax+rax+00h]
0x180029a66  mov     edi, ebx
0x180029a68  mov     rcx, cs:DhcpGlobalProcessTerminationEvent; hHandle
0x180029a6f  xor     edx, edx; dwMilliseconds
0x180029a71  call    cs:__imp_WaitForSingleObject
  ... truncated ...
```
