# FatDeleteEa

- ea: `0x140035608`
- end: `0x1400356e9`
- name: `FatDeleteEa`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14002cbe4`
- `0x140031468`

## callees

- `0x140035608`
- `0x1400356f0`
- `0x140035e50`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x14003569e`
- `ntoskrnl!CcFlushCache` at `0x14003569e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400356b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d768`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400356b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d768`
- `ntoskrnl!CcUnpinData` at `0x1400356cc`
- `ntoskrnl!CcUnpinData` at `0x14005d77e`
- `ntoskrnl!CcUnpinData` at `0x1400356cc`
- `ntoskrnl!CcUnpinData` at `0x14005d77e`
- `ntoskrnl!ExRaiseStatus` at `0x14003566a`
- `ntoskrnl!ExRaiseStatus` at `0x14003566a`

## pseudocode

```c
void __fastcall FatDeleteEa(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  __int64 v6; // [rsp+38h] [rbp-10h] BYREF
  PVOID Bcb; // [rsp+68h] [rbp+20h] BYREF

  Bcb = 0;
  v6 = 0;
  FatGetEaFile(a1, a2, (PVOID *)&v6, &Bcb, 0, 1);
  if ( !Bcb )
  {
    *(_DWORD *)(a1 + 72) = -1073741742;
    ExRaiseStatus(-1073741742);
  }
  FatDeleteEaSet(a1, a2, (__int64)Bcb, v6, a3);
  CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(*(_QWORD *)(a2 + 776) + 40LL), 0, 0, 0);
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(a2 + 784) + 8LL));
  if ( Bcb )
    CcUnpinData(Bcb);
}

```

## disassembly

```asm
0x140035608  mov     rax, rsp
0x14003560b  mov     [rax+8], rbx
0x14003560f  mov     [rax+18h], rsi
0x140035613  mov     [rax+20h], r9
0x140035617  mov     [rax+10h], rdx
0x14003561b  push    rdi
0x14003561c  sub     rsp, 40h
0x140035620  movzx   esi, r8w
0x140035624  mov     rbx, rdx
0x140035627  mov     rdi, rcx
0x14003562a  mov     qword ptr [rax+20h], 0
0x140035632  mov     byte ptr [rax-18h], 0
0x140035636  mov     qword ptr [rax-10h], 0
0x14003563e  mov     byte ptr [rax-20h], 1
0x140035642  mov     byte ptr [rax-28h], 0
0x140035646  lea     r9, [rax+20h]
0x14003564a  lea     r8, [rax-10h]
0x14003564e  call    FatGetEaFile
0x140035653  mov     [rsp+48h+var_18], 1
0x140035658  mov     r8, [rsp+48h+Bcb]
0x14003565d  test    r8, r8
0x140035660  jnz     short loc_140035676
0x140035662  mov     ecx, 0C0000052h; Status
0x140035667  mov     [rdi+48h], ecx
0x14003566a  call    cs:__imp_ExRaiseStatus
0x140035676  mov     word ptr [rsp+48h+var_28], si; int
0x14003567b  mov     r9, [rsp+48h+var_10]
0x140035680  mov     rdx, rbx
0x140035683  mov     rcx, rdi; int
0x140035686  call    FatDeleteEaSet
0x14003568b  mov     rcx, [rbx+308h]
0x140035692  xor     r9d, r9d; IoStatus
0x140035695  xor     r8d, r8d; Length
0x140035698  xor     edx, edx; FileOffset
0x14003569a  mov     rcx, [rcx+28h]; SectionObjectPointer
0x14003569e  call    cs:__imp_CcFlushCache
0x1400356a5  nop     dword ptr [rax+rax+00h]
0x1400356aa  nop
0x1400356ab  mov     rcx, [rbx+310h]
0x1400356b2  mov     rcx, [rcx+8]; Resource
0x1400356b6  call    cs:__imp_ExReleaseResourceLite
0x1400356bd  nop     dword ptr [rax+rax+00h]
0x1400356c2  mov     rcx, [rsp+48h+Bcb]; Bcb
0x1400356c7  test    rcx, rcx
0x1400356ca  jz      short loc_1400356D8
0x1400356cc  call    cs:__imp_CcUnpinData
0x1400356d3  nop     dword ptr [rax+rax+00h]
0x1400356d8  mov     rbx, [rsp+48h+arg_0]
0x1400356dd  mov     rsi, [rsp+48h+arg_10]
0x1400356e2  add     rsp, 40h
0x1400356e6  pop     rdi
0x1400356e7  retn
0x14005d74a  push    rbp
0x14005d74c  sub     rsp, 30h
0x14005d750  mov     rbp, rdx
0x14005d753  cmp     byte ptr [rbp+30h], 0
0x14005d757  jz      short loc_14005D775
0x14005d759  mov     rax, [rbp+58h]
0x14005d75d  mov     rcx, [rax+310h]
0x14005d764  mov     rcx, [rcx+8]; Resource
0x14005d768  call    cs:__imp_ExReleaseResourceLite
0x14005d76f  nop     dword ptr [rax+rax+00h]
0x14005d774  nop
0x14005d775  mov     rcx, [rbp+68h]; Bcb
0x14005d779  test    rcx, rcx
0x14005d77c  jz      short loc_14005D78B
0x14005d77e  call    cs:__imp_CcUnpinData
0x14005d785  nop     dword ptr [rax+rax+00h]
0x14005d78a  nop
0x14005d78b  add     rsp, 30h
0x14005d78f  pop     rbp
0x14005d790  retn
```
