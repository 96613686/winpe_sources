# ExprBooleanAND::clone(StoragePool &)

- ea: `0x180018d60`
- end: `0x180019140`
- name: `?clone@ExprBooleanAND@@UEAAPEAVExprNode@@AEAVStoragePool@@@Z`
- size: `992`
- prototype: `struct ExprNode *__fastcall(ExprBooleanAND *__hidden this, struct StoragePool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x180018d60`

## import_xrefs

- `msvcrt!malloc` at `0x180018ebe`
- `msvcrt!malloc` at `0x180018f59`
- `msvcrt!malloc` at `0x180018ff8`
- `msvcrt!malloc` at `0x180018ebe`
- `msvcrt!malloc` at `0x180018f59`
- `msvcrt!malloc` at `0x180018ff8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018f40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018fdf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018f40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018fdf`

## string_xrefs

- `0x180018f12`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180018fac`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18001904b`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019070`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019095`: `com\complus\src\events\queryengine\pool.cpp`
- `0x1800190ba`: `com\complus\src\events\queryengine\pool.cpp`
- `0x1800190df`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019101`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019123`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
struct ExprNode *__fastcall ExprBooleanAND::clone(ExprBooleanAND *this, struct StoragePool *a2)
{
  __int64 v2; // r8
  ExprBooleanAND *v4; // r13
  unsigned __int64 v5; // rax
  _QWORD *v6; // r15
  _QWORD *v7; // rsi
  _QWORD *v8; // rdi
  __int64 v9; // rdx
  unsigned __int64 v10; // rax
  _QWORD *v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // ecx
  struct ExprNode *result; // rax
  size_t v17; // r12
  _QWORD *v18; // rbp
  __int64 v19; // rbx
  void *v20; // rax
  unsigned __int64 v21; // rax
  size_t v22; // rsi
  _QWORD *v23; // rdi
  __int64 v24; // rbx
  void *v25; // rax
  unsigned __int64 v26; // rax
  size_t v27; // rsi
  _QWORD *v28; // rdi
  __int64 v29; // rbx
  void *v30; // rax
  unsigned __int64 v31; // rax

  v2 = *((_QWORD *)a2 + 1);
  v4 = this;
  v5 = *(_QWORD *)(v2 + 16);
  if ( v5 >= 0x10 )
  {
    v6 = *(_QWORD **)(v2 + 8);
    *(_QWORD *)(v2 + 16) = v5 - 16;
    *(_QWORD *)(v2 + 8) = v6 + 2;
    if ( v6 )
      goto LABEL_3;
  }
  v22 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 < 0x10u )
    v22 = 32;
  v23 = CoTaskMemAlloc(0x20u);
  if ( v23 )
  {
    v24 = *((_QWORD *)a2 + 1);
    v25 = malloc(v22);
    *v23 = v25;
    v23[1] = v25;
    v23[2] = v22;
    v23[3] = v24;
    if ( !v25 )
      InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x22u, 0xC0001204, 0x10u);
  }
  else
  {
    v23 = 0;
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x5Eu, 0xC0001204, 0x10u);
  }
  *(_QWORD *)a2 = v22;
  *((_QWORD *)a2 + 1) = v23;
  v26 = v23[2];
  if ( v26 >= 0x10 && (v6 = (_QWORD *)v23[1], v23[2] = v26 - 16, v23[1] = v6 + 2, v6) )
  {
LABEL_3:
    *v6 = **((_QWORD **)v4 + 1);
    v6[1] = 0;
  }
  else
  {
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
    v6 = 0;
  }
  v7 = v6;
  v8 = *(_QWORD **)(*((_QWORD *)v4 + 1) + 8LL);
  if ( v8 )
  {
    do
    {
      v9 = *((_QWORD *)a2 + 1);
      v10 = *(_QWORD *)(v9 + 16);
      if ( v10 >= 0x10 )
      {
        *(_QWORD *)(v9 + 16) = v10 - 16;
        v11 = *(_QWORD **)(v9 + 8);
        *(_QWORD *)(v9 + 8) = v11 + 2;
        if ( v11 )
          goto LABEL_7;
      }
      v17 = *(_QWORD *)a2;
      if ( *(_QWORD *)a2 < 0x10u )
        v17 = 32;
      v18 = CoTaskMemAlloc(0x20u);
      if ( v18 )
      {
        v19 = *((_QWORD *)a2 + 1);
        v20 = malloc(v17);
        *v18 = v20;
        v18[1] = v20;
        v18[2] = v17;
        v18[3] = v19;
        if ( !v20 )
          InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x22u, 0xC0001204, 0x10u);
      }
      else
      {
        v18 = 0;
        InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x5Eu, 0xC0001204, 0x10u);
      }
      *(_QWORD *)a2 = v17;
      *((_QWORD *)a2 + 1) = v18;
      v21 = v18[2];
      if ( v21 >= 0x10 && (v18[2] = v21 - 16, v11 = (_QWORD *)v18[1], v18[1] = v11 + 2, v11) )
      {
LABEL_7:
        *v11 = *v8;
        v11[1] = 0;
      }
      else
      {
        InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
        v11 = 0;
      }
      v7[1] = v11;
      v7 = v11;
      v8 = (_QWORD *)v8[1];
    }
    while ( v8 );
    v4 = this;
  }
  v12 = *((_QWORD *)a2 + 1);
  v13 = *(_QWORD *)(v12 + 16);
  if ( v13 >= 0x20 )
  {
    v14 = *(_QWORD *)(v12 + 8);
    *(_QWORD *)(v12 + 16) = v13 - 32;
    *(_QWORD *)(v12 + 8) = v14 + 32;
    if ( v14 )
      goto LABEL_12;
  }
  v27 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 < 0x20u )
    v27 = 64;
  v28 = CoTaskMemAlloc(0x20u);
  if ( v28 )
  {
    v29 = *((_QWORD *)a2 + 1);
    v30 = malloc(v27);
    *v28 = v30;
    v28[1] = v30;
    v28[2] = v27;
    v28[3] = v29;
    if ( !v30 )
      InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x22u, 0xC0001204, 0x10u);
  }
  else
  {
    v28 = 0;
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x5Eu, 0xC0001204, 0x10u);
  }
  *(_QWORD *)a2 = v27;
  *((_QWORD *)a2 + 1) = v28;
  v31 = v28[2];
  if ( v31 >= 0x20 && (v14 = v28[1], v28[2] = v31 - 32, v28[1] = v14 + 32, v14) )
  {
LABEL_12:
    v15 = *((_DWORD *)v4 + 4);
    *(_QWORD *)v14 = &ExprBooleanAND::`vftable';
    result = (struct ExprNode *)v14;
    *(_QWORD *)(v14 + 8) = v6;
    *(_DWORD *)(v14 + 16) = v15;
    *(_QWORD *)(v14 + 24) = 0;
  }
  else
  {
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180018d60  mov     [rsp+arg_10], rbx
0x180018d65  mov     [rsp+arg_18], rbp
0x180018d6a  mov     [rsp+arg_0], rcx
0x180018d6f  push    rsi
0x180018d70  push    rdi
0x180018d71  push    r13
0x180018d73  push    r14
0x180018d75  push    r15
0x180018d77  sub     rsp, 20h
0x180018d7b  mov     r8, [rdx+8]
0x180018d7f  xor     ebx, ebx
0x180018d81  mov     r14, rdx
0x180018d84  mov     r13, rcx
0x180018d87  mov     ebp, 20h ; ' '
0x180018d8c  mov     rax, [r8+10h]
0x180018d90  cmp     rax, 10h
0x180018d94  jb      loc_180018F32
0x180018d9a  mov     r15, [r8+8]
0x180018d9e  add     rax, 0FFFFFFFFFFFFFFF0h
0x180018da2  mov     [r8+10h], rax
0x180018da6  lea     rax, [r15+10h]
0x180018daa  mov     [r8+8], rax
0x180018dae  test    r15, r15
0x180018db1  jz      loc_180018F32
0x180018db7  mov     rax, [r13+8]
0x180018dbb  mov     rcx, [rax]
0x180018dbe  mov     [r15], rcx
0x180018dc1  mov     [r15+8], rbx
0x180018dc5  mov     rax, [r13+8]
0x180018dc9  mov     rsi, r15
0x180018dcc  mov     rdi, [rax+8]
0x180018dd0  test    rdi, rdi
0x180018dd3  jz      short loc_180018E35
0x180018dd5  mov     r13, rbp
0x180018dd8  mov     [rsp+48h+arg_8], r12
0x180018ddd  mov     rdx, [r14+8]
0x180018de1  mov     rax, [rdx+10h]
0x180018de5  cmp     rax, 10h
0x180018de9  jb      loc_180018E97
0x180018def  add     rax, 0FFFFFFFFFFFFFFF0h
0x180018df3  mov     [rdx+10h], rax
0x180018df7  mov     rax, [rdx+8]
0x180018dfb  lea     rcx, [rax+10h]
0x180018dff  mov     [rdx+8], rcx
0x180018e03  test    rax, rax
0x180018e06  jz      loc_180018E97
0x180018e0c  mov     rcx, [rdi]
0x180018e0f  mov     [rax], rcx
0x180018e12  mov     [rax+8], rbx
0x180018e16  mov     [rsi+8], rax
0x180018e1a  mov     rsi, rax
0x180018e1d  mov     rdi, [rdi+8]
0x180018e21  test    rdi, rdi
0x180018e24  jnz     short loc_180018DDD
0x180018e26  mov     r12, [rsp+48h+arg_8]
0x180018e2b  mov     ebp, 20h ; ' '
0x180018e30  mov     r13, [rsp+48h+arg_0]
0x180018e35  mov     rcx, [r14+8]
0x180018e39  mov     rax, [rcx+10h]
0x180018e3d  cmp     rax, 20h ; ' '
0x180018e41  jb      loc_180018FCC
0x180018e47  mov     rdx, [rcx+8]
0x180018e4b  add     rax, 0FFFFFFFFFFFFFFE0h
0x180018e4f  mov     [rcx+10h], rax
0x180018e53  lea     rax, [rdx+20h]
0x180018e57  mov     [rcx+8], rax
0x180018e5b  test    rdx, rdx
0x180018e5e  jz      loc_180018FCC
0x180018e64  mov     ecx, [r13+10h]
0x180018e68  lea     rax, ??_7ExprBooleanAND@@6B@; const ExprBooleanAND::`vftable'
0x180018e6f  mov     [rdx], rax
0x180018e72  mov     rax, rdx
0x180018e75  mov     [rdx+8], r15
0x180018e79  mov     [rdx+10h], ecx
0x180018e7c  mov     [rdx+18h], rbx
0x180018e80  mov     rbx, [rsp+48h+arg_10]
0x180018e85  mov     rbp, [rsp+48h+arg_18]
0x180018e8a  add     rsp, 20h
0x180018e8e  pop     r15
0x180018e90  pop     r14
0x180018e92  pop     r13
0x180018e94  pop     rdi
0x180018e95  pop     rsi
0x180018e96  retn
0x180018e97  mov     r12, [r14]
0x180018e9a  mov     rcx, r13; cb
0x180018e9d  cmp     r12, 10h
0x180018ea1  cmovb   r12, r13
0x180018ea5  call    cs:__imp_CoTaskMemAlloc
0x180018eab  mov     rbp, rax
0x180018eae  test    rax, rax
0x180018eb1  jz      loc_18001906B
0x180018eb7  mov     rbx, [r14+8]
0x180018ebb  mov     rcx, r12; Size
0x180018ebe  call    cs:__imp_malloc
0x180018ec4  mov     [rbp+0], rax
0x180018ec8  mov     [rbp+8], rax
0x180018ecc  mov     [rbp+10h], r12
0x180018ed0  mov     [rbp+18h], rbx
0x180018ed4  test    rax, rax
0x180018ed7  jz      loc_1800190FC
0x180018edd  xor     ebx, ebx
0x180018edf  mov     [r14], r12
0x180018ee2  mov     [r14+8], rbp
0x180018ee6  mov     rax, [rbp+10h]
0x180018eea  cmp     rax, 10h
0x180018eee  jb      short loc_180018F0D
0x180018ef0  add     rax, 0FFFFFFFFFFFFFFF0h
0x180018ef4  mov     [rbp+10h], rax
0x180018ef8  mov     rax, [rbp+8]
0x180018efc  lea     rcx, [rax+10h]
0x180018f00  mov     [rbp+8], rcx
0x180018f04  test    rax, rax
0x180018f07  jnz     loc_180018E0C
0x180018f0d  mov     edx, 64h ; 'd'; unsigned int
0x180018f12  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180018f19  mov     r9d, 10h; unsigned __int16
0x180018f1f  mov     r8d, 0C0001204h; unsigned int
0x180018f25  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180018f2a  mov     rax, rbx
0x180018f2d  jmp     loc_180018E16
0x180018f32  mov     rsi, [rdx]
0x180018f35  mov     rcx, rbp; cb
0x180018f38  cmp     rsi, 10h
0x180018f3c  cmovb   rsi, rbp
0x180018f40  call    cs:__imp_CoTaskMemAlloc
0x180018f46  mov     rdi, rax
0x180018f49  test    rax, rax
0x180018f4c  jz      loc_180019090
0x180018f52  mov     rbx, [r14+8]
0x180018f56  mov     rcx, rsi; Size
0x180018f59  call    cs:__imp_malloc
0x180018f5f  mov     [rdi], rax
0x180018f62  mov     [rdi+8], rax
0x180018f66  mov     [rdi+10h], rsi
0x180018f6a  mov     [rdi+18h], rbx
0x180018f6e  test    rax, rax
0x180018f71  jz      loc_1800190DA
0x180018f77  xor     ebx, ebx
0x180018f79  mov     [r14], rsi
0x180018f7c  mov     [r14+8], rdi
0x180018f80  mov     rax, [rdi+10h]
0x180018f84  cmp     rax, 10h
0x180018f88  jb      short loc_180018FA7
0x180018f8a  mov     r15, [rdi+8]
0x180018f8e  add     rax, 0FFFFFFFFFFFFFFF0h
0x180018f92  mov     [rdi+10h], rax
0x180018f96  lea     rax, [r15+10h]
0x180018f9a  mov     [rdi+8], rax
0x180018f9e  test    r15, r15
0x180018fa1  jnz     loc_180018DB7
0x180018fa7  mov     edx, 64h ; 'd'; unsigned int
0x180018fac  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180018fb3  mov     r9d, 10h; unsigned __int16
0x180018fb9  mov     r8d, 0C0001204h; unsigned int
0x180018fbf  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180018fc4  mov     r15, rbx
0x180018fc7  jmp     loc_180018DC5
0x180018fcc  mov     rsi, [r14]
0x180018fcf  mov     eax, 40h ; '@'
0x180018fd4  cmp     rsi, 20h ; ' '
0x180018fd8  mov     rcx, rbp; cb
0x180018fdb  cmovb   rsi, rax
0x180018fdf  call    cs:__imp_CoTaskMemAlloc
0x180018fe5  mov     rdi, rax
0x180018fe8  test    rax, rax
0x180018feb  jz      loc_1800190B5
0x180018ff1  mov     rbx, [r14+8]
0x180018ff5  mov     rcx, rsi; Size
0x180018ff8  call    cs:__imp_malloc
0x180018ffe  mov     [rdi], rax
0x180019001  mov     [rdi+8], rax
0x180019005  mov     [rdi+10h], rsi
0x180019009  mov     [rdi+18h], rbx
0x18001900d  test    rax, rax
0x180019010  jz      loc_18001911E
0x180019016  xor     ebx, ebx
0x180019018  mov     [r14], rsi
0x18001901b  mov     [r14+8], rdi
0x18001901f  mov     rax, [rdi+10h]
0x180019023  cmp     rax, 20h ; ' '
0x180019027  jb      short loc_180019046
0x180019029  mov     rdx, [rdi+8]
0x18001902d  add     rax, 0FFFFFFFFFFFFFFE0h
0x180019031  mov     [rdi+10h], rax
0x180019035  lea     rcx, [rdx+20h]
0x180019039  mov     [rdi+8], rcx
0x18001903d  test    rdx, rdx
0x180019040  jnz     loc_180018E64
0x180019046  mov     edx, 64h ; 'd'; unsigned int
0x18001904b  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180019052  mov     r9d, 10h; unsigned __int16
0x180019058  mov     r8d, 0C0001204h; unsigned int
0x18001905e  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180019063  mov     rax, rbx
0x180019066  jmp     loc_180018E80
0x18001906b  mov     edx, 5Eh ; '^'; unsigned int
0x180019070  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180019077  mov     r9d, 10h; unsigned __int16
0x18001907d  mov     r8d, 0C0001204h; unsigned int
0x180019083  mov     rbp, rbx
0x180019086  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001908b  jmp     loc_180018EDF
0x180019090  mov     edx, 5Eh ; '^'; unsigned int
0x180019095  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001909c  mov     r9d, 10h; unsigned __int16
0x1800190a2  mov     r8d, 0C0001204h; unsigned int
0x1800190a8  mov     rdi, rbx
0x1800190ab  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800190b0  jmp     loc_180018F79
0x1800190b5  mov     edx, 5Eh ; '^'; unsigned int
0x1800190ba  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x1800190c1  mov     r9d, 10h; unsigned __int16
0x1800190c7  mov     r8d, 0C0001204h; unsigned int
0x1800190cd  mov     rdi, rbx
0x1800190d0  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800190d5  jmp     loc_180019018
0x1800190da  mov     edx, 22h ; '"'; unsigned int
0x1800190df  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x1800190e6  mov     r9d, 10h; unsigned __int16
0x1800190ec  mov     r8d, 0C0001204h; unsigned int
0x1800190f2  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800190f7  jmp     loc_180018F77
0x1800190fc  mov     edx, 22h ; '"'; unsigned int
0x180019101  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180019108  mov     r9d, 10h; unsigned __int16
0x18001910e  mov     r8d, 0C0001204h; unsigned int
0x180019114  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180019119  jmp     loc_180018EDD
0x18001911e  mov     edx, 22h ; '"'; unsigned int
0x180019123  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001912a  mov     r9d, 10h; unsigned __int16
0x180019130  mov     r8d, 0C0001204h; unsigned int
0x180019136  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001913b  jmp     loc_180019016
```
