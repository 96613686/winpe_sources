# CipHvciPublishIncompatibleImageWNF

- ea: `0x180077654`
- end: `0x180077724`
- name: `CipHvciPublishIncompatibleImageWNF`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180076ee8`
- `0x18007706c`

## callees

- `0x18002c200`
- `0x180077654`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180077680`
- `ntoskrnl!ExAllocatePool2` at `0x180077680`
- `ntoskrnl!ExFreePoolWithTag` at `0x180077708`
- `ntoskrnl!ExFreePoolWithTag` at `0x180077708`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800776f2`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1800776f2`

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
0x180077654  push    rbx
0x180077656  push    rbp
0x180077657  push    rsi
0x180077658  push    rdi
0x180077659  push    r14
0x18007765b  push    r15
0x18007765d  sub     rsp, 48h
0x180077661  movzx   esi, word ptr [rcx]
0x180077664  mov     r14d, r8d
0x180077667  mov     r15, rdx
0x18007766a  mov     rbx, rcx
0x18007766d  add     esi, 0Eh
0x180077670  mov     ecx, 102h
0x180077675  mov     edx, esi
0x180077677  mov     r8d, 63734943h
0x18007767d  mov     ebp, r9d
0x180077680  call    cs:__imp_ExAllocatePool2
0x180077687  nop     dword ptr [rax+rax+00h]
0x18007768c  mov     rdi, rax
0x18007768f  test    rax, rax
0x180077692  jnz     short loc_18007769B
0x180077694  mov     ebx, 0C0000017h
0x180077699  jmp     short loc_180077714
0x18007769b  mov     eax, [r15]
0x18007769e  lea     rcx, [rdi+0Eh]; void *
0x1800776a2  mov     [rdi], eax
0x1800776a4  mov     [rdi+4], r14d
0x1800776a8  mov     [rdi+8], ebp
0x1800776ab  movzx   eax, word ptr [rbx]
0x1800776ae  mov     [rdi+0Ch], ax
0x1800776b2  movzx   r8d, word ptr [rbx]; Size
0x1800776b6  mov     rdx, [rbx+8]; Src
0x1800776ba  call    memmove
0x1800776bf  mov     r8d, 1000h
0x1800776c5  mov     [rsp+78h+var_48], 0
0x1800776cd  cmp     esi, r8d
0x1800776d0  mov     [rsp+78h+var_50], 0
0x1800776d8  mov     rdx, rdi
0x1800776db  mov     [rsp+78h+var_58], 0
0x1800776e4  cmovb   r8d, esi
0x1800776e8  lea     rcx, WNF_CI_HVCI_IMAGE_INCOMPATIBLE
0x1800776ef  xor     r9d, r9d
0x1800776f2  call    cs:__imp_ZwUpdateWnfStateData
0x1800776f9  nop     dword ptr [rax+rax+00h]
0x1800776fe  mov     edx, 63734943h; Tag
0x180077703  mov     rcx, rdi; P
0x180077706  mov     ebx, eax
0x180077708  call    cs:__imp_ExFreePoolWithTag
0x18007770f  nop     dword ptr [rax+rax+00h]
0x180077714  mov     eax, ebx
0x180077716  add     rsp, 48h
0x18007771a  pop     r15
0x18007771c  pop     r14
0x18007771e  pop     rdi
0x18007771f  pop     rsi
0x180077720  pop     rbp
0x180077721  pop     rbx
0x180077722  retn
```
