# NpFreeCcb

- ea: `0x14000e774`
- end: `0x14000e829`
- name: `NpFreeCcb`
- size: `181`
- prototype: `void __fastcall(_QWORD **P)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b030`
- `0x14000e640`

## callees

- `0x14000e774`
- `0x140010068`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e80d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e7db`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e80d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e7ca`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e7fc`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e7ca`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e7fc`

## pseudocode

```c
void __fastcall NpFreeCcb(_QWORD **P)
{
  PVOID *v2; // rdi
  PVOID *v3; // rdi

  NpRemoveAllAttributesFromList(P + 38);
  v2 = (PVOID *)P[54];
  if ( v2 )
  {
    if ( *v2 )
      ObfDereferenceObject(*v2);
    ExFreePoolWithTag(v2, 0);
    P[54] = 0;
  }
  v3 = (PVOID *)P[55];
  if ( v3 )
  {
    if ( *v3 )
      ObfDereferenceObject(*v3);
    ExFreePoolWithTag(v3, 0);
    P[55] = 0;
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000e774  mov     [rsp+arg_0], rbx
0x14000e779  push    rdi
0x14000e77a  sub     rsp, 20h
0x14000e77e  mov     rbx, rcx
0x14000e781  add     rcx, 130h
0x14000e788  call    NpRemoveAllAttributesFromList
0x14000e78d  mov     rdi, [rbx+1B0h]
0x14000e794  test    rdi, rdi
0x14000e797  jnz     short loc_14000E7C2
0x14000e799  mov     rdi, [rbx+1B8h]
0x14000e7a0  test    rdi, rdi
0x14000e7a3  jnz     short loc_14000E7F4
0x14000e7a5  xor     edx, edx; Tag
0x14000e7a7  mov     rcx, rbx; P
0x14000e7aa  call    cs:__imp_ExFreePoolWithTag
0x14000e7b1  nop     dword ptr [rax+rax+00h]
0x14000e7b6  mov     rbx, [rsp+28h+arg_0]
0x14000e7bb  add     rsp, 20h
0x14000e7bf  pop     rdi
0x14000e7c0  retn
0x14000e7c2  mov     rcx, [rdi]; Object
0x14000e7c5  test    rcx, rcx
0x14000e7c8  jz      short loc_14000E7D6
0x14000e7ca  call    cs:__imp_ObfDereferenceObject
0x14000e7d1  nop     dword ptr [rax+rax+00h]
0x14000e7d6  xor     edx, edx; Tag
0x14000e7d8  mov     rcx, rdi; P
0x14000e7db  call    cs:__imp_ExFreePoolWithTag
0x14000e7e2  nop     dword ptr [rax+rax+00h]
0x14000e7e7  mov     qword ptr [rbx+1B0h], 0
0x14000e7f2  jmp     short loc_14000E799
0x14000e7f4  mov     rcx, [rdi]; Object
0x14000e7f7  test    rcx, rcx
0x14000e7fa  jz      short loc_14000E808
0x14000e7fc  call    cs:__imp_ObfDereferenceObject
0x14000e803  nop     dword ptr [rax+rax+00h]
0x14000e808  xor     edx, edx; Tag
0x14000e80a  mov     rcx, rdi; P
0x14000e80d  call    cs:__imp_ExFreePoolWithTag
0x14000e814  nop     dword ptr [rax+rax+00h]
0x14000e819  mov     qword ptr [rbx+1B8h], 0
0x14000e824  jmp     loc_14000E7A5
```
