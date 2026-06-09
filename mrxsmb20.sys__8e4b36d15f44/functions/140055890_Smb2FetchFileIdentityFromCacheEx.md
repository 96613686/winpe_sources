# Smb2FetchFileIdentityFromCacheEx

- ea: `0x140055890`
- end: `0x140055a35`
- name: `Smb2FetchFileIdentityFromCacheEx`
- size: `421`
- prototype: `__int64 __fastcall(__int64, struct _NAME_CACHE_CONTROL_ *, __int64, char, struct _LIST_ENTRY *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003840`
- `0x140021fb0`

## callees

- `0x140055890`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140055967`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140055967`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400558f5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400558f5`
- `rdbss!RxNameCacheCheckEntry` at `0x140055937`
- `rdbss!RxNameCacheCheckEntry` at `0x140055937`
- `rdbss!RxNameCacheExpireEntry` at `0x14005594d`
- `rdbss!RxNameCacheExpireEntry` at `0x14005594d`
- `rdbss!RxNameCacheActivateEntry` at `0x1400559b0`
- `rdbss!RxNameCacheActivateEntry` at `0x1400559b0`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14005591a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400559df`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140055a18`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14005591a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400559df`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140055a18`
- `rdbss!RxCrackPathName` at `0x1400558e0`
- `rdbss!RxCrackPathName` at `0x1400558e0`

## pseudocode

```c
__int64 __fastcall Smb2FetchFileIdentityFromCacheEx(
        __int64 a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        __int64 a3,
        char a4,
        struct _LIST_ENTRY *a5)
{
  __int64 v6; // rax
  struct _NAME_CACHE *Entry; // rdi
  unsigned int v9; // ebx
  struct _LIST_ENTRY *v11; // rax
  struct _LIST_ENTRY *Flink; // rdx
  __int128 v13; // [rsp+20h] [rbp-28h] BYREF
  __int128 v14; // [rsp+30h] [rbp-18h] BYREF
  __int64 v15; // [rsp+60h] [rbp+18h] BYREF

  v15 = 0;
  v6 = a3;
  v13 = 0;
  v14 = 0;
  if ( !a3 )
    v6 = *(_QWORD *)(a1 + 56) + 360LL;
  RxCrackPathName(v6, 0, &v13, &v14);
  ExAcquirePushLockExclusiveEx(&Smb2FileIdentityCacheLock, 0);
  v15 = 4;
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &v13, &v15, 0);
  if ( !Entry )
  {
    v15 = 3LL - (a4 != 0);
    Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &v13, &v15, 0);
    if ( !Entry )
    {
      if ( a4 )
        goto LABEL_6;
      v15 = 1;
      Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &v13, &v15, 0);
      if ( !Entry )
        goto LABEL_6;
    }
  }
  if ( RxNameCacheCheckEntry(Entry, 0) )
  {
    RxNameCacheExpireEntry(a2, Entry);
LABEL_6:
    v9 = -1073741802;
    goto LABEL_7;
  }
  v11 = a5;
  v9 = 0;
  if ( a5 )
  {
    Flink = Entry->Link.Flink;
    *a5 = *Flink;
    v11[1] = Flink[1];
  }
  RxNameCacheActivateEntry(a2, Entry, 0, 0);
LABEL_7:
  ExReleasePushLockExclusiveEx(&Smb2FileIdentityCacheLock, 0);
  return v9;
}

```

## disassembly

```asm
0x140055890  mov     [rsp+arg_0], rbx
0x140055895  mov     [rsp+arg_8], rsi
0x14005589a  push    rdi
0x14005589b  sub     rsp, 40h
0x14005589f  mov     [rsp+48h+arg_10], 0
0x1400558a8  xorps   xmm0, xmm0
0x1400558ab  xorps   xmm1, xmm1
0x1400558ae  movzx   ebx, r9b
0x1400558b2  mov     rax, r8
0x1400558b5  mov     rsi, rdx
0x1400558b8  movups  [rsp+48h+var_28], xmm0
0x1400558bd  movups  [rsp+48h+var_18], xmm1
0x1400558c2  test    r8, r8
0x1400558c5  jnz     short loc_1400558D1
0x1400558c7  mov     rax, [rcx+38h]
0x1400558cb  add     rax, 168h
0x1400558d1  lea     r9, [rsp+48h+var_18]
0x1400558d6  xor     edx, edx
0x1400558d8  lea     r8, [rsp+48h+var_28]
0x1400558dd  mov     rcx, rax
0x1400558e0  call    cs:__imp_RxCrackPathName
0x1400558e7  nop     dword ptr [rax+rax+00h]
0x1400558ec  xor     edx, edx
0x1400558ee  lea     rcx, Smb2FileIdentityCacheLock
0x1400558f5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400558fc  nop     dword ptr [rax+rax+00h]
0x140055901  xor     r9d, r9d
0x140055904  mov     [rsp+48h+arg_10], 4
0x14005590d  lea     r8, [rsp+48h+arg_10]
0x140055912  mov     rcx, rsi
0x140055915  lea     rdx, [rsp+48h+var_28]
0x14005591a  call    cs:__imp_RxNameCacheFetchEntryEx
0x140055921  nop     dword ptr [rax+rax+00h]
0x140055926  mov     rdi, rax
0x140055929  test    rax, rax
0x14005592c  jz      loc_1400559BE
0x140055932  xor     edx, edx; MRxContext
0x140055934  mov     rcx, rdi; NameCache
0x140055937  call    cs:__imp_RxNameCacheCheckEntry
0x14005593e  nop     dword ptr [rax+rax+00h]
0x140055943  test    eax, eax
0x140055945  jz      short loc_140055986
0x140055947  mov     rdx, rdi; NameCache
0x14005594a  mov     rcx, rsi; NameCacheCtl
0x14005594d  call    cs:__imp_RxNameCacheExpireEntry
0x140055954  nop     dword ptr [rax+rax+00h]
0x140055959  mov     ebx, 0C0000016h
0x14005595e  xor     edx, edx
0x140055960  lea     rcx, Smb2FileIdentityCacheLock
0x140055967  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005596e  nop     dword ptr [rax+rax+00h]
0x140055973  mov     rsi, [rsp+48h+arg_8]
0x140055978  mov     eax, ebx
0x14005597a  mov     rbx, [rsp+48h+arg_0]
0x14005597f  add     rsp, 40h
0x140055983  pop     rdi
0x140055984  retn
0x140055986  mov     rax, [rsp+48h+arg_20]
0x14005598b  xor     ebx, ebx
0x14005598d  test    rax, rax
0x140055990  jz      short loc_1400559A4
0x140055992  mov     rdx, [rdi+28h]
0x140055996  movups  xmm0, xmmword ptr [rdx]
0x140055999  movups  xmmword ptr [rax], xmm0
0x14005599c  movups  xmm1, xmmword ptr [rdx+10h]
0x1400559a0  movups  xmmword ptr [rax+10h], xmm1
0x1400559a4  xor     r9d, r9d; MRxContext
0x1400559a7  xor     r8d, r8d; LifeTime
0x1400559aa  mov     rdx, rdi; NameCache
0x1400559ad  mov     rcx, rsi; NameCacheCtl
0x1400559b0  call    cs:__imp_RxNameCacheActivateEntry
0x1400559b7  nop     dword ptr [rax+rax+00h]
0x1400559bc  jmp     short loc_14005595E
0x1400559be  movzx   eax, bl
0x1400559c1  lea     r8, [rsp+48h+arg_10]
0x1400559c6  neg     al
0x1400559c8  lea     rdx, [rsp+48h+var_28]
0x1400559cd  sbb     rcx, rcx
0x1400559d0  xor     r9d, r9d
0x1400559d3  add     rcx, 3
0x1400559d7  mov     [rsp+48h+arg_10], rcx
0x1400559dc  mov     rcx, rsi
0x1400559df  call    cs:__imp_RxNameCacheFetchEntryEx
0x1400559e6  nop     dword ptr [rax+rax+00h]
0x1400559eb  mov     rdi, rax
0x1400559ee  test    rax, rax
0x1400559f1  jnz     loc_140055932
0x1400559f7  test    bl, bl
0x1400559f9  jnz     loc_140055959
0x1400559ff  xor     r9d, r9d
0x140055a02  mov     [rsp+48h+arg_10], 1
0x140055a0b  lea     r8, [rsp+48h+arg_10]
0x140055a10  mov     rcx, rsi
0x140055a13  lea     rdx, [rsp+48h+var_28]
0x140055a18  call    cs:__imp_RxNameCacheFetchEntryEx
0x140055a1f  nop     dword ptr [rax+rax+00h]
0x140055a24  mov     rdi, rax
0x140055a27  test    rax, rax
0x140055a2a  jz      loc_140055959
0x140055a30  jmp     loc_140055932
```
