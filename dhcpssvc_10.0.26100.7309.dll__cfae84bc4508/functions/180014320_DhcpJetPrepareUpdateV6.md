# DhcpJetPrepareUpdateV6

- ea: `0x180014320`
- end: `0x18001445e`
- name: `DhcpJetPrepareUpdateV6`
- size: `318`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180011c78`
- `0x18007ad70`
- `0x18007bb54`

## callees

- `0x180002854`
- `0x18000f144`
- `0x180014320`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x180014356`
- `ESENT!JetSetCurrentIndex` at `0x180014356`
- `ESENT!JetMakeKey` at `0x180014391`
- `ESENT!JetMakeKey` at `0x180014391`
- `ESENT!JetSeek` at `0x1800143bd`
- `ESENT!JetSeek` at `0x1800143bd`
- `ESENT!JetPrepareUpdate` at `0x1800143f1`
- `ESENT!JetPrepareUpdate` at `0x1800143f1`

## string_xrefs

- `0x180014364`: `JetPrepareUpdate:SetCurrentIndex`
- `0x18001439f`: `JetPrepareUpdate:MakeKey`
- `0x1800143cb`: `JetPrepareUpdate:Seek`
- `0x1800143ff`: `JetPrepareUpdate:PrepareUpdate`

## pseudocode

```c
__int64 __fastcall DhcpJetPrepareUpdateV6(__int64 a1, const void *a2, __int64 a3, int a4, __int64 a5, JET_SESID sesid)
{
  JET_TABLEID v6; // rdi
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int Key; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax

  v6 = DhcpGlobalClientTableV6Handle;
  if ( !a4 )
  {
    v9 = JetSetCurrentIndex(sesid, DhcpGlobalClientTableV6Handle, a1);
    v10 = DhcpMapJetError(v9, "JetPrepareUpdate:SetCurrentIndex");
    if ( v10 )
      goto LABEL_7;
    Key = JetMakeKey(sesid, v6, a2, 0xBu, 1u);
    v10 = DhcpMapJetError(Key, "JetPrepareUpdate:MakeKey");
    if ( v10 )
      goto LABEL_7;
    v12 = JetSeek(sesid, v6, 1u);
    v10 = DhcpMapJetError(v12, "JetPrepareUpdate:Seek");
    if ( v10 )
      goto LABEL_7;
  }
  v13 = JetPrepareUpdate(sesid, v6, a4 == 0 ? 2 : 0);
  v10 = DhcpMapJetError(v13, "JetPrepareUpdate:PrepareUpdate");
  if ( v10 )
  {
LABEL_7:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_3c7468642838320b8afbb5ce47767e51_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180014320  mov     [rsp+arg_0], rbx
0x180014325  mov     [rsp+arg_8], rbp
0x18001432a  mov     [rsp+arg_10], rdi
0x18001432f  push    r14
0x180014331  sub     rsp, 30h
0x180014335  mov     rdi, cs:DhcpGlobalClientTableV6Handle
0x18001433c  mov     ebp, r9d
0x18001433f  mov     r14, rdx
0x180014342  test    r9d, r9d
0x180014345  jnz     loc_1800143DD
0x18001434b  mov     r8, rcx
0x18001434e  mov     rdx, rdi
0x180014351  mov     rcx, [rsp+38h+sesid]
0x180014356  call    cs:__imp_JetSetCurrentIndex
0x18001435d  nop     dword ptr [rax+rax+00h]
0x180014362  mov     ecx, eax
0x180014364  lea     rdx, aJetprepareupda; "JetPrepareUpdate:SetCurrentIndex"
0x18001436b  call    DhcpMapJetError
0x180014370  mov     ebx, eax
0x180014372  test    eax, eax
0x180014374  jnz     loc_180014411
0x18001437a  mov     rcx, [rsp+38h+sesid]; sesid
0x18001437f  lea     r9d, [rbp+0Bh]; cbData
0x180014383  mov     r8, r14; pvData
0x180014386  mov     [rsp+38h+grbit], 1; grbit
0x18001438e  mov     rdx, rdi; tableid
0x180014391  call    cs:__imp_JetMakeKey
0x180014398  nop     dword ptr [rax+rax+00h]
0x18001439d  mov     ecx, eax
0x18001439f  lea     rdx, aJetprepareupda_1; "JetPrepareUpdate:MakeKey"
0x1800143a6  call    DhcpMapJetError
0x1800143ab  mov     ebx, eax
0x1800143ad  test    eax, eax
0x1800143af  jnz     short loc_180014411
0x1800143b1  mov     rcx, [rsp+38h+sesid]; sesid
0x1800143b6  lea     r8d, [rbp+1]; grbit
0x1800143ba  mov     rdx, rdi; tableid
0x1800143bd  call    cs:__imp_JetSeek
0x1800143c4  nop     dword ptr [rax+rax+00h]
0x1800143c9  mov     ecx, eax
0x1800143cb  lea     rdx, aJetprepareupda_2; "JetPrepareUpdate:Seek"
0x1800143d2  call    DhcpMapJetError
0x1800143d7  mov     ebx, eax
0x1800143d9  test    eax, eax
0x1800143db  jnz     short loc_180014411
0x1800143dd  mov     rcx, [rsp+38h+sesid]; sesid
0x1800143e2  neg     ebp
0x1800143e4  mov     rdx, rdi; tableid
0x1800143e7  sbb     r8d, r8d
0x1800143ea  not     r8d
0x1800143ed  and     r8d, 2; prep
0x1800143f1  call    cs:__imp_JetPrepareUpdate
0x1800143f8  nop     dword ptr [rax+rax+00h]
0x1800143fd  mov     ecx, eax
0x1800143ff  lea     rdx, aJetprepareupda_3; "JetPrepareUpdate:PrepareUpdate"
0x180014406  call    DhcpMapJetError
0x18001440b  mov     ebx, eax
0x18001440d  test    eax, eax
0x18001440f  jz      short loc_180014445
0x180014411  mov     rcx, cs:WPP_GLOBAL_Control
0x180014418  lea     rax, WPP_GLOBAL_Control
0x18001441f  cmp     rcx, rax
0x180014422  jz      short loc_180014445
0x180014424  test    dword ptr [rcx+1Ch], 800h
0x18001442b  jz      short loc_180014445
0x18001442d  mov     rcx, [rcx+10h]
0x180014431  lea     r8, WPP_3c7468642838320b8afbb5ce47767e51_Traceguids
0x180014438  mov     edx, 0Eh
0x18001443d  mov     r9d, ebx
0x180014440  call    WPP_SF_D
0x180014445  mov     rbp, [rsp+38h+arg_8]
0x18001444a  mov     eax, ebx
0x18001444c  mov     rbx, [rsp+38h+arg_0]
0x180014451  mov     rdi, [rsp+38h+arg_10]
0x180014456  add     rsp, 30h
0x18001445a  pop     r14
0x18001445c  retn
```
