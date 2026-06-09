# TMetaInferrence::Compile(TPEFixup &,TOutput &)

- ea: `0x18001e000`
- end: `0x18001e06d`
- name: `?Compile@TMetaInferrence@@UEAAXAEAVTPEFixup@@AEAVTOutput@@@Z`
- size: `109`
- prototype: `void __fastcall(TMetaInferrence *__hidden this, struct TPEFixup *, struct TOutput *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180015f34`

## callees

- `0x18001e074`
- `0x18001e9d4`
- `0x18001ec74`
- `0x18001ee28`
- `0x18001f02c`
- `0x18001fa9c`
- `0x18001ff10`
- `0x180020a68`
- `0x180030010`

## pseudocode

```c
void __fastcall TMetaInferrence::Compile(TMetaInferrence *this, struct TPEFixup *a2, struct TOutput *a3)
{
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = a3;
  *((_DWORD *)this + 6) = (*(__int64 (__fastcall **)(struct TPEFixup *, _QWORD))(*(_QWORD *)a2 + 16LL))(a2, 0);
  TMetaInferrence::InferTagMeta(this);
  TMetaInferrence::InferColumnMeta(this);
  TMetaInferrence::InferQueryMeta(this);
  TMetaInferrence::InferIndexMeta(this);
  TMetaInferrence::InferRelationMeta(this);
  TMetaInferrence::InferServerWiringMeta(this);
  TMetaInferrence::InferTableMeta(this);
  TMetaInferrence::InferDatabaseMeta(this);
}

```

## disassembly

```asm
0x18001e000  push    rbx
0x18001e002  sub     rsp, 20h
0x18001e006  mov     [rcx+8], rdx
0x18001e00a  mov     r9, rdx
0x18001e00d  mov     [rcx+10h], r8
0x18001e011  mov     rbx, rcx
0x18001e014  mov     rax, [rdx]
0x18001e017  mov     rcx, r9
0x18001e01a  xor     edx, edx
0x18001e01c  mov     rax, [rax+10h]
0x18001e020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e025  mov     rcx, rbx; this
0x18001e028  mov     [rbx+18h], eax
0x18001e02b  call    ?InferTagMeta@TMetaInferrence@@AEAAXXZ; TMetaInferrence::InferTagMeta(void)
0x18001e030  mov     rcx, rbx; this
0x18001e033  call    ?InferColumnMeta@TMetaInferrence@@AEAAXXZ; TMetaInferrence::InferColumnMeta(void)
0x18001e038  mov     rcx, rbx; this
0x18001e03b  call    ?InferQueryMeta@TMetaInferrence@@AEAAXXZ; TMetaInferrence::InferQueryMeta(void)
0x18001e040  mov     rcx, rbx; this
0x18001e043  call    ?InferIndexMeta@TMetaInferrence@@AEAAXXZ; TMetaInferrence::InferIndexMeta(void)
0x18001e048  mov     rcx, rbx; this
0x18001e04b  call    ?InferRelationMeta@TMetaInferrence@@AEAAXXZ; TMetaInferrence::InferRelationMeta(void)
0x18001e050  mov     rcx, rbx; this
0x18001e053  call    ?InferServerWiringMeta@TMetaInferrence@@AEAAXXZ; TMetaInferrence::InferServerWiringMeta(void)
0x18001e058  mov     rcx, rbx; this
0x18001e05b  call    ?InferTableMeta@TMetaInferrence@@AEAAXXZ; TMetaInferrence::InferTableMeta(void)
0x18001e060  mov     rcx, rbx; this
0x18001e063  add     rsp, 20h
0x18001e067  pop     rbx
0x18001e068  jmp     ?InferDatabaseMeta@TMetaInferrence@@AEAAXXZ; TMetaInferrence::InferDatabaseMeta(void)
```
