# FveFrRangeListClear

- ea: `0x14002c1c8`
- end: `0x14002c6ca`
- name: `FveFrRangeListClear`
- size: `1282`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14002bfa8`
- `0x14002f6ec`
- `0x14005c100`
- `0x14005d864`
- `0x140079c44`
- `0x1400c0ca0`

## callees

- `0x140018a84`
- `0x140022bf0`
- `0x14002c1c8`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002c47e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002c4f4`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002c524`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002c47e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002c4f4`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002c524`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c268`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c2e2`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c56a`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c268`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c2e2`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002c56a`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002c3ed`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002c588`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002c3ed`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002c588`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002c313`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002c60a`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002c313`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002c60a`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002c3b3`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002c5e1`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002c3b3`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002c5e1`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14002c445`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14002c445`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c6b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c6b9`
- `ntoskrnl!ExAllocatePool2` at `0x14002c4d3`
- `ntoskrnl!ExAllocatePool2` at `0x14002c4d3`

## pseudocode

```c
__int64 __fastcall FveFrRangeListClear(
        struct _RTL_AVL_TABLE **a1,
        struct _RTL_AVL_TABLE *a2,
        struct _RTL_AVL_TABLE *a3)
{
  struct _RTL_AVL_TABLE *v4; // rcx
  unsigned int v7; // esi
  int v8; // r15d
  struct _RTL_AVL_TABLE *v9; // rcx
  struct _RTL_AVL_TABLE **v10; // rsi
  TABLE_SEARCH_RESULT v11; // eax
  struct _RTL_AVL_TABLE **v12; // r14
  struct _RTL_AVL_TABLE *v13; // r14
  struct _RTL_AVL_TABLE *v14; // rax
  struct _RTL_AVL_TABLE *v15; // rcx
  bool v16; // zf
  struct _RTL_AVL_TABLE *v18; // rcx
  _QWORD *v19; // rax
  struct _RTL_AVL_TABLE *v20; // rcx
  struct _RTL_AVL_TABLE **v21; // rax
  struct _RTL_AVL_TABLE *v22; // rcx
  BOOLEAN i; // dl
  int v24; // eax
  __int64 v25; // rax
  _QWORD *v26; // r14
  _QWORD *v27; // rax
  unsigned int v28; // esi
  __int64 v29; // rdx
  struct _RTL_AVL_TABLE *v30; // rcx
  struct _RTL_AVL_TABLE **v31; // rax
  struct _RTL_AVL_TABLE *v32; // r13
  struct _RTL_AVL_TABLE *v33; // rcx
  _QWORD *v34; // rax
  unsigned __int8 NewElement[4]; // [rsp+24h] [rbp-45h] BYREF
  TABLE_SEARCH_RESULT SearchResult; // [rsp+28h] [rbp-41h] BYREF
  PVOID NodeOrParent; // [rsp+30h] [rbp-39h] BYREF
  PVOID RestartKey[2]; // [rsp+38h] [rbp-31h] BYREF
  PVOID P; // [rsp+48h] [rbp-21h]
  __int128 Buffer; // [rsp+50h] [rbp-19h] BYREF
  __int64 v41; // [rsp+60h] [rbp-9h]
  _QWORD *v42; // [rsp+68h] [rbp-1h] BYREF
  struct _RTL_AVL_TABLE *v43; // [rsp+70h] [rbp+7h]
  __int64 v44; // [rsp+78h] [rbp+Fh]

  v41 = 0;
  v4 = a1[8];
  NodeOrParent = 0;
  RestartKey[0] = 0;
  SearchResult = TableEmptyTree;
  v7 = -1073741670;
  NewElement[0] = 0;
  P = 0;
  Buffer = 0;
  if ( v4 )
  {
    v24 = FveRangeListClear();
    v8 = 0;
    if ( v24 != -1073741172 )
      v8 = v24;
    if ( v8 == -1073741670 )
    {
      v8 = -1073741670;
      goto LABEL_19;
    }
    v25 = *((unsigned int *)a1 + 6);
    if ( (_DWORD)v25 )
    {
      P = (PVOID)ExAllocatePool2(64, 24 * v25, 809850438);
      v26 = P;
      if ( !P )
        goto LABEL_19;
      v27 = RtlEnumerateGenericTableAvl(*a1, 1u);
      v28 = 0;
      while ( v27 )
      {
        v29 = 3LL * v28;
        *(_OWORD *)&v26[v29] = *(_OWORD *)v27;
        v26[v29 + 2] = v27[2];
        v27 = RtlEnumerateGenericTableAvl(*a1, 0);
        ++v28;
      }
    }
  }
  else
  {
    v8 = 0;
  }
  if ( a2 > a3 )
  {
    v7 = -1073741811;
    goto LABEL_19;
  }
  v7 = 0;
  if ( a2 != a3 )
  {
    v9 = *a1;
    Buffer = (unsigned __int64)a2;
    LODWORD(v41) = 4;
    v10 = (struct _RTL_AVL_TABLE **)RtlLookupElementGenericTableFullAvl(v9, &Buffer, &NodeOrParent, &SearchResult);
    v11 = SearchResult;
    if ( SearchResult == TableEmptyTree )
    {
      v7 = 0;
      goto LABEL_19;
    }
    a1[4] = (struct _RTL_AVL_TABLE *)((char *)a1[4] + 1);
    if ( v11 != TableFoundNode )
      NodeOrParent = 0;
    v12 = (struct _RTL_AVL_TABLE **)*((_QWORD *)&Buffer + 1);
    while ( 1 )
    {
      if ( a2 >= a3 )
        goto LABEL_28;
      if ( v11 == TableFoundNode )
      {
        v13 = v10[1];
        if ( v13 == a3 )
        {
          v14 = *v10;
          if ( *v10 != a2 )
          {
            if ( v13 == a1[6] )
              a1[6] = a2;
            v10[1] = a2;
            goto LABEL_28;
          }
          if ( !NodeOrParent )
          {
            v15 = *a1;
            Buffer = (unsigned __int64)a2;
            LODWORD(v41) = 4;
            v10 = (struct _RTL_AVL_TABLE **)RtlLookupElementGenericTableFullAvl(
                                              v15,
                                              &Buffer,
                                              &NodeOrParent,
                                              &SearchResult);
            v14 = *v10;
          }
          if ( v14 == a1[5] )
          {
            v20 = *a1;
            RestartKey[0] = NodeOrParent;
            v21 = (struct _RTL_AVL_TABLE **)RtlEnumerateGenericTableWithoutSplayingAvl(v20, RestartKey);
            if ( v21 )
              a1[5] = *v21;
          }
          if ( v10[1] == a1[6] )
          {
            v18 = *a1;
            v43 = *v10;
            v44 = 5;
            v42 = 0;
            v19 = RtlLookupElementGenericTableAvl(v18, &v42);
            if ( v19 || (v19 = v42) != 0 )
              a1[6] = (struct _RTL_AVL_TABLE *)v19[1];
          }
          RtlDeleteElementGenericTableAvlEx(*a1, NodeOrParent);
          v16 = (*((_DWORD *)a1 + 6))-- == 1;
          v7 = 0;
          if ( v16 )
          {
            a1[5] = (struct _RTL_AVL_TABLE *)-1LL;
            a1[6] = 0;
          }
          break;
        }
        if ( v13 > a3 )
        {
          if ( *v10 == a2 )
          {
            if ( *v10 == a1[5] )
              a1[5] = a3;
            *v10 = a3;
            goto LABEL_28;
          }
          v10[1] = a2;
          v22 = *a1;
          *(_QWORD *)&Buffer = a3;
          *((_QWORD *)&Buffer + 1) = v13;
          LODWORD(v41) = 1;
          if ( RtlInsertElementGenericTableAvl(v22, &Buffer, 0x18u, NewElement) )
          {
            ++*((_DWORD *)a1 + 6);
LABEL_28:
            v7 = 0;
            break;
          }
          v10[1] = v13;
          v7 = -1073741670;
          break;
        }
        if ( !NodeOrParent )
        {
          v30 = *a1;
          Buffer = (unsigned __int64)a2;
          LODWORD(v41) = 4;
          v10 = (struct _RTL_AVL_TABLE **)RtlLookupElementGenericTableFullAvl(
                                            v30,
                                            &Buffer,
                                            &NodeOrParent,
                                            &SearchResult);
        }
        RestartKey[0] = NodeOrParent;
        v31 = (struct _RTL_AVL_TABLE **)RtlEnumerateGenericTableWithoutSplayingAvl(*a1, RestartKey);
        v32 = v10[1];
        v12 = v31;
        if ( *v10 == a2 )
        {
          if ( *v10 == a1[5] && v31 )
            a1[5] = *v31;
          if ( v10[1] == a1[6] )
          {
            v33 = *a1;
            v43 = *v10;
            v44 = 5;
            v42 = 0;
            v34 = RtlLookupElementGenericTableAvl(v33, &v42);
            if ( v34 || (v34 = v42) != 0 )
              a1[6] = (struct _RTL_AVL_TABLE *)v34[1];
          }
          RtlDeleteElementGenericTableAvlEx(*a1, NodeOrParent);
          v16 = (*((_DWORD *)a1 + 6))-- == 1;
          if ( v16 )
          {
            a1[5] = (struct _RTL_AVL_TABLE *)-1LL;
            a1[6] = 0;
          }
        }
        else if ( v32 > a2 )
        {
          if ( v32 == a1[6] )
            a1[6] = a2;
          v10[1] = a2;
        }
        if ( !v12 )
          goto LABEL_28;
        a2 = v32;
        NodeOrParent = RestartKey[0];
        v11 = TableInsertAsLeft;
        *(_QWORD *)&Buffer = v32;
        *((_QWORD *)&Buffer + 1) = v12;
      }
      else
      {
        v10 = v12;
        if ( !v12 )
          goto LABEL_28;
        a2 = *v12;
        if ( *v12 >= a3 )
          goto LABEL_28;
        v12 = 0;
        *((_QWORD *)&Buffer + 1) = 0;
        v11 = TableFoundNode;
      }
      SearchResult = v11;
    }
  }
LABEL_19:
  if ( a1[8] && v8 != -1073741670 )
  {
    for ( i = 1; RtlEnumerateGenericTableAvl(*a1, i); i = 0 )
      ;
  }
  if ( P )
    ExFreePoolWithTag(P, 0x30455646u);
  return v7;
}

```

## disassembly

```asm
0x14002c1c8  mov     [rsp-8+arg_18], rbx
0x14002c1cd  push    rbp
0x14002c1ce  push    rsi
0x14002c1cf  push    rdi
0x14002c1d0  push    r12
0x14002c1d2  push    r13
0x14002c1d4  push    r14
0x14002c1d6  push    r15
0x14002c1d8  lea     rbp, [rsp-27h]
0x14002c1dd  sub     rsp, 90h
0x14002c1e4  mov     rax, cs:__security_cookie
0x14002c1eb  xor     rax, rsp
0x14002c1ee  mov     [rbp+57h+var_40], rax
0x14002c1f2  xor     r13d, r13d
0x14002c1f5  xor     eax, eax
0x14002c1f7  mov     rbx, rcx
0x14002c1fa  mov     [rbp+57h+var_60], rax
0x14002c1fe  mov     rcx, [rcx+40h]
0x14002c202  xorps   xmm0, xmm0
0x14002c205  mov     [rbp+57h+NodeOrParent], r13
0x14002c209  mov     r12, r8
0x14002c20c  mov     [rbp+57h+RestartKey], r13
0x14002c210  mov     rdi, rdx
0x14002c213  mov     [rbp+57h+SearchResult], r13d
0x14002c217  mov     esi, 0C000009Ah
0x14002c21c  mov     [rbp+57h+NewElement], r13b
0x14002c220  mov     [rbp+57h+P], r13
0x14002c224  movups  [rbp+57h+Buffer], xmm0
0x14002c228  test    rcx, rcx
0x14002c22b  jnz     loc_14002C497
0x14002c231  mov     r15d, r13d
0x14002c234  cmp     rdi, r12
0x14002c237  ja      loc_14002C53C
0x14002c23d  mov     esi, r13d
0x14002c240  mov     [rbp+57h+var_A0], r13d
0x14002c244  jz      loc_14002C334
0x14002c24a  mov     rcx, [rbx]; Table
0x14002c24d  lea     r9, [rbp+57h+SearchResult]; SearchResult
0x14002c251  lea     r8, [rbp+57h+NodeOrParent]; NodeOrParent
0x14002c255  mov     qword ptr [rbp+57h+Buffer], rdi
0x14002c259  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14002c25d  mov     qword ptr [rbp+57h+Buffer+8], r13
0x14002c261  mov     dword ptr [rbp+57h+var_60], 4
0x14002c268  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x14002c26f  nop     dword ptr [rax+rax+00h]
0x14002c274  mov     rsi, rax
0x14002c277  mov     eax, [rbp+57h+SearchResult]
0x14002c27a  test    eax, eax
0x14002c27c  jz      loc_14002C6A9
0x14002c282  inc     qword ptr [rbx+20h]
0x14002c286  cmp     eax, 1
0x14002c289  jz      short loc_14002C28F
0x14002c28b  mov     [rbp+57h+NodeOrParent], r13
0x14002c28f  mov     r14, qword ptr [rbp+57h+Buffer+8]
0x14002c293  cmp     rdi, r12
0x14002c296  jnb     loc_14002C394
0x14002c29c  cmp     eax, 1
0x14002c29f  jnz     loc_14002C663
0x14002c2a5  mov     r14, [rsi+8]
0x14002c2a9  cmp     r14, r12
0x14002c2ac  jnz     loc_14002C375
0x14002c2b2  mov     rax, [rsi]
0x14002c2b5  cmp     rax, rdi
0x14002c2b8  jnz     loc_14002C40E
0x14002c2be  cmp     [rbp+57h+NodeOrParent], r13
0x14002c2c2  jnz     short loc_14002C2F4
0x14002c2c4  mov     rcx, [rbx]; Table
0x14002c2c7  lea     r9, [rbp+57h+SearchResult]; SearchResult
0x14002c2cb  lea     r8, [rbp+57h+NodeOrParent]; NodeOrParent
0x14002c2cf  mov     qword ptr [rbp+57h+Buffer], rdi
0x14002c2d3  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14002c2d7  mov     qword ptr [rbp+57h+Buffer+8], r13
0x14002c2db  mov     dword ptr [rbp+57h+var_60], 4
0x14002c2e2  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x14002c2e9  nop     dword ptr [rax+rax+00h]
0x14002c2ee  mov     rsi, rax
0x14002c2f1  mov     rax, [rax]
0x14002c2f4  cmp     rax, [rbx+28h]
0x14002c2f8  jz      loc_14002C3DE
0x14002c2fe  mov     rax, [rbx+30h]
0x14002c302  cmp     [rsi+8], rax
0x14002c306  jz      loc_14002C399
0x14002c30c  mov     rdx, [rbp+57h+NodeOrParent]
0x14002c310  mov     rcx, [rbx]
0x14002c313  call    cs:__imp_RtlDeleteElementGenericTableAvlEx
0x14002c31a  nop     dword ptr [rax+rax+00h]
0x14002c31f  add     dword ptr [rbx+18h], 0FFFFFFFFh
0x14002c323  mov     esi, [rbp+57h+var_A0]
0x14002c326  jnz     short loc_14002C334
0x14002c328  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x14002c330  mov     [rbx+30h], r13
0x14002c334  cmp     [rbx+40h], r13
0x14002c338  jnz     loc_14002C46C
0x14002c33e  mov     rax, [rbp+57h+P]
0x14002c342  test    rax, rax
0x14002c345  jnz     loc_14002C6B1
0x14002c34b  mov     eax, esi
0x14002c34d  mov     rcx, [rbp+57h+var_40]
0x14002c351  xor     rcx, rsp; StackCookie
0x14002c354  call    __security_check_cookie
0x14002c359  mov     rbx, [rsp+0C0h+arg_18]
0x14002c361  add     rsp, 90h
0x14002c368  pop     r15
0x14002c36a  pop     r14
0x14002c36c  pop     r13
0x14002c36e  pop     r12
0x14002c370  pop     rdi
0x14002c371  pop     rsi
0x14002c372  pop     rbp
0x14002c373  retn
0x14002c375  jbe     loc_14002C546
0x14002c37b  mov     rax, [rsi]
0x14002c37e  cmp     rax, rdi
0x14002c381  jnz     loc_14002C421
0x14002c387  cmp     rax, [rbx+28h]
0x14002c38b  jz      loc_14002C68F
0x14002c391  mov     [rsi], r12
0x14002c394  mov     esi, [rbp+57h+var_A0]
0x14002c397  jmp     short loc_14002C334
0x14002c399  mov     rax, [rsi]
0x14002c39c  lea     rdx, [rbp+57h+var_58]; Buffer
0x14002c3a0  mov     rcx, [rbx]; Table
0x14002c3a3  mov     [rbp+57h+var_50], rax
0x14002c3a7  mov     [rbp+57h+var_48], 5
0x14002c3af  mov     [rbp+57h+var_58], r13
0x14002c3b3  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14002c3ba  nop     dword ptr [rax+rax+00h]
0x14002c3bf  test    rax, rax
0x14002c3c2  jnz     short loc_14002C3D1
0x14002c3c4  mov     rax, [rbp+57h+var_58]
0x14002c3c8  test    rax, rax
0x14002c3cb  jz      loc_14002C30C
0x14002c3d1  mov     rax, [rax+8]
0x14002c3d5  mov     [rbx+30h], rax
0x14002c3d9  jmp     loc_14002C30C
0x14002c3de  mov     rax, [rbp+57h+NodeOrParent]
0x14002c3e2  lea     rdx, [rbp+57h+RestartKey]; RestartKey
0x14002c3e6  mov     rcx, [rbx]; Table
0x14002c3e9  mov     [rbp+57h+RestartKey], rax
0x14002c3ed  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14002c3f4  nop     dword ptr [rax+rax+00h]
0x14002c3f9  test    rax, rax
0x14002c3fc  jz      loc_14002C2FE
0x14002c402  mov     rax, [rax]
0x14002c405  mov     [rbx+28h], rax
0x14002c409  jmp     loc_14002C2FE
0x14002c40e  cmp     r14, [rbx+30h]
0x14002c412  jz      loc_14002C698
0x14002c418  mov     [rsi+8], rdi
0x14002c41c  jmp     loc_14002C394
0x14002c421  mov     [rsi+8], rdi
0x14002c425  lea     r9, [rbp+57h+NewElement]; NewElement
0x14002c429  mov     rcx, [rbx]; Table
0x14002c42c  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14002c430  mov     r8d, 18h; BufferSize
0x14002c436  mov     qword ptr [rbp+57h+Buffer], r12
0x14002c43a  mov     qword ptr [rbp+57h+Buffer+8], r14
0x14002c43e  mov     dword ptr [rbp+57h+var_60], 1
0x14002c445  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14002c44c  nop     dword ptr [rax+rax+00h]
0x14002c451  test    rax, rax
0x14002c454  jz      short loc_14002C45E
0x14002c456  inc     dword ptr [rbx+18h]
0x14002c459  jmp     loc_14002C394
0x14002c45e  mov     [rsi+8], r14
0x14002c462  mov     esi, 0C000009Ah
0x14002c467  jmp     loc_14002C334
0x14002c46c  cmp     r15d, 0C000009Ah
0x14002c473  jz      loc_14002C33E
0x14002c479  mov     dl, 1; Restart
0x14002c47b  mov     rcx, [rbx]; Table
0x14002c47e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002c485  nop     dword ptr [rax+rax+00h]
0x14002c48a  test    rax, rax
0x14002c48d  jz      loc_14002C33E
0x14002c493  xor     edx, edx
0x14002c495  jmp     short loc_14002C47B
0x14002c497  call    FveRangeListClear
0x14002c49c  cmp     eax, 0C000028Ch
0x14002c4a1  mov     r15d, r13d
0x14002c4a4  cmovnz  r15d, eax
0x14002c4a8  cmp     r15d, esi
0x14002c4ab  jnz     short loc_14002C4B5
0x14002c4ad  mov     r15d, esi
0x14002c4b0  jmp     loc_14002C334
0x14002c4b5  mov     eax, [rbx+18h]
0x14002c4b8  test    eax, eax
0x14002c4ba  jz      loc_14002C234
0x14002c4c0  lea     rdx, [rax+rax*2]
0x14002c4c4  mov     ecx, 40h ; '@'
0x14002c4c9  shl     rdx, 3
0x14002c4cd  mov     r8d, 30455646h
0x14002c4d3  call    cs:__imp_ExAllocatePool2
0x14002c4da  nop     dword ptr [rax+rax+00h]
0x14002c4df  mov     [rbp+57h+P], rax
0x14002c4e3  mov     r14, rax
0x14002c4e6  test    rax, rax
0x14002c4e9  jz      loc_14002C334
0x14002c4ef  mov     rcx, [rbx]; Table
0x14002c4f2  mov     dl, 1; Restart
0x14002c4f4  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002c4fb  nop     dword ptr [rax+rax+00h]
0x14002c500  mov     esi, r13d
0x14002c503  jmp     short loc_14002C532
0x14002c505  movups  xmm0, xmmword ptr [rax]
0x14002c508  mov     ecx, esi
0x14002c50a  lea     rdx, [rcx+rcx*2]
0x14002c50e  movups  xmmword ptr [r14+rdx*8], xmm0
0x14002c513  movsd   xmm1, qword ptr [rax+10h]
0x14002c518  movsd   qword ptr [r14+rdx*8+10h], xmm1
0x14002c51f  xor     edx, edx; Restart
0x14002c521  mov     rcx, [rbx]; Table
0x14002c524  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002c52b  nop     dword ptr [rax+rax+00h]
0x14002c530  inc     esi
0x14002c532  test    rax, rax
0x14002c535  jnz     short loc_14002C505
0x14002c537  jmp     loc_14002C234
0x14002c53c  mov     esi, 0C000000Dh
0x14002c541  jmp     loc_14002C334
0x14002c546  cmp     [rbp+57h+NodeOrParent], r13
0x14002c54a  jnz     short loc_14002C579
0x14002c54c  mov     rcx, [rbx]; Table
0x14002c54f  lea     r9, [rbp+57h+SearchResult]; SearchResult
0x14002c553  lea     r8, [rbp+57h+NodeOrParent]; NodeOrParent
0x14002c557  mov     qword ptr [rbp+57h+Buffer], rdi
0x14002c55b  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14002c55f  mov     qword ptr [rbp+57h+Buffer+8], r13
0x14002c563  mov     dword ptr [rbp+57h+var_60], 4
0x14002c56a  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x14002c571  nop     dword ptr [rax+rax+00h]
0x14002c576  mov     rsi, rax
0x14002c579  mov     rcx, [rbp+57h+NodeOrParent]
0x14002c57d  lea     rdx, [rbp+57h+RestartKey]; RestartKey
0x14002c581  mov     [rbp+57h+RestartKey], rcx
0x14002c585  mov     rcx, [rbx]; Table
0x14002c588  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14002c58f  nop     dword ptr [rax+rax+00h]
0x14002c594  mov     r13, [rsi+8]
0x14002c598  mov     r14, rax
0x14002c59b  mov     rax, [rsi]
0x14002c59e  cmp     rax, rdi
0x14002c5a1  jnz     loc_14002C62E
0x14002c5a7  cmp     rax, [rbx+28h]
0x14002c5ab  jnz     short loc_14002C5B9
0x14002c5ad  test    r14, r14
0x14002c5b0  jz      short loc_14002C5B9
0x14002c5b2  mov     rcx, [r14]
0x14002c5b5  mov     [rbx+28h], rcx
0x14002c5b9  mov     rax, [rbx+30h]
0x14002c5bd  cmp     [rsi+8], rax
0x14002c5c1  jnz     short loc_14002C603
0x14002c5c3  mov     rax, [rsi]
0x14002c5c6  lea     rdx, [rbp+57h+var_58]; Buffer
0x14002c5ca  mov     rcx, [rbx]; Table
0x14002c5cd  mov     [rbp+57h+var_50], rax
0x14002c5d1  mov     [rbp+57h+var_48], 5
0x14002c5d9  mov     [rbp+57h+var_58], 0
0x14002c5e1  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14002c5e8  nop     dword ptr [rax+rax+00h]
0x14002c5ed  test    rax, rax
0x14002c5f0  jnz     short loc_14002C5FB
0x14002c5f2  mov     rax, [rbp+57h+var_58]
0x14002c5f6  test    rax, rax
0x14002c5f9  jz      short loc_14002C603
0x14002c5fb  mov     rax, [rax+8]
0x14002c5ff  mov     [rbx+30h], rax
0x14002c603  mov     rdx, [rbp+57h+NodeOrParent]
0x14002c607  mov     rcx, [rbx]
0x14002c60a  call    cs:__imp_RtlDeleteElementGenericTableAvlEx
0x14002c611  nop     dword ptr [rax+rax+00h]
0x14002c616  add     dword ptr [rbx+18h], 0FFFFFFFFh
0x14002c61a  jnz     short loc_14002C641
0x14002c61c  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x14002c624  mov     qword ptr [rbx+30h], 0
0x14002c62c  jmp     short loc_14002C641
0x14002c62e  cmp     r13, rdi
0x14002c631  jbe     short loc_14002C641
0x14002c633  cmp     r13, [rbx+30h]
0x14002c637  jnz     short loc_14002C63D
0x14002c639  mov     [rbx+30h], rdi
0x14002c63d  mov     [rsi+8], rdi
0x14002c641  test    r14, r14
0x14002c644  jz      short loc_14002C6A1
0x14002c646  mov     rax, [rbp+57h+RestartKey]
0x14002c64a  mov     rdi, r13
0x14002c64d  mov     [rbp+57h+NodeOrParent], rax
0x14002c651  mov     eax, 2
0x14002c656  mov     qword ptr [rbp+57h+Buffer], r13
0x14002c65a  xor     r13d, r13d
0x14002c65d  mov     qword ptr [rbp+57h+Buffer+8], r14
0x14002c661  jmp     short loc_14002C687
0x14002c663  mov     rsi, r14
0x14002c666  test    r14, r14
0x14002c669  jz      loc_14002C394
0x14002c66f  mov     rdi, [r14]
0x14002c672  cmp     rdi, r12
0x14002c675  jnb     loc_14002C394
0x14002c67b  mov     r14, r13
0x14002c67e  mov     qword ptr [rbp+57h+Buffer+8], r13
  ... truncated ...
```
