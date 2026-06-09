# DhcpDeleteMScopeClients

- ea: `0x180029b90`
- end: `0x180029da5`
- name: `DhcpDeleteMScopeClients`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002d3dc`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000f144`
- `0x180028df4`
- `0x180028e28`
- `0x180028fac`
- `0x1800290c4`
- `0x1800292f4`
- `0x180029b90`

## import_xrefs

- `ESENT!JetDelete` at `0x180029c74`
- `ESENT!JetDelete` at `0x180029c74`
- `ESENT!JetBeginTransaction` at `0x180029c4a`
- `ESENT!JetBeginTransaction` at `0x180029c4a`
- `KERNEL32!EnterCriticalSection` at `0x180029bcb`
- `KERNEL32!EnterCriticalSection` at `0x180029bcb`
- `KERNEL32!LeaveCriticalSection` at `0x180029d50`
- `KERNEL32!LeaveCriticalSection` at `0x180029d50`

## string_xrefs

- `0x180029c82`: `M:DeleteCurrentRecord`

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
0x180029b90  push    rbp
0x180029b92  push    rbx
0x180029b93  push    rsi
0x180029b94  push    rdi
0x180029b95  push    r13
0x180029b97  push    r14
0x180029b99  push    r15
0x180029b9b  mov     rbp, rsp
0x180029b9e  sub     rsp, 50h
0x180029ba2  mov     rsi, cs:DhcpGlobalJetServerSession
0x180029ba9  xorps   xmm0, xmm0
0x180029bac  mov     r15, cs:MadcapGlobalClientTableHandle
0x180029bb3  mov     r14d, ecx
0x180029bb6  movups  [rbp+var_20], xmm0
0x180029bba  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029bc1  mov     qword ptr [rbp+var_20+8], rsi
0x180029bc5  xor     edi, edi
0x180029bc7  mov     [rbp+var_10], r15
0x180029bcb  call    cs:__imp_EnterCriticalSection
0x180029bd2  nop     dword ptr [rax+rax+00h]
0x180029bd7  mov     rdx, cs:MadcapGlobalClientTable
0x180029bde  lea     r8d, [rdi+1]
0x180029be2  and     [rsp+50h+var_30], edi
0x180029be6  lea     rcx, [rbp+var_20]
0x180029bea  xor     r9d, r9d
0x180029bed  mov     rdx, [rdx]
0x180029bf0  call    MadcapJetPrepareSearch
0x180029bf5  lea     r13, WPP_GLOBAL_Control
0x180029bfc  mov     ebx, eax
0x180029bfe  test    eax, eax
0x180029c00  jnz     loc_180029D1F
0x180029c06  and     [rbp+arg_18], edi
0x180029c09  and     [rbp+arg_10], edi
0x180029c0c  jmp     loc_180029CF3
0x180029c11  mov     rdx, cs:MadcapGlobalClientTable
0x180029c18  lea     r9, [rbp+arg_8]
0x180029c1c  mov     [rbp+arg_8], 4
0x180029c23  lea     r8, [rbp+arg_10]
0x180029c27  lea     rcx, [rbp+var_20]
0x180029c2b  mov     edx, [rdx+58h]
0x180029c2e  call    MadcapJetGetValue
0x180029c33  mov     ebx, eax
0x180029c35  test    eax, eax
0x180029c37  jnz     loc_180029D1F
0x180029c3d  cmp     r14d, [rbp+arg_10]
0x180029c41  jnz     loc_180029CDA
0x180029c47  mov     rcx, rsi; sesid
0x180029c4a  call    cs:__imp_JetBeginTransaction
0x180029c51  nop     dword ptr [rax+rax+00h]
0x180029c56  mov     ecx, eax
0x180029c58  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x180029c5f  call    DhcpMapJetError
0x180029c64  mov     ebx, eax
0x180029c66  test    eax, eax
0x180029c68  jnz     loc_180029D1F
0x180029c6e  mov     rdx, r15; tableid
0x180029c71  mov     rcx, rsi; sesid
0x180029c74  call    cs:__imp_JetDelete
0x180029c7b  nop     dword ptr [rax+rax+00h]
0x180029c80  mov     ecx, eax
0x180029c82  lea     rdx, aMDeletecurrent; "M:DeleteCurrentRecord"
0x180029c89  call    DhcpMapJetError
0x180029c8e  mov     ebx, eax
0x180029c90  test    eax, eax
0x180029c92  jz      short loc_180029CCB
0x180029c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c9b  cmp     rcx, r13
0x180029c9e  jz      short loc_180029CBE
0x180029ca0  test    byte ptr [rcx+1Ch], 10h
0x180029ca4  jz      short loc_180029CBE
0x180029ca6  mov     rcx, [rcx+10h]
0x180029caa  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029cb1  mov     edx, 15h
0x180029cb6  mov     r9d, eax
0x180029cb9  call    WPP_SF_D
0x180029cbe  lea     rcx, [rbp+var_20]
0x180029cc2  mov     edi, ebx
0x180029cc4  call    MadcapJetRollBack
0x180029cc9  jmp     short loc_180029CD4
0x180029ccb  lea     rcx, [rbp+var_20]
0x180029ccf  call    MadcapJetCommitTransaction
0x180029cd4  mov     ebx, eax
0x180029cd6  test    eax, eax
0x180029cd8  jnz     short loc_180029D1F
0x180029cda  lea     rcx, [rbp+var_20]
0x180029cde  call    MadcapJetNextRecord
0x180029ce3  mov     ebx, eax
0x180029ce5  test    eax, eax
0x180029ce7  jnz     loc_180029D6E
0x180029ced  and     [rbp+arg_18], eax
0x180029cf0  and     [rbp+arg_10], eax
0x180029cf3  mov     rdx, cs:MadcapGlobalClientTable
0x180029cfa  lea     r9, [rbp+arg_8]
0x180029cfe  mov     [rbp+arg_8], 4
0x180029d05  lea     r8, [rbp+arg_18]
0x180029d09  lea     rcx, [rbp+var_20]
0x180029d0d  mov     edx, [rdx+8]
0x180029d10  call    MadcapJetGetValue
0x180029d15  mov     ebx, eax
0x180029d17  test    eax, eax
0x180029d19  jz      loc_180029C11
0x180029d1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d26  cmp     rcx, r13
0x180029d29  jz      short loc_180029D49
0x180029d2b  test    byte ptr [rcx+1Ch], 10h
0x180029d2f  jz      short loc_180029D49
0x180029d31  mov     rcx, [rcx+10h]
0x180029d35  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029d3c  mov     edx, 16h
0x180029d41  mov     r9d, ebx
0x180029d44  call    WPP_SF_D
0x180029d49  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029d50  call    cs:__imp_LeaveCriticalSection
0x180029d57  nop     dword ptr [rax+rax+00h]
0x180029d5c  mov     eax, ebx
0x180029d5e  add     rsp, 50h
0x180029d62  pop     r15
0x180029d64  pop     r14
0x180029d66  pop     r13
0x180029d68  pop     rdi
0x180029d69  pop     rsi
0x180029d6a  pop     rbx
0x180029d6b  pop     rbp
0x180029d6c  retn
0x180029d6e  cmp     eax, 103h
0x180029d73  jnz     short loc_180029D1F
0x180029d75  xor     ebx, ebx
0x180029d77  test    edi, edi
0x180029d79  jnz     short loc_180029D1F
0x180029d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d82  cmp     rcx, r13
0x180029d85  jz      short loc_180029D49
0x180029d87  test    dword ptr [rcx+1Ch], 200h
0x180029d8e  jz      short loc_180029D49
0x180029d90  mov     rcx, [rcx+10h]
0x180029d94  lea     edx, [rbx+17h]
0x180029d97  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x180029d9e  call    WPP_SF_
0x180029da3  jmp     short loc_180029D49
```
