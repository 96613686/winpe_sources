# MRxDAVIsFileNotFoundCachedWithName

- ea: `0x140025aa0`
- end: `0x140025b93`
- name: `MRxDAVIsFileNotFoundCachedWithName`
- size: `243`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003698`
- `0x1400130e0`
- `0x14001f6c0`

## callees

- `0x1400027ac`
- `0x140025aa0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140025ac1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025ac1`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025b7a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025b7a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025ad9`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025ad9`
- `rdbss!RxNameCacheActivateEntry` at `0x140025b53`
- `rdbss!RxNameCacheActivateEntry` at `0x140025b53`
- `rdbss!RxNameCacheExpireEntry` at `0x140025b67`
- `rdbss!RxNameCacheExpireEntry` at `0x140025b67`
- `rdbss!RxNameCacheCheckEntry` at `0x140025af7`
- `rdbss!RxNameCacheCheckEntry` at `0x140025af7`

## pseudocode

```c
char __fastcall MRxDAVIsFileNotFoundCachedWithName(__int64 a1, __int64 a2)
{
  struct _NAME_CACHE_CONTROL_ *v3; // rdi
  char v4; // si
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v6; // rbx

  v3 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(a2 + 40) + 384LL);
  v4 = 0;
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v3, a1, 0, 0);
  v6 = Entry;
  if ( Entry )
  {
    if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) || LODWORD(v6->Link.Blink) != -1073741772 )
    {
      RxNameCacheExpireEntry(v3, v6);
    }
    else
    {
      v4 = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 3), 29, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids, a1);
      RxNameCacheActivateEntry(v3, v6, 0, 0);
    }
  }
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
  return v4;
}

```

## disassembly

```asm
0x140025aa0  push    rbx
0x140025aa2  push    rbp
0x140025aa3  push    rsi
0x140025aa4  push    rdi
0x140025aa5  sub     rsp, 28h
0x140025aa9  mov     rdi, [rdx+28h]
0x140025aad  mov     rbp, rcx
0x140025ab0  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025ab7  add     rdi, 180h
0x140025abe  xor     sil, sil
0x140025ac1  call    cs:__imp_ExAcquireFastMutex
0x140025ac8  nop     dword ptr [rax+rax+00h]
0x140025acd  xor     r9d, r9d
0x140025ad0  xor     r8d, r8d
0x140025ad3  mov     rdx, rbp
0x140025ad6  mov     rcx, rdi
0x140025ad9  call    cs:__imp_RxNameCacheFetchEntryEx
0x140025ae0  nop     dword ptr [rax+rax+00h]
0x140025ae5  mov     rbx, rax
0x140025ae8  test    rax, rax
0x140025aeb  jz      loc_140025B73
0x140025af1  mov     edx, [rax+20h]; MRxContext
0x140025af4  mov     rcx, rax; NameCache
0x140025af7  call    cs:__imp_RxNameCacheCheckEntry
0x140025afe  nop     dword ptr [rax+rax+00h]
0x140025b03  test    eax, eax
0x140025b05  jnz     short loc_140025B61
0x140025b07  cmp     dword ptr [rbx+30h], 0C0000034h
0x140025b0e  jnz     short loc_140025B61
0x140025b10  mov     sil, 1
0x140025b13  mov     rcx, cs:WPP_GLOBAL_Control
0x140025b1a  lea     rax, WPP_GLOBAL_Control
0x140025b21  cmp     rcx, rax
0x140025b24  jz      short loc_140025B47
0x140025b26  test    dword ptr [rcx+2Ch], 2000h
0x140025b2d  jz      short loc_140025B47
0x140025b2f  mov     rcx, [rcx+18h]
0x140025b33  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x140025b3a  mov     edx, 1Dh
0x140025b3f  mov     r9, rbp
0x140025b42  call    WPP_SF_Z
0x140025b47  xor     r9d, r9d; MRxContext
0x140025b4a  xor     r8d, r8d; LifeTime
0x140025b4d  mov     rdx, rbx; NameCache
0x140025b50  mov     rcx, rdi; NameCacheCtl
0x140025b53  call    cs:__imp_RxNameCacheActivateEntry
0x140025b5a  nop     dword ptr [rax+rax+00h]
0x140025b5f  jmp     short loc_140025B73
0x140025b61  mov     rdx, rbx; NameCache
0x140025b64  mov     rcx, rdi; NameCacheCtl
0x140025b67  call    cs:__imp_RxNameCacheExpireEntry
0x140025b6e  nop     dword ptr [rax+rax+00h]
0x140025b73  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025b7a  call    cs:__imp_ExReleaseFastMutex
0x140025b81  nop     dword ptr [rax+rax+00h]
0x140025b86  mov     al, sil
0x140025b89  add     rsp, 28h
0x140025b8d  pop     rdi
0x140025b8e  pop     rsi
0x140025b8f  pop     rbp
0x140025b90  pop     rbx
0x140025b91  retn
```
