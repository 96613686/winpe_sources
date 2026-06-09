# Smb2InvalidateFileAbeStatusCacheEntry

- ea: `0x140056930`
- end: `0x140056a9a`
- name: `Smb2InvalidateFileAbeStatusCacheEntry`
- size: `362`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140005820`
- `0x140013210`
- `0x1400144c0`
- `0x1400236b0`

## callees

- `0x140010230`
- `0x140037120`
- `0x140056930`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140056a5f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140056a5f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400569f5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400569f5`
- `rdbss!RxNameCacheExpireEntry` at `0x140056a2b`
- `rdbss!RxNameCacheExpireEntry` at `0x140056a8c`
- `rdbss!RxNameCacheExpireEntry` at `0x140056a2b`
- `rdbss!RxNameCacheExpireEntry` at `0x140056a8c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140056a14`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140056a45`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140056a75`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140056a14`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140056a45`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140056a75`

## pseudocode

```c
__int64 __fastcall Smb2InvalidateFileAbeStatusCacheEntry(__int64 a1, struct _NAME_CACHE_CONTROL_ *a2, char a3)
{
  __int64 v3; // rax
  __int64 v6; // r10
  __int64 v7; // rdx
  __int64 result; // rax
  int v9; // r9d
  __int64 v10; // rdx
  struct _NAME_CACHE *i; // rax
  struct _NAME_CACHE *Entry; // rax
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-138h] BYREF
  __int64 v14; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v15[256]; // [rsp+40h] [rbp-118h] BYREF

  v3 = *(_QWORD *)(a1 + 56);
  v6 = *(_QWORD *)(v3 + 136);
  v7 = *(_QWORD *)(*(_QWORD *)(v3 + 120) + 40LL);
  result = (__int64)v15;
  v9 = *(_DWORD *)(v7 + 184);
  v14 = 0;
  *(_QWORD *)&Destination.Length = 0x1000000;
  Destination.Buffer = (PWSTR)v15;
  if ( (v9 & 0x800) != 0 )
  {
    v10 = *(_QWORD *)(a1 + 72);
    if ( v10 )
    {
      result = *(unsigned int *)(v6 + 8);
      if ( (result & 2) != 0 )
      {
        v14 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 40) + 40LL) + 96LL);
        result = Smb2GenerateFileIdString(&Destination, (ULONGLONG *)(v6 + 24), 0);
        if ( (int)result >= 0 )
        {
          ExAcquirePushLockExclusiveEx(&Smb2FileAbeStatusCacheLock, 0);
          if ( a3 )
          {
            for ( i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &Destination, 0, 0);
                  i;
                  i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &Destination, 0, 0) )
            {
              RxNameCacheExpireEntry(a2, i);
            }
          }
          else
          {
            Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &Destination, &v14, 0);
            if ( Entry )
              RxNameCacheExpireEntry(a2, Entry);
          }
          return ExReleasePushLockExclusiveEx(&Smb2FileAbeStatusCacheLock, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140056930  mov     [rsp+arg_10], rbx
0x140056935  push    rdi
0x140056936  sub     rsp, 150h
0x14005693d  mov     rax, cs:__security_cookie
0x140056944  xor     rax, rsp
0x140056947  mov     [rsp+158h+var_18], rax
0x14005694f  mov     rax, [rcx+38h]
0x140056953  mov     rbx, rdx
0x140056956  movzx   edi, r8b
0x14005695a  mov     r10, [rax+88h]
0x140056961  mov     rax, [rax+78h]
0x140056965  mov     rdx, [rax+28h]
0x140056969  lea     rax, [rsp+158h+var_118]
0x14005696e  mov     r9d, [rdx+0B8h]
0x140056975  mov     [rsp+158h+var_128], 0
0x14005697e  mov     qword ptr [rsp+158h+Destination.Length], 1000000h
0x140056987  mov     [rsp+158h+Destination.Buffer], rax
0x14005698c  bt      r9d, 0Bh
0x140056991  jb      short loc_1400569B5
0x140056993  mov     rcx, [rsp+158h+var_18]
0x14005699b  xor     rcx, rsp; StackCookie
0x14005699e  call    __security_check_cookie
0x1400569a3  mov     rbx, [rsp+158h+arg_10]
0x1400569ab  add     rsp, 150h
0x1400569b2  pop     rdi
0x1400569b3  retn
0x1400569b5  mov     rdx, [rcx+48h]
0x1400569b9  test    rdx, rdx
0x1400569bc  jz      short loc_140056993
0x1400569be  mov     eax, [r10+8]
0x1400569c2  test    al, 2
0x1400569c4  jz      short loc_140056993
0x1400569c6  mov     rax, [rdx+28h]
0x1400569ca  xor     r8d, r8d
0x1400569cd  lea     rdx, [r10+18h]
0x1400569d1  mov     rcx, [rax+28h]
0x1400569d5  mov     rax, [rcx+60h]
0x1400569d9  lea     rcx, [rsp+158h+Destination]; Destination
0x1400569de  mov     [rsp+158h+var_128], rax
0x1400569e3  call    Smb2GenerateFileIdString
0x1400569e8  test    eax, eax
0x1400569ea  js      short loc_140056993
0x1400569ec  xor     edx, edx
0x1400569ee  lea     rcx, Smb2FileAbeStatusCacheLock
0x1400569f5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400569fc  nop     dword ptr [rax+rax+00h]
0x140056a01  xor     r9d, r9d
0x140056a04  lea     rdx, [rsp+158h+Destination]
0x140056a09  mov     rcx, rbx
0x140056a0c  test    dil, dil
0x140056a0f  jz      short loc_140056A70
0x140056a11  xor     r8d, r8d
0x140056a14  call    cs:__imp_RxNameCacheFetchEntryEx
0x140056a1b  nop     dword ptr [rax+rax+00h]
0x140056a20  test    rax, rax
0x140056a23  jz      short loc_140056A56
0x140056a25  mov     rdx, rax; NameCache
0x140056a28  mov     rcx, rbx; NameCacheCtl
0x140056a2b  call    cs:__imp_RxNameCacheExpireEntry
0x140056a32  nop     dword ptr [rax+rax+00h]
0x140056a37  xor     r9d, r9d
0x140056a3a  lea     rdx, [rsp+158h+Destination]
0x140056a3f  xor     r8d, r8d
0x140056a42  mov     rcx, rbx
0x140056a45  call    cs:__imp_RxNameCacheFetchEntryEx
0x140056a4c  nop     dword ptr [rax+rax+00h]
0x140056a51  test    rax, rax
0x140056a54  jnz     short loc_140056A25
0x140056a56  xor     edx, edx
0x140056a58  lea     rcx, Smb2FileAbeStatusCacheLock
0x140056a5f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140056a66  nop     dword ptr [rax+rax+00h]
0x140056a6b  jmp     loc_140056993
0x140056a70  lea     r8, [rsp+158h+var_128]
0x140056a75  call    cs:__imp_RxNameCacheFetchEntryEx
0x140056a7c  nop     dword ptr [rax+rax+00h]
0x140056a81  test    rax, rax
0x140056a84  jz      short loc_140056A56
0x140056a86  mov     rdx, rax; NameCache
0x140056a89  mov     rcx, rbx; NameCacheCtl
0x140056a8c  call    cs:__imp_RxNameCacheExpireEntry
0x140056a93  nop     dword ptr [rax+rax+00h]
0x140056a98  jmp     short loc_140056A56
```
