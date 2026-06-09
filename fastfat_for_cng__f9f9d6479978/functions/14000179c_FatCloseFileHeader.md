# FatCloseFileHeader

- ea: `0x14000179c`
- end: `0x140001852`
- name: `FatCloseFileHeader`
- size: `182`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400034f0`
- `0x140029774`
- `0x14003805c`

## callees

- `0x14000179c`
- `0x1400465f4`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x1400017d3`
- `ntoskrnl!CcFlushCache` at `0x1400017d3`
- `ntoskrnl!CcPurgeCacheSection` at `0x140001806`
- `ntoskrnl!CcPurgeCacheSection` at `0x140001806`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14000181a`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14000181a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000183a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000183a`
- `ntoskrnl!ObfDereferenceObject` at `0x140001829`
- `ntoskrnl!ObfDereferenceObject` at `0x140001829`

## pseudocode

```c
void __fastcall FatCloseFileHeader(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct _FILE_OBJECT *v5; // rdi
  __int64 v6; // rcx

  v5 = *(struct _FILE_OBJECT **)(a2 + 424);
  FatAcquireExclusiveFcb(a1, a2, a3, a4);
  v6 = *(_QWORD *)(a2 + 424);
  if ( v6 )
  {
    CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(v6 + 40), 0, 0, 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 456), 0xFFFFFFFF) <= 1 )
    {
      *(_QWORD *)(a2 + 424) = 0;
      CcPurgeCacheSection(v5->SectionObjectPointer, 0, 0, 0);
      CcUninitializeCacheMap(v5, 0, 0);
      ObfDereferenceObject(v5);
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)(a2 + 8));
}

```

## disassembly

```asm
0x14000179c  mov     [rsp+arg_0], rbx
0x1400017a1  mov     [rsp+arg_8], rdx
0x1400017a6  push    rdi
0x1400017a7  sub     rsp, 20h
0x1400017ab  mov     rbx, rdx
0x1400017ae  mov     rdi, [rdx+1A8h]
0x1400017b5  call    FatAcquireExclusiveFcb
0x1400017ba  nop
0x1400017bb  mov     rcx, [rbx+1A8h]
0x1400017c2  test    rcx, rcx
0x1400017c5  jz      short loc_140001836
0x1400017c7  xor     r9d, r9d; IoStatus
0x1400017ca  xor     r8d, r8d; Length
0x1400017cd  xor     edx, edx; FileOffset
0x1400017cf  mov     rcx, [rcx+28h]; SectionObjectPointer
0x1400017d3  call    cs:__imp_CcFlushCache
0x1400017da  nop     dword ptr [rax+rax+00h]
0x1400017df  or      eax, 0FFFFFFFFh
0x1400017e2  lock xadd [rbx+1C8h], eax
0x1400017ea  sub     eax, 1
0x1400017ed  jg      short loc_140001836
0x1400017ef  mov     qword ptr [rbx+1A8h], 0
0x1400017fa  xor     r9d, r9d; Flags
0x1400017fd  xor     r8d, r8d; Length
0x140001800  xor     edx, edx; FileOffset
0x140001802  mov     rcx, [rdi+28h]; SectionObjectPointer
0x140001806  call    cs:__imp_CcPurgeCacheSection
0x14000180d  nop     dword ptr [rax+rax+00h]
0x140001812  xor     r8d, r8d; UninitializeEvent
0x140001815  xor     edx, edx; TruncateSize
0x140001817  mov     rcx, rdi; FileObject
0x14000181a  call    cs:__imp_CcUninitializeCacheMap
0x140001821  nop     dword ptr [rax+rax+00h]
0x140001826  mov     rcx, rdi; Object
0x140001829  call    cs:__imp_ObfDereferenceObject
0x140001830  nop     dword ptr [rax+rax+00h]
0x140001835  nop
0x140001836  mov     rcx, [rbx+8]; Resource
0x14000183a  call    cs:__imp_ExReleaseResourceLite
0x140001841  nop     dword ptr [rax+rax+00h]
0x140001846  mov     rbx, [rsp+28h+arg_0]
0x14000184b  add     rsp, 20h
0x14000184f  pop     rdi
0x140001850  retn
0x14000cc6d  push    rbp
0x14000cc6f  sub     rsp, 20h
0x14000cc73  mov     rbp, rdx
0x14000cc76  mov     rcx, [rbp+38h]
0x14000cc7a  mov     rcx, [rcx+8]; Resource
0x14000cc7e  call    cs:__imp_ExReleaseResourceLite
0x14000cc85  nop     dword ptr [rax+rax+00h]
0x14000cc8a  nop
0x14000cc8b  add     rsp, 20h
0x14000cc8f  pop     rbp
0x14000cc90  retn
```
