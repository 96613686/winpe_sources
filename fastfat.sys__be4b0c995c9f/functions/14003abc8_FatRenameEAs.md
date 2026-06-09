# FatRenameEAs

- ea: `0x14003abc8`
- end: `0x14003ad3d`
- name: `FatRenameEAs`
- size: `373`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14003bea4`

## callees

- `0x140005288`
- `0x14000c380`
- `0x14000c680`
- `0x140035e50`
- `0x1400367d8`
- `0x140036a6c`
- `0x140036c78`
- `0x14003abc8`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x14003acc9`
- `ntoskrnl!CcFlushCache` at `0x14003acc9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ad20`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e463`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ad20`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e463`
- `ntoskrnl!CcUnpinData` at `0x14003acee`
- `ntoskrnl!CcUnpinData` at `0x14005e42e`
- `ntoskrnl!CcUnpinData` at `0x14003acee`
- `ntoskrnl!CcUnpinData` at `0x14005e42e`

## pseudocode

```c
void __fastcall FatRenameEAs(int a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // [rsp+20h] [rbp-B8h]
  int v9[34]; // [rsp+50h] [rbp-88h] BYREF

  memset(v9, 0, 0x60u);
  v4 = *(_QWORD *)(a2 + 184);
  FatGetEaFile(a1, v4, 0, 0);
  if ( *(_QWORD *)(v4 + 776) )
  {
    FatReadEaSet(a1, v8, (int)v9);
    v5 = *(_QWORD *)v9 + 8LL;
    *(_QWORD *)(*(_QWORD *)v9 + 8LL) = 0;
    *(_DWORD *)(v5 + 8) = 0;
    *(_WORD *)(v5 + 12) = 0;
    memmove((void *)v5, *(const void **)(a2 + 488), *(unsigned __int16 *)(a2 + 480));
    FatMarkEaRangeDirty(v6, *(_QWORD *)(v4 + 776), v9);
    FatUnpinEaRange(v7, v9);
    CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(v4 + 776) + 40LL), 0, 0, 0);
  }
  FatUnpinEaRange(0, v9);
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v4 + 784) + 8LL));
}

```

## disassembly

```asm
0x14003abc8  mov     rax, rsp
0x14003abcb  mov     [rax+20h], r9
0x14003abcf  mov     [rax+8], rcx
0x14003abd3  push    rsi
0x14003abd4  push    rdi
0x14003abd5  push    r12
0x14003abd7  push    r14
0x14003abd9  push    r15
0x14003abdb  sub     rsp, 0B0h
0x14003abe2  movzx   r12d, r8w
0x14003abe6  mov     r15, rdx
0x14003abe9  mov     r14, rcx
0x14003abec  mov     [rsp+0D8h+var_A8], 0
0x14003abf1  mov     qword ptr [rax+20h], 0
0x14003abf9  mov     qword ptr [rax+10h], 0
0x14003ac01  xor     edx, edx; Val
0x14003ac03  lea     r8d, [rdx+60h]; Size
0x14003ac07  lea     rcx, [rsp+0D8h+var_88]; void *
0x14003ac0c  call    memset
0x14003ac11  mov     rdi, [r15+0B8h]
0x14003ac18  mov     [rsp+0D8h+var_A0], rdi
0x14003ac1d  mov     [rsp+0D8h+var_98], rdi
0x14003ac22  mov     [rsp+0D8h+var_B0], 0; char
0x14003ac27  mov     [rsp+0D8h+var_B8], 0; int
0x14003ac2c  lea     r9, [rsp+0D8h+Bcb]
0x14003ac34  lea     r8, [rsp+0D8h+arg_8]
0x14003ac3c  mov     rdx, rdi; int
0x14003ac3f  mov     rcx, r14; int
0x14003ac42  call    FatGetEaFile
0x14003ac47  mov     sil, 1
0x14003ac4a  mov     [rsp+0D8h+var_A8], sil
0x14003ac4f  cmp     qword ptr [rdi+308h], 0
0x14003ac57  jz      short loc_14003ACD5
0x14003ac59  lea     rax, [rsp+0D8h+var_88]
0x14003ac5e  mov     qword ptr [rsp+0D8h+var_B0], rax; int
0x14003ac63  movzx   r8d, r12w
0x14003ac67  mov     rdx, rdi
0x14003ac6a  mov     rcx, r14; int
0x14003ac6d  call    FatReadEaSet
0x14003ac72  mov     rcx, qword ptr [rsp+0D8h+var_88]
0x14003ac77  add     rcx, 8; void *
0x14003ac7b  xor     eax, eax
0x14003ac7d  mov     [rcx], rax
0x14003ac80  mov     [rcx+8], eax
0x14003ac83  mov     [rcx+0Ch], ax
0x14003ac87  movzx   r8d, word ptr [r15+1E0h]; Size
0x14003ac8f  mov     rdx, [r15+1E8h]; Src
0x14003ac96  call    memmove
0x14003ac9b  lea     r8, [rsp+0D8h+var_88]
0x14003aca0  mov     rdx, [rdi+308h]
0x14003aca7  call    FatMarkEaRangeDirty
0x14003acac  lea     rdx, [rsp+0D8h+var_88]
0x14003acb1  call    FatUnpinEaRange
0x14003acb6  mov     rcx, [rdi+308h]
0x14003acbd  xor     r9d, r9d; IoStatus
0x14003acc0  xor     r8d, r8d; Length
0x14003acc3  xor     edx, edx; FileOffset
0x14003acc5  mov     rcx, [rcx+28h]; SectionObjectPointer
0x14003acc9  call    cs:__imp_CcFlushCache
0x14003acd0  nop     dword ptr [rax+rax+00h]
0x14003acd5  jmp     short loc_14003ACE1
0x14003acd7  mov     sil, [rsp+0D8h+var_A8]
0x14003acdc  mov     rdi, [rsp+0D8h+var_A0]
0x14003ace1  mov     rcx, [rsp+0D8h+Bcb]; Bcb
0x14003ace9  test    rcx, rcx
0x14003acec  jz      short loc_14003AD06
0x14003acee  call    cs:__imp_CcUnpinData
0x14003acf5  nop     dword ptr [rax+rax+00h]
0x14003acfa  mov     [rsp+0D8h+Bcb], 0
0x14003ad06  lea     rdx, [rsp+0D8h+var_88]
0x14003ad0b  call    FatUnpinEaRange
0x14003ad10  test    sil, sil
0x14003ad13  jz      short loc_14003AD2C
0x14003ad15  mov     rcx, [rdi+310h]
0x14003ad1c  mov     rcx, [rcx+8]; Resource
0x14003ad20  call    cs:__imp_ExReleaseResourceLite
0x14003ad27  nop     dword ptr [rax+rax+00h]
0x14003ad2c  add     rsp, 0B0h
0x14003ad33  pop     r15
0x14003ad35  pop     r14
0x14003ad37  pop     r12
0x14003ad39  pop     rdi
0x14003ad3a  pop     rsi
0x14003ad3b  retn
0x14005e3f9  push    rbp
0x14005e3fb  sub     rsp, 30h
0x14005e3ff  mov     rbp, rdx
0x14005e402  mov     rdx, rcx
0x14005e405  mov     rcx, [rbp+0E0h]
0x14005e40c  call    FatExceptionFilter
0x14005e411  nop
0x14005e412  add     rsp, 30h
0x14005e416  pop     rbp
0x14005e417  retn
0x14005e419  push    rbp
0x14005e41b  sub     rsp, 30h
0x14005e41f  mov     rbp, rdx
0x14005e422  mov     rcx, [rbp+0F8h]; Bcb
0x14005e429  test    rcx, rcx
0x14005e42c  jz      short loc_14005E445
0x14005e42e  call    cs:__imp_CcUnpinData
0x14005e435  nop     dword ptr [rax+rax+00h]
0x14005e43a  mov     qword ptr [rbp+0F8h], 0
0x14005e445  lea     rdx, [rbp+50h]
0x14005e449  call    FatUnpinEaRange
0x14005e44e  cmp     byte ptr [rbp+30h], 0
0x14005e452  jz      short loc_14005E470
0x14005e454  mov     rax, [rbp+40h]
0x14005e458  mov     rcx, [rax+310h]
0x14005e45f  mov     rcx, [rcx+8]; Resource
0x14005e463  call    cs:__imp_ExReleaseResourceLite
0x14005e46a  nop     dword ptr [rax+rax+00h]
0x14005e46f  nop
0x14005e470  add     rsp, 30h
0x14005e474  pop     rbp
0x14005e475  retn
```
