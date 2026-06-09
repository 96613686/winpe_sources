# VctCompleteConnectRequest

- ea: `0x14002d150`
- end: `0x14002d30b`
- name: `VctCompleteConnectRequest`
- size: `443`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14002d150`
- `0x140038158`
- `0x140059ea0`
- `0x140092280`
- `0x140094990`
- `0x140094f90`

## import_xrefs

- `ntoskrnl!PsDereferenceSiloContext` at `0x14002d2e1`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14002d2e1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002d249`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002d249`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002d209`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002d209`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002d218`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002d218`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d2a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d2c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d2f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d2a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d2c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002d2f5`

## pseudocode

```c
__int64 __fastcall VctCompleteConnectRequest(char *P)
{
  int v2; // ebp
  __int64 v3; // r15
  __int64 *UnavailableServerListForDeviceSilo; // rax
  __int64 v5; // rdi
  __int64 v6; // rdi
  KIRQL v7; // bl
  int v8; // eax
  void *v9; // rcx
  void *v10; // rcx

  v2 = *(_DWORD *)P;
  v3 = *((_QWORD *)P + 15);
  if ( !*(_DWORD *)P )
  {
    *(_WORD *)(*((_QWORD *)P + 10) + 334LL) = *((_WORD *)P + 72);
    *(_WORD *)(*((_QWORD *)P + 10) + 332LL) = *((_WORD *)P + 73);
    if ( !*(_QWORD *)(*((_QWORD *)P + 10) + 32LL) || (v2 = VctCompleteInitialization(), v2 >= 0) )
      *((_QWORD *)P + 10) = 0;
  }
  if ( !P[112] )
  {
    UnavailableServerListForDeviceSilo = (__int64 *)SmbCeGetUnavailableServerListForDeviceSilo(
                                                      *((_QWORD *)P + 16),
                                                      *((_QWORD *)P + 17));
    SmbCeUpdateServerAvailability(UnavailableServerListForDeviceSilo, (const UNICODE_STRING *)(P + 152), v2, 1);
  }
  v5 = *((_QWORD *)P + 10);
  if ( v5 )
  {
    v6 = *(_QWORD *)(v5 + 24);
    v7 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920));
    *(_DWORD *)(v6 + 2352) = (unsigned int)PsGetCurrentThreadId();
    *(_QWORD *)(*((_QWORD *)P + 10) + 384LL) = 0;
    *(_DWORD *)(v6 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920), v7);
    VctDisconnectAndDereferenceEndpoint(*((PVOID *)P + 10));
    *((_QWORD *)P + 10) = 0;
  }
  v8 = *((_DWORD *)P + 1);
  *(_DWORD *)(v3 + 8) = v2;
  *(_DWORD *)(v3 + 12) = v8;
  (*(void (__fastcall **)(__int64))v3)(v3);
  v9 = (void *)*((_QWORD *)P + 13);
  if ( v9 )
  {
    ExFreePoolWithTag(v9, 0x6D536356u);
    *((_QWORD *)P + 13) = 0;
  }
  v10 = (void *)*((_QWORD *)P + 9);
  if ( v10 )
  {
    ExFreePoolWithTag(v10, 0x6D536356u);
    *((_QWORD *)P + 9) = 0;
  }
  if ( *((_QWORD *)P + 17) )
    PsDereferenceSiloContext();
  ExFreePoolWithTag(P, 0x6D536356u);
  return 0;
}

```

## disassembly

```asm
0x14002d150  push    r14
0x14002d152  sub     rsp, 30h
0x14002d156  mov     [rsp+38h+arg_8], rbp
0x14002d15b  mov     r14, rcx
0x14002d15e  mov     ebp, [rcx]
0x14002d160  mov     [rsp+38h+arg_18], rdi
0x14002d165  mov     [rsp+38h+var_10], r12
0x14002d16a  xor     r12d, r12d
0x14002d16d  mov     [rsp+38h+var_18], r15
0x14002d172  mov     r15, [rcx+78h]
0x14002d176  test    ebp, ebp
0x14002d178  jnz     short loc_14002D1BA
0x14002d17a  mov     rdx, [rcx+50h]
0x14002d17e  movzx   eax, word ptr [rcx+90h]
0x14002d185  mov     [rdx+14Eh], ax
0x14002d18c  mov     rdx, [rcx+50h]
0x14002d190  movzx   eax, word ptr [rcx+92h]
0x14002d197  mov     [rdx+14Ch], ax
0x14002d19e  mov     rdx, [rcx+50h]
0x14002d1a2  mov     rcx, [rdx+20h]
0x14002d1a6  test    rcx, rcx
0x14002d1a9  jz      short loc_14002D1B6
0x14002d1ab  call    VctCompleteInitialization
0x14002d1b0  mov     ebp, eax
0x14002d1b2  test    eax, eax
0x14002d1b4  js      short loc_14002D1BA
0x14002d1b6  mov     [r14+50h], r12
0x14002d1ba  cmp     [r14+70h], r12b
0x14002d1be  jnz     short loc_14002D1EB
0x14002d1c0  mov     rdx, [r14+88h]
0x14002d1c7  mov     rcx, [r14+80h]
0x14002d1ce  call    SmbCeGetUnavailableServerListForDeviceSilo
0x14002d1d3  mov     rcx, rax
0x14002d1d6  lea     rdx, [r14+98h]
0x14002d1dd  mov     r9d, 1
0x14002d1e3  mov     r8d, ebp
0x14002d1e6  call    SmbCeUpdateServerAvailability
0x14002d1eb  mov     rdi, [r14+50h]
0x14002d1ef  test    rdi, rdi
0x14002d1f2  jz      short loc_14002D26E
0x14002d1f4  mov     rdi, [rdi+18h]
0x14002d1f8  mov     [rsp+38h+arg_0], rbx
0x14002d1fd  mov     [rsp+38h+arg_10], rsi
0x14002d202  lea     rcx, [rdi+780h]; SpinLock
0x14002d209  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002d210  nop     dword ptr [rax+rax+00h]
0x14002d215  movzx   ebx, al
0x14002d218  call    cs:__imp_PsGetCurrentThreadId
0x14002d21f  nop     dword ptr [rax+rax+00h]
0x14002d224  mov     [rdi+930h], eax
0x14002d22a  lea     rcx, [rdi+780h]; SpinLock
0x14002d231  mov     rdx, [r14+50h]
0x14002d235  mov     [rdx+180h], r12
0x14002d23c  movzx   edx, bl; OldIrql
0x14002d23f  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x14002d249  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002d250  nop     dword ptr [rax+rax+00h]
0x14002d255  mov     rcx, [r14+50h]; pContext
0x14002d259  xor     edx, edx
0x14002d25b  call    VctDisconnectAndDereferenceEndpoint
0x14002d260  mov     rsi, [rsp+38h+arg_10]
0x14002d265  mov     rbx, [rsp+38h+arg_0]
0x14002d26a  mov     [r14+50h], r12
0x14002d26e  mov     eax, [r14+4]
0x14002d272  mov     rcx, r15
0x14002d275  mov     [r15+8], ebp
0x14002d279  mov     [r15+0Ch], eax
0x14002d27d  mov     rax, [r15]
0x14002d280  call    _guard_dispatch_icall
0x14002d285  mov     rcx, [r14+68h]; P
0x14002d289  mov     r15, [rsp+38h+var_18]
0x14002d28e  mov     rdi, [rsp+38h+arg_18]
0x14002d293  mov     rbp, [rsp+38h+arg_8]
0x14002d298  test    rcx, rcx
0x14002d29b  jz      short loc_14002D2B2
0x14002d29d  mov     edx, 6D536356h; Tag
0x14002d2a2  call    cs:__imp_ExFreePoolWithTag
0x14002d2a9  nop     dword ptr [rax+rax+00h]
0x14002d2ae  mov     [r14+68h], r12
0x14002d2b2  mov     rcx, [r14+48h]; P
0x14002d2b6  test    rcx, rcx
0x14002d2b9  jz      short loc_14002D2D0
0x14002d2bb  mov     edx, 6D536356h; Tag
0x14002d2c0  call    cs:__imp_ExFreePoolWithTag
0x14002d2c7  nop     dword ptr [rax+rax+00h]
0x14002d2cc  mov     [r14+48h], r12
0x14002d2d0  mov     rcx, [r14+88h]
0x14002d2d7  mov     r12, [rsp+38h+var_10]
0x14002d2dc  test    rcx, rcx
0x14002d2df  jz      short loc_14002D2ED
0x14002d2e1  call    cs:__imp_PsDereferenceSiloContext
0x14002d2e8  nop     dword ptr [rax+rax+00h]
0x14002d2ed  mov     edx, 6D536356h; Tag
0x14002d2f2  mov     rcx, r14; P
0x14002d2f5  call    cs:__imp_ExFreePoolWithTag
0x14002d2fc  nop     dword ptr [rax+rax+00h]
0x14002d301  xor     eax, eax
0x14002d303  add     rsp, 30h
0x14002d307  pop     r14
0x14002d309  retn
```
