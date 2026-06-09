# MRxDAVCreateStandardFileInfoCacheWithName

- ea: `0x14002564c`
- end: `0x140025750`
- name: `MRxDAVCreateStandardFileInfoCacheWithName`
- size: `260`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140025520`
- `0x1400255d4`

## callees

- `0x14000603c`
- `0x14002564c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14002566d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002566d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002573a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002573a`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025685`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025685`
- `rdbss!RxNameCacheCreateEntryEx` at `0x1400256a5`
- `rdbss!RxNameCacheCreateEntryEx` at `0x1400256a5`
- `rdbss!RxNameCacheActivateEntry` at `0x1400256e8`
- `rdbss!RxNameCacheActivateEntry` at `0x1400256e8`

## pseudocode

```c
void __fastcall MRxDAVCreateStandardFileInfoCacheWithName(__int64 a1, __int64 a2, __int64 a3)
{
  struct _NAME_CACHE_CONTROL_ *v4; // rbp
  __int64 Entry; // rbx
  __int64 v7; // r9
  __int64 v8; // rax
  ULONG v9; // r9d
  int v10; // edx
  int v11; // r8d

  v4 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(a2 + 40) + 200LL);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = RxNameCacheFetchEntryEx(v4, a1, 0, 0);
  if ( Entry || (LOBYTE(v7) = 1, (Entry = RxNameCacheCreateEntryEx(v4, a1, 0, v7)) != 0) )
  {
    v8 = *(_QWORD *)(Entry + 40);
    v9 = MRxContext;
    *(_OWORD *)v8 = *(_OWORD *)a3;
    *(_QWORD *)(v8 + 16) = *(_QWORD *)(a3 + 16);
    *(_DWORD *)(Entry + 48) = 0;
    RxNameCacheActivateEntry(v4, (PNAME_CACHE)Entry, FileInformationCacheLifeTimeInSec, v9);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      WPP_SF_dddZ(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v10,
        v11,
        *(_DWORD *)(*(_QWORD *)(Entry + 40) + 8LL),
        *(_DWORD *)a3,
        *(_DWORD *)(a3 + 8),
        a1);
  }
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
}

```

## disassembly

```asm
0x14002564c  push    rbx
0x14002564e  push    rbp
0x14002564f  push    rsi
0x140025650  push    rdi
0x140025651  sub     rsp, 48h
0x140025655  mov     rbp, [rdx+28h]
0x140025659  mov     rsi, rcx
0x14002565c  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025663  add     rbp, 0C8h
0x14002566a  mov     rdi, r8
0x14002566d  call    cs:__imp_ExAcquireFastMutex
0x140025674  nop     dword ptr [rax+rax+00h]
0x140025679  xor     r9d, r9d
0x14002567c  xor     r8d, r8d
0x14002567f  mov     rdx, rsi
0x140025682  mov     rcx, rbp
0x140025685  call    cs:__imp_RxNameCacheFetchEntryEx
0x14002568c  nop     dword ptr [rax+rax+00h]
0x140025691  mov     rbx, rax
0x140025694  test    rax, rax
0x140025697  jnz     short loc_1400256B9
0x140025699  mov     r9b, 1
0x14002569c  xor     r8d, r8d
0x14002569f  mov     rdx, rsi
0x1400256a2  mov     rcx, rbp
0x1400256a5  call    cs:__imp_RxNameCacheCreateEntryEx
0x1400256ac  nop     dword ptr [rax+rax+00h]
0x1400256b1  mov     rbx, rax
0x1400256b4  test    rax, rax
0x1400256b7  jz      short loc_140025733
0x1400256b9  movups  xmm0, xmmword ptr [rdi]
0x1400256bc  mov     rax, [rbx+28h]
0x1400256c0  mov     rdx, rbx; NameCache
0x1400256c3  mov     r9d, cs:MRxContext; MRxContext
0x1400256ca  mov     rcx, rbp; NameCacheCtl
0x1400256cd  movups  xmmword ptr [rax], xmm0
0x1400256d0  movsd   xmm1, qword ptr [rdi+10h]
0x1400256d5  movsd   qword ptr [rax+10h], xmm1
0x1400256da  mov     dword ptr [rbx+30h], 0
0x1400256e1  mov     r8d, cs:FileInformationCacheLifeTimeInSec; LifeTime
0x1400256e8  call    cs:__imp_RxNameCacheActivateEntry
0x1400256ef  nop     dword ptr [rax+rax+00h]
0x1400256f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400256fb  lea     rax, WPP_GLOBAL_Control
0x140025702  cmp     rcx, rax
0x140025705  jz      short loc_140025733
0x140025707  test    dword ptr [rcx+2Ch], 2000h
0x14002570e  jz      short loc_140025733
0x140025710  mov     eax, [rdi+8]
0x140025713  mov     r9, [rbx+28h]
0x140025717  mov     rcx, [rcx+18h]
0x14002571b  mov     [rsp+68h+var_38], rsi
0x140025720  mov     [rsp+68h+var_40], eax
0x140025724  mov     eax, [rdi]
0x140025726  mov     r9d, [r9+8]
0x14002572a  mov     [rsp+68h+var_48], eax
0x14002572e  call    WPP_SF_dddZ
0x140025733  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x14002573a  call    cs:__imp_ExReleaseFastMutex
0x140025741  nop     dword ptr [rax+rax+00h]
0x140025746  add     rsp, 48h
0x14002574a  pop     rdi
0x14002574b  pop     rsi
0x14002574c  pop     rbp
0x14002574d  pop     rbx
0x14002574e  retn
```
