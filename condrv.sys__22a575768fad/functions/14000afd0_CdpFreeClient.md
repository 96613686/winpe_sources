# CdpFreeClient

- ea: `0x14000afd0`
- end: `0x14000b014`
- name: `CdpFreeClient`
- size: `68`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ae70`
- `0x14000b4d0`
- `0x14000e0d0`

## callees

- `0x14000afd0`
- `0x14000b020`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000aff0`
- `ntoskrnl!ObfDereferenceObject` at `0x14000aff0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b001`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b001`

## pseudocode

```c
void __fastcall CdpFreeClient(_QWORD *P)
{
  char *v2; // rcx
  void *v3; // rcx

  v2 = (char *)P[1];
  if ( v2 )
    CdDereferenceServer(v2);
  v3 = (void *)P[3];
  if ( v3 )
    ObfDereferenceObject(v3);
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x14000afd0  push    rbx
0x14000afd2  sub     rsp, 20h
0x14000afd6  mov     rbx, rcx
0x14000afd9  mov     rcx, [rcx+8]; P
0x14000afdd  test    rcx, rcx
0x14000afe0  jz      short loc_14000AFE7
0x14000afe2  call    CdDereferenceServer
0x14000afe7  mov     rcx, [rbx+18h]; Object
0x14000afeb  test    rcx, rcx
0x14000afee  jz      short loc_14000AFFC
0x14000aff0  call    cs:__imp_ObfDereferenceObject
0x14000aff7  nop     dword ptr [rax+rax+00h]
0x14000affc  xor     edx, edx; Tag
0x14000affe  mov     rcx, rbx; P
0x14000b001  call    cs:__imp_ExFreePoolWithTag
0x14000b008  nop     dword ptr [rax+rax+00h]
0x14000b00d  add     rsp, 20h
0x14000b011  pop     rbx
0x14000b012  retn
```
