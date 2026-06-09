# PsmQueryBackgroundActivationType

- ea: `0x180001010`
- end: `0x18000118f`
- name: `PsmQueryBackgroundActivationType`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007ec0`

## callees

- `0x180001010`

## import_xrefs

- `ntdll!NtQuerySecurityAttributesToken` at `0x18000109a`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180001182`
- `ntdll!NtQuerySecurityAttributesToken` at `0x18000109a`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180001182`
- `ntdll!RtlFreeHeap` at `0x1800010d9`
- `ntdll!RtlFreeHeap` at `0x180001131`
- `ntdll!RtlFreeHeap` at `0x1800010d9`
- `ntdll!RtlFreeHeap` at `0x180001131`
- `ntdll!RtlAllocateHeap` at `0x180001056`
- `ntdll!RtlAllocateHeap` at `0x18000114b`
- `ntdll!RtlAllocateHeap` at `0x180001056`
- `ntdll!RtlAllocateHeap` at `0x18000114b`

## pseudocode

```c
__int64 __fastcall PsmQueryBackgroundActivationType(__int64 a1, signed __int32 *a2)
{
  PVOID Heap; // rbp
  signed __int32 v5; // r14d
  unsigned int v6; // esi
  PVOID v8; // rax
  SIZE_T Size; // [rsp+50h] [rbp+8h] BYREF

  LODWORD(Size) = 0;
  if ( a1 == -4 && PsmpProcessActivationType )
  {
    *a2 = PsmpProcessActivationType;
    return 0;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x58u);
  if ( !Heap )
    return 3221225626LL;
  v5 = 1;
  v6 = NtQuerySecurityAttributesToken(a1, &qword_18000B000, 1, Heap, 88, &Size);
  if ( v6 == -1073741789 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    v8 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)Size);
    Heap = v8;
    if ( !v8 )
      return 3221225626LL;
    v6 = NtQuerySecurityAttributesToken(a1, &qword_18000B000, 1, v8, Size, &Size);
  }
  if ( v6 == -1073741275 )
    goto LABEL_6;
  if ( !v6 )
  {
    if ( *((_DWORD *)Heap + 1) )
    {
      v5 = **(_DWORD **)(*((_QWORD *)Heap + 1) + 32LL);
      goto LABEL_7;
    }
LABEL_6:
    v6 = 0;
LABEL_7:
    if ( a1 == -4 )
      _InterlockedCompareExchange(&PsmpProcessActivationType, v5, 0);
    *a2 = v5;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return v6;
}

```

## disassembly

```asm
0x180001010  push    rbx
0x180001012  push    rdi
0x180001013  sub     rsp, 38h
0x180001017  mov     dword ptr [rsp+48h+Size], 0
0x18000101f  mov     rdi, rdx
0x180001022  mov     rbx, rcx
0x180001025  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x180001029  jnz     short loc_180001039
0x18000102b  mov     eax, cs:PsmpProcessActivationType
0x180001031  test    eax, eax
0x180001033  jnz     loc_18000110D
0x180001039  mov     rcx, gs:60h
0x180001042  mov     edx, 8; Flags
0x180001047  mov     r8d, 58h ; 'X'; Size
0x18000104d  mov     [rsp+48h+arg_8], rbp
0x180001052  mov     rcx, [rcx+30h]; HeapHandle
0x180001056  call    cs:__imp_RtlAllocateHeap
0x18000105c  mov     rbp, rax
0x18000105f  test    rax, rax
0x180001062  jz      loc_180001118
0x180001068  lea     rax, [rsp+48h+Size]
0x18000106d  mov     [rsp+48h+arg_10], rsi
0x180001072  mov     [rsp+48h+var_20], rax
0x180001077  lea     rdx, qword_18000B000
0x18000107e  mov     [rsp+48h+var_18], r14
0x180001083  mov     r9, rbp
0x180001086  mov     r14d, 1
0x18000108c  mov     [rsp+48h+var_28], 58h ; 'X'
0x180001094  mov     r8d, r14d
0x180001097  mov     rcx, rbx
0x18000109a  call    cs:__imp_NtQuerySecurityAttributesToken
0x1800010a0  mov     esi, eax
0x1800010a2  cmp     eax, 0C0000023h
0x1800010a7  jz      short loc_18000111F
0x1800010a9  cmp     esi, 0C0000225h
0x1800010af  jnz     short loc_1800010F7
0x1800010b1  xor     esi, esi
0x1800010b3  cmp     rbx, 0FFFFFFFFFFFFFFFCh
0x1800010b7  jnz     short loc_1800010C4
0x1800010b9  xor     eax, eax
0x1800010bb  lock cmpxchg cs:PsmpProcessActivationType, r14d
0x1800010c4  mov     [rdi], r14d
0x1800010c7  mov     rcx, gs:60h
0x1800010d0  mov     r8, rbp; P
0x1800010d3  xor     edx, edx; Flags
0x1800010d5  mov     rcx, [rcx+30h]; HeapHandle
0x1800010d9  call    cs:__imp_RtlFreeHeap
0x1800010df  mov     eax, esi
0x1800010e1  mov     rsi, [rsp+48h+arg_10]
0x1800010e6  mov     r14, [rsp+48h+var_18]
0x1800010eb  mov     rbp, [rsp+48h+arg_8]
0x1800010f0  add     rsp, 38h
0x1800010f4  pop     rdi
0x1800010f5  pop     rbx
0x1800010f6  retn
0x1800010f7  test    esi, esi
0x1800010f9  jnz     short loc_1800010C7
0x1800010fb  cmp     [rbp+4], esi
0x1800010fe  jz      short loc_1800010B1
0x180001100  mov     rax, [rbp+8]
0x180001104  mov     rcx, [rax+20h]
0x180001108  mov     r14d, [rcx]
0x18000110b  jmp     short loc_1800010B3
0x18000110d  mov     [rdx], eax
0x18000110f  xor     eax, eax
0x180001111  add     rsp, 38h
0x180001115  pop     rdi
0x180001116  pop     rbx
0x180001117  retn
0x180001118  mov     eax, 0C000009Ah
0x18000111d  jmp     short loc_1800010EB
0x18000111f  mov     rcx, gs:60h
0x180001128  mov     r8, rbp; P
0x18000112b  xor     edx, edx; Flags
0x18000112d  mov     rcx, [rcx+30h]; HeapHandle
0x180001131  call    cs:__imp_RtlFreeHeap
0x180001137  mov     rcx, gs:60h
0x180001140  xor     edx, edx; Flags
0x180001142  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x180001147  mov     rcx, [rcx+30h]; HeapHandle
0x18000114b  call    cs:__imp_RtlAllocateHeap
0x180001151  mov     rbp, rax
0x180001154  test    rax, rax
0x180001157  jnz     short loc_180001160
0x180001159  mov     eax, 0C000009Ah
0x18000115e  jmp     short loc_1800010E1
0x180001160  lea     rax, [rsp+48h+Size]
0x180001165  mov     r9, rbp
0x180001168  mov     [rsp+48h+var_20], rax
0x18000116d  lea     rdx, qword_18000B000
0x180001174  mov     eax, dword ptr [rsp+48h+Size]
0x180001178  mov     r8d, r14d
0x18000117b  mov     rcx, rbx
0x18000117e  mov     [rsp+48h+var_28], eax
0x180001182  call    cs:__imp_NtQuerySecurityAttributesToken
0x180001188  mov     esi, eax
0x18000118a  jmp     loc_1800010A9
```
