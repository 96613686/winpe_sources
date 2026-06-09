# PcpLineDestroy

- ea: `0x140002c1c`
- end: `0x140002d42`
- name: `PcpLineDestroy`
- size: `294`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x1400010e0`
- `0x140001884`
- `0x1400029d0`
- `0x14000d8b8`
- `0x14000eca0`
- `0x14000ee88`
- `0x14001f580`

## callees

- `0x140002500`
- `0x140002c1c`
- `0x140003770`
- `0x140011274`

## import_xrefs

- `NDIS!NdisReleaseRWLock` at `0x140002c7c`
- `NDIS!NdisReleaseRWLock` at `0x140002cab`
- `NDIS!NdisReleaseRWLock` at `0x140002d1a`
- `NDIS!NdisReleaseRWLock` at `0x140002c7c`
- `NDIS!NdisReleaseRWLock` at `0x140002cab`
- `NDIS!NdisReleaseRWLock` at `0x140002d1a`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002c45`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002ce9`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002c45`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002ce9`

## pseudocode

```c
void __fastcall PcpLineDestroy(PVOID P)
{
  struct _NDIS_RW_LOCK_EX *v2; // rcx
  int v3; // eax
  char v4; // si
  _QWORD *v5; // rcx
  PVOID *v6; // rax
  struct _LOCK_STATE_EX LockState; // [rsp+30h] [rbp+8h] BYREF

  *(_WORD *)&LockState.OldIrql = 0;
  v2 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)P + 2);
  LockState.Flags = 0;
  NdisAcquireRWLockWrite(v2, &LockState, 0);
  v3 = *((_DWORD *)P + 61);
  if ( v3 == 2 )
  {
    v4 = 1;
    *((_DWORD *)P + 61) = 0;
    *((_DWORD *)P + 58) |= 1u;
  }
  else
  {
    if ( !v3 )
    {
      NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)P + 2), &LockState);
      return;
    }
    v4 = 0;
    *((_DWORD *)P + 61) = 0;
  }
  NdisReleaseRWLock(*((PNDIS_RW_LOCK_EX *)P + 2), &LockState);
  if ( v4 )
    PcpTcIndicateInterfaceChange((__int64)P, 1073807376);
  if ( *((_WORD *)P + 120) )
    PcpLineFreeId(P);
  NdisAcquireRWLockWrite(PcgLineListLock, &LockState, 0);
  v5 = *(_QWORD **)P;
  if ( *(PVOID *)(*(_QWORD *)P + 8LL) != P || (v6 = (PVOID *)*((_QWORD *)P + 1), *v6 != P) )
    __fastfail(3u);
  *v6 = v5;
  v5[1] = v6;
  NdisReleaseRWLock(PcgLineListLock, &LockState);
  PcpLineDereference(P);
  PcpLineDereference(P);
}

```

## disassembly

```asm
0x140002c1c  mov     [rsp+arg_8], rbx
0x140002c21  mov     [rsp+arg_10], rsi
0x140002c26  push    rdi
0x140002c27  sub     rsp, 20h
0x140002c2b  xor     eax, eax
0x140002c2d  lea     rdx, [rsp+28h+LockState]; LockState
0x140002c32  mov     rbx, rcx
0x140002c35  mov     word ptr [rsp+28h+LockState.OldIrql], ax
0x140002c3a  mov     rcx, [rcx+10h]; Lock
0x140002c3e  xor     r8d, r8d; Flags
0x140002c41  mov     [rsp+28h+LockState.Flags], al
0x140002c45  call    cs:__imp_NdisAcquireRWLockWrite
0x140002c4c  nop     dword ptr [rax+rax+00h]
0x140002c51  mov     eax, [rbx+0F4h]
0x140002c57  xor     edi, edi
0x140002c59  cmp     eax, 2
0x140002c5c  jnz     short loc_140002C6F
0x140002c5e  lea     esi, [rax-1]
0x140002c61  mov     [rbx+0F4h], edi
0x140002c67  or      [rbx+0E8h], esi
0x140002c6d  jmp     short loc_140002CA2
0x140002c6f  test    eax, eax
0x140002c71  jnz     short loc_140002C99
0x140002c73  mov     rcx, [rbx+10h]; Lock
0x140002c77  lea     rdx, [rsp+28h+LockState]; LockState
0x140002c7c  call    cs:__imp_NdisReleaseRWLock
0x140002c83  nop     dword ptr [rax+rax+00h]
0x140002c88  mov     rbx, [rsp+28h+arg_8]
0x140002c8d  mov     rsi, [rsp+28h+arg_10]
0x140002c92  add     rsp, 20h
0x140002c96  pop     rdi
0x140002c97  retn
0x140002c99  mov     sil, dil
0x140002c9c  mov     [rbx+0F4h], edi
0x140002ca2  mov     rcx, [rbx+10h]; Lock
0x140002ca6  lea     rdx, [rsp+28h+LockState]; LockState
0x140002cab  call    cs:__imp_NdisReleaseRWLock
0x140002cb2  nop     dword ptr [rax+rax+00h]
0x140002cb7  test    sil, sil
0x140002cba  jz      short loc_140002CC9
0x140002cbc  mov     edx, 40010010h
0x140002cc1  mov     rcx, rbx
0x140002cc4  call    PcpTcIndicateInterfaceChange
0x140002cc9  cmp     [rbx+0F0h], di
0x140002cd0  jbe     short loc_140002CDA
0x140002cd2  mov     rcx, rbx
0x140002cd5  call    PcpLineFreeId
0x140002cda  mov     rcx, cs:PcgLineListLock; Lock
0x140002ce1  lea     rdx, [rsp+28h+LockState]; LockState
0x140002ce6  xor     r8d, r8d; Flags
0x140002ce9  call    cs:__imp_NdisAcquireRWLockWrite
0x140002cf0  nop     dword ptr [rax+rax+00h]
0x140002cf5  mov     rcx, [rbx]
0x140002cf8  cmp     [rcx+8], rbx
0x140002cfc  jnz     short loc_140002D3B
0x140002cfe  mov     rax, [rbx+8]
0x140002d02  cmp     [rax], rbx
0x140002d05  jnz     short loc_140002D3B
0x140002d07  mov     [rax], rcx
0x140002d0a  lea     rdx, [rsp+28h+LockState]; LockState
0x140002d0f  mov     [rcx+8], rax
0x140002d13  mov     rcx, cs:PcgLineListLock; Lock
0x140002d1a  call    cs:__imp_NdisReleaseRWLock
0x140002d21  nop     dword ptr [rax+rax+00h]
0x140002d26  mov     rcx, rbx; P
0x140002d29  call    PcpLineDereference
0x140002d2e  mov     rcx, rbx; P
0x140002d31  call    PcpLineDereference
0x140002d36  jmp     loc_140002C88
0x140002d3b  mov     ecx, 3
0x140002d40  int     29h; Win8: RtlFailFast(ecx)
```
