# DhcpJetPrepareSearch

- ea: `0x18000e540`
- end: `0x18000e646`
- name: `DhcpJetPrepareSearch`
- size: `262`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800068e4`
- `0x180009c10`
- `0x18000a000`
- `0x18000a390`
- `0x18000a780`
- `0x18004a1a4`
- `0x18004edbc`
- `0x1800503c8`

## callees

- `0x18000e540`
- `0x18000e814`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x18000e574`
- `ESENT!JetSetCurrentIndex` at `0x18000e574`
- `ESENT!JetMakeKey` at `0x18000e5de`
- `ESENT!JetMakeKey` at `0x18000e5de`
- `ESENT!JetSeek` at `0x18000e612`
- `ESENT!JetSeek` at `0x18000e612`
- `ESENT!JetMove` at `0x18000e5c2`
- `ESENT!JetMove` at `0x18000e5c2`

## string_xrefs

- `0x18000e61e`: `PrepareSearch:Move/Seek`

## pseudocode

```c
__int64 __fastcall DhcpJetPrepareSearch(__int64 a1, int a2, const void *a3, unsigned int a4)
{
  unsigned int Key; // edi
  unsigned int v9; // esi
  unsigned int v11; // eax

  Key = JetSetCurrentIndex(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, a1);
  v9 = DhcpMapJetError(Key, "PrepareSearch:SetCurrentIndex");
  if ( v9 )
    goto LABEL_2;
  if ( a2 )
  {
    v11 = JetMove(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 0x80000000, 0);
  }
  else
  {
    Key = JetMakeKey(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, a3, a4, 1u);
    v9 = DhcpMapJetError(Key, "PrepareSearch:MakeKey");
    if ( v9 )
    {
LABEL_2:
      DhcpMapJetError(Key, a1);
      return v9;
    }
    v11 = JetSeek(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 0x10u);
  }
  return DhcpMapJetError(v11, "PrepareSearch:Move/Seek");
}

```

## disassembly

```asm
0x18000e540  mov     [rsp+arg_0], rbx
0x18000e545  mov     [rsp+arg_8], rbp
0x18000e54a  mov     [rsp+arg_10], rsi
0x18000e54f  push    rdi
0x18000e550  push    r14
0x18000e552  push    r15
0x18000e554  sub     rsp, 30h
0x18000e558  mov     r15, r8
0x18000e55b  mov     ebp, edx
0x18000e55d  mov     rdx, cs:DhcpGlobalClientTableHandle
0x18000e564  mov     r8, rcx
0x18000e567  mov     rbx, rcx
0x18000e56a  mov     r14d, r9d
0x18000e56d  mov     rcx, cs:DhcpGlobalJetServerSession
0x18000e574  call    cs:__imp_JetSetCurrentIndex
0x18000e57b  nop     dword ptr [rax+rax+00h]
0x18000e580  mov     ecx, eax
0x18000e582  lea     rdx, aPreparesearchS; "PrepareSearch:SetCurrentIndex"
0x18000e589  mov     edi, eax
0x18000e58b  call    DhcpMapJetError
0x18000e590  mov     esi, eax
0x18000e592  test    eax, eax
0x18000e594  jz      short loc_18000E5A7
0x18000e596  mov     rdx, rbx
0x18000e599  mov     ecx, edi
0x18000e59b  call    DhcpMapJetError
0x18000e5a0  mov     eax, esi
0x18000e5a2  jmp     loc_18000E62C
0x18000e5a7  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000e5ae  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000e5b5  test    ebp, ebp
0x18000e5b7  jz      short loc_18000E5D0
0x18000e5b9  xor     r9d, r9d; grbit
0x18000e5bc  mov     r8d, 80000000h; cRow
0x18000e5c2  call    cs:__imp_JetMove
0x18000e5c9  nop     dword ptr [rax+rax+00h]
0x18000e5ce  jmp     short loc_18000E61E
0x18000e5d0  mov     r9d, r14d; cbData
0x18000e5d3  mov     [rsp+48h+grbit], 1; grbit
0x18000e5db  mov     r8, r15; pvData
0x18000e5de  call    cs:__imp_JetMakeKey
0x18000e5e5  nop     dword ptr [rax+rax+00h]
0x18000e5ea  mov     ecx, eax
0x18000e5ec  lea     rdx, aPreparesearchM; "PrepareSearch:MakeKey"
0x18000e5f3  mov     edi, eax
0x18000e5f5  call    DhcpMapJetError
0x18000e5fa  mov     esi, eax
0x18000e5fc  test    eax, eax
0x18000e5fe  jnz     short loc_18000E596
0x18000e600  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x18000e607  lea     r8d, [rax+10h]; grbit
0x18000e60b  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18000e612  call    cs:__imp_JetSeek
0x18000e619  nop     dword ptr [rax+rax+00h]
0x18000e61e  lea     rdx, aPreparesearchM_0; "PrepareSearch:Move/Seek"
0x18000e625  mov     ecx, eax
0x18000e627  call    DhcpMapJetError
0x18000e62c  mov     rbx, [rsp+48h+arg_0]
0x18000e631  mov     rbp, [rsp+48h+arg_8]
0x18000e636  mov     rsi, [rsp+48h+arg_10]
0x18000e63b  add     rsp, 30h
0x18000e63f  pop     r15
0x18000e641  pop     r14
0x18000e643  pop     rdi
0x18000e644  retn
```
