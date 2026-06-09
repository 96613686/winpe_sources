# EnqueuePolledReadIrp

- ea: `0x180017ca0`
- end: `0x180017d66`
- name: `EnqueuePolledReadIrp`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800053c0`

## callees

- `0x180017ca0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x180017d47`
- `ntoskrnl!KeReleaseSpinLock` at `0x180017d47`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180017cbf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180017cbf`

## pseudocode

```c
__int64 __fastcall EnqueuePolledReadIrp(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // r9
  unsigned int v6; // ebx
  _QWORD *v7; // rdx
  __int64 v8; // rax

  v2 = (KSPIN_LOCK *)(a1 + 232);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 232));
  _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)PolledReadCancelRoutine);
  if ( !*(_BYTE *)(a2 + 68) )
  {
    v7 = *(_QWORD **)(a1 + 224);
    if ( *v7 != a1 + 216 )
      __fastfail(3u);
    *(_QWORD *)(a2 + 168) = a1 + 216;
    *(_QWORD *)(a2 + 176) = v7;
    *v7 = a2 + 168;
    *(_QWORD *)(a1 + 224) = a2 + 168;
    goto LABEL_8;
  }
  if ( !_InterlockedExchange64((volatile __int64 *)(a2 + 104), 0) )
  {
    *(_QWORD *)(a2 + 176) = a2 + 168;
    *(_QWORD *)(a2 + 168) = a2 + 168;
LABEL_8:
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
    v8 = *(_QWORD *)(a2 + 184);
    v6 = 259;
    *(_BYTE *)(v8 + 3) |= 1u;
    goto LABEL_9;
  }
  v6 = -1073741536;
LABEL_9:
  KeReleaseSpinLock(v2, v5);
  return v6;
}

```

## disassembly

```asm
0x180017ca0  mov     [rsp+arg_0], rbx
0x180017ca5  mov     [rsp+arg_8], rsi
0x180017caa  push    rdi
0x180017cab  sub     rsp, 20h
0x180017caf  lea     rsi, [rcx+0E8h]
0x180017cb6  mov     rdi, rcx
0x180017cb9  mov     rcx, rsi; SpinLock
0x180017cbc  mov     rbx, rdx
0x180017cbf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180017cc6  nop     dword ptr [rax+rax+00h]
0x180017ccb  lea     r8, PolledReadCancelRoutine
0x180017cd2  mov     r9b, al
0x180017cd5  xchg    r8, [rbx+68h]
0x180017cd9  cmp     byte ptr [rbx+44h], 0
0x180017cdd  jz      short loc_180017D01
0x180017cdf  xor     edx, edx
0x180017ce1  xchg    rdx, [rbx+68h]
0x180017ce5  test    rdx, rdx
0x180017ce8  jz      short loc_180017CF1
0x180017cea  mov     ebx, 0C0000120h
0x180017cef  jmp     short loc_180017D41
0x180017cf1  lea     rax, [rbx+0A8h]
0x180017cf8  mov     [rax+8], rax
0x180017cfc  mov     [rax], rax
0x180017cff  jmp     short loc_180017D2D
0x180017d01  lea     rcx, [rdi+0D8h]
0x180017d08  mov     rdx, [rcx+8]
0x180017d0c  cmp     [rdx], rcx
0x180017d0f  jz      short loc_180017D18
0x180017d11  mov     ecx, 3
0x180017d16  int     29h; Win8: RtlFailFast(ecx)
0x180017d18  lea     rax, [rbx+0A8h]
0x180017d1f  mov     [rax], rcx
0x180017d22  mov     [rax+8], rdx
0x180017d26  mov     [rdx], rax
0x180017d29  mov     [rcx+8], rax
0x180017d2d  lock inc dword ptr [rdi+10h]
0x180017d31  mov     rax, [rbx+0B8h]
0x180017d38  mov     ebx, 103h
0x180017d3d  or      byte ptr [rax+3], 1
0x180017d41  mov     dl, r9b; NewIrql
0x180017d44  mov     rcx, rsi; SpinLock
0x180017d47  call    cs:__imp_KeReleaseSpinLock
0x180017d4e  nop     dword ptr [rax+rax+00h]
0x180017d53  mov     rsi, [rsp+28h+arg_8]
0x180017d58  mov     eax, ebx
0x180017d5a  mov     rbx, [rsp+28h+arg_0]
0x180017d5f  add     rsp, 20h
0x180017d63  pop     rdi
0x180017d64  retn
```
