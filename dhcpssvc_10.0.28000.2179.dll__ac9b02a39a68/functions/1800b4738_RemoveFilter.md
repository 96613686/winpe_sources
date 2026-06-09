# RemoveFilter

- ea: `0x1800b4738`
- end: `0x1800b48a2`
- name: `RemoveFilter`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180039998`

## callees

- `0x18000282c`
- `0x1800b4738`
- `0x1800b4cac`
- `0x1800b5974`
- `0x1800b5e24`

## import_xrefs

- `ESENT!JetDelete` at `0x1800b47d0`
- `ESENT!JetDelete` at `0x1800b47d0`
- `ESENT!JetBeginTransaction` at `0x1800b4764`
- `ESENT!JetBeginTransaction` at `0x1800b4764`
- `ESENT!JetRollback` at `0x1800b4831`
- `ESENT!JetRollback` at `0x1800b4831`
- `ESENT!JetCommitTransaction` at `0x1800b480c`
- `ESENT!JetCommitTransaction` at `0x1800b480c`
- `KERNEL32!EnterCriticalSection` at `0x1800b4751`
- `KERNEL32!EnterCriticalSection` at `0x1800b4751`
- `KERNEL32!LeaveCriticalSection` at `0x1800b4883`
- `KERNEL32!LeaveCriticalSection` at `0x1800b4883`

## string_xrefs

- `0x1800b483f`: `FilterJetRollback`
- `0x1800b481a`: `FilterJetCommitTransaction`
- `0x1800b47de`: `FilterJetDeleteCurrentRecord`

## pseudocode

```c
__int64 __fastcall RemoveFilter(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  __int64 v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax

  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v2 = JetBeginTransaction(DhcpGlobalJetServerSession);
  v4 = FilterMapJetError(v2, "FilterJetBeginTransaction");
  if ( v4 )
    goto LABEL_9;
  v5 = a1 + 8;
  if ( *(_DWORD *)(a1 + 4) != 1 )
    v5 = 0;
  v4 = FilterJetOpenKey(
         *(_DWORD *)(a1 + 4) == 1,
         v3,
         "TypePattern",
         v5,
         *(_DWORD *)(a1 + 4) == 1,
         *(_QWORD *)(a1 + 16),
         *(unsigned __int8 *)(a1 + 9));
  if ( v4
    || (v6 = JetDelete(DhcpGlobalJetServerSession, FilterGlobalTableHandle),
        (v4 = FilterMapJetError(v6, "FilterJetDeleteCurrentRecord")) != 0) )
  {
LABEL_9:
    v8 = JetRollback(DhcpGlobalJetServerSession, 0);
    FilterMapJetError(v8, "FilterJetRollback");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_0db8580d4aa93e5d318c9249289cee35_Traceguids, v4);
  }
  else
  {
    if ( *(_DWORD *)a1 )
      ComputeDistinctPrefixLengths(DhcpGlobalJetServerSession);
    v7 = JetCommitTransaction(DhcpGlobalJetServerSession, 1u);
    FilterMapJetError(v7, "FilterJetCommitTransaction");
  }
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return v4;
}

```

## disassembly

```asm
0x1800b4738  mov     [rsp+arg_0], rbx
0x1800b473d  mov     [rsp+arg_8], rsi
0x1800b4742  push    rdi
0x1800b4743  sub     rsp, 40h
0x1800b4747  mov     rdi, rcx
0x1800b474a  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b4751  call    cs:__imp_EnterCriticalSection
0x1800b4758  nop     dword ptr [rax+rax+00h]
0x1800b475d  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b4764  call    cs:__imp_JetBeginTransaction
0x1800b476b  nop     dword ptr [rax+rax+00h]
0x1800b4770  mov     ecx, eax
0x1800b4772  lea     rdx, aFilterjetbegin; "FilterJetBeginTransaction"
0x1800b4779  call    FilterMapJetError
0x1800b477e  xor     esi, esi
0x1800b4780  mov     ebx, eax
0x1800b4782  test    eax, eax
0x1800b4784  jnz     loc_1800B4828
0x1800b478a  movzx   eax, byte ptr [rdi+9]
0x1800b478e  lea     r9, [rdi+8]
0x1800b4792  cmp     dword ptr [rdi+4], 1
0x1800b4796  lea     r8, aTypepattern; "TypePattern"
0x1800b479d  mov     [rsp+48h+var_18], eax
0x1800b47a1  mov     ecx, esi
0x1800b47a3  mov     rax, [rdi+10h]
0x1800b47a7  setz    cl
0x1800b47aa  mov     [rsp+48h+var_20], rax
0x1800b47af  cmovnz  r9, rsi
0x1800b47b3  mov     [rsp+48h+var_28], ecx
0x1800b47b7  call    FilterJetOpenKey
0x1800b47bc  mov     ebx, eax
0x1800b47be  test    eax, eax
0x1800b47c0  jnz     short loc_1800B4828
0x1800b47c2  mov     rdx, cs:FilterGlobalTableHandle; tableid
0x1800b47c9  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b47d0  call    cs:__imp_JetDelete
0x1800b47d7  nop     dword ptr [rax+rax+00h]
0x1800b47dc  mov     ecx, eax
0x1800b47de  lea     rdx, aFilterjetdelet; "FilterJetDeleteCurrentRecord"
0x1800b47e5  call    FilterMapJetError
0x1800b47ea  mov     ebx, eax
0x1800b47ec  test    eax, eax
0x1800b47ee  jnz     short loc_1800B4828
0x1800b47f0  cmp     [rdi], esi
0x1800b47f2  jz      short loc_1800B4800
0x1800b47f4  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b47fb  call    ComputeDistinctPrefixLengths
0x1800b4800  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b4807  mov     edx, 1; grbit
0x1800b480c  call    cs:__imp_JetCommitTransaction
0x1800b4813  nop     dword ptr [rax+rax+00h]
0x1800b4818  mov     ecx, eax
0x1800b481a  lea     rdx, aFilterjetcommi; "FilterJetCommitTransaction"
0x1800b4821  call    FilterMapJetError
0x1800b4826  jmp     short loc_1800B487C
0x1800b4828  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b482f  xor     edx, edx; grbit
0x1800b4831  call    cs:__imp_JetRollback
0x1800b4838  nop     dword ptr [rax+rax+00h]
0x1800b483d  mov     ecx, eax
0x1800b483f  lea     rdx, aFilterjetrollb; "FilterJetRollback"
0x1800b4846  call    FilterMapJetError
0x1800b484b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4852  lea     rax, WPP_GLOBAL_Control
0x1800b4859  cmp     rcx, rax
0x1800b485c  jz      short loc_1800B487C
0x1800b485e  test    byte ptr [rcx+1Ch], 10h
0x1800b4862  jz      short loc_1800B487C
0x1800b4864  mov     rcx, [rcx+10h]
0x1800b4868  lea     r8, WPP_0db8580d4aa93e5d318c9249289cee35_Traceguids
0x1800b486f  mov     edx, 0Ah
0x1800b4874  mov     r9d, ebx
0x1800b4877  call    WPP_SF_D
0x1800b487c  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b4883  call    cs:__imp_LeaveCriticalSection
0x1800b488a  nop     dword ptr [rax+rax+00h]
0x1800b488f  mov     rsi, [rsp+48h+arg_8]
0x1800b4894  mov     eax, ebx
0x1800b4896  mov     rbx, [rsp+48h+arg_0]
0x1800b489b  add     rsp, 40h
0x1800b489f  pop     rdi
0x1800b48a0  retn
```
