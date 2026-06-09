# MRxSmbInvalidateBasicFileInfoCache

- ea: `0x14004b470`
- end: `0x14004b5e4`
- name: `MRxSmbInvalidateBasicFileInfoCache`
- size: `372`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14002b980`
- `0x14004ab38`
- `0x14004ad90`

## callees

- `0x14000e998`
- `0x14004b470`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004b51d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004b51d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004b4ad`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004b4ad`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b547`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b5d3`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b547`
- `rdbss!RxNameCacheExpireEntry` at `0x14004b5d3`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004b4c5`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004b5b8`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004b4c5`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004b5b8`

## pseudocode

```c
void __fastcall MRxSmbInvalidateBasicFileInfoCache(__int64 a1)
{
  bool v1; // zf
  __int64 v2; // rax
  __int16 *v3; // rbx
  __int64 v4; // rax
  struct _NAME_CACHE_CONTROL_ *v5; // rdi
  struct _NAME_CACHE *Entry; // rax
  __int16 v7; // r9
  unsigned __int16 i; // ax
  struct _NAME_CACHE *v9; // rax
  __int128 v10; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_BYTE *)(a1 + 32) == 0;
  v2 = *(_QWORD *)(a1 + 56);
  v10 = 0;
  v3 = (__int16 *)(v2 + 360);
  if ( v1 )
    v4 = *(_QWORD *)(a1 + 648);
  else
    v4 = *(_QWORD *)(v2 + 120);
  v5 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v4 + 40) + 288LL);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v5, v3, 0, 0);
  if ( Entry )
  {
    RxNameCacheExpireEntry(v5, Entry);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids, v3);
  }
  v7 = *v3;
  for ( i = 0; ; ++i )
  {
    if ( i >= (unsigned __int16)((unsigned __int16)*v3 >> 1) )
    {
      WORD1(v10) = *v3;
      LOWORD(v10) = v7;
      *((_QWORD *)&v10 + 1) = *((_QWORD *)v3 + 1);
      goto LABEL_9;
    }
    if ( *(_WORD *)(*((_QWORD *)v3 + 1) + 2LL * i) == 58 )
      break;
  }
  WORD1(v10) = 2 * i;
  LOWORD(v10) = 2 * i;
  *((_QWORD *)&v10 + 1) = *((_QWORD *)v3 + 1);
  v9 = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v5, &v10, 0, 0);
  if ( v9 )
    RxNameCacheExpireEntry(v5, v9);
LABEL_9:
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
}

```

## disassembly

```asm
0x14004b470  mov     [rsp+arg_0], rbx
0x14004b475  push    rdi
0x14004b476  sub     rsp, 30h
0x14004b47a  cmp     byte ptr [rcx+20h], 0
0x14004b47e  xorps   xmm0, xmm0
0x14004b481  mov     rax, [rcx+38h]
0x14004b485  movups  [rsp+38h+var_18], xmm0
0x14004b48a  lea     rbx, [rax+168h]
0x14004b491  jz      loc_14004B535
0x14004b497  mov     rax, [rax+78h]
0x14004b49b  mov     rdi, [rax+28h]
0x14004b49f  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004b4a6  add     rdi, 120h
0x14004b4ad  call    cs:__imp_ExAcquireFastMutex
0x14004b4b4  nop     dword ptr [rax+rax+00h]
0x14004b4b9  xor     r9d, r9d
0x14004b4bc  xor     r8d, r8d
0x14004b4bf  mov     rdx, rbx
0x14004b4c2  mov     rcx, rdi
0x14004b4c5  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004b4cc  nop     dword ptr [rax+rax+00h]
0x14004b4d1  test    rax, rax
0x14004b4d4  jnz     short loc_14004B541
0x14004b4d6  movzx   r9d, word ptr [rbx]
0x14004b4da  xor     eax, eax
0x14004b4dc  movzx   r8d, r9w
0x14004b4e0  shr     r8w, 1
0x14004b4e4  cmp     ax, r8w
0x14004b4e8  jnb     short loc_14004B501
0x14004b4ea  mov     rcx, [rbx+8]
0x14004b4ee  movzx   edx, ax
0x14004b4f1  cmp     word ptr [rcx+rdx*2], 3Ah ; ':'
0x14004b4f6  jz      loc_14004B594
0x14004b4fc  inc     ax
0x14004b4ff  jmp     short loc_14004B4E4
0x14004b501  mov     word ptr [rsp+38h+var_18+2], r9w
0x14004b507  mov     word ptr [rsp+38h+var_18], r9w
0x14004b50d  mov     rax, [rbx+8]
0x14004b511  mov     qword ptr [rsp+38h+var_18+8], rax
0x14004b516  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004b51d  call    cs:__imp_ExReleaseFastMutex
0x14004b524  nop     dword ptr [rax+rax+00h]
0x14004b529  mov     rbx, [rsp+38h+arg_0]
0x14004b52e  add     rsp, 30h
0x14004b532  pop     rdi
0x14004b533  retn
0x14004b535  mov     rax, [rcx+288h]
0x14004b53c  jmp     loc_14004B49B
0x14004b541  mov     rdx, rax; NameCache
0x14004b544  mov     rcx, rdi; NameCacheCtl
0x14004b547  call    cs:__imp_RxNameCacheExpireEntry
0x14004b54e  nop     dword ptr [rax+rax+00h]
0x14004b553  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004b55a  lea     rax, WPP_GLOBAL_Control
0x14004b561  cmp     rcx, rax
0x14004b564  jz      loc_14004B4D6
0x14004b56a  test    dword ptr [rcx+2Ch], 200h
0x14004b571  jz      loc_14004B4D6
0x14004b577  mov     rcx, [rcx+18h]
0x14004b57b  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x14004b582  mov     edx, 0Ch
0x14004b587  mov     r9, rbx
0x14004b58a  call    WPP_SF_Z
0x14004b58f  jmp     loc_14004B4D6
0x14004b594  add     ax, ax
0x14004b597  lea     rdx, [rsp+38h+var_18]
0x14004b59c  mov     word ptr [rsp+38h+var_18+2], ax
0x14004b5a1  xor     r9d, r9d
0x14004b5a4  mov     word ptr [rsp+38h+var_18], ax
0x14004b5a9  xor     r8d, r8d
0x14004b5ac  mov     rax, [rbx+8]
0x14004b5b0  mov     rcx, rdi
0x14004b5b3  mov     qword ptr [rsp+38h+var_18+8], rax
0x14004b5b8  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004b5bf  nop     dword ptr [rax+rax+00h]
0x14004b5c4  test    rax, rax
0x14004b5c7  jz      loc_14004B516
0x14004b5cd  mov     rdx, rax; NameCache
0x14004b5d0  mov     rcx, rdi; NameCacheCtl
0x14004b5d3  call    cs:__imp_RxNameCacheExpireEntry
0x14004b5da  nop     dword ptr [rax+rax+00h]
0x14004b5df  jmp     loc_14004B516
```
