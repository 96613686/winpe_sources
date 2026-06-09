# MadcapJetPrepareUpdate

- ea: `0x1800291c0`
- end: `0x1800292ec`
- name: `MadcapJetPrepareUpdate`
- size: `300`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180029f8c`

## callees

- `0x18000f144`
- `0x1800291c0`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x180029200`
- `ESENT!JetSetCurrentIndex` at `0x180029200`
- `ESENT!JetMakeKey` at `0x18002924e`
- `ESENT!JetMakeKey` at `0x18002924e`
- `ESENT!JetSeek` at `0x18002927c`
- `ESENT!JetSeek` at `0x18002927c`
- `ESENT!JetPrepareUpdate` at `0x1800292b2`
- `ESENT!JetPrepareUpdate` at `0x1800292b2`

## string_xrefs

- `0x18002920e`: `M:PrepareUpdate`
- `0x18002925c`: `M:prepareupdate:MakeKey`
- `0x18002928a`: `M:PrepareUpdate:Seek`
- `0x1800292c0`: `M:PrepareUpdate:PrepareUpdate`

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
0x1800291c0  mov     rax, rsp
0x1800291c3  mov     [rax+8], rbx
0x1800291c7  mov     [rax+10h], rbp
0x1800291cb  mov     [rax+18h], rsi
0x1800291cf  mov     [rax+20h], rdi
0x1800291d3  push    r12
0x1800291d5  push    r14
0x1800291d7  push    r15
0x1800291d9  sub     rsp, 30h
0x1800291dd  mov     ebp, [rsp+48h+arg_20]
0x1800291e1  lea     rbx, [rcx+10h]
0x1800291e5  lea     rdi, [rcx+8]
0x1800291e9  mov     r12, r8
0x1800291ec  mov     rsi, rdx
0x1800291ef  test    ebp, ebp
0x1800291f1  jnz     loc_1800292A0
0x1800291f7  mov     rcx, [rdi]
0x1800291fa  mov     r8, rdx
0x1800291fd  mov     rdx, [rbx]
0x180029200  call    cs:__imp_JetSetCurrentIndex
0x180029207  nop     dword ptr [rax+rax+00h]
0x18002920c  mov     ecx, eax
0x18002920e  lea     rdx, aMPrepareupdate_2; "M:PrepareUpdate"
0x180029215  mov     r14d, eax
0x180029218  call    DhcpMapJetError
0x18002921d  mov     r15d, eax
0x180029220  test    eax, eax
0x180029222  jz      short loc_180029237
0x180029224  mov     rdx, rsi
0x180029227  mov     ecx, r14d
0x18002922a  call    DhcpMapJetError
0x18002922f  mov     eax, r15d
0x180029232  jmp     loc_1800292CC
0x180029237  mov     rdx, [rbx]; tableid
0x18002923a  mov     r9d, 4; cbData
0x180029240  mov     rcx, [rdi]; sesid
0x180029243  mov     r8, r12; pvData
0x180029246  mov     [rsp+48h+grbit], 1; grbit
0x18002924e  call    cs:__imp_JetMakeKey
0x180029255  nop     dword ptr [rax+rax+00h]
0x18002925a  mov     ecx, eax
0x18002925c  lea     rdx, aMPrepareupdate; "M:prepareupdate:MakeKey"
0x180029263  mov     r14d, eax
0x180029266  call    DhcpMapJetError
0x18002926b  mov     r15d, eax
0x18002926e  test    eax, eax
0x180029270  jnz     short loc_180029224
0x180029272  mov     rdx, [rbx]; tableid
0x180029275  lea     r8d, [rax+1]; grbit
0x180029279  mov     rcx, [rdi]; sesid
0x18002927c  call    cs:__imp_JetSeek
0x180029283  nop     dword ptr [rax+rax+00h]
0x180029288  mov     ecx, eax
0x18002928a  lea     rdx, aMPrepareupdate_0; "M:PrepareUpdate:Seek"
0x180029291  mov     r14d, eax
0x180029294  call    DhcpMapJetError
0x180029299  mov     r15d, eax
0x18002929c  test    eax, eax
0x18002929e  jnz     short loc_180029224
0x1800292a0  mov     rdx, [rbx]; tableid
0x1800292a3  neg     ebp
0x1800292a5  mov     rcx, [rdi]; sesid
0x1800292a8  sbb     r8d, r8d
0x1800292ab  not     r8d
0x1800292ae  and     r8d, 2; prep
0x1800292b2  call    cs:__imp_JetPrepareUpdate
0x1800292b9  nop     dword ptr [rax+rax+00h]
0x1800292be  mov     ecx, eax
0x1800292c0  lea     rdx, aMPrepareupdate_1; "M:PrepareUpdate:PrepareUpdate"
0x1800292c7  call    DhcpMapJetError
0x1800292cc  mov     rbx, [rsp+48h+arg_0]
0x1800292d1  mov     rbp, [rsp+48h+arg_8]
0x1800292d6  mov     rsi, [rsp+48h+arg_10]
0x1800292db  mov     rdi, [rsp+48h+arg_18]
0x1800292e0  add     rsp, 30h
0x1800292e4  pop     r15
0x1800292e6  pop     r14
0x1800292e8  pop     r12
0x1800292ea  retn
```
