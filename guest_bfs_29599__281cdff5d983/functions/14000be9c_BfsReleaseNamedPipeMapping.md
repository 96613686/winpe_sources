# BfsReleaseNamedPipeMapping

- ea: `0x14000be9c`
- end: `0x14000bf6e`
- name: `BfsReleaseNamedPipeMapping`
- size: `210`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002620`
- `0x140002d30`
- `0x140003f70`
- `0x14000b920`

## callees

- `0x14000be9c`
- `0x140012cd4`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bebd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000bebd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bf4a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000bf4a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000bf18`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000bf28`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000bf18`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000bf28`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bef6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bef6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf39`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000beac`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000beac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf56`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000bf56`

## pseudocode

```c
void __fastcall BfsReleaseNamedPipeMapping(__int64 a1, __int64 a2)
{
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(a1, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 24), 0xFFFFFFFF) == 1 && !*(_DWORD *)(a2 + 24) )
  {
    if ( (*(_DWORD *)(a2 + 28) & 1) != 0 )
      BfsRemoveEntryHashTable(*(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 8), (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)a2);
    ExFreePoolWithTag(*(PVOID *)(a2 + 32), 0);
    ExFreePoolWithTag(*(PVOID *)(a2 + 40), 0);
    RtlFreeUnicodeString((PUNICODE_STRING)(a2 + 48));
    RtlFreeUnicodeString((PUNICODE_STRING)(a2 + 64));
    ExFreePoolWithTag((PVOID)a2, 0);
  }
  ExReleasePushLockExclusiveEx(a1, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000be9c  mov     [rsp+arg_0], rbx
0x14000bea1  push    rdi
0x14000bea2  sub     rsp, 20h
0x14000bea6  mov     rbx, rdx
0x14000bea9  mov     rdi, rcx
0x14000beac  call    cs:__imp_KeEnterCriticalRegion
0x14000beb3  nop     dword ptr [rax+rax+00h]
0x14000beb8  xor     edx, edx
0x14000beba  mov     rcx, rdi
0x14000bebd  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000bec4  nop     dword ptr [rax+rax+00h]
0x14000bec9  or      eax, 0FFFFFFFFh
0x14000becc  lock xadd [rbx+18h], eax
0x14000bed1  cmp     eax, 1
0x14000bed4  jnz     short loc_14000BF45
0x14000bed6  mov     eax, [rbx+18h]
0x14000bed9  test    eax, eax
0x14000bedb  jnz     short loc_14000BF45
0x14000bedd  mov     eax, [rbx+1Ch]
0x14000bee0  test    al, 1
0x14000bee2  jz      short loc_14000BEF0
0x14000bee4  mov     rcx, [rdi+8]
0x14000bee8  mov     rdx, rbx
0x14000beeb  call    BfsRemoveEntryHashTable
0x14000bef0  mov     rcx, [rbx+20h]; P
0x14000bef4  xor     edx, edx; Tag
0x14000bef6  call    cs:__imp_ExFreePoolWithTag
0x14000befd  nop     dword ptr [rax+rax+00h]
0x14000bf02  mov     rcx, [rbx+28h]; P
0x14000bf06  xor     edx, edx; Tag
0x14000bf08  call    cs:__imp_ExFreePoolWithTag
0x14000bf0f  nop     dword ptr [rax+rax+00h]
0x14000bf14  lea     rcx, [rbx+30h]; UnicodeString
0x14000bf18  call    cs:__imp_RtlFreeUnicodeString
0x14000bf1f  nop     dword ptr [rax+rax+00h]
0x14000bf24  lea     rcx, [rbx+40h]; UnicodeString
0x14000bf28  call    cs:__imp_RtlFreeUnicodeString
0x14000bf2f  nop     dword ptr [rax+rax+00h]
0x14000bf34  xor     edx, edx; Tag
0x14000bf36  mov     rcx, rbx; P
0x14000bf39  call    cs:__imp_ExFreePoolWithTag
0x14000bf40  nop     dword ptr [rax+rax+00h]
0x14000bf45  xor     edx, edx
0x14000bf47  mov     rcx, rdi
0x14000bf4a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000bf51  nop     dword ptr [rax+rax+00h]
0x14000bf56  call    cs:__imp_KeLeaveCriticalRegion
0x14000bf5d  nop     dword ptr [rax+rax+00h]
0x14000bf62  mov     rbx, [rsp+28h+arg_0]
0x14000bf67  add     rsp, 20h
0x14000bf6b  pop     rdi
0x14000bf6c  retn
```
