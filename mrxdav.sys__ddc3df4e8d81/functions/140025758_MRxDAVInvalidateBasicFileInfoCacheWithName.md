# MRxDAVInvalidateBasicFileInfoCacheWithName

- ea: `0x140025758`
- end: `0x140025800`
- name: `MRxDAVInvalidateBasicFileInfoCacheWithName`
- size: `168`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001f6c0`
- `0x140025808`

## callees

- `0x1400027ac`
- `0x140025758`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140025770`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025770`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400257e8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400257e8`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025789`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025789`
- `rdbss!RxNameCacheExpireEntry` at `0x1400257a1`
- `rdbss!RxNameCacheExpireEntry` at `0x1400257a1`

## pseudocode

```c
void __fastcall MRxDAVInvalidateBasicFileInfoCacheWithName(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  struct _NAME_CACHE *Entry; // rax

  v2 = *(_QWORD *)(a2 + 40);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v2 + 16, a1, 0, 0);
  if ( Entry )
  {
    RxNameCacheExpireEntry((PNAME_CACHE_CONTROL)(v2 + 16), Entry);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 3), 16, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids, a1);
  }
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
}

```

## disassembly

```asm
0x140025758  mov     [rsp+arg_0], rbx
0x14002575d  push    rdi
0x14002575e  sub     rsp, 20h
0x140025762  mov     rbx, [rdx+28h]
0x140025766  mov     rdi, rcx
0x140025769  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025770  call    cs:__imp_ExAcquireFastMutex
0x140025777  nop     dword ptr [rax+rax+00h]
0x14002577c  xor     r9d, r9d
0x14002577f  lea     rcx, [rbx+10h]
0x140025783  xor     r8d, r8d
0x140025786  mov     rdx, rdi
0x140025789  call    cs:__imp_RxNameCacheFetchEntryEx
0x140025790  nop     dword ptr [rax+rax+00h]
0x140025795  test    rax, rax
0x140025798  jz      short loc_1400257E1
0x14002579a  mov     rdx, rax; NameCache
0x14002579d  lea     rcx, [rbx+10h]; NameCacheCtl
0x1400257a1  call    cs:__imp_RxNameCacheExpireEntry
0x1400257a8  nop     dword ptr [rax+rax+00h]
0x1400257ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400257b4  lea     rax, WPP_GLOBAL_Control
0x1400257bb  cmp     rcx, rax
0x1400257be  jz      short loc_1400257E1
0x1400257c0  test    dword ptr [rcx+2Ch], 2000h
0x1400257c7  jz      short loc_1400257E1
0x1400257c9  mov     rcx, [rcx+18h]
0x1400257cd  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x1400257d4  mov     edx, 10h
0x1400257d9  mov     r9, rdi
0x1400257dc  call    WPP_SF_Z
0x1400257e1  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x1400257e8  call    cs:__imp_ExReleaseFastMutex
0x1400257ef  nop     dword ptr [rax+rax+00h]
0x1400257f4  mov     rbx, [rsp+28h+arg_0]
0x1400257f9  add     rsp, 20h
0x1400257fd  pop     rdi
0x1400257fe  retn
```
