# Smb2UpdateVolumeFeatureSupportCacheEntry

- ea: `0x1400575a0`
- end: `0x1400576ce`
- name: `Smb2UpdateVolumeFeatureSupportCacheEntry`
- size: `302`
- prototype: `__int64 __fastcall(__int64, struct _NAME_CACHE_CONTROL_ *, ULONGLONG, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x140001c70`
- `0x1400028d0`
- `0x140003a80`

## callees

- `0x140037120`
- `0x1400575a0`

## import_xrefs

- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400575fb`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x1400575fb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057669`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140057669`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057610`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140057610`
- `rdbss!RxNameCacheActivateEntry` at `0x1400576c0`
- `rdbss!RxNameCacheActivateEntry` at `0x1400576c0`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14005764c`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14005764c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14005762a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14005762a`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x1400576a7`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x1400576a7`

## pseudocode

```c
__int64 __fastcall Smb2UpdateVolumeFeatureSupportCacheEntry(
        __int64 a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        ULONGLONG a3,
        int a4,
        int a5)
{
  __int64 Entry; // rbx
  __int64 v9; // r9
  __int64 InstanceConfigurationBlock; // rax
  struct _UNICODE_STRING String; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v13[2]; // [rsp+30h] [rbp-48h] BYREF
  __int16 v14; // [rsp+50h] [rbp-28h]

  *(_QWORD *)&String.Length = 2228224;
  v14 = 0;
  String.Buffer = (PWSTR)v13;
  memset(v13, 0, sizeof(v13));
  RtlInt64ToUnicodeString(a3, 0x10u, &String);
  ExAcquirePushLockExclusiveEx(&Smb2VolumeFeatureSupportCacheLock, 0);
  Entry = RxNameCacheFetchEntryEx(a2, &String, 0, 0);
  if ( Entry || (LOBYTE(v9) = 1, (Entry = RxNameCacheCreateEntryEx(a2, &String, 0, v9)) != 0) )
  {
    *(_DWORD *)(Entry + 48) = a5;
    **(_DWORD **)(Entry + 40) |= a4;
    InstanceConfigurationBlock = MRxSmbGetInstanceConfigurationBlock(*(_QWORD *)(a1 + 80));
    RxNameCacheActivateEntry(a2, (PNAME_CACHE)Entry, *(_DWORD *)(InstanceConfigurationBlock + 44), 0);
  }
  return ExReleasePushLockExclusiveEx(&Smb2VolumeFeatureSupportCacheLock, 0);
}

```

## disassembly

```asm
0x1400575a0  mov     [rsp+arg_18], rbx
0x1400575a5  push    rbp
0x1400575a6  push    rsi
0x1400575a7  push    rdi
0x1400575a8  sub     rsp, 60h
0x1400575ac  mov     rax, cs:__security_cookie
0x1400575b3  xor     rax, rsp
0x1400575b6  mov     [rsp+78h+var_20], rax
0x1400575bb  xor     eax, eax
0x1400575bd  mov     qword ptr [rsp+78h+String.Length], 220000h
0x1400575c6  mov     r10, r8
0x1400575c9  mov     [rsp+78h+var_28], ax
0x1400575ce  xorps   xmm0, xmm0
0x1400575d1  lea     rax, [rsp+78h+var_48]
0x1400575d6  mov     rdi, rdx
0x1400575d9  mov     [rsp+78h+String.Buffer], rax
0x1400575de  mov     rbp, rcx
0x1400575e1  lea     r8, [rsp+78h+String]; String
0x1400575e6  mov     edx, 10h; Base
0x1400575eb  mov     rcx, r10; Value
0x1400575ee  mov     esi, r9d
0x1400575f1  movups  [rsp+78h+var_48], xmm0
0x1400575f6  movups  [rsp+78h+var_38], xmm0
0x1400575fb  call    cs:__imp_RtlInt64ToUnicodeString
0x140057602  nop     dword ptr [rax+rax+00h]
0x140057607  xor     edx, edx
0x140057609  lea     rcx, Smb2VolumeFeatureSupportCacheLock
0x140057610  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140057617  nop     dword ptr [rax+rax+00h]
0x14005761c  xor     r9d, r9d
0x14005761f  lea     rdx, [rsp+78h+String]
0x140057624  xor     r8d, r8d
0x140057627  mov     rcx, rdi
0x14005762a  call    cs:__imp_RxNameCacheFetchEntryEx
0x140057631  nop     dword ptr [rax+rax+00h]
0x140057636  mov     rbx, rax
0x140057639  test    rax, rax
0x14005763c  jnz     short loc_140057693
0x14005763e  mov     r9b, 1
0x140057641  lea     rdx, [rsp+78h+String]
0x140057646  xor     r8d, r8d
0x140057649  mov     rcx, rdi
0x14005764c  call    cs:__imp_RxNameCacheCreateEntryEx
0x140057653  nop     dword ptr [rax+rax+00h]
0x140057658  mov     rbx, rax
0x14005765b  test    rax, rax
0x14005765e  jnz     short loc_140057693
0x140057660  xor     edx, edx
0x140057662  lea     rcx, Smb2VolumeFeatureSupportCacheLock
0x140057669  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140057670  nop     dword ptr [rax+rax+00h]
0x140057675  mov     rcx, [rsp+78h+var_20]
0x14005767a  xor     rcx, rsp; StackCookie
0x14005767d  call    __security_check_cookie
0x140057682  mov     rbx, [rsp+78h+arg_18]
0x14005768a  add     rsp, 60h
0x14005768e  pop     rdi
0x14005768f  pop     rsi
0x140057690  pop     rbp
0x140057691  retn
0x140057693  mov     eax, [rsp+78h+arg_20]
0x14005769a  mov     [rbx+30h], eax
0x14005769d  mov     rax, [rbx+28h]
0x1400576a1  or      [rax], esi
0x1400576a3  mov     rcx, [rbp+50h]
0x1400576a7  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x1400576ae  nop     dword ptr [rax+rax+00h]
0x1400576b3  xor     r9d, r9d; MRxContext
0x1400576b6  mov     rdx, rbx; NameCache
0x1400576b9  mov     rcx, rdi; NameCacheCtl
0x1400576bc  mov     r8d, [rax+2Ch]; LifeTime
0x1400576c0  call    cs:__imp_RxNameCacheActivateEntry
0x1400576c7  nop     dword ptr [rax+rax+00h]
0x1400576cc  jmp     short loc_140057660
```
