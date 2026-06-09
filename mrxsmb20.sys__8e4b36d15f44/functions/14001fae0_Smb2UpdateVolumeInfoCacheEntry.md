# Smb2UpdateVolumeInfoCacheEntry

- ea: `0x14001fae0`
- end: `0x14001fbfc`
- name: `Smb2UpdateVolumeInfoCacheEntry`
- size: `284`
- prototype: `__int64 __fastcall(__int64, struct _NAME_CACHE_CONTROL_ *, ULONGLONG, __int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x1400229b0`

## callees

- `0x14001fae0`
- `0x140037120`

## import_xrefs

- `ntoskrnl!RtlInt64ToUnicodeString` at `0x14001fb27`
- `ntoskrnl!RtlInt64ToUnicodeString` at `0x14001fb27`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001fb95`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001fb95`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001fb3c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001fb3c`
- `rdbss!RxNameCacheActivateEntry` at `0x14001fbee`
- `rdbss!RxNameCacheActivateEntry` at `0x14001fbee`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14001fb78`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14001fb78`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001fb56`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001fb56`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001fbd5`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x14001fbd5`

## pseudocode

```c
__int64 __fastcall Smb2UpdateVolumeInfoCacheEntry(
        __int64 a1,
        struct _NAME_CACHE_CONTROL_ *a2,
        ULONGLONG a3,
        __int64 a4,
        int a5)
{
  __int64 Entry; // rbx
  __int64 v9; // r9
  __int64 InstanceConfigurationBlock; // rax
  __int64 v12; // rdx
  struct _UNICODE_STRING String; // [rsp+20h] [rbp-58h] BYREF
  char v14; // [rsp+30h] [rbp-48h] BYREF

  *(_QWORD *)&String.Length = 2228224;
  String.Buffer = (PWSTR)&v14;
  RtlInt64ToUnicodeString(a3, 0x10u, &String);
  ExAcquirePushLockExclusiveEx(&Smb2VolumeInfoCacheLock, 0);
  Entry = RxNameCacheFetchEntryEx(a2, &String, 0, 0);
  if ( Entry || (LOBYTE(v9) = 1, (Entry = RxNameCacheCreateEntryEx(a2, &String, 0, v9)) != 0) )
  {
    *(_DWORD *)(Entry + 48) = a5;
    if ( a5 >= 0 )
    {
      v12 = *(_QWORD *)(Entry + 40);
      *(_OWORD *)v12 = *(_OWORD *)a4;
      *(_OWORD *)(v12 + 16) = *(_OWORD *)(a4 + 16);
      *(_OWORD *)(v12 + 32) = *(_OWORD *)(a4 + 32);
      *(_OWORD *)(v12 + 48) = *(_OWORD *)(a4 + 48);
      *(_OWORD *)(v12 + 64) = *(_OWORD *)(a4 + 64);
      *(_OWORD *)(v12 + 80) = *(_OWORD *)(a4 + 80);
      *(_OWORD *)(v12 + 96) = *(_OWORD *)(a4 + 96);
      *(_OWORD *)(v12 + 112) = *(_OWORD *)(a4 + 112);
      *(_OWORD *)(v12 + 128) = *(_OWORD *)(a4 + 128);
      *(_OWORD *)(v12 + 144) = *(_OWORD *)(a4 + 144);
      *(_QWORD *)(v12 + 160) = *(_QWORD *)(a4 + 160);
    }
    InstanceConfigurationBlock = MRxSmbGetInstanceConfigurationBlock(*(_QWORD *)(a1 + 80));
    RxNameCacheActivateEntry(a2, (PNAME_CACHE)Entry, *(_DWORD *)(InstanceConfigurationBlock + 12), 0);
  }
  return ExReleasePushLockExclusiveEx(&Smb2VolumeInfoCacheLock, 0);
}

```

## disassembly

```asm
0x14001fae0  mov     [rsp+arg_18], rbx
0x14001fae5  push    rbp
0x14001fae6  push    rsi
0x14001fae7  push    rdi
0x14001fae8  sub     rsp, 60h
0x14001faec  mov     rax, cs:__security_cookie
0x14001faf3  xor     rax, rsp
0x14001faf6  mov     [rsp+78h+var_20], rax
0x14001fafb  mov     r10, r8
0x14001fafe  mov     qword ptr [rsp+78h+String.Length], 220000h
0x14001fb07  mov     rdi, rdx
0x14001fb0a  lea     rax, [rsp+78h+var_48]
0x14001fb0f  mov     rsi, rcx
0x14001fb12  mov     [rsp+78h+String.Buffer], rax
0x14001fb17  mov     rcx, r10; Value
0x14001fb1a  lea     r8, [rsp+78h+String]; String
0x14001fb1f  mov     edx, 10h; Base
0x14001fb24  mov     rbp, r9
0x14001fb27  call    cs:__imp_RtlInt64ToUnicodeString
0x14001fb2e  nop     dword ptr [rax+rax+00h]
0x14001fb33  xor     edx, edx
0x14001fb35  lea     rcx, Smb2VolumeInfoCacheLock
0x14001fb3c  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001fb43  nop     dword ptr [rax+rax+00h]
0x14001fb48  xor     r9d, r9d
0x14001fb4b  lea     rdx, [rsp+78h+String]
0x14001fb50  xor     r8d, r8d
0x14001fb53  mov     rcx, rdi
0x14001fb56  call    cs:__imp_RxNameCacheFetchEntryEx
0x14001fb5d  nop     dword ptr [rax+rax+00h]
0x14001fb62  mov     rbx, rax
0x14001fb65  test    rax, rax
0x14001fb68  jnz     short loc_14001FBBF
0x14001fb6a  mov     r9b, 1
0x14001fb6d  lea     rdx, [rsp+78h+String]
0x14001fb72  xor     r8d, r8d
0x14001fb75  mov     rcx, rdi
0x14001fb78  call    cs:__imp_RxNameCacheCreateEntryEx
0x14001fb7f  nop     dword ptr [rax+rax+00h]
0x14001fb84  mov     rbx, rax
0x14001fb87  test    rax, rax
0x14001fb8a  jnz     short loc_14001FBBF
0x14001fb8c  xor     edx, edx
0x14001fb8e  lea     rcx, Smb2VolumeInfoCacheLock
0x14001fb95  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001fb9c  nop     dword ptr [rax+rax+00h]
0x14001fba1  mov     rcx, [rsp+78h+var_20]
0x14001fba6  xor     rcx, rsp; StackCookie
0x14001fba9  call    __security_check_cookie
0x14001fbae  mov     rbx, [rsp+78h+arg_18]
0x14001fbb6  add     rsp, 60h
0x14001fbba  pop     rdi
0x14001fbbb  pop     rsi
0x14001fbbc  pop     rbp
0x14001fbbd  retn
0x14001fbbf  mov     eax, [rsp+78h+arg_20]
0x14001fbc6  mov     [rbx+30h], eax
0x14001fbc9  test    eax, eax
0x14001fbcb  jns     loc_14003C29A
0x14001fbd1  mov     rcx, [rsi+50h]
0x14001fbd5  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x14001fbdc  nop     dword ptr [rax+rax+00h]
0x14001fbe1  xor     r9d, r9d; MRxContext
0x14001fbe4  mov     rdx, rbx; NameCache
0x14001fbe7  mov     rcx, rdi; NameCacheCtl
0x14001fbea  mov     r8d, [rax+0Ch]; LifeTime
0x14001fbee  call    cs:__imp_RxNameCacheActivateEntry
0x14001fbf5  nop     dword ptr [rax+rax+00h]
0x14001fbfa  jmp     short loc_14001FB8C
0x14003c29a  movups  xmm0, xmmword ptr [rbp+0]
0x14003c29e  mov     rdx, [rbx+28h]
0x14003c2a2  movups  xmmword ptr [rdx], xmm0
0x14003c2a5  movups  xmm1, xmmword ptr [rbp+10h]
0x14003c2a9  movups  xmmword ptr [rdx+10h], xmm1
0x14003c2ad  movups  xmm0, xmmword ptr [rbp+20h]
0x14003c2b1  movups  xmmword ptr [rdx+20h], xmm0
0x14003c2b5  movups  xmm1, xmmword ptr [rbp+30h]
0x14003c2b9  movups  xmmword ptr [rdx+30h], xmm1
0x14003c2bd  movups  xmm0, xmmword ptr [rbp+40h]
0x14003c2c1  movups  xmmword ptr [rdx+40h], xmm0
0x14003c2c5  movups  xmm1, xmmword ptr [rbp+50h]
0x14003c2c9  movups  xmmword ptr [rdx+50h], xmm1
0x14003c2cd  movups  xmm0, xmmword ptr [rbp+60h]
0x14003c2d1  movups  xmmword ptr [rdx+60h], xmm0
0x14003c2d5  movups  xmm1, xmmword ptr [rbp+70h]
0x14003c2d9  movups  xmmword ptr [rdx+70h], xmm1
0x14003c2dd  movups  xmm0, xmmword ptr [rbp+80h]
0x14003c2e4  movups  xmmword ptr [rdx+80h], xmm0
0x14003c2eb  movups  xmm1, xmmword ptr [rbp+90h]
0x14003c2f2  movups  xmmword ptr [rdx+90h], xmm1
0x14003c2f9  mov     rax, [rbp+0A0h]
0x14003c300  mov     [rdx+0A0h], rax
0x14003c307  jmp     loc_14001FBD1
```
