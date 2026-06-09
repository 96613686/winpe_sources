# RemoveLinkFromConnectionTable

- ea: `0x140005880`
- end: `0x140005927`
- name: `RemoveLinkFromConnectionTable`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000550c`

## callees

- `0x140005880`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140005908`
- `NDIS!NdisReleaseRWLock` at `0x140005908`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400058aa`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400058aa`

## pseudocode

```c
void __fastcall RemoveLinkFromConnectionTable(__int64 a1)
{
  __int64 v1; // rbx
  _DWORD *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  _QWORD *v6; // rdx
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(unsigned int *)(a1 + 40);
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(ConnTableLock, &LockState, 0);
  if ( (_DWORD)v1 )
  {
    v3 = ConnectionTable;
    if ( (unsigned int)v1 <= *((_DWORD *)ConnectionTable + 1) )
    {
      v4 = *((_QWORD *)ConnectionTable + 7);
      if ( *(_QWORD *)(v4 + 8 * v1) )
      {
        *(_QWORD *)(v4 + 8 * v1) = 0;
        v5 = *(_QWORD *)(a1 + 256);
        if ( *(_QWORD *)(v5 + 8) != a1 + 256 || (v6 = *(_QWORD **)(a1 + 264), *v6 != a1 + 256) )
          __fastfail(3u);
        *v6 = v5;
        *(_QWORD *)(v5 + 8) = v6;
        --v3[2];
      }
    }
  }
  NdisReleaseRWLock(ConnTableLock, &LockState);
}

```

## disassembly

```asm
0x140005880  mov     [rsp+arg_8], rbx
0x140005885  push    rdi
0x140005886  sub     rsp, 20h
0x14000588a  mov     ebx, [rcx+28h]
0x14000588d  lea     rdx, [rsp+28h+LockState]; LockState
0x140005892  xor     eax, eax
0x140005894  mov     rdi, rcx
0x140005897  mov     rcx, cs:ConnTableLock; Lock
0x14000589e  xor     r8d, r8d; Flags
0x1400058a1  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x1400058a6  mov     [rsp+28h+LockState.Flags], al
0x1400058aa  call    cs:__imp_NdisAcquireRWLockWrite
0x1400058b1  nop     dword ptr [rax+rax+00h]
0x1400058b6  test    ebx, ebx
0x1400058b8  jz      short loc_1400058FC
0x1400058ba  mov     rax, cs:ConnectionTable
0x1400058c1  cmp     ebx, [rax+4]
0x1400058c4  ja      short loc_1400058FC
0x1400058c6  mov     rdx, [rax+38h]
0x1400058ca  cmp     qword ptr [rdx+rbx*8], 0
0x1400058cf  jz      short loc_1400058FC
0x1400058d1  lea     rcx, [rdi+100h]
0x1400058d8  mov     qword ptr [rdx+rbx*8], 0
0x1400058e0  mov     r8, [rcx]
0x1400058e3  cmp     [r8+8], rcx
0x1400058e7  jnz     short loc_140005920
0x1400058e9  mov     rdx, [rcx+8]
0x1400058ed  cmp     [rdx], rcx
0x1400058f0  jnz     short loc_140005920
0x1400058f2  mov     [rdx], r8
0x1400058f5  mov     [r8+8], rdx
0x1400058f9  dec     dword ptr [rax+8]
0x1400058fc  mov     rcx, cs:ConnTableLock; Lock
0x140005903  lea     rdx, [rsp+28h+LockState]; LockState
0x140005908  call    cs:__imp_NdisReleaseRWLock
0x14000590f  nop     dword ptr [rax+rax+00h]
0x140005914  mov     rbx, [rsp+28h+arg_8]
0x140005919  add     rsp, 20h
0x14000591d  pop     rdi
0x14000591e  retn
0x140005920  mov     ecx, 3
0x140005925  int     29h; Win8: RtlFailFast(ecx)
```
