# DhcpJetPrepareSearchV6

- ea: `0x180013f88`
- end: `0x1800140b8`
- name: `DhcpJetPrepareSearchV6`
- size: `304`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180002bb4`
- `0x180012778`
- `0x180014d30`
- `0x1800427f0`

## callees

- `0x180002854`
- `0x18000f144`
- `0x180013f88`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x180013fbb`
- `ESENT!JetSetCurrentIndex` at `0x180013fbb`
- `ESENT!JetMakeKey` at `0x180014071`
- `ESENT!JetMakeKey` at `0x180014071`
- `ESENT!JetSeek` at `0x1800140a0`
- `ESENT!JetSeek` at `0x1800140a0`
- `ESENT!JetMove` at `0x180013ff0`
- `ESENT!JetMove` at `0x180013ff0`

## string_xrefs

- `0x180013ffc`: `DhcpJetPrepareSearchV6:JetMove`

## pseudocode

```c
__int64 __fastcall DhcpJetPrepareSearchV6(
        __int64 a1,
        int a2,
        const void *a3,
        unsigned int a4,
        __int64 a5,
        JET_SESID sesid)
{
  JET_TABLEID v6; // rdi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  const char *v13; // rdx
  unsigned int Key; // eax

  v6 = DhcpGlobalClientTableV6Handle;
  v10 = JetSetCurrentIndex(sesid, DhcpGlobalClientTableV6Handle, a1);
  v11 = DhcpMapJetError(v10, "DhcpJetPrepareSearchV6:JetSetCurrentIndex");
  if ( !v11 )
  {
    if ( a2 )
    {
      v12 = JetMove(sesid, v6, 0x80000000, 0);
      v13 = "DhcpJetPrepareSearchV6:JetMove";
      goto LABEL_4;
    }
    Key = JetMakeKey(sesid, v6, a3, a4, 1u);
    v11 = DhcpMapJetError(Key, "DhcpJetPrepareSearchV6:JetMakeKey");
    if ( !v11 )
    {
      v12 = JetSeek(sesid, v6, 1u);
      v13 = "DhcpJetPrepareSearchV6:JetSeek";
LABEL_4:
      v11 = DhcpMapJetError(v12, v13);
      if ( !v11 )
        return v11;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_3c7468642838320b8afbb5ce47767e51_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180013f88  mov     rax, rsp
0x180013f8b  mov     [rax+8], rbx
0x180013f8f  mov     [rax+10h], rbp
0x180013f93  mov     [rax+18h], rdi
0x180013f97  mov     [rax+20h], r14
0x180013f9b  push    r15
0x180013f9d  sub     rsp, 30h
0x180013fa1  mov     rdi, cs:DhcpGlobalClientTableV6Handle
0x180013fa8  mov     r15, r8
0x180013fab  mov     r8, rcx
0x180013fae  mov     ebp, edx
0x180013fb0  mov     rcx, [rsp+38h+sesid]
0x180013fb5  mov     rdx, rdi
0x180013fb8  mov     r14d, r9d
0x180013fbb  call    cs:__imp_JetSetCurrentIndex
0x180013fc2  nop     dword ptr [rax+rax+00h]
0x180013fc7  mov     ecx, eax
0x180013fc9  lea     rdx, aDhcpjetprepare_3; "DhcpJetPrepareSearchV6:JetSetCurrentInd"...
0x180013fd0  call    DhcpMapJetError
0x180013fd5  mov     ebx, eax
0x180013fd7  test    eax, eax
0x180013fd9  jnz     short loc_180014010
0x180013fdb  mov     rcx, [rsp+38h+sesid]; sesid
0x180013fe0  mov     rdx, rdi; tableid
0x180013fe3  test    ebp, ebp
0x180013fe5  jz      short loc_180014062
0x180013fe7  xor     r9d, r9d; grbit
0x180013fea  mov     r8d, 80000000h; cRow
0x180013ff0  call    cs:__imp_JetMove
0x180013ff7  nop     dword ptr [rax+rax+00h]
0x180013ffc  lea     rdx, aDhcpjetprepare_4; "DhcpJetPrepareSearchV6:JetMove"
0x180014003  mov     ecx, eax
0x180014005  call    DhcpMapJetError
0x18001400a  mov     ebx, eax
0x18001400c  test    eax, eax
0x18001400e  jz      short loc_180014044
0x180014010  mov     rcx, cs:WPP_GLOBAL_Control
0x180014017  lea     rax, WPP_GLOBAL_Control
0x18001401e  cmp     rcx, rax
0x180014021  jz      short loc_180014044
0x180014023  test    dword ptr [rcx+1Ch], 800h
0x18001402a  jz      short loc_180014044
0x18001402c  mov     rcx, [rcx+10h]
0x180014030  lea     r8, WPP_3c7468642838320b8afbb5ce47767e51_Traceguids
0x180014037  mov     edx, 16h
0x18001403c  mov     r9d, ebx
0x18001403f  call    WPP_SF_D
0x180014044  mov     rbp, [rsp+38h+arg_8]
0x180014049  mov     eax, ebx
0x18001404b  mov     rbx, [rsp+38h+arg_0]
0x180014050  mov     rdi, [rsp+38h+arg_10]
0x180014055  mov     r14, [rsp+38h+arg_18]
0x18001405a  add     rsp, 30h
0x18001405e  pop     r15
0x180014060  retn
0x180014062  mov     ebp, 1
0x180014067  mov     r9d, r14d; cbData
0x18001406a  mov     r8, r15; pvData
0x18001406d  mov     [rsp+38h+grbit], ebp; grbit
0x180014071  call    cs:__imp_JetMakeKey
0x180014078  nop     dword ptr [rax+rax+00h]
0x18001407d  mov     ecx, eax
0x18001407f  lea     rdx, aDhcpjetprepare_6; "DhcpJetPrepareSearchV6:JetMakeKey"
0x180014086  call    DhcpMapJetError
0x18001408b  mov     ebx, eax
0x18001408d  test    eax, eax
0x18001408f  jnz     loc_180014010
0x180014095  mov     rcx, [rsp+38h+sesid]; sesid
0x18001409a  mov     r8d, ebp; grbit
0x18001409d  mov     rdx, rdi; tableid
0x1800140a0  call    cs:__imp_JetSeek
0x1800140a7  nop     dword ptr [rax+rax+00h]
0x1800140ac  lea     rdx, aDhcpjetprepare_9; "DhcpJetPrepareSearchV6:JetSeek"
0x1800140b3  jmp     loc_180014003
```
