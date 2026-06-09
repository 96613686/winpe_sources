# QueryEngine::Compile(tagTableInfo const *,ushort const *,IQueryPlan * *,int *)

- ea: `0x18000fce0`
- end: `0x18000ffbc`
- name: `?Compile@QueryEngine@@UEAAJPEBUtagTableInfo@@PEBGPEAPEAUIQueryPlan@@PEAH@Z`
- size: `732`
- prototype: `__int64 __fastcall(QueryEngine *__hidden this, const struct tagTableInfo *, const unsigned __int16 *, struct IQueryPlan **, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009e8c`
- `0x18000f820`

## callees

- `0x180002e40`
- `0x180003d54`
- `0x18000fce0`
- `0x18000ffd0`
- `0x1800100a0`
- `0x180046010`

## import_xrefs

- `msvcrt!malloc` at `0x18000fd3b`
- `msvcrt!malloc` at `0x18000fe0e`
- `msvcrt!malloc` at `0x18000fd3b`
- `msvcrt!malloc` at `0x18000fe0e`
- `msvcrt!free` at `0x18000fe7a`
- `msvcrt!free` at `0x18000fe7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fd24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fdc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fdf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fd24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fdc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fdf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe83`

## string_xrefs

- `0x18000febb`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18000ff49`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18000ff7d`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18000ff9f`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
__int64 __fastcall QueryEngine::Compile(
        QueryEngine *this,
        const struct tagTableInfo *a2,
        const unsigned __int16 *a3,
        struct IQueryPlan **a4,
        int *a5)
{
  _QWORD *v8; // rbx
  void *v9; // rax
  int v10; // r15d
  _DWORD *v11; // rbx
  _QWORD *v12; // rdi
  void *v13; // rax
  __int64 v14; // rdi
  void **v15; // rbx
  void *v16; // rdi
  char *v18; // rax
  char *v19; // rax
  int v20; // [rsp+20h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+28h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-A0h]
  _QWORD v23[10]; // [rsp+40h] [rbp-98h] BYREF
  int v24; // [rsp+90h] [rbp-48h]
  int v25; // [rsp+94h] [rbp-44h]

  v20 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *a5 = 0;
  *a4 = 0;
  v8 = CoTaskMemAlloc(0x20u);
  if ( v8 )
  {
    v9 = malloc(0x400u);
    *v8 = v9;
    v8[1] = v9;
    v8[2] = 1024;
    v8[3] = 0;
    if ( !v9 )
      InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x22u, 0xC0001204, 0x10u);
    pv = v8;
  }
  else
  {
    pv = 0;
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x3Fu, 0xC0001204, 0x10u);
  }
  v23[0] = a3;
  v23[6] = &v20;
  v23[1] = a3;
  v23[7] = &si128.m128i_i64[1];
  v23[2] = a3;
  v23[3] = 0;
  v23[8] = a2;
  v23[9] = a5;
  v24 = -2147220989;
  v25 = 0;
  v10 = Parser::Compile((Parser *)v23);
  if ( v10 >= 0 )
  {
    v11 = CoTaskMemAlloc(0x28u);
    if ( v11 )
    {
      v11[2] = 1;
      *(_QWORD *)v11 = &QueryPlan::`vftable';
      *((_QWORD *)v11 + 3) = 1024;
      v12 = CoTaskMemAlloc(0x20u);
      if ( v12 )
      {
        v13 = malloc(0x400u);
        *v12 = v13;
        v12[1] = v13;
        v12[2] = 1024;
        v12[3] = 0;
        if ( !v13 )
          InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x22u, 0xC0001204, 0x10u);
        *((_QWORD *)v11 + 4) = v12;
      }
      else
      {
        *((_QWORD *)v11 + 4) = 0;
        InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x3Fu, 0xC0001204, 0x10u);
      }
      if ( si128.m128i_i64[0] )
      {
        v14 = (*(__int64 (__fastcall **)(__int64, const struct tagTableInfo *, _DWORD *))(*(_QWORD *)si128.m128i_i64[0]
                                                                                        + 40LL))(
                si128.m128i_i64[0],
                a2,
                v11 + 6);
      }
      else
      {
        v18 = StoragePool::alloc((StoragePool *)(v11 + 6), 24);
        v14 = (__int64)v18;
        if ( v18 )
        {
          *((_QWORD *)v18 + 1) = 0;
          *((_QWORD *)v18 + 2) = 0;
          *(_QWORD *)v18 = &NextRow::`vftable';
        }
        else
        {
          v14 = 0;
        }
        v19 = StoragePool::alloc((StoragePool *)(v11 + 6), 24);
        if ( v19 )
        {
          *((_QWORD *)v19 + 1) = v14;
          *((_QWORD *)v19 + 2) = v14;
          *(_QWORD *)v19 = &Accept::`vftable';
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      }
      *((_QWORD *)v11 + 2) = v14;
      *a4 = (struct IQueryPlan *)v11;
    }
    else
    {
      *a4 = 0;
      v10 = -2147024882;
    }
  }
  Parser::Tokenizer::FreeCurrentToken((Parser::Tokenizer *)v23);
  v15 = (void **)pv;
  if ( pv )
  {
    do
    {
      v16 = v15[3];
      free(*v15);
      CoTaskMemFree(v15);
      pv = v16;
      v15 = (void **)v16;
    }
    while ( v16 );
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000fce0  push    rbx
0x18000fce2  push    rbp
0x18000fce3  push    rsi
0x18000fce4  push    rdi
0x18000fce5  push    r12
0x18000fce7  push    r14
0x18000fce9  push    r15
0x18000fceb  sub     rsp, 0A0h
0x18000fcf2  movdqa  xmm0, cs:__xmm@00000000000004000000000000000000
0x18000fcfa  xor     r12d, r12d
0x18000fcfd  mov     rsi, [rsp+0D8h+arg_20]
0x18000fd05  mov     ecx, 20h ; ' '; cb
0x18000fd0a  mov     r14, r9
0x18000fd0d  mov     [rsp+0D8h+var_B8], r12d
0x18000fd12  mov     rdi, r8
0x18000fd15  mov     rbp, rdx
0x18000fd18  movdqu  [rsp+0D8h+var_B0], xmm0
0x18000fd1e  mov     [rsi], r12d
0x18000fd21  mov     [r9], r12
0x18000fd24  call    cs:__imp_CoTaskMemAlloc
0x18000fd2a  mov     rbx, rax
0x18000fd2d  test    rax, rax
0x18000fd30  jz      loc_18000FEAB
0x18000fd36  mov     ecx, 400h; Size
0x18000fd3b  call    cs:__imp_malloc
0x18000fd41  mov     [rbx], rax
0x18000fd44  mov     [rbx+8], rax
0x18000fd48  mov     qword ptr [rbx+10h], 400h
0x18000fd50  mov     [rbx+18h], r12
0x18000fd54  test    rax, rax
0x18000fd57  jz      loc_18000FF78
0x18000fd5d  mov     [rsp+0D8h+pv], rbx
0x18000fd62  lea     rax, [rsp+0D8h+var_B8]
0x18000fd67  mov     [rsp+0D8h+var_98], rdi
0x18000fd6c  mov     [rsp+0D8h+var_68], rax
0x18000fd71  lea     rcx, [rsp+0D8h+var_98]; this
0x18000fd76  lea     rax, [rsp+0D8h+var_B0+8]
0x18000fd7b  mov     [rsp+0D8h+var_90], rdi
0x18000fd80  mov     [rsp+0D8h+var_60], rax
0x18000fd85  mov     [rsp+0D8h+var_88], rdi
0x18000fd8a  mov     [rsp+0D8h+var_80], r12
0x18000fd8f  mov     [rsp+0D8h+var_58], rbp
0x18000fd97  mov     [rsp+0D8h+var_50], rsi
0x18000fd9f  mov     [rsp+0D8h+var_48], 80040203h
0x18000fdaa  mov     [rsp+0D8h+var_44], r12d
0x18000fdb2  call    ?Compile@Parser@@QEAAJXZ; Parser::Compile(void)
0x18000fdb7  mov     r15d, eax
0x18000fdba  test    eax, eax
0x18000fdbc  js      loc_18000FE5F
0x18000fdc2  mov     ecx, 28h ; '('; cb
0x18000fdc7  call    cs:__imp_CoTaskMemAlloc
0x18000fdcd  mov     rbx, rax
0x18000fdd0  test    rax, rax
0x18000fdd3  jz      loc_18000FF60
0x18000fdd9  lea     rax, ??_7QueryPlan@@6B@; const QueryPlan::`vftable'
0x18000fde0  mov     dword ptr [rbx+8], 1
0x18000fde7  mov     [rbx], rax
0x18000fdea  mov     ecx, 20h ; ' '; cb
0x18000fdef  mov     qword ptr [rbx+18h], 400h
0x18000fdf7  call    cs:__imp_CoTaskMemAlloc
0x18000fdfd  mov     rdi, rax
0x18000fe00  test    rax, rax
0x18000fe03  jz      loc_18000FF3A
0x18000fe09  mov     ecx, 400h; Size
0x18000fe0e  call    cs:__imp_malloc
0x18000fe14  mov     [rdi], rax
0x18000fe17  mov     [rdi+8], rax
0x18000fe1b  mov     qword ptr [rdi+10h], 400h
0x18000fe23  mov     [rdi+18h], r12
0x18000fe27  test    rax, rax
0x18000fe2a  jz      loc_18000FF9A
0x18000fe30  mov     [rbx+20h], rdi
0x18000fe34  mov     rcx, qword ptr [rsp+0D8h+var_B0]
0x18000fe39  test    rcx, rcx
0x18000fe3c  jz      loc_18000FED2
0x18000fe42  mov     rax, [rcx]
0x18000fe45  lea     r8, [rbx+18h]
0x18000fe49  mov     rdx, rbp
0x18000fe4c  mov     rax, [rax+28h]
0x18000fe50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe55  mov     rdi, rax
0x18000fe58  mov     [rbx+10h], rdi
0x18000fe5c  mov     [r14], rbx
0x18000fe5f  lea     rcx, [rsp+0D8h+var_98]; this
0x18000fe64  call    ?FreeCurrentToken@Tokenizer@Parser@@AEAAXXZ; Parser::Tokenizer::FreeCurrentToken(void)
0x18000fe69  mov     rbx, [rsp+0D8h+pv]
0x18000fe6e  test    rbx, rbx
0x18000fe71  jz      short loc_18000FE96
0x18000fe73  mov     rcx, [rbx]; Block
0x18000fe76  mov     rdi, [rbx+18h]
0x18000fe7a  call    cs:__imp_free
0x18000fe80  mov     rcx, rbx; pv
0x18000fe83  call    cs:__imp_CoTaskMemFree
0x18000fe89  mov     [rsp+0D8h+pv], rdi
0x18000fe8e  mov     rbx, rdi
0x18000fe91  test    rdi, rdi
0x18000fe94  jnz     short loc_18000FE73
0x18000fe96  mov     eax, r15d
0x18000fe99  add     rsp, 0A0h
0x18000fea0  pop     r15
0x18000fea2  pop     r14
0x18000fea4  pop     r12
0x18000fea6  pop     rdi
0x18000fea7  pop     rsi
0x18000fea8  pop     rbp
0x18000fea9  pop     rbx
0x18000feaa  retn
0x18000feab  mov     edx, 3Fh ; '?'; unsigned int
0x18000feb0  mov     [rsp+0D8h+pv], r12
0x18000feb5  mov     r9d, 10h; unsigned __int16
0x18000febb  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18000fec2  mov     r8d, 0C0001204h; unsigned int
0x18000fec8  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000fecd  jmp     loc_18000FD62
0x18000fed2  mov     edx, 18h; unsigned __int64
0x18000fed7  lea     rcx, [rbx+18h]; this
0x18000fedb  call    ?alloc@StoragePool@@QEAAPEAX_K@Z; StoragePool::alloc(unsigned __int64)
0x18000fee0  mov     rdi, rax
0x18000fee3  test    rax, rax
0x18000fee6  jz      loc_18000FF6E
0x18000feec  mov     [rax+8], r12
0x18000fef0  mov     [rax+10h], r12
0x18000fef4  lea     rax, ??_7NextRow@@6B@; const NextRow::`vftable'
0x18000fefb  mov     [rdi], rax
0x18000fefe  mov     edx, 18h; unsigned __int64
0x18000ff03  lea     rcx, [rbx+18h]; this
0x18000ff07  call    ?alloc@StoragePool@@QEAAPEAX_K@Z; StoragePool::alloc(unsigned __int64)
0x18000ff0c  mov     rdx, rax
0x18000ff0f  test    rax, rax
0x18000ff12  jz      short loc_18000FF73
0x18000ff14  mov     [rax+8], rdi
0x18000ff18  mov     [rax+10h], rdi
0x18000ff1c  lea     rax, ??_7Accept@@6B@; const Accept::`vftable'
0x18000ff23  mov     [rdx], rax
0x18000ff26  mov     rax, [rdi]
0x18000ff29  mov     rcx, rdi
0x18000ff2c  mov     rax, [rax+8]
0x18000ff30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff35  jmp     loc_18000FE58
0x18000ff3a  mov     edx, 3Fh ; '?'; unsigned int
0x18000ff3f  mov     [rbx+20h], r12
0x18000ff43  mov     r9d, 10h; unsigned __int16
0x18000ff49  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18000ff50  mov     r8d, 0C0001204h; unsigned int
0x18000ff56  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000ff5b  jmp     loc_18000FE34
0x18000ff60  mov     [r14], r12
0x18000ff63  mov     r15d, 8007000Eh
0x18000ff69  jmp     loc_18000FE5F
0x18000ff6e  mov     rdi, r12
0x18000ff71  jmp     short loc_18000FEFE
0x18000ff73  mov     rdx, r12
0x18000ff76  jmp     short loc_18000FF26
0x18000ff78  mov     edx, 22h ; '"'; unsigned int
0x18000ff7d  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18000ff84  mov     r9d, 10h; unsigned __int16
0x18000ff8a  mov     r8d, 0C0001204h; unsigned int
0x18000ff90  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000ff95  jmp     loc_18000FD5D
0x18000ff9a  mov     edx, 22h ; '"'; unsigned int
0x18000ff9f  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18000ffa6  mov     r9d, 10h; unsigned __int16
0x18000ffac  mov     r8d, 0C0001204h; unsigned int
0x18000ffb2  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000ffb7  jmp     loc_18000FE30
```
