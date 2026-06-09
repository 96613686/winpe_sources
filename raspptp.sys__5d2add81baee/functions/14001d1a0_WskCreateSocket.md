# WskCreateSocket

- ea: `0x14001d1a0`
- end: `0x14001d3a5`
- name: `WskCreateSocket`
- size: `517`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140011d04`
- `0x140014fd8`

## callees

- `0x140007420`
- `0x140007710`
- `0x14001d1a0`
- `0x14001d57c`
- `0x14001d810`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d249`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d287`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d249`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d287`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d33d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d33d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d29d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d29d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d31f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d31f`
- `NDIS!NdisGetVersion` at `0x14001d200`
- `NDIS!NdisGetVersion` at `0x14001d255`
- `NDIS!NdisGetVersion` at `0x14001d200`
- `NDIS!NdisGetVersion` at `0x14001d255`

## pseudocode

```c
__int64 __fastcall WskCreateSocket(__int64 a1, int a2, int a3, __int64 a4, unsigned int a5)
{
  _WORD *v9; // rcx
  __int64 WskClientContext; // rdi
  __int64 v11; // r9
  int v12; // edi
  int v13; // r9d
  KIRQL v14; // al

  WskClientContext = GetWskClientContext();
  if ( !WskClientContext )
    return (unsigned int)-1073741127;
  if ( (unsigned __int16)(*v9 - 1) > 2u )
    return (unsigned int)-1073741811;
  *(_DWORD *)(v11 + 392) |= 1u;
  _InterlockedAdd((volatile signed __int32 *)(v11 + 512), 1u);
  NdisGetVersion();
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(a4 + 128),
    0,
    0,
    0x200u,
    (a5 + 55LL) & 0xFFFFFFFFFFFFFFF8uLL,
    0x72774152u,
    0xAu);
  NdisGetVersion();
  ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a4 + 256), 0, 0, 0x200u, 0x40u, 0x73774152u, 0xAu);
  KeInitializeSpinLock((PKSPIN_LOCK)(a4 + 456));
  *(_QWORD *)(a4 + 432) = a4 + 424;
  *(_QWORD *)(a4 + 424) = a4 + 424;
  *(_DWORD *)(a4 + 392) |= 0x800u;
  if ( *(_WORD *)a1 == 1 )
  {
    v12 = WskOpenConnectedSocket(WskClientContext, *(_QWORD *)(a1 + 16), a2, v13, a4);
    if ( v12 >= 0 )
    {
      *(_DWORD *)(a4 + 392) |= 0x10u;
      return (unsigned int)v12;
    }
    goto LABEL_7;
  }
  v12 = WskOpenSocket(WskClientContext, a1, &g_WskClientDgramDispatch, a4, a3 | 8u, a4 + 384);
  if ( v12 < 0 )
  {
LABEL_7:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a4 + 512), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a4 + 520))(a4);
    return (unsigned int)v12;
  }
  v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a4 + 456));
  *(_DWORD *)(a4 + 392) |= 0x20u;
  *(_BYTE *)(a4 + 464) = v14;
  KeReleaseSpinLock((PKSPIN_LOCK)(a4 + 456), v14);
  *(_DWORD *)(a4 + 392) |= 8u;
  if ( *(_WORD *)a1 == 3 )
    *(_DWORD *)(a4 + 392) |= 0x400u;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14001d1a0  push    rbx
0x14001d1a2  push    rbp
0x14001d1a3  push    rsi
0x14001d1a4  push    rdi
0x14001d1a5  push    r12
0x14001d1a7  push    r13
0x14001d1a9  push    r14
0x14001d1ab  push    r15
0x14001d1ad  sub     rsp, 58h
0x14001d1b1  mov     rbx, r9
0x14001d1b4  mov     ebp, r8d
0x14001d1b7  mov     r15, rdx
0x14001d1ba  mov     rsi, rcx
0x14001d1bd  call    GetWskClientContext
0x14001d1c2  mov     rdi, rax
0x14001d1c5  test    rax, rax
0x14001d1c8  jnz     short loc_14001D1D4
0x14001d1ca  mov     edi, 0C00002B9h
0x14001d1cf  jmp     loc_14001D391
0x14001d1d4  movzx   eax, word ptr [rcx]
0x14001d1d7  mov     r13d, 1
0x14001d1dd  sub     ax, r13w
0x14001d1e1  cmp     ax, 2
0x14001d1e5  jbe     short loc_14001D1F1
0x14001d1e7  mov     edi, 0C000000Dh
0x14001d1ec  jmp     loc_14001D391
0x14001d1f1  or      [r9+188h], r13d
0x14001d1f8  lock add [r9+200h], r13d
0x14001d200  call    cs:__imp_NdisGetVersion
0x14001d207  nop     dword ptr [rax+rax+00h]
0x14001d20c  mov     eax, [rsp+98h+arg_20]
0x14001d213  lea     rcx, [rbx+80h]; Lookaside
0x14001d21a  add     rax, 37h ; '7'
0x14001d21e  mov     r12d, 0Ah
0x14001d224  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001d228  mov     [rsp+98h+Depth], r12w; Depth
0x14001d22e  mov     r14d, 200h
0x14001d234  mov     [rsp+98h+Tag], 72774152h; Tag
0x14001d23c  mov     r9d, r14d; Flags
0x14001d23f  mov     [rsp+98h+Size], rax; Size
0x14001d244  xor     r8d, r8d; Free
0x14001d247  xor     edx, edx; Allocate
0x14001d249  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001d250  nop     dword ptr [rax+rax+00h]
0x14001d255  call    cs:__imp_NdisGetVersion
0x14001d25c  nop     dword ptr [rax+rax+00h]
0x14001d261  mov     [rsp+98h+Depth], r12w; Depth
0x14001d267  lea     rcx, [rbx+100h]; Lookaside
0x14001d26e  mov     [rsp+98h+Tag], 73774152h; Tag
0x14001d276  mov     r9d, r14d; Flags
0x14001d279  xor     r8d, r8d; Free
0x14001d27c  mov     [rsp+98h+Size], 40h ; '@'; Size
0x14001d285  xor     edx, edx; Allocate
0x14001d287  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001d28e  nop     dword ptr [rax+rax+00h]
0x14001d293  lea     r14, [rbx+1C8h]
0x14001d29a  mov     rcx, r14; SpinLock
0x14001d29d  call    cs:__imp_KeInitializeSpinLock
0x14001d2a4  nop     dword ptr [rax+rax+00h]
0x14001d2a9  lea     rax, [rbx+1A8h]
0x14001d2b0  mov     rcx, rdi
0x14001d2b3  mov     [rax+8], rax
0x14001d2b7  mov     [rax], rax
0x14001d2ba  bts     dword ptr [rbx+188h], 0Bh
0x14001d2c2  cmp     [rsi], r13w
0x14001d2c6  jz      loc_14001D360
0x14001d2cc  lea     rax, [rbx+180h]
0x14001d2d3  or      ebp, 8
0x14001d2d6  mov     qword ptr [rsp+98h+Tag], rax
0x14001d2db  lea     r8, g_WskClientDgramDispatch
0x14001d2e2  mov     r9, rbx
0x14001d2e5  mov     dword ptr [rsp+98h+Size], ebp
0x14001d2e9  mov     rdx, rsi
0x14001d2ec  call    WskOpenSocket
0x14001d2f1  mov     edi, eax
0x14001d2f3  test    eax, eax
0x14001d2f5  jns     short loc_14001D31C
0x14001d2f7  or      ecx, 0FFFFFFFFh
0x14001d2fa  lock xadd [rbx+200h], ecx
0x14001d302  cmp     ecx, r13d
0x14001d305  jnz     loc_14001D391
0x14001d30b  mov     rax, [rbx+208h]
0x14001d312  mov     rcx, rbx
0x14001d315  call    _guard_dispatch_icall
0x14001d31a  jmp     short loc_14001D391
0x14001d31c  mov     rcx, r14; SpinLock
0x14001d31f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001d326  nop     dword ptr [rax+rax+00h]
0x14001d32b  or      dword ptr [rbx+188h], 20h
0x14001d332  mov     rcx, r14; SpinLock
0x14001d335  mov     dl, al; NewIrql
0x14001d337  mov     [rbx+1D0h], al
0x14001d33d  call    cs:__imp_KeReleaseSpinLock
0x14001d344  nop     dword ptr [rax+rax+00h]
0x14001d349  or      dword ptr [rbx+188h], 8
0x14001d350  cmp     word ptr [rsi], 3
0x14001d354  jnz     short loc_14001D391
0x14001d356  bts     dword ptr [rbx+188h], 0Ah
0x14001d35e  jmp     short loc_14001D391
0x14001d360  mov     rdx, [rsi+10h]
0x14001d364  mov     r8, r15
0x14001d367  mov     [rsp+98h+Size], rbx
0x14001d36c  call    WskOpenConnectedSocket
0x14001d371  mov     edi, eax
0x14001d373  test    eax, eax
0x14001d375  jns     short loc_14001D38A
0x14001d377  or      eax, 0FFFFFFFFh
0x14001d37a  lock xadd [rbx+200h], eax
0x14001d382  cmp     eax, r13d
0x14001d385  jmp     loc_14001D305
0x14001d38a  or      dword ptr [rbx+188h], 10h
0x14001d391  mov     eax, edi
0x14001d393  add     rsp, 58h
0x14001d397  pop     r15
0x14001d399  pop     r14
0x14001d39b  pop     r13
0x14001d39d  pop     r12
0x14001d39f  pop     rdi
0x14001d3a0  pop     rsi
0x14001d3a1  pop     rbp
0x14001d3a2  pop     rbx
0x14001d3a3  retn
```
