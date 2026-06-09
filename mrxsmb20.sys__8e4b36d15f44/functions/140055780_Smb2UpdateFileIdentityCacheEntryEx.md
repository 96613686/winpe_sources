# Smb2UpdateFileIdentityCacheEntryEx

- ea: `0x140055780`
- end: `0x140055888`
- name: `Smb2UpdateFileIdentityCacheEntryEx`
- size: `264`
- prototype: `__int64 __fastcall(__int64, struct _NAME_CACHE_CONTROL_ *, __int64, int, _OWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140005820`

## callees

- `0x140055780`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005586b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005586b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400557d8`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400557d8`
- `rdbss!RxNameCacheActivateEntry` at `0x140055856`
- `rdbss!RxNameCacheActivateEntry` at `0x140055856`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14005581a`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14005581a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400557f9`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400557f9`
- `rdbss!RxCrackPathName` at `0x1400557c3`
- `rdbss!RxCrackPathName` at `0x1400557c3`

## pseudocode

```c
__int64 __fastcall Smb2UpdateFileIdentityCacheEntryEx(
        __int64 a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        __int64 a3,
        int a4,
        _OWORD *a5)
{
  __int64 v5; // rbx
  __int64 v7; // rcx
  __int64 Entry; // rax
  __int64 v9; // r9
  _OWORD *v10; // r8
  _OWORD *v11; // rdx
  __int128 v13; // [rsp+20h] [rbp-28h] BYREF
  __int128 v14; // [rsp+30h] [rbp-18h] BYREF
  __int64 v15; // [rsp+60h] [rbp+18h] BYREF

  v15 = a3;
  v5 = a4;
  v7 = *(_QWORD *)(a1 + 56) + 360LL;
  v15 = 0;
  v13 = 0;
  v14 = 0;
  RxCrackPathName(v7, 0, &v13, &v14);
  ExAcquirePushLockExclusiveEx(&Smb2FileIdentityCacheLock, 0);
  v15 = v5;
  Entry = RxNameCacheFetchEntryEx(a2, &v13, &v15, 0);
  if ( Entry || (LOBYTE(v9) = 1, (Entry = RxNameCacheCreateEntryEx(a2, &v13, &v15, v9)) != 0) )
  {
    v10 = *(_OWORD **)(Entry + 40);
    v11 = a5;
    *(_DWORD *)(Entry + 48) = 0;
    *v10 = *v11;
    v10[1] = v11[1];
    RxNameCacheActivateEntry(a2, (PNAME_CACHE)Entry, 0x1F4u, 0);
  }
  return ExReleasePushLockExclusiveEx(&Smb2FileIdentityCacheLock, 0);
}

```

## disassembly

```asm
0x140055780  mov     rax, rsp
0x140055783  mov     [rax+8], rbx
0x140055787  mov     [rax+10h], rsi
0x14005578b  mov     [rax+18h], r8
0x14005578f  push    rdi
0x140055790  sub     rsp, 40h
0x140055794  mov     rcx, [rcx+38h]
0x140055798  lea     r8, [rax-28h]
0x14005579c  movsxd  rbx, r9d
0x14005579f  mov     rdi, rdx
0x1400557a2  xorps   xmm0, xmm0
0x1400557a5  lea     r9, [rax-18h]
0x1400557a9  xorps   xmm1, xmm1
0x1400557ac  xor     esi, esi
0x1400557ae  add     rcx, 168h
0x1400557b5  mov     [rax+18h], rsi
0x1400557b9  xor     edx, edx
0x1400557bb  movups  xmmword ptr [rax-28h], xmm0
0x1400557bf  movups  xmmword ptr [rax-18h], xmm1
0x1400557c3  call    cs:__imp_RxCrackPathName
0x1400557ca  nop     dword ptr [rax+rax+00h]
0x1400557cf  xor     edx, edx
0x1400557d1  lea     rcx, Smb2FileIdentityCacheLock
0x1400557d8  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400557df  nop     dword ptr [rax+rax+00h]
0x1400557e4  xor     r9d, r9d
0x1400557e7  mov     [rsp+48h+arg_10], rbx
0x1400557ec  lea     r8, [rsp+48h+arg_10]
0x1400557f1  mov     rcx, rdi
0x1400557f4  lea     rdx, [rsp+48h+var_28]
0x1400557f9  call    cs:__imp_RxNameCacheFetchEntryEx
0x140055800  nop     dword ptr [rax+rax+00h]
0x140055805  test    rax, rax
0x140055808  jnz     short loc_14005582B
0x14005580a  mov     r9b, 1
0x14005580d  lea     r8, [rsp+48h+arg_10]
0x140055812  lea     rdx, [rsp+48h+var_28]
0x140055817  mov     rcx, rdi
0x14005581a  call    cs:__imp_RxNameCacheCreateEntryEx
0x140055821  nop     dword ptr [rax+rax+00h]
0x140055826  test    rax, rax
0x140055829  jz      short loc_140055862
0x14005582b  mov     r8, [rax+28h]
0x14005582f  xor     r9d, r9d; MRxContext
0x140055832  mov     rdx, [rsp+48h+arg_20]
0x140055837  mov     rcx, rdi; NameCacheCtl
0x14005583a  mov     [rax+30h], esi
0x14005583d  movups  xmm0, xmmword ptr [rdx]
0x140055840  movups  xmmword ptr [r8], xmm0
0x140055844  movups  xmm1, xmmword ptr [rdx+10h]
0x140055848  mov     rdx, rax; NameCache
0x14005584b  movups  xmmword ptr [r8+10h], xmm1
0x140055850  mov     r8d, 1F4h; LifeTime
0x140055856  call    cs:__imp_RxNameCacheActivateEntry
0x14005585d  nop     dword ptr [rax+rax+00h]
0x140055862  xor     edx, edx
0x140055864  lea     rcx, Smb2FileIdentityCacheLock
0x14005586b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140055872  nop     dword ptr [rax+rax+00h]
0x140055877  mov     rbx, [rsp+48h+arg_0]
0x14005587c  mov     rsi, [rsp+48h+arg_8]
0x140055881  add     rsp, 40h
0x140055885  pop     rdi
0x140055886  retn
```
