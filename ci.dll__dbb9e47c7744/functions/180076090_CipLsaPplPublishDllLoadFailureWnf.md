# CipLsaPplPublishDllLoadFailureWnf

- ea: `0x180076090`
- end: `0x180076150`
- name: `CipLsaPplPublishDllLoadFailureWnf`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800b5098`

## callees

- `0x18002c080`
- `0x180076090`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800760b5`
- `ntoskrnl!ExAllocatePool2` at `0x1800760b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x180076131`
- `ntoskrnl!ExFreePoolWithTag` at `0x180076131`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x18007611b`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x18007611b`

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
0x180076090  mov     [rsp+arg_0], rbx
0x180076095  mov     [rsp+arg_8], rsi
0x18007609a  push    rdi
0x18007609b  sub     rsp, 40h
0x18007609f  movzx   esi, word ptr [rcx]
0x1800760a2  mov     rbx, rcx
0x1800760a5  add     esi, 6
0x1800760a8  mov     ecx, 102h
0x1800760ad  mov     edx, esi
0x1800760af  mov     r8d, 63734943h
0x1800760b5  call    cs:__imp_ExAllocatePool2
0x1800760bc  nop     dword ptr [rax+rax+00h]
0x1800760c1  mov     rdi, rax
0x1800760c4  test    rax, rax
0x1800760c7  jnz     short loc_1800760D0
0x1800760c9  mov     eax, 0C0000017h
0x1800760ce  jmp     short loc_18007613F
0x1800760d0  movzx   eax, word ptr [rbx]
0x1800760d3  lea     rcx, [rdi+6]; void *
0x1800760d7  mov     [rdi+4], ax
0x1800760db  movzx   r8d, word ptr [rbx]; Size
0x1800760df  mov     rdx, [rbx+8]; Src
0x1800760e3  call    memmove
0x1800760e8  mov     r8d, 1000h
0x1800760ee  mov     [rsp+48h+var_18], 0
0x1800760f6  cmp     esi, r8d
0x1800760f9  mov     [rsp+48h+var_20], 0
0x180076101  mov     rdx, rdi
0x180076104  mov     [rsp+48h+var_28], 0
0x18007610d  cmovb   r8d, esi
0x180076111  lea     rcx, WNF_CI_LSAPPL_DLL_LOAD_FAILURE
0x180076118  xor     r9d, r9d
0x18007611b  call    cs:__imp_ZwUpdateWnfStateData
0x180076122  nop     dword ptr [rax+rax+00h]
0x180076127  mov     edx, 63734943h; Tag
0x18007612c  mov     rcx, rdi; P
0x18007612f  mov     ebx, eax
0x180076131  call    cs:__imp_ExFreePoolWithTag
0x180076138  nop     dword ptr [rax+rax+00h]
0x18007613d  mov     eax, ebx
0x18007613f  mov     rbx, [rsp+48h+arg_0]
0x180076144  mov     rsi, [rsp+48h+arg_8]
0x180076149  add     rsp, 40h
0x18007614d  pop     rdi
0x18007614e  retn
```
