# QuicPartitionUpdateStatelessResetKey

- ea: `0x140028ee0`
- end: `0x140028f66`
- name: `QuicPartitionUpdateStatelessResetKey`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14003f350`

## callees

- `0x140028ee0`
- `0x140034788`
- `0x140034814`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140028f0a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140028f0a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028f1c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028f1c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028f40`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028f40`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028f4c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028f4c`

## pseudocode

```c
__int64 __fastcall QuicPartitionUpdateStatelessResetKey(__int64 a1, __int64 a2, UCHAR *a3)
{
  __int64 result; // rax
  BCRYPT_HASH_HANDLE v5; // [rsp+20h] [rbp-18h] BYREF

  v5 = 0;
  result = CxPlatHashCreate(0, a3, 0x20u, &v5);
  if ( (int)result >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a1 + 40, 0);
    CxPlatHashFree(*(_QWORD *)(a1 + 32));
    *(_QWORD *)(a1 + 32) = v5;
    ExReleasePushLockExclusiveEx(a1 + 40, 0);
    KeLeaveCriticalRegion();
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140028ee0  mov     [rsp+arg_0], rbx
0x140028ee5  push    rdi
0x140028ee6  sub     rsp, 30h
0x140028eea  and     [rsp+38h+var_18], 0
0x140028ef0  lea     r9, [rsp+38h+var_18]
0x140028ef5  mov     rdi, rcx
0x140028ef8  mov     rdx, r8
0x140028efb  xor     ecx, ecx
0x140028efd  lea     r8d, [rcx+20h]
0x140028f01  call    CxPlatHashCreate
0x140028f06  test    eax, eax
0x140028f08  js      short loc_140028F5A
0x140028f0a  call    cs:__imp_KeEnterCriticalRegion
0x140028f11  nop     dword ptr [rax+rax+00h]
0x140028f16  xor     edx, edx
0x140028f18  lea     rcx, [rdi+28h]
0x140028f1c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140028f23  nop     dword ptr [rax+rax+00h]
0x140028f28  mov     rcx, [rdi+20h]
0x140028f2c  call    CxPlatHashFree
0x140028f31  mov     rax, [rsp+38h+var_18]
0x140028f36  lea     rcx, [rdi+28h]
0x140028f3a  xor     edx, edx
0x140028f3c  mov     [rdi+20h], rax
0x140028f40  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140028f47  nop     dword ptr [rax+rax+00h]
0x140028f4c  call    cs:__imp_KeLeaveCriticalRegion
0x140028f53  nop     dword ptr [rax+rax+00h]
0x140028f58  xor     eax, eax
0x140028f5a  mov     rbx, [rsp+38h+arg_0]
0x140028f5f  add     rsp, 30h
0x140028f63  pop     rdi
0x140028f64  retn
```
