# FIPfUserOpenCleanup

- ea: `0x14001070c`
- end: `0x140010801`
- name: `FIPfUserOpenCleanup`
- size: `245`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140010808`
- `0x140012fdc`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x14001070c`
- `0x1400153a0`

## import_xrefs

- `ntoskrnl!PsSetCurrentThreadPrefetching` at `0x140010756`
- `ntoskrnl!PsSetCurrentThreadPrefetching` at `0x140010770`
- `ntoskrnl!PsSetCurrentThreadPrefetching` at `0x140010756`
- `ntoskrnl!PsSetCurrentThreadPrefetching` at `0x140010770`
- `ntoskrnl!ObfDereferenceObject` at `0x1400107cd`
- `ntoskrnl!ObfDereferenceObject` at `0x1400107e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400107cd`
- `ntoskrnl!ObfDereferenceObject` at `0x1400107e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001077c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001077c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010748`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010748`

## pseudocode

```c
void __fastcall FIPfUserOpenCleanup(_QWORD *a1)
{
  __int64 v2; // rcx
  BOOLEAN v3; // bl
  __int64 v4; // rdx
  _QWORD *v5; // rax
  void *v6; // rcx
  void *v7; // rcx
  _QWORD v8[5]; // [rsp+20h] [rbp-28h] BYREF

  v2 = a1[9];
  if ( v2 || a1[8] )
  {
    v8[1] = a1[8];
    v8[0] = a1 + 5;
    v8[3] = a1[10];
    v8[2] = v2;
    KeEnterCriticalRegion();
    v3 = PsSetCurrentThreadPrefetching(1u);
    FIPfInterfaceClose(v8);
    PsSetCurrentThreadPrefetching(v3);
    KeLeaveCriticalRegion();
  }
  if ( (_QWORD *)*a1 != a1 )
  {
    FILockExclusiveAcquire(&qword_140009760);
    v4 = *a1;
    if ( *(_QWORD **)(*a1 + 8LL) != a1 || (v5 = (_QWORD *)a1[1], (_QWORD *)*v5 != a1) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    --dword_140009778;
    FILockExclusiveRelease(&qword_140009760);
  }
  v6 = (void *)a1[7];
  if ( v6 )
    ObfDereferenceObject(v6);
  v7 = (void *)a1[11];
  if ( v7 )
    ObfDereferenceObject(v7);
}

```

## disassembly

```asm
0x14001070c  mov     [rsp+arg_0], rbx
0x140010711  push    rdi
0x140010712  sub     rsp, 40h
0x140010716  mov     rdi, rcx
0x140010719  mov     rcx, [rcx+48h]
0x14001071d  test    rcx, rcx
0x140010720  jnz     short loc_140010728
0x140010722  cmp     [rdi+40h], rcx
0x140010726  jz      short loc_140010788
0x140010728  mov     rax, [rdi+40h]
0x14001072c  mov     [rsp+48h+var_20], rax
0x140010731  lea     rax, [rdi+28h]
0x140010735  mov     [rsp+48h+var_28], rax
0x14001073a  mov     rax, [rdi+50h]
0x14001073e  mov     [rsp+48h+var_10], rax
0x140010743  mov     [rsp+48h+var_18], rcx
0x140010748  call    cs:__imp_KeEnterCriticalRegion
0x14001074f  nop     dword ptr [rax+rax+00h]
0x140010754  mov     cl, 1; Prefetching
0x140010756  call    cs:__imp_PsSetCurrentThreadPrefetching
0x14001075d  nop     dword ptr [rax+rax+00h]
0x140010762  lea     rcx, [rsp+48h+var_28]
0x140010767  mov     bl, al
0x140010769  call    FIPfInterfaceClose
0x14001076e  mov     cl, bl; Prefetching
0x140010770  call    cs:__imp_PsSetCurrentThreadPrefetching
0x140010777  nop     dword ptr [rax+rax+00h]
0x14001077c  call    cs:__imp_KeLeaveCriticalRegion
0x140010783  nop     dword ptr [rax+rax+00h]
0x140010788  cmp     [rdi], rdi
0x14001078b  jz      short loc_1400107C4
0x14001078d  lea     rcx, qword_140009760
0x140010794  call    FILockExclusiveAcquire
0x140010799  mov     rdx, [rdi]
0x14001079c  cmp     [rdx+8], rdi
0x1400107a0  jnz     short loc_1400107FA
0x1400107a2  mov     rax, [rdi+8]
0x1400107a6  cmp     [rax], rdi
0x1400107a9  jnz     short loc_1400107FA
0x1400107ab  mov     [rax], rdx
0x1400107ae  lea     rcx, qword_140009760
0x1400107b5  mov     [rdx+8], rax
0x1400107b9  dec     cs:dword_140009778
0x1400107bf  call    FILockExclusiveRelease
0x1400107c4  mov     rcx, [rdi+38h]; Object
0x1400107c8  test    rcx, rcx
0x1400107cb  jz      short loc_1400107D9
0x1400107cd  call    cs:__imp_ObfDereferenceObject
0x1400107d4  nop     dword ptr [rax+rax+00h]
0x1400107d9  mov     rcx, [rdi+58h]; Object
0x1400107dd  test    rcx, rcx
0x1400107e0  jz      short loc_1400107EE
0x1400107e2  call    cs:__imp_ObfDereferenceObject
0x1400107e9  nop     dword ptr [rax+rax+00h]
0x1400107ee  mov     rbx, [rsp+48h+arg_0]
0x1400107f3  add     rsp, 40h
0x1400107f7  pop     rdi
0x1400107f8  retn
0x1400107fa  mov     ecx, 3
0x1400107ff  int     29h; Win8: RtlFailFast(ecx)
```
