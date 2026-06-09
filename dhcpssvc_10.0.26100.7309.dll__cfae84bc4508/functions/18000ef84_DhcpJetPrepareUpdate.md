# DhcpJetPrepareUpdate

- ea: `0x18000ef84`
- end: `0x18000f0bc`
- name: `DhcpJetPrepareUpdate`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180006ab8`
- `0x1800083d0`
- `0x1800093a0`
- `0x18000d97c`
- `0x180010360`
- `0x180020bb4`
- `0x180021b20`
- `0x18004e75c`

## callees

- `0x18000ef84`
- `0x18000f144`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x18000efc0`
- `ESENT!JetSetCurrentIndex` at `0x18000efc0`
- `ESENT!JetMakeKey` at `0x18000f012`
- `ESENT!JetMakeKey` at `0x18000f012`
- `ESENT!JetSeek` at `0x18000f046`
- `ESENT!JetSeek` at `0x18000f046`
- `ESENT!JetPrepareUpdate` at `0x18000f086`
- `ESENT!JetPrepareUpdate` at `0x18000f086`

## string_xrefs

- `0x18000efce`: `JetPrepareUpdate:SetCurrentIndex`
- `0x18000f020`: `JetPrepareUpdate:MakeKey`
- `0x18000f054`: `JetPrepareUpdate:Seek`
- `0x18000f094`: `JetPrepareUpdate:PrepareUpdate`

## pseudocode

```c
__int64 __fastcall DhcpJetPrepareUpdate(__int64 a1, const void *a2, __int64 a3, int a4)
{
  unsigned int Key; // esi
  unsigned int v8; // ebp
  unsigned int v10; // eax

  if ( !a4
    && ((Key = JetSetCurrentIndex(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, a1),
         (v8 = DhcpMapJetError(Key, "JetPrepareUpdate:SetCurrentIndex")) != 0)
     || (Key = JetMakeKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, a2, 4u, 1u),
         (v8 = DhcpMapJetError(Key, "JetPrepareUpdate:MakeKey")) != 0)
     || (Key = JetSeek(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 1u),
         (v8 = DhcpMapJetError(Key, "JetPrepareUpdate:Seek")) != 0)) )
  {
    DhcpMapJetError(Key, a1);
    return v8;
  }
  else
  {
    v10 = JetPrepareUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, a4 == 0 ? 2 : 0);
    return DhcpMapJetError(v10, "JetPrepareUpdate:PrepareUpdate");
  }
}

```

## disassembly

```asm
0x18000ef84  mov     rax, rsp
0x18000ef87  mov     [rax+8], rbx
0x18000ef8b  mov     [rax+10h], rbp
0x18000ef8f  mov     [rax+18h], rsi
0x18000ef93  mov     [rax+20h], rdi
0x18000ef97  push    r14
0x18000ef99  sub     rsp, 30h
0x18000ef9d  mov     edi, r9d
0x18000efa0  mov     r14, rdx
0x18000efa3  mov     rbx, rcx
0x18000efa6  test    r9d, r9d
0x18000efa9  jnz     loc_18000F06C
0x18000efaf  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000efb6  mov     r8, rcx
0x18000efb9  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000efc0  call    cs:__imp_JetSetCurrentIndex
0x18000efc7  nop     dword ptr [rax+rax+00h]
0x18000efcc  mov     ecx, eax
0x18000efce  lea     rdx, aJetprepareupda; "JetPrepareUpdate:SetCurrentIndex"
0x18000efd5  mov     esi, eax
0x18000efd7  call    DhcpMapJetError
0x18000efdc  mov     ebp, eax
0x18000efde  test    eax, eax
0x18000efe0  jz      short loc_18000EFF3
0x18000efe2  mov     rdx, rbx
0x18000efe5  mov     ecx, esi
0x18000efe7  call    DhcpMapJetError
0x18000efec  mov     eax, ebp
0x18000efee  jmp     loc_18000F0A0
0x18000eff3  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000effa  mov     r9d, 4; cbData
0x18000f000  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000f007  mov     r8, r14; pvData
0x18000f00a  mov     [rsp+38h+grbit], 1; grbit
0x18000f012  call    cs:__imp_JetMakeKey
0x18000f019  nop     dword ptr [rax+rax+00h]
0x18000f01e  mov     ecx, eax
0x18000f020  lea     rdx, aJetprepareupda_1; "JetPrepareUpdate:MakeKey"
0x18000f027  mov     esi, eax
0x18000f029  call    DhcpMapJetError
0x18000f02e  mov     ebp, eax
0x18000f030  test    eax, eax
0x18000f032  jnz     short loc_18000EFE2
0x18000f034  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000f03b  lea     r8d, [rax+1]; grbit
0x18000f03f  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000f046  call    cs:__imp_JetSeek
0x18000f04d  nop     dword ptr [rax+rax+00h]
0x18000f052  mov     ecx, eax
0x18000f054  lea     rdx, aJetprepareupda_2; "JetPrepareUpdate:Seek"
0x18000f05b  mov     esi, eax
0x18000f05d  call    DhcpMapJetError
0x18000f062  mov     ebp, eax
0x18000f064  test    eax, eax
0x18000f066  jnz     loc_18000EFE2
0x18000f06c  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000f073  neg     edi
0x18000f075  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000f07c  sbb     r8d, r8d
0x18000f07f  not     r8d
0x18000f082  and     r8d, 2; prep
0x18000f086  call    cs:__imp_JetPrepareUpdate
0x18000f08d  nop     dword ptr [rax+rax+00h]
0x18000f092  mov     ecx, eax
0x18000f094  lea     rdx, aJetprepareupda_3; "JetPrepareUpdate:PrepareUpdate"
0x18000f09b  call    DhcpMapJetError
0x18000f0a0  mov     rbx, [rsp+38h+arg_0]
0x18000f0a5  mov     rbp, [rsp+38h+arg_8]
0x18000f0aa  mov     rsi, [rsp+38h+arg_10]
0x18000f0af  mov     rdi, [rsp+38h+arg_18]
0x18000f0b4  add     rsp, 30h
0x18000f0b8  pop     r14
0x18000f0ba  retn
```
