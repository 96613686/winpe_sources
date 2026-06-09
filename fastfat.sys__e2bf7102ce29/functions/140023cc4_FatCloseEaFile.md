# FatCloseEaFile

- ea: `0x140023cc4`
- end: `0x140023d45`
- name: `FatCloseEaFile`
- size: `129`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140005a94`
- `0x14003f1bc`
- `0x140042ec8`
- `0x140048fd0`

## callees

- `0x140023cc4`
- `0x1400247f4`
- `0x1400426ec`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x140023cee`
- `ntoskrnl!CcFlushCache` at `0x140023cee`
- `ntoskrnl!ObfDereferenceObject` at `0x140023d2d`
- `ntoskrnl!ObfDereferenceObject` at `0x140023d2d`

## pseudocode

```c
LONG_PTR __fastcall FatCloseEaFile(__int64 a1, __int64 a2, char a3)
{
  struct _FILE_OBJECT *v3; // rbx
  LARGE_MCB *v5; // rdx
  __int64 v6; // rcx
  LONG_PTR result; // rax

  v3 = *(struct _FILE_OBJECT **)(a2 + 776);
  if ( v3 )
  {
    if ( a3 )
      CcFlushCache(v3->SectionObjectPointer, 0, 0, 0);
    v5 = (LARGE_MCB *)(*(_QWORD *)(a2 + 784) + 288LL);
    *(_QWORD *)(a2 + 776) = 0;
    FatRemoveMcbEntry(a2, v5, 0, 0xFFFFFFFF);
    FatSyncUninitializeCacheMap(v6, v3);
    return ObfDereferenceObject(v3);
  }
  return result;
}

```

## disassembly

```asm
0x140023cc4  mov     [rsp+arg_0], rbx
0x140023cc9  push    rdi
0x140023cca  sub     rsp, 20h
0x140023cce  mov     rbx, [rdx+308h]
0x140023cd5  mov     rdi, rdx
0x140023cd8  test    rbx, rbx
0x140023cdb  jz      short loc_140023D39
0x140023cdd  test    r8b, r8b
0x140023ce0  jz      short loc_140023CFA
0x140023ce2  mov     rcx, [rbx+28h]; SectionObjectPointer
0x140023ce6  xor     r9d, r9d; IoStatus
0x140023ce9  xor     r8d, r8d; Length
0x140023cec  xor     edx, edx; FileOffset
0x140023cee  call    cs:__imp_CcFlushCache
0x140023cf5  nop     dword ptr [rax+rax+00h]
0x140023cfa  mov     rdx, [rdi+310h]
0x140023d01  or      r9d, 0FFFFFFFFh
0x140023d05  add     rdx, 120h
0x140023d0c  mov     qword ptr [rdi+308h], 0
0x140023d17  xor     r8d, r8d
0x140023d1a  mov     rcx, rdi
0x140023d1d  call    FatRemoveMcbEntry
0x140023d22  mov     rdx, rbx
0x140023d25  call    FatSyncUninitializeCacheMap
0x140023d2a  mov     rcx, rbx; Object
0x140023d2d  call    cs:__imp_ObfDereferenceObject
0x140023d34  nop     dword ptr [rax+rax+00h]
0x140023d39  mov     rbx, [rsp+28h+arg_0]
0x140023d3e  add     rsp, 20h
0x140023d42  pop     rdi
0x140023d43  retn
```
