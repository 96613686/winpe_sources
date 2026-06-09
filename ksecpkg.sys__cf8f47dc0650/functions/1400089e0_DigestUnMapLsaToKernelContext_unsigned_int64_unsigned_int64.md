# DigestUnMapLsaToKernelContext(unsigned __int64,unsigned __int64)

- ea: `0x1400089e0`
- end: `0x140008a68`
- name: `?DigestUnMapLsaToKernelContext@@YAJ_K0@Z`
- size: `136`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400285b8`

## callees

- `0x140010160`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140008a28`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140008a28`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008a10`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140008a10`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400089fd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400089fd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008a3b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140008a3b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008a47`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140008a47`

## pseudocode

```c
__int64 __fastcall DigestUnMapLsaToKernelContext(__int64 a1, __int64 a2)
{
  _QWORD Buffer[2]; // [rsp+20h] [rbp-28h] BYREF

  Buffer[0] = a1;
  Buffer[1] = a2;
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(&g_DigestKernToLsaContextTableLock);
  RtlDeleteElementGenericTableAvl(&g_DigestKernToLsaContextTable, Buffer);
  ExReleaseFastMutexUnsafe(&g_DigestKernToLsaContextTableLock);
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x1400089e0  sub     rsp, 48h
0x1400089e4  mov     rax, cs:__security_cookie
0x1400089eb  xor     rax, rsp
0x1400089ee  mov     [rsp+48h+var_18], rax
0x1400089f3  mov     [rsp+48h+Buffer], rcx
0x1400089f8  mov     [rsp+48h+var_20], rdx
0x1400089fd  call    cs:__imp_KeEnterCriticalRegion
0x140008a04  nop     dword ptr [rax+rax+00h]
0x140008a09  lea     rcx, ?g_DigestKernToLsaContextTableLock@@3U_FAST_MUTEX@@A; FastMutex
0x140008a10  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140008a17  nop     dword ptr [rax+rax+00h]
0x140008a1c  lea     rdx, [rsp+48h+Buffer]; Buffer
0x140008a21  lea     rcx, ?g_DigestKernToLsaContextTable@@3U_RTL_AVL_TABLE@@A; Table
0x140008a28  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140008a2f  nop     dword ptr [rax+rax+00h]
0x140008a34  lea     rcx, ?g_DigestKernToLsaContextTableLock@@3U_FAST_MUTEX@@A; FastMutex
0x140008a3b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140008a42  nop     dword ptr [rax+rax+00h]
0x140008a47  call    cs:__imp_KeLeaveCriticalRegion
0x140008a4e  nop     dword ptr [rax+rax+00h]
0x140008a53  xor     eax, eax
0x140008a55  mov     rcx, [rsp+48h+var_18]
0x140008a5a  xor     rcx, rsp; StackCookie
0x140008a5d  call    __security_check_cookie
0x140008a62  add     rsp, 48h
0x140008a66  retn
```
