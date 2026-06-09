# CreateBucket

- ea: `0x14000b088`
- end: `0x14000b13e`
- name: `CreateBucket`
- size: `182`
- prototype: `__int64 __fastcall(_WORD *, const wchar_t *, _WORD *, void *, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ba74`

## callees

- `0x14000b088`
- `0x14000b144`
- `0x14000c554`

## pseudocode

```c
__int64 __fastcall CreateBucket(_WORD *a1, const wchar_t *a2, _WORD *a3, void *a4, void *a5, int a6)
{
  int v10; // ebx

  if ( !wcscmp_0(a2, L"system") )
  {
    v10 = 1;
  }
  else if ( !wcscmp_0(a2, L"user") )
  {
    v10 = 2;
  }
  else if ( !wcscmp_0(a2, L"other") )
  {
    v10 = 3;
  }
  else if ( !wcscmp_0(a2, L"inboxapp") )
  {
    v10 = 4;
  }
  else
  {
    v10 = 0;
    if ( !wcscmp_0(a2, L"otherapp") )
      v10 = 5;
  }
  return CreateBucket(a1, v10, a3, a4, a5, a6, 0);
}

```

## disassembly

```asm
0x14000b088  push    rbx
0x14000b08a  push    rbp
0x14000b08b  push    rsi
0x14000b08c  push    rdi
0x14000b08d  push    r14
0x14000b08f  sub     rsp, 40h
0x14000b093  mov     rdi, rdx
0x14000b096  mov     r14, rcx
0x14000b099  mov     rcx, rdi; String1
0x14000b09c  lea     rdx, aSystem; "system"
0x14000b0a3  mov     rsi, r9
0x14000b0a6  mov     rbp, r8
0x14000b0a9  call    wcscmp_0
0x14000b0ae  test    eax, eax
0x14000b0b0  jnz     short loc_14000B0B7
0x14000b0b2  lea     ebx, [rax+1]
0x14000b0b5  jmp     short loc_14000B118
0x14000b0b7  lea     rdx, aUser; "user"
0x14000b0be  mov     rcx, rdi; String1
0x14000b0c1  call    wcscmp_0
0x14000b0c6  test    eax, eax
0x14000b0c8  jnz     short loc_14000B0CF
0x14000b0ca  lea     ebx, [rax+2]
0x14000b0cd  jmp     short loc_14000B118
0x14000b0cf  lea     rdx, aOther; "other"
0x14000b0d6  mov     rcx, rdi; String1
0x14000b0d9  call    wcscmp_0
0x14000b0de  test    eax, eax
0x14000b0e0  jnz     short loc_14000B0E7
0x14000b0e2  lea     ebx, [rax+3]
0x14000b0e5  jmp     short loc_14000B118
0x14000b0e7  lea     rdx, aInboxapp; "inboxapp"
0x14000b0ee  mov     rcx, rdi; String1
0x14000b0f1  call    wcscmp_0
0x14000b0f6  test    eax, eax
0x14000b0f8  jnz     short loc_14000B0FF
0x14000b0fa  lea     ebx, [rax+4]
0x14000b0fd  jmp     short loc_14000B118
0x14000b0ff  lea     rdx, aOtherapp; "otherapp"
0x14000b106  mov     rcx, rdi; String1
0x14000b109  xor     ebx, ebx
0x14000b10b  call    wcscmp_0
0x14000b110  test    eax, eax
0x14000b112  lea     ecx, [rbx+5]
0x14000b115  cmovz   ebx, ecx
0x14000b118  mov     r9, rsi
0x14000b11b  mov     [rsp+68h+arg_30], 0
0x14000b127  mov     r8, rbp
0x14000b12a  mov     edx, ebx
0x14000b12c  mov     rcx, r14
0x14000b12f  add     rsp, 40h
0x14000b133  pop     r14
0x14000b135  pop     rdi
0x14000b136  pop     rsi
0x14000b137  pop     rbp
0x14000b138  pop     rbx
0x14000b139  jmp     ?CreateBucket@@YAJPEBGW4RULE_CATEGORY@@000W4RULE_TYPE@@PEAPEAU_RULE_BUCKET@@@Z; CreateBucket(ushort const *,RULE_CATEGORY,ushort const *,ushort const *,ushort const *,RULE_TYPE,_RULE_BUCKET * *)
```
