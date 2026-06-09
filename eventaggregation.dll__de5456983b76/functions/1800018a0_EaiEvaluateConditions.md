# EaiEvaluateConditions

- ea: `0x1800018a0`
- end: `0x18000195d`
- name: `EaiEvaluateConditions`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005cc0`
- `0x180008010`

## callees

- `0x1800018a0`
- `0x180001970`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180001943`
- `ntdll!RtlFreeHeap` at `0x180001943`

## pseudocode

```c
char __fastcall EaiEvaluateConditions(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rdx
  char v3; // bl
  PVOID P[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v6; // [rsp+30h] [rbp-38h]
  _QWORD v7[5]; // [rsp+38h] [rbp-30h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  *(_OWORD *)P = 0;
  v6 = 0;
  if ( !*(_QWORD *)(v1 + 8) )
    return 1;
  v6 = a1;
  v7[0] = P;
  P[0] = 0;
  LODWORD(P[1]) = 0;
  v2 = *(_QWORD *)(v1 + 8);
  v7[1] = EaiAggregationConditionNextChild;
  v7[2] = 0;
  v7[3] = 0;
  v3 = 1;
  v7[4] = EaiEvaluateAggregationConditionVisitNode;
  if ( (int)EapTreeTraverse(v7, v2) >= 0 )
  {
    v3 = *((_BYTE *)P[0] + WORD1(P[1]) - 1);
    --WORD1(P[1]);
  }
  if ( P[0] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
  return v3;
}

```

## disassembly

```asm
0x1800018a0  mov     r11, rsp
0x1800018a3  sub     rsp, 68h
0x1800018a7  mov     rdx, [rcx+38h]
0x1800018ab  xor     eax, eax
0x1800018ad  xorps   xmm0, xmm0
0x1800018b0  movups  xmmword ptr [rsp+68h+P], xmm0
0x1800018b5  mov     [r11-38h], rax
0x1800018b9  cmp     [rdx+8], rax
0x1800018bd  jz      loc_180001956
0x1800018c3  mov     [r11-38h], rcx
0x1800018c7  lea     rax, [r11-48h]
0x1800018cb  xor     ecx, ecx
0x1800018cd  mov     [r11-30h], rax
0x1800018d1  mov     [r11-48h], rcx
0x1800018d5  lea     rax, EaiAggregationConditionNextChild
0x1800018dc  mov     dword ptr [rsp+68h+P+8], ecx
0x1800018e0  mov     rdx, [rdx+8]
0x1800018e4  mov     [r11-28h], rax
0x1800018e8  lea     rax, EaiEvaluateAggregationConditionVisitNode
0x1800018ef  mov     [r11-20h], rcx
0x1800018f3  mov     [r11-18h], rcx
0x1800018f7  lea     rcx, [r11-30h]
0x1800018fb  mov     [r11-8], rbx
0x1800018ff  mov     bl, 1
0x180001901  mov     [r11-10h], rax
0x180001905  call    EapTreeTraverse
0x18000190a  mov     rcx, [rsp+68h+P]
0x18000190f  test    eax, eax
0x180001911  js      short loc_18000192A
0x180001913  movzx   eax, word ptr [rsp+68h+P+0Ah]
0x180001918  mov     edx, 0FFFFh
0x18000191d  movzx   ebx, byte ptr [rax+rcx-1]
0x180001922  add     ax, dx
0x180001925  mov     word ptr [rsp+68h+P+0Ah], ax
0x18000192a  test    rcx, rcx
0x18000192d  jz      short loc_180001949
0x18000192f  mov     rcx, gs:60h
0x180001938  xor     edx, edx; Flags
0x18000193a  mov     r8, [rsp+68h+P]; P
0x18000193f  mov     rcx, [rcx+30h]; HeapHandle
0x180001943  call    cs:__imp_RtlFreeHeap
0x180001949  movzx   eax, bl
0x18000194c  mov     rbx, [rsp+68h+var_8]
0x180001951  add     rsp, 68h
0x180001955  retn
0x180001956  mov     al, 1
0x180001958  add     rsp, 68h
0x18000195c  retn
```
