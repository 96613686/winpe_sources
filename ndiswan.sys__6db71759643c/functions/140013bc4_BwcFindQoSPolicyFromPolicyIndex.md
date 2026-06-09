# BwcFindQoSPolicyFromPolicyIndex

- ea: `0x140013bc4`
- end: `0x140013c44`
- name: `BwcFindQoSPolicyFromPolicyIndex`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140011064`
- `0x140011940`

## callees

- `0x140013bc4`

## import_xrefs

- `NDIS!NdisReleaseReadWriteLock` at `0x140013c29`
- `NDIS!NdisReleaseReadWriteLock` at `0x140013c29`
- `NDIS!NdisAcquireReadWriteLock` at `0x140013be4`
- `NDIS!NdisAcquireReadWriteLock` at `0x140013be4`

## pseudocode

```c
volatile signed __int32 *__fastcall BwcFindQoSPolicyFromPolicyIndex(int a1)
{
  volatile signed __int32 *v2; // rbx
  __int64 *v3; // rdx
  volatile signed __int32 *i; // rcx
  struct _LOCK_STATE LockState; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  LockState = 0;
  NdisAcquireReadWriteLock(&QoSPoliciesHashTableRWLock, 0, &LockState);
  v3 = &QoSPoliciesHashListHead[2 * (a1 & 0x1F)];
  for ( i = (volatile signed __int32 *)*v3; i != (volatile signed __int32 *)v3; i = *(volatile signed __int32 **)i )
  {
    if ( *((_DWORD *)i - 13) == a1 )
    {
      v2 = i - 16;
      _InterlockedIncrement(i - 10);
      break;
    }
  }
  NdisReleaseReadWriteLock(&QoSPoliciesHashTableRWLock, &LockState);
  return v2;
}

```

## disassembly

```asm
0x140013bc4  mov     [rsp+arg_8], rbx
0x140013bc9  push    rdi
0x140013bca  sub     rsp, 20h
0x140013bce  mov     edi, ecx
0x140013bd0  lea     r8, [rsp+28h+LockState]; LockState
0x140013bd5  xor     ebx, ebx
0x140013bd7  lea     rcx, QoSPoliciesHashTableRWLock; Lock
0x140013bde  xor     edx, edx; fWrite
0x140013be0  mov     dword ptr [rsp+28h+LockState.LockState], ebx
0x140013be4  call    cs:__imp_NdisAcquireReadWriteLock
0x140013beb  nop     dword ptr [rax+rax+00h]
0x140013bf0  mov     edx, edi
0x140013bf2  lea     rcx, QoSPoliciesHashListHead
0x140013bf9  and     edx, 1Fh
0x140013bfc  shl     rdx, 4
0x140013c00  add     rdx, rcx
0x140013c03  mov     rcx, [rdx]
0x140013c06  cmp     rcx, rdx
0x140013c09  jz      short loc_140013C1D
0x140013c0b  cmp     [rcx-34h], edi
0x140013c0e  jz      short loc_140013C15
0x140013c10  mov     rcx, [rcx]
0x140013c13  jmp     short loc_140013C06
0x140013c15  lea     rbx, [rcx-40h]
0x140013c19  lock inc dword ptr [rcx-28h]
0x140013c1d  lea     rdx, [rsp+28h+LockState]; LockState
0x140013c22  lea     rcx, QoSPoliciesHashTableRWLock; Lock
0x140013c29  call    cs:__imp_NdisReleaseReadWriteLock
0x140013c30  nop     dword ptr [rax+rax+00h]
0x140013c35  mov     rax, rbx
0x140013c38  mov     rbx, [rsp+28h+arg_8]
0x140013c3d  add     rsp, 20h
0x140013c41  pop     rdi
0x140013c42  retn
```
