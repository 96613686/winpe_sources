# MRxSmbFinishWrite

- ea: `0x14004ad90`
- end: `0x14004b1a6`
- name: `MRxSmbFinishWrite`
- size: `1046`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e998`
- `0x14004ad90`
- `0x14004b1b0`
- `0x14004b470`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004aeb9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004af24`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004aeb9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004af24`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004ae42`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004aee9`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004ae42`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004aee9`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b0d4`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b124`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b178`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b0d4`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b124`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b178`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004ae5a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004af05`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004b109`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004ae5a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004af05`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004b109`

## pseudocode

```c
__int64 __fastcall MRxSmbFinishWrite(__int64 a1, __int64 a2)
{
  unsigned int v4; // r14d
  char v5; // al
  unsigned int v6; // ebx
  __int64 v7; // rdi
  bool v8; // zf
  __int64 v9; // rax
  __int16 *v10; // rbx
  __int64 v11; // rax
  struct _NAME_CACHE_CONTROL_ *v12; // rsi
  struct _NAME_CACHE *Entry; // rax
  __int16 v14; // r9
  unsigned __int16 i; // ax
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rdi
  struct _NAME_CACHE *v20; // rsi
  __int64 v21; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  char v25; // al
  unsigned int v26; // eax
  struct _NAME_CACHE *v27; // rax
  __int128 v28; // [rsp+20h] [rbp-48h] BYREF

  v4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids);
  v5 = *(_BYTE *)(a1 + 388);
  switch ( v5 )
  {
    case 47:
      if ( *(_BYTE *)a2 != 6 || *(_WORD *)(a2 + 13) )
        v4 = -1073741629;
      v23 = *(_QWORD *)(a1 + 88);
      if ( v23 )
        v24 = *(_QWORD *)(v23 + 104) + 105LL;
      else
        v24 = 1;
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 80) + 420LL) & 0x40000000) != 0 )
        v6 = *(unsigned __int16 *)(a2 + 5) | (*(unsigned __int16 *)(a2 + 9) << 16);
      else
        v6 = *(unsigned __int16 *)(a2 + 5);
      if ( *(_BYTE *)v24 == 1 )
      {
        v6 = *(_DWORD *)(a1 + 496);
      }
      else if ( !*(_DWORD *)(a1 + 48) && *(_DWORD *)(a1 + 496) > 2u && !v6 )
      {
        v4 = -1073741629;
      }
      v25 = *(_BYTE *)(a1 + 386);
      if ( (v25 & 0x20) != 0 )
        *(_BYTE *)(a1 + 386) = v25 & 0xDF;
      break;
    case 11:
      if ( *(_BYTE *)a2 != 1 || *(_WORD *)(a2 + 3) )
        v4 = -1073741629;
      v6 = *(unsigned __int16 *)(a2 + 1);
      break;
    case -63:
      v6 = *(_DWORD *)(a1 + 496);
      v4 = *(_BYTE *)a2 != 0 ? 0xC00000C3 : 0;
      break;
    default:
      v6 = 0;
      v4 = -1073741629;
      break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids, v6);
  *(_DWORD *)(a1 + 512) = v6;
  if ( !v4 )
  {
    v26 = *(_DWORD *)(a1 + 496);
    if ( v6 > v26 )
    {
      *(_DWORD *)(a1 + 512) = v26;
      v4 = -1073741629;
    }
  }
  v7 = *(_QWORD *)(a1 + 24);
  MRxSmbInvalidateBasicFileInfoCache(v7);
  v8 = *(_BYTE *)(v7 + 32) == 0;
  v9 = *(_QWORD *)(v7 + 56);
  v28 = 0;
  v10 = (__int16 *)(v9 + 360);
  if ( v8 )
    v11 = *(_QWORD *)(v7 + 648);
  else
    v11 = *(_QWORD *)(v9 + 120);
  v12 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v11 + 40) + 472LL);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v12, v10, 0, 0);
  if ( Entry )
    RxNameCacheExpireEntry(v12, Entry);
  v14 = *v10;
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned __int16)((unsigned __int16)*v10 >> 1) )
    {
      WORD1(v28) = *v10;
      LOWORD(v28) = v14;
      *((_QWORD *)&v28 + 1) = *((_QWORD *)v10 + 1);
      goto LABEL_17;
    }
    if ( *(_WORD *)(*((_QWORD *)v10 + 1) + 2LL * i) == 58 )
      break;
  }
  WORD1(v28) = 2 * i;
  LOWORD(v28) = 2 * i;
  *((_QWORD *)&v28 + 1) = *((_QWORD *)v10 + 1);
  v27 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v12, &v28, 0, 0);
  if ( v27 )
    RxNameCacheExpireEntry(v12, v27);
LABEL_17:
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  v16 = *(_QWORD *)(v7 + 56);
  v17 = v16 + 360;
  if ( *(_BYTE *)(v7 + 32) )
    v18 = *(_QWORD *)(v16 + 120);
  else
    v18 = *(_QWORD *)(v7 + 648);
  v19 = *(_QWORD *)(v18 + 40);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  v20 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v19 + 1024, v17, 0, 0);
  if ( v20 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids, v17);
    RxNameCacheExpireEntry((PNAME_CACHE_CONTROL)(v19 + 1024), v20);
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  LOBYTE(v21) = 1;
  MRxSmbInvalidateFullDirectoryCacheParent(*(_QWORD *)(a1 + 24), v21);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x14004ad90  push    rbx
0x14004ad92  push    rbp
0x14004ad93  push    rsi
0x14004ad94  push    rdi
0x14004ad95  push    r14
0x14004ad97  push    r15
0x14004ad99  sub     rsp, 38h
0x14004ad9d  mov     rdi, rdx
0x14004ada0  mov     rbp, rcx
0x14004ada3  xor     r14d, r14d
0x14004ada6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004adad  lea     r15, WPP_GLOBAL_Control
0x14004adb4  cmp     rcx, r15
0x14004adb7  jnz     loc_14004AFEB
0x14004adbd  movzx   eax, byte ptr [rbp+184h]
0x14004adc4  cmp     al, 2Fh ; '/'
0x14004adc6  jz      loc_14004AF65
0x14004adcc  cmp     al, 0Bh
0x14004adce  jz      loc_14004B09D
0x14004add4  cmp     al, 0C1h
0x14004add6  jz      loc_14004B083
0x14004addc  xor     ebx, ebx
0x14004adde  mov     r14d, 0C00000C3h
0x14004ade4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004adeb  cmp     rcx, r15
0x14004adee  jnz     loc_14004B012
0x14004adf4  mov     [rbp+200h], ebx
0x14004adfa  test    r14d, r14d
0x14004adfd  jz      loc_14004B03C
0x14004ae03  mov     rdi, [rbp+18h]
0x14004ae07  mov     rcx, rdi
0x14004ae0a  call    MRxSmbInvalidateBasicFileInfoCache
0x14004ae0f  cmp     byte ptr [rdi+20h], 0
0x14004ae13  xorps   xmm0, xmm0
0x14004ae16  mov     rax, [rdi+38h]
0x14004ae1a  movups  [rsp+68h+var_48], xmm0
0x14004ae1f  lea     rbx, [rax+168h]
0x14004ae26  jz      loc_14004B05B
0x14004ae2c  mov     rax, [rax+78h]
0x14004ae30  mov     rsi, [rax+28h]
0x14004ae34  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004ae3b  add     rsi, 1D8h
0x14004ae42  call    cs:__imp_ExAcquireFastMutex
0x14004ae49  nop     dword ptr [rax+rax+00h]
0x14004ae4e  xor     r9d, r9d
0x14004ae51  xor     r8d, r8d
0x14004ae54  mov     rdx, rbx
0x14004ae57  mov     rcx, rsi
0x14004ae5a  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004ae61  nop     dword ptr [rax+rax+00h]
0x14004ae66  test    rax, rax
0x14004ae69  jnz     loc_14004B0CE
0x14004ae6f  movzx   r9d, word ptr [rbx]
0x14004ae73  xor     eax, eax
0x14004ae75  movzx   r8d, r9w
0x14004ae79  shr     r8w, 1
0x14004ae7d  nop     dword ptr [rax]
0x14004ae80  cmp     ax, r8w
0x14004ae84  jnb     short loc_14004AE9D
0x14004ae86  mov     rcx, [rbx+8]
0x14004ae8a  movzx   edx, ax
0x14004ae8d  cmp     word ptr [rcx+rdx*2], 3Ah ; ':'
0x14004ae92  jz      loc_14004B0E5
0x14004ae98  inc     ax
0x14004ae9b  jmp     short loc_14004AE80
0x14004ae9d  mov     word ptr [rsp+68h+var_48+2], r9w
0x14004aea3  mov     word ptr [rsp+68h+var_48], r9w
0x14004aea9  mov     rax, [rbx+8]
0x14004aead  mov     qword ptr [rsp+68h+var_48+8], rax
0x14004aeb2  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004aeb9  call    cs:__imp_ExReleaseFastMutex
0x14004aec0  nop     dword ptr [rax+rax+00h]
0x14004aec5  cmp     byte ptr [rdi+20h], 0
0x14004aec9  mov     rax, [rdi+38h]
0x14004aecd  lea     rbx, [rax+168h]
0x14004aed4  jz      loc_14004B135
0x14004aeda  mov     rax, [rax+78h]
0x14004aede  mov     rdi, [rax+28h]
0x14004aee2  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004aee9  call    cs:__imp_ExAcquireFastMutex
0x14004aef0  nop     dword ptr [rax+rax+00h]
0x14004aef5  xor     r9d, r9d
0x14004aef8  lea     rcx, [rdi+400h]
0x14004aeff  xor     r8d, r8d
0x14004af02  mov     rdx, rbx
0x14004af05  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004af0c  nop     dword ptr [rax+rax+00h]
0x14004af11  mov     rsi, rax
0x14004af14  test    rax, rax
0x14004af17  jnz     loc_14004B141
0x14004af1d  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004af24  call    cs:__imp_ExReleaseFastMutex
0x14004af2b  nop     dword ptr [rax+rax+00h]
0x14004af30  mov     rcx, [rbp+18h]
0x14004af34  mov     dl, 1
0x14004af36  call    MRxSmbInvalidateFullDirectoryCacheParent
0x14004af3b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004af42  cmp     rcx, r15
0x14004af45  jz      short loc_14004AF54
0x14004af47  test    dword ptr [rcx+2Ch], 400h
0x14004af4e  jnz     loc_14004B189
0x14004af54  mov     eax, r14d
0x14004af57  add     rsp, 38h
0x14004af5b  pop     r15
0x14004af5d  pop     r14
0x14004af5f  pop     rdi
0x14004af60  pop     rsi
0x14004af61  pop     rbp
0x14004af62  pop     rbx
0x14004af63  retn
0x14004af65  cmp     byte ptr [rdi], 6
0x14004af68  jnz     loc_14004B0B8
0x14004af6e  cmp     [rdi+0Dh], r14w
0x14004af73  jnz     loc_14004B0B8
0x14004af79  mov     rcx, [rbp+58h]
0x14004af7d  mov     rax, [rbp+50h]
0x14004af81  test    rcx, rcx
0x14004af84  jz      loc_14004B072
0x14004af8a  mov     rcx, [rcx+68h]
0x14004af8e  add     rcx, 69h ; 'i'
0x14004af92  test    dword ptr [rax+1A4h], 40000000h
0x14004af9c  movzx   edx, word ptr [rdi+5]
0x14004afa0  jz      loc_14004B07C
0x14004afa6  movzx   ebx, word ptr [rdi+9]
0x14004afaa  shl     ebx, 10h
0x14004afad  or      ebx, edx
0x14004afaf  cmp     byte ptr [rcx], 1
0x14004afb2  jz      loc_14004B067
0x14004afb8  cmp     dword ptr [rbp+30h], 0
0x14004afbc  jnz     short loc_14004AFCF
0x14004afbe  cmp     dword ptr [rbp+1F0h], 2
0x14004afc5  jbe     short loc_14004AFCF
0x14004afc7  test    ebx, ebx
0x14004afc9  jz      loc_14004B0C3
0x14004afcf  movzx   eax, byte ptr [rbp+182h]
0x14004afd6  test    al, 20h
0x14004afd8  jz      loc_14004ADE4
0x14004afde  and     al, 0DFh
0x14004afe0  mov     [rbp+182h], al
0x14004afe6  jmp     loc_14004ADE4
0x14004afeb  test    dword ptr [rcx+2Ch], 400h
0x14004aff2  jz      loc_14004ADBD
0x14004aff8  mov     rcx, [rcx+18h]
0x14004affc  lea     r8, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids
0x14004b003  mov     edx, 20h ; ' '
0x14004b008  call    WPP_SF_
0x14004b00d  jmp     loc_14004ADBD
0x14004b012  test    dword ptr [rcx+2Ch], 400h
0x14004b019  jz      loc_14004ADF4
0x14004b01f  mov     rcx, [rcx+18h]
0x14004b023  lea     r8, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids
0x14004b02a  mov     edx, 21h ; '!'
0x14004b02f  mov     r9d, ebx
0x14004b032  call    WPP_SF_d
0x14004b037  jmp     loc_14004ADF4
0x14004b03c  mov     eax, [rbp+1F0h]
0x14004b042  cmp     ebx, eax
0x14004b044  jbe     loc_14004AE03
0x14004b04a  mov     [rbp+200h], eax
0x14004b050  mov     r14d, 0C00000C3h
0x14004b056  jmp     loc_14004AE03
0x14004b05b  mov     rax, [rdi+288h]
0x14004b062  jmp     loc_14004AE30
0x14004b067  mov     ebx, [rbp+1F0h]
0x14004b06d  jmp     loc_14004AFCF
0x14004b072  mov     ecx, 1
0x14004b077  jmp     loc_14004AF92
0x14004b07c  mov     ebx, edx
0x14004b07e  jmp     loc_14004AFAF
0x14004b083  movzx   eax, byte ptr [rdi]
0x14004b086  mov     ebx, [rbp+1F0h]
0x14004b08c  neg     al
0x14004b08e  sbb     r14d, r14d
0x14004b091  and     r14d, 0C00000C3h
0x14004b098  jmp     loc_14004ADE4
0x14004b09d  cmp     byte ptr [rdi], 1
0x14004b0a0  jnz     short loc_14004B0A9
0x14004b0a2  cmp     [rdi+3], r14w
0x14004b0a7  jz      short loc_14004B0AF
0x14004b0a9  mov     r14d, 0C00000C3h
0x14004b0af  movzx   ebx, word ptr [rdi+1]
0x14004b0b3  jmp     loc_14004ADE4
0x14004b0b8  mov     r14d, 0C00000C3h
0x14004b0be  jmp     loc_14004AF79
0x14004b0c3  mov     r14d, 0C00000C3h
0x14004b0c9  jmp     loc_14004AFCF
0x14004b0ce  mov     rdx, rax; NameCache
0x14004b0d1  mov     rcx, rsi; NameCacheCtl
0x14004b0d4  call    cs:__imp_RxNameCacheExpireEntry
0x14004b0db  nop     dword ptr [rax+rax+00h]
0x14004b0e0  jmp     loc_14004AE6F
0x14004b0e5  add     ax, ax
0x14004b0e8  lea     rdx, [rsp+68h+var_48]
0x14004b0ed  mov     word ptr [rsp+68h+var_48+2], ax
0x14004b0f2  xor     r9d, r9d
0x14004b0f5  mov     word ptr [rsp+68h+var_48], ax
0x14004b0fa  xor     r8d, r8d
0x14004b0fd  mov     rax, [rbx+8]
0x14004b101  mov     rcx, rsi
0x14004b104  mov     qword ptr [rsp+68h+var_48+8], rax
0x14004b109  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004b110  nop     dword ptr [rax+rax+00h]
0x14004b115  test    rax, rax
0x14004b118  jz      loc_14004AEB2
0x14004b11e  mov     rdx, rax; NameCache
0x14004b121  mov     rcx, rsi; NameCacheCtl
0x14004b124  call    cs:__imp_RxNameCacheExpireEntry
0x14004b12b  nop     dword ptr [rax+rax+00h]
0x14004b130  jmp     loc_14004AEB2
0x14004b135  mov     rax, [rdi+288h]
0x14004b13c  jmp     loc_14004AEDE
0x14004b141  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004b148  cmp     rcx, r15
0x14004b14b  jz      short loc_14004B16E
0x14004b14d  test    dword ptr [rcx+2Ch], 200h
0x14004b154  jz      short loc_14004B16E
0x14004b156  mov     rcx, [rcx+18h]
0x14004b15a  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x14004b161  mov     edx, 12h
0x14004b166  mov     r9, rbx
0x14004b169  call    WPP_SF_Z
0x14004b16e  mov     rdx, rsi; NameCache
0x14004b171  lea     rcx, [rdi+400h]; NameCacheCtl
0x14004b178  call    cs:__imp_RxNameCacheExpireEntry
0x14004b17f  nop     dword ptr [rax+rax+00h]
0x14004b184  jmp     loc_14004AF1D
0x14004b189  mov     rcx, [rcx+18h]
0x14004b18d  lea     r8, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids
0x14004b194  mov     edx, 22h ; '"'
0x14004b199  mov     r9d, r14d
0x14004b19c  call    WPP_SF_d
0x14004b1a1  jmp     loc_14004AF54
```
