# AddProtocolCBToBundle

- ea: `0x140027404`
- end: `0x1400274cc`
- name: `AddProtocolCBToBundle`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140026c80`

## callees

- `0x140027404`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400274af`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400274af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027423`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027423`

## pseudocode

```c
void __fastcall AddProtocolCBToBundle(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rsi
  _QWORD *v5; // rcx
  int v6; // eax

  v2 = (KSPIN_LOCK *)(a2 + 1768);
  *(_BYTE *)(a2 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 1768));
  v5 = *(_QWORD **)(a2 + 288);
  if ( *v5 != a2 + 280 )
    __fastfail(3u);
  *(_QWORD *)a1 = a2 + 280;
  *(_QWORD *)(a1 + 8) = v5;
  *v5 = a1;
  *(_QWORD *)(a2 + 288) = a1;
  *(_QWORD *)(*(_QWORD *)(a2 + 264) + 8LL * *(_QWORD *)(a1 + 48)) = a1;
  v6 = *(_DWORD *)(a2 + 312);
  ++*(_DWORD *)(a2 + 272);
  *(_DWORD *)(a1 + 108) = v6 + 1;
  *(_DWORD *)(a2 + 312) = (2 * *(_DWORD *)(a2 + 312)) | 1;
  *(_DWORD *)(a1 + 20) = 3;
  if ( !*(_QWORD *)(a2 + 296) )
    *(_QWORD *)(a2 + 296) = a1;
  ++*(_DWORD *)(a2 + 24);
  KeReleaseSpinLock(v2, *(_BYTE *)(a2 + 1776));
}

```

## disassembly

```asm
0x140027404  mov     [rsp+arg_0], rbx
0x140027409  mov     [rsp+arg_8], rsi
0x14002740e  push    rdi
0x14002740f  sub     rsp, 20h
0x140027413  lea     rsi, [rdx+6E8h]
0x14002741a  mov     rdi, rcx
0x14002741d  mov     rcx, rsi; SpinLock
0x140027420  mov     rbx, rdx
0x140027423  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002742a  nop     dword ptr [rax+rax+00h]
0x14002742f  mov     [rbx+6F0h], al
0x140027435  lea     rax, [rbx+118h]
0x14002743c  mov     rcx, [rax+8]
0x140027440  cmp     [rcx], rax
0x140027443  jz      short loc_14002744C
0x140027445  mov     ecx, 3
0x14002744a  int     29h; Win8: RtlFailFast(ecx)
0x14002744c  mov     [rdi], rax
0x14002744f  mov     [rdi+8], rcx
0x140027453  mov     [rcx], rdi
0x140027456  mov     [rax+8], rdi
0x14002745a  mov     rax, [rbx+108h]
0x140027461  mov     rcx, [rdi+30h]
0x140027465  mov     [rax+rcx*8], rdi
0x140027469  mov     eax, [rbx+138h]
0x14002746f  inc     dword ptr [rbx+110h]
0x140027475  inc     eax
0x140027477  mov     [rdi+6Ch], eax
0x14002747a  mov     eax, [rbx+138h]
0x140027480  add     eax, eax
0x140027482  or      eax, 1
0x140027485  mov     [rbx+138h], eax
0x14002748b  mov     dword ptr [rdi+14h], 3
0x140027492  cmp     qword ptr [rbx+128h], 0
0x14002749a  jnz     short loc_1400274A3
0x14002749c  mov     [rbx+128h], rdi
0x1400274a3  inc     dword ptr [rbx+18h]
0x1400274a6  mov     rcx, rsi; SpinLock
0x1400274a9  mov     dl, [rbx+6F0h]; NewIrql
0x1400274af  call    cs:__imp_KeReleaseSpinLock
0x1400274b6  nop     dword ptr [rax+rax+00h]
0x1400274bb  mov     rbx, [rsp+28h+arg_0]
0x1400274c0  mov     rsi, [rsp+28h+arg_8]
0x1400274c5  add     rsp, 20h
0x1400274c9  pop     rdi
0x1400274ca  retn
```
