# MadcapJetPrepareSearch

- ea: `0x1800290c4`
- end: `0x1800291b9`
- name: `MadcapJetPrepareSearch`
- size: `245`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002936c`
- `0x18002955c`
- `0x180029b90`
- `0x180029dac`
- `0x18002dc20`

## callees

- `0x18000f144`
- `0x1800290c4`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x1800290f3`
- `ESENT!JetSetCurrentIndex` at `0x1800290f3`
- `ESENT!JetMakeKey` at `0x180029157`
- `ESENT!JetMakeKey` at `0x180029157`
- `ESENT!JetSeek` at `0x180029185`
- `ESENT!JetSeek` at `0x180029185`
- `ESENT!JetMove` at `0x180029139`
- `ESENT!JetMove` at `0x180029139`

## string_xrefs

- `0x180029191`: `M:PrepareSearch:Move/Seek`

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
0x1800290c4  mov     [rsp+arg_0], rbx
0x1800290c9  mov     [rsp+arg_8], rbp
0x1800290ce  mov     [rsp+arg_10], rsi
0x1800290d3  push    rdi
0x1800290d4  push    r14
0x1800290d6  push    r15
0x1800290d8  sub     rsp, 30h
0x1800290dc  mov     r14d, r8d
0x1800290df  mov     rdi, rdx
0x1800290e2  mov     r8, rdx
0x1800290e5  mov     rbx, rcx
0x1800290e8  mov     rdx, [rcx+10h]
0x1800290ec  mov     r15, r9
0x1800290ef  mov     rcx, [rcx+8]
0x1800290f3  call    cs:__imp_JetSetCurrentIndex
0x1800290fa  nop     dword ptr [rax+rax+00h]
0x1800290ff  mov     ecx, eax
0x180029101  lea     rdx, aMPreparesearch; "M:PrepareSearch:SetcurrentIndex"
0x180029108  mov     esi, eax
0x18002910a  call    DhcpMapJetError
0x18002910f  mov     ebp, eax
0x180029111  test    eax, eax
0x180029113  jz      short loc_180029123
0x180029115  mov     rdx, rdi
0x180029118  mov     ecx, esi
0x18002911a  call    DhcpMapJetError
0x18002911f  mov     eax, ebp
0x180029121  jmp     short loc_18002919F
0x180029123  mov     rdx, [rbx+10h]; tableid
0x180029127  mov     rcx, [rbx+8]; sesid
0x18002912b  test    r14d, r14d
0x18002912e  jz      short loc_180029147
0x180029130  xor     r9d, r9d; grbit
0x180029133  mov     r8d, 80000000h; cRow
0x180029139  call    cs:__imp_JetMove
0x180029140  nop     dword ptr [rax+rax+00h]
0x180029145  jmp     short loc_180029191
0x180029147  mov     r9d, [rsp+48h+cbData]; cbData
0x18002914c  mov     r8, r15; pvData
0x18002914f  mov     [rsp+48h+grbit], 1; grbit
0x180029157  call    cs:__imp_JetMakeKey
0x18002915e  nop     dword ptr [rax+rax+00h]
0x180029163  mov     ecx, eax
0x180029165  lea     rdx, aMPreparesearch_0; "M:PrepareSearch:MakeKey"
0x18002916c  mov     esi, eax
0x18002916e  call    DhcpMapJetError
0x180029173  mov     ebp, eax
0x180029175  test    eax, eax
0x180029177  jnz     short loc_180029115
0x180029179  mov     rdx, [rbx+10h]; tableid
0x18002917d  lea     r8d, [rax+10h]; grbit
0x180029181  mov     rcx, [rbx+8]; sesid
0x180029185  call    cs:__imp_JetSeek
0x18002918c  nop     dword ptr [rax+rax+00h]
0x180029191  lea     rdx, aMPreparesearch_1; "M:PrepareSearch:Move/Seek"
0x180029198  mov     ecx, eax
0x18002919a  call    DhcpMapJetError
0x18002919f  mov     rbx, [rsp+48h+arg_0]
0x1800291a4  mov     rbp, [rsp+48h+arg_8]
0x1800291a9  mov     rsi, [rsp+48h+arg_10]
0x1800291ae  add     rsp, 30h
0x1800291b2  pop     r15
0x1800291b4  pop     r14
0x1800291b6  pop     rdi
0x1800291b7  retn
```
