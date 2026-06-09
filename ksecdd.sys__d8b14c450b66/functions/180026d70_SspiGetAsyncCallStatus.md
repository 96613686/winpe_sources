# SspiGetAsyncCallStatus

- ea: `0x180026d70`
- end: `0x180026d80`
- name: `SspiGetAsyncCallStatus`
- size: `16`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *Handle)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026d70`

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
0x180026d70  test    rcx, rcx
0x180026d73  jz      short loc_180026D7A
0x180026d75  mov     eax, [rcx+14h]
0x180026d78  retn
0x180026d7a  mov     eax, 8009035Dh
0x180026d7f  retn
```
