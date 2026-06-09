# GetInfo

- ea: `0x180003c5c`
- end: `0x180003ccb`
- name: `GetInfo`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002710`

## callees

- `0x180003c5c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003ca0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003cba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003ca0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003cba`

## pseudocode

```c
__int64 __fastcall GetInfo(__int64 a1, unsigned int a2)
{
  if ( a1 )
  {
    if ( a2 < 0x238 )
      return 0;
    strcpy((char *)(a1 + 4), "vidcIYUV");
    *(_BYTE *)(a1 + 13) = 0;
    *(_WORD *)(a1 + 14) = 0;
    *(_DWORD *)(a1 + 16) = 0;
    LoadStringW(hDriverModule, 1u, (LPWSTR)(a1 + 56), 128);
    LoadStringW(hDriverModule, 2u, (LPWSTR)(a1 + 24), 16);
  }
  return 568;
}

```

## disassembly

```asm
0x180003c5c  push    rbx
0x180003c5e  sub     rsp, 20h
0x180003c62  mov     rbx, rcx
0x180003c65  test    rcx, rcx
0x180003c68  jz      short loc_180003CC0
0x180003c6a  cmp     edx, 238h
0x180003c70  jnb     short loc_180003C76
0x180003c72  xor     eax, eax
0x180003c74  jmp     short loc_180003CC5
0x180003c76  mov     edx, 1; uID
0x180003c7b  mov     dword ptr [rcx+4], 63646976h
0x180003c82  mov     qword ptr [rcx+8], 56555949h
0x180003c8a  lea     r8, [rcx+38h]; lpBuffer
0x180003c8e  mov     dword ptr [rcx+10h], 0
0x180003c95  mov     rcx, cs:hDriverModule; hInstance
0x180003c9c  lea     r9d, [rdx+7Fh]; cchBufferMax
0x180003ca0  call    cs:__imp_LoadStringW
0x180003ca6  mov     rcx, cs:hDriverModule; hInstance
0x180003cad  lea     r8, [rbx+18h]; lpBuffer
0x180003cb1  mov     edx, 2; uID
0x180003cb6  lea     r9d, [rdx+0Eh]; cchBufferMax
0x180003cba  call    cs:__imp_LoadStringW
0x180003cc0  mov     eax, 238h
0x180003cc5  add     rsp, 20h
0x180003cc9  pop     rbx
0x180003cca  retn
```
