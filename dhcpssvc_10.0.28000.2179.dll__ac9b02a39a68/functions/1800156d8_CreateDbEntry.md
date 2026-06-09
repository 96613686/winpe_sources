# CreateDbEntry

- ea: `0x1800156d8`
- end: `0x180015a6a`
- name: `CreateDbEntry`
- size: `914`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `10`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000fb40`
- `0x180015614`
- `0x180015a70`
- `0x180015b3c`
- `0x180015c2c`
- `0x180015d40`
- `0x180015e54`
- `0x180015f34`
- `0x1800163c0`
- `0x180016b74`

## callees

- `0x18000282c`
- `0x18000e814`
- `0x180010e3c`
- `0x1800156d8`
- `0x180016d44`
- `0x1800178a8`

## import_xrefs

- `ESENT!JetUpdate` at `0x1800159cf`
- `ESENT!JetUpdate` at `0x1800159cf`
- `ESENT!JetBeginTransaction` at `0x180015787`
- `ESENT!JetBeginTransaction` at `0x180015787`
- `ESENT!JetRollback` at `0x18001586b`
- `ESENT!JetRollback` at `0x18001586b`
- `ESENT!JetCommitTransaction` at `0x1800159f8`
- `ESENT!JetCommitTransaction` at `0x1800159f8`
- `ESENT!JetPrepareUpdate` at `0x1800157ee`
- `ESENT!JetPrepareUpdate` at `0x1800157ee`
- `ESENT!JetSetColumn` at `0x18001597e`
- `ESENT!JetSetColumn` at `0x18001597e`
- `KERNEL32!EnterCriticalSection` at `0x180015702`
- `KERNEL32!EnterCriticalSection` at `0x180015702`
- `KERNEL32!LeaveCriticalSection` at `0x1800157ae`
- `KERNEL32!LeaveCriticalSection` at `0x18001587e`
- `KERNEL32!LeaveCriticalSection` at `0x1800157ae`
- `KERNEL32!LeaveCriticalSection` at `0x18001587e`

## string_xrefs

- `0x1800157fc`: `C:JetPrepareUpdate`
- `0x1800159dd`: `C:CommitUpdate`
- `0x180015a06`: `C:JetCommitTransaction`

## pseudocode

```c
__int64 __fastcall CreateDbEntry(JET_SESID sesid, _DWORD *a2)
{
  int v4; // edx
  unsigned int v5; // eax
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  unsigned int v13; // r14d
  unsigned __int64 cbData; // rcx
  _QWORD *v15; // r9
  _QWORD *v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax

  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  ++a2[1];
  while ( !(unsigned int)FindRecord(sesid) )
  {
    if ( ++a2[1] == -1 )
      a2[1] = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      (unsigned int)&_ImageBase,
      a2[2],
      (__int64)EntryTypes[a2[2]],
      a2[1]);
  *a2 |= 1u;
  v5 = JetBeginTransaction(sesid);
  v6 = DhcpMapJetError(v5, "C:JetBeginTransaction");
  if ( v6 )
  {
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      v8 = 23;
LABEL_24:
      WPP_SF_D(v7[2], v8, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v6);
      return v6;
    }
    return v6;
  }
  v9 = JetPrepareUpdate(sesid, DbcfgTbl, 0);
  v10 = DhcpMapJetError(v9, "C:JetPrepareUpdate");
  v6 = v10;
  if ( !v10 )
  {
    v13 = 0;
    while ( 1 )
    {
      if ( (Bitmasks[v13] & *a2) == 0 )
        goto LABEL_39;
      cbData = (unsigned int)dword_1800FB684[2 * v13];
      v15 = (_QWORD *)((char *)a2 + (unsigned int)EntryMap[2 * v13]);
      if ( v13 == 6 )
        break;
      if ( !dword_1800FB684[2 * v13] )
      {
        v16 = (_QWORD *)*v15;
        v15 = v16;
        if ( !v16 )
          goto LABEL_39;
        v17 = -1;
        do
          ++v17;
        while ( *((_WORD *)v16 + v17) );
        cbData = 2 * v17 + 2;
        goto LABEL_36;
      }
LABEL_37:
      if ( cbData > 0xFFFFFFFF )
      {
        v6 = 534;
        goto LABEL_16;
      }
      v18 = JetSetColumn(sesid, DbcfgTbl, dword_1800F9038[4 * v13], v15, cbData, 0, 0);
      v19 = DhcpMapJetError(v18, "C:JetSetColumn");
      v6 = v19;
      if ( v19 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_20;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)&WPP_4c45059f8aca3467116f61052473c3dc_Traceguids,
            (unsigned int)(&DbcfgTable)[2 * v13],
            v19);
          goto LABEL_16;
        }
        goto LABEL_17;
      }
LABEL_39:
      if ( ++v13 >= 0x19 )
      {
        v20 = JetUpdate(sesid, DbcfgTbl, 0, 0, 0);
        v6 = DhcpMapJetError(v20, "C:CommitUpdate");
        if ( v6 )
          goto LABEL_16;
        v21 = JetCommitTransaction(sesid, 0);
        v6 = DhcpMapJetError(v21, "C:JetCommitTransaction");
        goto LABEL_21;
      }
    }
    v15 = (_QWORD *)*v15;
    if ( v15 )
      cbData = (unsigned int)a2[34];
LABEL_36:
    if ( !cbData )
      goto LABEL_39;
    goto LABEL_37;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v10);
LABEL_16:
      v11 = WPP_GLOBAL_Control;
    }
LABEL_17:
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x10) != 0 )
      WPP_SF_D(v11[2], 26, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v6);
  }
LABEL_20:
  JetRollback(sesid, 0);
LABEL_21:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    v8 = 27;
    goto LABEL_24;
  }
  return v6;
}

```

## disassembly

```asm
0x1800156d8  mov     rax, rsp
0x1800156db  mov     [rax+8], rbx
0x1800156df  mov     [rax+10h], rbp
0x1800156e3  mov     [rax+18h], rdi
0x1800156e7  mov     [rax+20h], r12
0x1800156eb  push    r13
0x1800156ed  push    r14
0x1800156ef  push    r15
0x1800156f1  sub     rsp, 40h
0x1800156f5  mov     rbp, rcx
0x1800156f8  mov     rbx, rdx
0x1800156fb  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180015702  call    cs:__imp_EnterCriticalSection
0x180015709  nop     dword ptr [rax+rax+00h]
0x18001570e  inc     dword ptr [rbx+4]
0x180015711  mov     edi, 0FFFFFFFFh
0x180015716  mov     eax, [rbx+4]
0x180015719  xor     r12d, r12d
0x18001571c  mov     edx, eax
0x18001571e  mov     rcx, rbp; sesid
0x180015721  call    FindRecord
0x180015726  test    eax, eax
0x180015728  jnz     short loc_18001573D
0x18001572a  inc     dword ptr [rbx+4]
0x18001572d  mov     eax, [rbx+4]
0x180015730  cmp     eax, edi
0x180015732  jnz     short loc_18001571C
0x180015734  mov     [rbx+4], r12d
0x180015738  mov     eax, r12d
0x18001573b  jmp     short loc_18001571C
0x18001573d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015744  lea     r13, WPP_GLOBAL_Control
0x18001574b  lea     r8, __ImageBase
0x180015752  cmp     rcx, r13
0x180015755  jz      short loc_180015781
0x180015757  test    dword ptr [rcx+1Ch], 8000h
0x18001575e  jz      short loc_180015781
0x180015760  mov     eax, [rbx+4]
0x180015763  mov     r9d, [rbx+8]
0x180015767  mov     rcx, [rcx+10h]
0x18001576b  mov     [rsp+58h+grbit], eax
0x18001576f  mov     rax, ds:rva EntryTypes[r8+r9*8]
0x180015777  mov     qword ptr [rsp+58h+cbData], rax
0x18001577c  call    WPP_SF_dsd
0x180015781  or      dword ptr [rbx], 1
0x180015784  mov     rcx, rbp; sesid
0x180015787  call    cs:__imp_JetBeginTransaction
0x18001578e  nop     dword ptr [rax+rax+00h]
0x180015793  mov     ecx, eax
0x180015795  lea     rdx, aCJetbegintrans; "C:JetBeginTransaction"
0x18001579c  call    DhcpMapJetError
0x1800157a1  mov     edi, eax
0x1800157a3  test    eax, eax
0x1800157a5  jz      short loc_1800157E1
0x1800157a7  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800157ae  call    cs:__imp_LeaveCriticalSection
0x1800157b5  nop     dword ptr [rax+rax+00h]
0x1800157ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157c1  cmp     rcx, r13
0x1800157c4  jz      loc_1800158B7
0x1800157ca  test    dword ptr [rcx+1Ch], 8000h
0x1800157d1  jz      loc_1800158B7
0x1800157d7  mov     edx, 17h
0x1800157dc  jmp     loc_1800158A4
0x1800157e1  mov     rdx, cs:DbcfgTbl; tableid
0x1800157e8  xor     r8d, r8d; prep
0x1800157eb  mov     rcx, rbp; sesid
0x1800157ee  call    cs:__imp_JetPrepareUpdate
0x1800157f5  nop     dword ptr [rax+rax+00h]
0x1800157fa  mov     ecx, eax
0x1800157fc  lea     rdx, aCJetprepareupd; "C:JetPrepareUpdate"
0x180015803  call    DhcpMapJetError
0x180015808  mov     edi, eax
0x18001580a  test    eax, eax
0x18001580c  jz      loc_1800158D9
0x180015812  mov     rcx, cs:WPP_GLOBAL_Control
0x180015819  cmp     rcx, r13
0x18001581c  jz      short loc_180015866
0x18001581e  test    byte ptr [rcx+1Ch], 10h
0x180015822  jz      short loc_180015843
0x180015824  mov     rcx, [rcx+10h]
0x180015828  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x18001582f  mov     edx, 18h
0x180015834  mov     r9d, eax
0x180015837  call    WPP_SF_D
0x18001583c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015843  cmp     rcx, r13
0x180015846  jz      short loc_180015866
0x180015848  test    byte ptr [rcx+1Ch], 10h
0x18001584c  jz      short loc_180015866
0x18001584e  mov     rcx, [rcx+10h]
0x180015852  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180015859  mov     edx, 1Ah
0x18001585e  mov     r9d, edi
0x180015861  call    WPP_SF_D
0x180015866  xor     edx, edx; grbit
0x180015868  mov     rcx, rbp; sesid
0x18001586b  call    cs:__imp_JetRollback
0x180015872  nop     dword ptr [rax+rax+00h]
0x180015877  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18001587e  call    cs:__imp_LeaveCriticalSection
0x180015885  nop     dword ptr [rax+rax+00h]
0x18001588a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015891  cmp     rcx, r13
0x180015894  jz      short loc_1800158B7
0x180015896  test    dword ptr [rcx+1Ch], 8000h
0x18001589d  jz      short loc_1800158B7
0x18001589f  mov     edx, 1Bh
0x1800158a4  mov     rcx, [rcx+10h]
0x1800158a8  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x1800158af  mov     r9d, edi
0x1800158b2  call    WPP_SF_D
0x1800158b7  mov     rbx, [rsp+58h+arg_0]
0x1800158bc  mov     eax, edi
0x1800158be  mov     rdi, [rsp+58h+arg_10]
0x1800158c3  mov     rbp, [rsp+58h+arg_8]
0x1800158c8  mov     r12, [rsp+58h+arg_18]
0x1800158cd  add     rsp, 40h
0x1800158d1  pop     r15
0x1800158d3  pop     r14
0x1800158d5  pop     r13
0x1800158d7  retn
0x1800158d9  mov     r14d, r12d
0x1800158dc  lea     rdx, __ImageBase
0x1800158e3  mov     r15d, r14d
0x1800158e6  mov     eax, ds:rva Bitmasks[rdx+r15*4]
0x1800158ee  test    [rbx], eax
0x1800158f0  jz      loc_1800159A5
0x1800158f6  mov     r9d, rva EntryMap[rdx+r15*8]
0x1800158fe  mov     ecx, rva dword_1800FB684[rdx+r15*8]
0x180015906  add     r9, rbx
0x180015909  cmp     r14d, 6
0x18001590d  jnz     short loc_180015922
0x18001590f  mov     rax, [r9]
0x180015912  mov     r9, rax
0x180015915  test    rax, rax
0x180015918  jz      short loc_180015948
0x18001591a  mov     ecx, [rbx+88h]
0x180015920  jmp     short loc_180015948
0x180015922  test    rcx, rcx
0x180015925  jnz     short loc_18001594D
0x180015927  mov     rax, [r9]
0x18001592a  mov     r9, rax; pvData
0x18001592d  test    rax, rax
0x180015930  jz      short loc_1800159A5
0x180015932  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180015936  inc     rcx
0x180015939  cmp     [rax+rcx*2], r12w
0x18001593e  jnz     short loc_180015936
0x180015940  lea     rcx, ds:2[rcx*2]
0x180015948  test    rcx, rcx
0x18001594b  jz      short loc_1800159A5
0x18001594d  mov     eax, 0FFFFFFFFh
0x180015952  cmp     rcx, rax
0x180015955  ja      loc_180015A60
0x18001595b  mov     [rsp+58h+psetinfo], r12; psetinfo
0x180015960  add     r15, r15
0x180015963  mov     [rsp+58h+grbit], r12d; grbit
0x180015968  mov     [rsp+58h+cbData], ecx; cbData
0x18001596c  mov     rcx, rbp; sesid
0x18001596f  mov     r8d, rva dword_1800F9038[rdx+r15*8]; columnid
0x180015977  mov     rdx, cs:DbcfgTbl; tableid
0x18001597e  call    cs:__imp_JetSetColumn
0x180015985  nop     dword ptr [rax+rax+00h]
0x18001598a  mov     ecx, eax
0x18001598c  lea     rdx, aCJetsetcolumn; "C:JetSetColumn"
0x180015993  call    DhcpMapJetError
0x180015998  mov     edi, eax
0x18001599a  test    eax, eax
0x18001599c  jnz     short loc_180015A19
0x18001599e  lea     rdx, __ImageBase
0x1800159a5  inc     r14d
0x1800159a8  cmp     r14d, 19h
0x1800159ac  jb      loc_1800158E3
0x1800159b2  test    edi, edi
0x1800159b4  jnz     loc_18001583C
0x1800159ba  mov     rdx, cs:DbcfgTbl; tableid
0x1800159c1  xor     r9d, r9d; cbBookmark
0x1800159c4  xor     r8d, r8d; pvBookmark
0x1800159c7  mov     qword ptr [rsp+58h+cbData], r12; pcbActual
0x1800159cc  mov     rcx, rbp; sesid
0x1800159cf  call    cs:__imp_JetUpdate
0x1800159d6  nop     dword ptr [rax+rax+00h]
0x1800159db  mov     ecx, eax
0x1800159dd  lea     rdx, aCCommitupdate; "C:CommitUpdate"
0x1800159e4  call    DhcpMapJetError
0x1800159e9  mov     edi, eax
0x1800159eb  test    eax, eax
0x1800159ed  jnz     loc_18001583C
0x1800159f3  xor     edx, edx; grbit
0x1800159f5  mov     rcx, rbp; sesid
0x1800159f8  call    cs:__imp_JetCommitTransaction
0x1800159ff  nop     dword ptr [rax+rax+00h]
0x180015a04  mov     ecx, eax
0x180015a06  lea     rdx, aCJetcommittran; "C:JetCommitTransaction"
0x180015a0d  call    DhcpMapJetError
0x180015a12  mov     edi, eax
0x180015a14  jmp     loc_180015877
0x180015a19  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a20  cmp     rcx, r13
0x180015a23  jz      loc_180015866
0x180015a29  test    byte ptr [rcx+1Ch], 10h
0x180015a2d  jz      loc_180015843
0x180015a33  mov     rcx, [rcx+10h]
0x180015a37  lea     r8, __ImageBase
0x180015a3e  mov     r9, rva DbcfgTable[r8+r15*8]
0x180015a46  mov     edx, 19h
0x180015a4b  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180015a52  mov     [rsp+58h+cbData], eax
0x180015a56  call    WPP_SF_sd
0x180015a5b  jmp     loc_18001583C
0x180015a60  mov     edi, 216h
0x180015a65  jmp     loc_18001583C
```
