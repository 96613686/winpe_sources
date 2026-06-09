# SspiGetAsyncCallStatus

- ea: `0x180026dc0`
- end: `0x180026dd0`
- name: `SspiGetAsyncCallStatus`
- size: `16`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *Handle)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026dc0`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiGetAsyncCallStatus(SspiAsyncContext *Handle)
{
  if ( Handle )
    return *((_DWORD *)Handle + 5);
  else
    return -2146892963;
}

```

## disassembly

```asm
0x180026dc0  test    rcx, rcx
0x180026dc3  jz      short loc_180026DCA
0x180026dc5  mov     eax, [rcx+14h]
0x180026dc8  retn
0x180026dca  mov     eax, 8009035Dh
0x180026dcf  retn
```
