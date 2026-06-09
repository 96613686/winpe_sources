# PxAllocateVc

- ea: `0x1400162c8`
- end: `0x140016378`
- name: `PxAllocateVc`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f490`
- `0x140013bc0`

## callees

- `0x1400084c0`
- `0x1400162c8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400162dc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400162dc`
- `ntoskrnl!KeInitializeSpinLock` at `0x140016307`
- `ntoskrnl!KeInitializeSpinLock` at `0x140016307`
- `NDIS!NdisInitializeTimer` at `0x140016324`
- `NDIS!NdisInitializeTimer` at `0x140016324`
- `NDIS!NdisInitializeEvent` at `0x140016337`
- `NDIS!NdisInitializeEvent` at `0x140016337`

## pseudocode

```c
char *__fastcall PxAllocateVc(__int64 a1)
{
  char *result; // rax
  char *v3; // rbx

  result = (char *)ExAllocateFromNPagedLookasideList(&VcLookaside);
  v3 = result;
  if ( result )
  {
    memset(result, 0, 0x218u);
    KeInitializeSpinLock((PKSPIN_LOCK)v3 + 64);
    NdisInitializeTimer((PNDIS_TIMER)(v3 + 320), PxIncomingCallTimeout, v3);
    NdisInitializeEvent((PNDIS_EVENT)(v3 + 448));
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 13) = v3 + 96;
    *((_QWORD *)v3 + 12) = v3 + 96;
    *((_DWORD *)v3 + 7) = 1;
    *((_QWORD *)v3 + 7) = a1;
    *((_QWORD *)v3 + 11) = *(_QWORD *)(a1 + 32);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1400162c8  mov     [rsp+arg_0], rbx
0x1400162cd  push    rdi
0x1400162ce  sub     rsp, 20h
0x1400162d2  mov     rdi, rcx
0x1400162d5  lea     rcx, VcLookaside; Lookaside
0x1400162dc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400162e3  nop     dword ptr [rax+rax+00h]
0x1400162e8  mov     rbx, rax
0x1400162eb  test    rax, rax
0x1400162ee  jz      short loc_14001636C
0x1400162f0  xor     edx, edx; Val
0x1400162f2  mov     r8d, 218h; Size
0x1400162f8  mov     rcx, rbx; void *
0x1400162fb  call    memset
0x140016300  lea     rcx, [rbx+200h]; SpinLock
0x140016307  call    cs:__imp_KeInitializeSpinLock
0x14001630e  nop     dword ptr [rax+rax+00h]
0x140016313  lea     rcx, [rbx+140h]; Timer
0x14001631a  mov     r8, rbx; FunctionContext
0x14001631d  lea     rdx, PxIncomingCallTimeout; TimerFunction
0x140016324  call    cs:__imp_NdisInitializeTimer
0x14001632b  nop     dword ptr [rax+rax+00h]
0x140016330  lea     rcx, [rbx+1C0h]; Event
0x140016337  call    cs:__imp_NdisInitializeEvent
0x14001633e  nop     dword ptr [rax+rax+00h]
0x140016343  lea     rax, [rbx+60h]
0x140016347  mov     qword ptr [rbx+10h], 0
0x14001634f  mov     [rax+8], rax
0x140016353  mov     [rax], rax
0x140016356  mov     dword ptr [rbx+1Ch], 1
0x14001635d  mov     [rbx+38h], rdi
0x140016361  mov     rax, [rdi+20h]
0x140016365  mov     [rbx+58h], rax
0x140016369  mov     rax, rbx
0x14001636c  mov     rbx, [rsp+28h+arg_0]
0x140016371  add     rsp, 20h
0x140016375  pop     rdi
0x140016376  retn
```
