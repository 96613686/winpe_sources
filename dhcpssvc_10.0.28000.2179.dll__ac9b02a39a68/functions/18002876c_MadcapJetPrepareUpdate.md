# MadcapJetPrepareUpdate

- ea: `0x18002876c`
- end: `0x180028898`
- name: `MadcapJetPrepareUpdate`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18002954c`

## callees

- `0x18000e814`
- `0x18002876c`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x1800287ac`
- `ESENT!JetSetCurrentIndex` at `0x1800287ac`
- `ESENT!JetMakeKey` at `0x1800287fa`
- `ESENT!JetMakeKey` at `0x1800287fa`
- `ESENT!JetSeek` at `0x180028828`
- `ESENT!JetSeek` at `0x180028828`
- `ESENT!JetPrepareUpdate` at `0x18002885e`
- `ESENT!JetPrepareUpdate` at `0x18002885e`

## string_xrefs

- `0x1800287ba`: `M:PrepareUpdate`
- `0x180028808`: `M:prepareupdate:MakeKey`
- `0x180028836`: `M:PrepareUpdate:Seek`
- `0x18002886c`: `M:PrepareUpdate:PrepareUpdate`

## pseudocode

```c
__int64 __fastcall MadcapJetPrepareUpdate(__int64 a1, __int64 a2, const void *a3, __int64 a4, int a5)
{
  JET_TABLEID *v5; // rbx
  JET_SESID *v6; // rdi
  unsigned int Key; // r14d
  unsigned int v10; // r15d
  unsigned int v12; // eax

  v5 = (JET_TABLEID *)(a1 + 16);
  v6 = (JET_SESID *)(a1 + 8);
  if ( !a5
    && ((Key = JetSetCurrentIndex(*v6, *v5, a2), (v10 = DhcpMapJetError(Key, "M:PrepareUpdate")) != 0)
     || (Key = JetMakeKey(*v6, *v5, a3, 4u, 1u), (v10 = DhcpMapJetError(Key, "M:prepareupdate:MakeKey")) != 0)
     || (Key = JetSeek(*v6, *v5, 1u), (v10 = DhcpMapJetError(Key, "M:PrepareUpdate:Seek")) != 0)) )
  {
    DhcpMapJetError(Key, a2);
    return v10;
  }
  else
  {
    v12 = JetPrepareUpdate(*v6, *v5, a5 == 0 ? 2 : 0);
    return DhcpMapJetError(v12, "M:PrepareUpdate:PrepareUpdate");
  }
}

```

## disassembly

```asm
0x18002876c  mov     rax, rsp
0x18002876f  mov     [rax+8], rbx
0x180028773  mov     [rax+10h], rbp
0x180028777  mov     [rax+18h], rsi
0x18002877b  mov     [rax+20h], rdi
0x18002877f  push    r12
0x180028781  push    r14
0x180028783  push    r15
0x180028785  sub     rsp, 30h
0x180028789  mov     ebp, [rsp+48h+arg_20]
0x18002878d  lea     rbx, [rcx+10h]
0x180028791  lea     rdi, [rcx+8]
0x180028795  mov     r12, r8
0x180028798  mov     rsi, rdx
0x18002879b  test    ebp, ebp
0x18002879d  jnz     loc_18002884C
0x1800287a3  mov     rcx, [rdi]
0x1800287a6  mov     r8, rdx
0x1800287a9  mov     rdx, [rbx]
0x1800287ac  call    cs:__imp_JetSetCurrentIndex
0x1800287b3  nop     dword ptr [rax+rax+00h]
0x1800287b8  mov     ecx, eax
0x1800287ba  lea     rdx, aMPrepareupdate_2; "M:PrepareUpdate"
0x1800287c1  mov     r14d, eax
0x1800287c4  call    DhcpMapJetError
0x1800287c9  mov     r15d, eax
0x1800287cc  test    eax, eax
0x1800287ce  jz      short loc_1800287E3
0x1800287d0  mov     rdx, rsi
0x1800287d3  mov     ecx, r14d
0x1800287d6  call    DhcpMapJetError
0x1800287db  mov     eax, r15d
0x1800287de  jmp     loc_180028878
0x1800287e3  mov     rdx, [rbx]; tableid
0x1800287e6  mov     r9d, 4; cbData
0x1800287ec  mov     rcx, [rdi]; sesid
0x1800287ef  mov     r8, r12; pvData
0x1800287f2  mov     [rsp+48h+grbit], 1; grbit
0x1800287fa  call    cs:__imp_JetMakeKey
0x180028801  nop     dword ptr [rax+rax+00h]
0x180028806  mov     ecx, eax
0x180028808  lea     rdx, aMPrepareupdate; "M:prepareupdate:MakeKey"
0x18002880f  mov     r14d, eax
0x180028812  call    DhcpMapJetError
0x180028817  mov     r15d, eax
0x18002881a  test    eax, eax
0x18002881c  jnz     short loc_1800287D0
0x18002881e  mov     rdx, [rbx]; tableid
0x180028821  lea     r8d, [rax+1]; grbit
0x180028825  mov     rcx, [rdi]; sesid
0x180028828  call    cs:__imp_JetSeek
0x18002882f  nop     dword ptr [rax+rax+00h]
0x180028834  mov     ecx, eax
0x180028836  lea     rdx, aMPrepareupdate_0; "M:PrepareUpdate:Seek"
0x18002883d  mov     r14d, eax
0x180028840  call    DhcpMapJetError
0x180028845  mov     r15d, eax
0x180028848  test    eax, eax
0x18002884a  jnz     short loc_1800287D0
0x18002884c  mov     rdx, [rbx]; tableid
0x18002884f  neg     ebp
0x180028851  mov     rcx, [rdi]; sesid
0x180028854  sbb     r8d, r8d
0x180028857  not     r8d
0x18002885a  and     r8d, 2; prep
0x18002885e  call    cs:__imp_JetPrepareUpdate
0x180028865  nop     dword ptr [rax+rax+00h]
0x18002886a  mov     ecx, eax
0x18002886c  lea     rdx, aMPrepareupdate_1; "M:PrepareUpdate:PrepareUpdate"
0x180028873  call    DhcpMapJetError
0x180028878  mov     rbx, [rsp+48h+arg_0]
0x18002887d  mov     rbp, [rsp+48h+arg_8]
0x180028882  mov     rsi, [rsp+48h+arg_10]
0x180028887  mov     rdi, [rsp+48h+arg_18]
0x18002888c  add     rsp, 30h
0x180028890  pop     r15
0x180028892  pop     r14
0x180028894  pop     r12
0x180028896  retn
```
