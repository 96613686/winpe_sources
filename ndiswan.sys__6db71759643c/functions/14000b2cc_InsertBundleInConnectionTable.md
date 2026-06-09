# InsertBundleInConnectionTable

- ea: `0x14000b2cc`
- end: `0x14000b3f3`
- name: `InsertBundleInConnectionTable`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a310`
- `0x140024008`

## callees

- `0x14000b2cc`
- `0x14000c6e0`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x14000b330`
- `NDIS!NdisReleaseRWLock` at `0x14000b3d0`
- `NDIS!NdisReleaseRWLock` at `0x14000b330`
- `NDIS!NdisReleaseRWLock` at `0x14000b3d0`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b2f8`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b2f8`

## pseudocode

```c
__int64 __fastcall InsertBundleInConnectionTable(char *a1)
{
  int v2; // ecx
  _DWORD *v4; // rcx
  __int64 v5; // rbx
  unsigned int v6; // r9d
  unsigned int v7; // esi
  __int64 v8; // r8
  unsigned int v9; // edx
  _DWORD *v10; // rax
  char *v11; // rax
  char **v12; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(ConnTableLock, &LockState, 0);
  v2 = *((_DWORD *)ConnectionTable + 1);
  if ( *((_DWORD *)ConnectionTable + 4) > (unsigned int)(v2 - 1) >> 1
    && (unsigned int)NdisWanCreateConnectionTable((unsigned int)(3 * v2)) )
  {
    NdisReleaseRWLock(ConnTableLock, &LockState);
    return 0;
  }
  else
  {
    v4 = ConnectionTable;
    v5 = *((unsigned int *)ConnectionTable + 5);
    v6 = *((_DWORD *)ConnectionTable + 1);
    v7 = v6;
    v8 = *((_QWORD *)ConnectionTable + 8);
    if ( !(_DWORD)v5 )
      v5 = 1;
    while ( *(_QWORD *)(v8 + 8 * v5) )
    {
      v9 = ((int)v5 + 1) % v6;
      v5 = v9;
      if ( !v9 )
        v5 = 1;
      if ( !--v7 )
        goto LABEL_14;
    }
    v10 = ConnectionTable;
    *(_QWORD *)(v8 + 8 * v5) = a1;
    ++v10[4];
    v11 = (char *)(v10 + 6);
    *((_QWORD *)a1 + 4) = (unsigned int)v5;
    v12 = (char **)*((_QWORD *)v11 + 1);
    if ( *v12 != v11 )
      __fastfail(3u);
    *(_QWORD *)a1 = v11;
    *((_QWORD *)a1 + 1) = v12;
    *v12 = a1;
    *((_QWORD *)v11 + 1) = a1;
    v4[5] = (unsigned int)(v5 + 1) % v4[1];
LABEL_14:
    NdisReleaseRWLock(ConnTableLock, &LockState);
    return v7 != 0 ? (unsigned int)v5 : 0;
  }
}

```

## disassembly

```asm
0x14000b2cc  mov     [rsp+arg_0], rbx
0x14000b2d1  mov     [rsp+arg_10], rsi
0x14000b2d6  push    rdi
0x14000b2d7  sub     rsp, 20h
0x14000b2db  xor     eax, eax
0x14000b2dd  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b2e2  mov     rdi, rcx
0x14000b2e5  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14000b2ea  mov     rcx, cs:ConnTableLock; Lock
0x14000b2f1  xor     r8d, r8d; Flags
0x14000b2f4  mov     [rsp+28h+LockState.Flags], al
0x14000b2f8  call    cs:__imp_NdisAcquireRWLockWrite
0x14000b2ff  nop     dword ptr [rax+rax+00h]
0x14000b304  mov     rdx, cs:ConnectionTable
0x14000b30b  mov     ecx, [rdx+4]
0x14000b30e  lea     eax, [rcx-1]
0x14000b311  shr     eax, 1
0x14000b313  cmp     [rdx+10h], eax
0x14000b316  jbe     short loc_14000B343
0x14000b318  lea     ecx, [rcx+rcx*2]
0x14000b31b  call    NdisWanCreateConnectionTable
0x14000b320  test    eax, eax
0x14000b322  jz      short loc_14000B343
0x14000b324  mov     rcx, cs:ConnTableLock; Lock
0x14000b32b  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b330  call    cs:__imp_NdisReleaseRWLock
0x14000b337  nop     dword ptr [rax+rax+00h]
0x14000b33c  xor     eax, eax
0x14000b33e  jmp     loc_14000B3E2
0x14000b343  mov     rcx, cs:ConnectionTable
0x14000b34a  mov     r10d, 1
0x14000b350  mov     ebx, [rcx+14h]
0x14000b353  test    ebx, ebx
0x14000b355  mov     r9d, [rcx+4]
0x14000b359  mov     esi, r9d
0x14000b35c  mov     r8, [rcx+40h]
0x14000b360  cmovz   ebx, r10d
0x14000b364  cmp     qword ptr [r8+rbx*8], 0
0x14000b369  mov     edx, ebx
0x14000b36b  jz      short loc_14000B384
0x14000b36d  lea     eax, [rbx+1]
0x14000b370  xor     edx, edx
0x14000b372  div     r9d
0x14000b375  test    edx, edx
0x14000b377  mov     ebx, edx
0x14000b379  cmovz   ebx, r10d
0x14000b37d  add     esi, 0FFFFFFFFh
0x14000b380  jnz     short loc_14000B364
0x14000b382  jmp     short loc_14000B3C4
0x14000b384  mov     rax, cs:ConnectionTable
0x14000b38b  mov     [r8+rbx*8], rdi
0x14000b38f  add     [rax+10h], r10d
0x14000b393  add     rax, 18h
0x14000b397  mov     [rdi+20h], rdx
0x14000b39b  mov     rdx, [rax+8]
0x14000b39f  cmp     [rdx], rax
0x14000b3a2  jz      short loc_14000B3AB
0x14000b3a4  mov     ecx, 3
0x14000b3a9  int     29h; Win8: RtlFailFast(ecx)
0x14000b3ab  mov     [rdi], rax
0x14000b3ae  mov     [rdi+8], rdx
0x14000b3b2  mov     [rdx], rdi
0x14000b3b5  xor     edx, edx
0x14000b3b7  mov     [rax+8], rdi
0x14000b3bb  lea     eax, [rbx+1]
0x14000b3be  div     dword ptr [rcx+4]
0x14000b3c1  mov     [rcx+14h], edx
0x14000b3c4  mov     rcx, cs:ConnTableLock; Lock
0x14000b3cb  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b3d0  call    cs:__imp_NdisReleaseRWLock
0x14000b3d7  nop     dword ptr [rax+rax+00h]
0x14000b3dc  neg     esi
0x14000b3de  sbb     eax, eax
0x14000b3e0  and     eax, ebx
0x14000b3e2  mov     rbx, [rsp+28h+arg_0]
0x14000b3e7  mov     rsi, [rsp+28h+arg_10]
0x14000b3ec  add     rsp, 20h
0x14000b3f0  pop     rdi
0x14000b3f1  retn
```
