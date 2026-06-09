# ReferenceCompletionContext

- ea: `0x140001008`
- end: `0x140001080`
- name: `ReferenceCompletionContext`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a7e0`

## callees

- `0x140001008`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001027`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001027`
- `ntoskrnl!ObfReferenceObject` at `0x140001055`
- `ntoskrnl!ObfReferenceObject` at `0x140001055`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001067`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001067`

## pseudocode

```c
__int64 __fastcall ReferenceCompletionContext(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // al
  __int64 v6; // rdx
  KIRQL v7; // bp
  void *v8; // rcx

  v2 = (KSPIN_LOCK *)(a2 + 184);
  *(_OWORD *)a1 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 184));
  v6 = *(_QWORD *)(a2 + 176);
  v7 = v5;
  if ( v6 )
  {
    v8 = *(void **)v6;
    *(_QWORD *)(a1 + 8) = *(_QWORD *)(v6 + 8);
    *(_QWORD *)a1 = v8;
    if ( v8 )
      ObfReferenceObject(v8);
  }
  KeReleaseSpinLock(v2, v7);
  return a1;
}

```

## disassembly

```asm
0x140001008  push    rbx
0x14000100a  push    rbp
0x14000100b  push    rsi
0x14000100c  push    rdi
0x14000100d  sub     rsp, 28h
0x140001011  xorps   xmm0, xmm0
0x140001014  lea     rsi, [rdx+0B8h]
0x14000101b  movups  xmmword ptr [rcx], xmm0
0x14000101e  mov     rdi, rcx
0x140001021  mov     rbx, rdx
0x140001024  mov     rcx, rsi; SpinLock
0x140001027  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000102e  nop     dword ptr [rax+rax+00h]
0x140001033  mov     rdx, [rbx+0B0h]
0x14000103a  mov     bpl, al
0x14000103d  test    rdx, rdx
0x140001040  jz      short loc_140001061
0x140001042  mov     rcx, [rdx]; Object
0x140001045  mov     rdx, [rdx+8]
0x140001049  mov     [rdi+8], rdx
0x14000104d  mov     [rdi], rcx
0x140001050  test    rcx, rcx
0x140001053  jz      short loc_140001061
0x140001055  call    cs:__imp_ObfReferenceObject
0x14000105c  nop     dword ptr [rax+rax+00h]
0x140001061  mov     dl, bpl; NewIrql
0x140001064  mov     rcx, rsi; SpinLock
0x140001067  call    cs:__imp_KeReleaseSpinLock
0x14000106e  nop     dword ptr [rax+rax+00h]
0x140001073  mov     rax, rdi
0x140001076  add     rsp, 28h
0x14000107a  pop     rdi
0x14000107b  pop     rsi
0x14000107c  pop     rbp
0x14000107d  pop     rbx
0x14000107e  retn
```
