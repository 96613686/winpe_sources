# CdCommonClosePrivate

- ea: `0x14000c248`
- end: `0x14000c36b`
- name: `CdCommonClosePrivate`
- size: `291`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000c0c8`
- `0x14000c374`

## callees

- `0x14000c248`
- `0x1400181a4`
- `0x14001943c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000c2d2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000c2d2`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000c31b`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000c31b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c2ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c349`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c358`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c2ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c349`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000c358`

## pseudocode

```c
char __fastcall CdCommonClosePrivate(__int64 a1, __int64 a2, __int64 a3, int a4, char a5)
{
  struct _ERESOURCE *v5; // rsi
  __int64 v7; // rdi
  __int64 v10; // r8
  __int64 v12; // rax
  bool v13; // [rsp+68h] [rbp+10h] BYREF

  v5 = (struct _ERESOURCE *)(a2 + 128);
  v13 = 0;
  v7 = a3;
  LOBYTE(a3) = a5;
  if ( !(unsigned __int8)CdAcquireResource(a1, a2 + 128, a3, 1) )
    return 0;
  LOBYTE(v10) = a5;
  if ( !(unsigned __int8)CdAcquireResource(a1, *(_QWORD *)(v7 + 200) + 32LL, v10, 0) )
  {
    ExReleaseResourceLite(v5);
    return 0;
  }
  ExAcquireFastMutex((PFAST_MUTEX)(a2 + 336));
  *(_QWORD *)(a2 + 392) = KeGetCurrentThread();
  v12 = *(_QWORD *)(v7 + 120);
  --*(_DWORD *)(v7 + 164);
  *(_DWORD *)(v7 + 168) -= a4;
  --*(_DWORD *)(v12 + 60);
  *(_DWORD *)(*(_QWORD *)(v7 + 120) + 64LL) -= a4;
  *(_QWORD *)(a2 + 392) = 0;
  ExReleaseFastMutex((PFAST_MUTEX)(a2 + 336));
  CdTeardownStructures(a1, (__int16 *)v7, &v13);
  if ( !v13 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v7 + 200) + 32LL));
  ExReleaseResourceLite(v5);
  return 1;
}

```

## disassembly

```asm
0x14000c248  push    rbx
0x14000c24a  push    rbp
0x14000c24b  push    rsi
0x14000c24c  push    rdi
0x14000c24d  push    r14
0x14000c24f  push    r15
0x14000c251  sub     rsp, 28h
0x14000c255  lea     rsi, [rdx+80h]
0x14000c25c  mov     [rsp+58h+arg_8], 0
0x14000c261  mov     r15d, r9d
0x14000c264  mov     rdi, r8
0x14000c267  mov     r8b, [rsp+58h+arg_20]
0x14000c26f  mov     r14, rdx
0x14000c272  mov     rdx, rsi
0x14000c275  mov     r9d, 1
0x14000c27b  mov     rbp, rcx
0x14000c27e  call    CdAcquireResource
0x14000c283  test    al, al
0x14000c285  jz      short loc_14000C2B8
0x14000c287  mov     rdx, [rdi+0C8h]
0x14000c28e  xor     r9d, r9d
0x14000c291  mov     r8b, [rsp+58h+arg_20]
0x14000c299  add     rdx, 20h ; ' '
0x14000c29d  mov     rcx, rbp
0x14000c2a0  call    CdAcquireResource
0x14000c2a5  test    al, al
0x14000c2a7  jnz     short loc_14000C2C8
0x14000c2a9  mov     rcx, rsi; Resource
0x14000c2ac  call    cs:__imp_ExReleaseResourceLite
0x14000c2b3  nop     dword ptr [rax+rax+00h]
0x14000c2b8  xor     al, al
0x14000c2ba  add     rsp, 28h
0x14000c2be  pop     r15
0x14000c2c0  pop     r14
0x14000c2c2  pop     rdi
0x14000c2c3  pop     rsi
0x14000c2c4  pop     rbp
0x14000c2c5  pop     rbx
0x14000c2c6  retn
0x14000c2c8  lea     rbx, [r14+150h]
0x14000c2cf  mov     rcx, rbx; FastMutex
0x14000c2d2  call    cs:__imp_ExAcquireFastMutex
0x14000c2d9  nop     dword ptr [rax+rax+00h]
0x14000c2de  mov     rax, gs:188h
0x14000c2e7  or      ecx, 0FFFFFFFFh
0x14000c2ea  mov     [r14+188h], rax
0x14000c2f1  mov     rax, [rdi+78h]
0x14000c2f5  add     [rdi+0A4h], ecx
0x14000c2fb  sub     [rdi+0A8h], r15d
0x14000c302  add     [rax+3Ch], ecx
0x14000c305  mov     rcx, rbx; FastMutex
0x14000c308  mov     rax, [rdi+78h]
0x14000c30c  sub     [rax+40h], r15d
0x14000c310  mov     qword ptr [r14+188h], 0
0x14000c31b  call    cs:__imp_ExReleaseFastMutex
0x14000c322  nop     dword ptr [rax+rax+00h]
0x14000c327  lea     r8, [rsp+58h+arg_8]
0x14000c32c  mov     rdx, rdi
0x14000c32f  mov     rcx, rbp
0x14000c332  call    CdTeardownStructures
0x14000c337  cmp     [rsp+58h+arg_8], 0
0x14000c33c  jnz     short loc_14000C355
0x14000c33e  mov     rcx, [rdi+0C8h]
0x14000c345  add     rcx, 20h ; ' '; Resource
0x14000c349  call    cs:__imp_ExReleaseResourceLite
0x14000c350  nop     dword ptr [rax+rax+00h]
0x14000c355  mov     rcx, rsi; Resource
0x14000c358  call    cs:__imp_ExReleaseResourceLite
0x14000c35f  nop     dword ptr [rax+rax+00h]
0x14000c364  mov     al, 1
0x14000c366  jmp     loc_14000C2BA
```
