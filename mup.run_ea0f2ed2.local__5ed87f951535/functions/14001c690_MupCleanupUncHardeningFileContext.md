# MupCleanupUncHardeningFileContext

- ea: `0x14001c690`
- end: `0x14001c757`
- name: `MupCleanupUncHardeningFileContext`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c300`
- `0x14001cb80`

## callees

- `0x14001c690`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001c721`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c721`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14001c6d5`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14001c6d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c6a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c6a2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c6fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c749`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c6fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c749`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c6b7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c6b7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c6f2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c73d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c6f2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c73d`

## pseudocode

```c
void __fastcall MupCleanupUncHardeningFileContext(__int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(&qword_14000A1F8, 0);
    if ( (*(_QWORD *)(v1 + 80))-- == 1 )
    {
      RtlRemoveUnicodePrefix(&PrefixTable, (PUNICODE_PREFIX_TABLE_ENTRY)(v1 + 8));
      *(_QWORD *)(v1 + 32) = 0;
      ExReleasePushLockExclusiveEx(&qword_14000A1F8, 0);
      KeLeaveCriticalRegion();
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 4), 0xFFFFFFFF) == 1 )
        ExFreePoolWithTag((PVOID)v1, 0x4855754Du);
    }
    else
    {
      ExReleasePushLockExclusiveEx(&qword_14000A1F8, 0);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x14001c690  push    rbx
0x14001c692  sub     rsp, 20h
0x14001c696  mov     rbx, [rcx]
0x14001c699  test    rbx, rbx
0x14001c69c  jz      loc_14001C72D
0x14001c6a2  call    cs:__imp_KeEnterCriticalRegion
0x14001c6a9  nop     dword ptr [rax+rax+00h]
0x14001c6ae  xor     edx, edx
0x14001c6b0  lea     rcx, qword_14000A1F8
0x14001c6b7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001c6be  nop     dword ptr [rax+rax+00h]
0x14001c6c3  sub     qword ptr [rbx+50h], 1
0x14001c6c8  jnz     short loc_14001C734
0x14001c6ca  lea     rdx, [rbx+8]; PrefixTableEntry
0x14001c6ce  lea     rcx, PrefixTable; PrefixTable
0x14001c6d5  call    cs:__imp_RtlRemoveUnicodePrefix
0x14001c6dc  nop     dword ptr [rax+rax+00h]
0x14001c6e1  xor     edx, edx
0x14001c6e3  mov     qword ptr [rbx+20h], 0
0x14001c6eb  lea     rcx, qword_14000A1F8
0x14001c6f2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001c6f9  nop     dword ptr [rax+rax+00h]
0x14001c6fe  call    cs:__imp_KeLeaveCriticalRegion
0x14001c705  nop     dword ptr [rax+rax+00h]
0x14001c70a  mov     eax, 0FFFFFFFFh
0x14001c70f  lock xadd [rbx+4], eax
0x14001c714  cmp     eax, 1
0x14001c717  jnz     short loc_14001C72D
0x14001c719  mov     edx, 4855754Dh; Tag
0x14001c71e  mov     rcx, rbx; P
0x14001c721  call    cs:__imp_ExFreePoolWithTag
0x14001c728  nop     dword ptr [rax+rax+00h]
0x14001c72d  add     rsp, 20h
0x14001c731  pop     rbx
0x14001c732  retn
0x14001c734  xor     edx, edx
0x14001c736  lea     rcx, qword_14000A1F8
0x14001c73d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001c744  nop     dword ptr [rax+rax+00h]
0x14001c749  call    cs:__imp_KeLeaveCriticalRegion
0x14001c750  nop     dword ptr [rax+rax+00h]
0x14001c755  jmp     short loc_14001C72D
```
