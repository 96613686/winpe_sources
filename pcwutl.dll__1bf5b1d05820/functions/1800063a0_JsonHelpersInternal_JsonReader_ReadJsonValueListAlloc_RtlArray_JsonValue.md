# JsonHelpersInternal::JsonReader::ReadJsonValueListAlloc(RtlArray<JsonValue *> * *)

- ea: `0x1800063a0`
- end: `0x18000665b`
- name: `?ReadJsonValueListAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(JsonHelpersInternal::JsonReader *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180005ef4`

## callees

- `0x180001524`
- `0x180002f54`
- `0x180002ff0`
- `0x180005ef4`
- `0x1800063a0`
- `0x1800191a2`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180006557`
- `KERNEL32!HeapAlloc` at `0x180006557`
- `KERNEL32!GetProcessHeap` at `0x1800063ec`
- `KERNEL32!GetProcessHeap` at `0x18000640a`
- `KERNEL32!GetProcessHeap` at `0x1800063ec`
- `KERNEL32!GetProcessHeap` at `0x18000640a`
- `KERNEL32!HeapReAlloc` at `0x180006577`
- `KERNEL32!HeapReAlloc` at `0x180006577`

## pseudocode

```c
__int64 __fastcall JsonHelpersInternal::JsonReader::ReadJsonValueListAlloc(
        JsonHelpersInternal::JsonReader *this,
        _QWORD *a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx
  __int64 v6; // r10
  __int64 v7; // r8
  __int16 v8; // r9
  __int64 v9; // rdx
  int v10; // esi
  __int16 v11; // r8
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // rcx
  __int64 v14; // r14
  unsigned __int64 v15; // r14
  unsigned __int128 v16; // rax
  size_t v17; // r12
  void *v18; // r8
  void *v19; // rcx
  void *v20; // rax
  LPVOID v21; // rsi
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rcx
  __int64 v24; // r9
  __int64 v25; // rdx
  __int16 v26; // r8
  __int16 v27; // cx
  _OWORD *v29; // [rsp+80h] [rbp+50h] BYREF
  struct JsonValue *v30; // [rsp+88h] [rbp+58h] BYREF

  v29 = 0;
  v30 = 0;
  v4 = operator new(0x30u);
  v5 = v4;
  if ( !v4 )
  {
    v10 = -2147024882;
    goto LABEL_51;
  }
  *v4 = 0;
  v4[1] = 0;
  v4[2] = 0;
  GetProcessHeap();
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  *(_QWORD *)v5 = GetProcessHeap();
  *((_QWORD *)v5 + 4) = 16;
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_QWORD *)v5 + 5) = 0;
  *((_QWORD *)v5 + 1) = 8;
  v6 = *((_QWORD *)this + 1);
  v29 = v5;
  while ( 1 )
  {
    v7 = *(_QWORD *)this;
    v8 = *(_WORD *)(v6 + 2LL * *(_QWORD *)this);
    if ( v8 != 9
      && *(_WORD *)(v6 + 2LL * *(_QWORD *)this) != 10
      && *(_WORD *)(v6 + 2LL * *(_QWORD *)this) != 13
      && *(_WORD *)(v6 + 2LL * *(_QWORD *)this) != 32 )
    {
      break;
    }
    *(_QWORD *)this = v7 + 1;
    if ( !v8 )
      *(_QWORD *)this = v7;
  }
  v9 = v7 + 1;
  *(_QWORD *)this = v7 + 1;
  if ( !v8 )
  {
    *(_QWORD *)this = v7;
LABEL_12:
    v10 = -2147024883;
    goto LABEL_51;
  }
  if ( v8 != 91 )
    goto LABEL_12;
  while ( 1 )
  {
    v11 = *(_WORD *)(v6 + 2 * v9);
    if ( v11 != 9 && *(_WORD *)(v6 + 2 * v9) != 10 && *(_WORD *)(v6 + 2 * v9) != 13 && *(_WORD *)(v6 + 2 * v9) != 32 )
      break;
    *(_QWORD *)this = v9 + 1;
    if ( v11 )
      ++v9;
    else
      *(_QWORD *)this = v9;
  }
  if ( v11 != 93 )
  {
    while ( 1 )
    {
      v10 = JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(this, &v30);
      if ( v10 < 0 )
        goto LABEL_51;
      v12 = *((_QWORD *)v5 + 2);
      if ( v12 >= *((_QWORD *)v5 + 3) )
      {
        v13 = v12 + 1;
        if ( v12 + 1 <= *((_QWORD *)v5 + 3) )
          goto LABEL_38;
        v14 = *((_QWORD *)v5 + 4) - 1LL;
        if ( v14 + v13 < v13 )
          goto LABEL_38;
        if ( !is_mul_ok(*((_QWORD *)v5 + 3), *((_QWORD *)v5 + 1)) )
          goto LABEL_38;
        v15 = (v14 + v13) & ~v14;
        v16 = v15 * (unsigned __int128)*((unsigned __int64 *)v5 + 1);
        v17 = v15 * *((_QWORD *)v5 + 1);
        if ( !is_mul_ok(v15, *((_QWORD *)v5 + 1)) )
          goto LABEL_38;
        v18 = (void *)*((_QWORD *)v5 + 5);
        v19 = *(void **)v5;
        if ( v18 )
        {
          v21 = HeapReAlloc(v19, DWORD2(v16), v18, v15 * *((_QWORD *)v5 + 1));
        }
        else
        {
          v20 = HeapAlloc(v19, DWORD2(v16), v15 * *((_QWORD *)v5 + 1));
          v21 = v20;
          if ( v20 )
            memset_0(v20, 0, v17);
        }
        if ( !v21 )
          goto LABEL_38;
        *((_QWORD *)v5 + 5) = v21;
        *((_QWORD *)v5 + 3) = v15;
      }
      v22 = *((_QWORD *)v5 + 1) * v12;
      if ( is_mul_ok(*((_QWORD *)v5 + 1), v12) )
      {
        v23 = *((_QWORD *)v5 + 5);
        if ( v23 + v22 >= v23 )
        {
          *(_QWORD *)(v23 + v22) = v30;
          ++*((_QWORD *)v5 + 2);
        }
      }
LABEL_38:
      v24 = *((_QWORD *)this + 1);
      v30 = 0;
      while ( 1 )
      {
        v25 = *(_QWORD *)this;
        v26 = *(_WORD *)(v24 + 2LL * *(_QWORD *)this);
        if ( v26 != 9
          && *(_WORD *)(v24 + 2LL * *(_QWORD *)this) != 10
          && *(_WORD *)(v24 + 2LL * *(_QWORD *)this) != 13
          && *(_WORD *)(v24 + 2LL * *(_QWORD *)this) != 32 )
        {
          break;
        }
        *(_QWORD *)this = v25 + 1;
        if ( !v26 )
          *(_QWORD *)this = v25;
      }
      v27 = *(_WORD *)(v24 + 2 * v25);
      *(_QWORD *)this = v25 + 1;
      if ( !v27 )
      {
        *(_QWORD *)this = v25;
        goto LABEL_12;
      }
      if ( v27 != 44 )
      {
        if ( v27 != 93 )
          goto LABEL_12;
        goto LABEL_22;
      }
    }
  }
  *(_QWORD *)this = v9 + 1;
LABEL_22:
  *a2 = v5;
  v10 = 0;
  v29 = 0;
LABEL_51:
  CleanupJsonValueList(&v29);
  CleanupJsonValue(&v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800063a0  mov     [rsp-38h+arg_0], rbx
0x1800063a5  push    rbp
0x1800063a6  push    rsi
0x1800063a7  push    rdi
0x1800063a8  push    r12
0x1800063aa  push    r13
0x1800063ac  push    r14
0x1800063ae  push    r15
0x1800063b0  mov     rbp, rsp
0x1800063b3  sub     rsp, 30h
0x1800063b7  xor     r12d, r12d
0x1800063ba  mov     rdi, rcx
0x1800063bd  mov     r13, rdx
0x1800063c0  mov     [rbp+arg_10], r12
0x1800063c4  mov     [rbp+arg_18], r12
0x1800063c8  lea     ecx, [r12+30h]; Size
0x1800063cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800063d2  mov     rbx, rax
0x1800063d5  test    rax, rax
0x1800063d8  jz      loc_18000662D
0x1800063de  xorps   xmm0, xmm0
0x1800063e1  movups  xmmword ptr [rax], xmm0
0x1800063e4  movups  xmmword ptr [rax+10h], xmm0
0x1800063e8  movups  xmmword ptr [rax+20h], xmm0
0x1800063ec  call    cs:__imp_GetProcessHeap
0x1800063f2  xorps   xmm0, xmm0
0x1800063f5  lea     esi, [r12+10h]
0x1800063fa  movups  xmmword ptr [rbx], xmm0
0x1800063fd  lea     r14d, [r12+8]
0x180006402  movups  xmmword ptr [rbx+10h], xmm0
0x180006406  movups  xmmword ptr [rbx+20h], xmm0
0x18000640a  call    cs:__imp_GetProcessHeap
0x180006410  mov     [rbx], rax
0x180006413  mov     [rbx+20h], rsi
0x180006417  mov     [rbx+10h], r12
0x18000641b  mov     [rbx+18h], r12
0x18000641f  mov     [rbx+28h], r12
0x180006423  mov     [rbx+8], r14
0x180006427  mov     r10, [rdi+8]
0x18000642b  mov     [rbp+arg_10], rbx
0x18000642f  mov     r8, [rdi]
0x180006432  movzx   r9d, word ptr [r10+r8*2]
0x180006437  mov     ecx, r9d
0x18000643a  sub     ecx, 9
0x18000643d  jz      short loc_18000644E
0x18000643f  sub     ecx, 1
0x180006442  jz      short loc_18000644E
0x180006444  sub     ecx, 3
0x180006447  jz      short loc_18000644E
0x180006449  cmp     ecx, 13h
0x18000644c  jnz     short loc_180006460
0x18000644e  lea     rax, [r8+1]
0x180006452  mov     [rdi], rax
0x180006455  cmp     r12w, r9w
0x180006459  jnz     short loc_18000642F
0x18000645b  mov     [rdi], r8
0x18000645e  jmp     short loc_18000642F
0x180006460  lea     rdx, [r8+1]
0x180006464  mov     [rdi], rdx
0x180006467  cmp     r12w, r9w
0x18000646b  jnz     short loc_180006472
0x18000646d  mov     [rdi], r8
0x180006470  jmp     short loc_18000647D
0x180006472  mov     eax, 5Bh ; '['
0x180006477  cmp     ax, r9w
0x18000647b  jz      short loc_180006487
0x18000647d  mov     esi, 8007000Dh
0x180006482  jmp     loc_180006632
0x180006487  movzx   r8d, word ptr [r10+rdx*2]
0x18000648c  mov     ecx, r8d
0x18000648f  sub     ecx, 9
0x180006492  jz      short loc_1800064A3
0x180006494  sub     ecx, 1
0x180006497  jz      short loc_1800064A3
0x180006499  sub     ecx, 3
0x18000649c  jz      short loc_1800064A3
0x18000649e  cmp     ecx, 13h
0x1800064a1  jnz     short loc_1800064BA
0x1800064a3  lea     rcx, [rdx+1]
0x1800064a7  mov     [rdi], rcx
0x1800064aa  cmp     r12w, r8w
0x1800064ae  jnz     short loc_1800064B5
0x1800064b0  mov     [rdi], rdx
0x1800064b3  jmp     short loc_180006487
0x1800064b5  mov     rdx, rcx
0x1800064b8  jmp     short loc_180006487
0x1800064ba  mov     eax, 5Dh ; ']'
0x1800064bf  cmp     ax, r8w
0x1800064c3  jnz     short loc_1800064DC
0x1800064c5  lea     rax, [rdx+1]
0x1800064c9  mov     [rdi], rax
0x1800064cc  mov     [r13+0], rbx
0x1800064d0  mov     esi, r12d
0x1800064d3  mov     [rbp+arg_10], r12
0x1800064d7  jmp     loc_180006632
0x1800064dc  lea     rdx, [rbp+arg_18]; struct JsonValue **
0x1800064e0  mov     rcx, rdi; this
0x1800064e3  call    ?ReadJsonValueAlloc@JsonReader@JsonHelpersInternal@@QEAAJPEAPEAUJsonValue@@@Z; JsonHelpersInternal::JsonReader::ReadJsonValueAlloc(JsonValue * *)
0x1800064e8  mov     esi, eax
0x1800064ea  test    eax, eax
0x1800064ec  js      loc_180006632
0x1800064f2  mov     r15, [rbx+10h]
0x1800064f6  cmp     r15, [rbx+18h]
0x1800064fa  jb      loc_180006590
0x180006500  lea     rcx, [r15+1]
0x180006504  cmp     rcx, [rbx+18h]
0x180006508  jbe     loc_1800065B9
0x18000650e  mov     r14, [rbx+20h]
0x180006512  dec     r14
0x180006515  lea     r8, [r14+rcx]
0x180006519  cmp     r8, rcx
0x18000651c  jb      loc_1800065B9
0x180006522  mov     rax, [rbx+8]
0x180006526  mul     qword ptr [rbx+18h]
0x18000652a  test    rdx, rdx
0x18000652d  jnz     loc_1800065B9
0x180006533  mov     rax, [rbx+8]
0x180006537  not     r14
0x18000653a  and     r14, r8
0x18000653d  mul     r14
0x180006540  mov     r12, rax
0x180006543  test    rdx, rdx
0x180006546  jnz     short loc_1800065B6
0x180006548  mov     r8, [rbx+28h]; lpMem
0x18000654c  mov     rcx, [rbx]; hHeap
0x18000654f  test    r8, r8
0x180006552  jnz     short loc_180006574
0x180006554  mov     r8, rax; dwBytes
0x180006557  call    cs:__imp_HeapAlloc
0x18000655d  mov     rsi, rax
0x180006560  test    rax, rax
0x180006563  jz      short loc_180006580
0x180006565  mov     r8, r12; Size
0x180006568  xor     edx, edx; Val
0x18000656a  mov     rcx, rax; void *
0x18000656d  call    memset_0
0x180006572  jmp     short loc_180006580
0x180006574  mov     r9, r12; dwBytes
0x180006577  call    cs:__imp_HeapReAlloc
0x18000657d  mov     rsi, rax
0x180006580  xor     r12d, r12d
0x180006583  test    rsi, rsi
0x180006586  jz      short loc_1800065B9
0x180006588  mov     [rbx+28h], rsi
0x18000658c  mov     [rbx+18h], r14
0x180006590  mov     rax, r15
0x180006593  mul     qword ptr [rbx+8]
0x180006597  test    rdx, rdx
0x18000659a  jnz     short loc_1800065B9
0x18000659c  mov     rcx, [rbx+28h]
0x1800065a0  lea     rdx, [rcx+rax]
0x1800065a4  cmp     rdx, rcx
0x1800065a7  jb      short loc_1800065B9
0x1800065a9  mov     rax, [rbp+arg_18]
0x1800065ad  mov     [rdx], rax
0x1800065b0  inc     qword ptr [rbx+10h]
0x1800065b4  jmp     short loc_1800065B9
0x1800065b6  xor     r12d, r12d
0x1800065b9  mov     r9, [rdi+8]
0x1800065bd  mov     [rbp+arg_18], r12
0x1800065c1  mov     rdx, [rdi]
0x1800065c4  movzx   r8d, word ptr [r9+rdx*2]
0x1800065c9  mov     ecx, r8d
0x1800065cc  sub     ecx, 9
0x1800065cf  jz      short loc_1800065E0
0x1800065d1  sub     ecx, 1
0x1800065d4  jz      short loc_1800065E0
0x1800065d6  sub     ecx, 3
0x1800065d9  jz      short loc_1800065E0
0x1800065db  cmp     ecx, 13h
0x1800065de  jnz     short loc_1800065F2
0x1800065e0  lea     rax, [rdx+1]
0x1800065e4  mov     [rdi], rax
0x1800065e7  cmp     r12w, r8w
0x1800065eb  jnz     short loc_1800065C1
0x1800065ed  mov     [rdi], rdx
0x1800065f0  jmp     short loc_1800065C1
0x1800065f2  movzx   ecx, word ptr [r9+rdx*2]
0x1800065f7  lea     rax, [rdx+1]
0x1800065fb  mov     [rdi], rax
0x1800065fe  cmp     r12w, cx
0x180006602  jz      short loc_180006625
0x180006604  mov     eax, 2Ch ; ','
0x180006609  cmp     ax, cx
0x18000660c  jz      loc_1800064DC
0x180006612  mov     eax, 5Dh ; ']'
0x180006617  cmp     ax, cx
0x18000661a  jnz     loc_18000647D
0x180006620  jmp     loc_1800064CC
0x180006625  mov     [rdi], rdx
0x180006628  jmp     loc_18000647D
0x18000662d  mov     esi, 8007000Eh
0x180006632  lea     rcx, [rbp+arg_10]
0x180006636  call    ?CleanupJsonValueList@@YAXPEAPEAV?$RtlArray@PEAUJsonValue@@@@@Z; CleanupJsonValueList(RtlArray<JsonValue *> * *)
0x18000663b  lea     rcx, [rbp+arg_18]; struct JsonValue **
0x18000663f  call    ?CleanupJsonValue@@YAXPEAPEAUJsonValue@@@Z; CleanupJsonValue(JsonValue * *)
0x180006644  mov     rbx, [rsp+30h+arg_0]
0x180006649  mov     eax, esi
0x18000664b  add     rsp, 30h
0x18000664f  pop     r15
0x180006651  pop     r14
0x180006653  pop     r13
0x180006655  pop     r12
0x180006657  pop     rdi
0x180006658  pop     rsi
0x180006659  pop     rbp
0x18000665a  retn
```
