# MRxSmbInvalidateFullDirectoryCacheParentForRename

- ea: `0x1400439e0`
- end: `0x140043c53`
- name: `MRxSmbInvalidateFullDirectoryCacheParentForRename`
- size: `627`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14002b980`
- `0x14003c3f8`

## callees

- `0x14000e01c`
- `0x14001621c`
- `0x1400438ac`
- `0x1400439e0`
- `0x140043d74`
- `0x14004eb10`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140043aff`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140043aff`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043c13`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043c13`
- `ntoskrnl!ExAcquireFastMutex` at `0x140043a6d`
- `ntoskrnl!ExAcquireFastMutex` at `0x140043a6d`
- `rdbss!RxNameCacheExpireEntry` at `0x140043c00`
- `rdbss!RxNameCacheExpireEntry` at `0x140043c00`
- `rdbss!RxNameCacheActivateEntry` at `0x140043c45`
- `rdbss!RxNameCacheActivateEntry` at `0x140043c45`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140043a86`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140043a86`
- `rdbss!RxNameCacheCheckEntry` at `0x140043aa4`
- `rdbss!RxNameCacheCheckEntry` at `0x140043aa4`

## pseudocode

```c
void __fastcall MRxSmbInvalidateFullDirectoryCacheParentForRename(__int64 a1, char a2)
{
  __int64 v2; // rdx
  __int64 v4; // rax
  struct _NAME_CACHE_CONTROL_ *v5; // rsi
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v7; // rbx
  struct _LIST_ENTRY *Flink; // rdi
  WCHAR v9; // dx
  int v10; // r8d
  int Flink_high; // r9d
  int v12; // r9d
  unsigned int Flink_low; // edx
  _QWORD v14[2]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v15; // [rsp+50h] [rbp-20h] BYREF
  __int128 v16; // [rsp+60h] [rbp-10h] BYREF
  char v17; // [rsp+A8h] [rbp+38h] BYREF

  v17 = a2;
  v2 = *(_QWORD *)(a1 + 456);
  v15 = 0;
  v14[0] = 0;
  v14[1] = v2 + 20;
  LOWORD(v14[0]) = *(_WORD *)(v2 + 16);
  v16 = 0;
  MRxSmbCreateParentDirPrefix(v14, &v15);
  if ( (_WORD)v15 )
  {
    if ( *(_BYTE *)(a1 + 32) )
      v4 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL);
    else
      v4 = *(_QWORD *)(a1 + 648);
    v5 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v4 + 40) + 1024LL);
    ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
    Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v5, &v15, 0, 0);
    v7 = Entry;
    if ( !Entry )
      goto LABEL_30;
    if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) == RX_NC_SUCCESS )
    {
      Flink = v7->Link.Flink;
      v17 = 1;
      WORD1(Flink->Flink) |= 1u;
      if ( !(unsigned __int8)MRxSmbIsFileInPartialDirectoryCache(v7, v14, &v17, 0) )
      {
        MRxSmbCreateSuffix(v14, &v16);
        v9 = RtlUpcaseUnicodeChar(**((_WORD **)&v16 + 1));
        if ( (unsigned __int16)(v9 - 65) > 0x19u )
        {
          if ( (unsigned __int16)(v9 - 48) > 9u )
          {
            switch ( v9 )
            {
              case '$':
                v10 = 0x10000000;
                break;
              case '@':
                v10 = 0x20000000;
                break;
              case '_':
                v10 = 0x8000000;
                break;
              default:
                v10 = 0x4000000;
                if ( v9 != 126 )
                  v10 = 0x80000000;
                break;
            }
          }
          else
          {
            v10 = 0x40000000;
          }
        }
        else
        {
          v10 = 1 << (v9 - 65);
        }
        Flink_high = HIDWORD(Flink->Flink);
        if ( (Flink_high & v10) == 0 )
        {
          v12 = v10 | Flink_high;
          ++LOWORD(Flink->Flink);
          HIDWORD(Flink->Flink) = v12;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
          {
            WPP_SF_ZZDD(WPP_GLOBAL_Control->AttachedDevice, 23, v10, (unsigned int)v14, (__int64)&v15, v12, v10);
          }
        }
      }
      Flink_low = LOWORD(Flink->Flink);
      if ( Flink_low <= 8 )
      {
        RxNameCacheActivateEntry(v5, v7, 0, 0);
        goto LABEL_30;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids,
          HIDWORD(Flink->Flink),
          Flink_low);
      }
    }
    RxNameCacheExpireEntry(v5, v7);
LABEL_30:
    ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  }
}

```

## disassembly

```asm
0x1400439e0  mov     [rsp-28h+arg_0], rbx
0x1400439e5  mov     [rsp-28h+arg_10], rsi
0x1400439ea  mov     [rsp-28h+arg_8], dl
0x1400439ee  push    rbp
0x1400439ef  push    rdi
0x1400439f0  push    r13
0x1400439f2  push    r14
0x1400439f4  push    r15
0x1400439f6  mov     rbp, rsp
0x1400439f9  sub     rsp, 70h
0x1400439fd  mov     rdx, [rcx+1C8h]
0x140043a04  xorps   xmm0, xmm0
0x140043a07  movups  [rbp+var_20], xmm0
0x140043a0b  xor     r14d, r14d
0x140043a0e  mov     rbx, rcx
0x140043a11  mov     [rbp+var_30], r14
0x140043a15  lea     rcx, [rbp+var_30]
0x140043a19  lea     rax, [rdx+14h]
0x140043a1d  xorps   xmm1, xmm1
0x140043a20  mov     [rbp+var_28], rax
0x140043a24  movzx   eax, word ptr [rdx+10h]
0x140043a28  lea     rdx, [rbp+var_20]
0x140043a2c  mov     word ptr [rbp+var_30], ax
0x140043a30  movups  [rbp+var_10], xmm1
0x140043a34  call    MRxSmbCreateParentDirPrefix
0x140043a39  cmp     word ptr [rbp+var_20], r14w
0x140043a3e  jz      loc_140043C1F
0x140043a44  cmp     [rbx+20h], r14b
0x140043a48  jnz     short loc_140043A53
0x140043a4a  mov     rax, [rbx+288h]
0x140043a51  jmp     short loc_140043A5B
0x140043a53  mov     rax, [rbx+38h]
0x140043a57  mov     rax, [rax+78h]
0x140043a5b  mov     rsi, [rax+28h]
0x140043a5f  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140043a66  add     rsi, 400h
0x140043a6d  call    cs:__imp_ExAcquireFastMutex
0x140043a74  nop     dword ptr [rax+rax+00h]
0x140043a79  xor     r9d, r9d
0x140043a7c  lea     rdx, [rbp+var_20]
0x140043a80  xor     r8d, r8d
0x140043a83  mov     rcx, rsi
0x140043a86  call    cs:__imp_RxNameCacheFetchEntryEx
0x140043a8d  nop     dword ptr [rax+rax+00h]
0x140043a92  mov     rbx, rax
0x140043a95  test    rax, rax
0x140043a98  jz      loc_140043C0C
0x140043a9e  mov     edx, [rax+20h]; MRxContext
0x140043aa1  mov     rcx, rax; NameCache
0x140043aa4  call    cs:__imp_RxNameCacheCheckEntry
0x140043aab  nop     dword ptr [rax+rax+00h]
0x140043ab0  test    eax, eax
0x140043ab2  jnz     loc_140043BFA
0x140043ab8  mov     rdi, [rbx+28h]
0x140043abc  lea     r15d, [rax+1]
0x140043ac0  xor     r9d, r9d
0x140043ac3  mov     [rbp+arg_8], r15b
0x140043ac7  lea     r8, [rbp+arg_8]
0x140043acb  mov     rcx, rbx
0x140043ace  lea     rdx, [rbp+var_30]
0x140043ad2  or      [rdi+2], r15w
0x140043ad7  call    MRxSmbIsFileInPartialDirectoryCache
0x140043adc  lea     r13, WPP_GLOBAL_Control
0x140043ae3  test    al, al
0x140043ae5  jnz     loc_140043BBE
0x140043aeb  lea     rdx, [rbp+var_10]
0x140043aef  lea     rcx, [rbp+var_30]
0x140043af3  call    MRxSmbCreateSuffix
0x140043af8  mov     rcx, qword ptr [rbp+var_10+8]
0x140043afc  movzx   ecx, word ptr [rcx]; SourceCharacter
0x140043aff  call    cs:__imp_RtlUpcaseUnicodeChar
0x140043b06  nop     dword ptr [rax+rax+00h]
0x140043b0b  movzx   edx, ax
0x140043b0e  lea     ecx, [rdx-41h]
0x140043b11  cmp     cx, 19h
0x140043b15  ja      short loc_140043B22
0x140043b17  lea     ecx, [rdx-41h]
0x140043b1a  mov     r8d, r15d
0x140043b1d  shl     r8d, cl
0x140043b20  jmp     short loc_140043B70
0x140043b22  lea     eax, [rdx-30h]
0x140043b25  cmp     ax, 9
0x140043b29  ja      short loc_140043B33
0x140043b2b  mov     r8d, 40000000h
0x140043b31  jmp     short loc_140043B70
0x140043b33  cmp     dx, 24h ; '$'
0x140043b37  jz      short loc_140043B6A
0x140043b39  cmp     dx, 40h ; '@'
0x140043b3d  jz      short loc_140043B62
0x140043b3f  cmp     dx, 5Fh ; '_'
0x140043b43  jz      short loc_140043B5A
0x140043b45  cmp     dx, 7Eh ; '~'
0x140043b49  mov     eax, 80000000h
0x140043b4e  mov     r8d, 4000000h
0x140043b54  cmovnz  r8d, eax
0x140043b58  jmp     short loc_140043B70
0x140043b5a  mov     r8d, 8000000h
0x140043b60  jmp     short loc_140043B70
0x140043b62  mov     r8d, 20000000h
0x140043b68  jmp     short loc_140043B70
0x140043b6a  mov     r8d, 10000000h
0x140043b70  mov     r9d, [rdi+4]
0x140043b74  test    r8d, r9d
0x140043b77  jnz     short loc_140043BBE
0x140043b79  or      r9d, r8d
0x140043b7c  add     [rdi], r15w
0x140043b80  mov     [rdi+4], r9d
0x140043b84  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043b8b  cmp     rcx, r13
0x140043b8e  jz      short loc_140043BBE
0x140043b90  test    dword ptr [rcx+2Ch], 200h
0x140043b97  jz      short loc_140043BBE
0x140043b99  mov     rcx, [rcx+18h]
0x140043b9d  lea     rax, [rbp+var_20]
0x140043ba1  mov     [rsp+70h+var_40], r8d
0x140043ba6  mov     edx, 17h
0x140043bab  mov     [rsp+70h+var_48], r9d
0x140043bb0  lea     r9, [rbp+var_30]
0x140043bb4  mov     [rsp+70h+var_50], rax
0x140043bb9  call    WPP_SF_ZZDD
0x140043bbe  movzx   edx, word ptr [rdi]
0x140043bc1  cmp     edx, 8
0x140043bc4  jbe     short loc_140043C39
0x140043bc6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043bcd  cmp     rcx, r13
0x140043bd0  jz      short loc_140043BFA
0x140043bd2  test    dword ptr [rcx+2Ch], 200h
0x140043bd9  jz      short loc_140043BFA
0x140043bdb  mov     r9d, [rdi+4]
0x140043bdf  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x140043be6  mov     rcx, [rcx+18h]
0x140043bea  mov     eax, edx
0x140043bec  mov     edx, 18h
0x140043bf1  mov     dword ptr [rsp+70h+var_50], eax
0x140043bf5  call    WPP_SF_Dd
0x140043bfa  mov     rdx, rbx; NameCache
0x140043bfd  mov     rcx, rsi; NameCacheCtl
0x140043c00  call    cs:__imp_RxNameCacheExpireEntry
0x140043c07  nop     dword ptr [rax+rax+00h]
0x140043c0c  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140043c13  call    cs:__imp_ExReleaseFastMutex
0x140043c1a  nop     dword ptr [rax+rax+00h]
0x140043c1f  lea     r11, [rsp+70h+var_s0]
0x140043c24  mov     rbx, [r11+30h]
0x140043c28  mov     rsi, [r11+40h]
0x140043c2c  mov     rsp, r11
0x140043c2f  pop     r15
0x140043c31  pop     r14
0x140043c33  pop     r13
0x140043c35  pop     rdi
0x140043c36  pop     rbp
0x140043c37  retn
0x140043c39  xor     r9d, r9d; MRxContext
0x140043c3c  xor     r8d, r8d; LifeTime
0x140043c3f  mov     rdx, rbx; NameCache
0x140043c42  mov     rcx, rsi; NameCacheCtl
0x140043c45  call    cs:__imp_RxNameCacheActivateEntry
0x140043c4c  nop     dword ptr [rax+rax+00h]
0x140043c51  jmp     short loc_140043C0C
```
