# MadcapRemoveClientEntryByClientId

- ea: `0x180029ba0`
- end: `0x180029da6`
- name: `MadcapRemoveClientEntryByClientId`
- size: `518`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180029f7c`
- `0x18002b85c`
- `0x18002d050`

## callees

- `0x18000282c`
- `0x18000e814`
- `0x180028388`
- `0x1800283bc`
- `0x180028590`
- `0x1800288a0`
- `0x180029ba0`
- `0x18002a234`
- `0x1800313bc`

## import_xrefs

- `ESENT!JetDelete` at `0x180029ca2`
- `ESENT!JetDelete` at `0x180029ca2`
- `ESENT!JetBeginTransaction` at `0x180029bf7`
- `ESENT!JetBeginTransaction` at `0x180029bf7`
- `KERNEL32!EnterCriticalSection` at `0x180029bd5`
- `KERNEL32!EnterCriticalSection` at `0x180029bd5`
- `KERNEL32!LeaveCriticalSection` at `0x180029d83`
- `KERNEL32!LeaveCriticalSection` at `0x180029d83`

## string_xrefs

- `0x180029cb0`: `M:Remove:Delete`

## pseudocode

```c
__int64 __fastcall MadcapRemoveClientEntryByClientId(__int64 a1, unsigned int a2)
{
  int v3; // esi
  unsigned int v5; // eax
  unsigned int Value; // ebx
  __int64 v7; // rdi
  _QWORD *v8; // rcx
  int v9; // eax
  __int64 v10; // r8
  unsigned int v12; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v13[3]; // [rsp+38h] [rbp-18h] BYREF
  int v14; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v15; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  v13[0] = 0;
  v14 = 0;
  v15 = 0;
  v12 = 0;
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
  v7 = (unsigned int)JetDelete(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle);
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
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids,
      (unsigned int)v7);
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
0x180029ba0  mov     [rsp-28h+arg_0], rbx
0x180029ba5  mov     [rsp-28h+arg_10], r8d
0x180029baa  push    rbp
0x180029bab  push    rsi
0x180029bac  push    rdi
0x180029bad  push    r13
0x180029baf  push    r14
0x180029bb1  mov     rbp, rsp
0x180029bb4  sub     rsp, 50h
0x180029bb8  xor     eax, eax
0x180029bba  mov     r14, rcx
0x180029bbd  xor     esi, esi
0x180029bbf  mov     [rbp+var_18], rax
0x180029bc3  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029bca  mov     [rbp+arg_10], esi
0x180029bcd  mov     [rbp+arg_18], eax
0x180029bd0  mov     edi, edx
0x180029bd2  mov     [rbp+var_20], eax
0x180029bd5  call    cs:__imp_EnterCriticalSection
0x180029bdc  nop     dword ptr [rax+rax+00h]
0x180029be1  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180029be8  mov     rax, cs:MadcapGlobalClientTableHandle
0x180029bef  mov     [rbp+var_10], rcx
0x180029bf3  mov     [rbp+var_8], rax
0x180029bf7  call    cs:__imp_JetBeginTransaction
0x180029bfe  nop     dword ptr [rax+rax+00h]
0x180029c03  mov     ecx, eax
0x180029c05  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x180029c0c  call    DhcpMapJetError
0x180029c11  lea     r13, WPP_GLOBAL_Control
0x180029c18  mov     ebx, eax
0x180029c1a  test    eax, eax
0x180029c1c  jnz     loc_180029CEC
0x180029c22  mov     rdx, cs:MadcapGlobalClientTable
0x180029c29  lea     rcx, [rbp+var_18]
0x180029c2d  mov     r9d, edi
0x180029c30  lea     esi, [rax+1]
0x180029c33  mov     r8, r14
0x180029c36  mov     rdx, [rdx+10h]
0x180029c3a  call    MadcapJetOpenKey
0x180029c3f  mov     ebx, eax
0x180029c41  test    eax, eax
0x180029c43  jnz     loc_180029CEC
0x180029c49  mov     rdx, cs:MadcapGlobalClientTable
0x180029c50  lea     edi, [rsi+3]
0x180029c53  mov     [rbp+arg_10], edi
0x180029c56  lea     r9, [rbp+arg_10]
0x180029c5a  lea     r8, [rbp+var_20]
0x180029c5e  lea     rcx, [rbp+var_18]
0x180029c62  mov     edx, [rdx+8]
0x180029c65  call    MadcapJetGetValue
0x180029c6a  mov     ebx, eax
0x180029c6c  test    eax, eax
0x180029c6e  jnz     short loc_180029CEC
0x180029c70  mov     rdx, cs:MadcapGlobalClientTable
0x180029c77  lea     r9, [rbp+arg_10]
0x180029c7b  mov     [rbp+arg_10], edi
0x180029c7e  lea     r8, [rbp+arg_18]
0x180029c82  lea     rcx, [rbp+var_18]
0x180029c86  mov     edx, [rdx+58h]
0x180029c89  call    MadcapJetGetValue
0x180029c8e  mov     ebx, eax
0x180029c90  test    eax, eax
0x180029c92  jnz     short loc_180029CEC
0x180029c94  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x180029c9b  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180029ca2  call    cs:__imp_JetDelete
0x180029ca9  nop     dword ptr [rax+rax+00h]
0x180029cae  mov     ecx, eax
0x180029cb0  lea     rdx, aMRemoveDelete; "M:Remove:Delete"
0x180029cb7  mov     edi, eax
0x180029cb9  call    DhcpMapJetError
0x180029cbe  mov     ebx, eax
0x180029cc0  test    eax, eax
0x180029cc2  jz      short loc_180029D35
0x180029cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180029ccb  cmp     rcx, r13
0x180029cce  jz      short loc_180029CF3
0x180029cd0  test    byte ptr [rcx+1Ch], 10h
0x180029cd4  jz      short loc_180029CF3
0x180029cd6  mov     rcx, [rcx+10h]
0x180029cda  lea     edx, [rsi+0Dh]
0x180029cdd  mov     r9d, edi
0x180029ce0  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029ce7  call    WPP_SF_D
0x180029cec  mov     rcx, cs:WPP_GLOBAL_Control
0x180029cf3  cmp     ebx, 4E33h
0x180029cf9  jz      short loc_180029D73
0x180029cfb  cmp     esi, 1
0x180029cfe  jnz     short loc_180029D10
0x180029d00  lea     rcx, [rbp+var_18]
0x180029d04  call    MadcapJetRollBack
0x180029d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d10  cmp     rcx, r13
0x180029d13  jz      short loc_180029D7C
0x180029d15  test    byte ptr [rcx+1Ch], 10h
0x180029d19  jz      short loc_180029D7C
0x180029d1b  mov     rcx, [rcx+10h]
0x180029d1f  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029d26  mov     edx, 10h
0x180029d2b  mov     r9d, ebx
0x180029d2e  call    WPP_SF_D
0x180029d33  jmp     short loc_180029D7C
0x180029d35  mov     edx, [rbp+var_20]
0x180029d38  mov     ecx, [rbp+arg_18]
0x180029d3b  call    DhcpMScopeReleaseAddress
0x180029d40  test    eax, eax
0x180029d42  jz      short loc_180029D73
0x180029d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d4b  cmp     rcx, r13
0x180029d4e  jz      short loc_180029D73
0x180029d50  test    byte ptr [rcx+1Ch], 10h
0x180029d54  jz      short loc_180029D73
0x180029d56  mov     r9d, [rbp+var_20]
0x180029d5a  mov     edx, 0Fh
0x180029d5f  mov     rcx, [rcx+10h]
0x180029d63  mov     [rsp+50h+var_28], eax
0x180029d67  mov     eax, [rbp+arg_18]
0x180029d6a  mov     [rsp+50h+var_30], eax
0x180029d6e  call    WPP_SF_LLl
0x180029d73  lea     rcx, [rbp+var_18]
0x180029d77  call    MadcapJetCommitTransaction
0x180029d7c  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029d83  call    cs:__imp_LeaveCriticalSection
0x180029d8a  nop     dword ptr [rax+rax+00h]
0x180029d8f  mov     eax, ebx
0x180029d91  mov     rbx, [rsp+50h+arg_0]
0x180029d99  add     rsp, 50h
0x180029d9d  pop     r14
0x180029d9f  pop     r13
0x180029da1  pop     rdi
0x180029da2  pop     rsi
0x180029da3  pop     rbp
0x180029da4  retn
```
