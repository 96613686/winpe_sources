# ExprBooleanAND::applyBoolean_Comparison(ExprComparison &,Operator,StoragePool &)

- ea: `0x180019440`
- end: `0x180019628`
- name: `?applyBoolean_Comparison@ExprBooleanAND@@UEAAPEAVExprNode@@AEAVExprComparison@@W4Operator@@AEAVStoragePool@@@Z`
- size: `488`
- prototype: `ExprBooleanOR *__fastcall(__int64, struct ExprNode *, int, size_t *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001a80`
- `0x180002e40`
- `0x180003d54`
- `0x180019440`
- `0x180021db8`

## import_xrefs

- `msvcrt!malloc` at `0x180019535`
- `msvcrt!malloc` at `0x180019535`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019517`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019517`

## string_xrefs

- `0x18001958c`: `com\complus\src\events\queryengine\pool.cpp`
- `0x1800195ba`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
ExprBooleanOR *__fastcall ExprBooleanAND::applyBoolean_Comparison(__int64 a1, struct ExprNode *a2, int a3, size_t *a4)
{
  size_t v7; // rcx
  _QWORD *v8; // rsi
  unsigned __int64 v9; // rax
  struct ExprNode **v10; // r8
  _QWORD *v11; // rax
  int i; // r9d
  size_t v14; // r12
  _QWORD *v15; // r15
  size_t v16; // rbx
  void *v17; // rax
  unsigned __int64 v18; // rax
  unsigned int v19; // edx
  char *v20; // rax
  ExprBooleanOR *v21; // rsi

  if ( a3 != 4 )
  {
    v20 = StoragePool::alloc((StoragePool *)a4, 24);
    if ( v20 )
      v21 = ExprBooleanOR::ExprBooleanOR((ExprBooleanOR *)v20, a2, (struct StoragePool *)a4);
    else
      v21 = 0;
    ExprBooleanOR::InsertChild_AND(v21, (struct ExprBooleanAND *)a1, (struct StoragePool *)a4);
    return v21;
  }
  v7 = a4[1];
  v8 = 0;
  v9 = *(_QWORD *)(v7 + 16);
  if ( v9 >= 0x10 )
  {
    v10 = *(struct ExprNode ***)(v7 + 8);
    *(_QWORD *)(v7 + 16) = v9 - 16;
    *(_QWORD *)(v7 + 8) = v10 + 2;
    if ( v10 )
      goto LABEL_4;
  }
  v14 = *a4;
  if ( *a4 < 0x10 )
    v14 = 32;
  v15 = CoTaskMemAlloc(0x20u);
  if ( !v15 )
  {
    v15 = 0;
    v19 = 94;
LABEL_22:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v19, 0xC0001204, 0x10u);
    goto LABEL_18;
  }
  v16 = a4[1];
  v17 = malloc(v14);
  v15[3] = v16;
  *v15 = v17;
  v15[1] = v17;
  v15[2] = v14;
  if ( !v17 )
  {
    v19 = 34;
    goto LABEL_22;
  }
LABEL_18:
  *a4 = v14;
  a4[1] = (size_t)v15;
  v18 = v15[2];
  if ( v18 < 0x10 || (v10 = (struct ExprNode **)v15[1], v15[2] = v18 - 16, v15[1] = v10 + 2, !v10) )
  {
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
    v10 = 0;
    goto LABEL_5;
  }
LABEL_4:
  *v10 = a2;
  v10[1] = 0;
LABEL_5:
  v11 = *(_QWORD **)(a1 + 8);
  for ( i = *(_DWORD *)(*((_QWORD *)*v10 + 1) + 16LL); v11; v11 = (_QWORD *)v11[1] )
  {
    if ( *(_DWORD *)(*(_QWORD *)(*v11 + 8LL) + 16LL) > i )
      break;
    v8 = v11;
  }
  v10[1] = (struct ExprNode *)v11;
  if ( v8 )
    v8[1] = v10;
  else
    *(_QWORD *)(a1 + 8) = v10;
  if ( *((_DWORD *)*v10 + 6) == 1 && !i )
    *(_QWORD *)(a1 + 24) = *((_QWORD *)*v10 + 2);
  ++*(_DWORD *)(a1 + 16);
  return (ExprBooleanOR *)a1;
}

```

## disassembly

```asm
0x180019440  mov     [rsp+arg_18], rbp
0x180019445  push    rsi
0x180019446  push    rdi
0x180019447  push    r14
0x180019449  sub     rsp, 20h
0x18001944d  mov     r14, r9
0x180019450  mov     rbp, rdx
0x180019453  mov     rdi, rcx
0x180019456  cmp     r8d, 4
0x18001945a  jnz     loc_1800195EB
0x180019460  mov     rcx, [r9+8]
0x180019464  xor     esi, esi
0x180019466  mov     [rsp+38h+arg_10], r15
0x18001946b  mov     rax, [rcx+10h]
0x18001946f  cmp     rax, 10h
0x180019473  jb      loc_180019502
0x180019479  mov     r8, [rcx+8]
0x18001947d  add     rax, 0FFFFFFFFFFFFFFF0h
0x180019481  mov     [rcx+10h], rax
0x180019485  lea     rax, [r8+10h]
0x180019489  mov     [rcx+8], rax
0x18001948d  test    r8, r8
0x180019490  jz      short loc_180019502
0x180019492  mov     [r8], rbp
0x180019495  mov     [r8+8], rsi
0x180019499  mov     rax, [r8]
0x18001949c  mov     r15, [rsp+38h+arg_10]
0x1800194a1  mov     rcx, [rax+8]
0x1800194a5  mov     rax, [rdi+8]
0x1800194a9  mov     r9d, [rcx+10h]
0x1800194ad  test    rax, rax
0x1800194b0  jz      short loc_1800194CB
0x1800194b2  mov     rcx, [rax]
0x1800194b5  mov     rdx, [rcx+8]
0x1800194b9  cmp     [rdx+10h], r9d
0x1800194bd  jg      short loc_1800194CB
0x1800194bf  mov     rsi, rax
0x1800194c2  mov     rax, [rax+8]
0x1800194c6  test    rax, rax
0x1800194c9  jnz     short loc_1800194B2
0x1800194cb  mov     [r8+8], rax
0x1800194cf  test    rsi, rsi
0x1800194d2  jz      loc_1800195D5
0x1800194d8  mov     [rsi+8], r8
0x1800194dc  mov     rax, [r8]
0x1800194df  cmp     dword ptr [rax+18h], 1
0x1800194e3  jnz     short loc_1800194EE
0x1800194e5  test    r9d, r9d
0x1800194e8  jz      loc_1800195DE
0x1800194ee  inc     dword ptr [rdi+10h]
0x1800194f1  mov     rax, rdi
0x1800194f4  mov     rbp, [rsp+38h+arg_18]
0x1800194f9  add     rsp, 20h
0x1800194fd  pop     r14
0x1800194ff  pop     rdi
0x180019500  pop     rsi
0x180019501  retn
0x180019502  mov     [rsp+38h+arg_8], r12
0x180019507  mov     ecx, 20h ; ' '; cb
0x18001950c  mov     r12, [r9]
0x18001950f  cmp     r12, 10h
0x180019513  cmovb   r12, rcx
0x180019517  call    cs:__imp_CoTaskMemAlloc
0x18001951d  mov     r15, rax
0x180019520  test    rax, rax
0x180019523  jz      loc_1800195AC
0x180019529  mov     [rsp+38h+arg_0], rbx
0x18001952e  mov     rcx, r12; Size
0x180019531  mov     rbx, [r14+8]
0x180019535  call    cs:__imp_malloc
0x18001953b  mov     [r15+18h], rbx
0x18001953f  mov     rbx, [rsp+38h+arg_0]
0x180019544  mov     [r15], rax
0x180019547  mov     [r15+8], rax
0x18001954b  mov     [r15+10h], r12
0x18001954f  test    rax, rax
0x180019552  jz      short loc_1800195CE
0x180019554  mov     [r14], r12
0x180019557  mov     r12, [rsp+38h+arg_8]
0x18001955c  mov     [r14+8], r15
0x180019560  mov     rax, [r15+10h]
0x180019564  cmp     rax, 10h
0x180019568  jb      short loc_180019587
0x18001956a  mov     r8, [r15+8]
0x18001956e  add     rax, 0FFFFFFFFFFFFFFF0h
0x180019572  mov     [r15+10h], rax
0x180019576  lea     rax, [r8+10h]
0x18001957a  mov     [r15+8], rax
0x18001957e  test    r8, r8
0x180019581  jnz     loc_180019492
0x180019587  mov     edx, 64h ; 'd'; unsigned int
0x18001958c  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180019593  mov     r9d, 10h; unsigned __int16
0x180019599  mov     r8d, 0C0001204h; unsigned int
0x18001959f  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800195a4  mov     r8, rsi
0x1800195a7  jmp     loc_180019499
0x1800195ac  mov     r15, rsi
0x1800195af  mov     edx, 5Eh ; '^'; unsigned int
0x1800195b4  mov     r9d, 10h; unsigned __int16
0x1800195ba  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x1800195c1  mov     r8d, 0C0001204h; unsigned int
0x1800195c7  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800195cc  jmp     short loc_180019554
0x1800195ce  mov     edx, 22h ; '"'
0x1800195d3  jmp     short loc_1800195B4
0x1800195d5  mov     [rdi+8], r8
0x1800195d9  jmp     loc_1800194DC
0x1800195de  mov     rax, [rax+10h]
0x1800195e2  mov     [rdi+18h], rax
0x1800195e6  jmp     loc_1800194EE
0x1800195eb  mov     edx, 18h; unsigned __int64
0x1800195f0  mov     rcx, r14; this
0x1800195f3  call    ?alloc@StoragePool@@QEAAPEAX_K@Z; StoragePool::alloc(unsigned __int64)
0x1800195f8  test    rax, rax
0x1800195fb  jz      short loc_180019610
0x1800195fd  mov     r8, r14; struct StoragePool *
0x180019600  mov     rdx, rbp; struct ExprNode *
0x180019603  mov     rcx, rax; this
0x180019606  call    ??0ExprBooleanOR@@QEAA@AEAVExprNode@@AEAVStoragePool@@@Z; ExprBooleanOR::ExprBooleanOR(ExprNode &,StoragePool &)
0x18001960b  mov     rsi, rax
0x18001960e  jmp     short loc_180019612
0x180019610  xor     esi, esi
0x180019612  mov     r8, r14; struct StoragePool *
0x180019615  mov     rdx, rdi; struct ExprBooleanAND *
0x180019618  mov     rcx, rsi; this
0x18001961b  call    ?InsertChild_AND@ExprBooleanOR@@QEAAXAEAVExprBooleanAND@@AEAVStoragePool@@@Z; ExprBooleanOR::InsertChild_AND(ExprBooleanAND &,StoragePool &)
0x180019620  mov     rax, rsi
0x180019623  jmp     loc_1800194F4
```
