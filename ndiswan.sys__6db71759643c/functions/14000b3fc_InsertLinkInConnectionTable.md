# InsertLinkInConnectionTable

- ea: `0x14000b3fc`
- end: `0x14000b532`
- name: `InsertLinkInConnectionTable`
- size: `310`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a310`
- `0x140024008`

## callees

- `0x14000b3fc`
- `0x14000c6e0`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x14000b463`
- `NDIS!NdisReleaseRWLock` at `0x14000b50f`
- `NDIS!NdisReleaseRWLock` at `0x14000b463`
- `NDIS!NdisReleaseRWLock` at `0x14000b50f`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b428`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b428`

## pseudocode

```c
__int64 __fastcall InsertLinkInConnectionTable(_QWORD *a1)
{
  int v2; // r8d
  _DWORD *v4; // rcx
  __int64 v5; // rbx
  unsigned int v6; // r8d
  unsigned int v7; // edi
  __int64 v8; // r9
  unsigned int v9; // eax
  _QWORD *v10; // rax
  PVOID *v11; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+38h] [rbp+10h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(ConnTableLock, &LockState, 0);
  v2 = *((_DWORD *)ConnectionTable + 1);
  if ( *((_DWORD *)ConnectionTable + 2) > (unsigned int)(v2 - 1) >> 1
    && (unsigned int)NdisWanCreateConnectionTable((unsigned int)(3 * v2)) )
  {
    NdisReleaseRWLock(ConnTableLock, &LockState);
    return 0;
  }
  else
  {
    v4 = ConnectionTable;
    v5 = *((unsigned int *)ConnectionTable + 3);
    v6 = *((_DWORD *)ConnectionTable + 1);
    v7 = v6;
    v8 = *((_QWORD *)ConnectionTable + 7);
    if ( !(_DWORD)v5 )
      v5 = 1;
    while ( 1 )
    {
      v9 = v5 + 1;
      if ( !*(_QWORD *)(v8 + 8 * v5) )
        break;
      v5 = v9 % v6;
      if ( !(v9 % v6) )
        v5 = 1;
      if ( !--v7 )
        goto LABEL_14;
    }
    *(_QWORD *)(v8 + 8 * v5) = a1;
    a1[5] = (unsigned int)v5;
    v4[3] = v9 % v4[1];
    _InterlockedAdd(&glLinkCount, 1u);
    v10 = ConnectionTable;
    ++*((_DWORD *)ConnectionTable + 2);
    v11 = (PVOID *)v10[6];
    if ( *v11 != v10 + 5 )
      __fastfail(3u);
    a1[32] = v10 + 5;
    a1[33] = v11;
    *v11 = a1 + 32;
    v10[6] = a1 + 32;
LABEL_14:
    NdisReleaseRWLock(ConnTableLock, &LockState);
    return v7 != 0 ? (unsigned int)v5 : 0;
  }
}

```

## disassembly

```asm
0x14000b3fc  mov     [rsp+arg_0], rbx
0x14000b401  mov     [rsp+arg_10], rsi
0x14000b406  push    rdi
0x14000b407  sub     rsp, 20h
0x14000b40b  xor     eax, eax
0x14000b40d  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b412  mov     rsi, rcx
0x14000b415  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x14000b41a  mov     rcx, cs:ConnTableLock; Lock
0x14000b421  xor     r8d, r8d; Flags
0x14000b424  mov     [rsp+28h+LockState.Flags], al
0x14000b428  call    cs:__imp_NdisAcquireRWLockWrite
0x14000b42f  nop     dword ptr [rax+rax+00h]
0x14000b434  mov     rdx, cs:ConnectionTable
0x14000b43b  mov     r8d, [rdx+4]
0x14000b43f  lea     eax, [r8-1]
0x14000b443  shr     eax, 1
0x14000b445  cmp     [rdx+8], eax
0x14000b448  jbe     short loc_14000B476
0x14000b44a  lea     ecx, [r8+r8*2]
0x14000b44e  call    NdisWanCreateConnectionTable
0x14000b453  test    eax, eax
0x14000b455  jz      short loc_14000B476
0x14000b457  mov     rcx, cs:ConnTableLock; Lock
0x14000b45e  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b463  call    cs:__imp_NdisReleaseRWLock
0x14000b46a  nop     dword ptr [rax+rax+00h]
0x14000b46f  xor     eax, eax
0x14000b471  jmp     loc_14000B521
0x14000b476  mov     rcx, cs:ConnectionTable
0x14000b47d  mov     r10d, 1
0x14000b483  mov     ebx, [rcx+0Ch]
0x14000b486  test    ebx, ebx
0x14000b488  mov     r8d, [rcx+4]
0x14000b48c  mov     edi, r8d
0x14000b48f  mov     r9, [rcx+38h]
0x14000b493  cmovz   ebx, r10d
0x14000b497  cmp     qword ptr [r9+rbx*8], 0
0x14000b49c  lea     eax, [rbx+1]
0x14000b49f  mov     edx, ebx
0x14000b4a1  jz      short loc_14000B4B7
0x14000b4a3  xor     edx, edx
0x14000b4a5  div     r8d
0x14000b4a8  test    edx, edx
0x14000b4aa  mov     ebx, edx
0x14000b4ac  cmovz   ebx, r10d
0x14000b4b0  add     edi, 0FFFFFFFFh
0x14000b4b3  jnz     short loc_14000B497
0x14000b4b5  jmp     short loc_14000B503
0x14000b4b7  mov     [r9+rbx*8], rsi
0x14000b4bb  mov     [rsi+28h], rdx
0x14000b4bf  xor     edx, edx
0x14000b4c1  div     dword ptr [rcx+4]
0x14000b4c4  mov     [rcx+0Ch], edx
0x14000b4c7  lock add cs:glLinkCount, r10d
0x14000b4cf  mov     rax, cs:ConnectionTable
0x14000b4d6  add     [rax+8], r10d
0x14000b4da  lea     rcx, [rax+28h]
0x14000b4de  mov     rdx, [rcx+8]
0x14000b4e2  cmp     [rdx], rcx
0x14000b4e5  jz      short loc_14000B4EE
0x14000b4e7  mov     ecx, 3
0x14000b4ec  int     29h; Win8: RtlFailFast(ecx)
0x14000b4ee  lea     rax, [rsi+100h]
0x14000b4f5  mov     [rax], rcx
0x14000b4f8  mov     [rax+8], rdx
0x14000b4fc  mov     [rdx], rax
0x14000b4ff  mov     [rcx+8], rax
0x14000b503  mov     rcx, cs:ConnTableLock; Lock
0x14000b50a  lea     rdx, [rsp+28h+LockState]; LockState
0x14000b50f  call    cs:__imp_NdisReleaseRWLock
0x14000b516  nop     dword ptr [rax+rax+00h]
0x14000b51b  neg     edi
0x14000b51d  sbb     eax, eax
0x14000b51f  and     eax, ebx
0x14000b521  mov     rbx, [rsp+28h+arg_0]
0x14000b526  mov     rsi, [rsp+28h+arg_10]
0x14000b52b  add     rsp, 20h
0x14000b52f  pop     rdi
0x14000b530  retn
```
