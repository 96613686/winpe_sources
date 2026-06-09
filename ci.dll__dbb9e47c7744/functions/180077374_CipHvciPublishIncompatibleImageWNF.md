# CipHvciPublishIncompatibleImageWNF

- ea: `0x180077374`
- end: `0x180077444`
- name: `CipHvciPublishIncompatibleImageWNF`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180076c08`
- `0x180076d8c`

## callees

- `0x18002c080`
- `0x180077374`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800773a0`
- `ntoskrnl!ExAllocatePool2` at `0x1800773a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180077428`
- `ntoskrnl!ExFreePoolWithTag` at `0x180077428`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180077412`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x180077412`

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
0x180077374  push    rbx
0x180077376  push    rbp
0x180077377  push    rsi
0x180077378  push    rdi
0x180077379  push    r14
0x18007737b  push    r15
0x18007737d  sub     rsp, 48h
0x180077381  movzx   esi, word ptr [rcx]
0x180077384  mov     r14d, r8d
0x180077387  mov     r15, rdx
0x18007738a  mov     rbx, rcx
0x18007738d  add     esi, 0Eh
0x180077390  mov     ecx, 102h
0x180077395  mov     edx, esi
0x180077397  mov     r8d, 63734943h
0x18007739d  mov     ebp, r9d
0x1800773a0  call    cs:__imp_ExAllocatePool2
0x1800773a7  nop     dword ptr [rax+rax+00h]
0x1800773ac  mov     rdi, rax
0x1800773af  test    rax, rax
0x1800773b2  jnz     short loc_1800773BB
0x1800773b4  mov     ebx, 0C0000017h
0x1800773b9  jmp     short loc_180077434
0x1800773bb  mov     eax, [r15]
0x1800773be  lea     rcx, [rdi+0Eh]; void *
0x1800773c2  mov     [rdi], eax
0x1800773c4  mov     [rdi+4], r14d
0x1800773c8  mov     [rdi+8], ebp
0x1800773cb  movzx   eax, word ptr [rbx]
0x1800773ce  mov     [rdi+0Ch], ax
0x1800773d2  movzx   r8d, word ptr [rbx]; Size
0x1800773d6  mov     rdx, [rbx+8]; Src
0x1800773da  call    memmove
0x1800773df  mov     r8d, 1000h
0x1800773e5  mov     [rsp+78h+var_48], 0
0x1800773ed  cmp     esi, r8d
0x1800773f0  mov     [rsp+78h+var_50], 0
0x1800773f8  mov     rdx, rdi
0x1800773fb  mov     [rsp+78h+var_58], 0
0x180077404  cmovb   r8d, esi
0x180077408  lea     rcx, WNF_CI_HVCI_IMAGE_INCOMPATIBLE
0x18007740f  xor     r9d, r9d
0x180077412  call    cs:__imp_ZwUpdateWnfStateData
0x180077419  nop     dword ptr [rax+rax+00h]
0x18007741e  mov     edx, 63734943h; Tag
0x180077423  mov     rcx, rdi; P
0x180077426  mov     ebx, eax
0x180077428  call    cs:__imp_ExFreePoolWithTag
0x18007742f  nop     dword ptr [rax+rax+00h]
0x180077434  mov     eax, ebx
0x180077436  add     rsp, 48h
0x18007743a  pop     r15
0x18007743c  pop     r14
0x18007743e  pop     rdi
0x18007743f  pop     rsi
0x180077440  pop     rbp
0x180077441  pop     rbx
0x180077442  retn
```
