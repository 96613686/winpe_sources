# CallInProgressStarted

- ea: `0x1800266c0`
- end: `0x180026747`
- name: `CallInProgressStarted`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000f898`

## callees

- `0x1800266c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1800266db`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1800266db`
- `HAL!KeQueryPerformanceCounter` at `0x18002670b`
- `HAL!KeQueryPerformanceCounter` at `0x18002670b`

## pseudocode

```c
__int64 __fastcall CallInProgressStarted(__int64 a1)
{
  LARGE_INTEGER *v2; // rdi

  if ( !*(_QWORD *)(a1 + 24) )
  {
    **(_QWORD **)(a1 + 16) = 0;
    return 0;
  }
  **(_QWORD **)(a1 + 16) = ExAllocateFromLookasideListEx(&Lookaside);
  v2 = **(LARGE_INTEGER ***)(a1 + 16);
  if ( v2 )
  {
    *v2 = *(LARGE_INTEGER *)(a1 + 24);
    v2[1] = *(LARGE_INTEGER *)(a1 + 32);
    v2[2] = KeQueryPerformanceCounter(0);
    return 0;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x1800266c0  mov     [rsp+arg_0], rbx
0x1800266c5  push    rdi
0x1800266c6  sub     rsp, 20h
0x1800266ca  cmp     qword ptr [rcx+18h], 0
0x1800266cf  mov     rbx, rcx
0x1800266d2  jz      short loc_180026729
0x1800266d4  lea     rcx, Lookaside; Lookaside
0x1800266db  call    cs:__imp_ExAllocateFromLookasideListEx
0x1800266e2  nop     dword ptr [rax+rax+00h]
0x1800266e7  mov     rcx, [rbx+10h]
0x1800266eb  mov     [rcx], rax
0x1800266ee  mov     rax, [rbx+10h]
0x1800266f2  mov     rdi, [rax]
0x1800266f5  test    rdi, rdi
0x1800266f8  jz      short loc_180026736
0x1800266fa  mov     rax, [rbx+18h]
0x1800266fe  xor     ecx, ecx; PerformanceFrequency
0x180026700  mov     [rdi], rax
0x180026703  mov     rax, [rbx+20h]
0x180026707  mov     [rdi+8], rax
0x18002670b  call    cs:__imp_KeQueryPerformanceCounter
0x180026712  nop     dword ptr [rax+rax+00h]
0x180026717  mov     [rdi+10h], rax
0x18002671b  xor     eax, eax
0x18002671d  mov     rbx, [rsp+28h+arg_0]
0x180026722  add     rsp, 20h
0x180026726  pop     rdi
0x180026727  retn
0x180026729  mov     rax, [rcx+10h]
0x18002672d  mov     qword ptr [rax], 0
0x180026734  jmp     short loc_18002671B
0x180026736  mov     rbx, [rsp+28h+arg_0]
0x18002673b  mov     eax, 0C000009Ah
0x180026740  add     rsp, 20h
0x180026744  pop     rdi
0x180026745  retn
```
