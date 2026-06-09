# RemoveExprIdFromContainerList

- ea: `0x1800bcae8`
- end: `0x1800bccb6`
- name: `RemoveExprIdFromContainerList`
- size: `462`
- prototype: `__int64 __fastcall(JET_SESID sesid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x1800b9508`

## callees

- `0x1800bc990`
- `0x1800bcae8`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetSetColumns` at `0x1800bcc0f`
- `ESENT!JetSetColumns` at `0x1800bcc0f`
- `ESENT!JetUpdate` at `0x1800bcc46`
- `ESENT!JetUpdate` at `0x1800bcc46`
- `ESENT!JetPrepareUpdate` at `0x1800bcbb6`
- `ESENT!JetPrepareUpdate` at `0x1800bcbb6`
- `ESENT!JetRetrieveColumn` at `0x1800bcb6e`
- `ESENT!JetRetrieveColumn` at `0x1800bcb6e`

## string_xrefs

- `0x1800bcc54`: `RemoveExprIdFromContainerList:JetUPdate`
- `0x1800bcc1d`: `RemoveExprIdFromContainerList(:JetSetColumns1`
- `0x1800bcbc4`: `RemoveExprIdFromContainerList(:JetPrepareUpdate`
- `0x1800bcb7c`: `RemoveExprIdFromContainerList(:JetRetrieveColumn`

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
  *(_QWORD *)&pretinfo.cbStruct = 16;
  *(_QWORD *)&pretinfo.itagSequence = 1;
  *a3 = 0;
  do
  {
    v6 = JetRetrieveColumn(sesid, PolicyConditionTableId, dword_1800F9670, &pvData, 4u, 0, 1u, &pretinfo);
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
      psetcolumn.columnid = dword_1800F9670;
      psetcolumn.itagSequence = pretinfo.itagSequence;
      psetcolumn.err = 0;
      memset(&psetcolumn.pvData, 0, 20);
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
0x1800bcae8  mov     [rsp-8+arg_8], rbx
0x1800bcaed  mov     [rsp-8+arg_18], rsi
0x1800bcaf2  push    rbp
0x1800bcaf3  push    rdi
0x1800bcaf4  push    r14
0x1800bcaf6  lea     rbp, [rsp-47h]
0x1800bcafb  sub     rsp, 90h
0x1800bcb02  mov     rax, cs:__security_cookie
0x1800bcb09  xor     rax, rsp
0x1800bcb0c  mov     [rbp+57h+var_20], rax
0x1800bcb10  mov     rdi, r8
0x1800bcb13  mov     [rbp+57h+pvData], 0
0x1800bcb1a  mov     r14d, edx
0x1800bcb1d  mov     qword ptr [rbp+57h+var_30.cbStruct], 10h
0x1800bcb25  mov     rsi, rcx
0x1800bcb28  mov     qword ptr [rbp+57h+var_30.itagSequence], 1
0x1800bcb30  mov     dword ptr [r8], 0
0x1800bcb37  mov     r8d, cs:dword_1800F9670; columnid
0x1800bcb3e  lea     rax, [rbp+57h+var_30]
0x1800bcb42  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bcb49  lea     r9, [rbp+57h+pvData]; pvData
0x1800bcb4d  mov     [rsp+0A0h+pretinfo], rax; pretinfo
0x1800bcb52  mov     rcx, rsi; sesid
0x1800bcb55  mov     [rsp+0A0h+grbit], 1; grbit
0x1800bcb5d  mov     [rsp+0A0h+pcbActual], 0; pcbActual
0x1800bcb66  mov     [rsp+0A0h+cbData], 4; cbData
0x1800bcb6e  call    cs:__imp_JetRetrieveColumn
0x1800bcb75  nop     dword ptr [rax+rax+00h]
0x1800bcb7a  mov     ecx, eax
0x1800bcb7c  lea     rdx, aRemoveexpridfr_0; "RemoveExprIdFromContainerList(:JetRetri"...
0x1800bcb83  mov     ebx, eax
0x1800bcb85  call    PolicyMapJetError
0x1800bcb8a  cmp     ebx, 3ECh
0x1800bcb90  jz      loc_1800BCC8F
0x1800bcb96  test    ebx, ebx
0x1800bcb98  jnz     loc_1800BCC91
0x1800bcb9e  cmp     [rbp+57h+pvData], r14d
0x1800bcba2  jnz     loc_1800BCC6F
0x1800bcba8  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bcbaf  lea     r8d, [rbx+2]; prep
0x1800bcbb3  mov     rcx, rsi; sesid
0x1800bcbb6  call    cs:__imp_JetPrepareUpdate
0x1800bcbbd  nop     dword ptr [rax+rax+00h]
0x1800bcbc2  mov     ecx, eax
0x1800bcbc4  lea     rdx, aRemoveexpridfr_1; "RemoveExprIdFromContainerList(:JetPrepa"...
0x1800bcbcb  call    PolicyMapJetError
0x1800bcbd0  test    eax, eax
0x1800bcbd2  jnz     loc_1800BCC91
0x1800bcbd8  mov     eax, cs:dword_1800F9670
0x1800bcbde  lea     r9d, [rbx+1]; csetcolumn
0x1800bcbe2  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bcbe9  lea     r8, [rbp+57h+psetcolumn]; psetcolumn
0x1800bcbed  mov     [rbp+57h+psetcolumn.columnid], eax
0x1800bcbf0  mov     rcx, rsi; sesid
0x1800bcbf3  mov     eax, [rbp+57h+var_30.itagSequence]
0x1800bcbf6  mov     [rbp+57h+psetcolumn.itagSequence], eax
0x1800bcbf9  mov     [rbp+57h+psetcolumn.err], ebx
0x1800bcbfc  mov     qword ptr [rbp+57h+psetcolumn.grbit], 0
0x1800bcc04  mov     [rbp+57h+psetcolumn.pvData], 0
0x1800bcc0c  mov     [rbp+57h+psetcolumn.cbData], ebx
0x1800bcc0f  call    cs:__imp_JetSetColumns
0x1800bcc16  nop     dword ptr [rax+rax+00h]
0x1800bcc1b  mov     ecx, eax
0x1800bcc1d  lea     rdx, aRemoveexpridfr; "RemoveExprIdFromContainerList(:JetSetCo"...
0x1800bcc24  call    PolicyMapJetError
0x1800bcc29  test    eax, eax
0x1800bcc2b  jnz     short loc_1800BCC91
0x1800bcc2d  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bcc34  xor     r9d, r9d; cbBookmark
0x1800bcc37  xor     r8d, r8d; pvBookmark
0x1800bcc3a  mov     qword ptr [rsp+0A0h+cbData], 0; pcbActual
0x1800bcc43  mov     rcx, rsi; sesid
0x1800bcc46  call    cs:__imp_JetUpdate
0x1800bcc4d  nop     dword ptr [rax+rax+00h]
0x1800bcc52  mov     ecx, eax
0x1800bcc54  lea     rdx, aRemoveexpridfr_2; "RemoveExprIdFromContainerList:JetUPdate"
0x1800bcc5b  mov     ebx, eax
0x1800bcc5d  call    PolicyMapJetError
0x1800bcc62  test    eax, eax
0x1800bcc64  jnz     short loc_1800BCC91
0x1800bcc66  inc     dword ptr [rdi]
0x1800bcc68  mov     ecx, [rbp+57h+var_30.itagSequence]
0x1800bcc6b  dec     ecx
0x1800bcc6d  jmp     short loc_1800BCC72
0x1800bcc6f  mov     ecx, [rbp+57h+var_30.itagSequence]
0x1800bcc72  inc     ecx
0x1800bcc74  mov     [rbp+57h+var_30.itagSequence], ecx
0x1800bcc77  test    eax, eax
0x1800bcc79  jz      loc_1800BCB37
0x1800bcc7f  cmp     ebx, 3ECh
0x1800bcc85  jz      short loc_1800BCC8F
0x1800bcc87  cmp     ebx, 0FFFFF9BDh
0x1800bcc8d  jnz     short loc_1800BCC91
0x1800bcc8f  xor     eax, eax
0x1800bcc91  mov     rcx, [rbp+57h+var_20]
0x1800bcc95  xor     rcx, rsp; StackCookie
0x1800bcc98  call    __security_check_cookie
0x1800bcc9d  lea     r11, [rsp+0A0h+var_10]
0x1800bcca5  mov     rbx, [r11+28h]
0x1800bcca9  mov     rsi, [r11+38h]
0x1800bccad  mov     rsp, r11
0x1800bccb0  pop     r14
0x1800bccb2  pop     rdi
0x1800bccb3  pop     rbp
0x1800bccb4  retn
```
