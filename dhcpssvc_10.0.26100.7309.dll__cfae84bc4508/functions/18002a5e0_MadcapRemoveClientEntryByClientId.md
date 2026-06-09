# MadcapRemoveClientEntryByClientId

- ea: `0x18002a5e0`
- end: `0x18002a7e9`
- name: `MadcapRemoveClientEntryByClientId`
- size: `521`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002a9c4`
- `0x18002c2b4`
- `0x18002da70`

## callees

- `0x180002854`
- `0x18000f144`
- `0x180028df4`
- `0x180028e28`
- `0x180028fe4`
- `0x1800292f4`
- `0x18002a5e0`
- `0x18002ac8c`
- `0x180031dc4`

## import_xrefs

- `ESENT!JetDelete` at `0x18002a6e5`
- `ESENT!JetDelete` at `0x18002a6e5`
- `ESENT!JetBeginTransaction` at `0x18002a63a`
- `ESENT!JetBeginTransaction` at `0x18002a63a`
- `KERNEL32!EnterCriticalSection` at `0x18002a618`
- `KERNEL32!EnterCriticalSection` at `0x18002a618`
- `KERNEL32!LeaveCriticalSection` at `0x18002a7c6`
- `KERNEL32!LeaveCriticalSection` at `0x18002a7c6`

## string_xrefs

- `0x18002a6f3`: `M:Remove:Delete`

## pseudocode

```c
__int64 __fastcall MadcapRemoveClientEntryByClientId(__int64 a1, unsigned int a2)
{
  int v3; // esi
  unsigned int v5; // eax
  unsigned int Value; // ebx
  unsigned int v7; // edi
  _QWORD *v8; // rcx
  int v9; // eax
  __int64 v10; // r8
  unsigned int v12; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+38h] [rbp-18h] BYREF
  int v14; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v15; // [rsp+98h] [rbp+48h] BYREF

  v15 = 0;
  v12 = 0;
  v3 = 0;
  v14 = 0;
  v13[0] = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v13[1] = DhcpGlobalJetServerSession;
  v13[2] = MadcapGlobalClientTableHandle;
  v5 = JetBeginTransaction(DhcpGlobalJetServerSession);
  Value = DhcpMapJetError(v5, "M:BeginTransaction");
  if ( Value )
    goto LABEL_9;
  v3 = 1;
  Value = MadcapJetOpenKey(v13, *(_QWORD *)(MadcapGlobalClientTable + 16), a1, a2);
  if ( Value )
    goto LABEL_9;
  v14 = 4;
  Value = MadcapJetGetValue(v13, *(unsigned int *)(MadcapGlobalClientTable + 8), &v12, &v14);
  if ( Value )
    goto LABEL_9;
  v14 = 4;
  Value = MadcapJetGetValue(v13, *(unsigned int *)(MadcapGlobalClientTable + 88), &v15, &v14);
  if ( Value )
    goto LABEL_9;
  v7 = JetDelete(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle);
  Value = DhcpMapJetError(v7, "M:Remove:Delete");
  if ( !Value )
  {
    v9 = DhcpMScopeReleaseAddress(v15, v12);
    if ( v9
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_LLl(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v10, v12, v15, v9);
    }
    goto LABEL_20;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, v7);
LABEL_9:
    v8 = WPP_GLOBAL_Control;
  }
  if ( Value == 20019 )
  {
LABEL_20:
    MadcapJetCommitTransaction(v13);
    goto LABEL_21;
  }
  if ( v3 == 1 )
  {
    MadcapJetRollBack(v13);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
    WPP_SF_D(v8[2], 16, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, Value);
LABEL_21:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return Value;
}

```

## disassembly

```asm
0x18002a5e0  mov     [rsp-28h+arg_0], rbx
0x18002a5e5  mov     [rsp-28h+arg_10], r8d
0x18002a5ea  push    rbp
0x18002a5eb  push    rsi
0x18002a5ec  push    rdi
0x18002a5ed  push    r13
0x18002a5ef  push    r14
0x18002a5f1  mov     rbp, rsp
0x18002a5f4  sub     rsp, 50h
0x18002a5f8  xor     eax, eax
0x18002a5fa  mov     r14, rcx
0x18002a5fd  and     [rbp+arg_18], eax
0x18002a600  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18002a607  and     [rbp+var_20], eax
0x18002a60a  xor     esi, esi
0x18002a60c  and     [rbp+arg_10], esi
0x18002a60f  mov     edi, edx
0x18002a611  mov     [rbp+var_14], eax
0x18002a614  and     [rbp-18h], rax
0x18002a618  call    cs:__imp_EnterCriticalSection
0x18002a61f  nop     dword ptr [rax+rax+00h]
0x18002a624  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18002a62b  mov     rax, cs:MadcapGlobalClientTableHandle
0x18002a632  mov     [rbp+var_10], rcx
0x18002a636  mov     [rbp+var_8], rax
0x18002a63a  call    cs:__imp_JetBeginTransaction
0x18002a641  nop     dword ptr [rax+rax+00h]
0x18002a646  mov     ecx, eax
0x18002a648  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x18002a64f  call    DhcpMapJetError
0x18002a654  lea     r13, WPP_GLOBAL_Control
0x18002a65b  mov     ebx, eax
0x18002a65d  test    eax, eax
0x18002a65f  jnz     loc_18002A72F
0x18002a665  mov     rdx, cs:MadcapGlobalClientTable
0x18002a66c  lea     rcx, [rbp+var_18]
0x18002a670  mov     r9d, edi
0x18002a673  lea     esi, [rax+1]
0x18002a676  mov     r8, r14
0x18002a679  mov     rdx, [rdx+10h]
0x18002a67d  call    MadcapJetOpenKey
0x18002a682  mov     ebx, eax
0x18002a684  test    eax, eax
0x18002a686  jnz     loc_18002A72F
0x18002a68c  mov     rdx, cs:MadcapGlobalClientTable
0x18002a693  lea     edi, [rsi+3]
0x18002a696  mov     [rbp+arg_10], edi
0x18002a699  lea     r9, [rbp+arg_10]
0x18002a69d  lea     r8, [rbp+var_20]
0x18002a6a1  lea     rcx, [rbp+var_18]
0x18002a6a5  mov     edx, [rdx+8]
0x18002a6a8  call    MadcapJetGetValue
0x18002a6ad  mov     ebx, eax
0x18002a6af  test    eax, eax
0x18002a6b1  jnz     short loc_18002A72F
0x18002a6b3  mov     rdx, cs:MadcapGlobalClientTable
0x18002a6ba  lea     r9, [rbp+arg_10]
0x18002a6be  mov     [rbp+arg_10], edi
0x18002a6c1  lea     r8, [rbp+arg_18]
0x18002a6c5  lea     rcx, [rbp+var_18]
0x18002a6c9  mov     edx, [rdx+58h]
0x18002a6cc  call    MadcapJetGetValue
0x18002a6d1  mov     ebx, eax
0x18002a6d3  test    eax, eax
0x18002a6d5  jnz     short loc_18002A72F
0x18002a6d7  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x18002a6de  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18002a6e5  call    cs:__imp_JetDelete
0x18002a6ec  nop     dword ptr [rax+rax+00h]
0x18002a6f1  mov     ecx, eax
0x18002a6f3  lea     rdx, aMRemoveDelete; "M:Remove:Delete"
0x18002a6fa  mov     edi, eax
0x18002a6fc  call    DhcpMapJetError
0x18002a701  mov     ebx, eax
0x18002a703  test    eax, eax
0x18002a705  jz      short loc_18002A778
0x18002a707  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a70e  cmp     rcx, r13
0x18002a711  jz      short loc_18002A736
0x18002a713  test    byte ptr [rcx+1Ch], 10h
0x18002a717  jz      short loc_18002A736
0x18002a719  mov     rcx, [rcx+10h]
0x18002a71d  lea     edx, [rsi+0Dh]
0x18002a720  mov     r9d, edi
0x18002a723  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x18002a72a  call    WPP_SF_D
0x18002a72f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a736  cmp     ebx, 4E33h
0x18002a73c  jz      short loc_18002A7B6
0x18002a73e  cmp     esi, 1
0x18002a741  jnz     short loc_18002A753
0x18002a743  lea     rcx, [rbp+var_18]
0x18002a747  call    MadcapJetRollBack
0x18002a74c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a753  cmp     rcx, r13
0x18002a756  jz      short loc_18002A7BF
0x18002a758  test    byte ptr [rcx+1Ch], 10h
0x18002a75c  jz      short loc_18002A7BF
0x18002a75e  mov     rcx, [rcx+10h]
0x18002a762  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x18002a769  mov     edx, 10h
0x18002a76e  mov     r9d, ebx
0x18002a771  call    WPP_SF_D
0x18002a776  jmp     short loc_18002A7BF
0x18002a778  mov     edx, [rbp+var_20]
0x18002a77b  mov     ecx, [rbp+arg_18]
0x18002a77e  call    DhcpMScopeReleaseAddress
0x18002a783  test    eax, eax
0x18002a785  jz      short loc_18002A7B6
0x18002a787  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a78e  cmp     rcx, r13
0x18002a791  jz      short loc_18002A7B6
0x18002a793  test    byte ptr [rcx+1Ch], 10h
0x18002a797  jz      short loc_18002A7B6
0x18002a799  mov     r9d, [rbp+var_20]
0x18002a79d  mov     edx, 0Fh
0x18002a7a2  mov     rcx, [rcx+10h]
0x18002a7a6  mov     [rsp+50h+var_28], eax
0x18002a7aa  mov     eax, [rbp+arg_18]
0x18002a7ad  mov     [rsp+50h+var_30], eax
0x18002a7b1  call    WPP_SF_LLl
0x18002a7b6  lea     rcx, [rbp+var_18]
0x18002a7ba  call    MadcapJetCommitTransaction
0x18002a7bf  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18002a7c6  call    cs:__imp_LeaveCriticalSection
0x18002a7cd  nop     dword ptr [rax+rax+00h]
0x18002a7d2  mov     eax, ebx
0x18002a7d4  mov     rbx, [rsp+50h+arg_0]
0x18002a7dc  add     rsp, 50h
0x18002a7e0  pop     r14
0x18002a7e2  pop     r13
0x18002a7e4  pop     rdi
0x18002a7e5  pop     rsi
0x18002a7e6  pop     rbp
0x18002a7e7  retn
```
