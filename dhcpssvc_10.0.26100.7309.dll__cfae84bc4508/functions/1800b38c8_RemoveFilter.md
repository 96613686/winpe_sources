# RemoveFilter

- ea: `0x1800b38c8`
- end: `0x1800b3a32`
- name: `RemoveFilter`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18003a260`

## callees

- `0x180002854`
- `0x1800b38c8`
- `0x1800b3e40`
- `0x1800b4ae0`
- `0x1800b4f88`

## import_xrefs

- `ESENT!JetDelete` at `0x1800b3960`
- `ESENT!JetDelete` at `0x1800b3960`
- `ESENT!JetBeginTransaction` at `0x1800b38f4`
- `ESENT!JetBeginTransaction` at `0x1800b38f4`
- `ESENT!JetRollback` at `0x1800b39c1`
- `ESENT!JetRollback` at `0x1800b39c1`
- `ESENT!JetCommitTransaction` at `0x1800b399c`
- `ESENT!JetCommitTransaction` at `0x1800b399c`
- `KERNEL32!EnterCriticalSection` at `0x1800b38e1`
- `KERNEL32!EnterCriticalSection` at `0x1800b38e1`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3a13`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3a13`

## string_xrefs

- `0x1800b39aa`: `FilterJetCommitTransaction`
- `0x1800b39cf`: `FilterJetRollback`
- `0x1800b396e`: `FilterJetDeleteCurrentRecord`

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
0x1800b38c8  mov     [rsp+arg_0], rbx
0x1800b38cd  mov     [rsp+arg_8], rsi
0x1800b38d2  push    rdi
0x1800b38d3  sub     rsp, 40h
0x1800b38d7  mov     rdi, rcx
0x1800b38da  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b38e1  call    cs:__imp_EnterCriticalSection
0x1800b38e8  nop     dword ptr [rax+rax+00h]
0x1800b38ed  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b38f4  call    cs:__imp_JetBeginTransaction
0x1800b38fb  nop     dword ptr [rax+rax+00h]
0x1800b3900  mov     ecx, eax
0x1800b3902  lea     rdx, aFilterjetbegin; "FilterJetBeginTransaction"
0x1800b3909  call    FilterMapJetError
0x1800b390e  xor     esi, esi
0x1800b3910  mov     ebx, eax
0x1800b3912  test    eax, eax
0x1800b3914  jnz     loc_1800B39B8
0x1800b391a  movzx   eax, byte ptr [rdi+9]
0x1800b391e  lea     r9, [rdi+8]
0x1800b3922  cmp     dword ptr [rdi+4], 1
0x1800b3926  lea     r8, aTypepattern; "TypePattern"
0x1800b392d  mov     [rsp+48h+var_18], eax
0x1800b3931  mov     ecx, esi
0x1800b3933  mov     rax, [rdi+10h]
0x1800b3937  setz    cl
0x1800b393a  mov     [rsp+48h+var_20], rax
0x1800b393f  cmovnz  r9, rsi
0x1800b3943  mov     [rsp+48h+var_28], ecx
0x1800b3947  call    FilterJetOpenKey
0x1800b394c  mov     ebx, eax
0x1800b394e  test    eax, eax
0x1800b3950  jnz     short loc_1800B39B8
0x1800b3952  mov     rdx, cs:FilterGlobalTableHandle; tableid
0x1800b3959  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b3960  call    cs:__imp_JetDelete
0x1800b3967  nop     dword ptr [rax+rax+00h]
0x1800b396c  mov     ecx, eax
0x1800b396e  lea     rdx, aFilterjetdelet; "FilterJetDeleteCurrentRecord"
0x1800b3975  call    FilterMapJetError
0x1800b397a  mov     ebx, eax
0x1800b397c  test    eax, eax
0x1800b397e  jnz     short loc_1800B39B8
0x1800b3980  cmp     [rdi], esi
0x1800b3982  jz      short loc_1800B3990
0x1800b3984  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b398b  call    ComputeDistinctPrefixLengths
0x1800b3990  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b3997  mov     edx, 1; grbit
0x1800b399c  call    cs:__imp_JetCommitTransaction
0x1800b39a3  nop     dword ptr [rax+rax+00h]
0x1800b39a8  mov     ecx, eax
0x1800b39aa  lea     rdx, aFilterjetcommi; "FilterJetCommitTransaction"
0x1800b39b1  call    FilterMapJetError
0x1800b39b6  jmp     short loc_1800B3A0C
0x1800b39b8  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800b39bf  xor     edx, edx; grbit
0x1800b39c1  call    cs:__imp_JetRollback
0x1800b39c8  nop     dword ptr [rax+rax+00h]
0x1800b39cd  mov     ecx, eax
0x1800b39cf  lea     rdx, aFilterjetrollb; "FilterJetRollback"
0x1800b39d6  call    FilterMapJetError
0x1800b39db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b39e2  lea     rax, WPP_GLOBAL_Control
0x1800b39e9  cmp     rcx, rax
0x1800b39ec  jz      short loc_1800B3A0C
0x1800b39ee  test    byte ptr [rcx+1Ch], 10h
0x1800b39f2  jz      short loc_1800B3A0C
0x1800b39f4  mov     rcx, [rcx+10h]
0x1800b39f8  lea     r8, WPP_0db8580d4aa93e5d318c9249289cee35_Traceguids
0x1800b39ff  mov     edx, 0Ah
0x1800b3a04  mov     r9d, ebx
0x1800b3a07  call    WPP_SF_D
0x1800b3a0c  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800b3a13  call    cs:__imp_LeaveCriticalSection
0x1800b3a1a  nop     dword ptr [rax+rax+00h]
0x1800b3a1f  mov     rsi, [rsp+48h+arg_8]
0x1800b3a24  mov     eax, ebx
0x1800b3a26  mov     rbx, [rsp+48h+arg_0]
0x1800b3a2b  add     rsp, 40h
0x1800b3a2f  pop     rdi
0x1800b3a30  retn
```
