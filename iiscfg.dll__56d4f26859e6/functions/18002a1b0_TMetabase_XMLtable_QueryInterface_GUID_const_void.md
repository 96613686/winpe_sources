# TMetabase_XMLtable::QueryInterface(_GUID const &,void * *)

- ea: `0x18002a1b0`
- end: `0x18002a2ba`
- name: `?QueryInterface@TMetabase_XMLtable@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `266`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000dfe0`
- `0x18000dff0`

## callees

- `0x18002a1b0`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall TMetabase_XMLtable::QueryInterface(TMetabase_XMLtable *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rdx
  __int64 v10; // rax

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISimpleTableAdvanced.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISimpleTableAdvanced.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISimpleTableAdvanced.Data4;
  if ( !v4 )
    goto LABEL_23;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISimpleTableRead2.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISimpleTableRead2.Data1 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISimpleTableRead2.Data4;
  if ( !v5 )
    goto LABEL_22;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISimpleTableWrite2.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISimpleTableWrite2.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISimpleTableWrite2.Data4;
  if ( !v6 )
  {
LABEL_22:
    *a3 = this;
    goto LABEL_25;
  }
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISimpleTableController.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISimpleTableController.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISimpleTableController.Data4;
  if ( !v7 )
  {
LABEL_23:
    v9 = (unsigned __int64)this + 8;
    goto LABEL_24;
  }
  v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_ISimpleTableInterceptor.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_ISimpleTableInterceptor.Data1 )
    v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_ISimpleTableInterceptor.Data4;
  if ( v8 )
  {
    v10 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v10 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v10 )
      goto LABEL_25;
    goto LABEL_22;
  }
  v9 = (unsigned __int64)this + 16;
LABEL_24:
  *a3 = (void *)(v9 & -(__int64)(this != 0));
LABEL_25:
  if ( !*a3 )
    return 2147500034LL;
  (*(void (__fastcall **)(TMetabase_XMLtable *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x18002a1b0  sub     rsp, 28h
0x18002a1b4  mov     r9, rcx
0x18002a1b7  test    r8, r8
0x18002a1ba  jnz     short loc_18002A1C6
0x18002a1bc  mov     eax, 80070057h
0x18002a1c1  jmp     loc_18002A2B5
0x18002a1c6  mov     qword ptr [r8], 0
0x18002a1cd  mov     rax, [rdx]
0x18002a1d0  sub     rax, qword ptr cs:IID_ISimpleTableAdvanced.Data1
0x18002a1d7  jnz     short loc_18002A1E4
0x18002a1d9  mov     rax, [rdx+8]
0x18002a1dd  sub     rax, qword ptr cs:IID_ISimpleTableAdvanced.Data4
0x18002a1e4  test    rax, rax
0x18002a1e7  jz      loc_18002A284
0x18002a1ed  mov     rax, [rdx]
0x18002a1f0  sub     rax, qword ptr cs:IID_ISimpleTableRead2.Data1
0x18002a1f7  jnz     short loc_18002A204
0x18002a1f9  mov     rax, [rdx+8]
0x18002a1fd  sub     rax, qword ptr cs:IID_ISimpleTableRead2.Data4
0x18002a204  test    rax, rax
0x18002a207  jz      short loc_18002A27F
0x18002a209  mov     rax, [rdx]
0x18002a20c  sub     rax, qword ptr cs:IID_ISimpleTableWrite2.Data1
0x18002a213  jnz     short loc_18002A220
0x18002a215  mov     rax, [rdx+8]
0x18002a219  sub     rax, qword ptr cs:IID_ISimpleTableWrite2.Data4
0x18002a220  test    rax, rax
0x18002a223  jz      short loc_18002A27F
0x18002a225  mov     rax, [rdx]
0x18002a228  sub     rax, qword ptr cs:IID_ISimpleTableController.Data1
0x18002a22f  jnz     short loc_18002A23C
0x18002a231  mov     rax, [rdx+8]
0x18002a235  sub     rax, qword ptr cs:IID_ISimpleTableController.Data4
0x18002a23c  test    rax, rax
0x18002a23f  jz      short loc_18002A284
0x18002a241  mov     rax, [rdx]
0x18002a244  sub     rax, qword ptr cs:IID_ISimpleTableInterceptor.Data1
0x18002a24b  jnz     short loc_18002A258
0x18002a24d  mov     rax, [rdx+8]
0x18002a251  sub     rax, qword ptr cs:IID_ISimpleTableInterceptor.Data4
0x18002a258  test    rax, rax
0x18002a25b  jnz     short loc_18002A263
0x18002a25d  lea     rdx, [rcx+10h]
0x18002a261  jmp     short loc_18002A288
0x18002a263  mov     rax, [rdx]
0x18002a266  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18002a26d  jnz     short loc_18002A27A
0x18002a26f  mov     rax, [rdx+8]
0x18002a273  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18002a27a  test    rax, rax
0x18002a27d  jnz     short loc_18002A297
0x18002a27f  mov     [r8], r9
0x18002a282  jmp     short loc_18002A297
0x18002a284  lea     rdx, [rcx+8]
0x18002a288  mov     rax, r9
0x18002a28b  neg     rax
0x18002a28e  sbb     rcx, rcx
0x18002a291  and     rcx, rdx
0x18002a294  mov     [r8], rcx
0x18002a297  cmp     qword ptr [r8], 0
0x18002a29b  jz      short loc_18002A2B0
0x18002a29d  mov     rax, [r9]
0x18002a2a0  mov     rcx, r9
0x18002a2a3  mov     rax, [rax+8]
0x18002a2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2ac  xor     eax, eax
0x18002a2ae  jmp     short loc_18002A2B5
0x18002a2b0  mov     eax, 80004002h
0x18002a2b5  add     rsp, 28h
0x18002a2b9  retn
```
