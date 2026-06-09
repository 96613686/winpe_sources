# HvSocketGetVmAddressInfo

- ea: `0x1400188c4`
- end: `0x1400189c2`
- name: `HvSocketGetVmAddressInfo`
- size: `254`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140018350`
- `0x14001b98c`
- `0x14001e5ac`
- `0x14001febc`

## callees

- `0x1400015dc`
- `0x1400188c4`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018988`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400189a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140018988`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400189a6`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001897c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001899a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001897c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14001899a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400188df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018939`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400188df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140018939`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400188ef`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018949`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400188ef`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140018949`

## pseudocode

```c
__int64 __fastcall HvSocketGetVmAddressInfo(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned int v6; // ebp
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rdi

  v6 = -1073741275;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  LOBYTE(v8) = 1;
  while ( 1 )
  {
    v9 = VmbusTlEnumerateObjectTable(v7, a1 + 1312, v8);
    v10 = v9;
    if ( !v9 )
      break;
    if ( *(_QWORD *)(v9 + 120) == *a2 && *(_QWORD *)(v9 + 128) == a2[1] && (*(_DWORD *)(v9 + 152) & 1) == 0 )
    {
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v10 + 16));
      *(_OWORD *)a3 = *(_OWORD *)(v10 + 104);
      *(_OWORD *)(a3 + 16) = *(_OWORD *)(v10 + 120);
      *(_OWORD *)(a3 + 32) = *(_OWORD *)(v10 + 136);
      *(_DWORD *)(a3 + 48) = *(_DWORD *)(v10 + 152);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 16));
      KeLeaveCriticalRegion();
      v6 = 0;
      break;
    }
    v8 = 0;
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  return v6;
}

```

## disassembly

```asm
0x1400188c4  push    rbx
0x1400188c6  push    rbp
0x1400188c7  push    rsi
0x1400188c8  push    rdi
0x1400188c9  push    r14
0x1400188cb  push    r15
0x1400188cd  sub     rsp, 28h
0x1400188d1  mov     rsi, r8
0x1400188d4  mov     r14, rdx
0x1400188d7  mov     rbx, rcx
0x1400188da  mov     ebp, 0C0000225h
0x1400188df  call    cs:__imp_KeEnterCriticalRegion
0x1400188e6  nop     dword ptr [rax+rax+00h]
0x1400188eb  lea     rcx, [rbx+10h]; FastMutex
0x1400188ef  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400188f6  nop     dword ptr [rax+rax+00h]
0x1400188fb  mov     r8b, 1
0x1400188fe  jmp     short loc_140018923
0x140018900  mov     rax, [rdi+78h]
0x140018904  cmp     rax, [r14]
0x140018907  jnz     short loc_140018920
0x140018909  mov     rax, [rdi+80h]
0x140018910  cmp     rax, [r14+8]
0x140018914  jnz     short loc_140018920
0x140018916  mov     eax, [rdi+98h]
0x14001891c  test    al, 1
0x14001891e  jz      short loc_140018939
0x140018920  xor     r8d, r8d
0x140018923  lea     rdx, [rbx+520h]
0x14001892a  call    VmbusTlEnumerateObjectTable
0x14001892f  mov     rdi, rax
0x140018932  test    rax, rax
0x140018935  jnz     short loc_140018900
0x140018937  jmp     short loc_140018996
0x140018939  call    cs:__imp_KeEnterCriticalRegion
0x140018940  nop     dword ptr [rax+rax+00h]
0x140018945  lea     rcx, [rdi+10h]; FastMutex
0x140018949  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140018950  nop     dword ptr [rax+rax+00h]
0x140018955  movups  xmm0, xmmword ptr [rdi+68h]
0x140018959  lea     rcx, [rdi+10h]; FastMutex
0x14001895d  movups  xmmword ptr [rsi], xmm0
0x140018960  movups  xmm1, xmmword ptr [rdi+78h]
0x140018964  movups  xmmword ptr [rsi+10h], xmm1
0x140018968  movups  xmm0, xmmword ptr [rdi+88h]
0x14001896f  movups  xmmword ptr [rsi+20h], xmm0
0x140018973  mov     eax, [rdi+98h]
0x140018979  mov     [rsi+30h], eax
0x14001897c  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140018983  nop     dword ptr [rax+rax+00h]
0x140018988  call    cs:__imp_KeLeaveCriticalRegion
0x14001898f  nop     dword ptr [rax+rax+00h]
0x140018994  xor     ebp, ebp
0x140018996  lea     rcx, [rbx+10h]; FastMutex
0x14001899a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400189a1  nop     dword ptr [rax+rax+00h]
0x1400189a6  call    cs:__imp_KeLeaveCriticalRegion
0x1400189ad  nop     dword ptr [rax+rax+00h]
0x1400189b2  mov     eax, ebp
0x1400189b4  add     rsp, 28h
0x1400189b8  pop     r15
0x1400189ba  pop     r14
0x1400189bc  pop     rdi
0x1400189bd  pop     rsi
0x1400189be  pop     rbp
0x1400189bf  pop     rbx
0x1400189c0  retn
```
