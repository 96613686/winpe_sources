# MadcapRemoveClientEntryByIpAddress

- ea: `0x18002a7f0`
- end: `0x18002a9bd`
- name: `MadcapRemoveClientEntryByIpAddress`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002da70`

## callees

- `0x180002854`
- `0x18000f144`
- `0x180028df4`
- `0x180028e28`
- `0x180028fe4`
- `0x1800292f4`
- `0x18002a7f0`
- `0x18002ac8c`
- `0x180031dc4`

## import_xrefs

- `ESENT!JetDelete` at `0x18002a8c2`
- `ESENT!JetDelete` at `0x18002a8c2`
- `ESENT!JetBeginTransaction` at `0x18002a83f`
- `ESENT!JetBeginTransaction` at `0x18002a83f`
- `KERNEL32!EnterCriticalSection` at `0x18002a81d`
- `KERNEL32!EnterCriticalSection` at `0x18002a81d`
- `KERNEL32!LeaveCriticalSection` at `0x18002a9a3`
- `KERNEL32!LeaveCriticalSection` at `0x18002a9a3`

## string_xrefs

- `0x18002a8d0`: `M:Remove:Delete`

## pseudocode

```c
__int64 __fastcall MadcapRemoveClientEntryByIpAddress(unsigned int a1)
{
  int v1; // esi
  unsigned int v2; // eax
  unsigned int Value; // ebx
  unsigned int v4; // edi
  _QWORD *v5; // rcx
  int v6; // eax
  __int64 v7; // r8
  _QWORD v9[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v10; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v11; // [rsp+88h] [rbp+38h] BYREF
  int v12; // [rsp+90h] [rbp+40h] BYREF

  v10 = a1;
  v11 = 0;
  v1 = 0;
  v12 = 0;
  v9[0] = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v9[1] = DhcpGlobalJetServerSession;
  v9[2] = MadcapGlobalClientTableHandle;
  v2 = JetBeginTransaction(DhcpGlobalJetServerSession);
  Value = DhcpMapJetError(v2, "M:BeginTransaction");
  if ( Value )
    goto LABEL_8;
  v1 = 1;
  Value = MadcapJetOpenKey(v9, *(_QWORD *)MadcapGlobalClientTable, &v10, 4);
  if ( Value )
    goto LABEL_8;
  v12 = 4;
  Value = MadcapJetGetValue(v9, *(unsigned int *)(MadcapGlobalClientTable + 88), &v11, &v12);
  if ( Value )
    goto LABEL_8;
  v4 = JetDelete(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle);
  Value = DhcpMapJetError(v4, "M:Remove:Delete");
  if ( !Value )
  {
    v6 = DhcpMScopeReleaseAddress(v11, v10);
    if ( v6
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_LLl(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v7, v10, v11, v6);
    }
    goto LABEL_19;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, v4);
LABEL_8:
    v5 = WPP_GLOBAL_Control;
  }
  if ( Value == 20019 )
  {
LABEL_19:
    MadcapJetCommitTransaction(v9);
    goto LABEL_20;
  }
  if ( v1 == 1 )
  {
    MadcapJetRollBack(v9);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
    WPP_SF_D(v5[2], 13, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, Value);
LABEL_20:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return Value;
}

```

## disassembly

```asm
0x18002a7f0  mov     [rsp-28h+arg_8], edx
0x18002a7f4  mov     [rsp-28h+arg_0], ecx
0x18002a7f8  push    rbp
0x18002a7f9  push    rbx
0x18002a7fa  push    rsi
0x18002a7fb  push    rdi
0x18002a7fc  push    r12
0x18002a7fe  mov     rbp, rsp
0x18002a801  sub     rsp, 50h
0x18002a805  xor     eax, eax
0x18002a807  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18002a80e  and     [rbp+arg_8], eax
0x18002a811  xor     esi, esi
0x18002a813  and     [rbp+arg_10], esi
0x18002a816  mov     [rbp+var_1C], eax
0x18002a819  and     [rbp-20h], rax
0x18002a81d  call    cs:__imp_EnterCriticalSection
0x18002a824  nop     dword ptr [rax+rax+00h]
0x18002a829  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18002a830  mov     rax, cs:MadcapGlobalClientTableHandle
0x18002a837  mov     [rbp+var_18], rcx
0x18002a83b  mov     [rbp+var_10], rax
0x18002a83f  call    cs:__imp_JetBeginTransaction
0x18002a846  nop     dword ptr [rax+rax+00h]
0x18002a84b  mov     ecx, eax
0x18002a84d  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x18002a854  call    DhcpMapJetError
0x18002a859  lea     r12, WPP_GLOBAL_Control
0x18002a860  mov     ebx, eax
0x18002a862  test    eax, eax
0x18002a864  jnz     loc_18002A90C
0x18002a86a  mov     rdx, cs:MadcapGlobalClientTable
0x18002a871  lea     edi, [rax+4]
0x18002a874  mov     r9d, edi
0x18002a877  lea     r8, [rbp+arg_0]
0x18002a87b  lea     rcx, [rbp+var_20]
0x18002a87f  lea     esi, [rax+1]
0x18002a882  mov     rdx, [rdx]
0x18002a885  call    MadcapJetOpenKey
0x18002a88a  mov     ebx, eax
0x18002a88c  test    eax, eax
0x18002a88e  jnz     short loc_18002A90C
0x18002a890  mov     rdx, cs:MadcapGlobalClientTable
0x18002a897  lea     r9, [rbp+arg_10]
0x18002a89b  mov     [rbp+arg_10], edi
0x18002a89e  lea     r8, [rbp+arg_8]
0x18002a8a2  lea     rcx, [rbp+var_20]
0x18002a8a6  mov     edx, [rdx+58h]
0x18002a8a9  call    MadcapJetGetValue
0x18002a8ae  mov     ebx, eax
0x18002a8b0  test    eax, eax
0x18002a8b2  jnz     short loc_18002A90C
0x18002a8b4  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x18002a8bb  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18002a8c2  call    cs:__imp_JetDelete
0x18002a8c9  nop     dword ptr [rax+rax+00h]
0x18002a8ce  mov     ecx, eax
0x18002a8d0  lea     rdx, aMRemoveDelete; "M:Remove:Delete"
0x18002a8d7  mov     edi, eax
0x18002a8d9  call    DhcpMapJetError
0x18002a8de  mov     ebx, eax
0x18002a8e0  test    eax, eax
0x18002a8e2  jz      short loc_18002A955
0x18002a8e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a8eb  cmp     rcx, r12
0x18002a8ee  jz      short loc_18002A913
0x18002a8f0  test    byte ptr [rcx+1Ch], 10h
0x18002a8f4  jz      short loc_18002A913
0x18002a8f6  mov     rcx, [rcx+10h]
0x18002a8fa  lea     edx, [rsi+0Ah]
0x18002a8fd  mov     r9d, edi
0x18002a900  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x18002a907  call    WPP_SF_D
0x18002a90c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a913  cmp     ebx, 4E33h
0x18002a919  jz      short loc_18002A993
0x18002a91b  cmp     esi, 1
0x18002a91e  jnz     short loc_18002A930
0x18002a920  lea     rcx, [rbp+var_20]
0x18002a924  call    MadcapJetRollBack
0x18002a929  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a930  cmp     rcx, r12
0x18002a933  jz      short loc_18002A99C
0x18002a935  test    byte ptr [rcx+1Ch], 10h
0x18002a939  jz      short loc_18002A99C
0x18002a93b  mov     rcx, [rcx+10h]
0x18002a93f  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x18002a946  mov     edx, 0Dh
0x18002a94b  mov     r9d, ebx
0x18002a94e  call    WPP_SF_D
0x18002a953  jmp     short loc_18002A99C
0x18002a955  mov     edx, [rbp+arg_0]
0x18002a958  mov     ecx, [rbp+arg_8]
0x18002a95b  call    DhcpMScopeReleaseAddress
0x18002a960  test    eax, eax
0x18002a962  jz      short loc_18002A993
0x18002a964  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a96b  cmp     rcx, r12
0x18002a96e  jz      short loc_18002A993
0x18002a970  test    byte ptr [rcx+1Ch], 10h
0x18002a974  jz      short loc_18002A993
0x18002a976  mov     r9d, [rbp+arg_0]
0x18002a97a  mov     edx, 0Ch
0x18002a97f  mov     rcx, [rcx+10h]
0x18002a983  mov     [rsp+50h+var_28], eax
0x18002a987  mov     eax, [rbp+arg_8]
0x18002a98a  mov     [rsp+50h+var_30], eax
0x18002a98e  call    WPP_SF_LLl
0x18002a993  lea     rcx, [rbp+var_20]
0x18002a997  call    MadcapJetCommitTransaction
0x18002a99c  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18002a9a3  call    cs:__imp_LeaveCriticalSection
0x18002a9aa  nop     dword ptr [rax+rax+00h]
0x18002a9af  mov     eax, ebx
0x18002a9b1  add     rsp, 50h
0x18002a9b5  pop     r12
0x18002a9b7  pop     rdi
0x18002a9b8  pop     rsi
0x18002a9b9  pop     rbx
0x18002a9ba  pop     rbp
0x18002a9bb  retn
```
