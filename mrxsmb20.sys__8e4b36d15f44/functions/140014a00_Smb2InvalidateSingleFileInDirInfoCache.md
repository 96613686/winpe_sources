# Smb2InvalidateSingleFileInDirInfoCache

- ea: `0x140014a00`
- end: `0x140014da3`
- name: `Smb2InvalidateSingleFileInDirInfoCache`
- size: `931`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `7`
- tags: ``

## callers

- `0x140013dc0`
- `0x140013fa0`
- `0x1400144c0`
- `0x140014590`
- `0x140024b10`
- `0x140027880`
- `0x14002f210`
- `0x14002f280`
- `0x140034e78`
- `0x1400513a0`
- `0x140055bd0`

## callees

- `0x140004d30`
- `0x140004f20`
- `0x140014a00`
- `0x140015100`
- `0x1400352ec`
- `0x1400355c8`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockEx` at `0x140014cca`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003b498`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003b505`
- `ntoskrnl!ExReleasePushLockEx` at `0x140014cca`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003b498`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003b505`
- `ntoskrnl!RtlHashUnicodeString` at `0x140014afa`
- `ntoskrnl!RtlHashUnicodeString` at `0x140014afa`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14003b456`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14003b456`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014ba8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014c03`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014ba8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014c03`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014b6f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014cae`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003b4e2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014b6f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140014cae`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003b4e2`
- `rdbss!RxNameCacheCheckEntry` at `0x140014bb9`
- `rdbss!RxNameCacheCheckEntry` at `0x140014bb9`
- `rdbss!RxNameCacheExpireEntry` at `0x140014c7a`
- `rdbss!RxNameCacheExpireEntry` at `0x140014c7a`
- `rdbss!RxNameCacheActivateEntry` at `0x140014bee`
- `rdbss!RxNameCacheActivateEntry` at `0x140014bee`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140014b8b`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140014b8b`
- `rdbss!RxCrackPathName` at `0x140014a59`
- `rdbss!RxCrackPathName` at `0x140014b5a`
- `rdbss!RxCrackPathName` at `0x140014a59`
- `rdbss!RxCrackPathName` at `0x140014b5a`

## pseudocode

```c
__int64 __fastcall Smb2InvalidateSingleFileInDirInfoCache(_QWORD *a1, struct _NAME_CACHE_CONTROL_ *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  struct _LIST_ENTRY *v6; // r12
  __int64 *v7; // r13
  __int64 v8; // r15
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v12; // rbx
  struct _LIST_ENTRY *Flink; // rsi
  int v14; // r8d
  __int64 v15; // rcx
  int v16; // eax
  struct _LIST_ENTRY **p_Blink; // rcx
  UNICODE_STRING String1; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING String; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v21[18]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v22; // [rsp+100h] [rbp+0h] BYREF
  ULONG HashValue; // [rsp+150h] [rbp+50h] BYREF
  __int64 v24; // [rsp+160h] [rbp+60h] BYREF
  __int64 v25; // [rsp+168h] [rbp+68h] BYREF

  String = 0;
  String1 = 0;
  v22 = 0;
  memset(v21, 0, 0x88u);
  result = RxCrackPathName(a1[7] + 360LL, &String, &String1, &v22);
  if ( String1.Length )
  {
    v5 = a1[8];
    v6 = 0;
    v7 = 0;
    v8 = 0;
    if ( v5 )
    {
      v9 = *(_QWORD *)(v5 + 56);
      if ( v9 )
      {
        v7 = (__int64 *)(v9 + 8);
        v10 = *(_QWORD **)(*(_QWORD *)(a1[9] + 40LL) + 40LL);
        if ( (*(_DWORD *)(v10[53] + 184LL) & 0x800) != 0 || (v8 = -1, (*(_BYTE *)(v10[3] + 1314LL) & 4) == 0) )
          v8 = v10[12];
      }
    }
    HashValue = 0;
    RtlHashUnicodeString(&String, 1u, 0, &HashValue);
    memset(v21, 0, 0x88u);
    LODWORD(v21[0]) = 8973226;
    v21[13] = &v21[12];
    v21[12] = &v21[12];
    v21[9] = &v21[8];
    v21[8] = &v21[8];
    LODWORD(v21[14]) = HashValue;
    while ( 1 )
    {
      v20 = 0;
      RxCrackPathName(&String, 0, &v20, 0);
      ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
      while ( 1 )
      {
        Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &v20, 0, v21);
        v12 = Entry;
        if ( !Entry )
        {
          ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
          goto LABEL_15;
        }
        if ( RxNameCacheCheckEntry(Entry, 0) == RX_NC_SUCCESS )
          break;
        RxNameCacheExpireEntry(a2, v12);
      }
      Flink = v12->Link.Flink;
      if ( Flink )
      {
        Smb2ReferenceDirCacheObject(v12->Link.Flink);
        v6 = v12[1].Link.Flink;
      }
      RxNameCacheActivateEntry(a2, v12, 0, 0);
      ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
      if ( !Flink )
        break;
      while ( 1 )
      {
        v16 = (int)Flink[2].Flink;
        if ( !v16 )
          break;
        if ( v16 != 3 )
          goto LABEL_24;
        ExAcquirePushLockExclusiveEx(&Flink[6].Blink, 0);
        p_Blink = &Flink[6].Blink;
        if ( LODWORD(Flink[2].Flink) == 3 )
        {
          _InterlockedIncrement((volatile signed __int32 *)&Flink[3].Blink);
LABEL_50:
          ExReleasePushLockEx(p_Blink, 0);
          goto LABEL_24;
        }
        ExReleasePushLockEx(p_Blink, 0);
      }
      LODWORD(v24) = 0;
      if ( v7 && (struct _LIST_ENTRY *)v8 == v6 )
      {
        v25 = *v7;
        LOBYTE(HashValue) = 1;
      }
      else
      {
        LOBYTE(HashValue) = 0;
        v25 = 0;
      }
      if ( HIDWORD(v25) == LODWORD(Flink[2].Blink) )
      {
        if ( (int)v25 >= 0 )
          __int2c();
LABEL_30:
        if ( HIDWORD(v25) != LODWORD(Flink[2].Blink) || (int)v25 >= 0 )
          __int2c();
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_ZqZ(WPP_GLOBAL_Control->AttachedDevice, 22, v14, (unsigned int)&String1, (char)Flink, (__int64)&String);
        }
        ExAcquirePushLockExclusiveEx(&Flink[6].Blink, 0);
        InvalidateDirectoryCacheEntry(Flink, &v25, &String1);
        p_Blink = &Flink[6].Blink;
        goto LABEL_50;
      }
      v25 = 0;
      ExAcquirePushLockSharedEx(&Flink[6].Blink, 0);
      LODWORD(v24) = QueryFileInfoFromDirectoryCache((unsigned int *)Flink, &String1, 1, 4u, &v25, 0, &v24);
      ExReleasePushLockEx(&Flink[6].Blink, 0);
      v14 = v24;
      if ( (((_DWORD)v24 + 1073741789) & 0xFFFFFEFF) == 0 )
        v14 = 0;
      if ( (_BYTE)HashValue )
        *(_QWORD *)(*(_QWORD *)(a1[8] + 56LL) + 8LL) = v25;
      if ( v14 >= 0 )
        goto LABEL_30;
LABEL_24:
      Smb2DereferenceDirCacheObject(Flink);
    }
LABEL_15:
    result = v21[12];
    if ( (_QWORD *)v21[12] != &v21[12] )
    {
      if ( *(_QWORD **)(v21[12] + 8LL) != &v21[12] || (v15 = v21[13], *(_QWORD **)v21[13] != &v21[12]) )
        __fastfail(3u);
      *(_QWORD *)v21[13] = v21[12];
      *(_QWORD *)(result + 8) = v15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014a00  push    rbp
0x140014a02  push    rsi
0x140014a03  push    rdi
0x140014a04  push    r14
0x140014a06  lea     rbp, [rsp-28h]
0x140014a0b  sub     rsp, 128h
0x140014a12  xorps   xmm0, xmm0
0x140014a15  mov     rdi, rdx
0x140014a18  mov     r14, rcx
0x140014a1b  xorps   xmm1, xmm1
0x140014a1e  mov     esi, 88h
0x140014a23  lea     rcx, [rsp+140h+var_D0]; void *
0x140014a28  mov     r8d, esi; Size
0x140014a2b  xor     edx, edx; Val
0x140014a2d  movups  xmmword ptr [rsp+140h+String.Length], xmm0
0x140014a32  movups  xmmword ptr [rsp+140h+String1.Length], xmm1
0x140014a37  movups  [rbp+40h+var_40], xmm0
0x140014a3b  call    memset
0x140014a40  mov     rcx, [r14+38h]
0x140014a44  lea     r9, [rbp+40h+var_40]
0x140014a48  add     rcx, 168h
0x140014a4f  lea     r8, [rsp+140h+String1]
0x140014a54  lea     rdx, [rsp+140h+String]
0x140014a59  call    cs:__imp_RxCrackPathName
0x140014a60  nop     dword ptr [rax+rax+00h]
0x140014a65  cmp     [rsp+140h+String1.Length], 0
0x140014a6b  jz      loc_140014C5F
0x140014a71  mov     rax, [r14+40h]
0x140014a75  mov     [rsp+140h+arg_8], rbx
0x140014a7d  xor     ebx, ebx
0x140014a7f  mov     [rsp+140h+var_20], r12
0x140014a87  mov     r12d, ebx
0x140014a8a  mov     [rsp+140h+var_28], r13
0x140014a92  mov     r13d, ebx
0x140014a95  mov     [rsp+140h+var_30], r15
0x140014a9d  mov     r15d, ebx
0x140014aa0  test    rax, rax
0x140014aa3  jz      short loc_140014AE9
0x140014aa5  mov     rcx, [rax+38h]
0x140014aa9  test    rcx, rcx
0x140014aac  jz      short loc_140014AE9
0x140014aae  mov     rax, [r14+48h]
0x140014ab2  lea     r13, [rcx+8]
0x140014ab6  mov     rcx, [rax+28h]
0x140014aba  mov     rdx, [rcx+28h]
0x140014abe  mov     rax, [rdx+1A8h]
0x140014ac5  test    dword ptr [rax+0B8h], 800h
0x140014acf  jnz     short loc_140014AE5
0x140014ad1  mov     rax, [rdx+18h]
0x140014ad5  mov     r15, 0FFFFFFFFFFFFFFFFh
0x140014adc  test    byte ptr [rax+522h], 4
0x140014ae3  jnz     short loc_140014AE9
0x140014ae5  mov     r15, [rdx+60h]
0x140014ae9  lea     r9, [rbp+40h+HashValue]; HashValue
0x140014aed  mov     [rbp+40h+HashValue], ebx
0x140014af0  xor     r8d, r8d; HashAlgorithm
0x140014af3  lea     rcx, [rsp+140h+String]; String
0x140014af8  mov     dl, 1; CaseInSensitive
0x140014afa  call    cs:__imp_RtlHashUnicodeString
0x140014b01  nop     dword ptr [rax+rax+00h]
0x140014b06  mov     r8, rsi; Size
0x140014b09  lea     rcx, [rsp+140h+var_D0]; void *
0x140014b0e  xor     edx, edx; Val
0x140014b10  call    memset
0x140014b15  lea     rax, [rbp+40h+var_70]
0x140014b19  mov     [rsp+140h+var_D0], 88EBAAh
0x140014b21  mov     [rbp+40h+var_68], rax
0x140014b25  lea     rax, [rbp+40h+var_70]
0x140014b29  mov     [rbp+40h+var_70], rax
0x140014b2d  lea     rax, [rbp+40h+var_90]
0x140014b31  mov     [rbp+40h+var_88], rax
0x140014b35  lea     rax, [rbp+40h+var_90]
0x140014b39  mov     [rbp+40h+var_90], rax
0x140014b3d  mov     eax, [rbp+40h+HashValue]
0x140014b40  mov     [rbp+40h+var_60], eax
0x140014b43  xorps   xmm0, xmm0
0x140014b46  lea     r8, [rsp+140h+var_E0]
0x140014b4b  xor     r9d, r9d
0x140014b4e  lea     rcx, [rsp+140h+String]
0x140014b53  xor     edx, edx
0x140014b55  movups  [rsp+140h+var_E0], xmm0
0x140014b5a  call    cs:__imp_RxCrackPathName
0x140014b61  nop     dword ptr [rax+rax+00h]
0x140014b66  xor     edx, edx
0x140014b68  lea     rcx, Smb2DirCacheLock
0x140014b6f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140014b76  nop     dword ptr [rax+rax+00h]
0x140014b7b  lea     r9, [rsp+140h+var_D0]
0x140014b80  xor     r8d, r8d
0x140014b83  lea     rdx, [rsp+140h+var_E0]
0x140014b88  mov     rcx, rdi
0x140014b8b  call    cs:__imp_RxNameCacheFetchEntryEx
0x140014b92  nop     dword ptr [rax+rax+00h]
0x140014b97  xor     edx, edx; MRxContext
0x140014b99  mov     rbx, rax
0x140014b9c  test    rax, rax
0x140014b9f  jnz     short loc_140014BB6
0x140014ba1  lea     rcx, Smb2DirCacheLock
0x140014ba8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140014baf  nop     dword ptr [rax+rax+00h]
0x140014bb4  jmp     short loc_140014C14
0x140014bb6  mov     rcx, rbx; NameCache
0x140014bb9  call    cs:__imp_RxNameCacheCheckEntry
0x140014bc0  nop     dword ptr [rax+rax+00h]
0x140014bc5  test    eax, eax
0x140014bc7  jnz     loc_140014C74
0x140014bcd  mov     rsi, [rbx+28h]
0x140014bd1  test    rsi, rsi
0x140014bd4  jz      short loc_140014BE2
0x140014bd6  mov     rcx, rsi
0x140014bd9  call    Smb2ReferenceDirCacheObject
0x140014bde  mov     r12, [rbx+78h]
0x140014be2  xor     r9d, r9d; MRxContext
0x140014be5  xor     r8d, r8d; LifeTime
0x140014be8  mov     rdx, rbx; NameCache
0x140014beb  mov     rcx, rdi; NameCacheCtl
0x140014bee  call    cs:__imp_RxNameCacheActivateEntry
0x140014bf5  nop     dword ptr [rax+rax+00h]
0x140014bfa  xor     edx, edx
0x140014bfc  lea     rcx, Smb2DirCacheLock
0x140014c03  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140014c0a  nop     dword ptr [rax+rax+00h]
0x140014c0f  test    rsi, rsi
0x140014c12  jnz     short loc_140014C8B
0x140014c14  mov     rax, [rbp+40h+var_70]
0x140014c18  lea     rcx, [rbp+40h+var_70]
0x140014c1c  mov     r15, [rsp+140h+var_30]
0x140014c24  mov     r13, [rsp+140h+var_28]
0x140014c2c  mov     r12, [rsp+140h+var_20]
0x140014c34  mov     rbx, [rsp+140h+arg_8]
0x140014c3c  cmp     rax, rcx
0x140014c3f  jz      short loc_140014C5F
0x140014c41  lea     rcx, [rbp+40h+var_70]
0x140014c45  cmp     [rax+8], rcx
0x140014c49  jnz     short loc_140014C6D
0x140014c4b  mov     rcx, [rbp+40h+var_68]
0x140014c4f  lea     rdx, [rbp+40h+var_70]
0x140014c53  cmp     [rcx], rdx
0x140014c56  jnz     short loc_140014C6D
0x140014c58  mov     [rcx], rax
0x140014c5b  mov     [rax+8], rcx
0x140014c5f  add     rsp, 128h
0x140014c66  pop     r14
0x140014c68  pop     rdi
0x140014c69  pop     rsi
0x140014c6a  pop     rbp
0x140014c6b  retn
0x140014c6d  mov     ecx, 3
0x140014c72  int     29h; Win8: RtlFailFast(ecx)
0x140014c74  mov     rdx, rbx; NameCache
0x140014c77  mov     rcx, rdi; NameCacheCtl
0x140014c7a  call    cs:__imp_RxNameCacheExpireEntry
0x140014c81  nop     dword ptr [rax+rax+00h]
0x140014c86  jmp     loc_140014B7B
0x140014c8b  mov     eax, [rsi+20h]
0x140014c8e  test    eax, eax
0x140014c90  jz      loc_140014D6D
0x140014c96  cmp     eax, 3
0x140014c99  jz      short loc_140014CA8
0x140014c9b  mov     rcx, rsi; P
0x140014c9e  call    Smb2DereferenceDirCacheObject
0x140014ca3  jmp     loc_140014B43
0x140014ca8  xor     edx, edx
0x140014caa  lea     rcx, [rsi+68h]
0x140014cae  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140014cb5  nop     dword ptr [rax+rax+00h]
0x140014cba  xor     edx, edx
0x140014cbc  lea     rcx, [rsi+68h]
0x140014cc0  cmp     dword ptr [rsi+20h], 3
0x140014cc4  jz      loc_140014D64
0x140014cca  call    cs:__imp_ExReleasePushLockEx
0x140014cd1  nop     dword ptr [rax+rax+00h]
0x140014cd6  jmp     short loc_140014C8B
0x140014cd8  mov     rcx, [rbp+40h+arg_18]
0x140014cdc  mov     rax, rcx
0x140014cdf  shr     rax, 20h
0x140014ce3  cmp     eax, [rsi+28h]
0x140014ce6  jnz     loc_14003B44C
0x140014cec  test    ecx, ecx
0x140014cee  jns     loc_140014D95
0x140014cf4  mov     rcx, [rbp+40h+arg_18]
0x140014cf8  mov     rax, rcx
0x140014cfb  shr     rax, 20h
0x140014cff  cmp     eax, [rsi+28h]
0x140014d02  jnz     loc_140014D9C
0x140014d08  test    ecx, ecx
0x140014d0a  js      short loc_140014D0E
0x140014d0c  int     2Ch; Windows NT - assertion failure
0x140014d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d15  lea     rax, WPP_GLOBAL_Control
0x140014d1c  cmp     rcx, rax
0x140014d1f  jz      loc_14003B4DC
0x140014d25  test    dword ptr [rcx+2Ch], 100h
0x140014d2c  jz      loc_14003B4DC
0x140014d32  cmp     byte ptr [rcx+29h], 2
0x140014d36  jb      loc_14003B4DC
0x140014d3c  mov     rcx, [rcx+18h]
0x140014d40  lea     rax, [rsp+140h+String]
0x140014d45  mov     [rsp+140h+var_118], rax
0x140014d4a  lea     r9, [rsp+140h+String1]
0x140014d4f  mov     edx, 16h
0x140014d54  mov     [rsp+140h+var_120], rsi
0x140014d59  call    WPP_SF_ZqZ
0x140014d5e  nop
0x140014d5f  jmp     loc_14003B4DC
0x140014d64  lock inc dword ptr [rsi+38h]
0x140014d68  jmp     loc_14003B505
0x140014d6d  xor     ebx, ebx
0x140014d6f  mov     dword ptr [rbp+40h+arg_10], ebx
0x140014d72  test    r13, r13
0x140014d75  jz      loc_14003B440
0x140014d7b  cmp     r15, r12
0x140014d7e  jnz     loc_14003B440
0x140014d84  mov     rax, [r13+0]
0x140014d88  mov     [rbp+40h+arg_18], rax
0x140014d8c  mov     byte ptr [rbp+40h+HashValue], 1
0x140014d90  jmp     loc_140014CD8
0x140014d95  int     2Ch; Windows NT - assertion failure
0x140014d97  jmp     loc_140014CF4
0x140014d9c  int     2Ch; Windows NT - assertion failure
0x140014d9e  jmp     loc_140014D0E
0x14003b440  mov     byte ptr [rbp+40h+HashValue], bl
0x14003b443  mov     [rbp+40h+arg_18], rbx
0x14003b447  jmp     loc_140014CD8
0x14003b44c  xor     edx, edx
0x14003b44e  mov     [rbp+40h+arg_18], rbx
0x14003b452  lea     rcx, [rsi+68h]
0x14003b456  call    cs:__imp_ExAcquirePushLockSharedEx
0x14003b45d  nop     dword ptr [rax+rax+00h]
0x14003b462  lea     rax, [rbp+40h+arg_10]
0x14003b466  mov     r9d, 4
0x14003b46c  mov     [rsp+140h+var_110], rax; __int64
0x14003b471  lea     rdx, [rsp+140h+String1]; String1
0x14003b476  lea     rax, [rbp+40h+arg_18]
0x14003b47a  mov     [rsp+140h+var_118], rbx; __int64
0x14003b47f  mov     r8b, 1
0x14003b482  mov     [rsp+140h+var_120], rax; __int64
0x14003b487  mov     rcx, rsi; Context
0x14003b48a  call    QueryFileInfoFromDirectoryCache
0x14003b48f  xor     edx, edx
0x14003b491  mov     dword ptr [rbp+40h+arg_10], eax
0x14003b494  lea     rcx, [rsi+68h]
0x14003b498  call    cs:__imp_ExReleasePushLockEx
0x14003b49f  nop     dword ptr [rax+rax+00h]
0x14003b4a4  mov     r8d, dword ptr [rbp+40h+arg_10]
0x14003b4a8  lea     ecx, [r8+3FFFFFDDh]
0x14003b4af  test    ecx, 0FFFFFEFFh
0x14003b4b5  cmovz   r8d, ebx
0x14003b4b9  cmp     byte ptr [rbp+40h+HashValue], bl
0x14003b4bc  jz      short loc_14003B4CE
0x14003b4be  mov     rcx, [r14+40h]
0x14003b4c2  mov     rax, [rbp+40h+arg_18]
0x14003b4c6  mov     rdx, [rcx+38h]
0x14003b4ca  mov     [rdx+8], rax
0x14003b4ce  test    r8d, r8d
0x14003b4d1  js      loc_140014C9B
0x14003b4d7  jmp     loc_140014CF4
0x14003b4dc  xor     edx, edx
0x14003b4de  lea     rcx, [rsi+68h]
0x14003b4e2  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003b4e9  nop     dword ptr [rax+rax+00h]
0x14003b4ee  lea     r8, [rsp+140h+String1]
0x14003b4f3  mov     rcx, rsi
0x14003b4f6  lea     rdx, [rbp+40h+arg_18]
0x14003b4fa  call    InvalidateDirectoryCacheEntry
0x14003b4ff  xor     edx, edx
0x14003b501  lea     rcx, [rsi+68h]
0x14003b505  call    cs:__imp_ExReleasePushLockEx
0x14003b50c  nop     dword ptr [rax+rax+00h]
0x14003b511  nop
0x14003b512  jmp     loc_140014C9B
```
