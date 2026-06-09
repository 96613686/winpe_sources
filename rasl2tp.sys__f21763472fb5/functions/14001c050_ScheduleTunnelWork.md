# ScheduleTunnelWork

- ea: `0x14001c050`
- end: `0x14001c1a6`
- name: `ScheduleTunnelWork`
- size: `342`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, __int64)`
- caller_count: `22`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140001e60`
- `0x1400024e0`
- `0x14000f008`
- `0x14000f7c4`
- `0x14000fd0c`
- `0x1400100d0`
- `0x14001083c`
- `0x140011070`
- `0x140011518`
- `0x1400126c8`
- `0x1400128bc`
- `0x140012f5c`
- `0x140013bc0`
- `0x140013c74`
- `0x140015190`
- `0x1400154b8`
- `0x140015fa8`
- `0x1400171e0`
- `0x140017330`
- `0x140017b90`
- `0x14001ac30`
- `0x14001be00`

## callees

- `0x1400012e0`
- `0x140001850`
- `0x140001990`
- `0x14001ac30`
- `0x14001c050`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001c0ba`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001c0ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c0a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c16e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c0a7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c16e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c084`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c108`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c084`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c108`

## pseudocode

```c
void __fastcall ScheduleTunnelWork(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        char a8)
{
  __int64 v9; // rbp
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  _QWORD *v15; // rcx

  v9 = *(_QWORD *)(a1 + 24);
  if ( !a8 )
  {
    *(_BYTE *)(v9 + 152) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v9 + 144));
    ++*(_DWORD *)(a1 + 20);
    KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 144), *(_BYTE *)(v9 + 152));
  }
  v13 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v9 + 960));
  v14 = v13;
  if ( v13 )
  {
    if ( a2 )
      v13 = (_QWORD *)ReferenceVc(a2);
    v13[2] = a3;
    v13[3] = a2;
    v13[4] = a4;
    v14[5] = a5;
    v14[6] = 0;
    v14[7] = 0;
    *(_BYTE *)(a1 + 336) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 328));
    v15 = *(_QWORD **)(a1 + 320);
    if ( *v15 != a1 + 312 )
      __fastfail(3u);
    v14[1] = v15;
    *v14 = a1 + 312;
    *v15 = v14;
    *(_QWORD *)(a1 + 320) = v14;
    if ( (*(_DWORD *)(a1 + 120) & 0x1000) == 0 )
    {
      SetFlags(a1 + 120, 4096);
      ScheduleWork(v9, &TunnelWork, a1);
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 328), *(_BYTE *)(a1 + 336));
  }
  else
  {
    ++g_ulAllocTwFailures;
    if ( !a8 )
      DereferenceTunnel(a1);
  }
}

```

## disassembly

```asm
0x14001c050  push    rbx
0x14001c052  push    rbp
0x14001c053  push    rsi
0x14001c054  push    rdi
0x14001c055  push    r12
0x14001c057  push    r14
0x14001c059  push    r15
0x14001c05b  sub     rsp, 20h
0x14001c05f  movzx   r14d, [rsp+58h+arg_38]
0x14001c068  mov     r15, r9
0x14001c06b  mov     rbp, [rcx+18h]
0x14001c06f  mov     r12, r8
0x14001c072  mov     rsi, rdx
0x14001c075  mov     rdi, rcx
0x14001c078  test    r14b, r14b
0x14001c07b  jnz     short loc_14001C0B3
0x14001c07d  lea     rcx, [rbp+90h]; SpinLock
0x14001c084  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001c08b  nop     dword ptr [rax+rax+00h]
0x14001c090  mov     [rbp+98h], al
0x14001c096  lea     rcx, [rbp+90h]; SpinLock
0x14001c09d  inc     dword ptr [rdi+14h]
0x14001c0a0  movzx   edx, byte ptr [rbp+98h]; NewIrql
0x14001c0a7  call    cs:__imp_KeReleaseSpinLock
0x14001c0ae  nop     dword ptr [rax+rax+00h]
0x14001c0b3  lea     rcx, [rbp+3C0h]; Lookaside
0x14001c0ba  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001c0c1  nop     dword ptr [rax+rax+00h]
0x14001c0c6  mov     rbx, rax
0x14001c0c9  test    rax, rax
0x14001c0cc  jz      loc_14001C18A
0x14001c0d2  test    rsi, rsi
0x14001c0d5  jz      short loc_14001C0DF
0x14001c0d7  mov     rcx, rsi
0x14001c0da  call    ReferenceVc
0x14001c0df  mov     [rax+10h], r12
0x14001c0e3  lea     rcx, [rdi+148h]; SpinLock
0x14001c0ea  mov     [rax+18h], rsi
0x14001c0ee  mov     [rax+20h], r15
0x14001c0f2  mov     rax, [rsp+58h+arg_20]
0x14001c0fa  mov     [rbx+28h], rax
0x14001c0fe  xor     eax, eax
0x14001c100  mov     [rbx+30h], rax
0x14001c104  mov     [rbx+38h], rax
0x14001c108  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001c10f  nop     dword ptr [rax+rax+00h]
0x14001c114  mov     [rdi+150h], al
0x14001c11a  lea     rax, [rdi+138h]
0x14001c121  mov     rcx, [rax+8]
0x14001c125  cmp     [rcx], rax
0x14001c128  jnz     short loc_14001C19F
0x14001c12a  mov     [rbx+8], rcx
0x14001c12e  mov     [rbx], rax
0x14001c131  mov     [rcx], rbx
0x14001c134  lea     rcx, [rdi+78h]
0x14001c138  mov     [rax+8], rbx
0x14001c13c  test    dword ptr [rcx], 1000h
0x14001c142  jnz     short loc_14001C160
0x14001c144  mov     edx, 1000h
0x14001c149  call    SetFlags
0x14001c14e  mov     r8, rdi
0x14001c151  lea     rdx, TunnelWork
0x14001c158  mov     rcx, rbp
0x14001c15b  call    ScheduleWork
0x14001c160  movzx   edx, byte ptr [rdi+150h]; NewIrql
0x14001c167  lea     rcx, [rdi+148h]; SpinLock
0x14001c16e  call    cs:__imp_KeReleaseSpinLock
0x14001c175  nop     dword ptr [rax+rax+00h]
0x14001c17a  add     rsp, 20h
0x14001c17e  pop     r15
0x14001c180  pop     r14
0x14001c182  pop     r12
0x14001c184  pop     rdi
0x14001c185  pop     rsi
0x14001c186  pop     rbp
0x14001c187  pop     rbx
0x14001c188  retn
0x14001c18a  inc     cs:g_ulAllocTwFailures
0x14001c190  test    r14b, r14b
0x14001c193  jnz     short loc_14001C17A
0x14001c195  mov     rcx, rdi
0x14001c198  call    DereferenceTunnel
0x14001c19d  jmp     short loc_14001C17A
0x14001c19f  mov     ecx, 3
0x14001c1a4  int     29h; Win8: RtlFailFast(ecx)
```
