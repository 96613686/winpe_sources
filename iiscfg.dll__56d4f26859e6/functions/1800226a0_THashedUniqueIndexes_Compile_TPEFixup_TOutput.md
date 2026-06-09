# THashedUniqueIndexes::Compile(TPEFixup &,TOutput &)

- ea: `0x1800226a0`
- end: `0x18002270d`
- name: `?Compile@THashedUniqueIndexes@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z`
- size: `109`
- prototype: `void __fastcall(THashedUniqueIndexes *__hidden this, struct TPEFixup *, struct TOutput *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015f34`

## callees

- `0x180022600`
- `0x1800226a0`
- `0x1800228d0`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall THashedUniqueIndexes::Compile(THashedUniqueIndexes *this, struct TPEFixup *a2, struct TOutput *a3)
{
  unsigned int v4; // ebx
  void **v5; // [rsp+20h] [rbp-28h] BYREF
  struct TPEFixup *v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+30h] [rbp-18h]

  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = a3;
  v6 = a2;
  v4 = 0;
  v7 = 0;
  v5 = &TTableMeta::`vftable';
  while ( v4 < (*(unsigned int (__fastcall **)(struct TPEFixup *))(*(_QWORD *)a2 + 320LL))(a2) )
  {
    THashedUniqueIndexes::FillInTheHashTableViaIndexMeta(this, (struct TTableMeta *)&v5);
    ++v4;
    TMetaTable<QueryMetaPublic>::Next(&v5);
    a2 = v6;
  }
}

```

## disassembly

```asm
0x1800226a0  mov     r11, rsp
0x1800226a3  mov     [r11+8], rbx
0x1800226a7  push    rdi
0x1800226a8  sub     rsp, 40h
0x1800226ac  mov     rdi, rcx
0x1800226af  mov     [rcx+8], rdx
0x1800226b3  mov     [rcx+10h], r8
0x1800226b7  mov     [r11-20h], rdx
0x1800226bb  xor     ebx, ebx
0x1800226bd  mov     [r11-18h], rbx
0x1800226c1  lea     rax, ??_7TTableMeta@@6B@; const TTableMeta::`vftable'
0x1800226c8  mov     [r11-28h], rax
0x1800226cc  mov     rax, [rdx]
0x1800226cf  mov     rcx, rdx
0x1800226d2  mov     rax, [rax+140h]
0x1800226d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226de  cmp     ebx, eax
0x1800226e0  jnb     short loc_180022702
0x1800226e2  lea     rdx, [rsp+48h+var_28]; struct TTableMeta *
0x1800226e7  mov     rcx, rdi; this
0x1800226ea  call    ?FillInTheHashTableViaIndexMeta@THashedUniqueIndexes@@AEAAXAEAVTTableMeta@@@Z; THashedUniqueIndexes::FillInTheHashTableViaIndexMeta(TTableMeta &)
0x1800226ef  inc     ebx
0x1800226f1  lea     rcx, [rsp+48h+var_28]
0x1800226f6  call    ?Next@?$TMetaTable@UQueryMetaPublic@@@@UEAA_NXZ; TMetaTable<QueryMetaPublic>::Next(void)
0x1800226fb  mov     rdx, [rsp+48h+var_20]
0x180022700  jmp     short loc_1800226CC
0x180022702  mov     rbx, [rsp+48h+arg_0]
0x180022707  add     rsp, 40h
0x18002270b  pop     rdi
0x18002270c  retn
```
