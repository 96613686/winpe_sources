# GetIpAddrs

- ea: `0x140024b08`
- end: `0x140024c37`
- name: `GetIpAddrs`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140047f20`

## callees

- `0x140024b08`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140024b64`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140024b64`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024ba1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140024ba1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024bf1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024c0d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024bf1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024c0d`

## pseudocode

```c
__int64 __fastcall GetIpAddrs(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  unsigned int v5; // edi
  _DWORD *v6; // rbx
  KIRQL v7; // al
  __int64 *v8; // rcx
  int v9; // r8d

  v3 = *(_QWORD *)(a2 + 8);
  if ( !v3 )
    return 3221225485LL;
  v5 = *(_DWORD *)(v3 + 40);
  if ( v5 < 4 )
    return 3221225507LL;
  if ( (*(_BYTE *)(v3 + 10) & 5) != 0 )
    v6 = *(_DWORD **)(v3 + 24);
  else
    v6 = MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000010u);
  if ( !v6 )
    return 3221225473LL;
  if ( *(_DWORD *)(a1 + 340) != 1 )
  {
    *v6++ = *(_DWORD *)(a1 + 488);
    v5 -= 4;
  }
  v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v8 = &NbtConfig;
  while ( 1 )
  {
    v8 = (__int64 *)*v8;
    if ( v8 == &NbtConfig )
      break;
    if ( v5 < 4 )
    {
      KeReleaseSpinLock(&SpinLock, v7);
      return 2147483653LL;
    }
    if ( v8 - 43 != (__int64 *)a1 )
    {
      v9 = *((_DWORD *)v8 + 36);
      if ( v9 )
      {
        *v6++ = v9;
        v5 -= 4;
      }
    }
  }
  KeReleaseSpinLock(&SpinLock, v7);
  if ( v5 < 4 )
    return 2147483653LL;
  *v6 = -1;
  return 0;
}

```

## disassembly

```asm
0x140024b08  mov     [rsp+arg_0], rbx
0x140024b0d  mov     [rsp+arg_8], rsi
0x140024b12  push    rdi
0x140024b13  sub     rsp, 30h
0x140024b17  mov     rsi, rcx
0x140024b1a  mov     rcx, [rdx+8]; MemoryDescriptorList
0x140024b1e  test    rcx, rcx
0x140024b21  jnz     short loc_140024B2D
0x140024b23  mov     eax, 0C000000Dh
0x140024b28  jmp     loc_140024C26
0x140024b2d  mov     edi, [rcx+28h]
0x140024b30  cmp     edi, 4
0x140024b33  jnb     short loc_140024B3F
0x140024b35  mov     eax, 0C0000023h
0x140024b3a  jmp     loc_140024C26
0x140024b3f  test    byte ptr [rcx+0Ah], 5
0x140024b43  jz      short loc_140024B4B
0x140024b45  mov     rbx, [rcx+18h]
0x140024b49  jmp     short loc_140024B73
0x140024b4b  xor     r9d, r9d; RequestedAddress
0x140024b4e  mov     [rsp+38h+Priority], 40000010h; Priority
0x140024b56  xor     edx, edx; AccessMode
0x140024b58  mov     [rsp+38h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140024b60  lea     r8d, [r9+1]; CacheType
0x140024b64  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140024b6b  nop     dword ptr [rax+rax+00h]
0x140024b70  mov     rbx, rax
0x140024b73  test    rbx, rbx
0x140024b76  jnz     short loc_140024B82
0x140024b78  mov     eax, 0C0000001h
0x140024b7d  jmp     loc_140024C26
0x140024b82  cmp     dword ptr [rsi+154h], 1
0x140024b89  jz      short loc_140024B9A
0x140024b8b  mov     eax, [rsi+1E8h]
0x140024b91  mov     [rbx], eax
0x140024b93  add     rbx, 4
0x140024b97  add     edi, 0FFFFFFFCh
0x140024b9a  lea     rcx, SpinLock; SpinLock
0x140024ba1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140024ba8  nop     dword ptr [rax+rax+00h]
0x140024bad  lea     r9, NbtConfig
0x140024bb4  mov     rcx, r9
0x140024bb7  mov     rcx, [rcx]
0x140024bba  cmp     rcx, r9
0x140024bbd  jz      short loc_140024C04
0x140024bbf  cmp     edi, 4
0x140024bc2  jb      short loc_140024BE8
0x140024bc4  lea     rdx, [rcx-158h]
0x140024bcb  cmp     rdx, rsi
0x140024bce  jz      short loc_140024BB7
0x140024bd0  mov     r8d, [rdx+1E8h]
0x140024bd7  test    r8d, r8d
0x140024bda  jz      short loc_140024BB7
0x140024bdc  mov     [rbx], r8d
0x140024bdf  add     rbx, 4
0x140024be3  add     edi, 0FFFFFFFCh
0x140024be6  jmp     short loc_140024BB7
0x140024be8  mov     dl, al; NewIrql
0x140024bea  lea     rcx, SpinLock; SpinLock
0x140024bf1  call    cs:__imp_KeReleaseSpinLock
0x140024bf8  nop     dword ptr [rax+rax+00h]
0x140024bfd  mov     eax, 80000005h
0x140024c02  jmp     short loc_140024C26
0x140024c04  mov     dl, al; NewIrql
0x140024c06  lea     rcx, SpinLock; SpinLock
0x140024c0d  call    cs:__imp_KeReleaseSpinLock
0x140024c14  nop     dword ptr [rax+rax+00h]
0x140024c19  cmp     edi, 4
0x140024c1c  jb      short loc_140024BFD
0x140024c1e  mov     dword ptr [rbx], 0FFFFFFFFh
0x140024c24  xor     eax, eax
0x140024c26  mov     rbx, [rsp+38h+arg_0]
0x140024c2b  mov     rsi, [rsp+38h+arg_8]
0x140024c30  add     rsp, 30h
0x140024c34  pop     rdi
0x140024c35  retn
```
