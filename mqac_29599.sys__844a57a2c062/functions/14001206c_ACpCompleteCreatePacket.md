# ACpCompleteCreatePacket

- ea: `0x14001206c`
- end: `0x1400120db`
- name: `ACpCompleteCreatePacket`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140011e00`
- `0x1400120e4`

## callees

- `0x140012754`
- `0x140017694`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140012083`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012083`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140012093`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140012093`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400120b9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400120b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400120c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400120c5`

## pseudocode

```c
void __fastcall ACpCompleteCreatePacket(__int64 a1, CPacket *a2, int a3, unsigned __int16 a4)
{
  __int64 v4; // rsi

  v4 = *(_QWORD *)(a1 + 64);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v4 + 8));
  CPacket::HandleCreatePacketCompleted(a2, a3, a4);
  CBaseObject::Release(a2);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v4 + 8));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14001206c  push    rbx
0x14001206e  push    rbp
0x14001206f  push    rsi
0x140012070  push    rdi
0x140012071  sub     rsp, 28h
0x140012075  mov     rsi, [rcx+40h]
0x140012079  movzx   ebx, r9w
0x14001207d  mov     edi, r8d
0x140012080  mov     rbp, rdx
0x140012083  call    cs:__imp_KeEnterCriticalRegion
0x14001208a  nop     dword ptr [rax+rax+00h]
0x14001208f  lea     rcx, [rsi+8]; FastMutex
0x140012093  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14001209a  nop     dword ptr [rax+rax+00h]
0x14001209f  movzx   r8d, bx; unsigned __int16
0x1400120a3  mov     edx, edi; int
0x1400120a5  mov     rcx, rbp; this
0x1400120a8  call    ?HandleCreatePacketCompleted@CPacket@@QEAAXJG@Z; CPacket::HandleCreatePacketCompleted(long,ushort)
0x1400120ad  mov     rcx, rbp; this
0x1400120b0  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x1400120b5  lea     rcx, [rsi+8]; FastMutex
0x1400120b9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400120c0  nop     dword ptr [rax+rax+00h]
0x1400120c5  call    cs:__imp_KeLeaveCriticalRegion
0x1400120cc  nop     dword ptr [rax+rax+00h]
0x1400120d1  add     rsp, 28h
0x1400120d5  pop     rdi
0x1400120d6  pop     rsi
0x1400120d7  pop     rbp
0x1400120d8  pop     rbx
0x1400120d9  retn
```
