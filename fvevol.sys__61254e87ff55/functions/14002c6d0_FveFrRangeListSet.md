# FveFrRangeListSet

- ea: `0x14002c6d0`
- end: `0x14002cab3`
- name: `FveFrRangeListSet`
- size: `995`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x14002bfa8`
- `0x14002f3d8`
- `0x1400593a4`
- `0x140059594`
- `0x140059844`
- `0x1400797c0`
- `0x1400962dc`

## callees

- `0x14000a324`
- `0x140018a84`
- `0x140022bf0`
- `0x14002c6d0`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002ca0b`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002ca39`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002ca84`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002ca0b`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002ca39`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002ca84`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c76a`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c804`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c76a`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c804`
- `ntoskrnl!RtlInsertElementGenericTableFullAvl` at `0x14002c7af`
- `ntoskrnl!RtlInsertElementGenericTableFullAvl` at `0x14002c9a0`
- `ntoskrnl!RtlInsertElementGenericTableFullAvl` at `0x14002c7af`
- `ntoskrnl!RtlInsertElementGenericTableFullAvl` at `0x14002c9a0`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002c831`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002c8d4`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002c831`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002c8d4`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002c90c`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002c944`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002c90c`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002c944`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002caa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002caa2`
- `ntoskrnl!ExAllocatePool2` at `0x14002c9f2`
- `ntoskrnl!ExAllocatePool2` at `0x14002c9f2`

## pseudocode

```c
__int64 __fastcall FveFrRangeListSet(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  int v3; // eax
  char v4; // di
  __int64 v6; // rcx
  _QWORD *Pool2; // r12
  _DWORD *v10; // rdi
  unsigned int v11; // r14d
  struct _RTL_AVL_TABLE *v12; // rcx
  _QWORD *v13; // rax
  TABLE_SEARCH_RESULT v14; // ecx
  _QWORD *v15; // r13
  PVOID v16; // rax
  struct _RTL_AVL_TABLE *v17; // rcx
  _QWORD *inserted; // rax
  _QWORD *v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  struct _RTL_AVL_TABLE *v22; // rcx
  _QWORD *v23; // rax
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  __int64 v26; // rcx
  _QWORD *v28; // rax
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // rax
  struct _RTL_AVL_TABLE *v31; // rcx
  bool v32; // zf
  __int64 v33; // rax
  _QWORD *v34; // rax
  __int64 v35; // r14
  __int64 v36; // rdx
  BOOLEAN i; // dl
  TABLE_SEARCH_RESULT v38; // [rsp+28h] [rbp-48h]
  int v39; // [rsp+34h] [rbp-3Ch]
  unsigned __int8 NewElement[4]; // [rsp+38h] [rbp-38h] BYREF
  TABLE_SEARCH_RESULT SearchResult; // [rsp+3Ch] [rbp-34h] BYREF
  PVOID NodeOrParent; // [rsp+40h] [rbp-30h] BYREF
  PVOID RestartKey; // [rsp+48h] [rbp-28h] BYREF
  __int128 Buffer; // [rsp+50h] [rbp-20h] BYREF
  __int64 v45; // [rsp+60h] [rbp-10h]

  v3 = 0;
  v4 = 0;
  v45 = 0;
  v6 = a1[8];
  Pool2 = 0;
  NodeOrParent = 0;
  RestartKey = 0;
  SearchResult = TableEmptyTree;
  NewElement[0] = 0;
  Buffer = 0;
  if ( v6 )
  {
    v3 = FveRangeListSet();
    v39 = v3;
    if ( v3 == -1073741670 )
    {
      v11 = -1073741670;
      goto LABEL_22;
    }
    v10 = a1 + 3;
    v33 = *((unsigned int *)a1 + 6);
    if ( (_DWORD)v33 )
    {
      Pool2 = (_QWORD *)ExAllocatePool2(64, 24 * v33, 809850438);
      if ( Pool2 )
      {
        v34 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)*a1, 1u);
        v35 = 0;
        while ( v34 )
        {
          v36 = 3 * v35;
          *(_OWORD *)&Pool2[v36] = *(_OWORD *)v34;
          Pool2[v36 + 2] = v34[2];
          v34 = RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)*a1, 0);
          v35 = (unsigned int)(v35 + 1);
        }
      }
    }
    v3 = v39;
  }
  else
  {
    v39 = 0;
    v10 = a1 + 3;
  }
  if ( a2 > a3 )
  {
    v11 = -1073741811;
    goto LABEL_35;
  }
  v11 = 0;
  if ( a2 != a3 )
  {
    v12 = (struct _RTL_AVL_TABLE *)*a1;
    Buffer = a2;
    LODWORD(v45) = 4;
    v13 = RtlLookupElementGenericTableFullAvl(v12, &Buffer, &NodeOrParent, &SearchResult);
    v14 = SearchResult;
    v15 = v13;
    if ( SearchResult == TableEmptyTree )
    {
      v31 = (struct _RTL_AVL_TABLE *)*a1;
      *((_QWORD *)&Buffer + 1) = a3;
      LODWORD(v45) = 1;
      v32 = RtlInsertElementGenericTableFullAvl(v31, &Buffer, 0x18u, NewElement, NodeOrParent, TableEmptyTree) == 0;
      v3 = v39;
      if ( v32 )
      {
        v11 = -1073741670;
        v4 = 1;
        goto LABEL_22;
      }
      ++*v10;
      ++a1[4];
      a1[5] = a2;
      a1[6] = a3;
      goto LABEL_21;
    }
    if ( SearchResult == TableFoundNode )
    {
      if ( v13[1] < a3 )
      {
        ++a1[4];
        *((_QWORD *)&Buffer + 1) = a3;
        while ( 1 )
        {
          v16 = NodeOrParent;
          RestartKey = NodeOrParent;
          if ( !NodeOrParent )
          {
            v14 = SearchResult;
            goto LABEL_8;
          }
          v28 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)*a1, &RestartKey);
          v24 = *((_QWORD *)&Buffer + 1);
          if ( !v28 || *v28 > *((_QWORD *)&Buffer + 1) )
            break;
          v29 = v28[1];
          if ( *((_QWORD *)&Buffer + 1) <= v29 )
            v24 = v29;
          *((_QWORD *)&Buffer + 1) = v24;
          RtlDeleteElementGenericTableAvlEx(*a1, RestartKey);
          --*v10;
        }
LABEL_17:
        v15[1] = v24;
        v25 = a1[6];
        if ( v25 <= v24 )
          v25 = v24;
        a1[6] = v25;
      }
      goto LABEL_20;
    }
    v16 = NodeOrParent;
LABEL_8:
    v38 = v14;
    v17 = (struct _RTL_AVL_TABLE *)*a1;
    *((_QWORD *)&Buffer + 1) = 0;
    inserted = RtlInsertElementGenericTableFullAvl(v17, &Buffer, 0x18u, NewElement, v16, v38);
    v19 = inserted;
    if ( inserted )
    {
      ++*v10;
      ++a1[4];
      v20 = *inserted;
      v21 = a1[5];
      if ( v21 >= v20 )
        v21 = v20;
      a1[5] = v21;
      v19[1] = a2;
      *((_DWORD *)v19 + 4) = 2;
      v22 = (struct _RTL_AVL_TABLE *)*a1;
      *((_QWORD *)&Buffer + 1) = a2;
      LODWORD(v45) = 3;
      v15 = RtlLookupElementGenericTableFullAvl(v22, &Buffer, &NodeOrParent, &SearchResult);
      if ( SearchResult == TableFoundNode )
      {
        *((_QWORD *)&Buffer + 1) = a3;
        while ( 1 )
        {
          RestartKey = NodeOrParent;
          if ( !NodeOrParent )
            break;
          v23 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)*a1, &RestartKey);
          v24 = *((_QWORD *)&Buffer + 1);
          if ( !v23 || *v23 > *((_QWORD *)&Buffer + 1) )
          {
            *((_DWORD *)v15 + 4) = 1;
            goto LABEL_17;
          }
          v30 = v23[1];
          if ( *((_QWORD *)&Buffer + 1) <= v30 )
            v24 = v30;
          *((_QWORD *)&Buffer + 1) = v24;
          RtlDeleteElementGenericTableAvlEx(*a1, RestartKey);
          --*v10;
        }
      }
LABEL_20:
      v3 = v39;
      goto LABEL_21;
    }
    v3 = v39;
    v11 = -1073741670;
LABEL_35:
    v4 = 0;
    goto LABEL_22;
  }
LABEL_21:
  v4 = 0;
LABEL_22:
  v26 = a1[8];
  if ( v26 && v3 != -1073741670 )
  {
    if ( v4 )
      FveRangeListClear(v26, a2, a3);
    for ( i = 1; RtlEnumerateGenericTableAvl((PRTL_AVL_TABLE)*a1, i); i = 0 )
      ;
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x30455646u);
  return v11;
}

```

## disassembly

```asm
0x14002c6d0  mov     [rsp-38h+arg_18], rbx
0x14002c6d5  push    rbp
0x14002c6d6  push    rsi
0x14002c6d7  push    rdi
0x14002c6d8  push    r12
0x14002c6da  push    r13
0x14002c6dc  push    r14
0x14002c6de  push    r15
0x14002c6e0  mov     rbp, rsp
0x14002c6e3  sub     rsp, 70h
0x14002c6e7  mov     rax, cs:__security_cookie
0x14002c6ee  xor     rax, rsp
0x14002c6f1  mov     [rbp+var_8], rax
0x14002c6f5  xor     eax, eax
0x14002c6f7  xor     dil, dil
0x14002c6fa  mov     rbx, rcx
0x14002c6fd  mov     [rbp+var_10], rax
0x14002c701  mov     rcx, [rcx+40h]
0x14002c705  xor     r12d, r12d
0x14002c708  mov     [rbp+NodeOrParent], rax
0x14002c70c  xorps   xmm0, xmm0
0x14002c70f  mov     [rbp+RestartKey], rax
0x14002c713  mov     rsi, r8
0x14002c716  mov     [rbp+SearchResult], eax
0x14002c719  mov     r15, rdx
0x14002c71c  mov     [rbp+NewElement], al
0x14002c71f  mov     [rbp+var_40], dil
0x14002c723  movups  [rbp+Buffer], xmm0
0x14002c727  test    rcx, rcx
0x14002c72a  jnz     loc_14002C957
0x14002c730  mov     [rbp+var_3C], eax
0x14002c733  lea     rdi, [rbx+18h]
0x14002c737  cmp     r15, rsi
0x14002c73a  ja      loc_14002CA55
0x14002c740  xor     r14d, r14d
0x14002c743  cmp     r15, rsi
0x14002c746  jz      loc_14002C86D
0x14002c74c  mov     rcx, [rbx]; Table
0x14002c74f  lea     r9, [rbp+SearchResult]; SearchResult
0x14002c753  lea     r8, [rbp+NodeOrParent]; NodeOrParent
0x14002c757  mov     qword ptr [rbp+Buffer], r15
0x14002c75b  lea     rdx, [rbp+Buffer]; Buffer
0x14002c75f  mov     qword ptr [rbp+Buffer+8], r14
0x14002c763  mov     dword ptr [rbp+var_10], 4
0x14002c76a  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x14002c771  nop     dword ptr [rax+rax+00h]
0x14002c776  mov     ecx, [rbp+SearchResult]
0x14002c779  mov     r13, rax
0x14002c77c  test    ecx, ecx
0x14002c77e  jz      loc_14002C976
0x14002c784  cmp     ecx, 1
0x14002c787  jz      loc_14002C8AE
0x14002c78d  mov     rax, [rbp+NodeOrParent]
0x14002c791  mov     [rsp+70h+var_48], ecx; SearchResult
0x14002c795  lea     r9, [rbp+NewElement]; NewElement
0x14002c799  mov     rcx, [rbx]; Table
0x14002c79c  lea     rdx, [rbp+Buffer]; Buffer
0x14002c7a0  mov     r8d, 18h; BufferSize
0x14002c7a6  mov     qword ptr [rbp+Buffer+8], r14
0x14002c7aa  mov     [rsp+70h+var_50], rax; NodeOrParent
0x14002c7af  call    cs:__imp_RtlInsertElementGenericTableFullAvl
0x14002c7b6  nop     dword ptr [rax+rax+00h]
0x14002c7bb  mov     rdx, rax
0x14002c7be  test    rax, rax
0x14002c7c1  jz      loc_14002C91C
0x14002c7c7  inc     dword ptr [rdi]
0x14002c7c9  lea     r9, [rbp+SearchResult]; SearchResult
0x14002c7cd  inc     qword ptr [rbx+20h]
0x14002c7d1  lea     r8, [rbp+NodeOrParent]; NodeOrParent
0x14002c7d5  mov     rcx, [rax]
0x14002c7d8  mov     rax, [rbx+28h]
0x14002c7dc  cmp     rax, rcx
0x14002c7df  cmovnb  rax, rcx
0x14002c7e3  mov     [rbx+28h], rax
0x14002c7e7  mov     [rdx+8], r15
0x14002c7eb  mov     dword ptr [rdx+10h], 2
0x14002c7f2  lea     rdx, [rbp+Buffer]; Buffer
0x14002c7f6  mov     rcx, [rbx]; Table
0x14002c7f9  mov     qword ptr [rbp+Buffer+8], r15
0x14002c7fd  mov     dword ptr [rbp+var_10], 3
0x14002c804  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x14002c80b  nop     dword ptr [rax+rax+00h]
0x14002c810  cmp     [rbp+SearchResult], 1
0x14002c814  mov     r13, rax
0x14002c817  jnz     short loc_14002C86A
0x14002c819  mov     qword ptr [rbp+Buffer+8], rsi
0x14002c81d  mov     rcx, [rbp+NodeOrParent]
0x14002c821  mov     [rbp+RestartKey], rcx
0x14002c825  test    rcx, rcx
0x14002c828  jz      short loc_14002C86A
0x14002c82a  mov     rcx, [rbx]; Table
0x14002c82d  lea     rdx, [rbp+RestartKey]; RestartKey
0x14002c831  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14002c838  nop     dword ptr [rax+rax+00h]
0x14002c83d  mov     rcx, qword ptr [rbp+Buffer+8]
0x14002c841  test    rax, rax
0x14002c844  jz      short loc_14002C84F
0x14002c846  cmp     [rax], rcx
0x14002c849  jbe     loc_14002C92E
0x14002c84f  mov     dword ptr [r13+10h], 1
0x14002c857  mov     [r13+8], rcx
0x14002c85b  mov     rax, [rbx+30h]
0x14002c85f  cmp     rax, rcx
0x14002c862  cmovbe  rax, rcx
0x14002c866  mov     [rbx+30h], rax
0x14002c86a  mov     eax, [rbp+var_3C]
0x14002c86d  mov     dil, r14b
0x14002c870  mov     rcx, [rbx+40h]
0x14002c874  test    rcx, rcx
0x14002c877  jnz     loc_14002CA60
0x14002c87d  test    r12, r12
0x14002c880  jnz     loc_14002CA9A
0x14002c886  mov     eax, r14d
0x14002c889  mov     rcx, [rbp+var_8]
0x14002c88d  xor     rcx, rsp; StackCookie
0x14002c890  call    __security_check_cookie
0x14002c895  mov     rbx, [rsp+70h+arg_18]
0x14002c89d  add     rsp, 70h
0x14002c8a1  pop     r15
0x14002c8a3  pop     r14
0x14002c8a5  pop     r13
0x14002c8a7  pop     r12
0x14002c8a9  pop     rdi
0x14002c8aa  pop     rsi
0x14002c8ab  pop     rbp
0x14002c8ac  retn
0x14002c8ae  cmp     [rax+8], rsi
0x14002c8b2  jnb     short loc_14002C86A
0x14002c8b4  inc     qword ptr [rbx+20h]
0x14002c8b8  mov     qword ptr [rbp+Buffer+8], rsi
0x14002c8bc  mov     rax, [rbp+NodeOrParent]
0x14002c8c0  mov     [rbp+RestartKey], rax
0x14002c8c4  test    rax, rax
0x14002c8c7  jz      loc_14002C96E
0x14002c8cd  mov     rcx, [rbx]; Table
0x14002c8d0  lea     rdx, [rbp+RestartKey]; RestartKey
0x14002c8d4  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14002c8db  nop     dword ptr [rax+rax+00h]
0x14002c8e0  mov     rcx, qword ptr [rbp+Buffer+8]
0x14002c8e4  test    rax, rax
0x14002c8e7  jz      loc_14002C857
0x14002c8ed  cmp     [rax], rcx
0x14002c8f0  ja      loc_14002C857
0x14002c8f6  mov     rax, [rax+8]
0x14002c8fa  mov     rdx, [rbp+RestartKey]
0x14002c8fe  cmp     rcx, rax
0x14002c901  cmovbe  rcx, rax
0x14002c905  mov     qword ptr [rbp+Buffer+8], rcx
0x14002c909  mov     rcx, [rbx]
0x14002c90c  call    cs:__imp_RtlDeleteElementGenericTableAvlEx
0x14002c913  nop     dword ptr [rax+rax+00h]
0x14002c918  dec     dword ptr [rdi]
0x14002c91a  jmp     short loc_14002C8BC
0x14002c91c  mov     eax, [rbp+var_3C]
0x14002c91f  mov     r14d, 0C000009Ah
0x14002c925  mov     dil, [rbp+var_40]
0x14002c929  jmp     loc_14002C870
0x14002c92e  mov     rax, [rax+8]
0x14002c932  mov     rdx, [rbp+RestartKey]
0x14002c936  cmp     rcx, rax
0x14002c939  cmovbe  rcx, rax
0x14002c93d  mov     qword ptr [rbp+Buffer+8], rcx
0x14002c941  mov     rcx, [rbx]
0x14002c944  call    cs:__imp_RtlDeleteElementGenericTableAvlEx
0x14002c94b  nop     dword ptr [rax+rax+00h]
0x14002c950  dec     dword ptr [rdi]
0x14002c952  jmp     loc_14002C81D
0x14002c957  call    FveRangeListSet
0x14002c95c  mov     [rbp+var_3C], eax
0x14002c95f  cmp     eax, 0C000009Ah
0x14002c964  jnz     short loc_14002C9D5
0x14002c966  mov     r14d, eax
0x14002c969  jmp     loc_14002C870
0x14002c96e  mov     ecx, [rbp+SearchResult]
0x14002c971  jmp     loc_14002C791
0x14002c976  mov     rax, [rbp+NodeOrParent]
0x14002c97a  lea     r9, [rbp+NewElement]; NewElement
0x14002c97e  mov     rcx, [rbx]; Table
0x14002c981  lea     rdx, [rbp+Buffer]; Buffer
0x14002c985  mov     [rsp+70h+var_48], r14d; SearchResult
0x14002c98a  mov     r8d, 18h; BufferSize
0x14002c990  mov     [rsp+70h+var_50], rax; NodeOrParent
0x14002c995  mov     qword ptr [rbp+Buffer+8], rsi
0x14002c999  mov     dword ptr [rbp+var_10], 1
0x14002c9a0  call    cs:__imp_RtlInsertElementGenericTableFullAvl
0x14002c9a7  nop     dword ptr [rax+rax+00h]
0x14002c9ac  test    rax, rax
0x14002c9af  mov     eax, [rbp+var_3C]
0x14002c9b2  jz      short loc_14002C9C7
0x14002c9b4  inc     dword ptr [rdi]
0x14002c9b6  inc     qword ptr [rbx+20h]
0x14002c9ba  mov     [rbx+28h], r15
0x14002c9be  mov     [rbx+30h], rsi
0x14002c9c2  jmp     loc_14002C86D
0x14002c9c7  mov     r14d, 0C000009Ah
0x14002c9cd  mov     dil, 1
0x14002c9d0  jmp     loc_14002C870
0x14002c9d5  lea     rdi, [rbx+18h]
0x14002c9d9  mov     eax, [rdi]
0x14002c9db  test    eax, eax
0x14002c9dd  jz      short loc_14002CA4D
0x14002c9df  lea     rdx, [rax+rax*2]
0x14002c9e3  mov     ecx, 40h ; '@'
0x14002c9e8  shl     rdx, 3
0x14002c9ec  mov     r8d, 30455646h
0x14002c9f2  call    cs:__imp_ExAllocatePool2
0x14002c9f9  nop     dword ptr [rax+rax+00h]
0x14002c9fe  mov     r12, rax
0x14002ca01  test    rax, rax
0x14002ca04  jz      short loc_14002CA4D
0x14002ca06  mov     rcx, [rbx]; Table
0x14002ca09  mov     dl, 1; Restart
0x14002ca0b  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002ca12  nop     dword ptr [rax+rax+00h]
0x14002ca17  xor     r14d, r14d
0x14002ca1a  jmp     short loc_14002CA48
0x14002ca1c  movups  xmm0, xmmword ptr [rax]
0x14002ca1f  lea     rdx, [r14+r14*2]
0x14002ca23  movups  xmmword ptr [r12+rdx*8], xmm0
0x14002ca28  movsd   xmm1, qword ptr [rax+10h]
0x14002ca2d  movsd   qword ptr [r12+rdx*8+10h], xmm1
0x14002ca34  xor     edx, edx; Restart
0x14002ca36  mov     rcx, [rbx]; Table
0x14002ca39  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002ca40  nop     dword ptr [rax+rax+00h]
0x14002ca45  inc     r14d
0x14002ca48  test    rax, rax
0x14002ca4b  jnz     short loc_14002CA1C
0x14002ca4d  mov     eax, [rbp+var_3C]
0x14002ca50  jmp     loc_14002C737
0x14002ca55  mov     r14d, 0C000000Dh
0x14002ca5b  jmp     loc_14002C925
0x14002ca60  cmp     eax, 0C000009Ah
0x14002ca65  jz      loc_14002C87D
0x14002ca6b  test    dil, dil
0x14002ca6e  jz      short loc_14002CA7B
0x14002ca70  mov     r8, rsi
0x14002ca73  mov     rdx, r15
0x14002ca76  call    FveRangeListClear
0x14002ca7b  mov     dl, 1
0x14002ca7d  jmp     short loc_14002CA81
0x14002ca7f  xor     edx, edx; Restart
0x14002ca81  mov     rcx, [rbx]; Table
0x14002ca84  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002ca8b  nop     dword ptr [rax+rax+00h]
0x14002ca90  test    rax, rax
0x14002ca93  jnz     short loc_14002CA7F
0x14002ca95  jmp     loc_14002C87D
0x14002ca9a  mov     edx, 30455646h; Tag
0x14002ca9f  mov     rcx, r12; P
0x14002caa2  call    cs:__imp_ExFreePoolWithTag
0x14002caa9  nop     dword ptr [rax+rax+00h]
0x14002caae  jmp     loc_14002C886
```
