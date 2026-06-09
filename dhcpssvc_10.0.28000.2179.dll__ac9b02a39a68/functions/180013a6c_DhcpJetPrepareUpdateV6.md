# DhcpJetPrepareUpdateV6

- ea: `0x180013a6c`
- end: `0x180013baa`
- name: `DhcpJetPrepareUpdateV6`
- size: `318`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800113b8`
- `0x18007ab8c`
- `0x18007b994`

## callees

- `0x18000282c`
- `0x18000e814`
- `0x180013a6c`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x180013aa2`
- `ESENT!JetSetCurrentIndex` at `0x180013aa2`
- `ESENT!JetMakeKey` at `0x180013add`
- `ESENT!JetMakeKey` at `0x180013add`
- `ESENT!JetSeek` at `0x180013b09`
- `ESENT!JetSeek` at `0x180013b09`
- `ESENT!JetPrepareUpdate` at `0x180013b3d`
- `ESENT!JetPrepareUpdate` at `0x180013b3d`

## string_xrefs

- `0x180013ab0`: `JetPrepareUpdate:SetCurrentIndex`
- `0x180013aeb`: `JetPrepareUpdate:MakeKey`
- `0x180013b17`: `JetPrepareUpdate:Seek`
- `0x180013b4b`: `JetPrepareUpdate:PrepareUpdate`

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
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_41653652a8cc332f218bba10df165c1f_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180013a6c  mov     [rsp+arg_0], rbx
0x180013a71  mov     [rsp+arg_8], rbp
0x180013a76  mov     [rsp+arg_10], rdi
0x180013a7b  push    r14
0x180013a7d  sub     rsp, 30h
0x180013a81  mov     rdi, cs:DhcpGlobalClientTableV6Handle
0x180013a88  mov     ebp, r9d
0x180013a8b  mov     r14, rdx
0x180013a8e  test    r9d, r9d
0x180013a91  jnz     loc_180013B29
0x180013a97  mov     r8, rcx
0x180013a9a  mov     rdx, rdi
0x180013a9d  mov     rcx, [rsp+38h+sesid]
0x180013aa2  call    cs:__imp_JetSetCurrentIndex
0x180013aa9  nop     dword ptr [rax+rax+00h]
0x180013aae  mov     ecx, eax
0x180013ab0  lea     rdx, aJetprepareupda; "JetPrepareUpdate:SetCurrentIndex"
0x180013ab7  call    DhcpMapJetError
0x180013abc  mov     ebx, eax
0x180013abe  test    eax, eax
0x180013ac0  jnz     loc_180013B5D
0x180013ac6  mov     rcx, [rsp+38h+sesid]; sesid
0x180013acb  lea     r9d, [rbp+0Bh]; cbData
0x180013acf  mov     r8, r14; pvData
0x180013ad2  mov     [rsp+38h+grbit], 1; grbit
0x180013ada  mov     rdx, rdi; tableid
0x180013add  call    cs:__imp_JetMakeKey
0x180013ae4  nop     dword ptr [rax+rax+00h]
0x180013ae9  mov     ecx, eax
0x180013aeb  lea     rdx, aJetprepareupda_1; "JetPrepareUpdate:MakeKey"
0x180013af2  call    DhcpMapJetError
0x180013af7  mov     ebx, eax
0x180013af9  test    eax, eax
0x180013afb  jnz     short loc_180013B5D
0x180013afd  mov     rcx, [rsp+38h+sesid]; sesid
0x180013b02  lea     r8d, [rbp+1]; grbit
0x180013b06  mov     rdx, rdi; tableid
0x180013b09  call    cs:__imp_JetSeek
0x180013b10  nop     dword ptr [rax+rax+00h]
0x180013b15  mov     ecx, eax
0x180013b17  lea     rdx, aJetprepareupda_2; "JetPrepareUpdate:Seek"
0x180013b1e  call    DhcpMapJetError
0x180013b23  mov     ebx, eax
0x180013b25  test    eax, eax
0x180013b27  jnz     short loc_180013B5D
0x180013b29  mov     rcx, [rsp+38h+sesid]; sesid
0x180013b2e  neg     ebp
0x180013b30  mov     rdx, rdi; tableid
0x180013b33  sbb     r8d, r8d
0x180013b36  not     r8d
0x180013b39  and     r8d, 2; prep
0x180013b3d  call    cs:__imp_JetPrepareUpdate
0x180013b44  nop     dword ptr [rax+rax+00h]
0x180013b49  mov     ecx, eax
0x180013b4b  lea     rdx, aJetprepareupda_3; "JetPrepareUpdate:PrepareUpdate"
0x180013b52  call    DhcpMapJetError
0x180013b57  mov     ebx, eax
0x180013b59  test    eax, eax
0x180013b5b  jz      short loc_180013B91
0x180013b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b64  lea     rax, WPP_GLOBAL_Control
0x180013b6b  cmp     rcx, rax
0x180013b6e  jz      short loc_180013B91
0x180013b70  test    dword ptr [rcx+1Ch], 800h
0x180013b77  jz      short loc_180013B91
0x180013b79  mov     rcx, [rcx+10h]
0x180013b7d  lea     r8, WPP_41653652a8cc332f218bba10df165c1f_Traceguids
0x180013b84  mov     edx, 0Eh
0x180013b89  mov     r9d, ebx
0x180013b8c  call    WPP_SF_D
0x180013b91  mov     rbp, [rsp+38h+arg_8]
0x180013b96  mov     eax, ebx
0x180013b98  mov     rbx, [rsp+38h+arg_0]
0x180013b9d  mov     rdi, [rsp+38h+arg_10]
0x180013ba2  add     rsp, 30h
0x180013ba6  pop     r14
0x180013ba8  retn
```
