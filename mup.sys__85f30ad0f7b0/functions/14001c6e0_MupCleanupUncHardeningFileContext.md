# MupCleanupUncHardeningFileContext

- ea: `0x14001c6e0`
- end: `0x14001c7a7`
- name: `MupCleanupUncHardeningFileContext`
- size: `199`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c350`
- `0x14001cbd0`

## callees

- `0x14001c6e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001c771`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c771`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14001c725`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14001c725`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c6f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001c6f2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c74e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c799`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c74e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001c799`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c707`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c707`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c742`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c78d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c742`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c78d`

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
0x14001c6e0  push    rbx
0x14001c6e2  sub     rsp, 20h
0x14001c6e6  mov     rbx, [rcx]
0x14001c6e9  test    rbx, rbx
0x14001c6ec  jz      loc_14001C77D
0x14001c6f2  call    cs:__imp_KeEnterCriticalRegion
0x14001c6f9  nop     dword ptr [rax+rax+00h]
0x14001c6fe  xor     edx, edx
0x14001c700  lea     rcx, qword_14000A1F8
0x14001c707  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001c70e  nop     dword ptr [rax+rax+00h]
0x14001c713  sub     qword ptr [rbx+50h], 1
0x14001c718  jnz     short loc_14001C784
0x14001c71a  lea     rdx, [rbx+8]; PrefixTableEntry
0x14001c71e  lea     rcx, PrefixTable; PrefixTable
0x14001c725  call    cs:__imp_RtlRemoveUnicodePrefix
0x14001c72c  nop     dword ptr [rax+rax+00h]
0x14001c731  xor     edx, edx
0x14001c733  mov     qword ptr [rbx+20h], 0
0x14001c73b  lea     rcx, qword_14000A1F8
0x14001c742  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001c749  nop     dword ptr [rax+rax+00h]
0x14001c74e  call    cs:__imp_KeLeaveCriticalRegion
0x14001c755  nop     dword ptr [rax+rax+00h]
0x14001c75a  mov     eax, 0FFFFFFFFh
0x14001c75f  lock xadd [rbx+4], eax
0x14001c764  cmp     eax, 1
0x14001c767  jnz     short loc_14001C77D
0x14001c769  mov     edx, 4855754Dh; Tag
0x14001c76e  mov     rcx, rbx; P
0x14001c771  call    cs:__imp_ExFreePoolWithTag
0x14001c778  nop     dword ptr [rax+rax+00h]
0x14001c77d  add     rsp, 20h
0x14001c781  pop     rbx
0x14001c782  retn
0x14001c784  xor     edx, edx
0x14001c786  lea     rcx, qword_14000A1F8
0x14001c78d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001c794  nop     dword ptr [rax+rax+00h]
0x14001c799  call    cs:__imp_KeLeaveCriticalRegion
0x14001c7a0  nop     dword ptr [rax+rax+00h]
0x14001c7a5  jmp     short loc_14001C77D
```
