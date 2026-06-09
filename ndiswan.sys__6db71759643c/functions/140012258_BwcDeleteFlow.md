# BwcDeleteFlow

- ea: `0x140012258`
- end: `0x140012313`
- name: `BwcDeleteFlow`
- size: `187`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140013ae0`

## callees

- `0x140011d7c`
- `0x140012258`
- `0x1400141c0`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x1400122dc`
- `NDIS!NdisReleaseRWLock` at `0x1400122dc`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400122b7`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400122b7`

## pseudocode

```c
__int64 __fastcall BwcDeleteFlow(PVOID P)
{
  int v2; // ecx
  PNDIS_RW_LOCK_EX *v3; // rbx
  struct _NDIS_RW_LOCK_EX *v4; // rcx
  __int64 result; // rax
  _DWORD v6[4]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v7; // [rsp+30h] [rbp-10h]
  __int64 v8; // [rsp+38h] [rbp-8h]
  struct _LOCK_STATE_EX LockState; // [rsp+50h] [rbp+10h] BYREF

  v8 = 1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v2 = *((_DWORD *)P + 90);
  v7 = 0;
  if ( (unsigned int)(v2 - 1) <= 0x270F )
  {
    v3 = (PNDIS_RW_LOCK_EX *)BwcVirtualLine;
    v6[0] = v2;
    v6[1] = 0;
    v6[2] = -v2;
    v4 = *(struct _NDIS_RW_LOCK_EX **)BwcVirtualLine;
    v6[3] = -1;
    NdisAcquireRWLockWrite(v4, &LockState, 0);
    QosLineUpdate(v3 + 1, 0, 0, v6);
    NdisReleaseRWLock(*v3, &LockState);
  }
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)P + 122);
  if ( (_DWORD)result == 1 )
    return BwcCleanupFlow(P);
  return result;
}

```

## disassembly

```asm
0x140012258  mov     [rsp-8+arg_8], rbx
0x14001225d  mov     [rsp-8+arg_10], rdi
0x140012262  push    rbp
0x140012263  mov     rbp, rsp
0x140012266  sub     rsp, 40h
0x14001226a  xor     eax, eax
0x14001226c  mov     [rbp+var_8], 1
0x140012274  xor     edx, edx
0x140012276  mov     word ptr [rbp+LockState.OldIrql], ax
0x14001227a  mov     rdi, rcx
0x14001227d  mov     [rbp+LockState.Flags], al
0x140012280  mov     ecx, [rcx+168h]
0x140012286  mov     [rbp+var_10], rdx
0x14001228a  lea     eax, [rcx-1]
0x14001228d  cmp     eax, 270Fh
0x140012292  ja      short loc_1400122E8
0x140012294  mov     rbx, cs:BwcVirtualLine
0x14001229b  xor     r8d, r8d; Flags
0x14001229e  mov     [rbp+var_20], ecx
0x1400122a1  neg     ecx
0x1400122a3  mov     [rbp+var_1C], edx
0x1400122a6  lea     rdx, [rbp+LockState]; LockState
0x1400122aa  mov     [rbp+var_18], ecx
0x1400122ad  mov     rcx, [rbx]; Lock
0x1400122b0  mov     [rbp+var_14], 0FFFFFFFFh
0x1400122b7  call    cs:__imp_NdisAcquireRWLockWrite
0x1400122be  nop     dword ptr [rax+rax+00h]
0x1400122c3  lea     rcx, [rbx+8]
0x1400122c7  xor     r8d, r8d
0x1400122ca  lea     r9, [rbp+var_20]
0x1400122ce  xor     edx, edx
0x1400122d0  call    QosLineUpdate
0x1400122d5  mov     rcx, [rbx]; Lock
0x1400122d8  lea     rdx, [rbp+LockState]; LockState
0x1400122dc  call    cs:__imp_NdisReleaseRWLock
0x1400122e3  nop     dword ptr [rax+rax+00h]
0x1400122e8  or      eax, 0FFFFFFFFh
0x1400122eb  lock xadd [rdi+1E8h], eax
0x1400122f3  dec     eax
0x1400122f5  cmp     eax, 1
0x1400122f8  jnz     short loc_140012302
0x1400122fa  mov     rcx, rdi; P
0x1400122fd  call    BwcCleanupFlow
0x140012302  mov     rbx, [rsp+40h+arg_8]
0x140012307  mov     rdi, [rsp+40h+arg_10]
0x14001230c  add     rsp, 40h
0x140012310  pop     rbp
0x140012311  retn
```
