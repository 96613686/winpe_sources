# BwcAddQoSPolicyToQoSPoliciesHashTable

- ea: `0x140013a30`
- end: `0x140013ad9`
- name: `BwcAddQoSPolicyToQoSPoliciesHashTable`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140011064`

## callees

- `0x140013a30`

## import_xrefs

- `NDIS!NdisReleaseReadWriteLock` at `0x140013abf`
- `NDIS!NdisReleaseReadWriteLock` at `0x140013abf`
- `NDIS!NdisAcquireReadWriteLock` at `0x140013a59`
- `NDIS!NdisAcquireReadWriteLock` at `0x140013a59`

## pseudocode

```c
__int64 __fastcall BwcAddQoSPolicyToQoSPoliciesHashTable(__int64 a1)
{
  int v1; // ebx
  __int64 *v3; // rcx
  __int64 v4; // r8
  __int64 *i; // rdx
  unsigned int v6; // ebx
  _LOCK_STATE LockState; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 12);
  LockState = 0;
  NdisAcquireReadWriteLock(&QoSPoliciesHashTableRWLock, 1u, &LockState);
  v3 = &QoSPoliciesHashListHead[2 * (v1 & 0x1F)];
  v4 = *v3;
  for ( i = (__int64 *)*v3; i != v3; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i - 13) == *(_DWORD *)(a1 + 12) )
    {
      v6 = -1073741270;
      goto LABEL_9;
    }
  }
  if ( *(__int64 **)(v4 + 8) != v3 )
    __fastfail(3u);
  v6 = 0;
  *(_QWORD *)(a1 + 64) = v4;
  *(_QWORD *)(a1 + 72) = v3;
  *(_QWORD *)(v4 + 8) = a1 + 64;
  *v3 = a1 + 64;
LABEL_9:
  NdisReleaseReadWriteLock(&QoSPoliciesHashTableRWLock, &LockState);
  return v6;
}

```

## disassembly

```asm
0x140013a30  mov     [rsp+arg_8], rbx
0x140013a35  push    rdi
0x140013a36  sub     rsp, 20h
0x140013a3a  mov     ebx, [rcx+0Ch]
0x140013a3d  lea     r8, [rsp+28h+LockState]; LockState
0x140013a42  mov     rdi, rcx
0x140013a45  mov     dword ptr [rsp+28h+LockState.LockState], 0
0x140013a4d  lea     rcx, QoSPoliciesHashTableRWLock; Lock
0x140013a54  mov     dl, 1; fWrite
0x140013a56  and     ebx, 1Fh
0x140013a59  call    cs:__imp_NdisAcquireReadWriteLock
0x140013a60  nop     dword ptr [rax+rax+00h]
0x140013a65  lea     rcx, QoSPoliciesHashListHead
0x140013a6c  shl     rbx, 4
0x140013a70  add     rcx, rbx
0x140013a73  mov     r8, [rcx]
0x140013a76  mov     rdx, r8
0x140013a79  cmp     rdx, rcx
0x140013a7c  jz      short loc_140013A92
0x140013a7e  mov     eax, [rdi+0Ch]
0x140013a81  cmp     [rdx-34h], eax
0x140013a84  jz      short loc_140013A8B
0x140013a86  mov     rdx, [rdx]
0x140013a89  jmp     short loc_140013A79
0x140013a8b  mov     ebx, 0C000022Ah
0x140013a90  jmp     short loc_140013AB3
0x140013a92  cmp     [r8+8], rcx
0x140013a96  jz      short loc_140013A9F
0x140013a98  mov     ecx, 3
0x140013a9d  int     29h; Win8: RtlFailFast(ecx)
0x140013a9f  lea     rdx, [rdi+40h]
0x140013aa3  xor     ebx, ebx
0x140013aa5  mov     [rdx], r8
0x140013aa8  mov     [rdx+8], rcx
0x140013aac  mov     [r8+8], rdx
0x140013ab0  mov     [rcx], rdx
0x140013ab3  lea     rdx, [rsp+28h+LockState]; LockState
0x140013ab8  lea     rcx, QoSPoliciesHashTableRWLock; Lock
0x140013abf  call    cs:__imp_NdisReleaseReadWriteLock
0x140013ac6  nop     dword ptr [rax+rax+00h]
0x140013acb  mov     eax, ebx
0x140013acd  mov     rbx, [rsp+28h+arg_8]
0x140013ad2  add     rsp, 20h
0x140013ad6  pop     rdi
0x140013ad7  retn
```
