# Smb2InvalidateDirInfoCacheEx

- ea: `0x140017960`
- end: `0x140017bd2`
- name: `Smb2InvalidateDirInfoCacheEx`
- size: `626`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140013210`
- `0x140013fa0`
- `0x14002f280`
- `0x140034e78`

## callees

- `0x140017960`
- `0x140029c14`
- `0x1400356ac`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140017a76`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140017a76`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400179be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400179be`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x140017a9e`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x140017a9e`
- `rdbss!RxNameCacheExpireEntry` at `0x140017a61`
- `rdbss!RxNameCacheExpireEntry` at `0x140017b2f`
- `rdbss!RxNameCacheExpireEntry` at `0x140017a61`
- `rdbss!RxNameCacheExpireEntry` at `0x140017b2f`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140017a27`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140017b14`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140017b49`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140017a27`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140017b14`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140017b49`
- `rdbss!RxCrackPathName` at `0x1400179a9`
- `rdbss!RxCrackPathName` at `0x1400179a9`

## pseudocode

```c
__int64 __fastcall Smb2InvalidateDirInfoCacheEx(
        __int64 a1,
        __int64 a2,
        struct _NAME_CACHE_CONTROL_ *a3,
        char a4,
        char a5)
{
  __int64 v7; // rax
  __int64 v9; // r8
  _QWORD *v10; // rdx
  __int64 v11; // rax
  struct _NAME_CACHE *Entry; // rdi
  int v13; // r8d
  struct _NAME_CACHE *i; // rax
  __int128 v16; // [rsp+30h] [rbp-18h] BYREF
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  v17 = 0;
  v7 = a2;
  v16 = 0;
  if ( !a2 )
    v7 = *(_QWORD *)(a1 + 56) + 360LL;
  RxCrackPathName(v7, 0, &v16, 0);
  ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
  if ( a4 )
  {
    LOBYTE(v9) = 1;
    RxNameCacheExpireEntriesWithPrefixEx(a3, &v16, v9);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_fb97726eb6f036c688a7379a523a601c_Traceguids,
        a1,
        (__int64)&v16);
    }
  }
  else if ( a5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        (unsigned int)WPP_fb97726eb6f036c688a7379a523a601c_Traceguids,
        a1,
        (__int64)&v16);
    }
    for ( i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a3, &v16, 0, 0);
          i;
          i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a3, &v16, 0, 0) )
    {
      RxNameCacheExpireEntry(a3, i);
    }
  }
  else
  {
    v10 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
    if ( (*(_DWORD *)(v10[53] + 184LL) & 0x800) == 0 && (*(_BYTE *)(v10[3] + 1314LL) & 4) != 0 )
      v11 = -1;
    else
      v11 = v10[12];
    v17 = v11;
    Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a3, &v16, &v17, 0);
    if ( Entry )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_iqZ(WPP_GLOBAL_Control->AttachedDevice, 17, v13, v17, a1, (__int64)&v16);
      }
      RxNameCacheExpireEntry(a3, Entry);
    }
  }
  return ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
}

```

## disassembly

```asm
0x140017960  mov     [rsp+arg_0], rbx
0x140017965  mov     [rsp+arg_10], rsi
0x14001796a  push    rdi
0x14001796b  sub     rsp, 40h
0x14001796f  mov     [rsp+48h+arg_8], 0
0x140017978  xorps   xmm0, xmm0
0x14001797b  movzx   edi, r9b
0x14001797f  mov     rsi, r8
0x140017982  mov     rax, rdx
0x140017985  mov     rbx, rcx
0x140017988  movups  [rsp+48h+var_18], xmm0
0x14001798d  test    rdx, rdx
0x140017990  jnz     short loc_14001799C
0x140017992  mov     rax, [rcx+38h]
0x140017996  add     rax, 168h
0x14001799c  xor     r9d, r9d
0x14001799f  lea     r8, [rsp+48h+var_18]
0x1400179a4  xor     edx, edx
0x1400179a6  mov     rcx, rax
0x1400179a9  call    cs:__imp_RxCrackPathName
0x1400179b0  nop     dword ptr [rax+rax+00h]
0x1400179b5  xor     edx, edx
0x1400179b7  lea     rcx, Smb2DirCacheLock
0x1400179be  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400179c5  nop     dword ptr [rax+rax+00h]
0x1400179ca  test    dil, dil
0x1400179cd  jnz     loc_140017A93
0x1400179d3  cmp     [rsp+48h+arg_20], dil
0x1400179d8  jnz     loc_140017AF3
0x1400179de  mov     rax, [rbx+48h]
0x1400179e2  mov     rcx, [rax+28h]
0x1400179e6  mov     rdx, [rcx+28h]
0x1400179ea  mov     rax, [rdx+1A8h]
0x1400179f1  test    dword ptr [rax+0B8h], 800h
0x1400179fb  jnz     short loc_140017A0E
0x1400179fd  mov     rax, [rdx+18h]
0x140017a01  test    byte ptr [rax+522h], 4
0x140017a08  jnz     loc_140017B5F
0x140017a0e  mov     rax, [rdx+60h]
0x140017a12  xor     r9d, r9d
0x140017a15  mov     [rsp+48h+arg_8], rax
0x140017a1a  lea     r8, [rsp+48h+arg_8]
0x140017a1f  mov     rcx, rsi
0x140017a22  lea     rdx, [rsp+48h+var_18]
0x140017a27  call    cs:__imp_RxNameCacheFetchEntryEx
0x140017a2e  nop     dword ptr [rax+rax+00h]
0x140017a33  mov     rdi, rax
0x140017a36  test    rax, rax
0x140017a39  jz      short loc_140017A6D
0x140017a3b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017a42  lea     rax, WPP_GLOBAL_Control
0x140017a49  cmp     rcx, rax
0x140017a4c  jz      short loc_140017A5B
0x140017a4e  test    dword ptr [rcx+2Ch], 100h
0x140017a55  jnz     loc_140017BA1
0x140017a5b  mov     rdx, rdi; NameCache
0x140017a5e  mov     rcx, rsi; NameCacheCtl
0x140017a61  call    cs:__imp_RxNameCacheExpireEntry
0x140017a68  nop     dword ptr [rax+rax+00h]
0x140017a6d  xor     edx, edx
0x140017a6f  lea     rcx, Smb2DirCacheLock
0x140017a76  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140017a7d  nop     dword ptr [rax+rax+00h]
0x140017a82  mov     rbx, [rsp+48h+arg_0]
0x140017a87  mov     rsi, [rsp+48h+arg_10]
0x140017a8c  add     rsp, 40h
0x140017a90  pop     rdi
0x140017a91  retn
0x140017a93  mov     r8b, 1
0x140017a96  lea     rdx, [rsp+48h+var_18]
0x140017a9b  mov     rcx, rsi
0x140017a9e  call    cs:__imp_RxNameCacheExpireEntriesWithPrefixEx
0x140017aa5  nop     dword ptr [rax+rax+00h]
0x140017aaa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017ab1  lea     rax, WPP_GLOBAL_Control
0x140017ab8  cmp     rcx, rax
0x140017abb  jz      short loc_140017A6D
0x140017abd  test    dword ptr [rcx+2Ch], 100h
0x140017ac4  jz      short loc_140017A6D
0x140017ac6  cmp     byte ptr [rcx+29h], 2
0x140017aca  jb      short loc_140017A6D
0x140017acc  mov     rcx, [rcx+18h]
0x140017ad0  lea     rax, [rsp+48h+var_18]
0x140017ad5  mov     edx, 0Fh
0x140017ada  mov     [rsp+48h+var_28], rax
0x140017adf  mov     r9, rbx
0x140017ae2  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x140017ae9  call    WPP_SF_qZ
0x140017aee  jmp     loc_140017A6D
0x140017af3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140017afa  lea     rax, WPP_GLOBAL_Control
0x140017b01  cmp     rcx, rax
0x140017b04  jnz     short loc_140017B6B
0x140017b06  xor     r9d, r9d
0x140017b09  lea     rdx, [rsp+48h+var_18]
0x140017b0e  xor     r8d, r8d
0x140017b11  mov     rcx, rsi
0x140017b14  call    cs:__imp_RxNameCacheFetchEntryEx
0x140017b1b  nop     dword ptr [rax+rax+00h]
0x140017b20  test    rax, rax
0x140017b23  jz      loc_140017A6D
0x140017b29  mov     rdx, rax; NameCache
0x140017b2c  mov     rcx, rsi; NameCacheCtl
0x140017b2f  call    cs:__imp_RxNameCacheExpireEntry
0x140017b36  nop     dword ptr [rax+rax+00h]
0x140017b3b  xor     r9d, r9d
0x140017b3e  lea     rdx, [rsp+48h+var_18]
0x140017b43  xor     r8d, r8d
0x140017b46  mov     rcx, rsi
0x140017b49  call    cs:__imp_RxNameCacheFetchEntryEx
0x140017b50  nop     dword ptr [rax+rax+00h]
0x140017b55  test    rax, rax
0x140017b58  jnz     short loc_140017B29
0x140017b5a  jmp     loc_140017A6D
0x140017b5f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140017b66  jmp     loc_140017A12
0x140017b6b  test    dword ptr [rcx+2Ch], 100h
0x140017b72  jz      short loc_140017B06
0x140017b74  cmp     byte ptr [rcx+29h], 2
0x140017b78  jb      short loc_140017B06
0x140017b7a  mov     rcx, [rcx+18h]
0x140017b7e  lea     rax, [rsp+48h+var_18]
0x140017b83  mov     edx, 10h
0x140017b88  mov     [rsp+48h+var_28], rax
0x140017b8d  mov     r9, rbx
0x140017b90  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x140017b97  call    WPP_SF_qZ
0x140017b9c  jmp     loc_140017B06
0x140017ba1  cmp     byte ptr [rcx+29h], 2
0x140017ba5  jb      loc_140017A5B
0x140017bab  mov     r9, [rsp+48h+arg_8]
0x140017bb0  lea     rax, [rsp+48h+var_18]
0x140017bb5  mov     rcx, [rcx+18h]
0x140017bb9  mov     edx, 11h
0x140017bbe  mov     [rsp+48h+var_20], rax
0x140017bc3  mov     [rsp+48h+var_28], rbx
0x140017bc8  call    WPP_SF_iqZ
0x140017bcd  jmp     loc_140017A5B
```
