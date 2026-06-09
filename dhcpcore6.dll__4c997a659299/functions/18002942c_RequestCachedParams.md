# RequestCachedParams

- ea: `0x18002942c`
- end: `0x18002953b`
- name: `RequestCachedParams`
- size: `271`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027440`

## callees

- `0x18000c41c`
- `0x18002942c`
- `0x18002a1d8`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800294c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800294c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002951b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002951b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029450`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180029450`

## pseudocode

```c
__int64 __fastcall RequestCachedParams(__int64 a1, __int64 a2, __int64 a3)
{
  RTL_SRWLOCK *v3; // r15
  __int64 i; // rsi
  unsigned int v8; // ebx
  const void *v9; // r9
  unsigned int v10; // edx
  __int64 v11; // r12
  __int64 Option; // rax
  __int64 v13; // r13
  __int64 v14; // rcx

  v3 = (RTL_SRWLOCK *)(a1 + 608);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 608));
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v8 = 0;
    if ( (unsigned int)i >= *(_DWORD *)a3 )
      break;
    if ( a2 )
    {
      v9 = *(const void **)(a2 + 8);
      v10 = *(_DWORD *)(a2 + 16);
    }
    else
    {
      v9 = *(const void **)(a1 + 656);
      v10 = *(_DWORD *)(a1 + 664);
    }
    v11 = *(_QWORD *)(a3 + 8);
    Option = Dhcpv6FindOption(
               (_QWORD **)(a1 + 632),
               *(unsigned int *)(v11 + 24 * i + 4),
               *(_DWORD *)(v11 + 24 * i + 8),
               v9,
               v10);
    v13 = Option;
    if ( Option )
    {
      *(_QWORD *)(*(_QWORD *)(a3 + 8) + 24 * i + 16) = LocalAlloc(0x40u, *(unsigned int *)(Option + 56));
      v14 = *(_QWORD *)(a3 + 8);
      if ( !*(_QWORD *)(v14 + 24 * i + 16) )
      {
        v8 = 8;
        break;
      }
      *(_DWORD *)(v14 + 24 * i + 12) = *(_DWORD *)(v13 + 56);
      memcpy_s(
        *(void *const *)(*(_QWORD *)(a3 + 8) + 24 * i + 16),
        *(unsigned int *)(*(_QWORD *)(a3 + 8) + 24 * i + 12),
        *(const void *const *)(v13 + 48),
        *(unsigned int *)(v13 + 56));
    }
    else
    {
      *(_QWORD *)(v11 + 24 * i + 16) = 0;
      *(_DWORD *)(*(_QWORD *)(a3 + 8) + 24 * i + 12) = 0;
    }
  }
  ReleaseSRWLockShared(v3);
  return v8;
}

```

## disassembly

```asm
0x18002942c  push    rbx
0x18002942e  push    rbp
0x18002942f  push    rsi
0x180029430  push    rdi
0x180029431  push    r12
0x180029433  push    r13
0x180029435  push    r14
0x180029437  push    r15
0x180029439  sub     rsp, 38h
0x18002943d  lea     r15, [rcx+260h]
0x180029444  mov     rbp, rcx
0x180029447  mov     rcx, r15; SRWLock
0x18002944a  mov     rdi, r8
0x18002944d  mov     r14, rdx
0x180029450  call    cs:__imp_AcquireSRWLockShared
0x180029457  nop     dword ptr [rax+rax+00h]
0x18002945c  xor     esi, esi
0x18002945e  xor     ebx, ebx
0x180029460  cmp     esi, [rdi]
0x180029462  jnb     loc_180029518
0x180029468  test    r14, r14
0x18002946b  jz      short loc_180029477
0x18002946d  mov     r9, [r14+8]
0x180029471  mov     edx, [r14+10h]
0x180029475  jmp     short loc_180029484
0x180029477  mov     r9, [rbp+290h]
0x18002947e  mov     edx, [rbp+298h]
0x180029484  mov     r12, [rdi+8]
0x180029488  lea     rbx, [rsi+rsi*2]
0x18002948c  mov     [rsp+78h+var_58], edx
0x180029490  lea     rcx, [rbp+278h]
0x180029497  mov     r8d, [r12+rbx*8+8]
0x18002949c  mov     edx, [r12+rbx*8+4]
0x1800294a1  call    Dhcpv6FindOption
0x1800294a6  mov     r13, rax
0x1800294a9  test    rax, rax
0x1800294ac  jnz     short loc_1800294BE
0x1800294ae  mov     [r12+rbx*8+10h], rax
0x1800294b3  mov     rax, [rdi+8]
0x1800294b7  mov     [rax+rbx*8+0Ch], r13d
0x1800294bc  jmp     short loc_18002950C
0x1800294be  mov     edx, [rax+38h]; uBytes
0x1800294c1  mov     ecx, 40h ; '@'; uFlags
0x1800294c6  call    cs:__imp_LocalAlloc
0x1800294cd  nop     dword ptr [rax+rax+00h]
0x1800294d2  mov     rcx, rax
0x1800294d5  mov     rax, [rdi+8]
0x1800294d9  mov     [rax+rbx*8+10h], rcx
0x1800294de  mov     rcx, [rdi+8]
0x1800294e2  cmp     qword ptr [rcx+rbx*8+10h], 0
0x1800294e8  jz      short loc_180029513
0x1800294ea  mov     eax, [r13+38h]
0x1800294ee  mov     [rcx+rbx*8+0Ch], eax
0x1800294f2  mov     rcx, [rdi+8]
0x1800294f6  mov     r9d, [r13+38h]; SourceSize
0x1800294fa  mov     r8, [r13+30h]; Source
0x1800294fe  mov     edx, [rcx+rbx*8+0Ch]; DestinationSize
0x180029502  mov     rcx, [rcx+rbx*8+10h]; Destination
0x180029507  call    memcpy_s
0x18002950c  inc     esi
0x18002950e  jmp     loc_18002945E
0x180029513  mov     ebx, 8
0x180029518  mov     rcx, r15; SRWLock
0x18002951b  call    cs:__imp_ReleaseSRWLockShared
0x180029522  nop     dword ptr [rax+rax+00h]
0x180029527  mov     eax, ebx
0x180029529  add     rsp, 38h
0x18002952d  pop     r15
0x18002952f  pop     r14
0x180029531  pop     r13
0x180029533  pop     r12
0x180029535  pop     rdi
0x180029536  pop     rsi
0x180029537  pop     rbp
0x180029538  pop     rbx
0x180029539  retn
```
