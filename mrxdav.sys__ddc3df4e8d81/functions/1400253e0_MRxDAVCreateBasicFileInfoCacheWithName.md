# MRxDAVCreateBasicFileInfoCacheWithName

- ea: `0x1400253e0`
- end: `0x14002551a`
- name: `MRxDAVCreateBasicFileInfoCacheWithName`
- size: `314`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140025520`
- `0x1400255d4`

## callees

- `0x140005ee8`
- `0x140005f88`
- `0x1400253e0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400253fe`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400253fe`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025504`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025504`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025416`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025416`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140025433`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140025433`
- `rdbss!RxNameCacheActivateEntry` at `0x140025490`
- `rdbss!RxNameCacheActivateEntry` at `0x140025490`

## pseudocode

```c
void __fastcall MRxDAVCreateBasicFileInfoCacheWithName(__int64 a1, __int64 a2, __int64 a3)
{
  struct _NAME_CACHE_CONTROL_ *v4; // rsi
  __int64 Entry; // rax
  __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // r8d

  v4 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(a2 + 40) + 16LL);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = RxNameCacheFetchEntryEx(v4, a1, 0, 0);
  if ( Entry || (LOBYTE(v7) = 1, (Entry = RxNameCacheCreateEntryEx(v4, a1, 0, v7)) != 0) )
  {
    v8 = *(_QWORD *)(Entry + 40);
    *(_OWORD *)v8 = *(_OWORD *)a3;
    *(_OWORD *)(v8 + 16) = *(_OWORD *)(a3 + 16);
    *(_QWORD *)(v8 + 32) = *(_QWORD *)(a3 + 32);
    *(_DWORD *)(Entry + 48) = 0;
    if ( (*(_DWORD *)(v8 + 32) & 0xFFFFFF7F) != 0 )
      *(_DWORD *)(v8 + 32) &= ~0x80u;
    RxNameCacheActivateEntry(v4, (PNAME_CACHE)Entry, FileInformationCacheLifeTimeInSec, MRxContext);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
        WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 3), 12, v9, *(_DWORD *)(a3 + 32), a1);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        WPP_SF_ddZ(*((_QWORD *)WPP_GLOBAL_Control + 3), 13, v9, *(_DWORD *)a3, *(_DWORD *)(a3 + 8), a1);
      }
    }
  }
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
}

```

## disassembly

```asm
0x1400253e0  push    rbx
0x1400253e2  push    rbp
0x1400253e3  push    rsi
0x1400253e4  push    rdi
0x1400253e5  sub     rsp, 38h
0x1400253e9  mov     rsi, [rdx+28h]
0x1400253ed  mov     rdi, rcx
0x1400253f0  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x1400253f7  add     rsi, 10h
0x1400253fb  mov     rbx, r8
0x1400253fe  call    cs:__imp_ExAcquireFastMutex
0x140025405  nop     dword ptr [rax+rax+00h]
0x14002540a  xor     r9d, r9d
0x14002540d  xor     r8d, r8d
0x140025410  mov     rdx, rdi
0x140025413  mov     rcx, rsi
0x140025416  call    cs:__imp_RxNameCacheFetchEntryEx
0x14002541d  nop     dword ptr [rax+rax+00h]
0x140025422  test    rax, rax
0x140025425  jnz     short loc_140025448
0x140025427  mov     r9b, 1
0x14002542a  xor     r8d, r8d
0x14002542d  mov     rdx, rdi
0x140025430  mov     rcx, rsi
0x140025433  call    cs:__imp_RxNameCacheCreateEntryEx
0x14002543a  nop     dword ptr [rax+rax+00h]
0x14002543f  test    rax, rax
0x140025442  jz      loc_1400254FD
0x140025448  movups  xmm0, xmmword ptr [rbx]
0x14002544b  mov     rdx, [rax+28h]
0x14002544f  movups  xmmword ptr [rdx], xmm0
0x140025452  movups  xmm1, xmmword ptr [rbx+10h]
0x140025456  movups  xmmword ptr [rdx+10h], xmm1
0x14002545a  movsd   xmm0, qword ptr [rbx+20h]
0x14002545f  movsd   qword ptr [rdx+20h], xmm0
0x140025464  mov     dword ptr [rax+30h], 0
0x14002546b  mov     r8d, [rdx+20h]
0x14002546f  and     r8d, 0FFFFFF7Fh
0x140025476  jz      short loc_14002547C
0x140025478  mov     [rdx+20h], r8d
0x14002547c  mov     r9d, cs:MRxContext; MRxContext
0x140025483  mov     rdx, rax; NameCache
0x140025486  mov     r8d, cs:FileInformationCacheLifeTimeInSec; LifeTime
0x14002548d  mov     rcx, rsi; NameCacheCtl
0x140025490  call    cs:__imp_RxNameCacheActivateEntry
0x140025497  nop     dword ptr [rax+rax+00h]
0x14002549c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254a3  lea     rbp, WPP_GLOBAL_Control
0x1400254aa  cmp     rcx, rbp
0x1400254ad  jz      short loc_1400254FD
0x1400254af  bt      dword ptr [rcx+2Ch], 0Dh
0x1400254b4  jnb     short loc_1400254CD
0x1400254b6  mov     r9d, [rbx+20h]
0x1400254ba  mov     edx, 0Ch
0x1400254bf  mov     rcx, [rcx+18h]
0x1400254c3  mov     [rsp+58h+var_38], rdi
0x1400254c8  call    WPP_SF_DZ
0x1400254cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254d4  cmp     rcx, rbp
0x1400254d7  jz      short loc_1400254FD
0x1400254d9  bt      dword ptr [rcx+2Ch], 0Dh
0x1400254de  jnb     short loc_1400254FD
0x1400254e0  mov     eax, [rbx+8]
0x1400254e3  mov     edx, 0Dh
0x1400254e8  mov     r9d, [rbx]
0x1400254eb  mov     rcx, [rcx+18h]
0x1400254ef  mov     [rsp+58h+var_30], rdi
0x1400254f4  mov     dword ptr [rsp+58h+var_38], eax
0x1400254f8  call    WPP_SF_ddZ
0x1400254fd  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025504  call    cs:__imp_ExReleaseFastMutex
0x14002550b  nop     dword ptr [rax+rax+00h]
0x140025510  add     rsp, 38h
0x140025514  pop     rdi
0x140025515  pop     rsi
0x140025516  pop     rbp
0x140025517  pop     rbx
0x140025518  retn
```
