# CreateDbEntry

- ea: `0x180015f58`
- end: `0x1800162f9`
- name: `CreateDbEntry`
- size: `929`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `10`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180010460`
- `0x180015e98`
- `0x180016300`
- `0x1800163cc`
- `0x1800164bc`
- `0x1800165d0`
- `0x1800166e4`
- `0x1800167c4`
- `0x180016e10`
- `0x1800175bc`

## callees

- `0x180002854`
- `0x18000f144`
- `0x180011724`
- `0x180015f58`
- `0x18001778c`
- `0x1800182d4`

## import_xrefs

- `ESENT!JetUpdate` at `0x1800161c7`
- `ESENT!JetUpdate` at `0x1800161c7`
- `ESENT!JetBeginTransaction` at `0x18001600b`
- `ESENT!JetBeginTransaction` at `0x18001600b`
- `ESENT!JetRollback` at `0x180016290`
- `ESENT!JetRollback` at `0x180016290`
- `ESENT!JetCommitTransaction` at `0x1800161ec`
- `ESENT!JetCommitTransaction` at `0x1800161ec`
- `ESENT!JetPrepareUpdate` at `0x180016076`
- `ESENT!JetPrepareUpdate` at `0x180016076`
- `ESENT!JetSetColumn` at `0x18001616b`
- `ESENT!JetSetColumn` at `0x18001616b`
- `KERNEL32!EnterCriticalSection` at `0x180015f81`
- `KERNEL32!EnterCriticalSection` at `0x180015f81`
- `KERNEL32!LeaveCriticalSection` at `0x180016032`
- `KERNEL32!LeaveCriticalSection` at `0x1800162a3`
- `KERNEL32!LeaveCriticalSection` at `0x180016032`
- `KERNEL32!LeaveCriticalSection` at `0x1800162a3`

## string_xrefs

- `0x180016084`: `C:JetPrepareUpdate`
- `0x1800161d5`: `C:CommitUpdate`
- `0x1800161fa`: `C:JetCommitTransaction`

## pseudocode

```c
__int64 __fastcall CreateDbEntry(JET_SESID sesid, _DWORD *a2)
{
  unsigned int v4; // r14d
  int v5; // r8d
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // eax
  _QWORD *v13; // rcx
  JET_COLUMNID *v14; // r13
  unsigned int *v15; // r15
  _DWORD *v16; // r12
  unsigned __int64 cbData; // rax
  _QWORD *v18; // r9
  __int64 v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax

  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  ++a2[1];
  v4 = 0;
  while ( !(unsigned int)FindRecord(sesid) )
  {
    v6 = a2[1] + 1;
    a2[1] = v6;
    if ( v6 == -1 )
      a2[1] = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&_ImageBase,
      v5,
      a2[2],
      (__int64)EntryTypes[a2[2]],
      a2[1]);
  *a2 |= 1u;
  v7 = JetBeginTransaction(sesid);
  v8 = DhcpMapJetError(v7, "C:JetBeginTransaction");
  if ( v8 )
  {
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    {
      v10 = 23;
LABEL_45:
      WPP_SF_D(v9[2], v10, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v8);
      return v8;
    }
    return v8;
  }
  v11 = JetPrepareUpdate(sesid, DbcfgTbl, 0);
  v12 = DhcpMapJetError(v11, "C:JetPrepareUpdate");
  v8 = v12;
  if ( !v12 )
  {
    v14 = (JET_COLUMNID *)&unk_1800F7038;
    v15 = (unsigned int *)&EntryMap;
    v16 = &Bitmasks;
    while ( 1 )
    {
      if ( (*v16 & *a2) == 0 )
        goto LABEL_29;
      cbData = v15[1];
      v18 = (_QWORD *)((char *)a2 + *v15);
      if ( v4 == 6 )
        break;
      if ( !v15[1] )
      {
        v18 = (_QWORD *)*v18;
        if ( !v18 )
          goto LABEL_29;
        v19 = -1;
        do
          ++v19;
        while ( *((_WORD *)v18 + v19) );
        cbData = 2 * v19 + 2;
        goto LABEL_26;
      }
LABEL_27:
      if ( cbData > 0xFFFFFFFF )
      {
        v8 = 534;
        goto LABEL_37;
      }
      v20 = JetSetColumn(sesid, DbcfgTbl, *v14, v18, cbData, 0, 0);
      v21 = DhcpMapJetError(v20, "C:JetSetColumn");
      v8 = v21;
      if ( v21 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_41;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            (unsigned int)&WPP_4c45059f8aca3467116f61052473c3dc_Traceguids,
            (unsigned int)(&DbcfgTable)[2 * v4],
            v21);
          goto LABEL_37;
        }
        goto LABEL_38;
      }
LABEL_29:
      ++v4;
      ++v16;
      v15 += 2;
      v14 += 4;
      if ( v4 >= 0x19 )
      {
        if ( !v8 )
        {
          v22 = JetUpdate(sesid, DbcfgTbl, 0, 0, 0);
          v8 = DhcpMapJetError(v22, "C:CommitUpdate");
          if ( !v8 )
          {
            v23 = JetCommitTransaction(sesid, 0);
            v8 = DhcpMapJetError(v23, "C:JetCommitTransaction");
            goto LABEL_42;
          }
        }
        goto LABEL_37;
      }
    }
    v18 = (_QWORD *)*v18;
    if ( v18 )
      cbData = (unsigned int)a2[34];
LABEL_26:
    if ( !cbData )
      goto LABEL_29;
    goto LABEL_27;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v12);
LABEL_37:
      v13 = WPP_GLOBAL_Control;
    }
LABEL_38:
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x10) != 0 )
      WPP_SF_D(v13[2], 26, &WPP_4c45059f8aca3467116f61052473c3dc_Traceguids, v8);
  }
LABEL_41:
  JetRollback(sesid, 0);
LABEL_42:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
  {
    v10 = 27;
    goto LABEL_45;
  }
  return v8;
}

```

## disassembly

```asm
0x180015f58  mov     [rsp+arg_0], rbx
0x180015f5d  mov     [rsp+arg_8], rbp
0x180015f62  mov     [rsp+arg_10], rsi
0x180015f67  push    rdi
0x180015f68  push    r12
0x180015f6a  push    r13
0x180015f6c  push    r14
0x180015f6e  push    r15
0x180015f70  sub     rsp, 40h
0x180015f74  mov     rbp, rcx
0x180015f77  mov     rdi, rdx
0x180015f7a  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180015f81  call    cs:__imp_EnterCriticalSection
0x180015f88  nop     dword ptr [rax+rax+00h]
0x180015f8d  inc     dword ptr [rdi+4]
0x180015f90  mov     ebx, 0FFFFFFFFh
0x180015f95  mov     eax, [rdi+4]
0x180015f98  xor     r14d, r14d
0x180015f9b  mov     edx, eax
0x180015f9d  mov     rcx, rbp; sesid
0x180015fa0  call    FindRecord
0x180015fa5  test    eax, eax
0x180015fa7  jnz     short loc_180015FBE
0x180015fa9  mov     eax, [rdi+4]
0x180015fac  inc     eax
0x180015fae  mov     [rdi+4], eax
0x180015fb1  cmp     eax, ebx
0x180015fb3  jnz     short loc_180015F9B
0x180015fb5  mov     [rdi+4], r14d
0x180015fb9  mov     eax, r14d
0x180015fbc  jmp     short loc_180015F9B
0x180015fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180015fc5  lea     rsi, WPP_GLOBAL_Control
0x180015fcc  lea     rdx, __ImageBase
0x180015fd3  mov     r15d, 8000h
0x180015fd9  cmp     rcx, rsi
0x180015fdc  jz      short loc_180016005
0x180015fde  test    [rcx+1Ch], r15d
0x180015fe2  jz      short loc_180016005
0x180015fe4  mov     eax, [rdi+4]
0x180015fe7  mov     r9d, [rdi+8]
0x180015feb  mov     rcx, [rcx+10h]
0x180015fef  mov     [rsp+68h+grbit], eax
0x180015ff3  mov     rax, ds:rva EntryTypes[rdx+r9*8]
0x180015ffb  mov     qword ptr [rsp+68h+cbData], rax
0x180016000  call    WPP_SF_dsd
0x180016005  or      dword ptr [rdi], 1
0x180016008  mov     rcx, rbp; sesid
0x18001600b  call    cs:__imp_JetBeginTransaction
0x180016012  nop     dword ptr [rax+rax+00h]
0x180016017  mov     ecx, eax
0x180016019  lea     rdx, aCJetbegintrans; "C:JetBeginTransaction"
0x180016020  call    DhcpMapJetError
0x180016025  mov     ebx, eax
0x180016027  test    eax, eax
0x180016029  jz      short loc_180016069
0x18001602b  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180016032  call    cs:__imp_LeaveCriticalSection
0x180016039  nop     dword ptr [rax+rax+00h]
0x18001603e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016045  cmp     rcx, rsi
0x180016048  jz      loc_1800162D8
0x18001604e  test    [rcx+1Ch], r15d
0x180016052  jz      loc_1800162D8
0x180016058  mov     edx, 17h
0x18001605d  lea     r8, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180016064  jmp     loc_1800162CC
0x180016069  mov     rdx, cs:DbcfgTbl; tableid
0x180016070  xor     r8d, r8d; prep
0x180016073  mov     rcx, rbp; sesid
0x180016076  call    cs:__imp_JetPrepareUpdate
0x18001607d  nop     dword ptr [rax+rax+00h]
0x180016082  mov     ecx, eax
0x180016084  lea     rdx, aCJetprepareupd; "C:JetPrepareUpdate"
0x18001608b  call    DhcpMapJetError
0x180016090  xor     ecx, ecx
0x180016092  lea     rsi, WPP_4c45059f8aca3467116f61052473c3dc_Traceguids
0x180016099  mov     ebx, eax
0x18001609b  test    eax, eax
0x18001609d  jz      short loc_1800160D9
0x18001609f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160a6  lea     rdi, WPP_GLOBAL_Control
0x1800160ad  cmp     rcx, rdi
0x1800160b0  jz      loc_18001628B
0x1800160b6  test    byte ptr [rcx+1Ch], 10h
0x1800160ba  jz      loc_18001626C
0x1800160c0  mov     rcx, [rcx+10h]
0x1800160c4  mov     edx, 18h
0x1800160c9  mov     r9d, eax
0x1800160cc  mov     r8, rsi
0x1800160cf  call    WPP_SF_D
0x1800160d4  jmp     loc_180016265
0x1800160d9  lea     r13, unk_1800F7038
0x1800160e0  lea     r15, EntryMap
0x1800160e7  lea     r12, Bitmasks
0x1800160ee  mov     eax, [r12]
0x1800160f2  test    [rdi], eax
0x1800160f4  jz      loc_180016191
0x1800160fa  mov     r9d, [r15]
0x1800160fd  mov     eax, [r15+4]
0x180016101  add     r9, rdi
0x180016104  cmp     r14d, 6
0x180016108  jnz     short loc_18001611A
0x18001610a  mov     r9, [r9]
0x18001610d  test    r9, r9
0x180016110  jz      short loc_18001613D
0x180016112  mov     eax, [rdi+88h]
0x180016118  jmp     short loc_18001613D
0x18001611a  test    rax, rax
0x18001611d  jnz     short loc_180016142
0x18001611f  mov     r9, [r9]; pvData
0x180016122  test    r9, r9
0x180016125  jz      short loc_180016191
0x180016127  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001612b  inc     rax
0x18001612e  cmp     [r9+rax*2], cx
0x180016133  jnz     short loc_18001612B
0x180016135  lea     rax, ds:2[rax*2]
0x18001613d  test    rax, rax
0x180016140  jz      short loc_180016191
0x180016142  mov     edx, 0FFFFFFFFh
0x180016147  cmp     rax, rdx
0x18001614a  ja      loc_180016259
0x180016150  mov     r8d, [r13+0]; columnid
0x180016154  mov     rdx, cs:DbcfgTbl; tableid
0x18001615b  mov     [rsp+68h+psetinfo], rcx; psetinfo
0x180016160  mov     [rsp+68h+grbit], ecx; grbit
0x180016164  mov     rcx, rbp; sesid
0x180016167  mov     [rsp+68h+cbData], eax; cbData
0x18001616b  call    cs:__imp_JetSetColumn
0x180016172  nop     dword ptr [rax+rax+00h]
0x180016177  mov     ecx, eax
0x180016179  lea     rdx, aCJetsetcolumn; "C:JetSetColumn"
0x180016180  call    DhcpMapJetError
0x180016185  xor     ecx, ecx
0x180016187  mov     ebx, eax
0x180016189  test    eax, eax
0x18001618b  jnz     loc_180016214
0x180016191  inc     r14d
0x180016194  add     r12, 4
0x180016198  add     r15, 8
0x18001619c  add     r13, 10h
0x1800161a0  cmp     r14d, 19h
0x1800161a4  jb      loc_1800160EE
0x1800161aa  test    ebx, ebx
0x1800161ac  jnz     loc_18001625E
0x1800161b2  mov     rdx, cs:DbcfgTbl; tableid
0x1800161b9  xor     r9d, r9d; cbBookmark
0x1800161bc  mov     qword ptr [rsp+68h+cbData], rcx; pcbActual
0x1800161c1  xor     r8d, r8d; pvBookmark
0x1800161c4  mov     rcx, rbp; sesid
0x1800161c7  call    cs:__imp_JetUpdate
0x1800161ce  nop     dword ptr [rax+rax+00h]
0x1800161d3  mov     ecx, eax
0x1800161d5  lea     rdx, aCCommitupdate; "C:CommitUpdate"
0x1800161dc  call    DhcpMapJetError
0x1800161e1  mov     ebx, eax
0x1800161e3  test    eax, eax
0x1800161e5  jnz     short loc_18001625E
0x1800161e7  xor     edx, edx; grbit
0x1800161e9  mov     rcx, rbp; sesid
0x1800161ec  call    cs:__imp_JetCommitTransaction
0x1800161f3  nop     dword ptr [rax+rax+00h]
0x1800161f8  mov     ecx, eax
0x1800161fa  lea     rdx, aCJetcommittran; "C:JetCommitTransaction"
0x180016201  call    DhcpMapJetError
0x180016206  mov     ebx, eax
0x180016208  lea     rdi, WPP_GLOBAL_Control
0x18001620f  jmp     loc_18001629C
0x180016214  mov     rcx, cs:WPP_GLOBAL_Control
0x18001621b  lea     rdi, WPP_GLOBAL_Control
0x180016222  cmp     rcx, rdi
0x180016225  jz      short loc_18001628B
0x180016227  test    byte ptr [rcx+1Ch], 10h
0x18001622b  jz      short loc_18001626C
0x18001622d  mov     rcx, [rcx+10h]
0x180016231  mov     edx, 19h
0x180016236  mov     [rsp+68h+cbData], eax
0x18001623a  mov     r8, rsi
0x18001623d  lea     rax, __ImageBase
0x180016244  mov     r9d, r14d
0x180016247  add     r9, r9
0x18001624a  mov     r9, rva DbcfgTable[rax+r9*8]
0x180016252  call    WPP_SF_sd
0x180016257  jmp     short loc_180016265
0x180016259  mov     ebx, 216h
0x18001625e  lea     rdi, WPP_GLOBAL_Control
0x180016265  mov     rcx, cs:WPP_GLOBAL_Control
0x18001626c  cmp     rcx, rdi
0x18001626f  jz      short loc_18001628B
0x180016271  test    byte ptr [rcx+1Ch], 10h
0x180016275  jz      short loc_18001628B
0x180016277  mov     rcx, [rcx+10h]
0x18001627b  mov     edx, 1Ah
0x180016280  mov     r9d, ebx
0x180016283  mov     r8, rsi
0x180016286  call    WPP_SF_D
0x18001628b  xor     edx, edx; grbit
0x18001628d  mov     rcx, rbp; sesid
0x180016290  call    cs:__imp_JetRollback
0x180016297  nop     dword ptr [rax+rax+00h]
0x18001629c  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800162a3  call    cs:__imp_LeaveCriticalSection
0x1800162aa  nop     dword ptr [rax+rax+00h]
0x1800162af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162b6  cmp     rcx, rdi
0x1800162b9  jz      short loc_1800162D8
0x1800162bb  test    dword ptr [rcx+1Ch], 8000h
0x1800162c2  jz      short loc_1800162D8
0x1800162c4  mov     edx, 1Bh
0x1800162c9  mov     r8, rsi
0x1800162cc  mov     rcx, [rcx+10h]
0x1800162d0  mov     r9d, ebx
0x1800162d3  call    WPP_SF_D
0x1800162d8  lea     r11, [rsp+68h+var_28]
0x1800162dd  mov     eax, ebx
0x1800162df  mov     rbx, [r11+30h]
0x1800162e3  mov     rbp, [r11+38h]
0x1800162e7  mov     rsi, [r11+40h]
0x1800162eb  mov     rsp, r11
0x1800162ee  pop     r15
0x1800162f0  pop     r14
0x1800162f2  pop     r13
0x1800162f4  pop     r12
0x1800162f6  pop     rdi
0x1800162f7  retn
```
