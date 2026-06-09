# RemoveExprIdFromContainerList

- ea: `0x1800bbb5c`
- end: `0x1800bbd1f`
- name: `RemoveExprIdFromContainerList`
- size: `451`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800b861c`

## callees

- `0x1800bba04`
- `0x1800bbb5c`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetSetColumns` at `0x1800bbc7b`
- `ESENT!JetSetColumns` at `0x1800bbc7b`
- `ESENT!JetUpdate` at `0x1800bbcaf`
- `ESENT!JetUpdate` at `0x1800bbcaf`
- `ESENT!JetPrepareUpdate` at `0x1800bbc27`
- `ESENT!JetPrepareUpdate` at `0x1800bbc27`
- `ESENT!JetRetrieveColumn` at `0x1800bbbdf`
- `ESENT!JetRetrieveColumn` at `0x1800bbbdf`

## string_xrefs

- `0x1800bbbed`: `RemoveExprIdFromContainerList(:JetRetrieveColumn`
- `0x1800bbc35`: `RemoveExprIdFromContainerList(:JetPrepareUpdate`
- `0x1800bbc89`: `RemoveExprIdFromContainerList(:JetSetColumns1`
- `0x1800bbcbd`: `RemoveExprIdFromContainerList:JetUPdate`

## pseudocode

```c
__int64 __fastcall RemoveExprIdFromContainerList(JET_SESID sesid, int a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  __int64 result; // rax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int itagSequence; // ecx
  int pvData; // [rsp+40h] [rbp-9h] BYREF
  JET_SETCOLUMN psetcolumn; // [rsp+48h] [rbp-1h] BYREF
  JET_RETINFO pretinfo; // [rsp+70h] [rbp+27h] BYREF

  pvData = 0;
  pretinfo.ibLongValue = 0;
  pretinfo.columnidNextTagged = 0;
  *a3 = 0;
  pretinfo.cbStruct = 16;
  pretinfo.itagSequence = 1;
  do
  {
    v6 = JetRetrieveColumn(sesid, PolicyConditionTableId, dword_1800F7860, &pvData, 4u, 0, 1u, &pretinfo);
    result = PolicyMapJetError(v6, "RemoveExprIdFromContainerList(:JetRetrieveColumn");
    if ( v6 == 1004 )
      return 0;
    if ( v6 )
      return result;
    if ( pvData == a2 )
    {
      v8 = JetPrepareUpdate(sesid, PolicyConditionTableId, 2u);
      result = PolicyMapJetError(v8, "RemoveExprIdFromContainerList(:JetPrepareUpdate");
      if ( (_DWORD)result )
        return result;
      psetcolumn.err = 0;
      memset(&psetcolumn.pvData, 0, 20);
      psetcolumn.columnid = dword_1800F7860;
      psetcolumn.itagSequence = pretinfo.itagSequence;
      v9 = JetSetColumns(sesid, PolicyConditionTableId, &psetcolumn, 1u);
      result = PolicyMapJetError(v9, "RemoveExprIdFromContainerList(:JetSetColumns1");
      if ( (_DWORD)result )
        return result;
      v6 = JetUpdate(sesid, PolicyConditionTableId, 0, 0, 0);
      result = PolicyMapJetError(v6, "RemoveExprIdFromContainerList:JetUPdate");
      if ( (_DWORD)result )
        return result;
      ++*a3;
      itagSequence = pretinfo.itagSequence - 1;
    }
    else
    {
      itagSequence = pretinfo.itagSequence;
    }
    pretinfo.itagSequence = itagSequence + 1;
  }
  while ( !(_DWORD)result );
  if ( v6 == 1004 || v6 == -1603 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800bbb5c  mov     [rsp-8+arg_8], rbx
0x1800bbb61  mov     [rsp-8+arg_18], rsi
0x1800bbb66  push    rbp
0x1800bbb67  push    rdi
0x1800bbb68  push    r14
0x1800bbb6a  lea     rbp, [rsp-47h]
0x1800bbb6f  sub     rsp, 90h
0x1800bbb76  mov     rax, cs:__security_cookie
0x1800bbb7d  xor     rax, rsp
0x1800bbb80  mov     [rbp+57h+var_20], rax
0x1800bbb84  and     [rbp+57h+pvData], 0
0x1800bbb88  mov     rdi, r8
0x1800bbb8b  and     [rbp+57h+var_30.ibLongValue], 0
0x1800bbb8f  mov     r14d, edx
0x1800bbb92  and     [rbp+57h+var_30.columnidNextTagged], 0
0x1800bbb96  mov     rsi, rcx
0x1800bbb99  and     dword ptr [r8], 0
0x1800bbb9d  mov     [rbp+57h+var_30.cbStruct], 10h
0x1800bbba4  mov     [rbp+57h+var_30.itagSequence], 1
0x1800bbbab  mov     r8d, cs:dword_1800F7860; columnid
0x1800bbbb2  lea     rax, [rbp+57h+var_30]
0x1800bbbb6  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bbbbd  lea     r9, [rbp+57h+pvData]; pvData
0x1800bbbc1  mov     [rsp+0A0h+pretinfo], rax; pretinfo
0x1800bbbc6  mov     rcx, rsi; sesid
0x1800bbbc9  mov     [rsp+0A0h+grbit], 1; grbit
0x1800bbbd1  and     [rsp+0A0h+var_78], 0
0x1800bbbd7  mov     [rsp+0A0h+cbData], 4; pcbActual
0x1800bbbdf  call    cs:__imp_JetRetrieveColumn
0x1800bbbe6  nop     dword ptr [rax+rax+00h]
0x1800bbbeb  mov     ecx, eax
0x1800bbbed  lea     rdx, aRemoveexpridfr_0; "RemoveExprIdFromContainerList(:JetRetri"...
0x1800bbbf4  mov     ebx, eax
0x1800bbbf6  call    PolicyMapJetError
0x1800bbbfb  cmp     ebx, 3ECh
0x1800bbc01  jz      loc_1800BBCF8
0x1800bbc07  test    ebx, ebx
0x1800bbc09  jnz     loc_1800BBCFA
0x1800bbc0f  cmp     [rbp+57h+pvData], r14d
0x1800bbc13  jnz     loc_1800BBCD8
0x1800bbc19  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bbc20  lea     r8d, [rbx+2]; prep
0x1800bbc24  mov     rcx, rsi; sesid
0x1800bbc27  call    cs:__imp_JetPrepareUpdate
0x1800bbc2e  nop     dword ptr [rax+rax+00h]
0x1800bbc33  mov     ecx, eax
0x1800bbc35  lea     rdx, aRemoveexpridfr_1; "RemoveExprIdFromContainerList(:JetPrepa"...
0x1800bbc3c  call    PolicyMapJetError
0x1800bbc41  test    eax, eax
0x1800bbc43  jnz     loc_1800BBCFA
0x1800bbc49  mov     eax, cs:dword_1800F7860
0x1800bbc4f  lea     r9d, [rbx+1]; csetcolumn
0x1800bbc53  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bbc5a  lea     r8, [rbp+57h+psetcolumn]; psetcolumn
0x1800bbc5e  and     [rbp+57h+psetcolumn.err], ebx
0x1800bbc61  mov     rcx, rsi; sesid
0x1800bbc64  and     [rbp+57h+psetcolumn.ibLongValue], ebx
0x1800bbc67  and     [rbp+57h+psetcolumn.grbit], ebx
0x1800bbc6a  and     [rbp+57h+psetcolumn.pvData], 0
0x1800bbc6f  and     [rbp+57h+psetcolumn.cbData], ebx
0x1800bbc72  mov     [rbp+57h+psetcolumn.columnid], eax
0x1800bbc75  mov     eax, [rbp+57h+var_30.itagSequence]
0x1800bbc78  mov     [rbp+57h+psetcolumn.itagSequence], eax
0x1800bbc7b  call    cs:__imp_JetSetColumns
0x1800bbc82  nop     dword ptr [rax+rax+00h]
0x1800bbc87  mov     ecx, eax
0x1800bbc89  lea     rdx, aRemoveexpridfr; "RemoveExprIdFromContainerList(:JetSetCo"...
0x1800bbc90  call    PolicyMapJetError
0x1800bbc95  test    eax, eax
0x1800bbc97  jnz     short loc_1800BBCFA
0x1800bbc99  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bbca0  xor     r9d, r9d; cbBookmark
0x1800bbca3  and     qword ptr [rsp+0A0h+cbData], 0
0x1800bbca9  xor     r8d, r8d; pvBookmark
0x1800bbcac  mov     rcx, rsi; sesid
0x1800bbcaf  call    cs:__imp_JetUpdate
0x1800bbcb6  nop     dword ptr [rax+rax+00h]
0x1800bbcbb  mov     ecx, eax
0x1800bbcbd  lea     rdx, aRemoveexpridfr_2; "RemoveExprIdFromContainerList:JetUPdate"
0x1800bbcc4  mov     ebx, eax
0x1800bbcc6  call    PolicyMapJetError
0x1800bbccb  test    eax, eax
0x1800bbccd  jnz     short loc_1800BBCFA
0x1800bbccf  inc     dword ptr [rdi]
0x1800bbcd1  mov     ecx, [rbp+57h+var_30.itagSequence]
0x1800bbcd4  dec     ecx
0x1800bbcd6  jmp     short loc_1800BBCDB
0x1800bbcd8  mov     ecx, [rbp+57h+var_30.itagSequence]
0x1800bbcdb  inc     ecx
0x1800bbcdd  mov     [rbp+57h+var_30.itagSequence], ecx
0x1800bbce0  test    eax, eax
0x1800bbce2  jz      loc_1800BBBAB
0x1800bbce8  cmp     ebx, 3ECh
0x1800bbcee  jz      short loc_1800BBCF8
0x1800bbcf0  cmp     ebx, 0FFFFF9BDh
0x1800bbcf6  jnz     short loc_1800BBCFA
0x1800bbcf8  xor     eax, eax
0x1800bbcfa  mov     rcx, [rbp+57h+var_20]
0x1800bbcfe  xor     rcx, rsp; StackCookie
0x1800bbd01  call    __security_check_cookie
0x1800bbd06  lea     r11, [rsp+0A0h+var_10]
0x1800bbd0e  mov     rbx, [r11+28h]
0x1800bbd12  mov     rsi, [r11+38h]
0x1800bbd16  mov     rsp, r11
0x1800bbd19  pop     r14
0x1800bbd1b  pop     rdi
0x1800bbd1c  pop     rbp
0x1800bbd1d  retn
```
