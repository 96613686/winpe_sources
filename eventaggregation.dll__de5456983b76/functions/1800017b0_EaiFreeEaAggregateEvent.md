# EaiFreeEaAggregateEvent

- ea: `0x1800017b0`
- end: `0x18000188e`
- name: `EaiFreeEaAggregateEvent`
- size: `222`
- prototype: `__int64 __fastcall(PVOID **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800016c0`
- `0x180001730`

## callees

- `0x1800017b0`
- `0x180001970`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800017ef`
- `ntdll!RtlFreeHeap` at `0x180001847`
- `ntdll!RtlFreeHeap` at `0x180001863`
- `ntdll!RtlFreeHeap` at `0x1800017ef`
- `ntdll!RtlFreeHeap` at `0x180001847`
- `ntdll!RtlFreeHeap` at `0x180001863`

## pseudocode

```c
__int64 __fastcall EaiFreeEaAggregateEvent(PVOID **a1)
{
  PVOID *v2; // rbx
  unsigned int v3; // esi
  PVOID v4; // rdx
  __int64 result; // rax
  _QWORD v6[7]; // [rsp+20h] [rbp-38h] BYREF

  if ( !a1 )
    return 3221225485LL;
  v2 = *a1;
  v3 = 0;
  if ( **a1 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, **a1);
    *v2 = 0;
  }
  v4 = v2[1];
  if ( v4 )
  {
    v6[0] = 0;
    v6[1] = EaiAggregationConditionNextChild;
    v6[2] = 0;
    v6[4] = EaiFreeAggregationConditionVisitNode;
    v6[3] = 0;
    v3 = EapTreeTraverse(v6, v4);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2[1]);
    v2[1] = 0;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  result = v3;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800017b0  push    rdi
0x1800017b2  sub     rsp, 50h
0x1800017b6  mov     rdi, rcx
0x1800017b9  test    rcx, rcx
0x1800017bc  jz      loc_180001883
0x1800017c2  mov     [rsp+58h+arg_0], rbx
0x1800017c7  mov     rbx, [rcx]
0x1800017ca  mov     [rsp+58h+arg_8], rbp
0x1800017cf  xor     ebp, ebp
0x1800017d1  mov     [rsp+58h+arg_10], rsi
0x1800017d6  mov     esi, ebp
0x1800017d8  mov     r8, [rbx]; P
0x1800017db  test    r8, r8
0x1800017de  jz      short loc_1800017F8
0x1800017e0  mov     rcx, gs:60h
0x1800017e9  xor     edx, edx; Flags
0x1800017eb  mov     rcx, [rcx+30h]; HeapHandle
0x1800017ef  call    cs:__imp_RtlFreeHeap
0x1800017f5  mov     [rbx], rbp
0x1800017f8  mov     rdx, [rbx+8]
0x1800017fc  test    rdx, rdx
0x1800017ff  jz      short loc_180001851
0x180001801  lea     rax, EaiAggregationConditionNextChild
0x180001808  mov     [rsp+58h+var_38], rbp
0x18000180d  mov     [rsp+58h+var_30], rax
0x180001812  lea     rcx, [rsp+58h+var_38]
0x180001817  lea     rax, EaiFreeAggregationConditionVisitNode
0x18000181e  mov     [rsp+58h+var_28], rbp
0x180001823  mov     [rsp+58h+var_18], rax
0x180001828  mov     [rsp+58h+var_20], rbp
0x18000182d  call    EapTreeTraverse
0x180001832  mov     rcx, gs:60h
0x18000183b  xor     edx, edx; Flags
0x18000183d  mov     r8, [rbx+8]; P
0x180001841  mov     esi, eax
0x180001843  mov     rcx, [rcx+30h]; HeapHandle
0x180001847  call    cs:__imp_RtlFreeHeap
0x18000184d  mov     [rbx+8], rbp
0x180001851  mov     rcx, gs:60h
0x18000185a  mov     r8, rbx; P
0x18000185d  xor     edx, edx; Flags
0x18000185f  mov     rcx, [rcx+30h]; HeapHandle
0x180001863  call    cs:__imp_RtlFreeHeap
0x180001869  mov     rbx, [rsp+58h+arg_0]
0x18000186e  mov     eax, esi
0x180001870  mov     rsi, [rsp+58h+arg_10]
0x180001875  mov     [rdi], rbp
0x180001878  mov     rbp, [rsp+58h+arg_8]
0x18000187d  add     rsp, 50h
0x180001881  pop     rdi
0x180001882  retn
0x180001883  mov     eax, 0C000000Dh
0x180001888  add     rsp, 50h
0x18000188c  pop     rdi
0x18000188d  retn
```
