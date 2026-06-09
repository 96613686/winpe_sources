# WskCreateServerSocket

- ea: `0x14001cfb0`
- end: `0x14001d195`
- name: `WskCreateServerSocket`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140012da4`

## callees

- `0x140007420`
- `0x140007710`
- `0x14001cfb0`
- `0x14001d810`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d090`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d0ce`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d090`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001d0ce`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d16f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001d16f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d0e4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001d0e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d151`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001d151`
- `NDIS!NdisGetVersion` at `0x14001d053`
- `NDIS!NdisGetVersion` at `0x14001d09c`
- `NDIS!NdisGetVersion` at `0x14001d053`
- `NDIS!NdisGetVersion` at `0x14001d09c`

## pseudocode

```c
__int64 __fastcall WskCreateServerSocket(__int64 a1, __int64 a2, __int64 a3)
{
  _WORD *v5; // rcx
  __int64 v6; // r8
  __int64 WskClientContext; // r15
  int v8; // edi
  __int64 (__fastcall **v9)(); // r14
  int v10; // esi
  KIRQL v11; // al

  WskClientContext = GetWskClientContext();
  if ( WskClientContext )
  {
    if ( (unsigned __int16)(*v5 - 1) <= 2u )
    {
      *(_DWORD *)(v6 + 392) |= 2u;
      if ( *(_WORD *)a1 == 1 )
      {
        v10 = 16;
        *(_DWORD *)(a1 + 8) = 1;
        *(_DWORD *)(v6 + 392) |= 0x10u;
        v9 = (__int64 (__fastcall **)())&g_WskListenDispatch;
      }
      else
      {
        *(_DWORD *)(a1 + 8) = 4;
        v9 = &g_WskClientDgramDispatch;
        *(_DWORD *)(v6 + 392) |= 8u;
        v10 = 0;
        if ( *(_WORD *)a1 == 3 )
          *(_DWORD *)(v6 + 392) |= 0x400u;
      }
      _InterlockedAdd((volatile signed __int32 *)(v6 + 512), 1u);
      NdisGetVersion();
      ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a3 + 128), 0, 0, 0x200u, 0x30u, 0x72774152u, 0xAu);
      NdisGetVersion();
      ExInitializeNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a3 + 256), 0, 0, 0x200u, 0x40u, 0x73774152u, 0xAu);
      KeInitializeSpinLock((PKSPIN_LOCK)(a3 + 456));
      *(_QWORD *)(a3 + 432) = a3 + 424;
      *(_QWORD *)(a3 + 424) = a3 + 424;
      *(_DWORD *)(a3 + 392) |= 0x800u;
      v8 = WskOpenSocket(WskClientContext, a1, v9, a3, v10, a3 + 384);
      if ( v8 >= 0 )
      {
        v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 456));
        *(_DWORD *)(a3 + 392) |= 0x20u;
        *(_BYTE *)(a3 + 464) = v11;
        KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 456), v11);
      }
      else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 512), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(__int64))(a3 + 520))(a3);
      }
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    return (unsigned int)-1073741127;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001cfb0  mov     [rsp+arg_0], rbx
0x14001cfb5  mov     [rsp+arg_8], rbp
0x14001cfba  push    rsi
0x14001cfbb  push    rdi
0x14001cfbc  push    r12
0x14001cfbe  push    r14
0x14001cfc0  push    r15
0x14001cfc2  sub     rsp, 40h
0x14001cfc6  mov     rbx, r8
0x14001cfc9  mov     rdi, rcx
0x14001cfcc  call    GetWskClientContext
0x14001cfd1  mov     r15, rax
0x14001cfd4  test    rax, rax
0x14001cfd7  jnz     short loc_14001CFE3
0x14001cfd9  mov     edi, 0C00002B9h
0x14001cfde  jmp     loc_14001D17B
0x14001cfe3  movzx   eax, word ptr [rcx]
0x14001cfe6  mov     ecx, 1
0x14001cfeb  sub     ax, cx
0x14001cfee  lea     edx, [rcx+1]
0x14001cff1  cmp     ax, dx
0x14001cff4  jbe     short loc_14001D000
0x14001cff6  mov     edi, 0C000000Dh
0x14001cffb  jmp     loc_14001D17B
0x14001d000  or      [r8+188h], edx
0x14001d007  cmp     [rdi], cx
0x14001d00a  jz      short loc_14001D035
0x14001d00c  mov     dword ptr [rdi+8], 4
0x14001d013  lea     r14, g_WskClientDgramDispatch
0x14001d01a  or      dword ptr [r8+188h], 8
0x14001d022  xor     esi, esi
0x14001d024  cmp     word ptr [rdi], 3
0x14001d028  jnz     short loc_14001D04B
0x14001d02a  bts     dword ptr [r8+188h], 0Ah
0x14001d033  jmp     short loc_14001D04B
0x14001d035  mov     esi, 10h
0x14001d03a  mov     [rdi+8], ecx
0x14001d03d  or      [r8+188h], esi
0x14001d044  lea     r14, g_WskListenDispatch
0x14001d04b  lock add [r8+200h], ecx
0x14001d053  call    cs:__imp_NdisGetVersion
0x14001d05a  nop     dword ptr [rax+rax+00h]
0x14001d05f  mov     r12d, 0Ah
0x14001d065  lea     rcx, [rbx+80h]; Lookaside
0x14001d06c  mov     [rsp+68h+Depth], r12w; Depth
0x14001d072  mov     ebp, 200h
0x14001d077  mov     [rsp+68h+Tag], 72774152h; Tag
0x14001d07f  mov     r9d, ebp; Flags
0x14001d082  xor     r8d, r8d; Free
0x14001d085  mov     [rsp+68h+Size], 30h ; '0'; Size
0x14001d08e  xor     edx, edx; Allocate
0x14001d090  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001d097  nop     dword ptr [rax+rax+00h]
0x14001d09c  call    cs:__imp_NdisGetVersion
0x14001d0a3  nop     dword ptr [rax+rax+00h]
0x14001d0a8  mov     [rsp+68h+Depth], r12w; Depth
0x14001d0ae  lea     rcx, [rbx+100h]; Lookaside
0x14001d0b5  mov     [rsp+68h+Tag], 73774152h; Tag
0x14001d0bd  mov     r9d, ebp; Flags
0x14001d0c0  xor     r8d, r8d; Free
0x14001d0c3  mov     [rsp+68h+Size], 40h ; '@'; Size
0x14001d0cc  xor     edx, edx; Allocate
0x14001d0ce  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001d0d5  nop     dword ptr [rax+rax+00h]
0x14001d0da  lea     rbp, [rbx+1C8h]
0x14001d0e1  mov     rcx, rbp; SpinLock
0x14001d0e4  call    cs:__imp_KeInitializeSpinLock
0x14001d0eb  nop     dword ptr [rax+rax+00h]
0x14001d0f0  lea     rax, [rbx+1A8h]
0x14001d0f7  mov     r9, rbx
0x14001d0fa  mov     [rax+8], rax
0x14001d0fe  mov     r8, r14
0x14001d101  mov     [rax], rax
0x14001d104  mov     rdx, rdi
0x14001d107  bts     dword ptr [rbx+188h], 0Bh
0x14001d10f  lea     rax, [rbx+180h]
0x14001d116  mov     qword ptr [rsp+68h+Tag], rax
0x14001d11b  mov     rcx, r15
0x14001d11e  mov     dword ptr [rsp+68h+Size], esi
0x14001d122  call    WskOpenSocket
0x14001d127  mov     edi, eax
0x14001d129  test    eax, eax
0x14001d12b  jns     short loc_14001D14E
0x14001d12d  or      ecx, 0FFFFFFFFh
0x14001d130  lock xadd [rbx+200h], ecx
0x14001d138  cmp     ecx, 1
0x14001d13b  jnz     short loc_14001D17B
0x14001d13d  mov     rax, [rbx+208h]
0x14001d144  mov     rcx, rbx
0x14001d147  call    _guard_dispatch_icall
0x14001d14c  jmp     short loc_14001D17B
0x14001d14e  mov     rcx, rbp; SpinLock
0x14001d151  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001d158  nop     dword ptr [rax+rax+00h]
0x14001d15d  or      dword ptr [rbx+188h], 20h
0x14001d164  mov     rcx, rbp; SpinLock
0x14001d167  mov     dl, al; NewIrql
0x14001d169  mov     [rbx+1D0h], al
0x14001d16f  call    cs:__imp_KeReleaseSpinLock
0x14001d176  nop     dword ptr [rax+rax+00h]
0x14001d17b  mov     rbx, [rsp+68h+arg_0]
0x14001d180  mov     eax, edi
0x14001d182  mov     rbp, [rsp+68h+arg_8]
0x14001d187  add     rsp, 40h
0x14001d18b  pop     r15
0x14001d18d  pop     r14
0x14001d18f  pop     r12
0x14001d191  pop     rdi
0x14001d192  pop     rsi
0x14001d193  retn
```
