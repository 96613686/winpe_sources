# NetioTimerWorkItemInitialize

- ea: `0x14005c080`
- end: `0x14005c199`
- name: `NetioTimerWorkItemInitialize`
- size: `281`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID IoObject)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14006aa50`

## callees

- `0x14005c080`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x14005c162`
- `ntoskrnl!ExDeleteTimer` at `0x14005c162`
- `ntoskrnl!IoSizeofWorkItem` at `0x14005c0e8`
- `ntoskrnl!IoSizeofWorkItem` at `0x14005c0e8`
- `ntoskrnl!ExAllocateTimer` at `0x14005c137`
- `ntoskrnl!ExAllocateTimer` at `0x14005c137`
- `ntoskrnl!IoInitializeWorkItem` at `0x14005c11e`
- `ntoskrnl!IoInitializeWorkItem` at `0x14005c11e`
- `ntoskrnl!ExAllocatePool2` at `0x14005c103`
- `ntoskrnl!ExAllocatePool2` at `0x14005c103`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c179`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c179`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005c0c4`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005c0c4`

## pseudocode

```c
__int64 __fastcall NetioTimerWorkItemInitialize(__int64 a1, __int64 a2, __int64 a3, char a4, void *a5, PVOID IoObject)
{
  PVOID v6; // r15
  unsigned int v7; // r14d
  ULONG v12; // eax
  struct _IO_WORKITEM *Pool2; // rax
  __int64 Timer; // rax
  __int64 v15; // rcx
  unsigned int v16; // ebx
  void *v17; // rcx

  v6 = a5;
  *(_OWORD *)a1 = 0;
  v7 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  if ( !a5 )
    v6 = IoObject;
  *(_QWORD *)(a1 + 48) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)a1);
  *(_QWORD *)(a1 + 32) = a2;
  *(_QWORD *)(a1 + 40) = a3;
  if ( (a4 & 1) != 0 )
  {
    *(_DWORD *)(a1 + 52) |= 4u;
    v7 = 8;
  }
  v12 = IoSizeofWorkItem();
  Pool2 = (struct _IO_WORKITEM *)ExAllocatePool2(64, v12, 1364682062);
  *(_QWORD *)(a1 + 8) = Pool2;
  if ( Pool2
    && (IoInitializeWorkItem(v6, Pool2),
        Timer = ExAllocateTimer(&NetiopTimerWorkItemTimeout, a1, v7),
        (*(_QWORD *)(a1 + 16) = Timer) != 0) )
  {
    return 0;
  }
  else
  {
    v15 = *(_QWORD *)(a1 + 16);
    v16 = -1073741801;
    if ( v15 )
      ExDeleteTimer(v15, 0, 0, 0);
    v17 = *(void **)(a1 + 8);
    if ( v17 )
      ExFreePoolWithTag(v17, 0x5157654Eu);
  }
  return v16;
}

```

## disassembly

```asm
0x14005c080  push    rbx
0x14005c082  push    rbp
0x14005c083  push    rsi
0x14005c084  push    rdi
0x14005c085  push    r14
0x14005c087  push    r15
0x14005c089  sub     rsp, 28h
0x14005c08d  mov     r15, [rsp+58h+arg_20]
0x14005c095  xorps   xmm0, xmm0
0x14005c098  movups  xmmword ptr [rcx], xmm0
0x14005c09b  xor     r14d, r14d
0x14005c09e  mov     esi, r9d
0x14005c0a1  movups  xmmword ptr [rcx+10h], xmm0
0x14005c0a5  test    r15, r15
0x14005c0a8  mov     rdi, r8
0x14005c0ab  movups  xmmword ptr [rcx+20h], xmm0
0x14005c0af  cmovz   r15, [rsp+58h+IoObject]
0x14005c0b8  mov     rbx, rdx
0x14005c0bb  xor     eax, eax
0x14005c0bd  mov     rbp, rcx
0x14005c0c0  mov     [rcx+30h], rax
0x14005c0c4  call    cs:__imp_KeInitializeSpinLock
0x14005c0cb  nop     dword ptr [rax+rax+00h]
0x14005c0d0  mov     [rbp+20h], rbx
0x14005c0d4  mov     [rbp+28h], rdi
0x14005c0d8  test    sil, 1
0x14005c0dc  jz      short loc_14005C0E8
0x14005c0de  or      dword ptr [rbp+34h], 4
0x14005c0e2  mov     r14d, 8
0x14005c0e8  call    cs:__imp_IoSizeofWorkItem
0x14005c0ef  nop     dword ptr [rax+rax+00h]
0x14005c0f4  mov     edi, 5157654Eh
0x14005c0f9  mov     edx, eax
0x14005c0fb  mov     r8d, edi
0x14005c0fe  mov     ecx, 40h ; '@'
0x14005c103  call    cs:__imp_ExAllocatePool2
0x14005c10a  nop     dword ptr [rax+rax+00h]
0x14005c10f  mov     [rbp+8], rax
0x14005c113  test    rax, rax
0x14005c116  jz      short loc_14005C14C
0x14005c118  mov     rdx, rax; IoWorkItem
0x14005c11b  mov     rcx, r15; IoObject
0x14005c11e  call    cs:__imp_IoInitializeWorkItem
0x14005c125  nop     dword ptr [rax+rax+00h]
0x14005c12a  mov     r8d, r14d
0x14005c12d  lea     rcx, NetiopTimerWorkItemTimeout
0x14005c134  mov     rdx, rbp
0x14005c137  call    cs:__imp_ExAllocateTimer
0x14005c13e  nop     dword ptr [rax+rax+00h]
0x14005c143  mov     [rbp+10h], rax
0x14005c147  test    rax, rax
0x14005c14a  jnz     short loc_14005C187
0x14005c14c  mov     rcx, [rbp+10h]
0x14005c150  mov     ebx, 0C0000017h
0x14005c155  test    rcx, rcx
0x14005c158  jz      short loc_14005C16E
0x14005c15a  xor     r9d, r9d
0x14005c15d  xor     r8d, r8d
0x14005c160  xor     edx, edx
0x14005c162  call    cs:__imp_ExDeleteTimer
0x14005c169  nop     dword ptr [rax+rax+00h]
0x14005c16e  mov     rcx, [rbp+8]; P
0x14005c172  test    rcx, rcx
0x14005c175  jz      short loc_14005C189
0x14005c177  mov     edx, edi; Tag
0x14005c179  call    cs:__imp_ExFreePoolWithTag
0x14005c180  nop     dword ptr [rax+rax+00h]
0x14005c185  jmp     short loc_14005C189
0x14005c187  xor     ebx, ebx
0x14005c189  mov     eax, ebx
0x14005c18b  add     rsp, 28h
0x14005c18f  pop     r15
0x14005c191  pop     r14
0x14005c193  pop     rdi
0x14005c194  pop     rsi
0x14005c195  pop     rbp
0x14005c196  pop     rbx
0x14005c197  retn
```
