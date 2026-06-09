# SymCrypt802_11SaeCustomDestroy

- ea: `0x1400599bc`
- end: `0x140059ad3`
- name: `SymCrypt802_11SaeCustomDestroy`
- size: `279`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140003598`
- `0x14001b440`
- `0x140023128`

## callees

- `0x14001d0dc`
- `0x14001d1a4`
- `0x14002c550`
- `0x1400599bc`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140059a17`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140059a69`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140059a17`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140059a69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059a28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059a7a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059a28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059a7a`

## pseudocode

```c
void __fastcall SymCrypt802_11SaeCustomDestroy(_QWORD *a1)
{
  __int64 v1; // rdx
  __int64 v3; // rsi
  __int64 v4; // rdi
  __int64 v5; // rdi
  __int64 v6; // rdi
  __int64 v7; // rdi

  v1 = a1[4];
  v3 = *a1;
  if ( v1 )
    SymCryptEcpointFree(*a1, v1);
  v4 = a1[3];
  if ( v4 )
  {
    SymCryptWipeAsm(a1[3], *(unsigned int *)(*(_QWORD *)(v3 + 624) + 16LL));
    v5 = v4 - *(unsigned int *)(v4 - 4);
    if ( v5 )
    {
      if ( *(_QWORD *)(v5 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 - 16), (PVOID)(v5 - 16));
      else
        ExFreePoolWithTag((PVOID)(v5 - 16), *(_DWORD *)(v5 - 16 + 8));
    }
  }
  v6 = a1[2];
  if ( v6 )
  {
    SymCryptWipeAsm(a1[2], *(unsigned int *)(*(_QWORD *)(v3 + 624) + 16LL));
    v7 = v6 - *(unsigned int *)(v6 - 4);
    if ( v7 )
    {
      if ( *(_QWORD *)(v7 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v7 - 16), (PVOID)(v7 - 16));
      else
        ExFreePoolWithTag((PVOID)(v7 - 16), *(_DWORD *)(v7 - 16 + 8));
    }
  }
  if ( v3 )
    SymCryptEcurveFree(v3);
  a1[4] = 0;
  a1[5] = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
}

```

## disassembly

```asm
0x1400599bc  mov     [rsp+arg_0], rbx
0x1400599c1  mov     [rsp+arg_8], rsi
0x1400599c6  push    rdi
0x1400599c7  sub     rsp, 20h
0x1400599cb  mov     rdx, [rcx+20h]
0x1400599cf  mov     rbx, rcx
0x1400599d2  mov     rsi, [rcx]
0x1400599d5  test    rdx, rdx
0x1400599d8  jz      short loc_1400599E2
0x1400599da  mov     rcx, rsi
0x1400599dd  call    SymCryptEcpointFree
0x1400599e2  mov     rdi, [rbx+18h]
0x1400599e6  test    rdi, rdi
0x1400599e9  jz      short loc_140059A34
0x1400599eb  mov     rax, [rsi+270h]
0x1400599f2  mov     rcx, rdi
0x1400599f5  mov     edx, [rax+10h]
0x1400599f8  call    SymCryptWipeAsm
0x1400599fd  mov     eax, [rdi-4]
0x140059a00  sub     rdi, rax
0x140059a03  jz      short loc_140059A34
0x140059a05  lea     rcx, [rdi-10h]; P
0x140059a09  mov     rax, [rcx]
0x140059a0c  test    rax, rax
0x140059a0f  jz      short loc_140059A25
0x140059a11  mov     rdx, rcx; Entry
0x140059a14  mov     rcx, rax; Lookaside
0x140059a17  call    cs:__imp_ExFreeToNPagedLookasideList
0x140059a1e  nop     dword ptr [rax+rax+00h]
0x140059a23  jmp     short loc_140059A34
0x140059a25  mov     edx, [rcx+8]; Tag
0x140059a28  call    cs:__imp_ExFreePoolWithTag
0x140059a2f  nop     dword ptr [rax+rax+00h]
0x140059a34  mov     rdi, [rbx+10h]
0x140059a38  test    rdi, rdi
0x140059a3b  jz      short loc_140059A86
0x140059a3d  mov     rax, [rsi+270h]
0x140059a44  mov     rcx, rdi
0x140059a47  mov     edx, [rax+10h]
0x140059a4a  call    SymCryptWipeAsm
0x140059a4f  mov     eax, [rdi-4]
0x140059a52  sub     rdi, rax
0x140059a55  jz      short loc_140059A86
0x140059a57  lea     rcx, [rdi-10h]; P
0x140059a5b  mov     rax, [rcx]
0x140059a5e  test    rax, rax
0x140059a61  jz      short loc_140059A77
0x140059a63  mov     rdx, rcx; Entry
0x140059a66  mov     rcx, rax; Lookaside
0x140059a69  call    cs:__imp_ExFreeToNPagedLookasideList
0x140059a70  nop     dword ptr [rax+rax+00h]
0x140059a75  jmp     short loc_140059A86
0x140059a77  mov     edx, [rcx+8]; Tag
0x140059a7a  call    cs:__imp_ExFreePoolWithTag
0x140059a81  nop     dword ptr [rax+rax+00h]
0x140059a86  test    rsi, rsi
0x140059a89  jz      short loc_140059A93
0x140059a8b  mov     rcx, rsi
0x140059a8e  call    SymCryptEcurveFree
0x140059a93  mov     rsi, [rsp+28h+arg_8]
0x140059a98  mov     qword ptr [rbx+20h], 0
0x140059aa0  mov     qword ptr [rbx+28h], 0
0x140059aa8  mov     qword ptr [rbx], 0
0x140059aaf  mov     qword ptr [rbx+8], 0
0x140059ab7  mov     qword ptr [rbx+10h], 0
0x140059abf  mov     qword ptr [rbx+18h], 0
0x140059ac7  mov     rbx, [rsp+28h+arg_0]
0x140059acc  add     rsp, 20h
0x140059ad0  pop     rdi
0x140059ad1  retn
```
