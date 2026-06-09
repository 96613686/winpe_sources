# RtlpInsertAssemblyStorageMapEntry

- ea: `0x1800cf8f4`
- end: `0x1800cfa7c`
- name: `RtlpInsertAssemblyStorageMapEntry`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800cee30`

## callees

- `0x18001861c`
- `0x18001a080`
- `0x18001b984`
- `0x1800cf8f4`
- `0x180163a80`

## string_xrefs

- `0x1800cfa37`: `SXS: %s() bad parameters\nSXS:  Map                    : %p\nSXS:  AssemblyRosterIndex    : 0x%lx\nSXS:  Map->AssemblyCount     : 0x%lx\nSXS:  StorageLocation        : %p\nSXS:  StorageLocation->Length: 0x%x\nSXS:  StorageLocation->Buffer: %p\nSXS:  OpenDirectoryHandle    : %p\n`

## pseudocode

```c
__int64 __fastcall RtlpInsertAssemblyStorageMapEntry(__int64 a1, unsigned int a2, const void **a3, _QWORD *a4)
{
  __int64 v4; // rbp
  __int64 v8; // r8
  __int64 Heap_0; // rax
  signed __int64 v10; // rdi
  __int64 result; // rax
  const void *v12; // rax
  int v13; // edx
  int v14; // ecx

  v4 = a2;
  if ( !a1 || !a2 || a2 > *(_DWORD *)(a1 + 4) )
  {
    if ( a3 )
    {
LABEL_16:
      v12 = a3[1];
      v13 = *(unsigned __int16 *)a3;
      goto LABEL_19;
    }
LABEL_17:
    v12 = 0;
    v13 = 0;
LABEL_19:
    if ( a1 )
      v14 = *(_DWORD *)(a1 + 4);
    else
      v14 = 0;
    DbgPrintEx(
      51,
      0,
      "SXS: %s() bad parameters\n"
      "SXS:  Map                    : %p\n"
      "SXS:  AssemblyRosterIndex    : 0x%lx\n"
      "SXS:  Map->AssemblyCount     : 0x%lx\n"
      "SXS:  StorageLocation        : %p\n"
      "SXS:  StorageLocation->Length: 0x%x\n"
      "SXS:  StorageLocation->Buffer: %p\n"
      "SXS:  OpenDirectoryHandle    : %p\n",
      "RtlpInsertAssemblyStorageMapEntry",
      (const void *)a1,
      v4,
      v14,
      a3,
      v13,
      v12,
      a4);
    return 3221225485LL;
  }
  if ( !a3 )
    goto LABEL_17;
  if ( *(_WORD *)a3 < 2u || !a3[1] || !a4 )
    goto LABEL_16;
  v8 = *(unsigned __int16 *)a3;
  if ( (unsigned __int64)(v8 + 2) > 0xFFFE )
    return 3221225734LL;
  Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, v8 + 34);
  v10 = Heap_0;
  if ( !Heap_0 )
    return 3221225495LL;
  *(_DWORD *)Heap_0 = 0;
  *(_WORD *)(Heap_0 + 8) = *(_WORD *)a3;
  *(_QWORD *)(Heap_0 + 16) = Heap_0 + 32;
  *(_WORD *)(Heap_0 + 10) = *(_WORD *)a3 + 2;
  memmove((void *)(Heap_0 + 32), a3[1], *(unsigned __int16 *)a3);
  *(_WORD *)(*(_QWORD *)(v10 + 16) + 2 * ((unsigned __int64)*(unsigned __int16 *)(v10 + 8) >> 1)) = 0;
  *(_QWORD *)(v10 + 24) = *a4;
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(a1 + 8) + 8 * v4), v10, 0) )
  {
    v10 = 0;
    *a4 = 0;
  }
  result = 0;
  if ( v10 )
  {
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v10);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800cf8f4  push    rbx
0x1800cf8f6  push    rbp
0x1800cf8f7  push    rsi
0x1800cf8f8  push    rdi
0x1800cf8f9  push    r14
0x1800cf8fb  sub     rsp, 60h
0x1800cf8ff  mov     ebp, edx
0x1800cf901  mov     r14, r9
0x1800cf904  mov     rbx, r8
0x1800cf907  mov     rsi, rcx
0x1800cf90a  test    rcx, rcx
0x1800cf90d  jz      loc_1800CFA09
0x1800cf913  cmp     ebp, 1
0x1800cf916  jb      loc_1800CFA09
0x1800cf91c  cmp     ebp, [rcx+4]
0x1800cf91f  ja      loc_1800CFA09
0x1800cf925  test    rbx, rbx
0x1800cf928  jz      loc_1800CFA14
0x1800cf92e  cmp     word ptr [r8], 2
0x1800cf933  jb      loc_1800CFA0E
0x1800cf939  cmp     qword ptr [r8+8], 0
0x1800cf93e  jz      loc_1800CFA0E
0x1800cf944  test    r9, r9
0x1800cf947  jz      loc_1800CFA0E
0x1800cf94d  movzx   r8d, word ptr [r8]
0x1800cf951  lea     rax, [r8+2]
0x1800cf955  cmp     rax, 0FFFEh
0x1800cf95b  ja      loc_1800CFA75
0x1800cf961  mov     rcx, gs:60h
0x1800cf96a  add     r8, 22h ; '"'
0x1800cf96e  xor     edx, edx
0x1800cf970  mov     rcx, [rcx+30h]
0x1800cf974  call    RtlAllocateHeap_0
0x1800cf979  mov     rdi, rax
0x1800cf97c  test    rax, rax
0x1800cf97f  jz      loc_1800CFA6E
0x1800cf985  mov     dword ptr [rax], 0
0x1800cf98b  lea     rcx, [rdi+20h]; void *
0x1800cf98f  movzx   eax, word ptr [rbx]
0x1800cf992  mov     [rdi+8], ax
0x1800cf996  mov     [rdi+10h], rcx
0x1800cf99a  movzx   eax, word ptr [rbx]
0x1800cf99d  add     ax, 2
0x1800cf9a1  mov     [rdi+0Ah], ax
0x1800cf9a5  movzx   r8d, word ptr [rbx]; Size
0x1800cf9a9  mov     rdx, [rbx+8]; Src
0x1800cf9ad  call    memmove
0x1800cf9b2  movzx   edx, word ptr [rdi+8]
0x1800cf9b6  xor     eax, eax
0x1800cf9b8  mov     rcx, [rdi+10h]
0x1800cf9bc  shr     rdx, 1
0x1800cf9bf  mov     [rcx+rdx*2], ax
0x1800cf9c3  mov     rax, [r14]
0x1800cf9c6  mov     [rdi+18h], rax
0x1800cf9ca  xor     eax, eax
0x1800cf9cc  mov     rcx, [rsi+8]
0x1800cf9d0  lock cmpxchg [rcx+rbp*8], rdi
0x1800cf9d6  jnz     short loc_1800CF9DD
0x1800cf9d8  xor     edi, edi
0x1800cf9da  mov     [r14], rdi
0x1800cf9dd  xor     eax, eax
0x1800cf9df  test    rdi, rdi
0x1800cf9e2  jz      short loc_1800CF9FD
0x1800cf9e4  mov     rcx, gs:60h
0x1800cf9ed  mov     r8, rdi
0x1800cf9f0  xor     edx, edx
0x1800cf9f2  mov     rcx, [rcx+30h]
0x1800cf9f6  call    RtlFreeHeap_0
0x1800cf9fb  xor     eax, eax
0x1800cf9fd  add     rsp, 60h
0x1800cfa01  pop     r14
0x1800cfa03  pop     rdi
0x1800cfa04  pop     rsi
0x1800cfa05  pop     rbp
0x1800cfa06  pop     rbx
0x1800cfa07  retn
0x1800cfa09  test    rbx, rbx
0x1800cfa0c  jz      short loc_1800CFA14
0x1800cfa0e  mov     rax, [r8+8]
0x1800cfa12  jmp     short loc_1800CFA1B
0x1800cfa14  xor     eax, eax
0x1800cfa16  test    rbx, rbx
0x1800cfa19  jz      short loc_1800CFA6A
0x1800cfa1b  movzx   edx, word ptr [r8]
0x1800cfa1f  test    rsi, rsi
0x1800cfa22  jnz     short loc_1800CFA65
0x1800cfa24  xor     ecx, ecx
0x1800cfa26  mov     [rsp+88h+var_38], r14
0x1800cfa2b  lea     r9, aRtlpinsertasse; "RtlpInsertAssemblyStorageMapEntry"
0x1800cfa32  mov     [rsp+88h+var_40], rax
0x1800cfa37  lea     r8, aSxsSBadParamet_1; "SXS: %s() bad parameters\nSXS:  Map    "...
0x1800cfa3e  mov     [rsp+88h+var_48], edx
0x1800cfa42  xor     edx, edx
0x1800cfa44  mov     [rsp+88h+var_50], rbx
0x1800cfa49  mov     [rsp+88h+var_58], ecx
0x1800cfa4d  mov     [rsp+88h+var_60], ebp
0x1800cfa51  lea     ecx, [rdx+33h]
0x1800cfa54  mov     [rsp+88h+var_68], rsi
0x1800cfa59  call    DbgPrintEx
0x1800cfa5e  mov     eax, 0C000000Dh
0x1800cfa63  jmp     short loc_1800CF9FD
0x1800cfa65  mov     ecx, [rcx+4]
0x1800cfa68  jmp     short loc_1800CFA26
0x1800cfa6a  xor     edx, edx
0x1800cfa6c  jmp     short loc_1800CFA1F
0x1800cfa6e  mov     eax, 0C0000017h
0x1800cfa73  jmp     short loc_1800CF9FD
0x1800cfa75  mov     eax, 0C0000106h
0x1800cfa7a  jmp     short loc_1800CF9FD
```
