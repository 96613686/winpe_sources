# CallInProgressStarted

- ea: `0x180026710`
- end: `0x180026797`
- name: `CallInProgressStarted`
- size: `135`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000f900`

## callees

- `0x180026710`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x18002672b`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x18002672b`
- `HAL!KeQueryPerformanceCounter` at `0x18002675b`
- `HAL!KeQueryPerformanceCounter` at `0x18002675b`

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
0x180026710  mov     [rsp+arg_0], rbx
0x180026715  push    rdi
0x180026716  sub     rsp, 20h
0x18002671a  cmp     qword ptr [rcx+18h], 0
0x18002671f  mov     rbx, rcx
0x180026722  jz      short loc_180026779
0x180026724  lea     rcx, Lookaside; Lookaside
0x18002672b  call    cs:__imp_ExAllocateFromLookasideListEx
0x180026732  nop     dword ptr [rax+rax+00h]
0x180026737  mov     rcx, [rbx+10h]
0x18002673b  mov     [rcx], rax
0x18002673e  mov     rax, [rbx+10h]
0x180026742  mov     rdi, [rax]
0x180026745  test    rdi, rdi
0x180026748  jz      short loc_180026786
0x18002674a  mov     rax, [rbx+18h]
0x18002674e  xor     ecx, ecx; PerformanceFrequency
0x180026750  mov     [rdi], rax
0x180026753  mov     rax, [rbx+20h]
0x180026757  mov     [rdi+8], rax
0x18002675b  call    cs:__imp_KeQueryPerformanceCounter
0x180026762  nop     dword ptr [rax+rax+00h]
0x180026767  mov     [rdi+10h], rax
0x18002676b  xor     eax, eax
0x18002676d  mov     rbx, [rsp+28h+arg_0]
0x180026772  add     rsp, 20h
0x180026776  pop     rdi
0x180026777  retn
0x180026779  mov     rax, [rcx+10h]
0x18002677d  mov     qword ptr [rax], 0
0x180026784  jmp     short loc_18002676B
0x180026786  mov     rbx, [rsp+28h+arg_0]
0x18002678b  mov     eax, 0C000009Ah
0x180026790  add     rsp, 20h
0x180026794  pop     rdi
0x180026795  retn
```
