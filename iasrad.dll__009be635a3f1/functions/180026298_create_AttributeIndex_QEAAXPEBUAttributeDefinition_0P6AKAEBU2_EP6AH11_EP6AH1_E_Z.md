# ?create@AttributeIndex@@QEAAXPEBUAttributeDefinition@@0P6AKAEBU2@@_EP6AH11@_EP6AH1@_E@Z

- ea: `0x180026298`
- end: `0x1800263ca`
- name: `?create@AttributeIndex@@QEAAXPEBUAttributeDefinition@@0P6AKAEBU2@@_EP6AH11@_EP6AH1@_E@Z`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180020578`

## callees

- `0x18000e470`
- `0x180026298`
- `0x18002e202`
- `0x180030010`

## import_xrefs

- `msvcrt!free` at `0x1800262b4`
- `msvcrt!free` at `0x1800262b4`

## pseudocode

```c
void *__fastcall AttributeIndex::create(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 (__fastcall *a6)(__int64))
{
  __int64 v10; // rdi
  __int64 i; // rbx
  int v12; // eax
  int v13; // ecx
  unsigned int j; // ecx
  __int64 v15; // rbx
  char *v16; // rax
  size_t v17; // rbx
  char *v18; // r12
  void *result; // rax
  char *v20; // rbx
  unsigned int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx

  free(*(void **)a1);
  *(_QWORD *)(a1 + 24) = a5;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = a4;
  if ( a6 )
  {
    LODWORD(v10) = 0;
    for ( i = a2; i != a3; LODWORD(v10) = v13 )
    {
      v12 = a6(i);
      v13 = v10 + 1;
      if ( !v12 )
        v13 = v10;
      i += 28;
    }
  }
  else
  {
    v10 = 0x6DB6DB6DB6DB6DB7LL * ((a3 - a2) >> 2);
  }
  for ( j = 1; j < (unsigned int)v10; j *= 2 )
    ;
  v15 = j;
  *(_DWORD *)(a1 + 8) = j - 1;
  v16 = (char *)operator new(8 * (j + 2LL * (unsigned int)v10));
  v17 = 8 * v15;
  *(_QWORD *)a1 = v16;
  v18 = v16;
  result = memset_0(v16, 0, v17);
  if ( (_DWORD)v10 )
  {
    v20 = &v18[v17];
    while ( a2 != a3 )
    {
      if ( !a6 || (result = (void *)a6(a2), (_DWORD)result) )
      {
        v21 = (*(__int64 (__fastcall **)(__int64))(a1 + 16))(a2);
        v22 = *(_QWORD **)a1;
        v23 = v21 & *(_DWORD *)(a1 + 8);
        result = *(void **)(*(_QWORD *)a1 + 8 * v23);
        *(_QWORD *)v20 = result;
        v22[v23] = v20;
        *((_QWORD *)v20 + 1) = a2;
        v20 += 16;
      }
      a2 += 28;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026298  push    rbx
0x18002629a  push    rbp
0x18002629b  push    rsi
0x18002629c  push    rdi
0x18002629d  push    r12
0x18002629f  push    r14
0x1800262a1  sub     rsp, 28h
0x1800262a5  mov     r14, rcx
0x1800262a8  mov     rbx, r9
0x1800262ab  mov     rcx, [rcx]; Block
0x1800262ae  mov     rbp, r8
0x1800262b1  mov     rsi, rdx
0x1800262b4  call    cs:__imp_free
0x1800262ba  cmp     [rsp+58h+arg_28], 0
0x1800262c3  mov     rax, [rsp+58h+arg_20]
0x1800262cb  mov     [r14+18h], rax
0x1800262cf  mov     qword ptr [r14], 0
0x1800262d6  mov     [r14+10h], rbx
0x1800262da  jz      short loc_18002630B
0x1800262dc  xor     edi, edi
0x1800262de  mov     rbx, rsi
0x1800262e1  cmp     rsi, rbp
0x1800262e4  jz      short loc_180026323
0x1800262e6  mov     rax, [rsp+58h+arg_28]
0x1800262ee  mov     rcx, rbx
0x1800262f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262f6  test    eax, eax
0x1800262f8  lea     ecx, [rdi+1]
0x1800262fb  cmovz   ecx, edi
0x1800262fe  add     rbx, 1Ch
0x180026302  mov     edi, ecx
0x180026304  cmp     rbx, rbp
0x180026307  jnz     short loc_1800262E6
0x180026309  jmp     short loc_180026323
0x18002630b  mov     rdi, rbp
0x18002630e  mov     rax, 6DB6DB6DB6DB6DB7h
0x180026318  sub     rdi, rsi
0x18002631b  sar     rdi, 2
0x18002631f  imul    rdi, rax
0x180026323  mov     ecx, 1
0x180026328  cmp     edi, ecx
0x18002632a  jbe     short loc_180026332
0x18002632c  add     ecx, ecx
0x18002632e  cmp     ecx, edi
0x180026330  jb      short loc_18002632C
0x180026332  lea     eax, [rcx-1]
0x180026335  mov     ebx, ecx
0x180026337  mov     [r14+8], eax
0x18002633b  mov     eax, edi
0x18002633d  lea     rcx, [rbx+rax*2]
0x180026341  shl     rcx, 3; Size
0x180026345  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002634a  shl     rbx, 3
0x18002634e  xor     edx, edx; Val
0x180026350  mov     r8, rbx; Size
0x180026353  mov     [r14], rax
0x180026356  mov     rcx, rax; void *
0x180026359  mov     r12, rax
0x18002635c  call    memset_0
0x180026361  test    edi, edi
0x180026363  jz      short loc_1800263BD
0x180026365  add     rbx, r12
0x180026368  jmp     short loc_1800263B8
0x18002636a  cmp     [rsp+58h+arg_28], 0
0x180026373  jz      short loc_180026389
0x180026375  mov     rax, [rsp+58h+arg_28]
0x18002637d  mov     rcx, rsi
0x180026380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026385  test    eax, eax
0x180026387  jz      short loc_1800263B4
0x180026389  mov     rax, [r14+10h]
0x18002638d  mov     rcx, rsi
0x180026390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026395  mov     edx, [r14+8]
0x180026399  mov     rcx, [r14]
0x18002639c  mov     eax, eax
0x18002639e  and     rdx, rax
0x1800263a1  mov     rax, [rcx+rdx*8]
0x1800263a5  mov     [rbx], rax
0x1800263a8  mov     [rcx+rdx*8], rbx
0x1800263ac  mov     [rbx+8], rsi
0x1800263b0  add     rbx, 10h
0x1800263b4  add     rsi, 1Ch
0x1800263b8  cmp     rsi, rbp
0x1800263bb  jnz     short loc_18002636A
0x1800263bd  add     rsp, 28h
0x1800263c1  pop     r14
0x1800263c3  pop     r12
0x1800263c5  pop     rdi
0x1800263c6  pop     rsi
0x1800263c7  pop     rbp
0x1800263c8  pop     rbx
0x1800263c9  retn
```
