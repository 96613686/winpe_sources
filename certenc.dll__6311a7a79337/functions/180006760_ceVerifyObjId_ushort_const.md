# ceVerifyObjId(ushort const *)

- ea: `0x180006760`
- end: `0x1800067ae`
- name: `?ceVerifyObjId@@YAJPEBG@Z`
- size: `78`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800032e0`
- `0x1800081f0`

## callees

- `0x180005ab8`
- `0x180006760`
- `0x1800067b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067a0`

## pseudocode

```c
__int64 __fastcall ceVerifyObjId(const unsigned __int16 *a1)
{
  unsigned int v1; // edi
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  hMem = 0;
  if ( (unsigned int)ceConvertWszToSz(&hMem, a1) )
    v1 = ceVerifyObjIdA((const char *)hMem);
  else
    v1 = -2147024882;
  if ( hMem )
    LocalFree(hMem);
  return v1;
}

```

## disassembly

```asm
0x180006760  push    rdi
0x180006762  sub     rsp, 20h
0x180006766  mov     rdx, rcx; unsigned __int16 *
0x180006769  mov     [rsp+28h+hMem], 0
0x180006772  lea     rcx, [rsp+28h+hMem]; char **
0x180006777  call    ?ceConvertWszToSz@@YAHPEAPEADPEBGJ@Z; ceConvertWszToSz(char * *,ushort const *,long)
0x18000677c  test    eax, eax
0x18000677e  jnz     short loc_180006787
0x180006780  mov     edi, 8007000Eh
0x180006785  jmp     short loc_180006793
0x180006787  mov     rcx, [rsp+28h+hMem]; char *
0x18000678c  call    ?ceVerifyObjIdA@@YAJPEBD@Z; ceVerifyObjIdA(char const *)
0x180006791  mov     edi, eax
0x180006793  cmp     [rsp+28h+hMem], 0
0x180006799  jz      short loc_1800067A6
0x18000679b  mov     rcx, [rsp+28h+hMem]; hMem
0x1800067a0  call    cs:__imp_LocalFree
0x1800067a6  mov     eax, edi
0x1800067a8  add     rsp, 20h
0x1800067ac  pop     rdi
0x1800067ad  retn
```
