# MRxSmbInvalidateFullDirectoryCache

- ea: `0x14004ab70`
- end: `0x14004ac46`
- name: `MRxSmbInvalidateFullDirectoryCache`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f310`
- `0x14002a430`
- `0x14004ab38`

## callees

- `0x14000e998`
- `0x14004ab70`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004ac29`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004ac29`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004aba8`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004aba8`
- `rdbss!RxNameCacheExpireEntry` at `0x14004ac16`
- `rdbss!RxNameCacheExpireEntry` at `0x14004ac16`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004abc4`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004abc4`

## pseudocode

```c
void __fastcall MRxSmbInvalidateFullDirectoryCache(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rdi
  struct _NAME_CACHE *Entry; // rsi

  v1 = *(_QWORD *)(a1 + 56);
  v2 = v1 + 360;
  if ( *(_BYTE *)(a1 + 32) )
    v3 = *(_QWORD *)(v1 + 120);
  else
    v3 = *(_QWORD *)(a1 + 648);
  v4 = *(_QWORD *)(v3 + 40);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v4 + 1024, v2, 0, 0);
  if ( Entry )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids, v2);
    RxNameCacheExpireEntry((PNAME_CACHE_CONTROL)(v4 + 1024), Entry);
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
}

```

## disassembly

```asm
0x14004ab70  mov     [rsp+arg_0], rbx
0x14004ab75  mov     [rsp+arg_8], rsi
0x14004ab7a  push    rdi
0x14004ab7b  sub     rsp, 20h
0x14004ab7f  cmp     byte ptr [rcx+20h], 0
0x14004ab83  mov     rax, [rcx+38h]
0x14004ab87  lea     rbx, [rax+168h]
0x14004ab8e  jnz     short loc_14004AB99
0x14004ab90  mov     rax, [rcx+288h]
0x14004ab97  jmp     short loc_14004AB9D
0x14004ab99  mov     rax, [rax+78h]
0x14004ab9d  mov     rdi, [rax+28h]
0x14004aba1  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004aba8  call    cs:__imp_ExAcquireFastMutex
0x14004abaf  nop     dword ptr [rax+rax+00h]
0x14004abb4  xor     r9d, r9d
0x14004abb7  lea     rcx, [rdi+400h]
0x14004abbe  xor     r8d, r8d
0x14004abc1  mov     rdx, rbx
0x14004abc4  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004abcb  nop     dword ptr [rax+rax+00h]
0x14004abd0  mov     rsi, rax
0x14004abd3  test    rax, rax
0x14004abd6  jz      short loc_14004AC22
0x14004abd8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004abdf  lea     rax, WPP_GLOBAL_Control
0x14004abe6  cmp     rcx, rax
0x14004abe9  jz      short loc_14004AC0C
0x14004abeb  test    dword ptr [rcx+2Ch], 200h
0x14004abf2  jz      short loc_14004AC0C
0x14004abf4  mov     rcx, [rcx+18h]
0x14004abf8  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x14004abff  mov     edx, 12h
0x14004ac04  mov     r9, rbx
0x14004ac07  call    WPP_SF_Z
0x14004ac0c  mov     rdx, rsi; NameCache
0x14004ac0f  lea     rcx, [rdi+400h]; NameCacheCtl
0x14004ac16  call    cs:__imp_RxNameCacheExpireEntry
0x14004ac1d  nop     dword ptr [rax+rax+00h]
0x14004ac22  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004ac29  call    cs:__imp_ExReleaseFastMutex
0x14004ac30  nop     dword ptr [rax+rax+00h]
0x14004ac35  mov     rbx, [rsp+28h+arg_0]
0x14004ac3a  mov     rsi, [rsp+28h+arg_8]
0x14004ac3f  add     rsp, 20h
0x14004ac43  pop     rdi
0x14004ac44  retn
```
