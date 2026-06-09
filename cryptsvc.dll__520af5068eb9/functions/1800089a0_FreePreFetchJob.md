# FreePreFetchJob

- ea: `0x1800089a0`
- end: `0x1800089fd`
- name: `FreePreFetchJob`
- size: `93`
- prototype: `__int64 __fastcall(_QWORD *hMem)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b60`
- `0x180003c90`
- `0x18000f950`

## callees

- `0x1800068b0`
- `0x180007a80`
- `0x1800089a0`

## import_xrefs

- `CRYPT32!CryptMemFree` at `0x1800089ed`
- `CRYPT32!CryptMemFree` at `0x1800089f5`
- `CRYPT32!CryptMemFree` at `0x1800089ed`
- `CRYPT32!CryptMemFree` at `0x1800089f5`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x1800089da`
- `CRYPT32!I_CryptRemoveLruEntry` at `0x1800089da`

## pseudocode

```c
__int64 __fastcall FreePreFetchJob(_QWORD *hMem)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  ReleaseTokenEntry(hMem + 16);
  v2 = (void *)hMem[27];
  if ( v2 )
    CryptMemFree(v2);
  v3 = (void *)hMem[28];
  if ( v3 )
    CryptMemFree(v3);
  v4 = hMem[13];
  if ( v4 )
    I_CryptRemoveLruEntry(v4, 4);
  return PkiFree(hMem);
}

```

## disassembly

```asm
0x1800089a0  push    rbx
0x1800089a2  sub     rsp, 20h
0x1800089a6  mov     rbx, rcx
0x1800089a9  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1800089ad  call    ReleaseTokenEntry
0x1800089b2  mov     rcx, [rbx+0D8h]; pv
0x1800089b9  test    rcx, rcx
0x1800089bc  jnz     short loc_1800089F5
0x1800089be  mov     rcx, [rbx+0E0h]; pv
0x1800089c5  test    rcx, rcx
0x1800089c8  jnz     short loc_1800089ED
0x1800089ca  mov     rcx, [rbx+68h]
0x1800089ce  test    rcx, rcx
0x1800089d1  jz      short loc_1800089E0
0x1800089d3  xor     r8d, r8d
0x1800089d6  lea     edx, [r8+4]
0x1800089da  call    cs:__imp_I_CryptRemoveLruEntry
0x1800089e0  mov     rcx, rbx; hMem
0x1800089e3  add     rsp, 20h
0x1800089e7  pop     rbx
0x1800089e8  jmp     PkiFree
0x1800089ed  call    cs:__imp_CryptMemFree
0x1800089f3  jmp     short loc_1800089CA
0x1800089f5  call    cs:__imp_CryptMemFree
0x1800089fb  jmp     short loc_1800089BE
```
