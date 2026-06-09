# ExprBooleanOR::InsertChild_Comparison(ExprComparison &,StoragePool &)

- ea: `0x18001a5f0`
- end: `0x18001a7bd`
- name: `?InsertChild_Comparison@ExprBooleanOR@@QEAAXAEAVExprComparison@@AEAVStoragePool@@@Z`
- size: `461`
- prototype: `void __fastcall(ExprBooleanOR *__hidden this, struct ExprComparison *, struct StoragePool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a560`

## callees

- `0x180003d54`
- `0x18001a5f0`
- `0x180046010`

## import_xrefs

- `msvcrt!malloc` at `0x18001a6ee`
- `msvcrt!malloc` at `0x18001a6ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a6d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a6d9`

## string_xrefs

- `0x18001a740`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18001a76d`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
void __fastcall ExprBooleanOR::InsertChild_Comparison(
        ExprBooleanOR *this,
        struct ExprComparison *a2,
        struct StoragePool *a3)
{
  __int64 v5; // rcx
  int v7; // ebp
  unsigned __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r15
  _QWORD *v12; // r14
  _QWORD *i; // rsi
  size_t v14; // r12
  _QWORD *v15; // r15
  __int64 v16; // rbx
  void *v17; // rax
  unsigned __int64 v18; // rax
  unsigned int v19; // edx

  v5 = *((_QWORD *)a3 + 1);
  v7 = 1;
  v8 = *(_QWORD *)(v5 + 16);
  if ( v8 >= 0x18 )
  {
    v9 = *(_QWORD *)(v5 + 8);
    *(_QWORD *)(v5 + 16) = v8 - 24;
    *(_QWORD *)(v5 + 8) = v9 + 24;
    if ( v9 )
      goto LABEL_3;
  }
  v14 = *(_QWORD *)a3;
  if ( *(_QWORD *)a3 < 0x18u )
    v14 = 48;
  v15 = CoTaskMemAlloc(0x20u);
  if ( !v15 )
  {
    v15 = 0;
    v19 = 94;
LABEL_23:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v19, 0xC0001204, 0x10u);
    goto LABEL_19;
  }
  v16 = *((_QWORD *)a3 + 1);
  v17 = malloc(v14);
  *v15 = v17;
  v15[1] = v17;
  v15[2] = v14;
  v15[3] = v16;
  if ( !v17 )
  {
    v19 = 34;
    goto LABEL_23;
  }
LABEL_19:
  *(_QWORD *)a3 = v14;
  *((_QWORD *)a3 + 1) = v15;
  v18 = v15[2];
  if ( v18 < 0x18 || (v9 = v15[1], v15[2] = v18 - 24, v15[1] = v9 + 24, !v9) )
  {
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
    v9 = 0;
    goto LABEL_4;
  }
LABEL_3:
  *(_QWORD *)v9 = a2;
  *(_DWORD *)(v9 + 8) = 1;
  *(_QWORD *)(v9 + 16) = 0;
LABEL_4:
  if ( *((_DWORD *)a2 + 6) != 1 || *(_DWORD *)(*((_QWORD *)a2 + 1) + 16LL) )
  {
    *(_QWORD *)(v9 + 16) = *((_QWORD *)this + 1);
    v10 = *((_QWORD *)this + 1);
    if ( v10 )
      v7 = *(_DWORD *)(v10 + 8) + 1;
    *(_DWORD *)(v9 + 8) = v7;
    *((_BYTE *)this + 16) = 0;
LABEL_9:
    *((_QWORD *)this + 1) = v9;
    return;
  }
  v11 = *((_QWORD *)a2 + 2);
  v12 = 0;
  for ( i = (_QWORD *)*((_QWORD *)this + 1); i; i = (_QWORD *)i[2] )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*i + 64LL))(*i, v11) )
      break;
    v12 = i;
  }
  *(_QWORD *)(v9 + 16) = i;
  if ( i )
    v7 = *((_DWORD *)i + 2) + 1;
  *(_DWORD *)(v9 + 8) = v7;
  if ( !v12 )
    goto LABEL_9;
  v12[2] = v9;
}

```

## disassembly

```asm
0x18001a5f0  push    rbx
0x18001a5f2  push    rbp
0x18001a5f3  push    rsi
0x18001a5f4  push    rdi
0x18001a5f5  push    r14
0x18001a5f7  push    r15
0x18001a5f9  sub     rsp, 28h
0x18001a5fd  mov     rdi, rcx
0x18001a600  mov     r14, r8
0x18001a603  mov     rcx, [r8+8]
0x18001a607  mov     rsi, rdx
0x18001a60a  mov     ebp, 1
0x18001a60f  mov     rax, [rcx+10h]
0x18001a613  cmp     rax, 18h
0x18001a617  jb      loc_18001A6BF
0x18001a61d  mov     rbx, [rcx+8]
0x18001a621  add     rax, 0FFFFFFFFFFFFFFE8h
0x18001a625  mov     [rcx+10h], rax
0x18001a629  lea     rax, [rbx+18h]
0x18001a62d  mov     [rcx+8], rax
0x18001a631  test    rbx, rbx
0x18001a634  jz      loc_18001A6BF
0x18001a63a  mov     [rbx], rsi
0x18001a63d  mov     [rbx+8], ebp
0x18001a640  mov     qword ptr [rbx+10h], 0
0x18001a648  cmp     [rsi+18h], ebp
0x18001a64b  jnz     short loc_18001A657
0x18001a64d  mov     rax, [rsi+8]
0x18001a651  cmp     dword ptr [rax+10h], 0
0x18001a655  jz      short loc_18001A685
0x18001a657  mov     rax, [rdi+8]
0x18001a65b  mov     [rbx+10h], rax
0x18001a65f  mov     rax, [rdi+8]
0x18001a663  test    rax, rax
0x18001a666  jz      short loc_18001A66D
0x18001a668  mov     ebp, [rax+8]
0x18001a66b  inc     ebp
0x18001a66d  mov     [rbx+8], ebp
0x18001a670  mov     byte ptr [rdi+10h], 0
0x18001a674  mov     [rdi+8], rbx
0x18001a678  add     rsp, 28h
0x18001a67c  pop     r15
0x18001a67e  pop     r14
0x18001a680  pop     rdi
0x18001a681  pop     rsi
0x18001a682  pop     rbp
0x18001a683  pop     rbx
0x18001a684  retn
0x18001a685  mov     r15, [rsi+10h]
0x18001a689  xor     r14d, r14d
0x18001a68c  mov     rsi, [rdi+8]
0x18001a690  test    rsi, rsi
0x18001a693  jnz     loc_18001A788
0x18001a699  mov     [rbx+10h], rsi
0x18001a69d  test    rsi, rsi
0x18001a6a0  jnz     loc_18001A7B3
0x18001a6a6  mov     [rbx+8], ebp
0x18001a6a9  test    r14, r14
0x18001a6ac  jz      short loc_18001A674
0x18001a6ae  mov     [r14+10h], rbx
0x18001a6b2  add     rsp, 28h
0x18001a6b6  pop     r15
0x18001a6b8  pop     r14
0x18001a6ba  pop     rdi
0x18001a6bb  pop     rsi
0x18001a6bc  pop     rbp
0x18001a6bd  pop     rbx
0x18001a6be  retn
0x18001a6bf  mov     [rsp+58h+arg_0], r12
0x18001a6c4  mov     eax, 30h ; '0'
0x18001a6c9  mov     r12, [r8]
0x18001a6cc  mov     ecx, 20h ; ' '; cb
0x18001a6d1  cmp     r12, 18h
0x18001a6d5  cmovb   r12, rax
0x18001a6d9  call    cs:__imp_CoTaskMemAlloc
0x18001a6df  mov     r15, rax
0x18001a6e2  test    rax, rax
0x18001a6e5  jz      short loc_18001A75F
0x18001a6e7  mov     rbx, [r14+8]
0x18001a6eb  mov     rcx, r12; Size
0x18001a6ee  call    cs:__imp_malloc
0x18001a6f4  mov     [r15], rax
0x18001a6f7  mov     [r15+8], rax
0x18001a6fb  mov     [r15+10h], r12
0x18001a6ff  mov     [r15+18h], rbx
0x18001a703  test    rax, rax
0x18001a706  jz      short loc_18001A781
0x18001a708  mov     [r14], r12
0x18001a70b  mov     r12, [rsp+58h+arg_0]
0x18001a710  mov     [r14+8], r15
0x18001a714  mov     rax, [r15+10h]
0x18001a718  cmp     rax, 18h
0x18001a71c  jb      short loc_18001A73B
0x18001a71e  mov     rbx, [r15+8]
0x18001a722  add     rax, 0FFFFFFFFFFFFFFE8h
0x18001a726  mov     [r15+10h], rax
0x18001a72a  lea     rax, [rbx+18h]
0x18001a72e  mov     [r15+8], rax
0x18001a732  test    rbx, rbx
0x18001a735  jnz     loc_18001A63A
0x18001a73b  mov     edx, 64h ; 'd'; unsigned int
0x18001a740  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001a747  mov     r9d, 10h; unsigned __int16
0x18001a74d  mov     r8d, 0C0001204h; unsigned int
0x18001a753  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001a758  xor     ebx, ebx
0x18001a75a  jmp     loc_18001A648
0x18001a75f  xor     r15d, r15d
0x18001a762  mov     edx, 5Eh ; '^'; unsigned int
0x18001a767  mov     r9d, 10h; unsigned __int16
0x18001a76d  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001a774  mov     r8d, 0C0001204h; unsigned int
0x18001a77a  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001a77f  jmp     short loc_18001A708
0x18001a781  mov     edx, 22h ; '"'
0x18001a786  jmp     short loc_18001A767
0x18001a788  mov     rcx, [rsi]
0x18001a78b  mov     rdx, r15
0x18001a78e  mov     rax, [rcx]
0x18001a791  mov     rax, [rax+40h]
0x18001a795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a79a  test    al, al
0x18001a79c  jnz     loc_18001A699
0x18001a7a2  mov     r14, rsi
0x18001a7a5  mov     rsi, [rsi+10h]
0x18001a7a9  test    rsi, rsi
0x18001a7ac  jnz     short loc_18001A788
0x18001a7ae  jmp     loc_18001A699
0x18001a7b3  mov     ebp, [rsi+8]
0x18001a7b6  inc     ebp
0x18001a7b8  jmp     loc_18001A6A6
```
