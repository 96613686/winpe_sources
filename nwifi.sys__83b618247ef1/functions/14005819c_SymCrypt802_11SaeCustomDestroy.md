# SymCrypt802_11SaeCustomDestroy

- ea: `0x14005819c`
- end: `0x1400582b3`
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
- `0x14002c2c0`
- `0x14005819c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400581f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140058249`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400581f7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140058249`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058208`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005825a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058208`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005825a`

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
0x14005819c  mov     [rsp+arg_0], rbx
0x1400581a1  mov     [rsp+arg_8], rsi
0x1400581a6  push    rdi
0x1400581a7  sub     rsp, 20h
0x1400581ab  mov     rdx, [rcx+20h]
0x1400581af  mov     rbx, rcx
0x1400581b2  mov     rsi, [rcx]
0x1400581b5  test    rdx, rdx
0x1400581b8  jz      short loc_1400581C2
0x1400581ba  mov     rcx, rsi
0x1400581bd  call    SymCryptEcpointFree
0x1400581c2  mov     rdi, [rbx+18h]
0x1400581c6  test    rdi, rdi
0x1400581c9  jz      short loc_140058214
0x1400581cb  mov     rax, [rsi+270h]
0x1400581d2  mov     rcx, rdi
0x1400581d5  mov     edx, [rax+10h]
0x1400581d8  call    SymCryptWipeAsm
0x1400581dd  mov     eax, [rdi-4]
0x1400581e0  sub     rdi, rax
0x1400581e3  jz      short loc_140058214
0x1400581e5  lea     rcx, [rdi-10h]; P
0x1400581e9  mov     rax, [rcx]
0x1400581ec  test    rax, rax
0x1400581ef  jz      short loc_140058205
0x1400581f1  mov     rdx, rcx; Entry
0x1400581f4  mov     rcx, rax; Lookaside
0x1400581f7  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400581fe  nop     dword ptr [rax+rax+00h]
0x140058203  jmp     short loc_140058214
0x140058205  mov     edx, [rcx+8]; Tag
0x140058208  call    cs:__imp_ExFreePoolWithTag
0x14005820f  nop     dword ptr [rax+rax+00h]
0x140058214  mov     rdi, [rbx+10h]
0x140058218  test    rdi, rdi
0x14005821b  jz      short loc_140058266
0x14005821d  mov     rax, [rsi+270h]
0x140058224  mov     rcx, rdi
0x140058227  mov     edx, [rax+10h]
0x14005822a  call    SymCryptWipeAsm
0x14005822f  mov     eax, [rdi-4]
0x140058232  sub     rdi, rax
0x140058235  jz      short loc_140058266
0x140058237  lea     rcx, [rdi-10h]; P
0x14005823b  mov     rax, [rcx]
0x14005823e  test    rax, rax
0x140058241  jz      short loc_140058257
0x140058243  mov     rdx, rcx; Entry
0x140058246  mov     rcx, rax; Lookaside
0x140058249  call    cs:__imp_ExFreeToNPagedLookasideList
0x140058250  nop     dword ptr [rax+rax+00h]
0x140058255  jmp     short loc_140058266
0x140058257  mov     edx, [rcx+8]; Tag
0x14005825a  call    cs:__imp_ExFreePoolWithTag
0x140058261  nop     dword ptr [rax+rax+00h]
0x140058266  test    rsi, rsi
0x140058269  jz      short loc_140058273
0x14005826b  mov     rcx, rsi
0x14005826e  call    SymCryptEcurveFree
0x140058273  mov     rsi, [rsp+28h+arg_8]
0x140058278  mov     qword ptr [rbx+20h], 0
0x140058280  mov     qword ptr [rbx+28h], 0
0x140058288  mov     qword ptr [rbx], 0
0x14005828f  mov     qword ptr [rbx+8], 0
0x140058297  mov     qword ptr [rbx+10h], 0
0x14005829f  mov     qword ptr [rbx+18h], 0
0x1400582a7  mov     rbx, [rsp+28h+arg_0]
0x1400582ac  add     rsp, 20h
0x1400582b0  pop     rdi
0x1400582b1  retn
```
