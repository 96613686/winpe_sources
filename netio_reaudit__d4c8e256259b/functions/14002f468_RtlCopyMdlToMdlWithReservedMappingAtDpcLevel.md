# RtlCopyMdlToMdlWithReservedMappingAtDpcLevel

- ea: `0x14002f468`
- end: `0x14002f719`
- name: `RtlCopyMdlToMdlWithReservedMappingAtDpcLevel`
- size: `689`
- prototype: `__int64 __usercall@<rax>(PMDL SourceMdl@<rcx>, __int64, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14002f100`
- `0x140047a60`

## callees

- `0x14002f468`
- `0x140077fa0`
- `0x140077fd0`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14002f55c`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002f5d4`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002f55c`
- `ntoskrnl!IoBuildPartialMdl` at `0x14002f5d4`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14002f582`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14002f5fb`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14002f582`
- `ntoskrnl!MmMapLockedPagesWithReservedMapping` at `0x14002f5fb`
- `ntoskrnl!RtlPrefetchMemoryNonTemporal` at `0x14002f62c`
- `ntoskrnl!RtlPrefetchMemoryNonTemporal` at `0x14002f62c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002f4dc`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14002f4dc`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14002f65d`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14002f698`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14002f65d`
- `ntoskrnl!MmUnmapReservedMapping` at `0x14002f698`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002f6ec`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14002f6ec`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002f677`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002f6b2`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002f677`
- `ntoskrnl!MmUnmapLockedPages` at `0x14002f6b2`

## pseudocode

```c
void __fastcall RtlCopyMdlToMdlWithReservedMappingAtDpcLevel(
        PMDL SourceMdl,
        unsigned __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        __int64 a5,
        char a6)
{
  PMDL v6; // r14
  char v10; // bl
  char v11; // r13
  unsigned __int64 v12; // r12
  unsigned __int64 v13; // rdx
  __int64 ByteOffset; // rcx
  unsigned __int64 v15; // r15
  PVOID MappedSystemVa; // r14
  unsigned __int64 v17; // rbx
  __int64 v18; // rcx
  PVOID v19; // r12
  SIZE_T v20; // r15
  SIZE_T v21; // rbx
  char v22; // [rsp+20h] [rbp-99h]
  unsigned __int64 v24; // [rsp+30h] [rbp-89h]
  unsigned __int64 i; // [rsp+38h] [rbp-81h]
  _MDL TargetMdl; // [rsp+48h] [rbp-71h] BYREF
  struct _MDL MemoryDescriptorList; // [rsp+80h] [rbp-39h] BYREF

  v6 = SourceMdl;
  TargetMdl.Next = 0;
  TargetMdl.StartVa = 0;
  MemoryDescriptorList.Next = 0;
  MemoryDescriptorList.StartVa = 0;
  *(_DWORD *)&TargetMdl.Size = 56;
  *(_QWORD *)&TargetMdl.ByteCount = 4096;
  *(_DWORD *)&MemoryDescriptorList.Size = 56;
  *(_QWORD *)&MemoryDescriptorList.ByteCount = 4096;
  KeAcquireSpinLockAtDpcLevel(&RtlMappingAddressLock);
  v10 = v6->MdlFlags & 5;
  v11 = *(_BYTE *)(a3 + 10) & 5;
  v22 = v10;
  v12 = a4 + a5;
  v24 = a4 + a5;
  v13 = a2 + a5;
  for ( i = a2 + a5; a4 < v24; v6 = SourceMdl )
  {
    if ( a2 >= v13 )
      break;
    ByteOffset = v6->ByteOffset;
    v15 = v13;
    if ( (unsigned __int64)(((_DWORD)a2 + (_DWORD)ByteOffset + 4096) & 0xFFFFF000) - ByteOffset <= v13 )
      v15 = (((_DWORD)a2 + (_DWORD)ByteOffset + 4096) & 0xFFFFF000) - ByteOffset;
    IoBuildPartialMdl(v6, &TargetMdl, (char *)v6->StartVa + ByteOffset + a2, v15 - a2);
    if ( v10 )
      MappedSystemVa = TargetMdl.MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesWithReservedMapping(RtlMappingSourceAddress, 0x74506D52u, &TargetMdl, MmCached);
    v17 = v12;
    v18 = *(unsigned int *)(a3 + 44);
    if ( (unsigned __int64)(((_DWORD)a4 + (_DWORD)v18 + 4096) & 0xFFFFF000) - v18 <= v12 )
      v17 = (((_DWORD)a4 + (_DWORD)v18 + 4096) & 0xFFFFF000) - v18;
    IoBuildPartialMdl((PMDL)a3, &MemoryDescriptorList, (PVOID)(a4 + v18 + *(_QWORD *)(a3 + 32)), v17 - a4);
    if ( v11 )
      v19 = MemoryDescriptorList.MappedSystemVa;
    else
      v19 = MmMapLockedPagesWithReservedMapping(RtlMappingTargetAddress, 0x74506D52u, &MemoryDescriptorList, MmCached);
    v20 = v15 - a2;
    v21 = v17 - a4;
    if ( v21 >= v20 )
      v21 = v20;
    if ( a6 )
      RtlPrefetchMemoryNonTemporal(MappedSystemVa, v21);
    RtlCopyVolatileMemory(v19, MappedSystemVa, v21);
    if ( !v22 )
      MmUnmapReservedMapping(RtlMappingSourceAddress, 0x74506D52u, &TargetMdl);
    if ( (TargetMdl.MdlFlags & 0x20) != 0 )
      MmUnmapLockedPages(TargetMdl.MappedSystemVa, &TargetMdl);
    if ( !v11 )
      MmUnmapReservedMapping(RtlMappingTargetAddress, 0x74506D52u, &MemoryDescriptorList);
    if ( (MemoryDescriptorList.MdlFlags & 0x20) != 0 )
      MmUnmapLockedPages(MemoryDescriptorList.MappedSystemVa, &MemoryDescriptorList);
    v12 = v24;
    a2 += v21;
    v13 = i;
    a4 += v21;
    v10 = v22;
  }
  KeReleaseSpinLockFromDpcLevel(&RtlMappingAddressLock);
}

```

## disassembly

```asm
0x14002f468  push    rbp
0x14002f46a  push    rbx
0x14002f46b  push    rsi
0x14002f46c  push    rdi
0x14002f46d  push    r12
0x14002f46f  push    r13
0x14002f471  push    r14
0x14002f473  push    r15
0x14002f475  lea     rbp, [rsp-0Fh]
0x14002f47a  sub     rsp, 0C8h
0x14002f481  mov     rax, cs:__security_cookie
0x14002f488  xor     rax, rsp
0x14002f48b  mov     [rbp+47h+var_48], rax
0x14002f48f  xor     r15d, r15d
0x14002f492  mov     [rbp+47h+var_C0], rcx
0x14002f496  mov     r14, rcx
0x14002f499  mov     [rbp+47h+TargetMdl.Next], r15
0x14002f49d  lea     rcx, RtlMappingAddressLock; SpinLock
0x14002f4a4  mov     [rbp+47h+TargetMdl.StartVa], r15
0x14002f4a8  mov     [rbp+47h+MemoryDescriptorList.Next], r15
0x14002f4ac  mov     rsi, r9
0x14002f4af  mov     [rbp+47h+MemoryDescriptorList.StartVa], r15
0x14002f4b3  mov     r13, r8
0x14002f4b6  mov     [rsp+100h+SourceMdl], r8
0x14002f4bb  mov     rdi, rdx
0x14002f4be  mov     dword ptr [rbp+47h+TargetMdl.Size], 38h ; '8'
0x14002f4c5  mov     qword ptr [rbp+47h+TargetMdl.ByteCount], 1000h
0x14002f4cd  mov     dword ptr [rbp+47h+MemoryDescriptorList.Size], 38h ; '8'
0x14002f4d4  mov     qword ptr [rbp+47h+MemoryDescriptorList.ByteCount], 1000h
0x14002f4dc  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14002f4e3  nop     dword ptr [rax+rax+00h]
0x14002f4e8  mov     rax, [rbp+47h+arg_20]
0x14002f4ec  mov     bl, [r14+0Ah]
0x14002f4f0  mov     r13b, [r13+0Ah]
0x14002f4f4  and     bl, 5
0x14002f4f7  and     r13b, 5
0x14002f4fb  mov     [rsp+100h+var_E0], bl
0x14002f4ff  lea     r12, [rsi+rax]
0x14002f503  mov     [rsp+100h+var_D0], r12
0x14002f508  lea     rdx, [rdi+rax]
0x14002f50c  mov     [rsp+100h+var_C8], rdx
0x14002f511  cmp     rsi, r12
0x14002f514  jnb     loc_14002F6E5
0x14002f51a  mov     r8d, 0FFFFF000h
0x14002f520  cmp     rdi, rdx
0x14002f523  jnb     loc_14002F6E5
0x14002f529  mov     ecx, [r14+2Ch]
0x14002f52d  mov     r15, rdx
0x14002f530  lea     eax, [rcx+1000h]
0x14002f536  add     eax, edi
0x14002f538  and     rax, r8
0x14002f53b  mov     r8, [r14+20h]
0x14002f53f  sub     rax, rcx
0x14002f542  cmp     rax, rdx
0x14002f545  lea     rdx, [rbp+47h+TargetMdl]; TargetMdl
0x14002f549  cmovbe  r15, rax
0x14002f54d  add     r8, rcx
0x14002f550  mov     r9d, r15d
0x14002f553  add     r8, rdi; VirtualAddress
0x14002f556  sub     r9d, edi; Length
0x14002f559  mov     rcx, r14; SourceMdl
0x14002f55c  call    cs:__imp_IoBuildPartialMdl
0x14002f563  nop     dword ptr [rax+rax+00h]
0x14002f568  test    bl, bl
0x14002f56a  jnz     short loc_14002F593
0x14002f56c  mov     rcx, cs:RtlMappingSourceAddress; MappingAddress
0x14002f573  lea     r8, [rbp+47h+TargetMdl]; MemoryDescriptorList
0x14002f577  mov     r9d, 1; CacheType
0x14002f57d  mov     edx, 74506D52h; PoolTag
0x14002f582  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x14002f589  nop     dword ptr [rax+rax+00h]
0x14002f58e  mov     r14, rax
0x14002f591  jmp     short loc_14002F597
0x14002f593  mov     r14, [rbp+47h+TargetMdl.MappedSystemVa]
0x14002f597  mov     r10, [rsp+100h+SourceMdl]
0x14002f59c  mov     edx, 0FFFFF000h
0x14002f5a1  mov     rbx, r12
0x14002f5a4  mov     ecx, [r10+2Ch]
0x14002f5a8  mov     r8, [r10+20h]
0x14002f5ac  lea     eax, [rcx+1000h]
0x14002f5b2  add     eax, esi
0x14002f5b4  and     rax, rdx
0x14002f5b7  lea     rdx, [rbp+47h+MemoryDescriptorList]; TargetMdl
0x14002f5bb  sub     rax, rcx
0x14002f5be  cmp     rax, r12
0x14002f5c1  cmovbe  rbx, rax
0x14002f5c5  add     r8, rcx
0x14002f5c8  mov     r9d, ebx
0x14002f5cb  add     r8, rsi; VirtualAddress
0x14002f5ce  sub     r9d, esi; Length
0x14002f5d1  mov     rcx, r10; SourceMdl
0x14002f5d4  call    cs:__imp_IoBuildPartialMdl
0x14002f5db  nop     dword ptr [rax+rax+00h]
0x14002f5e0  test    r13b, r13b
0x14002f5e3  jnz     short loc_14002F60C
0x14002f5e5  mov     rcx, cs:RtlMappingTargetAddress; MappingAddress
0x14002f5ec  lea     r8, [rbp+47h+MemoryDescriptorList]; MemoryDescriptorList
0x14002f5f0  mov     r9d, 1; CacheType
0x14002f5f6  mov     edx, 74506D52h; PoolTag
0x14002f5fb  call    cs:__imp_MmMapLockedPagesWithReservedMapping
0x14002f602  nop     dword ptr [rax+rax+00h]
0x14002f607  mov     r12, rax
0x14002f60a  jmp     short loc_14002F610
0x14002f60c  mov     r12, [rbp+47h+MemoryDescriptorList.MappedSystemVa]
0x14002f610  sub     r15, rdi
0x14002f613  sub     rbx, rsi
0x14002f616  cmp     rbx, r15
0x14002f619  cmovnb  rbx, r15
0x14002f61d  xor     r15d, r15d
0x14002f620  cmp     [rbp+47h+arg_28], r15b
0x14002f624  jz      short loc_14002F638
0x14002f626  mov     rdx, rbx; Length
0x14002f629  mov     rcx, r14; Source
0x14002f62c  call    cs:__imp_RtlPrefetchMemoryNonTemporal
0x14002f633  nop     dword ptr [rax+rax+00h]
0x14002f638  mov     r8, rbx; Size
0x14002f63b  mov     rdx, r14; Src
0x14002f63e  mov     rcx, r12; void *
0x14002f641  call    RtlCopyVolatileMemory
0x14002f646  cmp     [rsp+100h+var_E0], r15b
0x14002f64b  jnz     short loc_14002F669
0x14002f64d  mov     rcx, cs:RtlMappingSourceAddress; BaseAddress
0x14002f654  lea     r8, [rbp+47h+TargetMdl]; MemoryDescriptorList
0x14002f658  mov     edx, 74506D52h; PoolTag
0x14002f65d  call    cs:__imp_MmUnmapReservedMapping
0x14002f664  nop     dword ptr [rax+rax+00h]
0x14002f669  test    byte ptr [rbp+47h+TargetMdl.MdlFlags], 20h
0x14002f66d  jz      short loc_14002F683
0x14002f66f  mov     rcx, [rbp+47h+TargetMdl.MappedSystemVa]; BaseAddress
0x14002f673  lea     rdx, [rbp+47h+TargetMdl]; MemoryDescriptorList
0x14002f677  call    cs:__imp_MmUnmapLockedPages
0x14002f67e  nop     dword ptr [rax+rax+00h]
0x14002f683  test    r13b, r13b
0x14002f686  jnz     short loc_14002F6A4
0x14002f688  mov     rcx, cs:RtlMappingTargetAddress; BaseAddress
0x14002f68f  lea     r8, [rbp+47h+MemoryDescriptorList]; MemoryDescriptorList
0x14002f693  mov     edx, 74506D52h; PoolTag
0x14002f698  call    cs:__imp_MmUnmapReservedMapping
0x14002f69f  nop     dword ptr [rax+rax+00h]
0x14002f6a4  test    byte ptr [rbp+47h+MemoryDescriptorList.MdlFlags], 20h
0x14002f6a8  jz      short loc_14002F6BE
0x14002f6aa  mov     rcx, [rbp+47h+MemoryDescriptorList.MappedSystemVa]; BaseAddress
0x14002f6ae  lea     rdx, [rbp+47h+MemoryDescriptorList]; MemoryDescriptorList
0x14002f6b2  call    cs:__imp_MmUnmapLockedPages
0x14002f6b9  nop     dword ptr [rax+rax+00h]
0x14002f6be  mov     r12, [rsp+100h+var_D0]
0x14002f6c3  add     rdi, rbx
0x14002f6c6  mov     rdx, [rsp+100h+var_C8]
0x14002f6cb  add     rsi, rbx
0x14002f6ce  mov     bl, [rsp+100h+var_E0]
0x14002f6d2  mov     r8d, 0FFFFF000h
0x14002f6d8  mov     r14, [rbp+47h+var_C0]
0x14002f6dc  cmp     rsi, r12
0x14002f6df  jb      loc_14002F520
0x14002f6e5  lea     rcx, RtlMappingAddressLock; SpinLock
0x14002f6ec  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002f6f3  nop     dword ptr [rax+rax+00h]
0x14002f6f8  mov     rcx, [rbp+47h+var_48]
0x14002f6fc  xor     rcx, rsp; StackCookie
0x14002f6ff  call    __security_check_cookie
0x14002f704  add     rsp, 0C8h
0x14002f70b  pop     r15
0x14002f70d  pop     r14
0x14002f70f  pop     r13
0x14002f711  pop     r12
0x14002f713  pop     rdi
0x14002f714  pop     rsi
0x14002f715  pop     rbx
0x14002f716  pop     rbp
0x14002f717  retn
```
