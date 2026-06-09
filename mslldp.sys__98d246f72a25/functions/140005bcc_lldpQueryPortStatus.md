# lldpQueryPortStatus

- ea: `0x140005bcc`
- end: `0x140005d1a`
- name: `lldpQueryPortStatus`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ec80`
- `0x14000f1c0`

## callees

- `0x140005bcc`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140005c7b`
- `NDIS!NdisReleaseRWLock` at `0x140005cf7`
- `NDIS!NdisReleaseRWLock` at `0x140005c7b`
- `NDIS!NdisReleaseRWLock` at `0x140005cf7`
- `NDIS!NdisAcquireRWLockRead` at `0x140005c4f`
- `NDIS!NdisAcquireRWLockRead` at `0x140005c96`
- `NDIS!NdisAcquireRWLockRead` at `0x140005c4f`
- `NDIS!NdisAcquireRWLockRead` at `0x140005c96`

## pseudocode

```c
__int64 __fastcall lldpQueryPortStatus(__int64 a1, __int64 a2)
{
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  char v6; // al
  __int64 v7; // rcx
  __int16 v8; // ax
  __int64 result; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  _m_prefetchw((const void *)(a1 + 304));
  v4 = *(_DWORD *)(a1 + 304);
  do
  {
    v5 = v4;
    v4 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 304), v4, v4);
  }
  while ( v5 != v4 );
  *(_BYTE *)(a2 + 16) = ~(4 * v4) & 0x18
                      | ~(2 * v4) & 0x20
                      | ~(4 * v4) & 4
                      | (*(_BYTE *)(a2 + 16) & 0xFD ^ (2 * (*(_BYTE *)(a1 + 216) & 1))) & 0xC3;
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 976), &LockState, 0);
  *(_DWORD *)(a2 + 17) = *(_DWORD *)(a1 + 144);
  *(_WORD *)(a2 + 21) = *(_WORD *)(a1 + 148);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 976), &LockState);
  NdisAcquireRWLockRead(*(PNDIS_RW_LOCK_EX *)(a1 + 960), &LockState, 0);
  v6 = *(_BYTE *)(a2 + 16);
  if ( *(_QWORD *)(a1 + 968) )
  {
    *(_BYTE *)(a2 + 16) = v6 | 1;
    v7 = *(_QWORD *)(a1 + 968);
    *(_DWORD *)(a2 + 23) = *(_DWORD *)(v7 + 4);
    v8 = *(_WORD *)(v7 + 8);
  }
  else
  {
    *(_BYTE *)(a2 + 16) = v6 & 0xFE;
    v8 = 0;
    *(_DWORD *)(a2 + 23) = 0;
  }
  *(_WORD *)(a2 + 27) = v8;
  *(_QWORD *)(a2 + 32) = *(_QWORD *)(a1 + 224);
  *(_QWORD *)(a2 + 40) = *(_QWORD *)(a1 + 232);
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 960), &LockState);
  result = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a2 + 48) = result;
  return result;
}

```

## disassembly

```asm
0x140005bcc  mov     [rsp+arg_8], rbx
0x140005bd1  push    rdi
0x140005bd2  sub     rsp, 20h
0x140005bd6  xor     eax, eax
0x140005bd8  mov     rdi, rdx
0x140005bdb  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x140005be0  mov     rbx, rcx
0x140005be3  mov     [rsp+28h+LockState.Flags], al
0x140005be7  prefetchw byte ptr [rcx+130h]
0x140005bee  mov     eax, [rcx+130h]
0x140005bf4  mov     r8d, eax
0x140005bf7  lock cmpxchg [rcx+130h], r8d
0x140005c00  jnz     short loc_140005BF4
0x140005c02  mov     cl, [rdx+10h]
0x140005c05  mov     r8d, eax
0x140005c08  mov     dl, [rbx+0D8h]
0x140005c0e  and     cl, 0FDh
0x140005c11  and     dl, 1
0x140005c14  shl     r8b, 2
0x140005c18  add     dl, dl
0x140005c1a  not     r8b
0x140005c1d  xor     dl, cl
0x140005c1f  and     r8b, 18h
0x140005c23  mov     ecx, eax
0x140005c25  and     dl, 0C3h
0x140005c28  shl     cl, 2
0x140005c2b  add     al, al
0x140005c2d  not     cl
0x140005c2f  not     al
0x140005c31  and     cl, 4
0x140005c34  and     al, 20h
0x140005c36  or      dl, cl
0x140005c38  or      dl, al
0x140005c3a  or      dl, r8b
0x140005c3d  xor     r8d, r8d; Flags
0x140005c40  mov     [rdi+10h], dl
0x140005c43  lea     rdx, [rsp+28h+LockState]; LockState
0x140005c48  mov     rcx, [rbx+3D0h]; Lock
0x140005c4f  call    cs:__imp_NdisAcquireRWLockRead
0x140005c56  nop     dword ptr [rax+rax+00h]
0x140005c5b  mov     eax, [rbx+90h]
0x140005c61  lea     rdx, [rsp+28h+LockState]; LockState
0x140005c66  mov     [rdi+11h], eax
0x140005c69  movzx   eax, word ptr [rbx+94h]
0x140005c70  mov     [rdi+15h], ax
0x140005c74  mov     rcx, [rbx+3D0h]; Lock
0x140005c7b  call    cs:__imp_NdisReleaseRWLock
0x140005c82  nop     dword ptr [rax+rax+00h]
0x140005c87  mov     rcx, [rbx+3C0h]; Lock
0x140005c8e  lea     rdx, [rsp+28h+LockState]; LockState
0x140005c93  xor     r8d, r8d; Flags
0x140005c96  call    cs:__imp_NdisAcquireRWLockRead
0x140005c9d  nop     dword ptr [rax+rax+00h]
0x140005ca2  cmp     qword ptr [rbx+3C8h], 0
0x140005caa  mov     al, [rdi+10h]
0x140005cad  jz      short loc_140005CC7
0x140005caf  or      al, 1
0x140005cb1  mov     [rdi+10h], al
0x140005cb4  mov     rcx, [rbx+3C8h]
0x140005cbb  mov     eax, [rcx+4]
0x140005cbe  mov     [rdi+17h], eax
0x140005cc1  movzx   eax, word ptr [rcx+8]
0x140005cc5  jmp     short loc_140005CD1
0x140005cc7  and     al, 0FEh
0x140005cc9  mov     [rdi+10h], al
0x140005ccc  xor     eax, eax
0x140005cce  mov     [rdi+17h], eax
0x140005cd1  mov     [rdi+1Bh], ax
0x140005cd5  lea     rdx, [rsp+28h+LockState]; LockState
0x140005cda  mov     rax, [rbx+0E0h]
0x140005ce1  mov     [rdi+20h], rax
0x140005ce5  mov     rax, [rbx+0E8h]
0x140005cec  mov     [rdi+28h], rax
0x140005cf0  mov     rcx, [rbx+3C0h]; Lock
0x140005cf7  call    cs:__imp_NdisReleaseRWLock
0x140005cfe  nop     dword ptr [rax+rax+00h]
0x140005d03  mov     rax, [rbx+0F0h]
0x140005d0a  mov     rbx, [rsp+28h+arg_8]
0x140005d0f  mov     [rdi+30h], rax
0x140005d13  add     rsp, 20h
0x140005d17  pop     rdi
0x140005d18  retn
```
