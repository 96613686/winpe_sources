# UpCallCreateQueueEx2

- ea: `0x14003a070`
- end: `0x14003a12b`
- name: `UpCallCreateQueueEx2`
- size: `187`
- prototype: `__int64 __fastcall(KSPIN_LOCK **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140039a60`

## callees

- `0x140014570`
- `0x14003a070`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14003a0b0`
- `ntoskrnl!KeInitializeSpinLock` at `0x14003a0b0`
- `ntoskrnl!KeInitializeQueue` at `0x14003a0e0`
- `ntoskrnl!KeInitializeQueue` at `0x14003a0e0`
- `ntoskrnl!ExAllocatePool2` at `0x14003a094`
- `ntoskrnl!ExAllocatePool2` at `0x14003a094`

## pseudocode

```c
__int64 __fastcall UpCallCreateQueueEx2(KSPIN_LOCK **a1)
{
  KSPIN_LOCK *Pool2; // rax
  KSPIN_LOCK *v3; // rbx
  int v4; // edi
  _DWORD *v5; // rsi

  *a1 = 0;
  Pool2 = (KSPIN_LOCK *)ExAllocatePool2(66, 25728, 1717924437);
  v3 = Pool2;
  if ( Pool2 )
  {
    v4 = 128;
    KeInitializeSpinLock(Pool2);
    *((_DWORD *)v3 + 2) = 128;
    *(KSPIN_LOCK *)((char *)v3 + 12) = 128;
    v3[3] = 0;
    v3[4] = 0;
    *((_DWORD *)v3 + 26) = 0;
    KeInitializeQueue((PRKQUEUE)(v3 + 5), 0);
    v5 = v3 + 16;
    do
    {
      v5[5] = 1;
      FreeRequest(v3, v5);
      v5 += 50;
      --v4;
    }
    while ( v4 );
    *a1 = v3;
  }
  return v3 == 0 ? 0xC000009A : 0;
}

```

## disassembly

```asm
0x14003a070  push    rbx
0x14003a072  push    rsi
0x14003a073  push    rdi
0x14003a074  push    r14
0x14003a076  sub     rsp, 28h
0x14003a07a  mov     r14, rcx
0x14003a07d  mov     qword ptr [rcx], 0
0x14003a084  mov     ecx, 42h ; 'B'
0x14003a089  mov     edx, 6480h
0x14003a08e  mov     r8d, 66657255h
0x14003a094  call    cs:__imp_ExAllocatePool2
0x14003a09b  nop     dword ptr [rax+rax+00h]
0x14003a0a0  mov     rbx, rax
0x14003a0a3  test    rax, rax
0x14003a0a6  jz      short loc_14003A114
0x14003a0a8  mov     rcx, rax; SpinLock
0x14003a0ab  mov     edi, 80h
0x14003a0b0  call    cs:__imp_KeInitializeSpinLock
0x14003a0b7  nop     dword ptr [rax+rax+00h]
0x14003a0bc  lea     rcx, [rbx+28h]; Queue
0x14003a0c0  mov     [rbx+8], edi
0x14003a0c3  xor     edx, edx; Count
0x14003a0c5  mov     [rbx+0Ch], rdi
0x14003a0c9  mov     qword ptr [rbx+18h], 0
0x14003a0d1  mov     qword ptr [rbx+20h], 0
0x14003a0d9  mov     dword ptr [rbx+68h], 0
0x14003a0e0  call    cs:__imp_KeInitializeQueue
0x14003a0e7  nop     dword ptr [rax+rax+00h]
0x14003a0ec  lea     rsi, [rbx+80h]
0x14003a0f3  mov     rdx, rsi; P
0x14003a0f6  mov     dword ptr [rsi+14h], 1
0x14003a0fd  mov     rcx, rbx; SpinLock
0x14003a100  call    FreeRequest
0x14003a105  add     rsi, 0C8h
0x14003a10c  add     edi, 0FFFFFFFFh
0x14003a10f  jnz     short loc_14003A0F3
0x14003a111  mov     [r14], rbx
0x14003a114  neg     rbx
0x14003a117  sbb     eax, eax
0x14003a119  not     eax
0x14003a11b  and     eax, 0C000009Ah
0x14003a120  add     rsp, 28h
0x14003a124  pop     r14
0x14003a126  pop     rdi
0x14003a127  pop     rsi
0x14003a128  pop     rbx
0x14003a129  retn
```
