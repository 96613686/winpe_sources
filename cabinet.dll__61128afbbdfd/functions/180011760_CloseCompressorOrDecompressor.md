# CloseCompressorOrDecompressor

- ea: `0x180011760`
- end: `0x180011788`
- name: `CloseCompressorOrDecompressor`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011710`
- `0x180011750`

## callees

- `0x180011760`
- `0x180011d6c`
- `0x1800120ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001176f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001176f`

## pseudocode

```c
__int64 __fastcall CloseCompressorOrDecompressor(__int64 a1, __int64 a2)
{
  DWORD v2; // eax
  __int64 v3; // rcx

  v2 = CmpsValidateHandle(a1, a2);
  if ( v2 )
  {
    SetLastError(v2);
    return 0;
  }
  else
  {
    CmpsFreeContext(v3);
    return 1;
  }
}

```

## disassembly

```asm
0x180011760  sub     rsp, 28h
0x180011764  call    CmpsValidateHandle
0x180011769  test    eax, eax
0x18001176b  jz      short loc_18001177C
0x18001176d  mov     ecx, eax; dwErrCode
0x18001176f  call    cs:__imp_SetLastError
0x180011775  xor     eax, eax
0x180011777  add     rsp, 28h
0x18001177b  retn
0x18001177c  call    CmpsFreeContext
0x180011781  mov     eax, 1
0x180011786  jmp     short loc_180011777
```
