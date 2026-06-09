# MRxSmbInvalidateFullDirectoryCacheParent

- ea: `0x14004b1b0`
- end: `0x14004b466`
- name: `MRxSmbInvalidateFullDirectoryCacheParent`
- size: `694`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `5`
- tags: ``

## callers

- `0x14000f310`
- `0x140029440`
- `0x14002b980`
- `0x14002cec0`
- `0x14002d030`
- `0x14002f120`
- `0x140036d40`
- `0x14003a204`
- `0x14003b4c8`
- `0x14003c3f8`
- `0x14004442c`
- `0x140044568`
- `0x140044624`
- `0x140048b30`
- `0x14004ad90`
- `0x140052c00`

## callees

- `0x14000e01c`
- `0x14001621c`
- `0x1400438ac`
- `0x140043d74`
- `0x14004b1b0`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14004b308`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14004b308`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004b42e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004b42e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004b258`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004b258`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b40b`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b40b`
- `rdbss!RxNameCacheActivateEntry` at `0x14004b458`
- `rdbss!RxNameCacheActivateEntry` at `0x14004b458`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004b272`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004b272`
- `rdbss!RxNameCacheCheckEntry` at `0x14004b2a0`
- `rdbss!RxNameCacheCheckEntry` at `0x14004b2a0`

## pseudocode

```c
void __fastcall MRxSmbInvalidateFullDirectoryCacheParent(__int64 a1, char a2)
{
  __int64 v2; // rbx
  __int64 v4; // rbp
  unsigned int v5; // r8d
  __int64 v6; // r9
  __int64 v7; // r10
  __int64 v8; // rax
  __int64 v9; // rax
  struct _NAME_CACHE_CONTROL_ *v10; // rdi
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v12; // rbx
  struct _LIST_ENTRY *Flink; // rsi
  WCHAR v14; // dx
  int v15; // r8d
  int Flink_high; // r9d
  int v17; // r9d
  unsigned int Flink_low; // edx
  __int128 v19; // [rsp+40h] [rbp-38h] BYREF
  __int128 v20; // [rsp+50h] [rbp-28h] BYREF
  char v21; // [rsp+80h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v19 = 0;
  v4 = v2 + 360;
  v5 = *(unsigned __int16 *)(v2 + 360) >> 1;
  v6 = *(_QWORD *)(v2 + 368);
  v20 = 0;
  v7 = v6;
  if ( v5 )
  {
    v8 = 0;
    do
    {
      if ( *(_WORD *)(v6 + 2 * v8) == 92 )
        v7 = v6 + 2 * v8;
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < v5 );
  }
  LOWORD(v19) = 2 * ((v7 - v6) >> 1);
  WORD1(v19) = v19;
  *((_QWORD *)&v19 + 1) = *(_QWORD *)(v2 + 368);
  if ( (_WORD)v19 )
  {
    if ( *(_BYTE *)(a1 + 32) )
      v9 = *(_QWORD *)(v2 + 120);
    else
      v9 = *(_QWORD *)(a1 + 648);
    v10 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v9 + 40) + 1024LL);
    ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
    Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v10, &v19, 0, 0);
    v12 = Entry;
    if ( !Entry )
      goto LABEL_36;
    if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) == RX_NC_SUCCESS )
    {
      Flink = v12->Link.Flink;
      v21 = 1;
      WORD1(Flink->Flink) |= 1u;
      if ( !a2 && !(unsigned __int8)MRxSmbIsFileInPartialDirectoryCache(v12, v4, &v21, 0) )
      {
        MRxSmbCreateSuffix(v4, &v20);
        v14 = RtlUpcaseUnicodeChar(**((_WORD **)&v20 + 1));
        if ( (unsigned __int16)(v14 - 65) > 0x19u )
        {
          if ( (unsigned __int16)(v14 - 48) > 9u )
          {
            switch ( v14 )
            {
              case '$':
                v15 = 0x10000000;
                break;
              case '@':
                v15 = 0x20000000;
                break;
              case '_':
                v15 = 0x8000000;
                break;
              default:
                v15 = 0x4000000;
                if ( v14 != 126 )
                  v15 = 0x80000000;
                break;
            }
          }
          else
          {
            v15 = 0x40000000;
          }
        }
        else
        {
          v15 = 1 << (v14 - 65);
        }
        Flink_high = HIDWORD(Flink->Flink);
        if ( (Flink_high & v15) == 0 )
        {
          v17 = v15 | Flink_high;
          ++LOWORD(Flink->Flink);
          HIDWORD(Flink->Flink) = v17;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_ZZDD(WPP_GLOBAL_Control->AttachedDevice, 21, v15, v4, (__int64)&v19, v17, v15);
          }
        }
      }
      Flink_low = LOWORD(Flink->Flink);
      if ( Flink_low <= 8 )
      {
        RxNameCacheActivateEntry(v10, v12, 0, 0);
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids,
          HIDWORD(Flink->Flink),
          Flink_low);
      }
    }
    RxNameCacheExpireEntry(v10, v12);
LABEL_36:
    ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  }
}

```

## disassembly

```asm
0x14004b1b0  push    rbx
0x14004b1b2  push    rbp
0x14004b1b3  push    r14
0x14004b1b5  sub     rsp, 60h
0x14004b1b9  mov     rbx, [rcx+38h]
0x14004b1bd  xorps   xmm0, xmm0
0x14004b1c0  movups  [rsp+78h+var_38], xmm0
0x14004b1c5  movzx   r14d, dl
0x14004b1c9  xorps   xmm1, xmm1
0x14004b1cc  lea     rbp, [rbx+168h]
0x14004b1d3  movzx   r8d, word ptr [rbp+0]
0x14004b1d8  shr     r8d, 1
0x14004b1db  mov     r9, [rbp+8]
0x14004b1df  movups  [rsp+78h+var_28], xmm1
0x14004b1e4  mov     r10, r9
0x14004b1e7  jz      short loc_14004B206
0x14004b1e9  xor     eax, eax
0x14004b1eb  nop     dword ptr [rax+rax+00h]
0x14004b1f0  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x14004b1f6  lea     rdx, [r9+rax*2]
0x14004b1fa  jnz     short loc_14004B1FF
0x14004b1fc  mov     r10, rdx
0x14004b1ff  inc     eax
0x14004b201  cmp     eax, r8d
0x14004b204  jb      short loc_14004B1F0
0x14004b206  sub     r10, r9
0x14004b209  sar     r10, 1
0x14004b20c  add     r10w, r10w
0x14004b210  mov     word ptr [rsp+78h+var_38], r10w
0x14004b216  mov     word ptr [rsp+78h+var_38+2], r10w
0x14004b21c  mov     rax, [rbp+8]
0x14004b220  mov     qword ptr [rsp+78h+var_38+8], rax
0x14004b225  jz      loc_14004B442
0x14004b22b  cmp     byte ptr [rcx+20h], 0
0x14004b22f  mov     [rsp+78h+arg_10], rdi
0x14004b237  jnz     short loc_14004B242
0x14004b239  mov     rax, [rcx+288h]
0x14004b240  jmp     short loc_14004B246
0x14004b242  mov     rax, [rbx+78h]
0x14004b246  mov     rdi, [rax+28h]
0x14004b24a  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004b251  add     rdi, 400h
0x14004b258  call    cs:__imp_ExAcquireFastMutex
0x14004b25f  nop     dword ptr [rax+rax+00h]
0x14004b264  xor     r9d, r9d
0x14004b267  lea     rdx, [rsp+78h+var_38]
0x14004b26c  xor     r8d, r8d
0x14004b26f  mov     rcx, rdi
0x14004b272  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004b279  nop     dword ptr [rax+rax+00h]
0x14004b27e  mov     rbx, rax
0x14004b281  test    rax, rax
0x14004b284  jz      loc_14004B427
0x14004b28a  mov     edx, [rax+20h]; MRxContext
0x14004b28d  mov     rcx, rax; NameCache
0x14004b290  mov     [rsp+78h+arg_8], rsi
0x14004b298  mov     [rsp+78h+arg_18], r15
0x14004b2a0  call    cs:__imp_RxNameCacheCheckEntry
0x14004b2a7  nop     dword ptr [rax+rax+00h]
0x14004b2ac  test    eax, eax
0x14004b2ae  jnz     loc_14004B405
0x14004b2b4  mov     rsi, [rbx+28h]
0x14004b2b8  lea     r15, WPP_GLOBAL_Control
0x14004b2bf  mov     [rsp+78h+arg_0], 1
0x14004b2c7  or      word ptr [rsi+2], 1
0x14004b2cc  test    r14b, r14b
0x14004b2cf  jnz     loc_14004B3C9
0x14004b2d5  xor     r9d, r9d
0x14004b2d8  lea     r8, [rsp+78h+arg_0]
0x14004b2e0  mov     rdx, rbp
0x14004b2e3  mov     rcx, rbx
0x14004b2e6  call    MRxSmbIsFileInPartialDirectoryCache
0x14004b2eb  test    al, al
0x14004b2ed  jnz     loc_14004B3C9
0x14004b2f3  lea     rdx, [rsp+78h+var_28]
0x14004b2f8  mov     rcx, rbp
0x14004b2fb  call    MRxSmbCreateSuffix
0x14004b300  mov     rcx, qword ptr [rsp+78h+var_28+8]
0x14004b305  movzx   ecx, word ptr [rcx]; SourceCharacter
0x14004b308  call    cs:__imp_RtlUpcaseUnicodeChar
0x14004b30f  nop     dword ptr [rax+rax+00h]
0x14004b314  movzx   edx, ax
0x14004b317  lea     ecx, [rdx-41h]
0x14004b31a  cmp     cx, 19h
0x14004b31e  ja      short loc_14004B32E
0x14004b320  lea     ecx, [rdx-41h]
0x14004b323  mov     r8d, 1
0x14004b329  shl     r8d, cl
0x14004b32c  jmp     short loc_14004B37C
0x14004b32e  lea     eax, [rdx-30h]
0x14004b331  cmp     ax, 9
0x14004b335  ja      short loc_14004B33F
0x14004b337  mov     r8d, 40000000h
0x14004b33d  jmp     short loc_14004B37C
0x14004b33f  cmp     dx, 24h ; '$'
0x14004b343  jz      short loc_14004B376
0x14004b345  cmp     dx, 40h ; '@'
0x14004b349  jz      short loc_14004B36E
0x14004b34b  cmp     dx, 5Fh ; '_'
0x14004b34f  jz      short loc_14004B366
0x14004b351  cmp     dx, 7Eh ; '~'
0x14004b355  mov     eax, 80000000h
0x14004b35a  mov     r8d, 4000000h
0x14004b360  cmovnz  r8d, eax
0x14004b364  jmp     short loc_14004B37C
0x14004b366  mov     r8d, 8000000h
0x14004b36c  jmp     short loc_14004B37C
0x14004b36e  mov     r8d, 20000000h
0x14004b374  jmp     short loc_14004B37C
0x14004b376  mov     r8d, 10000000h
0x14004b37c  mov     r9d, [rsi+4]
0x14004b380  test    r8d, r9d
0x14004b383  jnz     short loc_14004B3C9
0x14004b385  or      r9d, r8d
0x14004b388  inc     word ptr [rsi]
0x14004b38b  mov     [rsi+4], r9d
0x14004b38f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004b396  cmp     rcx, r15
0x14004b399  jz      short loc_14004B3C9
0x14004b39b  test    dword ptr [rcx+2Ch], 200h
0x14004b3a2  jz      short loc_14004B3C9
0x14004b3a4  mov     rcx, [rcx+18h]
0x14004b3a8  lea     rax, [rsp+78h+var_38]
0x14004b3ad  mov     [rsp+78h+var_48], r8d
0x14004b3b2  mov     edx, 15h
0x14004b3b7  mov     [rsp+78h+var_50], r9d
0x14004b3bc  mov     r9, rbp
0x14004b3bf  mov     [rsp+78h+var_58], rax
0x14004b3c4  call    WPP_SF_ZZDD
0x14004b3c9  movzx   edx, word ptr [rsi]
0x14004b3cc  cmp     edx, 8
0x14004b3cf  jbe     short loc_14004B44C
0x14004b3d1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004b3d8  cmp     rcx, r15
0x14004b3db  jz      short loc_14004B405
0x14004b3dd  test    dword ptr [rcx+2Ch], 200h
0x14004b3e4  jz      short loc_14004B405
0x14004b3e6  mov     r9d, [rsi+4]
0x14004b3ea  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x14004b3f1  mov     rcx, [rcx+18h]
0x14004b3f5  mov     eax, edx
0x14004b3f7  mov     edx, 16h
0x14004b3fc  mov     dword ptr [rsp+78h+var_58], eax
0x14004b400  call    WPP_SF_Dd
0x14004b405  mov     rdx, rbx; NameCache
0x14004b408  mov     rcx, rdi; NameCacheCtl
0x14004b40b  call    cs:__imp_RxNameCacheExpireEntry
0x14004b412  nop     dword ptr [rax+rax+00h]
0x14004b417  mov     rsi, [rsp+78h+arg_8]
0x14004b41f  mov     r15, [rsp+78h+arg_18]
0x14004b427  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004b42e  call    cs:__imp_ExReleaseFastMutex
0x14004b435  nop     dword ptr [rax+rax+00h]
0x14004b43a  mov     rdi, [rsp+78h+arg_10]
0x14004b442  add     rsp, 60h
0x14004b446  pop     r14
0x14004b448  pop     rbp
0x14004b449  pop     rbx
0x14004b44a  retn
0x14004b44c  xor     r9d, r9d; MRxContext
0x14004b44f  xor     r8d, r8d; LifeTime
0x14004b452  mov     rdx, rbx; NameCache
0x14004b455  mov     rcx, rdi; NameCacheCtl
0x14004b458  call    cs:__imp_RxNameCacheActivateEntry
0x14004b45f  nop     dword ptr [rax+rax+00h]
0x14004b464  jmp     short loc_14004B417
```
