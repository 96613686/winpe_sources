# WskCreateSocket

- ea: `0x14001fb10`
- end: `0x14001fd0e`
- name: `WskCreateSocket`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140019358`

## callees

- `0x140004504`
- `0x140004830`
- `0x14001fb10`
- `0x14001fe6c`
- `0x140020100`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001fbb9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001fbf7`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001fbb9`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x14001fbf7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001fca6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001fca6`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001fc0d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001fc0d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001fc88`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001fc88`
- `NDIS!NdisGetVersion` at `0x14001fb70`
- `NDIS!NdisGetVersion` at `0x14001fbc5`
- `NDIS!NdisGetVersion` at `0x14001fb70`
- `NDIS!NdisGetVersion` at `0x14001fbc5`

## pseudocode

```c
__int64 __fastcall WskCreateSocket(__int64 a1, int a2, char a3, __int64 a4, unsigned int a5)
{
  _WORD *v9; // rcx
  __int64 WskClientContext; // rdi
  __int64 v11; // r9
  int v12; // edi
  int v13; // r8d
  int v14; // r9d
  KIRQL v15; // al

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
    v12 = WskOpenConnectedSocket(WskClientContext, *(_QWORD *)(a1 + 16), a2, v14, a4);
    if ( v12 >= 0 )
    {
      *(_DWORD *)(a4 + 392) |= 0x10u;
      return (unsigned int)v12;
    }
    goto LABEL_7;
  }
  v12 = WskOpenSocket(WskClientContext, a1, v13, a4, a3 | 8u, a4 + 384);
  if ( v12 < 0 )
  {
LABEL_7:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a4 + 512), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a4 + 520))(a4);
    return (unsigned int)v12;
  }
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a4 + 456));
  *(_DWORD *)(a4 + 392) |= 0x20u;
  *(_BYTE *)(a4 + 464) = v15;
  KeReleaseSpinLock((PKSPIN_LOCK)(a4 + 456), v15);
  *(_DWORD *)(a4 + 392) |= 8u;
  if ( *(_WORD *)a1 == 3 )
    *(_DWORD *)(a4 + 392) |= 0x400u;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14001fb10  push    rbx
0x14001fb12  push    rbp
0x14001fb13  push    rsi
0x14001fb14  push    rdi
0x14001fb15  push    r12
0x14001fb17  push    r13
0x14001fb19  push    r14
0x14001fb1b  push    r15
0x14001fb1d  sub     rsp, 58h
0x14001fb21  mov     rbx, r9
0x14001fb24  mov     ebp, r8d
0x14001fb27  mov     r15, rdx
0x14001fb2a  mov     rsi, rcx
0x14001fb2d  call    GetWskClientContext
0x14001fb32  mov     rdi, rax
0x14001fb35  test    rax, rax
0x14001fb38  jnz     short loc_14001FB44
0x14001fb3a  mov     edi, 0C00002B9h
0x14001fb3f  jmp     loc_14001FCFA
0x14001fb44  movzx   eax, word ptr [rcx]
0x14001fb47  mov     r13d, 1
0x14001fb4d  sub     ax, r13w
0x14001fb51  cmp     ax, 2
0x14001fb55  jbe     short loc_14001FB61
0x14001fb57  mov     edi, 0C000000Dh
0x14001fb5c  jmp     loc_14001FCFA
0x14001fb61  or      [r9+188h], r13d
0x14001fb68  lock add [r9+200h], r13d
0x14001fb70  call    cs:__imp_NdisGetVersion
0x14001fb77  nop     dword ptr [rax+rax+00h]
0x14001fb7c  mov     eax, [rsp+98h+arg_20]
0x14001fb83  lea     rcx, [rbx+80h]; Lookaside
0x14001fb8a  add     rax, 37h ; '7'
0x14001fb8e  mov     r12d, 0Ah
0x14001fb94  and     rax, 0FFFFFFFFFFFFFFF8h
0x14001fb98  mov     [rsp+98h+Depth], r12w; Depth
0x14001fb9e  mov     r14d, 200h
0x14001fba4  mov     [rsp+98h+Tag], 72774152h; Tag
0x14001fbac  mov     r9d, r14d; Flags
0x14001fbaf  mov     [rsp+98h+Size], rax; Size
0x14001fbb4  xor     r8d, r8d; Free
0x14001fbb7  xor     edx, edx; Allocate
0x14001fbb9  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001fbc0  nop     dword ptr [rax+rax+00h]
0x14001fbc5  call    cs:__imp_NdisGetVersion
0x14001fbcc  nop     dword ptr [rax+rax+00h]
0x14001fbd1  mov     [rsp+98h+Depth], r12w; Depth
0x14001fbd7  lea     rcx, [rbx+100h]; Lookaside
0x14001fbde  mov     [rsp+98h+Tag], 73774152h; Tag
0x14001fbe6  mov     r9d, r14d; Flags
0x14001fbe9  xor     r8d, r8d; Free
0x14001fbec  mov     [rsp+98h+Size], 40h ; '@'; Size
0x14001fbf5  xor     edx, edx; Allocate
0x14001fbf7  call    cs:__imp_ExInitializeNPagedLookasideList
0x14001fbfe  nop     dword ptr [rax+rax+00h]
0x14001fc03  lea     r14, [rbx+1C8h]
0x14001fc0a  mov     rcx, r14; SpinLock
0x14001fc0d  call    cs:__imp_KeInitializeSpinLock
0x14001fc14  nop     dword ptr [rax+rax+00h]
0x14001fc19  lea     rax, [rbx+1A8h]
0x14001fc20  mov     rcx, rdi
0x14001fc23  mov     [rax+8], rax
0x14001fc27  mov     [rax], rax
0x14001fc2a  bts     dword ptr [rbx+188h], 0Bh
0x14001fc32  cmp     [rsi], r13w
0x14001fc36  jz      loc_14001FCC9
0x14001fc3c  lea     rax, [rbx+180h]
0x14001fc43  or      ebp, 8
0x14001fc46  mov     qword ptr [rsp+98h+Tag], rax
0x14001fc4b  mov     r9, rbx
0x14001fc4e  mov     rdx, rsi
0x14001fc51  mov     dword ptr [rsp+98h+Size], ebp
0x14001fc55  call    WskOpenSocket
0x14001fc5a  mov     edi, eax
0x14001fc5c  test    eax, eax
0x14001fc5e  jns     short loc_14001FC85
0x14001fc60  or      ecx, 0FFFFFFFFh
0x14001fc63  lock xadd [rbx+200h], ecx
0x14001fc6b  cmp     ecx, r13d
0x14001fc6e  jnz     loc_14001FCFA
0x14001fc74  mov     rax, [rbx+208h]
0x14001fc7b  mov     rcx, rbx
0x14001fc7e  call    _guard_dispatch_icall
0x14001fc83  jmp     short loc_14001FCFA
0x14001fc85  mov     rcx, r14; SpinLock
0x14001fc88  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001fc8f  nop     dword ptr [rax+rax+00h]
0x14001fc94  or      dword ptr [rbx+188h], 20h
0x14001fc9b  mov     rcx, r14; SpinLock
0x14001fc9e  mov     dl, al; NewIrql
0x14001fca0  mov     [rbx+1D0h], al
0x14001fca6  call    cs:__imp_KeReleaseSpinLock
0x14001fcad  nop     dword ptr [rax+rax+00h]
0x14001fcb2  or      dword ptr [rbx+188h], 8
0x14001fcb9  cmp     word ptr [rsi], 3
0x14001fcbd  jnz     short loc_14001FCFA
0x14001fcbf  bts     dword ptr [rbx+188h], 0Ah
0x14001fcc7  jmp     short loc_14001FCFA
0x14001fcc9  mov     rdx, [rsi+10h]
0x14001fccd  mov     r8, r15
0x14001fcd0  mov     [rsp+98h+Size], rbx
0x14001fcd5  call    WskOpenConnectedSocket
0x14001fcda  mov     edi, eax
0x14001fcdc  test    eax, eax
0x14001fcde  jns     short loc_14001FCF3
0x14001fce0  or      eax, 0FFFFFFFFh
0x14001fce3  lock xadd [rbx+200h], eax
0x14001fceb  cmp     eax, r13d
0x14001fcee  jmp     loc_14001FC6E
0x14001fcf3  or      dword ptr [rbx+188h], 10h
0x14001fcfa  mov     eax, edi
0x14001fcfc  add     rsp, 58h
0x14001fd00  pop     r15
0x14001fd02  pop     r14
0x14001fd04  pop     r13
0x14001fd06  pop     r12
0x14001fd08  pop     rdi
0x14001fd09  pop     rsi
0x14001fd0a  pop     rbp
0x14001fd0b  pop     rbx
0x14001fd0c  retn
```
