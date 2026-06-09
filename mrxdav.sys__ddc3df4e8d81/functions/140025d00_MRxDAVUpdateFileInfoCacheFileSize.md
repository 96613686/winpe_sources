# MRxDAVUpdateFileInfoCacheFileSize

- ea: `0x140025d00`
- end: `0x140025ded`
- name: `MRxDAVUpdateFileInfoCacheFileSize`
- size: `237`
- prototype: `void __fastcall(__int64, struct _LIST_ENTRY **)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140022a80`
- `0x140023fa0`
- `0x1400241b0`

## callees

- `0x1400028e4`
- `0x140025d00`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140025d35`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025d35`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025dd7`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025dd7`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025d51`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025d51`
- `rdbss!RxNameCacheActivateEntry` at `0x140025d86`
- `rdbss!RxNameCacheActivateEntry` at `0x140025d86`

## pseudocode

```c
void __fastcall MRxDAVUpdateFileInfoCacheFileSize(__int64 a1, struct _LIST_ENTRY **a2)
{
  __int64 v3; // rax
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rbp
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v8; // rbx
  struct _LIST_ENTRY *Flink; // r8

  v3 = *(_QWORD *)(a1 + 56);
  v4 = v3 + 360;
  if ( *(_BYTE *)(a1 + 32) )
    v5 = *(_QWORD *)(v3 + 120);
  else
    v5 = *(_QWORD *)(a1 + 648);
  v6 = *(_QWORD *)(v5 + 40);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v6 + 200, v4, 0, 0);
  v8 = Entry;
  if ( Entry )
  {
    Flink = Entry->Link.Flink;
    Flink->Flink = *a2;
    Flink->Blink = *a2;
    RxNameCacheActivateEntry((PNAME_CACHE_CONTROL)(v6 + 200), Entry, 0, 0);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      WPP_SF_dZ(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        18,
        (unsigned int)WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids,
        v8->Link.Flink->Blink,
        v4);
  }
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
}

```

## disassembly

```asm
0x140025d00  push    rbx
0x140025d02  push    rbp
0x140025d03  push    rsi
0x140025d04  push    rdi
0x140025d05  sub     rsp, 38h
0x140025d09  cmp     byte ptr [rcx+20h], 0
0x140025d0d  mov     rsi, rdx
0x140025d10  mov     rax, [rcx+38h]
0x140025d14  lea     rdi, [rax+168h]
0x140025d1b  jnz     short loc_140025D26
0x140025d1d  mov     rax, [rcx+288h]
0x140025d24  jmp     short loc_140025D2A
0x140025d26  mov     rax, [rax+78h]
0x140025d2a  mov     rbp, [rax+28h]
0x140025d2e  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025d35  call    cs:__imp_ExAcquireFastMutex
0x140025d3c  nop     dword ptr [rax+rax+00h]
0x140025d41  xor     r9d, r9d
0x140025d44  lea     rcx, [rbp+0C8h]
0x140025d4b  xor     r8d, r8d
0x140025d4e  mov     rdx, rdi
0x140025d51  call    cs:__imp_RxNameCacheFetchEntryEx
0x140025d58  nop     dword ptr [rax+rax+00h]
0x140025d5d  mov     rbx, rax
0x140025d60  test    rax, rax
0x140025d63  jz      short loc_140025DD0
0x140025d65  mov     r8, [rax+28h]
0x140025d69  lea     rcx, [rbp+0C8h]; NameCacheCtl
0x140025d70  mov     rdx, [rsi]
0x140025d73  xor     r9d, r9d; MRxContext
0x140025d76  mov     [r8], rdx
0x140025d79  mov     rdx, [rsi]
0x140025d7c  mov     [r8+8], rdx
0x140025d80  xor     r8d, r8d; LifeTime
0x140025d83  mov     rdx, rax; NameCache
0x140025d86  call    cs:__imp_RxNameCacheActivateEntry
0x140025d8d  nop     dword ptr [rax+rax+00h]
0x140025d92  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d99  lea     rax, WPP_GLOBAL_Control
0x140025da0  cmp     rcx, rax
0x140025da3  jz      short loc_140025DD0
0x140025da5  test    dword ptr [rcx+2Ch], 2000h
0x140025dac  jz      short loc_140025DD0
0x140025dae  mov     r9, [rbx+28h]
0x140025db2  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x140025db9  mov     rcx, [rcx+18h]
0x140025dbd  mov     edx, 12h
0x140025dc2  mov     [rsp+58h+var_38], rdi
0x140025dc7  mov     r9d, [r9+8]
0x140025dcb  call    WPP_SF_dZ
0x140025dd0  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025dd7  call    cs:__imp_ExReleaseFastMutex
0x140025dde  nop     dword ptr [rax+rax+00h]
0x140025de3  add     rsp, 38h
0x140025de7  pop     rdi
0x140025de8  pop     rsi
0x140025de9  pop     rbp
0x140025dea  pop     rbx
0x140025deb  retn
```
