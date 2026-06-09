# SspiSetAsyncNotifyCallback

- ea: `0x180026d40`
- end: `0x180026d5f`
- name: `SspiSetAsyncNotifyCallback`
- size: `31`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *Context, SspiAsyncNotifyCallback Callback, void *CallbackData)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026d40`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiSetAsyncNotifyCallback(
        SspiAsyncContext *Context,
        SspiAsyncNotifyCallback Callback,
        void *CallbackData)
{
  SECURITY_STATUS result; // eax

  if ( !Context || *((_DWORD *)Context + 5) == 590696 )
    return -2146892963;
  *(_QWORD *)Context = Callback;
  result = 0;
  *((_QWORD *)Context + 1) = CallbackData;
  return result;
}

```

## disassembly

```asm
0x180026d40  test    rcx, rcx
0x180026d43  jz      short loc_180026D59
0x180026d45  cmp     dword ptr [rcx+14h], 90368h
0x180026d4c  jz      short loc_180026D59
0x180026d4e  mov     [rcx], rdx
0x180026d51  xor     eax, eax
0x180026d53  mov     [rcx+8], r8
0x180026d57  retn
0x180026d59  mov     eax, 8009035Dh
0x180026d5e  retn
```
