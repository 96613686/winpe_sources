# MRxSmbCreateInternalFileInfoCache

- ea: `0x1400437a8`
- end: `0x1400438a4`
- name: `MRxSmbCreateInternalFileInfoCache`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140048b30`

## callees

- `0x1400437a8`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004388c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004388c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400437f7`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400437f7`
- `rdbss!RxNameCacheActivateEntry` at `0x140043879`
- `rdbss!RxNameCacheActivateEntry` at `0x140043879`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14004382f`
- `rdbss!RxNameCacheCreateEntryEx` at `0x14004382f`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004380f`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004380f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004385d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14004385d`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14004384d`

## pseudocode

```c
void __fastcall MRxSmbCreateInternalFileInfoCache(__int64 a1, _QWORD *a2, __int64 a3, int a4)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  struct _NAME_CACHE_CONTROL_ *v9; // rsi
  __int64 Entry; // rdi
  __int64 v11; // r9
  ULONG v12; // ebx
  __int64 ConfigurationBlock; // rax

  if ( !*(_BYTE *)(a3 + 505) )
  {
    v6 = *(_QWORD *)(a1 + 56);
    v7 = v6 + 360;
    if ( *(_BYTE *)(a1 + 32) )
      v8 = *(_QWORD *)(v6 + 120);
    else
      v8 = *(_QWORD *)(a1 + 648);
    v9 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v8 + 40) + 656LL);
    ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
    Entry = RxNameCacheFetchEntryEx(v9, v7, 0, 0);
    if ( Entry || (LOBYTE(v11) = 1, (Entry = RxNameCacheCreateEntryEx(v9, v7, 0, v11)) != 0) )
    {
      **(_QWORD **)(Entry + 40) = *a2;
      *(_DWORD *)(Entry + 48) = a4;
      v12 = *(_DWORD *)(MRxSmbLegacyPerfCtrs + 8LL);
      ConfigurationBlock = MRxSmbGetConfigurationBlock();
      RxNameCacheActivateEntry(v9, (PNAME_CACHE)Entry, *(_DWORD *)(ConfigurationBlock + 144), v12);
    }
    ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  }
}

```

## disassembly

```asm
0x1400437a8  push    rbx
0x1400437aa  push    rbp
0x1400437ab  push    rsi
0x1400437ac  push    rdi
0x1400437ad  push    r14
0x1400437af  sub     rsp, 20h
0x1400437b3  cmp     byte ptr [r8+1F9h], 0
0x1400437bb  mov     ebp, r9d
0x1400437be  mov     r14, rdx
0x1400437c1  jnz     loc_140043898
0x1400437c7  cmp     byte ptr [rcx+20h], 0
0x1400437cb  mov     rax, [rcx+38h]
0x1400437cf  lea     rbx, [rax+168h]
0x1400437d6  jnz     short loc_1400437E1
0x1400437d8  mov     rax, [rcx+288h]
0x1400437df  jmp     short loc_1400437E5
0x1400437e1  mov     rax, [rax+78h]
0x1400437e5  mov     rsi, [rax+28h]
0x1400437e9  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x1400437f0  add     rsi, 290h
0x1400437f7  call    cs:__imp_ExAcquireFastMutex
0x1400437fe  nop     dword ptr [rax+rax+00h]
0x140043803  xor     r9d, r9d
0x140043806  xor     r8d, r8d
0x140043809  mov     rdx, rbx
0x14004380c  mov     rcx, rsi
0x14004380f  call    cs:__imp_RxNameCacheFetchEntryEx
0x140043816  nop     dword ptr [rax+rax+00h]
0x14004381b  mov     rdi, rax
0x14004381e  test    rax, rax
0x140043821  jnz     short loc_140043843
0x140043823  mov     r9b, 1
0x140043826  xor     r8d, r8d
0x140043829  mov     rdx, rbx
0x14004382c  mov     rcx, rsi
0x14004382f  call    cs:__imp_RxNameCacheCreateEntryEx
0x140043836  nop     dword ptr [rax+rax+00h]
0x14004383b  mov     rdi, rax
0x14004383e  test    rax, rax
0x140043841  jz      short loc_140043885
0x140043843  mov     rax, [r14]
0x140043846  mov     rdx, [rdi+28h]
0x14004384a  mov     [rdx], rax
0x14004384d  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x140043854  mov     [rdi+30h], ebp
0x140043857  mov     rdx, [rax]
0x14004385a  mov     ebx, [rdx+8]
0x14004385d  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140043864  nop     dword ptr [rax+rax+00h]
0x140043869  mov     r9d, ebx; MRxContext
0x14004386c  mov     rdx, rdi; NameCache
0x14004386f  mov     rcx, rsi; NameCacheCtl
0x140043872  mov     r8d, [rax+90h]; LifeTime
0x140043879  call    cs:__imp_RxNameCacheActivateEntry
0x140043880  nop     dword ptr [rax+rax+00h]
0x140043885  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004388c  call    cs:__imp_ExReleaseFastMutex
0x140043893  nop     dword ptr [rax+rax+00h]
0x140043898  add     rsp, 20h
0x14004389c  pop     r14
0x14004389e  pop     rdi
0x14004389f  pop     rsi
0x1400438a0  pop     rbp
0x1400438a1  pop     rbx
0x1400438a2  retn
```
