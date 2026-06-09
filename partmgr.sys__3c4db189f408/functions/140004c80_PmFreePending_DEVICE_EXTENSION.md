# PmFreePending(_DEVICE_EXTENSION *)

- ea: `0x140004c80`
- end: `0x140004d12`
- name: `?PmFreePending@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `146`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140005c50`

## callees

- `0x140004c80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004cfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004cfd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004cbb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004cbb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004c99`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004c99`

## pseudocode

```c
void __fastcall PmFreePending(KSPIN_LOCK *a1)
{
  KSPIN_LOCK *v1; // rbp
  _QWORD **v2; // rdi
  KIRQL v3; // al
  _QWORD *v4; // rbx
  KIRQL v5; // r14
  _QWORD **v6; // rsi
  _QWORD *v7; // rcx
  __int64 v8; // rax
  _QWORD *v9; // rdx

  v1 = a1 + 14;
  v2 = (_QWORD **)(a1 + 112);
  v3 = KeAcquireSpinLockRaiseToDpc(a1 + 14);
  v4 = *v2;
  v5 = v3;
  while ( v4 != v2 )
  {
    v6 = (_QWORD **)(v4 + 23);
    while ( 1 )
    {
      v7 = *v6;
      if ( *v6 == v6 )
        break;
      v8 = *v7;
      if ( *(_QWORD **)(*v7 + 8LL) != v7 || (v9 = (_QWORD *)v7[1], (_QWORD *)*v9 != v7) )
        __fastfail(3u);
      *v9 = v8;
      *(_QWORD *)(v8 + 8) = v9;
      ExFreePoolWithTag(v7, 0);
    }
    v4 = (_QWORD *)*v4;
  }
  KeReleaseSpinLock(v1, v5);
}

```

## disassembly

```asm
0x140004c80  push    rbx
0x140004c82  push    rbp
0x140004c83  push    rsi
0x140004c84  push    rdi
0x140004c85  push    r14
0x140004c87  sub     rsp, 20h
0x140004c8b  lea     rbp, [rcx+70h]
0x140004c8f  lea     rdi, [rcx+380h]
0x140004c96  mov     rcx, rbp; SpinLock
0x140004c99  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004ca0  nop     dword ptr [rax+rax+00h]
0x140004ca5  mov     rbx, [rdi]
0x140004ca8  mov     r14b, al
0x140004cab  jmp     short loc_140004CB0
0x140004cad  mov     rbx, [rbx]
0x140004cb0  cmp     rbx, rdi
0x140004cb3  jnz     short loc_140004CD3
0x140004cb5  mov     dl, r14b; NewIrql
0x140004cb8  mov     rcx, rbp; SpinLock
0x140004cbb  call    cs:__imp_KeReleaseSpinLock
0x140004cc2  nop     dword ptr [rax+rax+00h]
0x140004cc7  add     rsp, 20h
0x140004ccb  pop     r14
0x140004ccd  pop     rdi
0x140004cce  pop     rsi
0x140004ccf  pop     rbp
0x140004cd0  pop     rbx
0x140004cd1  retn
0x140004cd3  lea     rsi, [rbx+0B8h]
0x140004cda  mov     rcx, [rsi]; P
0x140004cdd  cmp     rcx, rsi
0x140004ce0  jz      short loc_140004CAD
0x140004ce2  mov     rax, [rcx]
0x140004ce5  cmp     [rax+8], rcx
0x140004ce9  jnz     short loc_140004D0B
0x140004ceb  mov     rdx, [rcx+8]
0x140004cef  cmp     [rdx], rcx
0x140004cf2  jnz     short loc_140004D0B
0x140004cf4  mov     [rdx], rax
0x140004cf7  mov     [rax+8], rdx
0x140004cfb  xor     edx, edx; Tag
0x140004cfd  call    cs:__imp_ExFreePoolWithTag
0x140004d04  nop     dword ptr [rax+rax+00h]
0x140004d09  jmp     short loc_140004CDA
0x140004d0b  mov     ecx, 3
0x140004d10  int     29h; Win8: RtlFailFast(ecx)
```
