# CipPublishWhqlOnlyBlockWNF

- ea: `0x18006bc5c`
- end: `0x18006bd1c`
- name: `CipPublishWhqlOnlyBlockWNF`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18006b4c8`

## callees

- `0x18002c040`
- `0x18006bc5c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18006bc81`
- `ntoskrnl!ExAllocatePool2` at `0x18006bc81`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006bcfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006bcfd`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x18006bce7`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x18006bce7`

## pseudocode

```c
__int64 __fastcall CipPublishWhqlOnlyBlockWNF(const void **a1)
{
  unsigned int v2; // esi
  _WORD *Pool2; // rdi
  __int64 v5; // r8
  unsigned int updated; // ebx

  v2 = *(unsigned __int16 *)a1 + 22;
  Pool2 = (_WORD *)ExAllocatePool2(258, v2, 1668499779);
  if ( !Pool2 )
    return 3221225495LL;
  Pool2[10] = *(_WORD *)a1;
  memmove(Pool2 + 11, a1[1], *(unsigned __int16 *)a1);
  v5 = 4096;
  if ( v2 < 0x1000 )
    v5 = v2;
  updated = ZwUpdateWnfStateData(&WNF_CI_BLOCKED_DRIVER_WHQLONLY, Pool2, v5);
  ExFreePoolWithTag(Pool2, 0x63734943u);
  return updated;
}

```

## disassembly

```asm
0x18006bc5c  mov     [rsp+arg_0], rbx
0x18006bc61  mov     [rsp+arg_8], rsi
0x18006bc66  push    rdi
0x18006bc67  sub     rsp, 40h
0x18006bc6b  movzx   esi, word ptr [rcx]
0x18006bc6e  mov     rbx, rcx
0x18006bc71  add     esi, 16h
0x18006bc74  mov     ecx, 102h
0x18006bc79  mov     edx, esi
0x18006bc7b  mov     r8d, 63734943h
0x18006bc81  call    cs:__imp_ExAllocatePool2
0x18006bc88  nop     dword ptr [rax+rax+00h]
0x18006bc8d  mov     rdi, rax
0x18006bc90  test    rax, rax
0x18006bc93  jnz     short loc_18006BC9C
0x18006bc95  mov     eax, 0C0000017h
0x18006bc9a  jmp     short loc_18006BD0B
0x18006bc9c  movzx   eax, word ptr [rbx]
0x18006bc9f  lea     rcx, [rdi+16h]; void *
0x18006bca3  mov     [rdi+14h], ax
0x18006bca7  movzx   r8d, word ptr [rbx]; Size
0x18006bcab  mov     rdx, [rbx+8]; Src
0x18006bcaf  call    memmove
0x18006bcb4  mov     r8d, 1000h
0x18006bcba  mov     [rsp+48h+var_18], 0
0x18006bcc2  cmp     esi, r8d
0x18006bcc5  mov     [rsp+48h+var_20], 0
0x18006bccd  mov     rdx, rdi
0x18006bcd0  mov     [rsp+48h+var_28], 0
0x18006bcd9  cmovb   r8d, esi
0x18006bcdd  lea     rcx, WNF_CI_BLOCKED_DRIVER_WHQLONLY
0x18006bce4  xor     r9d, r9d
0x18006bce7  call    cs:__imp_ZwUpdateWnfStateData
0x18006bcee  nop     dword ptr [rax+rax+00h]
0x18006bcf3  mov     edx, 63734943h; Tag
0x18006bcf8  mov     rcx, rdi; P
0x18006bcfb  mov     ebx, eax
0x18006bcfd  call    cs:__imp_ExFreePoolWithTag
0x18006bd04  nop     dword ptr [rax+rax+00h]
0x18006bd09  mov     eax, ebx
0x18006bd0b  mov     rbx, [rsp+48h+arg_0]
0x18006bd10  mov     rsi, [rsp+48h+arg_8]
0x18006bd15  add     rsp, 40h
0x18006bd19  pop     rdi
0x18006bd1a  retn
```
