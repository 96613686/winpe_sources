# MRxDAVInvalidateFileNotFoundCacheForRename

- ea: `0x140005a4c`
- end: `0x140005b36`
- name: `MRxDAVInvalidateFileNotFoundCacheForRename`
- size: `234`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022a80`

## callees

- `0x1400027ac`
- `0x140005a4c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140005ad2`
- `ntoskrnl!ExAcquireFastMutex` at `0x140005ad2`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005b1e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005b1e`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140005af0`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140005af0`
- `rdbss!RxNameCacheExpireEntry` at `0x140005b0b`
- `rdbss!RxNameCacheExpireEntry` at `0x140005b0b`

## pseudocode

```c
void __fastcall MRxDAVInvalidateFileNotFoundCacheForRename(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rbx
  struct _NAME_CACHE *Entry; // rax
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 456);
  v3 = *(_QWORD *)(a1 + 56);
  v7[0] = 0;
  v7[1] = v1 + 20;
  LOWORD(v7[0]) = *(_WORD *)(v1 + 16);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 3), 32, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids, v7);
  if ( *(_BYTE *)(a1 + 32) )
    v4 = *(_QWORD *)(v3 + 120);
  else
    v4 = *(_QWORD *)(a1 + 648);
  v5 = *(_QWORD *)(v4 + 40);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v5 + 384, v7, 0, 0);
  if ( Entry )
    RxNameCacheExpireEntry((PNAME_CACHE_CONTROL)(v5 + 384), Entry);
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
}

```

## disassembly

```asm
0x140005a4c  mov     r11, rsp
0x140005a4f  mov     [r11+8], rbx
0x140005a53  push    rdi
0x140005a54  sub     rsp, 30h
0x140005a58  mov     rdx, [rcx+1C8h]
0x140005a5f  mov     rbx, rcx
0x140005a62  mov     rdi, [rcx+38h]
0x140005a66  mov     qword ptr [r11-18h], 0
0x140005a6e  lea     rax, [rdx+14h]
0x140005a72  mov     [r11-10h], rax
0x140005a76  movzx   eax, word ptr [rdx+10h]
0x140005a7a  mov     word ptr [rsp+38h+var_18], ax
0x140005a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a86  lea     rax, WPP_GLOBAL_Control
0x140005a8d  cmp     rcx, rax
0x140005a90  jz      short loc_140005AB4
0x140005a92  test    dword ptr [rcx+2Ch], 4000h
0x140005a99  jz      short loc_140005AB4
0x140005a9b  mov     rcx, [rcx+18h]
0x140005a9f  lea     r9, [r11-18h]
0x140005aa3  mov     edx, 20h ; ' '
0x140005aa8  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x140005aaf  call    WPP_SF_Z
0x140005ab4  cmp     byte ptr [rbx+20h], 0
0x140005ab8  jnz     short loc_140005AC3
0x140005aba  mov     rax, [rbx+288h]
0x140005ac1  jmp     short loc_140005AC7
0x140005ac3  mov     rax, [rdi+78h]
0x140005ac7  mov     rbx, [rax+28h]
0x140005acb  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140005ad2  call    cs:__imp_ExAcquireFastMutex
0x140005ad9  nop     dword ptr [rax+rax+00h]
0x140005ade  xor     r9d, r9d
0x140005ae1  lea     rdx, [rsp+38h+var_18]
0x140005ae6  xor     r8d, r8d
0x140005ae9  lea     rcx, [rbx+180h]
0x140005af0  call    cs:__imp_RxNameCacheFetchEntryEx
0x140005af7  nop     dword ptr [rax+rax+00h]
0x140005afc  test    rax, rax
0x140005aff  jz      short loc_140005B17
0x140005b01  mov     rdx, rax; NameCache
0x140005b04  lea     rcx, [rbx+180h]; NameCacheCtl
0x140005b0b  call    cs:__imp_RxNameCacheExpireEntry
0x140005b12  nop     dword ptr [rax+rax+00h]
0x140005b17  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140005b1e  call    cs:__imp_ExReleaseFastMutex
0x140005b25  nop     dword ptr [rax+rax+00h]
0x140005b2a  mov     rbx, [rsp+38h+arg_0]
0x140005b2f  add     rsp, 30h
0x140005b33  pop     rdi
0x140005b34  retn
```
