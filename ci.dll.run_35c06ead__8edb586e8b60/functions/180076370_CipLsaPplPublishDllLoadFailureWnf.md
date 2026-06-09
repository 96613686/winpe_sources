# CipLsaPplPublishDllLoadFailureWnf

- ea: `0x180076370`
- end: `0x180076430`
- name: `CipLsaPplPublishDllLoadFailureWnf`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800b4f38`

## callees

- `0x18002c200`
- `0x180076370`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180076395`
- `ntoskrnl!ExAllocatePool2` at `0x180076395`
- `ntoskrnl!ExFreePoolWithTag` at `0x180076411`
- `ntoskrnl!ExFreePoolWithTag` at `0x180076411`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800763fb`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800763fb`

## pseudocode

```c
__int64 __fastcall CipLsaPplPublishDllLoadFailureWnf(const void **a1)
{
  unsigned int v2; // esi
  _WORD *Pool2; // rdi
  __int64 v5; // r8
  unsigned int updated; // ebx

  v2 = *(unsigned __int16 *)a1 + 6;
  Pool2 = (_WORD *)ExAllocatePool2(258, v2, 1668499779);
  if ( !Pool2 )
    return 3221225495LL;
  Pool2[2] = *(_WORD *)a1;
  memmove(Pool2 + 3, a1[1], *(unsigned __int16 *)a1);
  v5 = 4096;
  if ( v2 < 0x1000 )
    v5 = v2;
  updated = ZwUpdateWnfStateData(&WNF_CI_LSAPPL_DLL_LOAD_FAILURE, Pool2, v5);
  ExFreePoolWithTag(Pool2, 0x63734943u);
  return updated;
}

```

## disassembly

```asm
0x180076370  mov     [rsp+arg_0], rbx
0x180076375  mov     [rsp+arg_8], rsi
0x18007637a  push    rdi
0x18007637b  sub     rsp, 40h
0x18007637f  movzx   esi, word ptr [rcx]
0x180076382  mov     rbx, rcx
0x180076385  add     esi, 6
0x180076388  mov     ecx, 102h
0x18007638d  mov     edx, esi
0x18007638f  mov     r8d, 63734943h
0x180076395  call    cs:__imp_ExAllocatePool2
0x18007639c  nop     dword ptr [rax+rax+00h]
0x1800763a1  mov     rdi, rax
0x1800763a4  test    rax, rax
0x1800763a7  jnz     short loc_1800763B0
0x1800763a9  mov     eax, 0C0000017h
0x1800763ae  jmp     short loc_18007641F
0x1800763b0  movzx   eax, word ptr [rbx]
0x1800763b3  lea     rcx, [rdi+6]; void *
0x1800763b7  mov     [rdi+4], ax
0x1800763bb  movzx   r8d, word ptr [rbx]; Size
0x1800763bf  mov     rdx, [rbx+8]; Src
0x1800763c3  call    memmove
0x1800763c8  mov     r8d, 1000h
0x1800763ce  mov     [rsp+48h+var_18], 0
0x1800763d6  cmp     esi, r8d
0x1800763d9  mov     [rsp+48h+var_20], 0
0x1800763e1  mov     rdx, rdi
0x1800763e4  mov     [rsp+48h+var_28], 0
0x1800763ed  cmovb   r8d, esi
0x1800763f1  lea     rcx, WNF_CI_LSAPPL_DLL_LOAD_FAILURE
0x1800763f8  xor     r9d, r9d
0x1800763fb  call    cs:__imp_ZwUpdateWnfStateData
0x180076402  nop     dword ptr [rax+rax+00h]
0x180076407  mov     edx, 63734943h; Tag
0x18007640c  mov     rcx, rdi; P
0x18007640f  mov     ebx, eax
0x180076411  call    cs:__imp_ExFreePoolWithTag
0x180076418  nop     dword ptr [rax+rax+00h]
0x18007641d  mov     eax, ebx
0x18007641f  mov     rbx, [rsp+48h+arg_0]
0x180076424  mov     rsi, [rsp+48h+arg_8]
0x180076429  add     rsp, 40h
0x18007642d  pop     rdi
0x18007642e  retn
```
