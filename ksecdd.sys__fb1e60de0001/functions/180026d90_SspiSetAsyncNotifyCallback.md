# SspiSetAsyncNotifyCallback

- ea: `0x180026d90`
- end: `0x180026daf`
- name: `SspiSetAsyncNotifyCallback`
- size: `31`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *Context, SspiAsyncNotifyCallback Callback, void *CallbackData)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026d90`

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
0x180026d90  test    rcx, rcx
0x180026d93  jz      short loc_180026DA9
0x180026d95  cmp     dword ptr [rcx+14h], 90368h
0x180026d9c  jz      short loc_180026DA9
0x180026d9e  mov     [rcx], rdx
0x180026da1  xor     eax, eax
0x180026da3  mov     [rcx+8], r8
0x180026da7  retn
0x180026da9  mov     eax, 8009035Dh
0x180026dae  retn
```
