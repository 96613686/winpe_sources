# CKSThunkDriver::CreateFilterDevice(_DEVICE_OBJECT *)

- ea: `0x14000a6c0`
- end: `0x14000a768`
- name: `?CreateFilterDevice@CKSThunkDriver@@UEAAPEAVCKernelFilterDevice@@PEAU_DEVICE_OBJECT@@@Z`
- size: `168`
- prototype: `struct CKernelFilterDevice *__fastcall(CKSThunkDriver *__hidden this, struct _DEVICE_OBJECT *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003ac0`
- `0x14000a6c0`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x14000a749`
- `ntoskrnl!KeInitializeMutex` at `0x14000a749`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000a717`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000a717`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a6dd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a6dd`

## pseudocode

```c
struct CKernelFilterDevice *__fastcall CKSThunkDriver::CreateFilterDevice(
        CKSThunkDriver *this,
        struct _DEVICE_OBJECT *a2)
{
  char *PoolWithTag; // rax
  char *v4; // rbx
  __int64 v5; // rax

  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x80u, 0x774E434Bu);
  v4 = PoolWithTag;
  if ( !PoolWithTag )
    return 0;
  memset(PoolWithTag, 0, 0x80u);
  v5 = *((_QWORD *)this + 1);
  *(_QWORD *)v4 = &CKernelFilterDevice::`vftable';
  *((_QWORD *)v4 + 4) = v5;
  KeInitializeSpinLock((PKSPIN_LOCK)v4 + 1);
  *((_QWORD *)v4 + 3) = v4 + 16;
  *((_QWORD *)v4 + 2) = v4 + 16;
  *(_QWORD *)v4 = &CKSThunkDevice::`vftable'{for `CKernelFilterDevice'};
  *((_QWORD *)v4 + 8) = &CKSThunkDevice::`vftable'{for `CKSAutomationThunk'};
  KeInitializeMutex((PRKMUTEX)(v4 + 72), 0);
  return (struct CKernelFilterDevice *)v4;
}

```

## disassembly

```asm
0x14000a6c0  mov     [rsp+arg_0], rbx
0x14000a6c5  push    rdi
0x14000a6c6  sub     rsp, 20h
0x14000a6ca  mov     rdi, rcx
0x14000a6cd  mov     edx, 80h; NumberOfBytes
0x14000a6d2  mov     ecx, 200h; PoolType
0x14000a6d7  mov     r8d, 774E434Bh; Tag
0x14000a6dd  call    cs:__imp_ExAllocatePoolWithTag
0x14000a6e4  nop     dword ptr [rax+rax+00h]
0x14000a6e9  mov     rbx, rax
0x14000a6ec  test    rax, rax
0x14000a6ef  jz      short loc_14000A757
0x14000a6f1  xor     edx, edx; Val
0x14000a6f3  mov     r8d, 80h; Size
0x14000a6f9  mov     rcx, rax; void *
0x14000a6fc  call    memset
0x14000a701  mov     rax, [rdi+8]
0x14000a705  lea     rcx, ??_7CKernelFilterDevice@@6B@; const CKernelFilterDevice::`vftable'
0x14000a70c  mov     [rbx], rcx
0x14000a70f  lea     rcx, [rbx+8]; SpinLock
0x14000a713  mov     [rbx+20h], rax
0x14000a717  call    cs:__imp_KeInitializeSpinLock
0x14000a71e  nop     dword ptr [rax+rax+00h]
0x14000a723  lea     rax, [rbx+10h]
0x14000a727  xor     edx, edx; Level
0x14000a729  mov     [rax+8], rax
0x14000a72d  lea     rcx, [rbx+48h]; Mutex
0x14000a731  mov     [rax], rax
0x14000a734  lea     rax, ??_7CKSThunkDevice@@6BCKernelFilterDevice@@@; const CKSThunkDevice::`vftable'{for `CKernelFilterDevice'}
0x14000a73b  mov     [rbx], rax
0x14000a73e  lea     rax, ??_7CKSThunkDevice@@6BCKSAutomationThunk@@@; const CKSThunkDevice::`vftable'{for `CKSAutomationThunk'}
0x14000a745  mov     [rbx+40h], rax
0x14000a749  call    cs:__imp_KeInitializeMutex
0x14000a750  nop     dword ptr [rax+rax+00h]
0x14000a755  jmp     short loc_14000A759
0x14000a757  xor     ebx, ebx
0x14000a759  mov     rax, rbx
0x14000a75c  mov     rbx, [rsp+28h+arg_0]
0x14000a761  add     rsp, 20h
0x14000a765  pop     rdi
0x14000a766  retn
```
