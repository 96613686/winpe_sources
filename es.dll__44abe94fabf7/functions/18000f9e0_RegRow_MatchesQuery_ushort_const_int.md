# RegRow::MatchesQuery(ushort const *,int *)

- ea: `0x18000f9e0`
- end: `0x18000fc1c`
- name: `?MatchesQuery@RegRow@@UEAAJPEBGPEAH@Z`
- size: `572`
- prototype: `__int64 __fastcall(RegRow *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002e40`
- `0x18000f9e0`
- `0x18000fc24`
- `0x18000ffd0`
- `0x1800100a0`
- `0x1800100d8`
- `0x180046010`

## import_xrefs

- `msvcrt!free` at `0x18000fb07`
- `msvcrt!free` at `0x18000fb07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fb10`

## pseudocode

```c
__int64 __fastcall RegRow::MatchesQuery(RegRow *this, const unsigned __int16 *a2, int *a3)
{
  __int64 v3; // r9
  _DWORD *v7; // rsi
  int v8; // r14d
  __int64 v9; // rdi
  void **v10; // rbx
  void *v11; // rdi
  char *v13; // rax
  char *v14; // rax
  _DWORD v15[2]; // [rsp+28h] [rbp-69h] BYREF
  __int64 v16; // [rsp+30h] [rbp-61h]
  int v17; // [rsp+38h] [rbp-59h] BYREF
  __int64 v18; // [rsp+40h] [rbp-51h]
  char v19[8]; // [rsp+48h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-41h]
  _QWORD v21[10]; // [rsp+58h] [rbp-39h] BYREF
  int v22; // [rsp+A8h] [rbp+17h]
  int v23; // [rsp+ACh] [rbp+1Bh]
  _BYTE v24[48]; // [rsp+B8h] [rbp+27h] BYREF

  v3 = *((_QWORD *)this + 7);
  if ( !v3 )
    return 2147807233LL;
  v7 = 0;
  v15[0] = *(_DWORD *)(v3 + 544);
  v15[1] = 0;
  v16 = *(_QWORD *)(v3 + 552);
  *a3 = 0;
  v17 = 0;
  v18 = 0;
  StoragePool::StoragePool((StoragePool *)v19);
  v21[0] = a2;
  v21[6] = &v17;
  v21[1] = a2;
  v21[7] = v19;
  v21[8] = v15;
  v21[2] = a2;
  v21[3] = 0;
  v21[9] = a3;
  v22 = -2147220989;
  v23 = 0;
  v8 = Parser::Compile((Parser *)v21);
  if ( v8 >= 0 )
  {
    v7 = CoTaskMemAlloc(0x28u);
    if ( v7 )
    {
      v7[2] = 1;
      *(_QWORD *)v7 = &QueryPlan::`vftable';
      StoragePool::StoragePool((StoragePool *)(v7 + 6));
      if ( v18 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _DWORD *))(*(_QWORD *)v18 + 40LL))(v18, v15, v7 + 6);
      }
      else
      {
        v13 = StoragePool::alloc((StoragePool *)(v7 + 6), 24);
        v9 = (__int64)v13;
        if ( v13 )
        {
          *((_QWORD *)v13 + 1) = 0;
          *((_QWORD *)v13 + 2) = 0;
          *(_QWORD *)v13 = &NextRow::`vftable';
        }
        else
        {
          v9 = 0;
        }
        v14 = StoragePool::alloc((StoragePool *)(v7 + 6), 24);
        if ( v14 )
        {
          *((_QWORD *)v14 + 1) = v9;
          *((_QWORD *)v14 + 2) = v9;
          *(_QWORD *)v14 = &Accept::`vftable';
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      }
      *((_QWORD *)v7 + 2) = v9;
    }
    else
    {
      v7 = 0;
      v8 = -2147024882;
    }
  }
  Parser::Tokenizer::FreeCurrentToken((Parser::Tokenizer *)v21);
  v10 = (void **)pv;
  if ( pv )
  {
    do
    {
      v11 = v10[3];
      free(*v10);
      CoTaskMemFree(v10);
      pv = v11;
      v10 = (void **)v11;
    }
    while ( v11 );
  }
  if ( v8 >= 0 )
  {
    RowQueryInterpreter::RowQueryInterpreter((RowQueryInterpreter *)v24, this);
    v8 = (*(__int64 (__fastcall **)(_DWORD *, _BYTE *))(*(_QWORD *)v7 + 24LL))(v7, v24);
    if ( v8 >= 0 )
      v8 = v24[17] == 0;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f9e0  mov     rax, rsp
0x18000f9e3  mov     [rax+20h], rbx
0x18000f9e7  push    rbp
0x18000f9e8  push    rdi
0x18000f9e9  push    r15
0x18000f9eb  lea     rbp, [rax-5Fh]
0x18000f9ef  sub     rsp, 0D0h
0x18000f9f6  mov     r9, [rcx+38h]
0x18000f9fa  mov     rdi, r8
0x18000f9fd  mov     rbx, rdx
0x18000fa00  mov     r15, rcx
0x18000fa03  test    r9, r9
0x18000fa06  jz      loc_18000FB99
0x18000fa0c  mov     [rax+8], rsi
0x18000fa10  lea     rcx, [rbp+57h+var_A0]; this
0x18000fa14  mov     [rax+10h], r12
0x18000fa18  xor     r12d, r12d
0x18000fa1b  mov     [rax+18h], r14
0x18000fa1f  mov     esi, r12d
0x18000fa22  mov     eax, [r9+220h]
0x18000fa29  mov     [rbp+57h+var_C0], eax
0x18000fa2c  xor     eax, eax
0x18000fa2e  mov     [rbp+57h+var_BC], eax
0x18000fa31  mov     rax, [r9+228h]
0x18000fa38  mov     [rbp+57h+var_B8], rax
0x18000fa3c  mov     [r8], r12d
0x18000fa3f  mov     [rbp+57h+var_B0], r12d
0x18000fa43  mov     [rbp+57h+var_A8], r12
0x18000fa47  call    ??0StoragePool@@QEAA@_K@Z; StoragePool::StoragePool(unsigned __int64)
0x18000fa4c  lea     rax, [rbp+57h+var_B0]
0x18000fa50  mov     [rbp+57h+var_90], rbx
0x18000fa54  mov     [rbp+57h+var_60], rax
0x18000fa58  lea     rcx, [rbp+57h+var_90]; this
0x18000fa5c  lea     rax, [rbp+57h+var_A0]
0x18000fa60  mov     [rbp+57h+var_88], rbx
0x18000fa64  mov     [rbp+57h+var_58], rax
0x18000fa68  lea     rax, [rbp+57h+var_C0]
0x18000fa6c  mov     [rbp+57h+var_50], rax
0x18000fa70  mov     [rbp+57h+var_80], rbx
0x18000fa74  mov     [rbp+57h+var_78], r12
0x18000fa78  mov     [rbp+57h+var_48], rdi
0x18000fa7c  mov     [rbp+57h+var_40], 80040203h
0x18000fa83  mov     [rbp+57h+var_3C], r12d
0x18000fa87  call    ?Compile@Parser@@QEAAJXZ; Parser::Compile(void)
0x18000fa8c  mov     r14d, eax
0x18000fa8f  test    eax, eax
0x18000fa91  js      short loc_18000FAEC
0x18000fa93  mov     ecx, 28h ; '('; cb
0x18000fa98  call    cs:__imp_CoTaskMemAlloc
0x18000fa9e  mov     rsi, rax
0x18000faa1  test    rax, rax
0x18000faa4  jz      loc_18000FC04
0x18000faaa  lea     rax, ??_7QueryPlan@@6B@; const QueryPlan::`vftable'
0x18000fab1  mov     dword ptr [rsi+8], 1
0x18000fab8  lea     rcx, [rsi+18h]; this
0x18000fabc  mov     [rsi], rax
0x18000fabf  call    ??0StoragePool@@QEAA@_K@Z; StoragePool::StoragePool(unsigned __int64)
0x18000fac4  mov     rcx, [rbp+57h+var_A8]
0x18000fac8  test    rcx, rcx
0x18000facb  jz      loc_18000FBA0
0x18000fad1  mov     rax, [rcx]
0x18000fad4  lea     r8, [rsi+18h]
0x18000fad8  lea     rdx, [rbp+57h+var_C0]
0x18000fadc  mov     rax, [rax+28h]
0x18000fae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fae5  mov     rdi, rax
0x18000fae8  mov     [rsi+10h], rdi
0x18000faec  lea     rcx, [rbp+57h+var_90]; this
0x18000faf0  call    ?FreeCurrentToken@Tokenizer@Parser@@AEAAXXZ; Parser::Tokenizer::FreeCurrentToken(void)
0x18000faf5  mov     rbx, [rbp+57h+pv]
0x18000faf9  test    rbx, rbx
0x18000fafc  jz      short loc_18000FB22
0x18000fafe  xchg    ax, ax
0x18000fb00  mov     rcx, [rbx]; Block
0x18000fb03  mov     rdi, [rbx+18h]
0x18000fb07  call    cs:__imp_free
0x18000fb0d  mov     rcx, rbx; pv
0x18000fb10  call    cs:__imp_CoTaskMemFree
0x18000fb16  mov     [rbp+57h+pv], rdi
0x18000fb1a  mov     rbx, rdi
0x18000fb1d  test    rdi, rdi
0x18000fb20  jnz     short loc_18000FB00
0x18000fb22  test    r14d, r14d
0x18000fb25  js      short loc_18000FB6A
0x18000fb27  mov     rdx, r15; struct RegRow *
0x18000fb2a  lea     rcx, [rbp+57h+var_30]; this
0x18000fb2e  call    ??0RowQueryInterpreter@@QEAA@AEAVRegRow@@@Z; RowQueryInterpreter::RowQueryInterpreter(RegRow &)
0x18000fb33  mov     rcx, [rsi]
0x18000fb36  lea     rdx, [rbp+57h+var_30]
0x18000fb3a  mov     rax, [rcx+18h]
0x18000fb3e  mov     rcx, rsi
0x18000fb41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb46  mov     r14d, eax
0x18000fb49  test    eax, eax
0x18000fb4b  js      short loc_18000FB5B
0x18000fb4d  cmp     [rbp+57h+var_1F], r12b
0x18000fb51  mov     r14d, 1
0x18000fb57  cmovnz  r14d, r12d
0x18000fb5b  mov     rax, [rsi]
0x18000fb5e  mov     rcx, rsi
0x18000fb61  mov     rax, [rax+10h]
0x18000fb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb6a  mov     r12, [rsp+0E0h+arg_8]
0x18000fb72  mov     eax, r14d
0x18000fb75  mov     r14, [rsp+0E0h+arg_10]
0x18000fb7d  mov     rsi, [rsp+0E0h+arg_0]
0x18000fb85  mov     rbx, [rsp+0E0h+arg_18]
0x18000fb8d  add     rsp, 0D0h
0x18000fb94  pop     r15
0x18000fb96  pop     rdi
0x18000fb97  pop     rbp
0x18000fb98  retn
0x18000fb99  mov     eax, 8004F001h
0x18000fb9e  jmp     short loc_18000FB85
0x18000fba0  mov     edx, 18h; unsigned __int64
0x18000fba5  lea     rcx, [rsi+18h]; this
0x18000fba9  call    ?alloc@StoragePool@@QEAAPEAX_K@Z; StoragePool::alloc(unsigned __int64)
0x18000fbae  mov     rdi, rax
0x18000fbb1  test    rax, rax
0x18000fbb4  jz      short loc_18000FC12
0x18000fbb6  mov     [rax+8], r12
0x18000fbba  mov     [rax+10h], r12
0x18000fbbe  lea     rax, ??_7NextRow@@6B@; const NextRow::`vftable'
0x18000fbc5  mov     [rdi], rax
0x18000fbc8  mov     edx, 18h; unsigned __int64
0x18000fbcd  lea     rcx, [rsi+18h]; this
0x18000fbd1  call    ?alloc@StoragePool@@QEAAPEAX_K@Z; StoragePool::alloc(unsigned __int64)
0x18000fbd6  mov     rdx, rax
0x18000fbd9  test    rax, rax
0x18000fbdc  jz      short loc_18000FC17
0x18000fbde  mov     [rax+8], rdi
0x18000fbe2  mov     [rax+10h], rdi
0x18000fbe6  lea     rax, ??_7Accept@@6B@; const Accept::`vftable'
0x18000fbed  mov     [rdx], rax
0x18000fbf0  mov     rax, [rdi]
0x18000fbf3  mov     rcx, rdi
0x18000fbf6  mov     rax, [rax+8]
0x18000fbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbff  jmp     loc_18000FAE8
0x18000fc04  mov     rsi, r12
0x18000fc07  mov     r14d, 8007000Eh
0x18000fc0d  jmp     loc_18000FAEC
0x18000fc12  mov     rdi, r12
0x18000fc15  jmp     short loc_18000FBC8
0x18000fc17  mov     rdx, r12
0x18000fc1a  jmp     short loc_18000FBF0
```
