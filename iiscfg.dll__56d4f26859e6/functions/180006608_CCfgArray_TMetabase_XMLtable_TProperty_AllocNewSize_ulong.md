# CCfgArray<TMetabase_XMLtable::TProperty>::AllocNewSize(ulong)

- ea: `0x180006608`
- end: `0x1800066ab`
- name: `?AllocNewSize@?$CCfgArray@VTProperty@TMetabase_XMLtable@@@@AEAAJK@Z`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000c008`
- `0x18000e168`

## callees

- `0x180001ef0`
- `0x180006608`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006694`
- `ole32!CoTaskMemFree` at `0x180006694`
- `ole32!CoTaskMemAlloc` at `0x18000662c`
- `ole32!CoTaskMemAlloc` at `0x18000662c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCfgArray<TMetabase_XMLtable::TProperty>::AllocNewSize(__int64 a1, unsigned int a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  unsigned int i; // r8d
  __int64 v8; // rdx
  _DWORD *v9; // rcx

  v4 = CoTaskMemAlloc(saturated_mul(a2, 0x10u));
  v5 = v4;
  if ( v4 )
    `vector constructor iterator'(v4, 0x10u, a2, (void *(*)(void *))TMetabase_XMLtable::TProperty::TProperty);
  else
    v5 = 0;
  if ( !v5 )
    return 2147942414LL;
  for ( i = 0; i < *(_DWORD *)(a1 + 8); ++i )
  {
    v8 = 2LL * i;
    v9 = *(_DWORD **)a1;
    v5[v8 + 1] = *(_QWORD *)(*(_QWORD *)a1 + 16LL * i + 8);
    LODWORD(v5[v8]) = v9[4 * i];
  }
  CoTaskMemFree(*(LPVOID *)a1);
  *(_QWORD *)a1 = v5;
  *(_DWORD *)(a1 + 8) = a2;
  return 0;
}

```

## disassembly

```asm
0x180006608  push    rbx
0x18000660a  push    rbp
0x18000660b  push    rsi
0x18000660c  push    rdi
0x18000660d  sub     rsp, 28h
0x180006611  mov     ebp, edx
0x180006613  mov     rdi, rcx
0x180006616  mov     eax, 10h
0x18000661b  mul     rbp
0x18000661e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006625  cmovb   rax, rcx
0x180006629  mov     rcx, rax; cb
0x18000662c  call    cs:__imp_CoTaskMemAlloc
0x180006632  mov     rbx, rax
0x180006635  mov     [rsp+48h+arg_10], rax
0x18000663a  test    rax, rax
0x18000663d  jz      short loc_180006658
0x18000663f  lea     r9, ??0TProperty@TMetabase_XMLtable@@QEAA@XZ; void *(*)(void *)
0x180006646  mov     r8d, ebp; unsigned __int64
0x180006649  mov     edx, 10h; unsigned __int64
0x18000664e  mov     rcx, rax; void *
0x180006651  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180006656  jmp     short loc_18000665A
0x180006658  xor     ebx, ebx
0x18000665a  test    rbx, rbx
0x18000665d  jnz     short loc_180006666
0x18000665f  mov     eax, 8007000Eh
0x180006664  jmp     short loc_1800066A2
0x180006666  xor     r8d, r8d
0x180006669  cmp     [rdi+8], r8d
0x18000666d  jbe     short loc_180006691
0x18000666f  mov     edx, r8d
0x180006672  add     rdx, rdx
0x180006675  mov     rcx, [rdi]
0x180006678  mov     rax, [rcx+rdx*8+8]
0x18000667d  mov     [rbx+rdx*8+8], rax
0x180006682  mov     eax, [rcx+rdx*8]
0x180006685  mov     [rbx+rdx*8], eax
0x180006688  inc     r8d
0x18000668b  cmp     r8d, [rdi+8]
0x18000668f  jb      short loc_18000666F
0x180006691  mov     rcx, [rdi]; pv
0x180006694  call    cs:__imp_CoTaskMemFree
0x18000669a  mov     [rdi], rbx
0x18000669d  mov     [rdi+8], ebp
0x1800066a0  xor     eax, eax
0x1800066a2  add     rsp, 28h
0x1800066a6  pop     rdi
0x1800066a7  pop     rsi
0x1800066a8  pop     rbp
0x1800066a9  pop     rbx
0x1800066aa  retn
```
