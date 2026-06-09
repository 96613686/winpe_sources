# MadcapRemoveClientEntryByIpAddress

- ea: `0x180029dac`
- end: `0x180029f76`
- name: `MadcapRemoveClientEntryByIpAddress`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18002d050`

## callees

- `0x18000282c`
- `0x18000e814`
- `0x180028388`
- `0x1800283bc`
- `0x180028590`
- `0x1800288a0`
- `0x180029dac`
- `0x18002a234`
- `0x1800313bc`

## import_xrefs

- `ESENT!JetDelete` at `0x180029e7b`
- `ESENT!JetDelete` at `0x180029e7b`
- `ESENT!JetBeginTransaction` at `0x180029df8`
- `ESENT!JetBeginTransaction` at `0x180029df8`
- `KERNEL32!EnterCriticalSection` at `0x180029dd6`
- `KERNEL32!EnterCriticalSection` at `0x180029dd6`
- `KERNEL32!LeaveCriticalSection` at `0x180029f5c`
- `KERNEL32!LeaveCriticalSection` at `0x180029f5c`

## string_xrefs

- `0x180029e89`: `M:Remove:Delete`

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
  v1 = 0;
  v9[0] = 0;
  v12 = 0;
  v11 = 0;
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
0x180029dac  mov     [rsp-28h+arg_8], edx
0x180029db0  mov     [rsp-28h+arg_0], ecx
0x180029db4  push    rbp
0x180029db5  push    rbx
0x180029db6  push    rsi
0x180029db7  push    rdi
0x180029db8  push    r12
0x180029dba  mov     rbp, rsp
0x180029dbd  sub     rsp, 50h
0x180029dc1  xor     eax, eax
0x180029dc3  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029dca  xor     esi, esi
0x180029dcc  mov     [rbp+var_20], rax
0x180029dd0  mov     [rbp+arg_10], esi
0x180029dd3  mov     [rbp+arg_8], eax
0x180029dd6  call    cs:__imp_EnterCriticalSection
0x180029ddd  nop     dword ptr [rax+rax+00h]
0x180029de2  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180029de9  mov     rax, cs:MadcapGlobalClientTableHandle
0x180029df0  mov     [rbp+var_18], rcx
0x180029df4  mov     [rbp+var_10], rax
0x180029df8  call    cs:__imp_JetBeginTransaction
0x180029dff  nop     dword ptr [rax+rax+00h]
0x180029e04  mov     ecx, eax
0x180029e06  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x180029e0d  call    DhcpMapJetError
0x180029e12  lea     r12, WPP_GLOBAL_Control
0x180029e19  mov     ebx, eax
0x180029e1b  test    eax, eax
0x180029e1d  jnz     loc_180029EC5
0x180029e23  mov     rdx, cs:MadcapGlobalClientTable
0x180029e2a  lea     edi, [rax+4]
0x180029e2d  mov     r9d, edi
0x180029e30  lea     r8, [rbp+arg_0]
0x180029e34  lea     rcx, [rbp+var_20]
0x180029e38  lea     esi, [rax+1]
0x180029e3b  mov     rdx, [rdx]
0x180029e3e  call    MadcapJetOpenKey
0x180029e43  mov     ebx, eax
0x180029e45  test    eax, eax
0x180029e47  jnz     short loc_180029EC5
0x180029e49  mov     rdx, cs:MadcapGlobalClientTable
0x180029e50  lea     r9, [rbp+arg_10]
0x180029e54  mov     [rbp+arg_10], edi
0x180029e57  lea     r8, [rbp+arg_8]
0x180029e5b  lea     rcx, [rbp+var_20]
0x180029e5f  mov     edx, [rdx+58h]
0x180029e62  call    MadcapJetGetValue
0x180029e67  mov     ebx, eax
0x180029e69  test    eax, eax
0x180029e6b  jnz     short loc_180029EC5
0x180029e6d  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x180029e74  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180029e7b  call    cs:__imp_JetDelete
0x180029e82  nop     dword ptr [rax+rax+00h]
0x180029e87  mov     ecx, eax
0x180029e89  lea     rdx, aMRemoveDelete; "M:Remove:Delete"
0x180029e90  mov     edi, eax
0x180029e92  call    DhcpMapJetError
0x180029e97  mov     ebx, eax
0x180029e99  test    eax, eax
0x180029e9b  jz      short loc_180029F0E
0x180029e9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ea4  cmp     rcx, r12
0x180029ea7  jz      short loc_180029ECC
0x180029ea9  test    byte ptr [rcx+1Ch], 10h
0x180029ead  jz      short loc_180029ECC
0x180029eaf  mov     rcx, [rcx+10h]
0x180029eb3  lea     edx, [rsi+0Ah]
0x180029eb6  mov     r9d, edi
0x180029eb9  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029ec0  call    WPP_SF_D
0x180029ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ecc  cmp     ebx, 4E33h
0x180029ed2  jz      short loc_180029F4C
0x180029ed4  cmp     esi, 1
0x180029ed7  jnz     short loc_180029EE9
0x180029ed9  lea     rcx, [rbp+var_20]
0x180029edd  call    MadcapJetRollBack
0x180029ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ee9  cmp     rcx, r12
0x180029eec  jz      short loc_180029F55
0x180029eee  test    byte ptr [rcx+1Ch], 10h
0x180029ef2  jz      short loc_180029F55
0x180029ef4  mov     rcx, [rcx+10h]
0x180029ef8  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029eff  mov     edx, 0Dh
0x180029f04  mov     r9d, ebx
0x180029f07  call    WPP_SF_D
0x180029f0c  jmp     short loc_180029F55
0x180029f0e  mov     edx, [rbp+arg_0]
0x180029f11  mov     ecx, [rbp+arg_8]
0x180029f14  call    DhcpMScopeReleaseAddress
0x180029f19  test    eax, eax
0x180029f1b  jz      short loc_180029F4C
0x180029f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f24  cmp     rcx, r12
0x180029f27  jz      short loc_180029F4C
0x180029f29  test    byte ptr [rcx+1Ch], 10h
0x180029f2d  jz      short loc_180029F4C
0x180029f2f  mov     r9d, [rbp+arg_0]
0x180029f33  mov     edx, 0Ch
0x180029f38  mov     rcx, [rcx+10h]
0x180029f3c  mov     [rsp+50h+var_28], eax
0x180029f40  mov     eax, [rbp+arg_8]
0x180029f43  mov     [rsp+50h+var_30], eax
0x180029f47  call    WPP_SF_LLl
0x180029f4c  lea     rcx, [rbp+var_20]
0x180029f50  call    MadcapJetCommitTransaction
0x180029f55  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029f5c  call    cs:__imp_LeaveCriticalSection
0x180029f63  nop     dword ptr [rax+rax+00h]
0x180029f68  mov     eax, ebx
0x180029f6a  add     rsp, 50h
0x180029f6e  pop     r12
0x180029f70  pop     rdi
0x180029f71  pop     rsi
0x180029f72  pop     rbx
0x180029f73  pop     rbp
0x180029f74  retn
```
