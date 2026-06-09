# CipHvciPublishIncompatibleImageWNF

- ea: `0x180075dc4`
- end: `0x180075e94`
- name: `CipHvciPublishIncompatibleImageWNF`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180075658`
- `0x1800757dc`

## callees

- `0x18002c040`
- `0x180075dc4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180075df0`
- `ntoskrnl!ExAllocatePool2` at `0x180075df0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075e78`
- `ntoskrnl!ExFreePoolWithTag` at `0x180075e78`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180075e62`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180075e62`

## pseudocode

```c
__int64 __fastcall CipHvciPublishIncompatibleImageWNF(const void **a1, _DWORD *a2, int a3, int a4)
{
  unsigned int v7; // esi
  __int64 Pool2; // rax
  void *v10; // rdi
  unsigned int updated; // ebx
  __int64 v12; // r8

  v7 = *(unsigned __int16 *)a1 + 14;
  Pool2 = ExAllocatePool2(258, v7, 1668499779);
  v10 = (void *)Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = *a2;
    *(_DWORD *)(Pool2 + 4) = a3;
    *(_DWORD *)(Pool2 + 8) = a4;
    *(_WORD *)(Pool2 + 12) = *(_WORD *)a1;
    memmove((void *)(Pool2 + 14), a1[1], *(unsigned __int16 *)a1);
    v12 = 4096;
    if ( v7 < 0x1000 )
      v12 = v7;
    updated = ZwUpdateWnfStateData(&WNF_CI_HVCI_IMAGE_INCOMPATIBLE, v10, v12);
    ExFreePoolWithTag(v10, 0x63734943u);
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return updated;
}

```

## disassembly

```asm
0x180075dc4  push    rbx
0x180075dc6  push    rbp
0x180075dc7  push    rsi
0x180075dc8  push    rdi
0x180075dc9  push    r14
0x180075dcb  push    r15
0x180075dcd  sub     rsp, 48h
0x180075dd1  movzx   esi, word ptr [rcx]
0x180075dd4  mov     r14d, r8d
0x180075dd7  mov     r15, rdx
0x180075dda  mov     rbx, rcx
0x180075ddd  add     esi, 0Eh
0x180075de0  mov     ecx, 102h
0x180075de5  mov     edx, esi
0x180075de7  mov     r8d, 63734943h
0x180075ded  mov     ebp, r9d
0x180075df0  call    cs:__imp_ExAllocatePool2
0x180075df7  nop     dword ptr [rax+rax+00h]
0x180075dfc  mov     rdi, rax
0x180075dff  test    rax, rax
0x180075e02  jnz     short loc_180075E0B
0x180075e04  mov     ebx, 0C0000017h
0x180075e09  jmp     short loc_180075E84
0x180075e0b  mov     eax, [r15]
0x180075e0e  lea     rcx, [rdi+0Eh]; void *
0x180075e12  mov     [rdi], eax
0x180075e14  mov     [rdi+4], r14d
0x180075e18  mov     [rdi+8], ebp
0x180075e1b  movzx   eax, word ptr [rbx]
0x180075e1e  mov     [rdi+0Ch], ax
0x180075e22  movzx   r8d, word ptr [rbx]; Size
0x180075e26  mov     rdx, [rbx+8]; Src
0x180075e2a  call    memmove
0x180075e2f  mov     r8d, 1000h
0x180075e35  mov     [rsp+78h+var_48], 0
0x180075e3d  cmp     esi, r8d
0x180075e40  mov     [rsp+78h+var_50], 0
0x180075e48  mov     rdx, rdi
0x180075e4b  mov     [rsp+78h+var_58], 0
0x180075e54  cmovb   r8d, esi
0x180075e58  lea     rcx, WNF_CI_HVCI_IMAGE_INCOMPATIBLE
0x180075e5f  xor     r9d, r9d
0x180075e62  call    cs:__imp_ZwUpdateWnfStateData
0x180075e69  nop     dword ptr [rax+rax+00h]
0x180075e6e  mov     edx, 63734943h; Tag
0x180075e73  mov     rcx, rdi; P
0x180075e76  mov     ebx, eax
0x180075e78  call    cs:__imp_ExFreePoolWithTag
0x180075e7f  nop     dword ptr [rax+rax+00h]
0x180075e84  mov     eax, ebx
0x180075e86  add     rsp, 48h
0x180075e8a  pop     r15
0x180075e8c  pop     r14
0x180075e8e  pop     rdi
0x180075e8f  pop     rsi
0x180075e90  pop     rbp
0x180075e91  pop     rbx
0x180075e92  retn
```
