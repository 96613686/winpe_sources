# AddOrUpdateStatelessEntry

- ea: `0x1800680e4`
- end: `0x18006829f`
- name: `AddOrUpdateStatelessEntry`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180070088`

## callees

- `0x18000282c`
- `0x1800680e4`
- `0x1800924c0`
- `0x1800a0ac8`
- `0x1800a0bac`
- `0x1800b6c1c`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x180068196`
- `ESENT!JetPrepareUpdate` at `0x180068196`
- `KERNEL32!EnterCriticalSection` at `0x180068113`
- `KERNEL32!EnterCriticalSection` at `0x1800681ec`
- `KERNEL32!EnterCriticalSection` at `0x180068113`
- `KERNEL32!EnterCriticalSection` at `0x1800681ec`
- `KERNEL32!LeaveCriticalSection` at `0x1800681cd`
- `KERNEL32!LeaveCriticalSection` at `0x18006821d`
- `KERNEL32!LeaveCriticalSection` at `0x1800681cd`
- `KERNEL32!LeaveCriticalSection` at `0x18006821d`

## string_xrefs

- `0x1800681a2`: `DhcpDALJetPrepareUpdate`

## pseudocode

```c
__int64 __fastcall AddOrUpdateStatelessEntry(__int64 a1, __int128 *a2, __int64 a3)
{
  JET_SESID v6; // r14
  unsigned int v7; // edi
  unsigned int v8; // eax
  unsigned int updated; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int128 v13; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+40h] [rbp-30h]
  int v15; // [rsp+48h] [rbp-28h]
  int v16; // [rsp+4Ch] [rbp-24h]
  __int64 v17; // [rsp+50h] [rbp-20h]
  __int64 v18; // [rsp+58h] [rbp-18h]
  __int64 v19; // [rsp+60h] [rbp-10h]
  int v20; // [rsp+68h] [rbp-8h]
  int v21; // [rsp+6Ch] [rbp-4h]

  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v6 = DhcpGlobalJetServerSession;
  v17 = a3 + 16;
  v7 = 0;
  v19 = *(_QWORD *)(a3 + 24);
  v20 = *(_DWORD *)(a3 + 32);
  v14 = a3;
  v15 = 16;
  v16 = 1;
  v18 = 8;
  v21 = 0;
  if ( (unsigned int)DhcpDALJetPrepareUpdate(DhcpGlobalJetServerSession, StatelessClientsTableHandle, 3, 0) != 2
    || (v7 = 1,
        v8 = JetPrepareUpdate(v6, StatelessClientsTableHandle, 0),
        (updated = DhcpDALMapJetError(v8, "DhcpDALJetPrepareUpdate")) == 0) )
  {
    updated = SetStatelessClientColumns(v6, a3, v7);
  }
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( updated )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v11 = 148;
      goto LABEL_13;
    }
  }
  else if ( v7 )
  {
    EnterCriticalSection(&DhcpGlobalStatelessCritSect);
    v13 = *a2;
    updated = MemServerUpdateStatelessRecordsCount(a1, &v13, 1, 0);
    LeaveCriticalSection(&DhcpGlobalStatelessCritSect);
    if ( updated )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        v11 = 147;
LABEL_13:
        WPP_SF_D(v10[2], v11, &WPP_231d8333dd4b30ed6ff0645bbbc6c159_Traceguids, updated);
      }
    }
  }
  return updated;
}

```

## disassembly

```asm
0x1800680e4  mov     rax, rsp
0x1800680e7  mov     [rax+8], rbx
0x1800680eb  mov     [rax+10h], rsi
0x1800680ef  mov     [rax+18h], rdi
0x1800680f3  mov     [rax+20h], r12
0x1800680f7  push    rbp
0x1800680f8  push    r14
0x1800680fa  push    r15
0x1800680fc  mov     rbp, rsp
0x1800680ff  sub     rsp, 70h
0x180068103  mov     r12, rcx
0x180068106  mov     rsi, r8
0x180068109  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180068110  mov     r15, rdx
0x180068113  call    cs:__imp_EnterCriticalSection
0x18006811a  nop     dword ptr [rax+rax+00h]
0x18006811f  mov     r14, cs:DhcpGlobalJetServerSession
0x180068126  lea     rax, [rsi+10h]
0x18006812a  mov     rdx, cs:StatelessClientsTableHandle; tableid
0x180068131  lea     r9, [rbp+var_30]
0x180068135  mov     [rbp+var_20], rax
0x180068139  lea     r8, aSubnetprefixin; "SubnetPrefixInterfaceIdClientDuid"
0x180068140  mov     rax, [rsi+18h]
0x180068144  xor     edi, edi
0x180068146  mov     [rbp+var_10], rax
0x18006814a  mov     rcx, r14; sesid
0x18006814d  mov     eax, [rsi+20h]
0x180068150  mov     [rsp+70h+var_48], edi; int
0x180068154  mov     [rbp+var_8], eax
0x180068157  mov     [rbp+var_30], rsi
0x18006815b  mov     [rbp+var_28], 10h
0x180068162  mov     [rbp+var_24], 1
0x180068169  mov     [rbp+var_18], 8
0x180068171  mov     [rbp+var_4], edi
0x180068174  mov     [rsp+70h+var_50], 3; int
0x18006817c  call    DhcpDALJetPrepareUpdate
0x180068181  cmp     eax, 2
0x180068184  jnz     short loc_1800681B6
0x180068186  mov     rdx, cs:StatelessClientsTableHandle; tableid
0x18006818d  lea     edi, [rax-1]
0x180068190  xor     r8d, r8d; prep
0x180068193  mov     rcx, r14; sesid
0x180068196  call    cs:__imp_JetPrepareUpdate
0x18006819d  nop     dword ptr [rax+rax+00h]
0x1800681a2  lea     rdx, aDhcpdaljetprep_4; "DhcpDALJetPrepareUpdate"
0x1800681a9  mov     ecx, eax
0x1800681ab  call    DhcpDALMapJetError
0x1800681b0  mov     ebx, eax
0x1800681b2  test    eax, eax
0x1800681b4  jnz     short loc_1800681C6
0x1800681b6  mov     r8d, edi
0x1800681b9  mov     rdx, rsi
0x1800681bc  mov     rcx, r14
0x1800681bf  call    SetStatelessClientColumns
0x1800681c4  mov     ebx, eax
0x1800681c6  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800681cd  call    cs:__imp_LeaveCriticalSection
0x1800681d4  nop     dword ptr [rax+rax+00h]
0x1800681d9  test    ebx, ebx
0x1800681db  jnz     short loc_18006824D
0x1800681dd  test    edi, edi
0x1800681df  jz      loc_18006827E
0x1800681e5  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x1800681ec  call    cs:__imp_EnterCriticalSection
0x1800681f3  nop     dword ptr [rax+rax+00h]
0x1800681f8  movups  xmm0, xmmword ptr [r15]
0x1800681fc  xor     r9d, r9d
0x1800681ff  lea     r8d, [rbx+1]
0x180068203  lea     rdx, [rbp+var_40]
0x180068207  mov     rcx, r12
0x18006820a  movdqu  [rbp+var_40], xmm0
0x18006820f  call    MemServerUpdateStatelessRecordsCount
0x180068214  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x18006821b  mov     ebx, eax
0x18006821d  call    cs:__imp_LeaveCriticalSection
0x180068224  nop     dword ptr [rax+rax+00h]
0x180068229  test    ebx, ebx
0x18006822b  jz      short loc_18006827E
0x18006822d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068234  lea     rax, WPP_GLOBAL_Control
0x18006823b  cmp     rcx, rax
0x18006823e  jz      short loc_18006827E
0x180068240  test    byte ptr [rcx+1Ch], 20h
0x180068244  jz      short loc_18006827E
0x180068246  mov     edx, 93h
0x18006824b  jmp     short loc_18006826B
0x18006824d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068254  lea     rax, WPP_GLOBAL_Control
0x18006825b  cmp     rcx, rax
0x18006825e  jz      short loc_18006827E
0x180068260  test    byte ptr [rcx+1Ch], 20h
0x180068264  jz      short loc_18006827E
0x180068266  mov     edx, 94h
0x18006826b  mov     rcx, [rcx+10h]
0x18006826f  lea     r8, WPP_231d8333dd4b30ed6ff0645bbbc6c159_Traceguids
0x180068276  mov     r9d, ebx
0x180068279  call    WPP_SF_D
0x18006827e  lea     r11, [rsp+70h+var_s0]
0x180068283  mov     eax, ebx
0x180068285  mov     rbx, [r11+20h]
0x180068289  mov     rsi, [r11+28h]
0x18006828d  mov     rdi, [r11+30h]
0x180068291  mov     r12, [r11+38h]
0x180068295  mov     rsp, r11
0x180068298  pop     r15
0x18006829a  pop     r14
0x18006829c  pop     rbp
0x18006829d  retn
```
