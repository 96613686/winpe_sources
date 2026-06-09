# MadcapJetPrepareSearch

- ea: `0x180028670`
- end: `0x180028765`
- name: `MadcapJetPrepareSearch`
- size: `245`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002891c`
- `0x180028b08`
- `0x180029144`
- `0x180029360`
- `0x18002d1f0`

## callees

- `0x18000e814`
- `0x180028670`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x18002869f`
- `ESENT!JetSetCurrentIndex` at `0x18002869f`
- `ESENT!JetMakeKey` at `0x180028703`
- `ESENT!JetMakeKey` at `0x180028703`
- `ESENT!JetSeek` at `0x180028731`
- `ESENT!JetSeek` at `0x180028731`
- `ESENT!JetMove` at `0x1800286e5`
- `ESENT!JetMove` at `0x1800286e5`

## string_xrefs

- `0x18002873d`: `M:PrepareSearch:Move/Seek`

## pseudocode

```c
__int64 __fastcall MadcapJetPrepareSearch(__int64 a1, __int64 a2, int a3, const void *a4, unsigned int cbData)
{
  unsigned int Key; // esi
  unsigned int v10; // ebp
  JET_TABLEID v12; // rdx
  JET_SESID v13; // rcx
  unsigned int v14; // eax

  Key = JetSetCurrentIndex(*(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), a2);
  v10 = DhcpMapJetError(Key, "M:PrepareSearch:SetcurrentIndex");
  if ( v10 )
    goto LABEL_2;
  v12 = *(_QWORD *)(a1 + 16);
  v13 = *(_QWORD *)(a1 + 8);
  if ( a3 )
  {
    v14 = JetMove(v13, v12, 0x80000000, 0);
  }
  else
  {
    Key = JetMakeKey(v13, v12, a4, cbData, 1u);
    v10 = DhcpMapJetError(Key, "M:PrepareSearch:MakeKey");
    if ( v10 )
    {
LABEL_2:
      DhcpMapJetError(Key, a2);
      return v10;
    }
    v14 = JetSeek(*(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), 0x10u);
  }
  return DhcpMapJetError(v14, "M:PrepareSearch:Move/Seek");
}

```

## disassembly

```asm
0x180028670  mov     [rsp+arg_0], rbx
0x180028675  mov     [rsp+arg_8], rbp
0x18002867a  mov     [rsp+arg_10], rsi
0x18002867f  push    rdi
0x180028680  push    r14
0x180028682  push    r15
0x180028684  sub     rsp, 30h
0x180028688  mov     r14d, r8d
0x18002868b  mov     rdi, rdx
0x18002868e  mov     r8, rdx
0x180028691  mov     rbx, rcx
0x180028694  mov     rdx, [rcx+10h]
0x180028698  mov     r15, r9
0x18002869b  mov     rcx, [rcx+8]
0x18002869f  call    cs:__imp_JetSetCurrentIndex
0x1800286a6  nop     dword ptr [rax+rax+00h]
0x1800286ab  mov     ecx, eax
0x1800286ad  lea     rdx, aMPreparesearch; "M:PrepareSearch:SetcurrentIndex"
0x1800286b4  mov     esi, eax
0x1800286b6  call    DhcpMapJetError
0x1800286bb  mov     ebp, eax
0x1800286bd  test    eax, eax
0x1800286bf  jz      short loc_1800286CF
0x1800286c1  mov     rdx, rdi
0x1800286c4  mov     ecx, esi
0x1800286c6  call    DhcpMapJetError
0x1800286cb  mov     eax, ebp
0x1800286cd  jmp     short loc_18002874B
0x1800286cf  mov     rdx, [rbx+10h]; tableid
0x1800286d3  mov     rcx, [rbx+8]; sesid
0x1800286d7  test    r14d, r14d
0x1800286da  jz      short loc_1800286F3
0x1800286dc  xor     r9d, r9d; grbit
0x1800286df  mov     r8d, 80000000h; cRow
0x1800286e5  call    cs:__imp_JetMove
0x1800286ec  nop     dword ptr [rax+rax+00h]
0x1800286f1  jmp     short loc_18002873D
0x1800286f3  mov     r9d, [rsp+48h+cbData]; cbData
0x1800286f8  mov     r8, r15; pvData
0x1800286fb  mov     [rsp+48h+grbit], 1; grbit
0x180028703  call    cs:__imp_JetMakeKey
0x18002870a  nop     dword ptr [rax+rax+00h]
0x18002870f  mov     ecx, eax
0x180028711  lea     rdx, aMPreparesearch_0; "M:PrepareSearch:MakeKey"
0x180028718  mov     esi, eax
0x18002871a  call    DhcpMapJetError
0x18002871f  mov     ebp, eax
0x180028721  test    eax, eax
0x180028723  jnz     short loc_1800286C1
0x180028725  mov     rdx, [rbx+10h]; tableid
0x180028729  lea     r8d, [rax+10h]; grbit
0x18002872d  mov     rcx, [rbx+8]; sesid
0x180028731  call    cs:__imp_JetSeek
0x180028738  nop     dword ptr [rax+rax+00h]
0x18002873d  lea     rdx, aMPreparesearch_1; "M:PrepareSearch:Move/Seek"
0x180028744  mov     ecx, eax
0x180028746  call    DhcpMapJetError
0x18002874b  mov     rbx, [rsp+48h+arg_0]
0x180028750  mov     rbp, [rsp+48h+arg_8]
0x180028755  mov     rsi, [rsp+48h+arg_10]
0x18002875a  add     rsp, 30h
0x18002875e  pop     r15
0x180028760  pop     r14
0x180028762  pop     rdi
0x180028763  retn
```
