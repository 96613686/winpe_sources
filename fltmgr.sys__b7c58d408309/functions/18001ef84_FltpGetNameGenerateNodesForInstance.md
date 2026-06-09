# FltpGetNameGenerateNodesForInstance

- ea: `0x18001ef84`
- end: `0x18001f094`
- name: `FltpGetNameGenerateNodesForInstance`
- size: `272`
- prototype: `void __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000eb80`
- `0x18005e010`

## callees

- `0x18001ef84`
- `0x180024c00`

## import_xrefs

- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18001efb3`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18001efb3`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18001efde`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18001efde`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001efc3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001efc3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001f074`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001f074`
- `ntoskrnl!ExReleaseFastResource` at `0x18001f068`
- `ntoskrnl!ExReleaseFastResource` at `0x18001f068`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18001f04e`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18001f04e`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001f008`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001f031`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001f008`
- `ntoskrnl!ExAcquireRundownProtectionCacheAwareEx` at `0x18001f031`

## pseudocode

```c
void __fastcall FltpGetNameGenerateNodesForInstance(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // rbx
  __int64 v9; // r8
  _BYTE v10[136]; // [rsp+20h] [rbp-88h] BYREF

  memset(v10, 0, 0x48u);
  v6 = 0;
  v7 = 0;
  ExInitializeFastOwnerEntry(v10);
  v8 = *(_QWORD *)(a1 + 64);
  KeEnterCriticalRegion();
  LOBYTE(v9) = 1;
  ExAcquireFastResourceShared(v8 + 192, v10, v9);
  if ( (*(_DWORD *)(a1 + 80) & 6) == 0 )
  {
    v6 = *(_QWORD *)(a1 + 312);
    if ( v6 )
    {
      if ( !ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v6 + 16) + 56LL), 1u) )
      {
LABEL_7:
        v6 = 0;
        goto LABEL_8;
      }
      v7 = *(_QWORD *)(a1 + 304);
      if ( v7
        && !ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v7 + 16) + 56LL), 1u) )
      {
        v7 = 0;
        ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v6 + 16) + 56LL), 1u);
        goto LABEL_7;
      }
    }
  }
LABEL_8:
  ExReleaseFastResource(v8 + 192, v10);
  KeLeaveCriticalRegion();
  *a2 = v6;
  *a3 = v7;
}

```

## disassembly

```asm
0x18001ef84  push    rbx
0x18001ef86  push    rbp
0x18001ef87  push    rsi
0x18001ef88  push    rdi
0x18001ef89  push    r14
0x18001ef8b  push    r15
0x18001ef8d  sub     rsp, 78h
0x18001ef91  mov     r15, rdx
0x18001ef94  mov     r14, r8
0x18001ef97  xor     edx, edx; Val
0x18001ef99  mov     rbp, rcx
0x18001ef9c  lea     rcx, [rsp+0A8h+var_88]; void *
0x18001efa1  lea     r8d, [rdx+48h]; Size
0x18001efa5  call    memset
0x18001efaa  lea     rcx, [rsp+0A8h+var_88]
0x18001efaf  xor     edi, edi
0x18001efb1  xor     esi, esi
0x18001efb3  call    cs:__imp_ExInitializeFastOwnerEntry
0x18001efba  nop     dword ptr [rax+rax+00h]
0x18001efbf  mov     rbx, [rbp+40h]
0x18001efc3  call    cs:__imp_KeEnterCriticalRegion
0x18001efca  nop     dword ptr [rax+rax+00h]
0x18001efcf  mov     r8b, 1
0x18001efd2  lea     rdx, [rsp+0A8h+var_88]
0x18001efd7  lea     rcx, [rbx+0C0h]
0x18001efde  call    cs:__imp_ExAcquireFastResourceShared
0x18001efe5  nop     dword ptr [rax+rax+00h]
0x18001efea  mov     eax, [rbp+50h]
0x18001efed  test    al, 6
0x18001efef  jnz     short loc_18001F05C
0x18001eff1  mov     rdi, [rbp+138h]
0x18001eff8  test    rdi, rdi
0x18001effb  jz      short loc_18001F05C
0x18001effd  mov     rcx, [rdi+10h]
0x18001f001  lea     edx, [rsi+1]; Count
0x18001f004  mov     rcx, [rcx+38h]; RunRefCacheAware
0x18001f008  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x18001f00f  nop     dword ptr [rax+rax+00h]
0x18001f014  test    al, al
0x18001f016  jz      short loc_18001F05A
0x18001f018  mov     rsi, [rbp+130h]
0x18001f01f  test    rsi, rsi
0x18001f022  jz      short loc_18001F05C
0x18001f024  mov     rcx, [rsi+10h]
0x18001f028  mov     edx, 1; Count
0x18001f02d  mov     rcx, [rcx+38h]; RunRefCacheAware
0x18001f031  call    cs:__imp_ExAcquireRundownProtectionCacheAwareEx
0x18001f038  nop     dword ptr [rax+rax+00h]
0x18001f03d  test    al, al
0x18001f03f  jnz     short loc_18001F05C
0x18001f041  mov     rcx, [rdi+10h]
0x18001f045  xor     esi, esi
0x18001f047  mov     rcx, [rcx+38h]; RunRef
0x18001f04b  lea     edx, [rsi+1]; Count
0x18001f04e  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x18001f055  nop     dword ptr [rax+rax+00h]
0x18001f05a  xor     edi, edi
0x18001f05c  lea     rdx, [rsp+0A8h+var_88]
0x18001f061  lea     rcx, [rbx+0C0h]
0x18001f068  call    cs:__imp_ExReleaseFastResource
0x18001f06f  nop     dword ptr [rax+rax+00h]
0x18001f074  call    cs:__imp_KeLeaveCriticalRegion
0x18001f07b  nop     dword ptr [rax+rax+00h]
0x18001f080  mov     [r15], rdi
0x18001f083  mov     [r14], rsi
0x18001f086  add     rsp, 78h
0x18001f08a  pop     r15
0x18001f08c  pop     r14
0x18001f08e  pop     rdi
0x18001f08f  pop     rsi
0x18001f090  pop     rbp
0x18001f091  pop     rbx
0x18001f092  retn
```
