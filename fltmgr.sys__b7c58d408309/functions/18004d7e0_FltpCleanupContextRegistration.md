# FltpCleanupContextRegistration

- ea: `0x18004d7e0`
- end: `0x18004da16`
- name: `FltpCleanupContextRegistration`
- size: `566`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18004c810`
- `0x18004d410`
- `0x18004f6c4`

## callees

- `0x18004d7e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18004d9f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004d9f2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d823`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d868`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d8ad`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d8f2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d937`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d97c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d9c1`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d823`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d868`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d8ad`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d8f2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d937`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d97c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18004d9c1`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d836`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d87b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d8c0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d905`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d94a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d98f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d9d4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d836`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d87b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d8c0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d905`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d94a`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d98f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18004d9d4`

## pseudocode

```c
void __fastcall FltpCleanupContextRegistration(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rdi
  __int64 v4; // rdi
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rdi
  __int64 v8; // rdi

  if ( *(_QWORD *)(a1 + 304) )
  {
    _mm_lfence();
    v2 = *(_QWORD *)(a1 + 312);
    for ( *(_QWORD *)(a1 + 312) = 0; v2; v2 = *(_QWORD *)(v2 + 16) )
    {
      if ( (*(_BYTE *)(v2 + 26) & 1) != 0 )
      {
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v2 + 64));
        ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(v2 + 192));
      }
    }
    v3 = *(_QWORD *)(a1 + 320);
    for ( *(_QWORD *)(a1 + 320) = 0; v3; v3 = *(_QWORD *)(v3 + 16) )
    {
      if ( (*(_BYTE *)(v3 + 26) & 1) != 0 )
      {
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 64));
        ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(v3 + 192));
      }
    }
    v4 = *(_QWORD *)(a1 + 328);
    for ( *(_QWORD *)(a1 + 328) = 0; v4; v4 = *(_QWORD *)(v4 + 16) )
    {
      if ( (*(_BYTE *)(v4 + 26) & 1) != 0 )
      {
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v4 + 64));
        ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(v4 + 192));
      }
    }
    v5 = *(_QWORD *)(a1 + 336);
    for ( *(_QWORD *)(a1 + 336) = 0; v5; v5 = *(_QWORD *)(v5 + 16) )
    {
      if ( (*(_BYTE *)(v5 + 26) & 1) != 0 )
      {
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v5 + 64));
        ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(v5 + 192));
      }
    }
    v6 = *(_QWORD *)(a1 + 344);
    for ( *(_QWORD *)(a1 + 344) = 0; v6; v6 = *(_QWORD *)(v6 + 16) )
    {
      if ( (*(_BYTE *)(v6 + 26) & 1) != 0 )
      {
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v6 + 64));
        ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(v6 + 192));
      }
    }
    v7 = *(_QWORD *)(a1 + 352);
    for ( *(_QWORD *)(a1 + 352) = 0; v7; v7 = *(_QWORD *)(v7 + 16) )
    {
      if ( (*(_BYTE *)(v7 + 26) & 1) != 0 )
      {
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v7 + 64));
        ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(v7 + 192));
      }
    }
    v8 = *(_QWORD *)(a1 + 360);
    for ( *(_QWORD *)(a1 + 360) = 0; v8; v8 = *(_QWORD *)(v8 + 16) )
    {
      if ( (*(_BYTE *)(v8 + 26) & 1) != 0 )
      {
        ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v8 + 64));
        ExDeletePagedLookasideList((PPAGED_LOOKASIDE_LIST)(v8 + 192));
      }
    }
    ExFreePoolWithTag(*(PVOID *)(a1 + 304), 0);
    *(_QWORD *)(a1 + 304) = 0;
  }
}

```

## disassembly

```asm
0x18004d7e0  push    rbx
0x18004d7e2  sub     rsp, 20h
0x18004d7e6  cmp     qword ptr [rcx+130h], 0
0x18004d7ee  mov     rbx, rcx
0x18004d7f1  jz      loc_18004DA0F
0x18004d7f7  mov     [rsp+28h+arg_0], rsi
0x18004d7fc  mov     [rsp+28h+arg_8], rdi
0x18004d801  lfence
0x18004d804  mov     rdi, [rcx+138h]
0x18004d80b  xor     esi, esi
0x18004d80d  mov     [rcx+138h], rsi
0x18004d814  test    rdi, rdi
0x18004d817  jz      short loc_18004D84B
0x18004d819  test    byte ptr [rdi+1Ah], 1
0x18004d81d  jz      short loc_18004D842
0x18004d81f  lea     rcx, [rdi+40h]; Lookaside
0x18004d823  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004d82a  nop     dword ptr [rax+rax+00h]
0x18004d82f  lea     rcx, [rdi+0C0h]; Lookaside
0x18004d836  call    cs:__imp_ExDeletePagedLookasideList
0x18004d83d  nop     dword ptr [rax+rax+00h]
0x18004d842  mov     rdi, [rdi+10h]
0x18004d846  test    rdi, rdi
0x18004d849  jnz     short loc_18004D819
0x18004d84b  mov     rdi, [rbx+140h]
0x18004d852  mov     [rbx+140h], rsi
0x18004d859  test    rdi, rdi
0x18004d85c  jz      short loc_18004D890
0x18004d85e  test    byte ptr [rdi+1Ah], 1
0x18004d862  jz      short loc_18004D887
0x18004d864  lea     rcx, [rdi+40h]; Lookaside
0x18004d868  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004d86f  nop     dword ptr [rax+rax+00h]
0x18004d874  lea     rcx, [rdi+0C0h]; Lookaside
0x18004d87b  call    cs:__imp_ExDeletePagedLookasideList
0x18004d882  nop     dword ptr [rax+rax+00h]
0x18004d887  mov     rdi, [rdi+10h]
0x18004d88b  test    rdi, rdi
0x18004d88e  jnz     short loc_18004D85E
0x18004d890  mov     rdi, [rbx+148h]
0x18004d897  mov     [rbx+148h], rsi
0x18004d89e  test    rdi, rdi
0x18004d8a1  jz      short loc_18004D8D5
0x18004d8a3  test    byte ptr [rdi+1Ah], 1
0x18004d8a7  jz      short loc_18004D8CC
0x18004d8a9  lea     rcx, [rdi+40h]; Lookaside
0x18004d8ad  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004d8b4  nop     dword ptr [rax+rax+00h]
0x18004d8b9  lea     rcx, [rdi+0C0h]; Lookaside
0x18004d8c0  call    cs:__imp_ExDeletePagedLookasideList
0x18004d8c7  nop     dword ptr [rax+rax+00h]
0x18004d8cc  mov     rdi, [rdi+10h]
0x18004d8d0  test    rdi, rdi
0x18004d8d3  jnz     short loc_18004D8A3
0x18004d8d5  mov     rdi, [rbx+150h]
0x18004d8dc  mov     [rbx+150h], rsi
0x18004d8e3  test    rdi, rdi
0x18004d8e6  jz      short loc_18004D91A
0x18004d8e8  test    byte ptr [rdi+1Ah], 1
0x18004d8ec  jz      short loc_18004D911
0x18004d8ee  lea     rcx, [rdi+40h]; Lookaside
0x18004d8f2  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004d8f9  nop     dword ptr [rax+rax+00h]
0x18004d8fe  lea     rcx, [rdi+0C0h]; Lookaside
0x18004d905  call    cs:__imp_ExDeletePagedLookasideList
0x18004d90c  nop     dword ptr [rax+rax+00h]
0x18004d911  mov     rdi, [rdi+10h]
0x18004d915  test    rdi, rdi
0x18004d918  jnz     short loc_18004D8E8
0x18004d91a  mov     rdi, [rbx+158h]
0x18004d921  mov     [rbx+158h], rsi
0x18004d928  test    rdi, rdi
0x18004d92b  jz      short loc_18004D95F
0x18004d92d  test    byte ptr [rdi+1Ah], 1
0x18004d931  jz      short loc_18004D956
0x18004d933  lea     rcx, [rdi+40h]; Lookaside
0x18004d937  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004d93e  nop     dword ptr [rax+rax+00h]
0x18004d943  lea     rcx, [rdi+0C0h]; Lookaside
0x18004d94a  call    cs:__imp_ExDeletePagedLookasideList
0x18004d951  nop     dword ptr [rax+rax+00h]
0x18004d956  mov     rdi, [rdi+10h]
0x18004d95a  test    rdi, rdi
0x18004d95d  jnz     short loc_18004D92D
0x18004d95f  mov     rdi, [rbx+160h]
0x18004d966  mov     [rbx+160h], rsi
0x18004d96d  test    rdi, rdi
0x18004d970  jz      short loc_18004D9A4
0x18004d972  test    byte ptr [rdi+1Ah], 1
0x18004d976  jz      short loc_18004D99B
0x18004d978  lea     rcx, [rdi+40h]; Lookaside
0x18004d97c  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004d983  nop     dword ptr [rax+rax+00h]
0x18004d988  lea     rcx, [rdi+0C0h]; Lookaside
0x18004d98f  call    cs:__imp_ExDeletePagedLookasideList
0x18004d996  nop     dword ptr [rax+rax+00h]
0x18004d99b  mov     rdi, [rdi+10h]
0x18004d99f  test    rdi, rdi
0x18004d9a2  jnz     short loc_18004D972
0x18004d9a4  mov     rdi, [rbx+168h]
0x18004d9ab  mov     [rbx+168h], rsi
0x18004d9b2  test    rdi, rdi
0x18004d9b5  jz      short loc_18004D9E9
0x18004d9b7  test    byte ptr [rdi+1Ah], 1
0x18004d9bb  jz      short loc_18004D9E0
0x18004d9bd  lea     rcx, [rdi+40h]; Lookaside
0x18004d9c1  call    cs:__imp_ExDeleteNPagedLookasideList
0x18004d9c8  nop     dword ptr [rax+rax+00h]
0x18004d9cd  lea     rcx, [rdi+0C0h]; Lookaside
0x18004d9d4  call    cs:__imp_ExDeletePagedLookasideList
0x18004d9db  nop     dword ptr [rax+rax+00h]
0x18004d9e0  mov     rdi, [rdi+10h]
0x18004d9e4  test    rdi, rdi
0x18004d9e7  jnz     short loc_18004D9B7
0x18004d9e9  mov     rcx, [rbx+130h]; P
0x18004d9f0  xor     edx, edx; Tag
0x18004d9f2  call    cs:__imp_ExFreePoolWithTag
0x18004d9f9  nop     dword ptr [rax+rax+00h]
0x18004d9fe  mov     rdi, [rsp+28h+arg_8]
0x18004da03  mov     [rbx+130h], rsi
0x18004da0a  mov     rsi, [rsp+28h+arg_0]
0x18004da0f  add     rsp, 20h
0x18004da13  pop     rbx
0x18004da14  retn
```
