# MRxDAVInvalidateFileNotFoundCache

- ea: `0x14002586c`
- end: `0x140025935`
- name: `MRxDAVInvalidateFileNotFoundCache`
- size: `201`
- prototype: `_UNKNOWN **__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400130e0`

## callees

- `0x1400027ac`
- `0x14002586c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14002589f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002589f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400258e9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400258e9`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400258bb`
- `rdbss!RxNameCacheFetchEntryEx` at `0x1400258bb`
- `rdbss!RxNameCacheExpireEntry` at `0x1400258d6`
- `rdbss!RxNameCacheExpireEntry` at `0x1400258d6`

## pseudocode

```c
_UNKNOWN **__fastcall MRxDAVInvalidateFileNotFoundCache(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rdi
  struct _NAME_CACHE *Entry; // rax
  _UNKNOWN **result; // rax

  v1 = *(_QWORD *)(a1 + 56);
  v2 = v1 + 360;
  if ( *(_BYTE *)(a1 + 32) )
    v3 = *(_QWORD *)(v1 + 120);
  else
    v3 = *(_QWORD *)(a1 + 648);
  v4 = *(_QWORD *)(v3 + 40);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v4 + 384, v2, 0, 0);
  if ( Entry )
    RxNameCacheExpireEntry((PNAME_CACHE_CONTROL)(v4 + 384), Entry);
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    return (_UNKNOWN **)WPP_SF_Z(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          31,
                          WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids,
                          v2);
  return result;
}

```

## disassembly

```asm
0x14002586c  mov     [rsp+arg_0], rbx
0x140025871  push    rdi
0x140025872  sub     rsp, 20h
0x140025876  cmp     byte ptr [rcx+20h], 0
0x14002587a  mov     rax, [rcx+38h]
0x14002587e  lea     rbx, [rax+168h]
0x140025885  jnz     short loc_140025890
0x140025887  mov     rax, [rcx+288h]
0x14002588e  jmp     short loc_140025894
0x140025890  mov     rax, [rax+78h]
0x140025894  mov     rdi, [rax+28h]
0x140025898  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x14002589f  call    cs:__imp_ExAcquireFastMutex
0x1400258a6  nop     dword ptr [rax+rax+00h]
0x1400258ab  xor     r9d, r9d
0x1400258ae  lea     rcx, [rdi+180h]
0x1400258b5  xor     r8d, r8d
0x1400258b8  mov     rdx, rbx
0x1400258bb  call    cs:__imp_RxNameCacheFetchEntryEx
0x1400258c2  nop     dword ptr [rax+rax+00h]
0x1400258c7  test    rax, rax
0x1400258ca  jz      short loc_1400258E2
0x1400258cc  mov     rdx, rax; NameCache
0x1400258cf  lea     rcx, [rdi+180h]; NameCacheCtl
0x1400258d6  call    cs:__imp_RxNameCacheExpireEntry
0x1400258dd  nop     dword ptr [rax+rax+00h]
0x1400258e2  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x1400258e9  call    cs:__imp_ExReleaseFastMutex
0x1400258f0  nop     dword ptr [rax+rax+00h]
0x1400258f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400258fc  lea     rax, WPP_GLOBAL_Control
0x140025903  cmp     rcx, rax
0x140025906  jz      short loc_140025929
0x140025908  test    dword ptr [rcx+2Ch], 2000h
0x14002590f  jz      short loc_140025929
0x140025911  mov     rcx, [rcx+18h]
0x140025915  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x14002591c  mov     edx, 1Fh
0x140025921  mov     r9, rbx
0x140025924  call    WPP_SF_Z
0x140025929  mov     rbx, [rsp+28h+arg_0]
0x14002592e  add     rsp, 20h
0x140025932  pop     rdi
0x140025933  retn
```
