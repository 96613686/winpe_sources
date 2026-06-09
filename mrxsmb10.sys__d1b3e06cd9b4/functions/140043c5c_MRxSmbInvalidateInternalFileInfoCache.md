# MRxSmbInvalidateInternalFileInfoCache

- ea: `0x140043c5c`
- end: `0x140043d6e`
- name: `MRxSmbInvalidateInternalFileInfoCache`
- size: `274`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14002b980`
- `0x140036d40`
- `0x14003a204`
- `0x14003c3f8`
- `0x140052c00`

## callees

- `0x14000e998`
- `0x140043c5c`
- `0x140044700`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x140043d56`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043d56`
- `ntoskrnl!ExAcquireFastMutex` at `0x140043c9e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140043c9e`
- `rdbss!RxNameCacheExpireEntry` at `0x140043ccd`
- `rdbss!RxNameCacheExpireEntry` at `0x140043d43`
- `rdbss!RxNameCacheExpireEntry` at `0x140043ccd`
- `rdbss!RxNameCacheExpireEntry` at `0x140043d43`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140043cb6`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140043d2c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140043cb6`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140043d2c`

## pseudocode

```c
void __fastcall MRxSmbInvalidateInternalFileInfoCache(__int64 a1)
{
  bool v1; // zf
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // rax
  struct _NAME_CACHE_CONTROL_ *v5; // rbx
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v7; // rax
  __int128 v8; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_BYTE *)(a1 + 32) == 0;
  v2 = *(_QWORD *)(a1 + 56);
  v8 = 0;
  v3 = v2 + 360;
  if ( v1 )
    v4 = *(_QWORD *)(a1 + 648);
  else
    v4 = *(_QWORD *)(v2 + 120);
  v5 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v4 + 40) + 656LL);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v5, v3, 0, 0);
  if ( Entry )
  {
    RxNameCacheExpireEntry(v5, Entry);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids, v3);
  }
  if ( (unsigned __int8)MRxSmbIsStreamFile(v3, &v8) )
  {
    v7 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v5, &v8, 0, 0);
    if ( v7 )
      RxNameCacheExpireEntry(v5, v7);
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
}

```

## disassembly

```asm
0x140043c5c  mov     [rsp+arg_0], rbx
0x140043c61  push    rdi
0x140043c62  sub     rsp, 30h
0x140043c66  cmp     byte ptr [rcx+20h], 0
0x140043c6a  xorps   xmm0, xmm0
0x140043c6d  mov     rax, [rcx+38h]
0x140043c71  movups  [rsp+38h+var_18], xmm0
0x140043c76  lea     rdi, [rax+168h]
0x140043c7d  jnz     short loc_140043C88
0x140043c7f  mov     rax, [rcx+288h]
0x140043c86  jmp     short loc_140043C8C
0x140043c88  mov     rax, [rax+78h]
0x140043c8c  mov     rbx, [rax+28h]
0x140043c90  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140043c97  add     rbx, 290h
0x140043c9e  call    cs:__imp_ExAcquireFastMutex
0x140043ca5  nop     dword ptr [rax+rax+00h]
0x140043caa  xor     r9d, r9d
0x140043cad  xor     r8d, r8d
0x140043cb0  mov     rdx, rdi
0x140043cb3  mov     rcx, rbx
0x140043cb6  call    cs:__imp_RxNameCacheFetchEntryEx
0x140043cbd  nop     dword ptr [rax+rax+00h]
0x140043cc2  test    rax, rax
0x140043cc5  jz      short loc_140043D0D
0x140043cc7  mov     rdx, rax; NameCache
0x140043cca  mov     rcx, rbx; NameCacheCtl
0x140043ccd  call    cs:__imp_RxNameCacheExpireEntry
0x140043cd4  nop     dword ptr [rax+rax+00h]
0x140043cd9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043ce0  lea     rax, WPP_GLOBAL_Control
0x140043ce7  cmp     rcx, rax
0x140043cea  jz      short loc_140043D0D
0x140043cec  test    dword ptr [rcx+2Ch], 200h
0x140043cf3  jz      short loc_140043D0D
0x140043cf5  mov     rcx, [rcx+18h]
0x140043cf9  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x140043d00  mov     edx, 0Dh
0x140043d05  mov     r9, rdi
0x140043d08  call    WPP_SF_Z
0x140043d0d  lea     rdx, [rsp+38h+var_18]
0x140043d12  mov     rcx, rdi
0x140043d15  call    MRxSmbIsStreamFile
0x140043d1a  test    al, al
0x140043d1c  jz      short loc_140043D4F
0x140043d1e  xor     r9d, r9d
0x140043d21  lea     rdx, [rsp+38h+var_18]
0x140043d26  xor     r8d, r8d
0x140043d29  mov     rcx, rbx
0x140043d2c  call    cs:__imp_RxNameCacheFetchEntryEx
0x140043d33  nop     dword ptr [rax+rax+00h]
0x140043d38  test    rax, rax
0x140043d3b  jz      short loc_140043D4F
0x140043d3d  mov     rdx, rax; NameCache
0x140043d40  mov     rcx, rbx; NameCacheCtl
0x140043d43  call    cs:__imp_RxNameCacheExpireEntry
0x140043d4a  nop     dword ptr [rax+rax+00h]
0x140043d4f  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140043d56  call    cs:__imp_ExReleaseFastMutex
0x140043d5d  nop     dword ptr [rax+rax+00h]
0x140043d62  mov     rbx, [rsp+38h+arg_0]
0x140043d67  add     rsp, 30h
0x140043d6b  pop     rdi
0x140043d6c  retn
```
