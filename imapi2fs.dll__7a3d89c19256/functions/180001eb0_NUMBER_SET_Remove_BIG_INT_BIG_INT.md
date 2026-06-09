# NUMBER_SET::Remove(BIG_INT,BIG_INT)

- ea: `0x180001eb0`
- end: `0x180001fdf`
- name: `?Remove@NUMBER_SET@@QEAAEVBIG_INT@@0@Z`
- size: `303`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18005ef94`
- `0x18006f488`

## callees

- `0x180001eb0`

## import_xrefs

- `ntdll!RtlInsertElementGenericTableAvl` at `0x180001fc8`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180001fc8`
- `ntdll!RtlDeleteElementGenericTableAvlEx` at `0x180001f49`
- `ntdll!RtlDeleteElementGenericTableAvlEx` at `0x180001f49`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x180001f23`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x180001f23`

## pseudocode

```c
__int64 __fastcall NUMBER_SET::Remove(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // rdi
  unsigned __int8 v6; // r14
  _QWORD *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  _QWORD Buffer[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+30h] [rbp-38h]
  __int64 v13; // [rsp+38h] [rbp-30h]
  TABLE_SEARCH_RESULT SearchResult; // [rsp+78h] [rbp+10h] BYREF
  PVOID NodeOrParent; // [rsp+80h] [rbp+18h] BYREF

  v3 = a2;
  v5 = a2 + a3;
  v6 = 1;
  while ( v3 < v5 )
  {
    Buffer[1] = NUMBER_EXTENT_cd;
    Buffer[0] = &MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable';
    NodeOrParent = 0;
    SearchResult = TableEmptyTree;
    v12 = v3;
    v13 = v3;
    v7 = RtlLookupElementGenericTableFullAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer, &NodeOrParent, &SearchResult);
    if ( SearchResult == TableFoundNode )
    {
      v8 = v7[3];
      v9 = v7[2];
      if ( v9 == v8 )
      {
        RtlDeleteElementGenericTableAvlEx(a1 + 16, NodeOrParent);
      }
      else if ( v9 == v3 )
      {
        v7[2] = v3 + 1;
      }
      else if ( v8 == v3 )
      {
        v7[3] = v3 - 1;
      }
      else
      {
        v12 = v3 + 1;
        v13 = v7[3];
        v7[3] = v3 - 1;
        if ( !RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer, 0x20u, 0) )
          goto LABEL_16;
      }
      --*(_QWORD *)(a1 + 120);
    }
    if ( v6 )
    {
      v6 = 1;
      goto LABEL_9;
    }
LABEL_16:
    v6 = 0;
LABEL_9:
    ++v3;
  }
  return v6;
}

```

## disassembly

```asm
0x180001eb0  mov     [rsp+arg_18], rbx
0x180001eb5  push    rbp
0x180001eb6  push    rdi
0x180001eb7  push    r12
0x180001eb9  push    r14
0x180001ebb  push    r15
0x180001ebd  sub     rsp, 40h
0x180001ec1  mov     rbx, rdx
0x180001ec4  mov     [rsp+68h+arg_0], rsi
0x180001ec9  mov     rbp, rcx
0x180001ecc  lea     rdi, [rdx+r8]
0x180001ed0  mov     r14b, 1
0x180001ed3  lea     r12, ??_7MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE@@6B@; const MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable'
0x180001eda  xor     r15d, r15d
0x180001edd  nop     dword ptr [rax]
0x180001ee0  cmp     rbx, rdi
0x180001ee3  jge     short loc_180001F60
0x180001ee5  mov     rax, cs:?NUMBER_EXTENT_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const NUMBER_EXTENT_cd
0x180001eec  lea     r9, [rsp+68h+SearchResult]; SearchResult
0x180001ef1  lea     r8, [rsp+68h+NodeOrParent]; NodeOrParent
0x180001ef9  mov     [rsp+68h+var_40], rax
0x180001efe  lea     rdx, [rsp+68h+Buffer]; Buffer
0x180001f03  mov     [rsp+68h+Buffer], r12
0x180001f08  lea     rcx, [rbp+10h]; Table
0x180001f0c  mov     [rsp+68h+NodeOrParent], r15
0x180001f14  mov     [rsp+68h+SearchResult], r15d
0x180001f19  mov     [rsp+68h+var_38], rbx
0x180001f1e  mov     [rsp+68h+var_30], rbx
0x180001f23  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x180001f29  cmp     [rsp+68h+SearchResult], 1
0x180001f2e  jnz     short loc_180001F53
0x180001f30  mov     r8, [rax+18h]
0x180001f34  mov     rdx, [rax+10h]
0x180001f38  cmp     rdx, r8
0x180001f3b  jnz     short loc_180001F7E
0x180001f3d  mov     rdx, [rsp+68h+NodeOrParent]
0x180001f45  lea     rcx, [rbp+10h]
0x180001f49  call    cs:__imp_RtlDeleteElementGenericTableAvlEx
0x180001f4f  dec     qword ptr [rbp+78h]
0x180001f53  test    r14b, r14b
0x180001f56  jz      short loc_180001FD7
0x180001f58  mov     r14b, 1
0x180001f5b  inc     rbx
0x180001f5e  jmp     short loc_180001EE0
0x180001f60  mov     rsi, [rsp+68h+arg_0]
0x180001f65  movzx   eax, r14b
0x180001f69  mov     rbx, [rsp+68h+arg_18]
0x180001f71  add     rsp, 40h
0x180001f75  pop     r15
0x180001f77  pop     r14
0x180001f79  pop     r12
0x180001f7b  pop     rdi
0x180001f7c  pop     rbp
0x180001f7d  retn
0x180001f7e  cmp     rdx, rbx
0x180001f81  jnz     short loc_180001F8D
0x180001f83  lea     rcx, [rbx+1]
0x180001f87  mov     [rax+10h], rcx
0x180001f8b  jmp     short loc_180001F4F
0x180001f8d  cmp     r8, rbx
0x180001f90  jnz     short loc_180001F9C
0x180001f92  lea     rcx, [rbx-1]
0x180001f96  mov     [rax+18h], rcx
0x180001f9a  jmp     short loc_180001F4F
0x180001f9c  lea     rcx, [rbx+1]
0x180001fa0  xor     r9d, r9d; NewElement
0x180001fa3  mov     [rsp+68h+var_38], rcx
0x180001fa8  lea     rdx, [rsp+68h+Buffer]; Buffer
0x180001fad  mov     rcx, [rax+18h]
0x180001fb1  mov     r8d, 20h ; ' '; BufferSize
0x180001fb7  mov     [rsp+68h+var_30], rcx
0x180001fbc  lea     rcx, [rbx-1]
0x180001fc0  mov     [rax+18h], rcx
0x180001fc4  lea     rcx, [rbp+10h]; Table
0x180001fc8  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180001fce  test    rax, rax
0x180001fd1  jnz     loc_180001F4F
0x180001fd7  xor     r14b, r14b
0x180001fda  jmp     loc_180001F5B
```
