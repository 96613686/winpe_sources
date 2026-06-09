# ExprConstant::BuildCondition(tagTableInfo const &,StoragePool &,tagCondition &,Operator,int)

- ea: `0x180002f70`
- end: `0x18000326e`
- name: `?BuildCondition@ExprConstant@@QEAAXAEBUtagTableInfo@@AEAVStoragePool@@AEAUtagCondition@@W4Operator@@H@Z`
- size: `766`
- prototype: `char __fastcall(__int64, __int64, size_t *, __int64, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002d60`
- `0x18003c380`

## callees

- `0x180002f70`
- `0x180003d54`
- `0x1800434ba`

## import_xrefs

- `msvcrt!malloc` at `0x1800030e7`
- `msvcrt!malloc` at `0x18000318b`
- `msvcrt!malloc` at `0x1800030e7`
- `msvcrt!malloc` at `0x18000318b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800030cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003170`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800030cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003170`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180003086`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180003086`

## string_xrefs

- `0x180003143`: `com\complus\src\events\queryengine\pool.cpp`
- `0x1800031dc`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180003207`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18000322c`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
char __fastcall ExprConstant::BuildCondition(__int64 a1, __int64 a2, size_t *a3, __int64 a4, int a5, int a6)
{
  __int64 v9; // rax
  int v10; // edx
  __int64 v11; // rax
  size_t v12; // rcx
  __int64 v13; // r15
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // r15
  char *v16; // rsi
  int v17; // edx
  size_t v18; // rcx
  unsigned __int64 v19; // rax
  GUID *v20; // rsi
  int v21; // edx
  size_t v22; // r13
  _QWORD *v23; // r12
  size_t v24; // rdi
  void *v25; // rax
  unsigned __int64 v26; // rax
  size_t v27; // r12
  _QWORD *v28; // r15
  size_t v29; // rdi
  void *v30; // rax
  unsigned __int64 v31; // rax
  unsigned int v32; // edx
  unsigned int v33; // edx

  *(_DWORD *)a4 = a6;
  *(_DWORD *)(a4 + 32) = a5;
  LOBYTE(v9) = 0;
  *(_OWORD *)(a4 + 8) = 0;
  *(_QWORD *)(a4 + 24) = 0;
  v10 = *(_DWORD *)(a1 + 8);
  if ( !v10 )
  {
    *(_WORD *)(a4 + 8) = 31;
    v11 = 2 * (*(_QWORD *)(a1 + 24) + 1LL);
    if ( !is_mul_ok(*(_QWORD *)(a1 + 24) + 1LL, 2u) )
      v11 = -1;
    v12 = a3[1];
    v13 = v11 + 7;
    v14 = *(_QWORD *)(v12 + 16);
    v15 = v13 & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v15 <= v14 )
    {
      v16 = *(char **)(v12 + 8);
      *(_QWORD *)(v12 + 16) = v14 - v15;
      *(_QWORD *)(v12 + 8) = &v16[v15];
      if ( v16 )
        goto LABEL_6;
    }
    v22 = *a3;
    if ( v15 > *a3 )
      v22 = 2 * v15;
    v16 = 0;
    v23 = CoTaskMemAlloc(0x20u);
    if ( v23 )
    {
      v24 = a3[1];
      v25 = malloc(v22);
      *v23 = v25;
      v23[1] = v25;
      v23[2] = v22;
      v23[3] = v24;
      if ( v25 )
      {
LABEL_19:
        *a3 = v22;
        a3[1] = (size_t)v23;
        v26 = v23[2];
        if ( v15 > v26 || (v16 = (char *)v23[1], v23[2] = v26 - v15, v23[1] = &v16[v15], !v16) )
          InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
LABEL_6:
        *(_QWORD *)(a4 + 16) = v16;
        LOBYTE(v9) = (unsigned __int8)memcpy_0(v16, *(const void **)(a1 + 16), 2LL * *(_QWORD *)(a1 + 24) + 2);
        return v9;
      }
      v32 = 34;
    }
    else
    {
      v23 = 0;
      v32 = 94;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v32, 0xC0001204, 0x10u);
    goto LABEL_19;
  }
  v17 = v10 - 1;
  if ( !v17 )
  {
    *(_WORD *)(a4 + 8) = 72;
    v18 = a3[1];
    v19 = *(_QWORD *)(v18 + 16);
    if ( v19 >= 0x10 )
    {
      v20 = *(GUID **)(v18 + 8);
      *(_QWORD *)(v18 + 16) = v19 - 16;
      *(_QWORD *)(v18 + 8) = v20 + 1;
      if ( v20 )
      {
LABEL_11:
        *(_QWORD *)(a4 + 16) = v20;
        LOBYTE(v9) = CLSIDFromString(*(LPCOLESTR *)(a1 + 16), v20);
        return v9;
      }
    }
    v27 = *a3;
    if ( *a3 < 0x10 )
      v27 = 32;
    v20 = 0;
    v28 = CoTaskMemAlloc(0x20u);
    if ( v28 )
    {
      v29 = a3[1];
      v30 = malloc(v27);
      *v28 = v30;
      v28[1] = v30;
      v28[2] = v27;
      v28[3] = v29;
      if ( v30 )
      {
LABEL_26:
        *a3 = v27;
        a3[1] = (size_t)v28;
        v31 = v28[2];
        if ( v31 < 0x10 || (v20 = (GUID *)v28[1], v28[2] = v31 - 16, v28[1] = v20 + 1, !v20) )
          InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
        goto LABEL_11;
      }
      v33 = 34;
    }
    else
    {
      v28 = 0;
      v33 = 94;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v33, 0xC0001204, 0x10u);
    goto LABEL_26;
  }
  v21 = v17 - 1;
  if ( v21 )
  {
    if ( v21 == 1 )
    {
      *(_WORD *)(a4 + 8) = 11;
      LOBYTE(v9) = -*(_BYTE *)(a1 + 16);
      *(_WORD *)(a4 + 16) = -(*(_BYTE *)(a1 + 16) != 0);
    }
  }
  else
  {
    *(_WORD *)(a4 + 8) = 20;
    v9 = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(a4 + 16) = v9;
  }
  return v9;
}

```

## disassembly

```asm
0x180002f70  mov     [rsp+arg_8], rbx
0x180002f75  mov     [rsp+arg_10], rbp
0x180002f7a  push    rsi
0x180002f7b  push    rdi
0x180002f7c  push    r12
0x180002f7e  push    r14
0x180002f80  push    r15
0x180002f82  sub     rsp, 20h
0x180002f86  mov     eax, [rsp+48h+arg_28]
0x180002f8a  xorps   xmm0, xmm0
0x180002f8d  mov     [r9], eax
0x180002f90  mov     rbx, r9
0x180002f93  mov     eax, [rsp+48h+arg_20]
0x180002f97  mov     r14, r8
0x180002f9a  mov     [r9+20h], eax
0x180002f9e  mov     rbp, rcx
0x180002fa1  xor     eax, eax
0x180002fa3  movups  xmmword ptr [r9+8], xmm0
0x180002fa8  mov     [r9+18h], rax
0x180002fac  mov     edx, [rcx+8]
0x180002faf  test    edx, edx
0x180002fb1  jnz     loc_180003040
0x180002fb7  mov     word ptr [r9+8], 1Fh
0x180002fbe  mov     eax, 2
0x180002fc3  mov     rcx, [rcx+18h]
0x180002fc7  inc     rcx
0x180002fca  mul     rcx
0x180002fcd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002fd4  cmovb   rax, rcx
0x180002fd8  mov     rcx, [r8+8]
0x180002fdc  lea     r15, [rax+7]
0x180002fe0  mov     rax, [rcx+10h]
0x180002fe4  and     r15, 0FFFFFFFFFFFFFFF8h
0x180002fe8  cmp     r15, rax
0x180002feb  ja      loc_1800030B6
0x180002ff1  mov     rsi, [rcx+8]
0x180002ff5  sub     rax, r15
0x180002ff8  mov     [rcx+10h], rax
0x180002ffc  lea     rax, [rsi+r15]
0x180003000  mov     [rcx+8], rax
0x180003004  test    rsi, rsi
0x180003007  jz      loc_1800030B6
0x18000300d  mov     [rbx+10h], rsi
0x180003011  mov     rcx, rsi; void *
0x180003014  mov     r8, [rbp+18h]
0x180003018  mov     rdx, [rbp+10h]; Src
0x18000301c  lea     r8, ds:2[r8*2]; Size
0x180003024  call    memcpy_0
0x180003029  mov     rbx, [rsp+48h+arg_8]
0x18000302e  mov     rbp, [rsp+48h+arg_10]
0x180003033  add     rsp, 20h
0x180003037  pop     r15
0x180003039  pop     r14
0x18000303b  pop     r12
0x18000303d  pop     rdi
0x18000303e  pop     rsi
0x18000303f  retn
0x180003040  sub     edx, 1
0x180003043  jnz     short loc_18000308E
0x180003045  mov     word ptr [r9+8], 48h ; 'H'
0x18000304c  mov     rcx, [r8+8]
0x180003050  mov     rax, [rcx+10h]
0x180003054  cmp     rax, 10h
0x180003058  jb      loc_180003160
0x18000305e  mov     rsi, [rcx+8]
0x180003062  add     rax, 0FFFFFFFFFFFFFFF0h
0x180003066  mov     [rcx+10h], rax
0x18000306a  lea     rax, [rsi+10h]
0x18000306e  mov     [rcx+8], rax
0x180003072  test    rsi, rsi
0x180003075  jz      loc_180003160
0x18000307b  mov     [rbx+10h], rsi
0x18000307f  mov     rdx, rsi; pclsid
0x180003082  mov     rcx, [rbp+10h]; lpsz
0x180003086  call    cs:__imp_CLSIDFromString
0x18000308c  jmp     short loc_180003029
0x18000308e  sub     edx, 1
0x180003091  jz      loc_180003251
0x180003097  cmp     edx, 1
0x18000309a  jnz     short loc_180003029
0x18000309c  mov     word ptr [r9+8], 0Bh
0x1800030a3  movzx   eax, byte ptr [rcx+10h]
0x1800030a7  neg     al
0x1800030a9  sbb     cx, cx
0x1800030ac  mov     [r9+10h], cx
0x1800030b1  jmp     loc_180003029
0x1800030b6  mov     [rsp+48h+arg_0], r13
0x1800030bb  mov     r13, [r8]
0x1800030be  cmp     r15, r13
0x1800030c1  ja      loc_180003265
0x1800030c7  mov     ecx, 20h ; ' '; cb
0x1800030cc  call    cs:__imp_CoTaskMemAlloc
0x1800030d2  xor     esi, esi
0x1800030d4  mov     r12, rax
0x1800030d7  test    rax, rax
0x1800030da  jz      loc_1800031F9
0x1800030e0  mov     rdi, [r14+8]
0x1800030e4  mov     rcx, r13; Size
0x1800030e7  call    cs:__imp_malloc
0x1800030ed  mov     [r12], rax
0x1800030f1  mov     [r12+8], rax
0x1800030f6  mov     [r12+10h], r13
0x1800030fb  mov     [r12+18h], rdi
0x180003100  test    rax, rax
0x180003103  jz      loc_18000324A
0x180003109  mov     [r14], r13
0x18000310c  mov     r13, [rsp+48h+arg_0]
0x180003111  mov     [r14+8], r12
0x180003115  mov     rax, [r12+10h]
0x18000311a  cmp     r15, rax
0x18000311d  ja      short loc_18000313E
0x18000311f  mov     rsi, [r12+8]
0x180003124  sub     rax, r15
0x180003127  mov     [r12+10h], rax
0x18000312c  lea     rax, [rsi+r15]
0x180003130  mov     [r12+8], rax
0x180003135  test    rsi, rsi
0x180003138  jnz     loc_18000300D
0x18000313e  mov     edx, 64h ; 'd'; unsigned int
0x180003143  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18000314a  mov     r9d, 10h; unsigned __int16
0x180003150  mov     r8d, 0C0001204h; unsigned int
0x180003156  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000315b  jmp     loc_18000300D
0x180003160  mov     r12, [r8]
0x180003163  mov     ecx, 20h ; ' '; cb
0x180003168  cmp     r12, 10h
0x18000316c  cmovb   r12, rcx
0x180003170  call    cs:__imp_CoTaskMemAlloc
0x180003176  xor     esi, esi
0x180003178  mov     r15, rax
0x18000317b  test    rax, rax
0x18000317e  jz      loc_18000321E
0x180003184  mov     rdi, [r14+8]
0x180003188  mov     rcx, r12; Size
0x18000318b  call    cs:__imp_malloc
0x180003191  mov     [r15], rax
0x180003194  mov     [r15+8], rax
0x180003198  mov     [r15+10h], r12
0x18000319c  mov     [r15+18h], rdi
0x1800031a0  test    rax, rax
0x1800031a3  jz      loc_180003243
0x1800031a9  mov     [r14], r12
0x1800031ac  mov     [r14+8], r15
0x1800031b0  mov     rax, [r15+10h]
0x1800031b4  cmp     rax, 10h
0x1800031b8  jb      short loc_1800031D7
0x1800031ba  mov     rsi, [r15+8]
0x1800031be  add     rax, 0FFFFFFFFFFFFFFF0h
0x1800031c2  mov     [r15+10h], rax
0x1800031c6  lea     rax, [rsi+10h]
0x1800031ca  mov     [r15+8], rax
0x1800031ce  test    rsi, rsi
0x1800031d1  jnz     loc_18000307B
0x1800031d7  mov     edx, 64h ; 'd'; unsigned int
0x1800031dc  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x1800031e3  mov     r9d, 10h; unsigned __int16
0x1800031e9  mov     r8d, 0C0001204h; unsigned int
0x1800031ef  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800031f4  jmp     loc_18000307B
0x1800031f9  mov     r12, rsi
0x1800031fc  mov     edx, 5Eh ; '^'; unsigned int
0x180003201  mov     r9d, 10h; unsigned __int16
0x180003207  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18000320e  mov     r8d, 0C0001204h; unsigned int
0x180003214  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180003219  jmp     loc_180003109
0x18000321e  mov     r15, rsi
0x180003221  mov     edx, 5Eh ; '^'; unsigned int
0x180003226  mov     r9d, 10h; unsigned __int16
0x18000322c  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180003233  mov     r8d, 0C0001204h; unsigned int
0x180003239  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000323e  jmp     loc_1800031A9
0x180003243  mov     edx, 22h ; '"'
0x180003248  jmp     short loc_180003226
0x18000324a  mov     edx, 22h ; '"'
0x18000324f  jmp     short loc_180003201
0x180003251  mov     word ptr [r9+8], 14h
0x180003258  mov     rax, [rcx+10h]
0x18000325c  mov     [r9+10h], rax
0x180003260  jmp     loc_180003029
0x180003265  lea     r13, [r15+r15]
0x180003269  jmp     loc_1800030C7
```
