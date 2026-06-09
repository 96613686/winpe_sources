# DhcpJetPrepareUpdate

- ea: `0x18000e64c`
- end: `0x18000e784`
- name: `DhcpJetPrepareUpdate`
- size: `312`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180006aec`
- `0x1800083cc`
- `0x1800092e0`
- `0x18000d028`
- `0x18000fa40`
- `0x180020094`
- `0x180020fdc`
- `0x18004e3bc`

## callees

- `0x18000e64c`
- `0x18000e814`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x18000e688`
- `ESENT!JetSetCurrentIndex` at `0x18000e688`
- `ESENT!JetMakeKey` at `0x18000e6da`
- `ESENT!JetMakeKey` at `0x18000e6da`
- `ESENT!JetSeek` at `0x18000e70e`
- `ESENT!JetSeek` at `0x18000e70e`
- `ESENT!JetPrepareUpdate` at `0x18000e74e`
- `ESENT!JetPrepareUpdate` at `0x18000e74e`

## string_xrefs

- `0x18000e696`: `JetPrepareUpdate:SetCurrentIndex`
- `0x18000e6e8`: `JetPrepareUpdate:MakeKey`
- `0x18000e71c`: `JetPrepareUpdate:Seek`
- `0x18000e75c`: `JetPrepareUpdate:PrepareUpdate`

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
0x18000e64c  mov     rax, rsp
0x18000e64f  mov     [rax+8], rbx
0x18000e653  mov     [rax+10h], rbp
0x18000e657  mov     [rax+18h], rsi
0x18000e65b  mov     [rax+20h], rdi
0x18000e65f  push    r14
0x18000e661  sub     rsp, 30h
0x18000e665  mov     edi, r9d
0x18000e668  mov     r14, rdx
0x18000e66b  mov     rbx, rcx
0x18000e66e  test    r9d, r9d
0x18000e671  jnz     loc_18000E734
0x18000e677  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000e67e  mov     r8, rcx
0x18000e681  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000e688  call    cs:__imp_JetSetCurrentIndex
0x18000e68f  nop     dword ptr [rax+rax+00h]
0x18000e694  mov     ecx, eax
0x18000e696  lea     rdx, aJetprepareupda; "JetPrepareUpdate:SetCurrentIndex"
0x18000e69d  mov     esi, eax
0x18000e69f  call    DhcpMapJetError
0x18000e6a4  mov     ebp, eax
0x18000e6a6  test    eax, eax
0x18000e6a8  jz      short loc_18000E6BB
0x18000e6aa  mov     rdx, rbx
0x18000e6ad  mov     ecx, esi
0x18000e6af  call    DhcpMapJetError
0x18000e6b4  mov     eax, ebp
0x18000e6b6  jmp     loc_18000E768
0x18000e6bb  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000e6c2  mov     r9d, 4; cbData
0x18000e6c8  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000e6cf  mov     r8, r14; pvData
0x18000e6d2  mov     [rsp+38h+grbit], 1; grbit
0x18000e6da  call    cs:__imp_JetMakeKey
0x18000e6e1  nop     dword ptr [rax+rax+00h]
0x18000e6e6  mov     ecx, eax
0x18000e6e8  lea     rdx, aJetprepareupda_1; "JetPrepareUpdate:MakeKey"
0x18000e6ef  mov     esi, eax
0x18000e6f1  call    DhcpMapJetError
0x18000e6f6  mov     ebp, eax
0x18000e6f8  test    eax, eax
0x18000e6fa  jnz     short loc_18000E6AA
0x18000e6fc  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000e703  lea     r8d, [rax+1]; grbit
0x18000e707  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000e70e  call    cs:__imp_JetSeek
0x18000e715  nop     dword ptr [rax+rax+00h]
0x18000e71a  mov     ecx, eax
0x18000e71c  lea     rdx, aJetprepareupda_2; "JetPrepareUpdate:Seek"
0x18000e723  mov     esi, eax
0x18000e725  call    DhcpMapJetError
0x18000e72a  mov     ebp, eax
0x18000e72c  test    eax, eax
0x18000e72e  jnz     loc_18000E6AA
0x18000e734  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000e73b  neg     edi
0x18000e73d  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000e744  sbb     r8d, r8d
0x18000e747  not     r8d
0x18000e74a  and     r8d, 2; prep
0x18000e74e  call    cs:__imp_JetPrepareUpdate
0x18000e755  nop     dword ptr [rax+rax+00h]
0x18000e75a  mov     ecx, eax
0x18000e75c  lea     rdx, aJetprepareupda_3; "JetPrepareUpdate:PrepareUpdate"
0x18000e763  call    DhcpMapJetError
0x18000e768  mov     rbx, [rsp+38h+arg_0]
0x18000e76d  mov     rbp, [rsp+38h+arg_8]
0x18000e772  mov     rsi, [rsp+38h+arg_10]
0x18000e777  mov     rdi, [rsp+38h+arg_18]
0x18000e77c  add     rsp, 30h
0x18000e780  pop     r14
0x18000e782  retn
```
