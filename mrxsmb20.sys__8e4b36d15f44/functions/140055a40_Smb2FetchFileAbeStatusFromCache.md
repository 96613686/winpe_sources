# Smb2FetchFileAbeStatusFromCache

- ea: `0x140055a40`
- end: `0x140055bc4`
- name: `Smb2FetchFileAbeStatusFromCache`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003840`

## callees

- `0x140010230`
- `0x140037120`
- `0x140055a40`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140055b7b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140055b7b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140055b12`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140055b12`
- `rdbss!RxNameCacheCheckEntry` at `0x140055b4b`
- `rdbss!RxNameCacheCheckEntry` at `0x140055b4b`
- `rdbss!RxNameCacheExpireEntry` at `0x140055b61`
- `rdbss!RxNameCacheExpireEntry` at `0x140055b61`
- `rdbss!RxNameCacheActivateEntry` at `0x140055bb6`
- `rdbss!RxNameCacheActivateEntry` at `0x140055bb6`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140055b2e`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140055b2e`

## pseudocode

```c
__int64 __fastcall Smb2FetchFileAbeStatusFromCache(__int64 a1, struct _NAME_CACHE_CONTROL_ *a2)
{
  __int64 v2; // rax
  __int64 v4; // r9
  int v5; // r8d
  __int64 v7; // rdx
  __int64 v8; // rbp
  int v9; // ebx
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v11; // rsi
  __int64 v12; // [rsp+20h] [rbp-148h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+28h] [rbp-140h] BYREF
  char v14; // [rsp+40h] [rbp-128h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v4 = *(_QWORD *)(v2 + 136);
  v5 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v2 + 120) + 40LL) + 184LL);
  v12 = 0;
  *(_QWORD *)&Destination.Length = 0x1000000;
  Destination.Buffer = (PWSTR)&v14;
  if ( (v5 & 0x800) == 0 )
    return 3221225494LL;
  v7 = *(_QWORD *)(a1 + 72);
  if ( !v7 || (*(_DWORD *)(v4 + 8) & 2) == 0 )
    return 3221225494LL;
  v8 = *(_QWORD *)(*(_QWORD *)(v7 + 40) + 40LL);
  v12 = *(_QWORD *)(v8 + 96);
  v9 = Smb2GenerateFileIdString(&Destination, (ULONGLONG *)(v4 + 24), 0);
  if ( v9 >= 0 )
  {
    ExAcquirePushLockExclusiveEx(&Smb2FileAbeStatusCacheLock, 0);
    Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &Destination, &v12, 0);
    v11 = Entry;
    if ( Entry )
    {
      if ( RxNameCacheCheckEntry(Entry, *(_DWORD *)(v8 + 264)) == RX_NC_SUCCESS )
      {
        RxNameCacheActivateEntry(a2, v11, 0, 0);
        goto LABEL_10;
      }
      RxNameCacheExpireEntry(a2, v11);
    }
    v9 = -1073741802;
LABEL_10:
    ExReleasePushLockExclusiveEx(&Smb2FileAbeStatusCacheLock, 0);
    return (unsigned int)v9;
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140055a40  push    rbx
0x140055a42  push    rdi
0x140055a43  sub     rsp, 158h
0x140055a4a  mov     rax, cs:__security_cookie
0x140055a51  xor     rax, rsp
0x140055a54  mov     [rsp+168h+var_28], rax
0x140055a5c  mov     rax, [rcx+38h]
0x140055a60  mov     rdi, rdx
0x140055a63  mov     r9, [rax+88h]
0x140055a6a  mov     rax, [rax+78h]
0x140055a6e  mov     rdx, [rax+28h]
0x140055a72  lea     rax, [rsp+168h+var_128]
0x140055a77  mov     r8d, [rdx+0B8h]
0x140055a7e  mov     [rsp+168h+var_148], 0
0x140055a87  mov     qword ptr [rsp+168h+Destination.Length], 1000000h
0x140055a90  mov     [rsp+168h+Destination.Buffer], rax
0x140055a95  bt      r8d, 0Bh
0x140055a9a  jb      short loc_140055ABC
0x140055a9c  mov     eax, 0C0000016h
0x140055aa1  mov     rcx, [rsp+168h+var_28]
0x140055aa9  xor     rcx, rsp; StackCookie
0x140055aac  call    __security_check_cookie
0x140055ab1  add     rsp, 158h
0x140055ab8  pop     rdi
0x140055ab9  pop     rbx
0x140055aba  retn
0x140055abc  mov     rdx, [rcx+48h]
0x140055ac0  test    rdx, rdx
0x140055ac3  jz      short loc_140055A9C
0x140055ac5  mov     eax, [r9+8]
0x140055ac9  test    al, 2
0x140055acb  jz      short loc_140055A9C
0x140055acd  mov     rax, [rdx+28h]
0x140055ad1  lea     rcx, [rsp+168h+Destination]; Destination
0x140055ad6  mov     [rsp+168h+arg_10], rbp
0x140055ade  lea     rdx, [r9+18h]
0x140055ae2  xor     r8d, r8d
0x140055ae5  mov     rbp, [rax+28h]
0x140055ae9  mov     rax, [rbp+60h]
0x140055aed  mov     [rsp+168h+var_148], rax
0x140055af2  call    Smb2GenerateFileIdString
0x140055af7  mov     ebx, eax
0x140055af9  test    eax, eax
0x140055afb  js      loc_140055B9E
0x140055b01  xor     edx, edx
0x140055b03  mov     [rsp+168h+var_18], rsi
0x140055b0b  lea     rcx, Smb2FileAbeStatusCacheLock
0x140055b12  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140055b19  nop     dword ptr [rax+rax+00h]
0x140055b1e  xor     r9d, r9d
0x140055b21  lea     r8, [rsp+168h+var_148]
0x140055b26  lea     rdx, [rsp+168h+Destination]
0x140055b2b  mov     rcx, rdi
0x140055b2e  call    cs:__imp_RxNameCacheFetchEntryEx
0x140055b35  nop     dword ptr [rax+rax+00h]
0x140055b3a  mov     rsi, rax
0x140055b3d  test    rax, rax
0x140055b40  jz      short loc_140055B6D
0x140055b42  mov     edx, [rbp+108h]; MRxContext
0x140055b48  mov     rcx, rax; NameCache
0x140055b4b  call    cs:__imp_RxNameCacheCheckEntry
0x140055b52  nop     dword ptr [rax+rax+00h]
0x140055b57  mov     rdx, rsi; NameCache
0x140055b5a  mov     rcx, rdi; NameCacheCtl
0x140055b5d  test    eax, eax
0x140055b5f  jz      short loc_140055BB0
0x140055b61  call    cs:__imp_RxNameCacheExpireEntry
0x140055b68  nop     dword ptr [rax+rax+00h]
0x140055b6d  mov     ebx, 0C0000016h
0x140055b72  xor     edx, edx
0x140055b74  lea     rcx, Smb2FileAbeStatusCacheLock
0x140055b7b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140055b82  nop     dword ptr [rax+rax+00h]
0x140055b87  mov     rsi, [rsp+168h+var_18]
0x140055b8f  mov     eax, ebx
0x140055b91  mov     rbp, [rsp+168h+arg_10]
0x140055b99  jmp     loc_140055AA1
0x140055b9e  mov     rbp, [rsp+168h+arg_10]
0x140055ba6  mov     eax, 0C0000016h
0x140055bab  jmp     loc_140055AA1
0x140055bb0  xor     r9d, r9d; MRxContext
0x140055bb3  xor     r8d, r8d; LifeTime
0x140055bb6  call    cs:__imp_RxNameCacheActivateEntry
0x140055bbd  nop     dword ptr [rax+rax+00h]
0x140055bc2  jmp     short loc_140055B72
```
