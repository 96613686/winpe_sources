# UlCleanupDelegationConsumer

- ea: `0x1400b3cac`
- end: `0x1400b3df7`
- name: `UlCleanupDelegationConsumer`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140062af0`

## callees

- `0x14000a350`
- `0x140060dfc`
- `0x14009622c`
- `0x1400a033c`
- `0x1400b3cac`
- `0x1400b3e00`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b3d24`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b3d24`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400b3cf9`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400b3cf9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b3d30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b3d58`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b3d30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b3d58`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b3d4c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b3d4c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b3cda`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b3cda`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b3cbe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b3ce6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b3cbe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b3ce6`

## pseudocode

```c
__int64 __fastcall UlCleanupDelegationConsumer(__int64 a1, ULONG_PTR a2, ULONG_PTR a3)
{
  char v6; // bl
  int v7; // eax
  __int64 result; // rax

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 328) + 4144LL, 0);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
  UlpAttemptDetachFromRequestQueue(a3);
  *(_WORD *)(a3 + 4) = 257;
  v6 = UlpAttemptRequestQueueCleanup(a2);
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*(_QWORD *)(a2 + 328) + 4144LL, 0);
  KeLeaveCriticalRegion();
  *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
  *(_DWORD *)(a1 + 48) = 259;
  *(_QWORD *)(a3 + 32) = a1;
  if ( v6 )
  {
    v7 = _InterlockedDecrement((volatile signed __int32 *)a2);
    if ( UxDebugCheckRefcount && v7 <= -1 )
      UlBugCheckEx(3u, a2, 1u, v7);
    if ( !v7 )
      UlFreeRequestQueue((PSECURITY_DESCRIPTOR *)a2);
  }
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)a3);
  if ( UxDebugCheckRefcount && (int)result <= -1 )
    UlBugCheckEx(3u, a3, 1u, (int)result);
  if ( !(_DWORD)result )
    return UlConsumerCleanupCompletion(a3);
  return result;
}

```

## disassembly

```asm
0x1400b3cac  push    rbx
0x1400b3cae  push    rbp
0x1400b3caf  push    rsi
0x1400b3cb0  push    rdi
0x1400b3cb1  sub     rsp, 28h
0x1400b3cb5  mov     rbp, r8
0x1400b3cb8  mov     rsi, rdx
0x1400b3cbb  mov     rdi, rcx
0x1400b3cbe  call    cs:__imp_KeEnterCriticalRegion
0x1400b3cc5  nop     dword ptr [rax+rax+00h]
0x1400b3cca  mov     rcx, [rsi+148h]
0x1400b3cd1  xor     edx, edx
0x1400b3cd3  add     rcx, 1030h
0x1400b3cda  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400b3ce1  nop     dword ptr [rax+rax+00h]
0x1400b3ce6  call    cs:__imp_KeEnterCriticalRegion
0x1400b3ced  nop     dword ptr [rax+rax+00h]
0x1400b3cf2  mov     rcx, [rsi+118h]
0x1400b3cf9  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400b3d00  nop     dword ptr [rax+rax+00h]
0x1400b3d05  mov     rcx, rbp
0x1400b3d08  call    UlpAttemptDetachFromRequestQueue
0x1400b3d0d  mov     rcx, rsi
0x1400b3d10  mov     word ptr [rbp+4], 101h
0x1400b3d16  call    UlpAttemptRequestQueueCleanup
0x1400b3d1b  mov     rcx, [rsi+118h]
0x1400b3d22  mov     bl, al
0x1400b3d24  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400b3d2b  nop     dword ptr [rax+rax+00h]
0x1400b3d30  call    cs:__imp_KeLeaveCriticalRegion
0x1400b3d37  nop     dword ptr [rax+rax+00h]
0x1400b3d3c  mov     rcx, [rsi+148h]
0x1400b3d43  xor     edx, edx
0x1400b3d45  add     rcx, 1030h
0x1400b3d4c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400b3d53  nop     dword ptr [rax+rax+00h]
0x1400b3d58  call    cs:__imp_KeLeaveCriticalRegion
0x1400b3d5f  nop     dword ptr [rax+rax+00h]
0x1400b3d64  mov     rcx, [rdi+0B8h]
0x1400b3d6b  or      byte ptr [rcx+3], 1
0x1400b3d6f  mov     dword ptr [rdi+30h], 103h
0x1400b3d76  mov     [rbp+20h], rdi
0x1400b3d7a  or      edi, 0FFFFFFFFh
0x1400b3d7d  test    bl, bl
0x1400b3d7f  jz      short loc_1400B3DB5
0x1400b3d81  mov     eax, edi
0x1400b3d83  lock xadd [rsi], eax
0x1400b3d87  add     eax, edi
0x1400b3d89  cmp     cs:UxDebugCheckRefcount, 0
0x1400b3d90  jz      short loc_1400B3DA9
0x1400b3d92  cmp     eax, edi
0x1400b3d94  jg      short loc_1400B3DA9
0x1400b3d96  movsxd  r9, eax; BugCheckParameter4
0x1400b3d99  lea     r8d, [rdi+2]; BugCheckParameter3
0x1400b3d9d  mov     rdx, rsi; BugCheckParameter2
0x1400b3da0  lea     ecx, [rdi+4]; BugCheckParameter1
0x1400b3da3  call    UlBugCheckEx
0x1400b3da9  test    eax, eax
0x1400b3dab  jnz     short loc_1400B3DB5
0x1400b3dad  mov     rcx, rsi; P
0x1400b3db0  call    UlFreeRequestQueue
0x1400b3db5  mov     eax, edi
0x1400b3db7  lock xadd [rbp+0], eax
0x1400b3dbc  add     eax, edi
0x1400b3dbe  cmp     cs:UxDebugCheckRefcount, 0
0x1400b3dc5  jz      short loc_1400B3DE1
0x1400b3dc7  cmp     eax, edi
0x1400b3dc9  jg      short loc_1400B3DE1
0x1400b3dcb  mov     r8d, 1; BugCheckParameter3
0x1400b3dd1  movsxd  r9, eax; BugCheckParameter4
0x1400b3dd4  mov     rdx, rbp; BugCheckParameter2
0x1400b3dd7  lea     ecx, [r8+2]; BugCheckParameter1
0x1400b3ddb  call    UlBugCheckEx
0x1400b3de1  test    eax, eax
0x1400b3de3  jnz     short loc_1400B3DED
0x1400b3de5  mov     rcx, rbp
0x1400b3de8  call    UlConsumerCleanupCompletion
0x1400b3ded  add     rsp, 28h
0x1400b3df1  pop     rdi
0x1400b3df2  pop     rsi
0x1400b3df3  pop     rbp
0x1400b3df4  pop     rbx
0x1400b3df5  retn
```
