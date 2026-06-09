# FveFrRangeListClear

- ea: `0x14002b1c8`
- end: `0x14002b6ca`
- name: `FveFrRangeListClear`
- size: `1282`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14002afa8`
- `0x14002e6ec`
- `0x14005a0a8`
- `0x14005b7f4`
- `0x140077c14`
- `0x1400bd230`

## callees

- `0x140018074`
- `0x1400218c0`
- `0x14002b1c8`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002b47e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002b4f4`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002b524`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002b47e`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002b4f4`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14002b524`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002b268`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002b2e2`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002b56a`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002b268`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002b2e2`
- `ntoskrnl!RtlLookupElementGenericTableFullAvl` at `0x14002b56a`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002b3ed`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002b588`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002b3ed`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x14002b588`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002b313`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002b60a`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002b313`
- `ntoskrnl!RtlDeleteElementGenericTableAvlEx` at `0x14002b60a`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002b3b3`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002b5e1`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002b3b3`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14002b5e1`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14002b445`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x14002b445`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b6b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b6b9`
- `ntoskrnl!ExAllocatePool2` at `0x14002b4d3`
- `ntoskrnl!ExAllocatePool2` at `0x14002b4d3`

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
0x14002b1c8  mov     [rsp-8+arg_18], rbx
0x14002b1cd  push    rbp
0x14002b1ce  push    rsi
0x14002b1cf  push    rdi
0x14002b1d0  push    r12
0x14002b1d2  push    r13
0x14002b1d4  push    r14
0x14002b1d6  push    r15
0x14002b1d8  lea     rbp, [rsp-27h]
0x14002b1dd  sub     rsp, 90h
0x14002b1e4  mov     rax, cs:__security_cookie
0x14002b1eb  xor     rax, rsp
0x14002b1ee  mov     [rbp+57h+var_40], rax
0x14002b1f2  xor     r13d, r13d
0x14002b1f5  xor     eax, eax
0x14002b1f7  mov     rbx, rcx
0x14002b1fa  mov     [rbp+57h+var_60], rax
0x14002b1fe  mov     rcx, [rcx+40h]
0x14002b202  xorps   xmm0, xmm0
0x14002b205  mov     [rbp+57h+NodeOrParent], r13
0x14002b209  mov     r12, r8
0x14002b20c  mov     [rbp+57h+RestartKey], r13
0x14002b210  mov     rdi, rdx
0x14002b213  mov     [rbp+57h+SearchResult], r13d
0x14002b217  mov     esi, 0C000009Ah
0x14002b21c  mov     [rbp+57h+NewElement], r13b
0x14002b220  mov     [rbp+57h+P], r13
0x14002b224  movups  [rbp+57h+Buffer], xmm0
0x14002b228  test    rcx, rcx
0x14002b22b  jnz     loc_14002B497
0x14002b231  mov     r15d, r13d
0x14002b234  cmp     rdi, r12
0x14002b237  ja      loc_14002B53C
0x14002b23d  mov     esi, r13d
0x14002b240  mov     [rbp+57h+var_A0], r13d
0x14002b244  jz      loc_14002B334
0x14002b24a  mov     rcx, [rbx]; Table
0x14002b24d  lea     r9, [rbp+57h+SearchResult]; SearchResult
0x14002b251  lea     r8, [rbp+57h+NodeOrParent]; NodeOrParent
0x14002b255  mov     qword ptr [rbp+57h+Buffer], rdi
0x14002b259  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14002b25d  mov     qword ptr [rbp+57h+Buffer+8], r13
0x14002b261  mov     dword ptr [rbp+57h+var_60], 4
0x14002b268  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x14002b26f  nop     dword ptr [rax+rax+00h]
0x14002b274  mov     rsi, rax
0x14002b277  mov     eax, [rbp+57h+SearchResult]
0x14002b27a  test    eax, eax
0x14002b27c  jz      loc_14002B6A9
0x14002b282  inc     qword ptr [rbx+20h]
0x14002b286  cmp     eax, 1
0x14002b289  jz      short loc_14002B28F
0x14002b28b  mov     [rbp+57h+NodeOrParent], r13
0x14002b28f  mov     r14, qword ptr [rbp+57h+Buffer+8]
0x14002b293  cmp     rdi, r12
0x14002b296  jnb     loc_14002B394
0x14002b29c  cmp     eax, 1
0x14002b29f  jnz     loc_14002B663
0x14002b2a5  mov     r14, [rsi+8]
0x14002b2a9  cmp     r14, r12
0x14002b2ac  jnz     loc_14002B375
0x14002b2b2  mov     rax, [rsi]
0x14002b2b5  cmp     rax, rdi
0x14002b2b8  jnz     loc_14002B40E
0x14002b2be  cmp     [rbp+57h+NodeOrParent], r13
0x14002b2c2  jnz     short loc_14002B2F4
0x14002b2c4  mov     rcx, [rbx]; Table
0x14002b2c7  lea     r9, [rbp+57h+SearchResult]; SearchResult
0x14002b2cb  lea     r8, [rbp+57h+NodeOrParent]; NodeOrParent
0x14002b2cf  mov     qword ptr [rbp+57h+Buffer], rdi
0x14002b2d3  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14002b2d7  mov     qword ptr [rbp+57h+Buffer+8], r13
0x14002b2db  mov     dword ptr [rbp+57h+var_60], 4
0x14002b2e2  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x14002b2e9  nop     dword ptr [rax+rax+00h]
0x14002b2ee  mov     rsi, rax
0x14002b2f1  mov     rax, [rax]
0x14002b2f4  cmp     rax, [rbx+28h]
0x14002b2f8  jz      loc_14002B3DE
0x14002b2fe  mov     rax, [rbx+30h]
0x14002b302  cmp     [rsi+8], rax
0x14002b306  jz      loc_14002B399
0x14002b30c  mov     rdx, [rbp+57h+NodeOrParent]
0x14002b310  mov     rcx, [rbx]
0x14002b313  call    cs:__imp_RtlDeleteElementGenericTableAvlEx
0x14002b31a  nop     dword ptr [rax+rax+00h]
0x14002b31f  add     dword ptr [rbx+18h], 0FFFFFFFFh
0x14002b323  mov     esi, [rbp+57h+var_A0]
0x14002b326  jnz     short loc_14002B334
0x14002b328  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x14002b330  mov     [rbx+30h], r13
0x14002b334  cmp     [rbx+40h], r13
0x14002b338  jnz     loc_14002B46C
0x14002b33e  mov     rax, [rbp+57h+P]
0x14002b342  test    rax, rax
0x14002b345  jnz     loc_14002B6B1
0x14002b34b  mov     eax, esi
0x14002b34d  mov     rcx, [rbp+57h+var_40]
0x14002b351  xor     rcx, rsp; StackCookie
0x14002b354  call    __security_check_cookie
0x14002b359  mov     rbx, [rsp+0C0h+arg_18]
0x14002b361  add     rsp, 90h
0x14002b368  pop     r15
0x14002b36a  pop     r14
0x14002b36c  pop     r13
0x14002b36e  pop     r12
0x14002b370  pop     rdi
0x14002b371  pop     rsi
0x14002b372  pop     rbp
0x14002b373  retn
0x14002b375  jbe     loc_14002B546
0x14002b37b  mov     rax, [rsi]
0x14002b37e  cmp     rax, rdi
0x14002b381  jnz     loc_14002B421
0x14002b387  cmp     rax, [rbx+28h]
0x14002b38b  jz      loc_14002B68F
0x14002b391  mov     [rsi], r12
0x14002b394  mov     esi, [rbp+57h+var_A0]
0x14002b397  jmp     short loc_14002B334
0x14002b399  mov     rax, [rsi]
0x14002b39c  lea     rdx, [rbp+57h+var_58]; Buffer
0x14002b3a0  mov     rcx, [rbx]; Table
0x14002b3a3  mov     [rbp+57h+var_50], rax
0x14002b3a7  mov     [rbp+57h+var_48], 5
0x14002b3af  mov     [rbp+57h+var_58], r13
0x14002b3b3  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14002b3ba  nop     dword ptr [rax+rax+00h]
0x14002b3bf  test    rax, rax
0x14002b3c2  jnz     short loc_14002B3D1
0x14002b3c4  mov     rax, [rbp+57h+var_58]
0x14002b3c8  test    rax, rax
0x14002b3cb  jz      loc_14002B30C
0x14002b3d1  mov     rax, [rax+8]
0x14002b3d5  mov     [rbx+30h], rax
0x14002b3d9  jmp     loc_14002B30C
0x14002b3de  mov     rax, [rbp+57h+NodeOrParent]
0x14002b3e2  lea     rdx, [rbp+57h+RestartKey]; RestartKey
0x14002b3e6  mov     rcx, [rbx]; Table
0x14002b3e9  mov     [rbp+57h+RestartKey], rax
0x14002b3ed  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14002b3f4  nop     dword ptr [rax+rax+00h]
0x14002b3f9  test    rax, rax
0x14002b3fc  jz      loc_14002B2FE
0x14002b402  mov     rax, [rax]
0x14002b405  mov     [rbx+28h], rax
0x14002b409  jmp     loc_14002B2FE
0x14002b40e  cmp     r14, [rbx+30h]
0x14002b412  jz      loc_14002B698
0x14002b418  mov     [rsi+8], rdi
0x14002b41c  jmp     loc_14002B394
0x14002b421  mov     [rsi+8], rdi
0x14002b425  lea     r9, [rbp+57h+NewElement]; NewElement
0x14002b429  mov     rcx, [rbx]; Table
0x14002b42c  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14002b430  mov     r8d, 18h; BufferSize
0x14002b436  mov     qword ptr [rbp+57h+Buffer], r12
0x14002b43a  mov     qword ptr [rbp+57h+Buffer+8], r14
0x14002b43e  mov     dword ptr [rbp+57h+var_60], 1
0x14002b445  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14002b44c  nop     dword ptr [rax+rax+00h]
0x14002b451  test    rax, rax
0x14002b454  jz      short loc_14002B45E
0x14002b456  inc     dword ptr [rbx+18h]
0x14002b459  jmp     loc_14002B394
0x14002b45e  mov     [rsi+8], r14
0x14002b462  mov     esi, 0C000009Ah
0x14002b467  jmp     loc_14002B334
0x14002b46c  cmp     r15d, 0C000009Ah
0x14002b473  jz      loc_14002B33E
0x14002b479  mov     dl, 1; Restart
0x14002b47b  mov     rcx, [rbx]; Table
0x14002b47e  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002b485  nop     dword ptr [rax+rax+00h]
0x14002b48a  test    rax, rax
0x14002b48d  jz      loc_14002B33E
0x14002b493  xor     edx, edx
0x14002b495  jmp     short loc_14002B47B
0x14002b497  call    FveRangeListClear
0x14002b49c  cmp     eax, 0C000028Ch
0x14002b4a1  mov     r15d, r13d
0x14002b4a4  cmovnz  r15d, eax
0x14002b4a8  cmp     r15d, esi
0x14002b4ab  jnz     short loc_14002B4B5
0x14002b4ad  mov     r15d, esi
0x14002b4b0  jmp     loc_14002B334
0x14002b4b5  mov     eax, [rbx+18h]
0x14002b4b8  test    eax, eax
0x14002b4ba  jz      loc_14002B234
0x14002b4c0  lea     rdx, [rax+rax*2]
0x14002b4c4  mov     ecx, 40h ; '@'
0x14002b4c9  shl     rdx, 3
0x14002b4cd  mov     r8d, 30455646h
0x14002b4d3  call    cs:__imp_ExAllocatePool2
0x14002b4da  nop     dword ptr [rax+rax+00h]
0x14002b4df  mov     [rbp+57h+P], rax
0x14002b4e3  mov     r14, rax
0x14002b4e6  test    rax, rax
0x14002b4e9  jz      loc_14002B334
0x14002b4ef  mov     rcx, [rbx]; Table
0x14002b4f2  mov     dl, 1; Restart
0x14002b4f4  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002b4fb  nop     dword ptr [rax+rax+00h]
0x14002b500  mov     esi, r13d
0x14002b503  jmp     short loc_14002B532
0x14002b505  movups  xmm0, xmmword ptr [rax]
0x14002b508  mov     ecx, esi
0x14002b50a  lea     rdx, [rcx+rcx*2]
0x14002b50e  movups  xmmword ptr [r14+rdx*8], xmm0
0x14002b513  movsd   xmm1, qword ptr [rax+10h]
0x14002b518  movsd   qword ptr [r14+rdx*8+10h], xmm1
0x14002b51f  xor     edx, edx; Restart
0x14002b521  mov     rcx, [rbx]; Table
0x14002b524  call    cs:__imp_RtlEnumerateGenericTableAvl
0x14002b52b  nop     dword ptr [rax+rax+00h]
0x14002b530  inc     esi
0x14002b532  test    rax, rax
0x14002b535  jnz     short loc_14002B505
0x14002b537  jmp     loc_14002B234
0x14002b53c  mov     esi, 0C000000Dh
0x14002b541  jmp     loc_14002B334
0x14002b546  cmp     [rbp+57h+NodeOrParent], r13
0x14002b54a  jnz     short loc_14002B579
0x14002b54c  mov     rcx, [rbx]; Table
0x14002b54f  lea     r9, [rbp+57h+SearchResult]; SearchResult
0x14002b553  lea     r8, [rbp+57h+NodeOrParent]; NodeOrParent
0x14002b557  mov     qword ptr [rbp+57h+Buffer], rdi
0x14002b55b  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14002b55f  mov     qword ptr [rbp+57h+Buffer+8], r13
0x14002b563  mov     dword ptr [rbp+57h+var_60], 4
0x14002b56a  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x14002b571  nop     dword ptr [rax+rax+00h]
0x14002b576  mov     rsi, rax
0x14002b579  mov     rcx, [rbp+57h+NodeOrParent]
0x14002b57d  lea     rdx, [rbp+57h+RestartKey]; RestartKey
0x14002b581  mov     [rbp+57h+RestartKey], rcx
0x14002b585  mov     rcx, [rbx]; Table
0x14002b588  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x14002b58f  nop     dword ptr [rax+rax+00h]
0x14002b594  mov     r13, [rsi+8]
0x14002b598  mov     r14, rax
0x14002b59b  mov     rax, [rsi]
0x14002b59e  cmp     rax, rdi
0x14002b5a1  jnz     loc_14002B62E
0x14002b5a7  cmp     rax, [rbx+28h]
0x14002b5ab  jnz     short loc_14002B5B9
0x14002b5ad  test    r14, r14
0x14002b5b0  jz      short loc_14002B5B9
0x14002b5b2  mov     rcx, [r14]
0x14002b5b5  mov     [rbx+28h], rcx
0x14002b5b9  mov     rax, [rbx+30h]
0x14002b5bd  cmp     [rsi+8], rax
0x14002b5c1  jnz     short loc_14002B603
0x14002b5c3  mov     rax, [rsi]
0x14002b5c6  lea     rdx, [rbp+57h+var_58]; Buffer
0x14002b5ca  mov     rcx, [rbx]; Table
0x14002b5cd  mov     [rbp+57h+var_50], rax
0x14002b5d1  mov     [rbp+57h+var_48], 5
0x14002b5d9  mov     [rbp+57h+var_58], 0
0x14002b5e1  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14002b5e8  nop     dword ptr [rax+rax+00h]
0x14002b5ed  test    rax, rax
0x14002b5f0  jnz     short loc_14002B5FB
0x14002b5f2  mov     rax, [rbp+57h+var_58]
0x14002b5f6  test    rax, rax
0x14002b5f9  jz      short loc_14002B603
0x14002b5fb  mov     rax, [rax+8]
0x14002b5ff  mov     [rbx+30h], rax
0x14002b603  mov     rdx, [rbp+57h+NodeOrParent]
0x14002b607  mov     rcx, [rbx]
0x14002b60a  call    cs:__imp_RtlDeleteElementGenericTableAvlEx
0x14002b611  nop     dword ptr [rax+rax+00h]
0x14002b616  add     dword ptr [rbx+18h], 0FFFFFFFFh
0x14002b61a  jnz     short loc_14002B641
0x14002b61c  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x14002b624  mov     qword ptr [rbx+30h], 0
0x14002b62c  jmp     short loc_14002B641
0x14002b62e  cmp     r13, rdi
0x14002b631  jbe     short loc_14002B641
0x14002b633  cmp     r13, [rbx+30h]
0x14002b637  jnz     short loc_14002B63D
0x14002b639  mov     [rbx+30h], rdi
0x14002b63d  mov     [rsi+8], rdi
0x14002b641  test    r14, r14
0x14002b644  jz      short loc_14002B6A1
0x14002b646  mov     rax, [rbp+57h+RestartKey]
0x14002b64a  mov     rdi, r13
0x14002b64d  mov     [rbp+57h+NodeOrParent], rax
0x14002b651  mov     eax, 2
0x14002b656  mov     qword ptr [rbp+57h+Buffer], r13
0x14002b65a  xor     r13d, r13d
0x14002b65d  mov     qword ptr [rbp+57h+Buffer+8], r14
0x14002b661  jmp     short loc_14002B687
0x14002b663  mov     rsi, r14
0x14002b666  test    r14, r14
0x14002b669  jz      loc_14002B394
0x14002b66f  mov     rdi, [r14]
0x14002b672  cmp     rdi, r12
0x14002b675  jnb     loc_14002B394
0x14002b67b  mov     r14, r13
0x14002b67e  mov     qword ptr [rbp+57h+Buffer+8], r13
  ... truncated ...
```
