# UlCleanupDelegationConsumer

- ea: `0x1400b3bcc`
- end: `0x1400b3d17`
- name: `UlCleanupDelegationConsumer`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140062ad0`

## callees

- `0x14000a350`
- `0x140060ddc`
- `0x14009620c`
- `0x1400a031c`
- `0x1400b3bcc`
- `0x1400b3d20`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b3c44`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1400b3c44`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400b3c19`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1400b3c19`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b3c50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b3c78`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b3c50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400b3c78`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b3c6c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400b3c6c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b3bfa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b3bfa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b3bde`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b3c06`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b3bde`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b3c06`

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
0x1400b3bcc  push    rbx
0x1400b3bce  push    rbp
0x1400b3bcf  push    rsi
0x1400b3bd0  push    rdi
0x1400b3bd1  sub     rsp, 28h
0x1400b3bd5  mov     rbp, r8
0x1400b3bd8  mov     rsi, rdx
0x1400b3bdb  mov     rdi, rcx
0x1400b3bde  call    cs:__imp_KeEnterCriticalRegion
0x1400b3be5  nop     dword ptr [rax+rax+00h]
0x1400b3bea  mov     rcx, [rsi+148h]
0x1400b3bf1  xor     edx, edx
0x1400b3bf3  add     rcx, 1030h
0x1400b3bfa  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400b3c01  nop     dword ptr [rax+rax+00h]
0x1400b3c06  call    cs:__imp_KeEnterCriticalRegion
0x1400b3c0d  nop     dword ptr [rax+rax+00h]
0x1400b3c12  mov     rcx, [rsi+118h]
0x1400b3c19  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1400b3c20  nop     dword ptr [rax+rax+00h]
0x1400b3c25  mov     rcx, rbp
0x1400b3c28  call    UlpAttemptDetachFromRequestQueue
0x1400b3c2d  mov     rcx, rsi
0x1400b3c30  mov     word ptr [rbp+4], 101h
0x1400b3c36  call    UlpAttemptRequestQueueCleanup
0x1400b3c3b  mov     rcx, [rsi+118h]
0x1400b3c42  mov     bl, al
0x1400b3c44  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1400b3c4b  nop     dword ptr [rax+rax+00h]
0x1400b3c50  call    cs:__imp_KeLeaveCriticalRegion
0x1400b3c57  nop     dword ptr [rax+rax+00h]
0x1400b3c5c  mov     rcx, [rsi+148h]
0x1400b3c63  xor     edx, edx
0x1400b3c65  add     rcx, 1030h
0x1400b3c6c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400b3c73  nop     dword ptr [rax+rax+00h]
0x1400b3c78  call    cs:__imp_KeLeaveCriticalRegion
0x1400b3c7f  nop     dword ptr [rax+rax+00h]
0x1400b3c84  mov     rcx, [rdi+0B8h]
0x1400b3c8b  or      byte ptr [rcx+3], 1
0x1400b3c8f  mov     dword ptr [rdi+30h], 103h
0x1400b3c96  mov     [rbp+20h], rdi
0x1400b3c9a  or      edi, 0FFFFFFFFh
0x1400b3c9d  test    bl, bl
0x1400b3c9f  jz      short loc_1400B3CD5
0x1400b3ca1  mov     eax, edi
0x1400b3ca3  lock xadd [rsi], eax
0x1400b3ca7  add     eax, edi
0x1400b3ca9  cmp     cs:UxDebugCheckRefcount, 0
0x1400b3cb0  jz      short loc_1400B3CC9
0x1400b3cb2  cmp     eax, edi
0x1400b3cb4  jg      short loc_1400B3CC9
0x1400b3cb6  movsxd  r9, eax; BugCheckParameter4
0x1400b3cb9  lea     r8d, [rdi+2]; BugCheckParameter3
0x1400b3cbd  mov     rdx, rsi; BugCheckParameter2
0x1400b3cc0  lea     ecx, [rdi+4]; BugCheckParameter1
0x1400b3cc3  call    UlBugCheckEx
0x1400b3cc9  test    eax, eax
0x1400b3ccb  jnz     short loc_1400B3CD5
0x1400b3ccd  mov     rcx, rsi; P
0x1400b3cd0  call    UlFreeRequestQueue
0x1400b3cd5  mov     eax, edi
0x1400b3cd7  lock xadd [rbp+0], eax
0x1400b3cdc  add     eax, edi
0x1400b3cde  cmp     cs:UxDebugCheckRefcount, 0
0x1400b3ce5  jz      short loc_1400B3D01
0x1400b3ce7  cmp     eax, edi
0x1400b3ce9  jg      short loc_1400B3D01
0x1400b3ceb  mov     r8d, 1; BugCheckParameter3
0x1400b3cf1  movsxd  r9, eax; BugCheckParameter4
0x1400b3cf4  mov     rdx, rbp; BugCheckParameter2
0x1400b3cf7  lea     ecx, [r8+2]; BugCheckParameter1
0x1400b3cfb  call    UlBugCheckEx
0x1400b3d01  test    eax, eax
0x1400b3d03  jnz     short loc_1400B3D0D
0x1400b3d05  mov     rcx, rbp
0x1400b3d08  call    UlConsumerCleanupCompletion
0x1400b3d0d  add     rsp, 28h
0x1400b3d11  pop     rdi
0x1400b3d12  pop     rsi
0x1400b3d13  pop     rbp
0x1400b3d14  pop     rbx
0x1400b3d15  retn
```
