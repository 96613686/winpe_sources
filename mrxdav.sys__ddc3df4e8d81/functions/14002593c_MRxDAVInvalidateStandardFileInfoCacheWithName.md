# MRxDAVInvalidateStandardFileInfoCacheWithName

- ea: `0x14002593c`
- end: `0x140025a01`
- name: `MRxDAVInvalidateStandardFileInfoCacheWithName`
- size: `197`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001f6c0`
- `0x140025808`

## callees

- `0x1400028e4`
- `0x14002593c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140025959`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025959`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400259e4`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400259e4`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025975`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025975`
- `rdbss!RxNameCacheExpireEntry` at `0x140025993`
- `rdbss!RxNameCacheExpireEntry` at `0x140025993`

## pseudocode

```c
void __fastcall MRxDAVInvalidateStandardFileInfoCacheWithName(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v5; // rbx

  v2 = *(_QWORD *)(a2 + 40);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v2 + 200, a1, 0, 0);
  v5 = Entry;
  if ( Entry )
  {
    RxNameCacheExpireEntry((PNAME_CACHE_CONTROL)(v2 + 200), Entry);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        17,
        (unsigned int)WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids,
        v5->Link.Flink->Blink,
        a1);
  }
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
}

```

## disassembly

```asm
0x14002593c  mov     [rsp+arg_0], rbx
0x140025941  mov     [rsp+arg_8], rsi
0x140025946  push    rdi
0x140025947  sub     rsp, 30h
0x14002594b  mov     rdi, [rdx+28h]
0x14002594f  mov     rsi, rcx
0x140025952  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025959  call    cs:__imp_ExAcquireFastMutex
0x140025960  nop     dword ptr [rax+rax+00h]
0x140025965  xor     r9d, r9d
0x140025968  lea     rcx, [rdi+0C8h]
0x14002596f  xor     r8d, r8d
0x140025972  mov     rdx, rsi
0x140025975  call    cs:__imp_RxNameCacheFetchEntryEx
0x14002597c  nop     dword ptr [rax+rax+00h]
0x140025981  mov     rbx, rax
0x140025984  test    rax, rax
0x140025987  jz      short loc_1400259DD
0x140025989  mov     rdx, rax; NameCache
0x14002598c  lea     rcx, [rdi+0C8h]; NameCacheCtl
0x140025993  call    cs:__imp_RxNameCacheExpireEntry
0x14002599a  nop     dword ptr [rax+rax+00h]
0x14002599f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400259a6  lea     rax, WPP_GLOBAL_Control
0x1400259ad  cmp     rcx, rax
0x1400259b0  jz      short loc_1400259DD
0x1400259b2  test    dword ptr [rcx+2Ch], 2000h
0x1400259b9  jz      short loc_1400259DD
0x1400259bb  mov     r9, [rbx+28h]
0x1400259bf  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x1400259c6  mov     rcx, [rcx+18h]
0x1400259ca  mov     edx, 11h
0x1400259cf  mov     [rsp+38h+var_18], rsi
0x1400259d4  mov     r9d, [r9+8]
0x1400259d8  call    WPP_SF_dZ
0x1400259dd  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x1400259e4  call    cs:__imp_ExReleaseFastMutex
0x1400259eb  nop     dword ptr [rax+rax+00h]
0x1400259f0  mov     rbx, [rsp+38h+arg_0]
0x1400259f5  mov     rsi, [rsp+38h+arg_8]
0x1400259fa  add     rsp, 30h
0x1400259fe  pop     rdi
0x1400259ff  retn
```
