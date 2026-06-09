# chain_prepare_for_write_

- ea: `0x18000d7e0`
- end: `0x18000da37`
- name: `chain_prepare_for_write_`
- size: `599`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d290`
- `0x18000d370`

## callees

- `0x180004ad0`
- `0x180004c00`
- `0x18000d770`
- `0x18000d7e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000d8b0`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000d8b0`

## pseudocode

```c
__int64 __fastcall chain_prepare_for_write_(__int64 a1, int a2)
{
  __int64 *v2; // r8
  __int64 j; // rbx
  __int64 *i; // r9
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rsi
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  __int64 v13; // rax
  __int64 *v14; // rdx
  __int64 v15; // rax
  _QWORD *v16; // rdx
  _DWORD *v17; // r10
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 *v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // r8
  char v23; // dl
  _DWORD *v24; // rcx
  __int64 *k; // rax
  __int64 v26; // rcx

  v2 = *(__int64 **)(a1 + 16);
  j = 0;
  for ( i = v2; i; j += (unsigned int)(*(_DWORD *)(v6 + 8) + 4) )
  {
    v6 = *i;
    i = (__int64 *)i[2];
  }
  for ( ; v2[2]; v2 = (__int64 *)v2[2] )
    *(_DWORD *)(*v2 + 4) = 0;
  *(_DWORD *)(**(_QWORD **)(a1 + 24) + 4LL) = 1;
  if ( !a2 )
    goto LABEL_31;
  v7 = *(_QWORD *)(a1 + 56);
  if ( j < v7 )
  {
    v8 = *(_QWORD *)(a1 + 24);
    if ( **(_DWORD **)v8 == 1 )
    {
      *(_DWORD *)(*(_QWORD *)v8 + 8LL) += v7 - j;
LABEL_30:
      j = v7;
      goto LABEL_31;
    }
  }
  if ( j + 4 <= v7 )
  {
    v9 = FLAC__metadata_object_new(1);
    if ( v9 )
    {
      *(_DWORD *)(v9 + 8) = *(_DWORD *)(a1 + 56) - j - 4;
      v10 = calloc(1u, 0x18u);
      v11 = v10;
      if ( v10 )
      {
        *v10 = v9;
        v10[1] = 0;
        v10[2] = 0;
        *(_DWORD *)(v9 + 4) = 1;
        v13 = *(_QWORD *)(a1 + 24);
        if ( v13 )
          *(_DWORD *)(*(_QWORD *)v13 + 4LL) = 0;
        if ( *(_QWORD *)(a1 + 16) )
        {
          *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) = v11;
          v11[1] = *(_QWORD *)(a1 + 24);
        }
        else
        {
          *(_QWORD *)(a1 + 16) = v11;
        }
        ++*(_DWORD *)(a1 + 32);
        j = 0;
        v14 = *(__int64 **)(a1 + 16);
        for ( *(_QWORD *)(a1 + 24) = v11; v14; j += (unsigned int)(*(_DWORD *)(v15 + 8) + 4) )
        {
          v15 = *v14;
          v14 = (__int64 *)v14[2];
        }
        goto LABEL_31;
      }
      FLAC__metadata_object_delete((_QWORD *)v9);
    }
    *(_DWORD *)(a1 + 36) = 11;
    return 0;
  }
  if ( j > v7 )
  {
    v16 = *(_QWORD **)(a1 + 24);
    v17 = (_DWORD *)*v16;
    if ( *(_DWORD *)*v16 == 1 )
    {
      v18 = (unsigned int)v17[2];
      v19 = j - v7;
      if ( v18 + 4 == j - v7 )
      {
        chain_delete_node_(a1);
        v20 = *(__int64 **)(a1 + 16);
        for ( j = 0; v20; j += (unsigned int)(*(_DWORD *)(v21 + 8) + 4) )
        {
          v21 = *v20;
          v20 = (__int64 *)v20[2];
        }
        goto LABEL_31;
      }
      if ( v18 >= v19 )
      {
        v17[2] = v18 - v19;
        goto LABEL_30;
      }
    }
  }
LABEL_31:
  v22 = *(_QWORD **)(a1 + 16);
  if ( !v22 )
    return j;
  v23 = FLAC__STREAM_METADATA_LENGTH_LEN;
  while ( 1 )
  {
    v24 = (_DWORD *)*v22;
    if ( *(_DWORD *)(*v22 + 8LL) >= (unsigned int)(1 << v23) )
      break;
LABEL_38:
    v22 = (_QWORD *)v22[2];
    if ( !v22 )
      return j;
  }
  if ( *v24 == 1 )
  {
    j = 0;
    v24[2] = (1 << v23) - 1;
    for ( k = *(__int64 **)(a1 + 16); k; j += (unsigned int)(*(_DWORD *)(v26 + 8) + 4) )
    {
      v26 = *k;
      k = (__int64 *)k[2];
    }
    v23 = FLAC__STREAM_METADATA_LENGTH_LEN;
    goto LABEL_38;
  }
  *(_DWORD *)(a1 + 36) = 5;
  return 0;
}

```

## disassembly

```asm
0x18000d7e0  mov     [rsp+arg_8], rbx
0x18000d7e5  mov     [rsp+arg_10], rbp
0x18000d7ea  push    rdi
0x18000d7eb  sub     rsp, 20h
0x18000d7ef  mov     r8, [rcx+10h]
0x18000d7f3  xor     ebp, ebp
0x18000d7f5  mov     rdi, rcx
0x18000d7f8  mov     ebx, ebp
0x18000d7fa  mov     r9, r8
0x18000d7fd  test    r8, r8
0x18000d800  jz      short loc_18000D825
0x18000d802  nop     dword ptr [rax+00h]
0x18000d806  nop     word ptr [rax+rax+00000000h]
0x18000d810  mov     rax, [r9]
0x18000d813  mov     r9, [r9+10h]
0x18000d817  mov     eax, [rax+8]
0x18000d81a  add     eax, 4
0x18000d81d  add     rbx, rax
0x18000d820  test    r9, r9
0x18000d823  jnz     short loc_18000D810
0x18000d825  cmp     [r8+10h], rbp
0x18000d829  jz      short loc_18000D840
0x18000d82b  nop     dword ptr [rax+rax+00h]
0x18000d830  mov     rax, [r8]
0x18000d833  mov     [rax+4], ebp
0x18000d836  mov     r8, [r8+10h]
0x18000d83a  cmp     [r8+10h], rbp
0x18000d83e  jnz     short loc_18000D830
0x18000d840  mov     rax, [rcx+18h]
0x18000d844  mov     [rsp+28h+arg_0], rsi
0x18000d849  mov     rcx, [rax]
0x18000d84c  mov     dword ptr [rcx+4], 1
0x18000d853  test    edx, edx
0x18000d855  jz      loc_18000D9A6
0x18000d85b  mov     rcx, [rdi+38h]
0x18000d85f  cmp     rbx, rcx
0x18000d862  jge     short loc_18000D87C
0x18000d864  mov     rax, [rdi+18h]
0x18000d868  mov     rdx, [rax]
0x18000d86b  cmp     dword ptr [rdx], 1
0x18000d86e  jnz     short loc_18000D87C
0x18000d870  mov     eax, ecx
0x18000d872  sub     eax, ebx
0x18000d874  add     [rdx+8], eax
0x18000d877  jmp     loc_18000D9A3
0x18000d87c  lea     rax, [rbx+4]
0x18000d880  cmp     rax, rcx
0x18000d883  jg      loc_18000D947
0x18000d889  mov     ecx, 1
0x18000d88e  call    FLAC__metadata_object_new
0x18000d893  mov     rsi, rax
0x18000d896  test    rax, rax
0x18000d899  jz      short loc_18000D8C6
0x18000d89b  mov     eax, [rdi+38h]
0x18000d89e  mov     edx, 18h; Size
0x18000d8a3  sub     eax, ebx
0x18000d8a5  mov     ecx, 1; Count
0x18000d8aa  sub     eax, 4
0x18000d8ad  mov     [rsi+8], eax
0x18000d8b0  call    cs:__imp_calloc
0x18000d8b6  mov     rcx, rax
0x18000d8b9  test    rax, rax
0x18000d8bc  jnz     short loc_18000D8D4
0x18000d8be  mov     rcx, rsi
0x18000d8c1  call    FLAC__metadata_object_delete
0x18000d8c6  mov     dword ptr [rdi+24h], 0Bh
0x18000d8cd  xor     eax, eax
0x18000d8cf  jmp     loc_18000DA17
0x18000d8d4  mov     [rax], rsi
0x18000d8d7  mov     [rax+8], rbp
0x18000d8db  mov     [rax+10h], rbp
0x18000d8df  mov     dword ptr [rsi+4], 1
0x18000d8e6  mov     rax, [rdi+18h]
0x18000d8ea  test    rax, rax
0x18000d8ed  jz      short loc_18000D8F5
0x18000d8ef  mov     rax, [rax]
0x18000d8f2  mov     [rax+4], ebp
0x18000d8f5  cmp     [rdi+10h], rbp
0x18000d8f9  jnz     short loc_18000D901
0x18000d8fb  mov     [rdi+10h], rcx
0x18000d8ff  jmp     short loc_18000D911
0x18000d901  mov     rax, [rdi+18h]
0x18000d905  mov     [rax+10h], rcx
0x18000d909  mov     rax, [rdi+18h]
0x18000d90d  mov     [rcx+8], rax
0x18000d911  inc     dword ptr [rdi+20h]
0x18000d914  mov     rbx, rbp
0x18000d917  mov     rdx, [rdi+10h]
0x18000d91b  mov     [rdi+18h], rcx
0x18000d91f  test    rdx, rdx
0x18000d922  jz      loc_18000D9A6
0x18000d928  nop     dword ptr [rax+rax+00000000h]
0x18000d930  mov     rax, [rdx]
0x18000d933  mov     rdx, [rdx+10h]
0x18000d937  mov     eax, [rax+8]
0x18000d93a  add     eax, 4
0x18000d93d  add     rbx, rax
0x18000d940  test    rdx, rdx
0x18000d943  jnz     short loc_18000D930
0x18000d945  jmp     short loc_18000D9A6
0x18000d947  cmp     rbx, rcx
0x18000d94a  jle     short loc_18000D9A6
0x18000d94c  mov     rdx, [rdi+18h]
0x18000d950  mov     r10, [rdx]
0x18000d953  cmp     dword ptr [r10], 1
0x18000d957  jnz     short loc_18000D9A6
0x18000d959  mov     r8d, [r10+8]
0x18000d95d  mov     r9, rbx
0x18000d960  sub     r9, rcx
0x18000d963  lea     rax, [r8+4]
0x18000d967  cmp     rax, r9
0x18000d96a  jnz     short loc_18000D997
0x18000d96c  mov     rcx, rdi
0x18000d96f  call    chain_delete_node_
0x18000d974  mov     rdx, [rdi+10h]
0x18000d978  mov     rbx, rbp
0x18000d97b  test    rdx, rdx
0x18000d97e  jz      short loc_18000D9A6
0x18000d980  mov     rax, [rdx]
0x18000d983  mov     rdx, [rdx+10h]
0x18000d987  mov     eax, [rax+8]
0x18000d98a  add     eax, 4
0x18000d98d  add     rbx, rax
0x18000d990  test    rdx, rdx
0x18000d993  jnz     short loc_18000D980
0x18000d995  jmp     short loc_18000D9A6
0x18000d997  cmp     r8, r9
0x18000d99a  jl      short loc_18000D9A6
0x18000d99c  sub     r8d, r9d
0x18000d99f  mov     [r10+8], r8d
0x18000d9a3  mov     rbx, rcx
0x18000d9a6  mov     r8, [rdi+10h]
0x18000d9aa  test    r8, r8
0x18000d9ad  jz      short loc_18000DA14
0x18000d9af  mov     edx, cs:FLAC__STREAM_METADATA_LENGTH_LEN
0x18000d9b5  nop     word ptr [rax+rax+00000000h]
0x18000d9c0  mov     ecx, edx
0x18000d9c2  mov     eax, 1
0x18000d9c7  shl     eax, cl
0x18000d9c9  mov     rcx, [r8]
0x18000d9cc  cmp     [rcx+8], eax
0x18000d9cf  jb      short loc_18000DA0B
0x18000d9d1  cmp     dword ptr [rcx], 1
0x18000d9d4  jnz     short loc_18000DA2C
0x18000d9d6  dec     eax
0x18000d9d8  mov     rbx, rbp
0x18000d9db  mov     [rcx+8], eax
0x18000d9de  mov     rax, [rdi+10h]
0x18000d9e2  test    rax, rax
0x18000d9e5  jz      short loc_18000DA05
0x18000d9e7  nop     word ptr [rax+rax+00000000h]
0x18000d9f0  mov     rcx, [rax]
0x18000d9f3  mov     rax, [rax+10h]
0x18000d9f7  mov     ecx, [rcx+8]
0x18000d9fa  add     ecx, 4
0x18000d9fd  add     rbx, rcx
0x18000da00  test    rax, rax
0x18000da03  jnz     short loc_18000D9F0
0x18000da05  mov     edx, cs:FLAC__STREAM_METADATA_LENGTH_LEN
0x18000da0b  mov     r8, [r8+10h]
0x18000da0f  test    r8, r8
0x18000da12  jnz     short loc_18000D9C0
0x18000da14  mov     rax, rbx
0x18000da17  mov     rsi, [rsp+28h+arg_0]
0x18000da1c  mov     rbx, [rsp+28h+arg_8]
0x18000da21  mov     rbp, [rsp+28h+arg_10]
0x18000da26  add     rsp, 20h
0x18000da2a  pop     rdi
0x18000da2b  retn
0x18000da2c  mov     dword ptr [rdi+24h], 5
0x18000da33  xor     eax, eax
0x18000da35  jmp     short loc_18000DA17
```
