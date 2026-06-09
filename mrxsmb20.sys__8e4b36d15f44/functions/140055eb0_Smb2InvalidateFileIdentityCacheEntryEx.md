# Smb2InvalidateFileIdentityCacheEntryEx

- ea: `0x140055eb0`
- end: `0x140055fa2`
- name: `Smb2InvalidateFileIdentityCacheEntryEx`
- size: `242`
- prototype: `__int64 __fastcall(__int64, struct _NAME_CACHE_CONTROL_ *, __int64, char)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14001d020`
- `0x1400236b0`
- `0x140024b10`
- `0x14002f280`

## callees

- `0x140055eb0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140055f5d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140055f5d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140055f10`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140055f10`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x140055f80`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x140055f80`
- `rdbss!RxNameCacheExpireEntry` at `0x140055f94`
- `rdbss!RxNameCacheExpireEntry` at `0x140055f94`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140055f3c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140055f3c`
- `rdbss!RxCrackPathName` at `0x140055efb`
- `rdbss!RxCrackPathName` at `0x140055efb`

## pseudocode

```c
__int64 __fastcall Smb2InvalidateFileIdentityCacheEntryEx(
        __int64 a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        __int64 a3,
        char a4)
{
  __int64 v5; // rax
  __int64 v7; // r8
  int i; // ebx
  struct _NAME_CACHE *Entry; // rax
  __int128 v11; // [rsp+20h] [rbp-28h] BYREF
  __int128 v12; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  v5 = a3;
  v11 = 0;
  v12 = 0;
  if ( !a3 )
    v5 = *(_QWORD *)(a1 + 56) + 360LL;
  RxCrackPathName(v5, 0, &v11, &v12);
  ExAcquirePushLockExclusiveEx(&Smb2FileIdentityCacheLock, 0);
  if ( a4 )
  {
    LOBYTE(v7) = 1;
    RxNameCacheExpireEntriesWithPrefixEx(a2, &v11, v7);
  }
  else
  {
    for ( i = 1; i <= 4; ++i )
    {
      v13 = (unsigned int)i;
      Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &v11, &v13, 0);
      if ( Entry )
        RxNameCacheExpireEntry(a2, Entry);
    }
  }
  return ExReleasePushLockExclusiveEx(&Smb2FileIdentityCacheLock, 0);
}

```

## disassembly

```asm
0x140055eb0  mov     [rsp+arg_0], rbx
0x140055eb5  push    rdi
0x140055eb6  sub     rsp, 40h
0x140055eba  mov     [rsp+48h+arg_10], 0
0x140055ec3  xorps   xmm0, xmm0
0x140055ec6  xorps   xmm1, xmm1
0x140055ec9  movzx   ebx, r9b
0x140055ecd  mov     rax, r8
0x140055ed0  mov     rdi, rdx
0x140055ed3  movups  [rsp+48h+var_28], xmm0
0x140055ed8  movups  [rsp+48h+var_18], xmm1
0x140055edd  test    r8, r8
0x140055ee0  jnz     short loc_140055EEC
0x140055ee2  mov     rax, [rcx+38h]
0x140055ee6  add     rax, 168h
0x140055eec  lea     r9, [rsp+48h+var_18]
0x140055ef1  xor     edx, edx
0x140055ef3  lea     r8, [rsp+48h+var_28]
0x140055ef8  mov     rcx, rax
0x140055efb  call    cs:__imp_RxCrackPathName
0x140055f02  nop     dword ptr [rax+rax+00h]
0x140055f07  xor     edx, edx
0x140055f09  lea     rcx, Smb2FileIdentityCacheLock
0x140055f10  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140055f17  nop     dword ptr [rax+rax+00h]
0x140055f1c  test    bl, bl
0x140055f1e  jnz     short loc_140055F75
0x140055f20  mov     ebx, 1
0x140055f25  mov     eax, ebx
0x140055f27  lea     r8, [rsp+48h+arg_10]
0x140055f2c  xor     r9d, r9d
0x140055f2f  mov     [rsp+48h+arg_10], rax
0x140055f34  lea     rdx, [rsp+48h+var_28]
0x140055f39  mov     rcx, rdi
0x140055f3c  call    cs:__imp_RxNameCacheFetchEntryEx
0x140055f43  nop     dword ptr [rax+rax+00h]
0x140055f48  test    rax, rax
0x140055f4b  jnz     short loc_140055F8E
0x140055f4d  inc     ebx
0x140055f4f  cmp     ebx, 4
0x140055f52  jle     short loc_140055F25
0x140055f54  xor     edx, edx
0x140055f56  lea     rcx, Smb2FileIdentityCacheLock
0x140055f5d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140055f64  nop     dword ptr [rax+rax+00h]
0x140055f69  mov     rbx, [rsp+48h+arg_0]
0x140055f6e  add     rsp, 40h
0x140055f72  pop     rdi
0x140055f73  retn
0x140055f75  mov     r8b, 1
0x140055f78  lea     rdx, [rsp+48h+var_28]
0x140055f7d  mov     rcx, rdi
0x140055f80  call    cs:__imp_RxNameCacheExpireEntriesWithPrefixEx
0x140055f87  nop     dword ptr [rax+rax+00h]
0x140055f8c  jmp     short loc_140055F54
0x140055f8e  mov     rdx, rax; NameCache
0x140055f91  mov     rcx, rdi; NameCacheCtl
0x140055f94  call    cs:__imp_RxNameCacheExpireEntry
0x140055f9b  nop     dword ptr [rax+rax+00h]
0x140055fa0  jmp     short loc_140055F4D
```
