# DhcpDeleteMScopeClients

- ea: `0x180029144`
- end: `0x180029359`
- name: `DhcpDeleteMScopeClients`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002c95c`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000e814`
- `0x180028388`
- `0x1800283bc`
- `0x180028558`
- `0x180028670`
- `0x1800288a0`
- `0x180029144`

## import_xrefs

- `ESENT!JetDelete` at `0x180029228`
- `ESENT!JetDelete` at `0x180029228`
- `ESENT!JetBeginTransaction` at `0x1800291fe`
- `ESENT!JetBeginTransaction` at `0x1800291fe`
- `KERNEL32!EnterCriticalSection` at `0x18002917f`
- `KERNEL32!EnterCriticalSection` at `0x18002917f`
- `KERNEL32!LeaveCriticalSection` at `0x180029304`
- `KERNEL32!LeaveCriticalSection` at `0x180029304`

## string_xrefs

- `0x180029236`: `M:DeleteCurrentRecord`

## pseudocode

```c
__int64 __fastcall DhcpDeleteMScopeClients(int a1)
{
  JET_SESID v1; // rsi
  JET_TABLEID v2; // r15
  unsigned int v4; // edi
  unsigned int Value; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int Record; // eax
  _QWORD v13[4]; // [rsp+30h] [rbp-20h] BYREF
  int v14; // [rsp+98h] [rbp+48h] BYREF
  int i; // [rsp+A0h] [rbp+50h] BYREF
  int v16; // [rsp+A8h] [rbp+58h] BYREF

  v1 = DhcpGlobalJetServerSession;
  v2 = MadcapGlobalClientTableHandle;
  v13[0] = 0;
  v13[1] = DhcpGlobalJetServerSession;
  v4 = 0;
  v13[2] = MadcapGlobalClientTableHandle;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  Value = MadcapJetPrepareSearch(v13, *(_QWORD *)MadcapGlobalClientTable, 1);
  if ( !Value )
  {
    v16 = 0;
    for ( i = 0; ; i = 0 )
    {
      v14 = 4;
      Value = MadcapJetGetValue(v13, *(unsigned int *)(MadcapGlobalClientTable + 8), &v16, &v14);
      if ( Value )
        break;
      v14 = 4;
      Value = MadcapJetGetValue(v13, *(unsigned int *)(MadcapGlobalClientTable + 88), &i, &v14);
      if ( Value )
        break;
      if ( a1 == i )
      {
        v6 = JetBeginTransaction(v1);
        Value = DhcpMapJetError(v6, "M:BeginTransaction");
        if ( Value )
          break;
        v7 = JetDelete(v1, v2);
        v8 = DhcpMapJetError(v7, "M:DeleteCurrentRecord");
        v9 = v8;
        if ( v8 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, v8);
          }
          v4 = v9;
          v10 = MadcapJetRollBack(v13);
        }
        else
        {
          v10 = MadcapJetCommitTransaction(v13);
        }
        Value = v10;
        if ( v10 )
          break;
      }
      Record = MadcapJetNextRecord(v13);
      Value = Record;
      if ( Record )
      {
        if ( Record != 259 )
          break;
        Value = 0;
        if ( v4 )
          break;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids);
        goto LABEL_19;
      }
      v16 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, Value);
LABEL_19:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return Value;
}

```

## disassembly

```asm
0x180029144  push    rbp
0x180029146  push    rbx
0x180029147  push    rsi
0x180029148  push    rdi
0x180029149  push    r13
0x18002914b  push    r14
0x18002914d  push    r15
0x18002914f  mov     rbp, rsp
0x180029152  sub     rsp, 50h
0x180029156  mov     rsi, cs:DhcpGlobalJetServerSession
0x18002915d  xorps   xmm0, xmm0
0x180029160  mov     r15, cs:MadcapGlobalClientTableHandle
0x180029167  mov     r14d, ecx
0x18002916a  movups  [rbp+var_20], xmm0
0x18002916e  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029175  mov     qword ptr [rbp+var_20+8], rsi
0x180029179  xor     edi, edi
0x18002917b  mov     [rbp+var_10], r15
0x18002917f  call    cs:__imp_EnterCriticalSection
0x180029186  nop     dword ptr [rax+rax+00h]
0x18002918b  mov     rdx, cs:MadcapGlobalClientTable
0x180029192  lea     r8d, [rdi+1]
0x180029196  xor     r9d, r9d
0x180029199  mov     [rsp+50h+var_30], edi
0x18002919d  lea     rcx, [rbp+var_20]
0x1800291a1  mov     rdx, [rdx]
0x1800291a4  call    MadcapJetPrepareSearch
0x1800291a9  lea     r13, WPP_GLOBAL_Control
0x1800291b0  mov     ebx, eax
0x1800291b2  test    eax, eax
0x1800291b4  jnz     loc_1800292D3
0x1800291ba  mov     [rbp+arg_18], edi
0x1800291bd  mov     [rbp+arg_10], edi
0x1800291c0  jmp     loc_1800292A7
0x1800291c5  mov     rdx, cs:MadcapGlobalClientTable
0x1800291cc  lea     r9, [rbp+arg_8]
0x1800291d0  mov     [rbp+arg_8], 4
0x1800291d7  lea     r8, [rbp+arg_10]
0x1800291db  lea     rcx, [rbp+var_20]
0x1800291df  mov     edx, [rdx+58h]
0x1800291e2  call    MadcapJetGetValue
0x1800291e7  mov     ebx, eax
0x1800291e9  test    eax, eax
0x1800291eb  jnz     loc_1800292D3
0x1800291f1  cmp     r14d, [rbp+arg_10]
0x1800291f5  jnz     loc_18002928E
0x1800291fb  mov     rcx, rsi; sesid
0x1800291fe  call    cs:__imp_JetBeginTransaction
0x180029205  nop     dword ptr [rax+rax+00h]
0x18002920a  mov     ecx, eax
0x18002920c  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x180029213  call    DhcpMapJetError
0x180029218  mov     ebx, eax
0x18002921a  test    eax, eax
0x18002921c  jnz     loc_1800292D3
0x180029222  mov     rdx, r15; tableid
0x180029225  mov     rcx, rsi; sesid
0x180029228  call    cs:__imp_JetDelete
0x18002922f  nop     dword ptr [rax+rax+00h]
0x180029234  mov     ecx, eax
0x180029236  lea     rdx, aMDeletecurrent; "M:DeleteCurrentRecord"
0x18002923d  call    DhcpMapJetError
0x180029242  mov     ebx, eax
0x180029244  test    eax, eax
0x180029246  jz      short loc_18002927F
0x180029248  mov     rcx, cs:WPP_GLOBAL_Control
0x18002924f  cmp     rcx, r13
0x180029252  jz      short loc_180029272
0x180029254  test    byte ptr [rcx+1Ch], 10h
0x180029258  jz      short loc_180029272
0x18002925a  mov     rcx, [rcx+10h]
0x18002925e  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029265  mov     edx, 15h
0x18002926a  mov     r9d, eax
0x18002926d  call    WPP_SF_D
0x180029272  lea     rcx, [rbp+var_20]
0x180029276  mov     edi, ebx
0x180029278  call    MadcapJetRollBack
0x18002927d  jmp     short loc_180029288
0x18002927f  lea     rcx, [rbp+var_20]
0x180029283  call    MadcapJetCommitTransaction
0x180029288  mov     ebx, eax
0x18002928a  test    eax, eax
0x18002928c  jnz     short loc_1800292D3
0x18002928e  lea     rcx, [rbp+var_20]
0x180029292  call    MadcapJetNextRecord
0x180029297  mov     ebx, eax
0x180029299  test    eax, eax
0x18002929b  jnz     loc_180029322
0x1800292a1  mov     [rbp+arg_18], eax
0x1800292a4  mov     [rbp+arg_10], eax
0x1800292a7  mov     rdx, cs:MadcapGlobalClientTable
0x1800292ae  lea     r9, [rbp+arg_8]
0x1800292b2  mov     [rbp+arg_8], 4
0x1800292b9  lea     r8, [rbp+arg_18]
0x1800292bd  lea     rcx, [rbp+var_20]
0x1800292c1  mov     edx, [rdx+8]
0x1800292c4  call    MadcapJetGetValue
0x1800292c9  mov     ebx, eax
0x1800292cb  test    eax, eax
0x1800292cd  jz      loc_1800291C5
0x1800292d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292da  cmp     rcx, r13
0x1800292dd  jz      short loc_1800292FD
0x1800292df  test    byte ptr [rcx+1Ch], 10h
0x1800292e3  jz      short loc_1800292FD
0x1800292e5  mov     rcx, [rcx+10h]
0x1800292e9  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x1800292f0  mov     edx, 16h
0x1800292f5  mov     r9d, ebx
0x1800292f8  call    WPP_SF_D
0x1800292fd  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029304  call    cs:__imp_LeaveCriticalSection
0x18002930b  nop     dword ptr [rax+rax+00h]
0x180029310  mov     eax, ebx
0x180029312  add     rsp, 50h
0x180029316  pop     r15
0x180029318  pop     r14
0x18002931a  pop     r13
0x18002931c  pop     rdi
0x18002931d  pop     rsi
0x18002931e  pop     rbx
0x18002931f  pop     rbp
0x180029320  retn
0x180029322  cmp     eax, 103h
0x180029327  jnz     short loc_1800292D3
0x180029329  xor     ebx, ebx
0x18002932b  test    edi, edi
0x18002932d  jnz     short loc_1800292D3
0x18002932f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029336  cmp     rcx, r13
0x180029339  jz      short loc_1800292FD
0x18002933b  test    dword ptr [rcx+1Ch], 200h
0x180029342  jz      short loc_1800292FD
0x180029344  mov     rcx, [rcx+10h]
0x180029348  lea     edx, [rbx+17h]
0x18002934b  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029352  call    WPP_SF_
0x180029357  jmp     short loc_1800292FD
```
