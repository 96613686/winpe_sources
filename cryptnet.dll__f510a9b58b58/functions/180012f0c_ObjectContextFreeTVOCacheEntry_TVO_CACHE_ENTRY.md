# ObjectContextFreeTVOCacheEntry(_TVO_CACHE_ENTRY *)

- ea: `0x180012f0c`
- end: `0x180012f5a`
- name: `?ObjectContextFreeTVOCacheEntry@@YAXPEAU_TVO_CACHE_ENTRY@@@Z`
- size: `78`
- prototype: `void __fastcall(HLOCAL hMem)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008f80`
- `0x180012540`
- `0x18001e410`

## callees

- `0x18000a990`
- `0x180012f0c`
- `0x180012f60`
- `0x180012f9c`

## import_xrefs

- `CRYPT32!I_CryptReleaseLruEntry` at `0x180012f23`
- `CRYPT32!I_CryptReleaseLruEntry` at `0x180012f23`

## pseudocode

```c
void __fastcall ObjectContextFreeTVOCacheEntry(HLOCAL hMem)
{
  __int64 v2; // rcx
  void *v3; // rdx

  RemoveCrlPreFetchEntry((struct _TVO_CACHE_ENTRY *)hMem);
  v2 = *((_QWORD *)hMem + 15);
  if ( v2 )
    I_CryptReleaseLruEntry(v2);
  operator delete(*((HLOCAL *)hMem + 7));
  operator delete(*((HLOCAL *)hMem + 9));
  v3 = (void *)*((_QWORD *)hMem + 5);
  if ( v3 )
    ObjectContextFree(*((const char **)hMem + 4), v3);
  operator delete(hMem);
}

```

## disassembly

```asm
0x180012f0c  push    rbx
0x180012f0e  sub     rsp, 20h
0x180012f12  mov     rbx, rcx
0x180012f15  call    ?RemoveCrlPreFetchEntry@@YAXPEAU_TVO_CACHE_ENTRY@@@Z; RemoveCrlPreFetchEntry(_TVO_CACHE_ENTRY *)
0x180012f1a  mov     rcx, [rbx+78h]
0x180012f1e  test    rcx, rcx
0x180012f21  jz      short loc_180012F29
0x180012f23  call    cs:__imp_I_CryptReleaseLruEntry
0x180012f29  mov     rcx, [rbx+38h]; hMem
0x180012f2d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012f32  mov     rcx, [rbx+48h]; hMem
0x180012f36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012f3b  mov     rdx, [rbx+28h]; void *
0x180012f3f  test    rdx, rdx
0x180012f42  jz      short loc_180012F4D
0x180012f44  mov     rcx, [rbx+20h]; char *
0x180012f48  call    ?ObjectContextFree@@YAXPEBDPEAX@Z; ObjectContextFree(char const *,void *)
0x180012f4d  mov     rcx, rbx; hMem
0x180012f50  add     rsp, 20h
0x180012f54  pop     rbx
0x180012f55  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
