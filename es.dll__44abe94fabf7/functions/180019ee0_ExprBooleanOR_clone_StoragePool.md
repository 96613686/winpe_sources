# ExprBooleanOR::clone(StoragePool &)

- ea: `0x180019ee0`
- end: `0x18001a29c`
- name: `?clone@ExprBooleanOR@@UEAAPEAVExprNode@@AEAVStoragePool@@@Z`
- size: `956`
- prototype: `struct ExprNode *__fastcall(ExprBooleanOR *__hidden this, struct StoragePool *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x180019ee0`
- `0x180046010`

## import_xrefs

- `msvcrt!malloc` at `0x18001a069`
- `msvcrt!malloc` at `0x18001a103`
- `msvcrt!malloc` at `0x18001a1a7`
- `msvcrt!malloc` at `0x18001a069`
- `msvcrt!malloc` at `0x18001a103`
- `msvcrt!malloc` at `0x18001a1a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a0ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a18e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a050`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a0ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a18e`

## string_xrefs

- `0x18001a0ba`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18001a159`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18001a1f8`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18001a226`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18001a24b`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18001a270`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
struct ExprNode *__fastcall ExprBooleanOR::clone(ExprBooleanOR *this, struct StoragePool *a2)
{
  __int64 v3; // rdx
  unsigned __int64 v5; // rax
  __int64 v6; // r14
  __int64 v7; // rbp
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  unsigned __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  __int64 v14; // rdx
  struct ExprNode *result; // rax
  size_t v16; // r12
  _QWORD *v17; // r15
  __int64 v18; // rbx
  void *v19; // rax
  unsigned __int64 v20; // rax
  size_t v21; // rbp
  _QWORD *v22; // r15
  __int64 v23; // rbx
  void *v24; // rax
  unsigned __int64 v25; // rax
  size_t v26; // rbp
  _QWORD *v27; // rdi
  __int64 v28; // rbx
  void *v29; // rax
  unsigned __int64 v30; // rax
  unsigned int v31; // edx
  unsigned int v32; // edx
  unsigned int v33; // edx
  __int64 v34; // [rsp+50h] [rbp+8h]

  v3 = *((_QWORD *)a2 + 1);
  v5 = *(_QWORD *)(v3 + 16);
  if ( v5 >= 0x18 )
  {
    v6 = *(_QWORD *)(v3 + 8);
    *(_QWORD *)(v3 + 16) = v5 - 24;
    v34 = v6;
    *(_QWORD *)(v3 + 8) = v6 + 24;
    if ( v6 )
      goto LABEL_3;
  }
  v21 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 < 0x18u )
    v21 = 48;
  v22 = CoTaskMemAlloc(0x20u);
  if ( !v22 )
  {
    v22 = 0;
    v32 = 94;
LABEL_37:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v32, 0xC0001204, 0x10u);
    goto LABEL_24;
  }
  v23 = *((_QWORD *)a2 + 1);
  v24 = malloc(v21);
  *v22 = v24;
  v22[1] = v24;
  v22[2] = v21;
  v22[3] = v23;
  if ( !v24 )
  {
    v32 = 34;
    goto LABEL_37;
  }
LABEL_24:
  *(_QWORD *)a2 = v21;
  *((_QWORD *)a2 + 1) = v22;
  v25 = v22[2];
  if ( v25 >= 0x18 )
  {
    v6 = v22[1];
    v22[2] = v25 - 24;
    v34 = v6;
    v22[1] = v6 + 24;
    if ( v6 )
    {
LABEL_3:
      *(_QWORD *)v6 = (*(__int64 (__fastcall **)(_QWORD, struct StoragePool *))(***((_QWORD ***)this + 1) + 32LL))(
                        **((_QWORD **)this + 1),
                        a2);
      *(_DWORD *)(v6 + 8) = 1;
      *(_QWORD *)(v6 + 16) = 0;
      goto LABEL_4;
    }
  }
  InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
  v6 = 0;
  v34 = 0;
LABEL_4:
  v7 = v6;
  v8 = *(_QWORD **)(*((_QWORD *)this + 1) + 16LL);
  if ( v8 )
  {
    while ( 1 )
    {
      v9 = *((_QWORD *)a2 + 1);
      v10 = *(_QWORD *)(v9 + 16);
      if ( v10 >= 0x18 )
      {
        v11 = *(_QWORD *)(v9 + 8);
        *(_QWORD *)(v9 + 16) = v10 - 24;
        *(_QWORD *)(v9 + 8) = v11 + 24;
        if ( v11 )
          goto LABEL_7;
      }
      v16 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 < 0x18u )
        v16 = 48;
      v17 = CoTaskMemAlloc(0x20u);
      if ( !v17 )
        break;
      v18 = *((_QWORD *)a2 + 1);
      v19 = malloc(v16);
      *v17 = v19;
      v17[1] = v19;
      v17[2] = v16;
      v17[3] = v18;
      if ( !v19 )
      {
        v31 = 34;
        goto LABEL_35;
      }
LABEL_17:
      *(_QWORD *)a2 = v16;
      *((_QWORD *)a2 + 1) = v17;
      v20 = v17[2];
      if ( v20 < 0x18 || (v11 = v17[1], v17[2] = v20 - 24, v17[1] = v11 + 24, !v11) )
      {
        InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
        v11 = 0;
        goto LABEL_8;
      }
LABEL_7:
      *(_QWORD *)v11 = (*(__int64 (__fastcall **)(_QWORD, struct StoragePool *))(*(_QWORD *)*v8 + 32LL))(*v8, a2);
      *(_DWORD *)(v11 + 8) = 1;
      *(_QWORD *)(v11 + 16) = 0;
LABEL_8:
      *(_QWORD *)(v7 + 16) = v11;
      v7 = v11;
      v8 = (_QWORD *)v8[2];
      if ( !v8 )
      {
        v6 = v34;
        goto LABEL_10;
      }
    }
    v17 = 0;
    v31 = 94;
LABEL_35:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v31, 0xC0001204, 0x10u);
    goto LABEL_17;
  }
LABEL_10:
  v12 = *((_QWORD *)a2 + 1);
  v13 = *(_QWORD *)(v12 + 16);
  if ( v13 >= 0x18 )
  {
    v14 = *(_QWORD *)(v12 + 8);
    *(_QWORD *)(v12 + 16) = v13 - 24;
    *(_QWORD *)(v12 + 8) = v14 + 24;
    if ( v14 )
      goto LABEL_12;
  }
  v26 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 < 0x18u )
    v26 = 48;
  v27 = CoTaskMemAlloc(0x20u);
  if ( !v27 )
  {
    v27 = 0;
    v33 = 94;
LABEL_39:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v33, 0xC0001204, 0x10u);
    goto LABEL_31;
  }
  v28 = *((_QWORD *)a2 + 1);
  v29 = malloc(v26);
  *v27 = v29;
  v27[1] = v29;
  v27[2] = v26;
  v27[3] = v28;
  if ( !v29 )
  {
    v33 = 34;
    goto LABEL_39;
  }
LABEL_31:
  *(_QWORD *)a2 = v26;
  *((_QWORD *)a2 + 1) = v27;
  v30 = v27[2];
  if ( v30 >= 0x18 )
  {
    v14 = v27[1];
    v27[2] = v30 - 24;
    v27[1] = v14 + 24;
    if ( v14 )
    {
LABEL_12:
      *(_QWORD *)(v14 + 8) = v6;
      *(_QWORD *)v14 = &ExprBooleanOR::`vftable';
      result = (struct ExprNode *)v14;
      *(_BYTE *)(v14 + 16) = 0;
      return result;
    }
  }
  InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
  return 0;
}

```

## disassembly

```asm
0x180019ee0  mov     [rsp+arg_10], rbx
0x180019ee5  mov     [rsp+arg_18], rbp
0x180019eea  push    rsi
0x180019eeb  push    rdi
0x180019eec  push    r12
0x180019eee  push    r13
0x180019ef0  push    r14
0x180019ef2  sub     rsp, 20h
0x180019ef6  mov     rsi, rdx
0x180019ef9  mov     [rsp+48h+arg_8], r15
0x180019efe  mov     rdx, [rdx+8]
0x180019f02  xor     r13d, r13d
0x180019f05  mov     rdi, rcx
0x180019f08  mov     r12d, 30h ; '0'
0x180019f0e  mov     rax, [rdx+10h]
0x180019f12  cmp     rax, 18h
0x180019f16  jb      loc_18001A0DA
0x180019f1c  mov     r14, [rdx+8]
0x180019f20  add     rax, 0FFFFFFFFFFFFFFE8h
0x180019f24  mov     [rdx+10h], rax
0x180019f28  mov     [rsp+48h+arg_0], r14
0x180019f2d  lea     rax, [r14+18h]
0x180019f31  mov     [rdx+8], rax
0x180019f35  test    r14, r14
0x180019f38  jz      loc_18001A0DA
0x180019f3e  mov     rax, [rdi+8]
0x180019f42  mov     rdx, rsi
0x180019f45  mov     rcx, [rax]
0x180019f48  mov     rax, [rcx]
0x180019f4b  mov     rax, [rax+20h]
0x180019f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f54  mov     [r14], rax
0x180019f57  mov     dword ptr [r14+8], 1
0x180019f5f  mov     [r14+10h], r13
0x180019f63  mov     rax, [rdi+8]
0x180019f67  mov     rbp, r14
0x180019f6a  mov     rdi, [rax+10h]
0x180019f6e  test    rdi, rdi
0x180019f71  jz      short loc_180019FE0
0x180019f73  mov     r14, r12
0x180019f76  mov     rcx, [rsi+8]
0x180019f7a  mov     rax, [rcx+10h]
0x180019f7e  cmp     rax, 18h
0x180019f82  jb      loc_18001A040
0x180019f88  mov     rbx, [rcx+8]
0x180019f8c  add     rax, 0FFFFFFFFFFFFFFE8h
0x180019f90  mov     [rcx+10h], rax
0x180019f94  lea     rax, [rbx+18h]
0x180019f98  mov     [rcx+8], rax
0x180019f9c  test    rbx, rbx
0x180019f9f  jz      loc_18001A040
0x180019fa5  mov     rcx, [rdi]
0x180019fa8  mov     rdx, rsi
0x180019fab  mov     rax, [rcx]
0x180019fae  mov     rax, [rax+20h]
0x180019fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fb7  mov     [rbx], rax
0x180019fba  mov     dword ptr [rbx+8], 1
0x180019fc1  mov     [rbx+10h], r13
0x180019fc5  mov     [rbp+10h], rbx
0x180019fc9  mov     rbp, rbx
0x180019fcc  mov     rdi, [rdi+10h]
0x180019fd0  test    rdi, rdi
0x180019fd3  jnz     short loc_180019F76
0x180019fd5  mov     r14, [rsp+48h+arg_0]
0x180019fda  mov     r12d, 30h ; '0'
0x180019fe0  mov     rcx, [rsi+8]
0x180019fe4  mov     r15, [rsp+48h+arg_8]
0x180019fe9  mov     rax, [rcx+10h]
0x180019fed  cmp     rax, 18h
0x180019ff1  jb      loc_18001A17E
0x180019ff7  mov     rdx, [rcx+8]
0x180019ffb  add     rax, 0FFFFFFFFFFFFFFE8h
0x180019fff  mov     [rcx+10h], rax
0x18001a003  lea     rax, [rdx+18h]
0x18001a007  mov     [rcx+8], rax
0x18001a00b  test    rdx, rdx
0x18001a00e  jz      loc_18001A17E
0x18001a014  lea     rax, ??_7ExprBooleanOR@@6B@; const ExprBooleanOR::`vftable'
0x18001a01b  mov     [rdx+8], r14
0x18001a01f  mov     [rdx], rax
0x18001a022  mov     rax, rdx
0x18001a025  mov     [rdx+10h], r13b
0x18001a029  mov     rbx, [rsp+48h+arg_10]
0x18001a02e  mov     rbp, [rsp+48h+arg_18]
0x18001a033  add     rsp, 20h
0x18001a037  pop     r14
0x18001a039  pop     r13
0x18001a03b  pop     r12
0x18001a03d  pop     rdi
0x18001a03e  pop     rsi
0x18001a03f  retn
0x18001a040  mov     r12, [rsi]
0x18001a043  mov     ecx, 20h ; ' '; cb
0x18001a048  cmp     r12, 18h
0x18001a04c  cmovb   r12, r14
0x18001a050  call    cs:__imp_CoTaskMemAlloc
0x18001a056  mov     r15, rax
0x18001a059  test    rax, rax
0x18001a05c  jz      loc_18001A218
0x18001a062  mov     rbx, [rsi+8]
0x18001a066  mov     rcx, r12; Size
0x18001a069  call    cs:__imp_malloc
0x18001a06f  mov     [r15], rax
0x18001a072  mov     [r15+8], rax
0x18001a076  mov     [r15+10h], r12
0x18001a07a  mov     [r15+18h], rbx
0x18001a07e  test    rax, rax
0x18001a081  jz      loc_18001A28E
0x18001a087  mov     [rsi], r12
0x18001a08a  mov     [rsi+8], r15
0x18001a08e  mov     rax, [r15+10h]
0x18001a092  cmp     rax, 18h
0x18001a096  jb      short loc_18001A0B5
0x18001a098  mov     rbx, [r15+8]
0x18001a09c  add     rax, 0FFFFFFFFFFFFFFE8h
0x18001a0a0  mov     [r15+10h], rax
0x18001a0a4  lea     rax, [rbx+18h]
0x18001a0a8  mov     [r15+8], rax
0x18001a0ac  test    rbx, rbx
0x18001a0af  jnz     loc_180019FA5
0x18001a0b5  mov     edx, 64h ; 'd'; unsigned int
0x18001a0ba  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001a0c1  mov     r9d, 10h; unsigned __int16
0x18001a0c7  mov     r8d, 0C0001204h; unsigned int
0x18001a0cd  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001a0d2  mov     rbx, r13
0x18001a0d5  jmp     loc_180019FC5
0x18001a0da  mov     rbp, [rsi]
0x18001a0dd  mov     ecx, 20h ; ' '; cb
0x18001a0e2  cmp     rbp, 18h
0x18001a0e6  cmovb   rbp, r12
0x18001a0ea  call    cs:__imp_CoTaskMemAlloc
0x18001a0f0  mov     r15, rax
0x18001a0f3  test    rax, rax
0x18001a0f6  jz      loc_18001A23D
0x18001a0fc  mov     rbx, [rsi+8]
0x18001a100  mov     rcx, rbp; Size
0x18001a103  call    cs:__imp_malloc
0x18001a109  mov     [r15], rax
0x18001a10c  mov     [r15+8], rax
0x18001a110  mov     [r15+10h], rbp
0x18001a114  mov     [r15+18h], rbx
0x18001a118  test    rax, rax
0x18001a11b  jz      loc_18001A287
0x18001a121  mov     [rsi], rbp
0x18001a124  mov     [rsi+8], r15
0x18001a128  mov     rax, [r15+10h]
0x18001a12c  cmp     rax, 18h
0x18001a130  jb      short loc_18001A154
0x18001a132  mov     r14, [r15+8]
0x18001a136  add     rax, 0FFFFFFFFFFFFFFE8h
0x18001a13a  mov     [r15+10h], rax
0x18001a13e  mov     [rsp+48h+arg_0], r14
0x18001a143  lea     rax, [r14+18h]
0x18001a147  mov     [r15+8], rax
0x18001a14b  test    r14, r14
0x18001a14e  jnz     loc_180019F3E
0x18001a154  mov     edx, 64h ; 'd'; unsigned int
0x18001a159  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001a160  mov     r9d, 10h; unsigned __int16
0x18001a166  mov     r8d, 0C0001204h; unsigned int
0x18001a16c  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001a171  mov     r14, r13
0x18001a174  mov     [rsp+48h+arg_0], r13
0x18001a179  jmp     loc_180019F63
0x18001a17e  mov     rbp, [rsi]
0x18001a181  mov     ecx, 20h ; ' '; cb
0x18001a186  cmp     rbp, 18h
0x18001a18a  cmovb   rbp, r12
0x18001a18e  call    cs:__imp_CoTaskMemAlloc
0x18001a194  mov     rdi, rax
0x18001a197  test    rax, rax
0x18001a19a  jz      loc_18001A262
0x18001a1a0  mov     rbx, [rsi+8]
0x18001a1a4  mov     rcx, rbp; Size
0x18001a1a7  call    cs:__imp_malloc
0x18001a1ad  mov     [rdi], rax
0x18001a1b0  mov     [rdi+8], rax
0x18001a1b4  mov     [rdi+10h], rbp
0x18001a1b8  mov     [rdi+18h], rbx
0x18001a1bc  test    rax, rax
0x18001a1bf  jz      loc_18001A295
0x18001a1c5  mov     [rsi], rbp
0x18001a1c8  mov     [rsi+8], rdi
0x18001a1cc  mov     rax, [rdi+10h]
0x18001a1d0  cmp     rax, 18h
0x18001a1d4  jb      short loc_18001A1F3
0x18001a1d6  mov     rdx, [rdi+8]
0x18001a1da  add     rax, 0FFFFFFFFFFFFFFE8h
0x18001a1de  mov     [rdi+10h], rax
0x18001a1e2  lea     rcx, [rdx+18h]
0x18001a1e6  mov     [rdi+8], rcx
0x18001a1ea  test    rdx, rdx
0x18001a1ed  jnz     loc_18001A014
0x18001a1f3  mov     edx, 64h ; 'd'; unsigned int
0x18001a1f8  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001a1ff  mov     r9d, 10h; unsigned __int16
0x18001a205  mov     r8d, 0C0001204h; unsigned int
0x18001a20b  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001a210  mov     rax, r13
0x18001a213  jmp     loc_18001A029
0x18001a218  mov     r15, r13
0x18001a21b  mov     edx, 5Eh ; '^'; unsigned int
0x18001a220  mov     r9d, 10h; unsigned __int16
0x18001a226  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001a22d  mov     r8d, 0C0001204h; unsigned int
0x18001a233  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001a238  jmp     loc_18001A087
0x18001a23d  mov     r15, r13
0x18001a240  mov     edx, 5Eh ; '^'; unsigned int
0x18001a245  mov     r9d, 10h; unsigned __int16
0x18001a24b  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001a252  mov     r8d, 0C0001204h; unsigned int
0x18001a258  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001a25d  jmp     loc_18001A121
0x18001a262  mov     rdi, r13
0x18001a265  mov     edx, 5Eh ; '^'; unsigned int
0x18001a26a  mov     r9d, 10h; unsigned __int16
0x18001a270  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001a277  mov     r8d, 0C0001204h; unsigned int
0x18001a27d  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001a282  jmp     loc_18001A1C5
0x18001a287  mov     edx, 22h ; '"'
0x18001a28c  jmp     short loc_18001A245
0x18001a28e  mov     edx, 22h ; '"'
0x18001a293  jmp     short loc_18001A220
0x18001a295  mov     edx, 22h ; '"'
0x18001a29a  jmp     short loc_18001A26A
```
