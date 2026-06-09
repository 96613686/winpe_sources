# THashedPKIndexes::Compile(TPEFixup &,TOutput &)

- ea: `0x180020e10`
- end: `0x180020e6f`
- name: `?Compile@THashedPKIndexes@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z`
- size: `95`
- prototype: `void __fastcall(THashedPKIndexes *__hidden this, struct TPEFixup *, struct TOutput *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180015f34`

## callees

- `0x180021084`
- `0x180021368`
- `0x180021588`
- `0x1800218f4`
- `0x180021bb4`
- `0x180021dd4`
- `0x180030010`

## pseudocode

```c
void __fastcall THashedPKIndexes::Compile(THashedPKIndexes *this, struct TPEFixup *a2, struct TOutput *a3)
{
  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 5) = a3;
  THashedPKIndexes::FillInTheHashTableForColumnMeta(this);
  THashedPKIndexes::FillInTheHashTableForDatabase(this);
  THashedPKIndexes::FillInTheHashTableForIndexMeta(this);
  THashedPKIndexes::FillInTheHashTableForQueryMeta(this);
  THashedPKIndexes::FillInTheHashTableForTableMeta(this);
  THashedPKIndexes::FillInTheHashTableForTagMeta(this);
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 72LL))(
    *((_QWORD *)this + 4),
    *((_QWORD *)this + 2),
    *((_DWORD *)this + 7) >> 3);
}

```

## disassembly

```asm
0x180020e10  push    rbx
0x180020e12  sub     rsp, 20h
0x180020e16  mov     rbx, rcx
0x180020e19  mov     [rcx+20h], rdx
0x180020e1d  mov     [rcx+28h], r8
0x180020e21  call    ?FillInTheHashTableForColumnMeta@THashedPKIndexes@@AEAAXXZ; THashedPKIndexes::FillInTheHashTableForColumnMeta(void)
0x180020e26  mov     rcx, rbx; this
0x180020e29  call    ?FillInTheHashTableForDatabase@THashedPKIndexes@@AEAAXXZ; THashedPKIndexes::FillInTheHashTableForDatabase(void)
0x180020e2e  mov     rcx, rbx; this
0x180020e31  call    ?FillInTheHashTableForIndexMeta@THashedPKIndexes@@AEAAXXZ; THashedPKIndexes::FillInTheHashTableForIndexMeta(void)
0x180020e36  mov     rcx, rbx; this
0x180020e39  call    ?FillInTheHashTableForQueryMeta@THashedPKIndexes@@AEAAXXZ; THashedPKIndexes::FillInTheHashTableForQueryMeta(void)
0x180020e3e  mov     rcx, rbx; this
0x180020e41  call    ?FillInTheHashTableForTableMeta@THashedPKIndexes@@AEAAXXZ; THashedPKIndexes::FillInTheHashTableForTableMeta(void)
0x180020e46  mov     rcx, rbx; this
0x180020e49  call    ?FillInTheHashTableForTagMeta@THashedPKIndexes@@AEAAXXZ; THashedPKIndexes::FillInTheHashTableForTagMeta(void)
0x180020e4e  mov     rcx, [rbx+20h]
0x180020e52  mov     r8d, [rbx+1Ch]
0x180020e56  mov     rdx, [rbx+10h]
0x180020e5a  shr     r8d, 3
0x180020e5e  mov     rax, [rcx]
0x180020e61  mov     rax, [rax+48h]
0x180020e65  add     rsp, 20h
0x180020e69  pop     rbx
0x180020e6a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
