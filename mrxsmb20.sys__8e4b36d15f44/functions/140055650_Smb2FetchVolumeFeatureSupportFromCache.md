# Smb2FetchVolumeFeatureSupportFromCache

- ea: `0x140055650`
- end: `0x14005577a`
- name: `Smb2FetchVolumeFeatureSupportFromCache`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001c70`
- `0x1400028d0`
- `0x140003a80`

## callees

- `0x140037120`
- `0x140055650`

## import_xrefs

- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400556b5`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400556b5`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140055738`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140055738`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400556ca`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400556ca`
- `rdbss!RxNameCacheCheckEntry` at `0x1400556fd`
- `rdbss!RxNameCacheCheckEntry` at `0x1400556fd`
- `rdbss!RxNameCacheExpireEntry` at `0x140055767`
- `rdbss!RxNameCacheExpireEntry` at `0x140055767`
- `rdbss!RxNameCacheActivateEntry` at `0x140055723`
- `rdbss!RxNameCacheActivateEntry` at `0x140055723`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400556e4`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400556e4`

## pseudocode

```c
__int64 __fastcall Smb2FetchVolumeFeatureSupportFromCache(
        __int64 a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        ULONGLONG a3,
        _DWORD *a4)
{
  unsigned int v5; // ebx
  __int64 result; // rax
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v9; // rbp
  struct _UNICODE_STRING v10; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v11[2]; // [rsp+30h] [rbp-48h] BYREF
  __int16 v12; // [rsp+50h] [rbp-28h]

  v5 = 0;
  result = 0;
  *(_DWORD *)(&v10.MaximumLength + 1) = 0;
  v12 = 0;
  memset(v11, 0, sizeof(v11));
  if ( a4 )
  {
    *(_DWORD *)&v10.Length = 2228224;
    v10.Buffer = (PWSTR)v11;
    RtlInt64ToUnicodeString(a3, 0x10u, &v10);
    ExAcquirePushLockExclusiveEx(&Smb2VolumeFeatureSupportCacheLock, 0);
    Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &v10, 0, 0);
    v9 = Entry;
    if ( Entry )
    {
      if ( RxNameCacheCheckEntry(Entry, 0) == RX_NC_SUCCESS )
      {
        *a4 = v9->Link.Flink->Flink;
        RxNameCacheActivateEntry(a2, v9, 0, 0);
LABEL_5:
        ExReleasePushLockExclusiveEx(&Smb2VolumeFeatureSupportCacheLock, 0);
        return v5;
      }
      RxNameCacheExpireEntry(a2, v9);
    }
    v5 = -1073741275;
    goto LABEL_5;
  }
  return result;
}

```

## disassembly

```asm
0x140055650  mov     r11, rsp
0x140055653  push    rbx
0x140055654  push    rsi
0x140055655  push    rdi
0x140055656  sub     rsp, 60h
0x14005565a  mov     rax, cs:__security_cookie
0x140055661  xor     rax, rsp
0x140055664  mov     [rsp+78h+var_20], rax
0x140055669  mov     rdi, r9
0x14005566c  xor     ebx, ebx
0x14005566e  xor     eax, eax
0x140055670  mov     [rsp+78h+var_54], ebx
0x140055674  mov     [rsp+78h+var_28], ax
0x140055679  xorps   xmm0, xmm0
0x14005567c  mov     r9, r8
0x14005567f  mov     rsi, rdx
0x140055682  movups  [rsp+78h+var_48], xmm0
0x140055687  movups  [rsp+78h+var_38], xmm0
0x14005568c  test    rdi, rdi
0x14005568f  jz      loc_14005574E
0x140055695  lea     rax, [r11-48h]
0x140055699  mov     [rsp+78h+var_58], 220000h
0x1400556a1  lea     r8, [r11-58h]; String
0x1400556a5  mov     [r11-50h], rax
0x1400556a9  mov     edx, 10h; Base
0x1400556ae  mov     [r11+8], rbp
0x1400556b2  mov     rcx, r9; Value
0x1400556b5  call    cs:__imp_RtlInt64ToUnicodeString
0x1400556bc  nop     dword ptr [rax+rax+00h]
0x1400556c1  xor     edx, edx
0x1400556c3  lea     rcx, Smb2VolumeFeatureSupportCacheLock
0x1400556ca  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400556d1  nop     dword ptr [rax+rax+00h]
0x1400556d6  xor     r9d, r9d
0x1400556d9  lea     rdx, [rsp+78h+var_58]
0x1400556de  xor     r8d, r8d
0x1400556e1  mov     rcx, rsi
0x1400556e4  call    cs:__imp_RxNameCacheFetchEntryEx
0x1400556eb  nop     dword ptr [rax+rax+00h]
0x1400556f0  mov     rbp, rax
0x1400556f3  test    rax, rax
0x1400556f6  jz      short loc_140055773
0x1400556f8  xor     edx, edx; MRxContext
0x1400556fa  mov     rcx, rax; NameCache
0x1400556fd  call    cs:__imp_RxNameCacheCheckEntry
0x140055704  nop     dword ptr [rax+rax+00h]
0x140055709  mov     rcx, rsi; NameCacheCtl
0x14005570c  test    eax, eax
0x14005570e  jnz     short loc_140055764
0x140055710  mov     rdx, [rbp+28h]
0x140055714  xor     r9d, r9d; MRxContext
0x140055717  mov     r8d, [rdx]
0x14005571a  mov     rdx, rbp; NameCache
0x14005571d  mov     [rdi], r8d
0x140055720  xor     r8d, r8d; LifeTime
0x140055723  call    cs:__imp_RxNameCacheActivateEntry
0x14005572a  nop     dword ptr [rax+rax+00h]
0x14005572f  xor     edx, edx
0x140055731  lea     rcx, Smb2VolumeFeatureSupportCacheLock
0x140055738  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14005573f  nop     dword ptr [rax+rax+00h]
0x140055744  mov     rbp, [rsp+78h+arg_0]
0x14005574c  mov     eax, ebx
0x14005574e  mov     rcx, [rsp+78h+var_20]
0x140055753  xor     rcx, rsp; StackCookie
0x140055756  call    __security_check_cookie
0x14005575b  add     rsp, 60h
0x14005575f  pop     rdi
0x140055760  pop     rsi
0x140055761  pop     rbx
0x140055762  retn
0x140055764  mov     rdx, rbp; NameCache
0x140055767  call    cs:__imp_RxNameCacheExpireEntry
0x14005576e  nop     dword ptr [rax+rax+00h]
0x140055773  mov     ebx, 0C0000225h
0x140055778  jmp     short loc_14005572F
```
