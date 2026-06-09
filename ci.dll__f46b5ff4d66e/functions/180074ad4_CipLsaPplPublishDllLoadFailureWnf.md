# CipLsaPplPublishDllLoadFailureWnf

- ea: `0x180074ad4`
- end: `0x180074b94`
- name: `CipLsaPplPublishDllLoadFailureWnf`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1800b3c18`

## callees

- `0x18002c040`
- `0x180074ad4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180074af9`
- `ntoskrnl!ExAllocatePool2` at `0x180074af9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180074b75`
- `ntoskrnl!ExFreePoolWithTag` at `0x180074b75`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180074b5f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180074b5f`

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
0x180074ad4  mov     [rsp+arg_0], rbx
0x180074ad9  mov     [rsp+arg_8], rsi
0x180074ade  push    rdi
0x180074adf  sub     rsp, 40h
0x180074ae3  movzx   esi, word ptr [rcx]
0x180074ae6  mov     rbx, rcx
0x180074ae9  add     esi, 6
0x180074aec  mov     ecx, 102h
0x180074af1  mov     edx, esi
0x180074af3  mov     r8d, 63734943h
0x180074af9  call    cs:__imp_ExAllocatePool2
0x180074b00  nop     dword ptr [rax+rax+00h]
0x180074b05  mov     rdi, rax
0x180074b08  test    rax, rax
0x180074b0b  jnz     short loc_180074B14
0x180074b0d  mov     eax, 0C0000017h
0x180074b12  jmp     short loc_180074B83
0x180074b14  movzx   eax, word ptr [rbx]
0x180074b17  lea     rcx, [rdi+6]; void *
0x180074b1b  mov     [rdi+4], ax
0x180074b1f  movzx   r8d, word ptr [rbx]; Size
0x180074b23  mov     rdx, [rbx+8]; Src
0x180074b27  call    memmove
0x180074b2c  mov     r8d, 1000h
0x180074b32  mov     [rsp+48h+var_18], 0
0x180074b3a  cmp     esi, r8d
0x180074b3d  mov     [rsp+48h+var_20], 0
0x180074b45  mov     rdx, rdi
0x180074b48  mov     [rsp+48h+var_28], 0
0x180074b51  cmovb   r8d, esi
0x180074b55  lea     rcx, WNF_CI_LSAPPL_DLL_LOAD_FAILURE
0x180074b5c  xor     r9d, r9d
0x180074b5f  call    cs:__imp_ZwUpdateWnfStateData
0x180074b66  nop     dword ptr [rax+rax+00h]
0x180074b6b  mov     edx, 63734943h; Tag
0x180074b70  mov     rcx, rdi; P
0x180074b73  mov     ebx, eax
0x180074b75  call    cs:__imp_ExFreePoolWithTag
0x180074b7c  nop     dword ptr [rax+rax+00h]
0x180074b81  mov     eax, ebx
0x180074b83  mov     rbx, [rsp+48h+arg_0]
0x180074b88  mov     rsi, [rsp+48h+arg_8]
0x180074b8d  add     rsp, 40h
0x180074b91  pop     rdi
0x180074b92  retn
```
