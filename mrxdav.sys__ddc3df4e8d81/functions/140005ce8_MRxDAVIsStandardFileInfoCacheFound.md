# MRxDAVIsStandardFileInfoCacheFound

- ea: `0x140005ce8`
- end: `0x140005e27`
- name: `MRxDAVIsStandardFileInfoCacheFound`
- size: `319`
- prototype: `char __fastcall(__int64, struct _LIST_ENTRY *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025a08`

## callees

- `0x1400028e4`
- `0x140005ce8`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140005d36`
- `ntoskrnl!ExAcquireFastMutex` at `0x140005d36`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005e0a`
- `ntoskrnl!ExReleaseFastMutex` at `0x140005e0a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140005d4e`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140005d4e`
- `rdbss!RxNameCacheActivateEntry` at `0x140005daa`
- `rdbss!RxNameCacheActivateEntry` at `0x140005daa`
- `rdbss!RxNameCacheExpireEntry` at `0x140005df7`
- `rdbss!RxNameCacheExpireEntry` at `0x140005df7`
- `rdbss!RxNameCacheCheckEntry` at `0x140005d6c`
- `rdbss!RxNameCacheCheckEntry` at `0x140005d6c`

## pseudocode

```c
char __fastcall MRxDAVIsStandardFileInfoCacheFound(__int64 a1, struct _LIST_ENTRY *a2, _DWORD *a3, __int64 a4)
{
  __int64 v4; // rax
  char v5; // bp
  __int64 v6; // rdi
  __int64 v9; // rax
  struct _NAME_CACHE_CONTROL_ *v10; // rsi
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v12; // rbx
  int Blink; // ecx
  struct _LIST_ENTRY *Flink; // rax

  v4 = *(_QWORD *)(a1 + 56);
  v5 = 0;
  v6 = a4;
  if ( !a4 )
    v6 = v4 + 360;
  if ( *(_BYTE *)(a1 + 32) )
    v9 = *(_QWORD *)(v4 + 120);
  else
    v9 = *(_QWORD *)(a1 + 648);
  v10 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v9 + 40) + 200LL);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v10, v6, 0, 0);
  v12 = Entry;
  if ( Entry )
  {
    if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) )
    {
      RxNameCacheExpireEntry(v10, v12);
    }
    else
    {
      Blink = (int)v12->Link.Blink;
      v5 = 1;
      ++v10->Spare[0];
      Flink = v12->Link.Flink;
      *a3 = Blink;
      *a2 = *Flink;
      a2[1].Flink = Flink[1].Flink;
      RxNameCacheActivateEntry(v10, v12, 0, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        WPP_SF_dZ(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          27,
          (unsigned int)WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids,
          v12->Link.Flink->Blink,
          v6);
    }
  }
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
  return v5;
}

```

## disassembly

```asm
0x140005ce8  push    rbx
0x140005cea  push    rbp
0x140005ceb  push    rsi
0x140005cec  push    rdi
0x140005ced  push    r14
0x140005cef  push    r15
0x140005cf1  sub     rsp, 38h
0x140005cf5  mov     rax, [rcx+38h]
0x140005cf9  xor     bpl, bpl
0x140005cfc  mov     rdi, r9
0x140005cff  mov     r15, r8
0x140005d02  mov     r14, rdx
0x140005d05  test    r9, r9
0x140005d08  jnz     short loc_140005D11
0x140005d0a  lea     rdi, [rax+168h]
0x140005d11  cmp     [rcx+20h], bpl
0x140005d15  jnz     short loc_140005D20
0x140005d17  mov     rax, [rcx+288h]
0x140005d1e  jmp     short loc_140005D24
0x140005d20  mov     rax, [rax+78h]
0x140005d24  mov     rsi, [rax+28h]
0x140005d28  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140005d2f  add     rsi, 0C8h
0x140005d36  call    cs:__imp_ExAcquireFastMutex
0x140005d3d  nop     dword ptr [rax+rax+00h]
0x140005d42  xor     r9d, r9d
0x140005d45  xor     r8d, r8d
0x140005d48  mov     rdx, rdi
0x140005d4b  mov     rcx, rsi
0x140005d4e  call    cs:__imp_RxNameCacheFetchEntryEx
0x140005d55  nop     dword ptr [rax+rax+00h]
0x140005d5a  mov     rbx, rax
0x140005d5d  test    rax, rax
0x140005d60  jz      loc_140005E03
0x140005d66  mov     edx, [rax+20h]; MRxContext
0x140005d69  mov     rcx, rax; NameCache
0x140005d6c  call    cs:__imp_RxNameCacheCheckEntry
0x140005d73  nop     dword ptr [rax+rax+00h]
0x140005d78  mov     rdx, rbx; NameCache
0x140005d7b  test    eax, eax
0x140005d7d  jnz     short loc_140005DF4
0x140005d7f  mov     ecx, [rbx+30h]
0x140005d82  lea     ebp, [rax+1]
0x140005d85  add     [rsi+74h], ebp
0x140005d88  xor     r9d, r9d; MRxContext
0x140005d8b  mov     rax, [rbx+28h]
0x140005d8f  xor     r8d, r8d; LifeTime
0x140005d92  mov     [r15], ecx
0x140005d95  mov     rcx, rsi; NameCacheCtl
0x140005d98  movups  xmm0, xmmword ptr [rax]
0x140005d9b  movups  xmmword ptr [r14], xmm0
0x140005d9f  movsd   xmm1, qword ptr [rax+10h]
0x140005da4  movsd   qword ptr [r14+10h], xmm1
0x140005daa  call    cs:__imp_RxNameCacheActivateEntry
0x140005db1  nop     dword ptr [rax+rax+00h]
0x140005db6  mov     rcx, cs:WPP_GLOBAL_Control
0x140005dbd  lea     rax, WPP_GLOBAL_Control
0x140005dc4  cmp     rcx, rax
0x140005dc7  jz      short loc_140005E03
0x140005dc9  test    dword ptr [rcx+2Ch], 2000h
0x140005dd0  jz      short loc_140005E03
0x140005dd2  mov     r9, [rbx+28h]
0x140005dd6  lea     edx, [rbp+1Ah]
0x140005dd9  mov     rcx, [rcx+18h]
0x140005ddd  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x140005de4  mov     [rsp+68h+var_48], rdi
0x140005de9  mov     r9d, [r9+8]
0x140005ded  call    WPP_SF_dZ
0x140005df2  jmp     short loc_140005E03
0x140005df4  mov     rcx, rsi; NameCacheCtl
0x140005df7  call    cs:__imp_RxNameCacheExpireEntry
0x140005dfe  nop     dword ptr [rax+rax+00h]
0x140005e03  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140005e0a  call    cs:__imp_ExReleaseFastMutex
0x140005e11  nop     dword ptr [rax+rax+00h]
0x140005e16  mov     al, bpl
0x140005e19  add     rsp, 38h
0x140005e1d  pop     r15
0x140005e1f  pop     r14
0x140005e21  pop     rdi
0x140005e22  pop     rsi
0x140005e23  pop     rbp
0x140005e24  pop     rbx
0x140005e25  retn
```
