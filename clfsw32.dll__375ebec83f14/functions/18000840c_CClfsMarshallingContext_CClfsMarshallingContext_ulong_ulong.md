# CClfsMarshallingContext::CClfsMarshallingContext(ulong,ulong)

- ea: `0x18000840c`
- end: `0x18000856e`
- name: `??0CClfsMarshallingContext@@QEAA@KK@Z`
- size: `354`
- prototype: `CClfsMarshallingContext *__fastcall(CClfsMarshallingContext *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a7e0`
- `0x18000aec0`
- `0x18000d500`

## callees

- `0x18000840c`

## import_xrefs

- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18000851a`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18000853c`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180008551`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18000851a`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x18000853c`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x180008551`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18000843d`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18000843d`

## pseudocode

```c
CClfsMarshallingContext *__fastcall CClfsMarshallingContext::CClfsMarshallingContext(
        CClfsMarshallingContext *this,
        int a2,
        int a3)
{
  unsigned int v3; // esi

  *(_QWORD *)((char *)this + 36) = 10;
  *((_DWORD *)this + 8) = 0;
  v3 = a2 + a3;
  *((_DWORD *)this + 11) = 0;
  InitializeSListHead((PSLIST_HEADER)this + 1);
  if ( v3 < *((_DWORD *)this + 9) )
    *((_DWORD *)this + 9) = v3;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 6) = -1;
  *((_QWORD *)this + 7) = -1;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = -1;
  *((_BYTE *)this + 100) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = a2;
  *((_DWORD *)this + 31) = a3;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_DWORD *)this + 38) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((CLFS_LSN *)this + 25) = CLFS_LSN_NULL;
  *((CLFS_LSN *)this + 26) = CLFS_LSN_NULL;
  *((CLFS_LSN *)this + 27) = CLFS_LSN_NULL;
  *((CLFS_LSN *)this + 28) = CLFS_LSN_INVALID;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  RtlInitializeCriticalSectionAndSpinCount((PRTL_CRITICAL_SECTION)((char *)this + 248), 5u);
  *(_DWORD *)this = -1040322550;
  *((_DWORD *)this + 1) = 368;
  RtlInitializeCriticalSectionAndSpinCount((PRTL_CRITICAL_SECTION)((char *)this + 328), 5u);
  RtlInitializeCriticalSectionAndSpinCount((PRTL_CRITICAL_SECTION)((char *)this + 288), 5u);
  return this;
}

```

## disassembly

```asm
0x18000840c  push    rbx
0x18000840e  push    rbp
0x18000840f  push    rsi
0x180008410  push    rdi
0x180008411  push    r14
0x180008413  push    r15
0x180008415  sub     rsp, 28h
0x180008419  xor     r15d, r15d
0x18000841c  mov     qword ptr [rcx+24h], 0Ah
0x180008424  mov     [rcx+20h], r15d
0x180008428  lea     esi, [rdx+r8]
0x18000842c  mov     [rcx+2Ch], r15d
0x180008430  mov     rbx, rcx
0x180008433  add     rcx, 10h; ListHead
0x180008437  mov     ebp, r8d
0x18000843a  mov     r14d, edx
0x18000843d  call    cs:__imp_InitializeSListHead
0x180008444  nop     dword ptr [rax+rax+00h]
0x180008449  cmp     esi, [rbx+24h]
0x18000844c  jnb     short loc_180008451
0x18000844e  mov     [rbx+24h], esi
0x180008451  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008455  mov     [rbx+40h], r15
0x180008459  mov     [rbx+30h], rax
0x18000845d  lea     rcx, [rbx+0F8h]; CriticalSection
0x180008464  mov     [rbx+38h], rax
0x180008468  mov     edi, 5
0x18000846d  mov     [rbx+48h], r15
0x180008471  mov     edx, edi; SpinCount
0x180008473  mov     [rbx+50h], r15
0x180008477  mov     [rbx+58h], r15
0x18000847b  mov     dword ptr [rbx+60h], 0FFFFFFFFh
0x180008482  mov     [rbx+64h], r15b
0x180008486  mov     [rbx+68h], r15
0x18000848a  mov     [rbx+70h], r15
0x18000848e  mov     [rbx+78h], r14d
0x180008492  mov     [rbx+7Ch], ebp
0x180008495  mov     [rbx+80h], r15
0x18000849c  mov     [rbx+88h], r15
0x1800084a3  mov     [rbx+90h], r15
0x1800084aa  mov     [rbx+98h], r15d
0x1800084b1  mov     [rbx+0A0h], r15
0x1800084b8  mov     [rbx+0A8h], r15
0x1800084bf  mov     [rbx+0B0h], r15
0x1800084c6  mov     [rbx+0B8h], r15
0x1800084cd  mov     [rbx+0C0h], r15
0x1800084d4  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x1800084db  mov     [rbx+0C8h], rax
0x1800084e2  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x1800084e9  mov     [rbx+0D0h], rax
0x1800084f0  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x1800084f7  mov     [rbx+0D8h], rax
0x1800084fe  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x180008505  mov     [rbx+0E0h], rax
0x18000850c  mov     [rbx+0E8h], r15
0x180008513  mov     [rbx+0F0h], r15
0x18000851a  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180008521  nop     dword ptr [rax+rax+00h]
0x180008526  lea     rcx, [rbx+148h]; CriticalSection
0x18000852d  mov     dword ptr [rbx], 0C1FDF00Ah
0x180008533  mov     edx, edi; SpinCount
0x180008535  mov     dword ptr [rbx+4], 170h
0x18000853c  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180008543  nop     dword ptr [rax+rax+00h]
0x180008548  lea     rcx, [rbx+120h]; CriticalSection
0x18000854f  mov     edx, edi; SpinCount
0x180008551  call    cs:__imp_RtlInitializeCriticalSectionAndSpinCount
0x180008558  nop     dword ptr [rax+rax+00h]
0x18000855d  mov     rax, rbx
0x180008560  add     rsp, 28h
0x180008564  pop     r15
0x180008566  pop     r14
0x180008568  pop     rdi
0x180008569  pop     rsi
0x18000856a  pop     rbp
0x18000856b  pop     rbx
0x18000856c  retn
```
