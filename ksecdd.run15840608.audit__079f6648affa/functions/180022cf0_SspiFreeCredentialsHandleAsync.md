# SspiFreeCredentialsHandleAsync

- ea: `0x180022cf0`
- end: `0x180022d08`
- name: `SspiFreeCredentialsHandleAsync`
- size: `24`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *AsyncContext, PCredHandle phCredential)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022cf0`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiFreeCredentialsHandleAsync(SspiAsyncContext *AsyncContext, PCredHandle phCredential)
{
  SECURITY_STATUS result; // eax

  result = -2146892963;
  if ( AsyncContext )
  {
    if ( *((_DWORD *)AsyncContext + 5) != 590696 )
      return -2146893054;
  }
  return result;
}

```

## disassembly

```asm
0x180022cf0  mov     eax, 8009035Dh
0x180022cf5  test    rcx, rcx
0x180022cf8  jz      short locret_180022D07
0x180022cfa  cmp     dword ptr [rcx+14h], 90368h
0x180022d01  lea     edx, [rax-5Bh]
0x180022d04  cmovnz  eax, edx
0x180022d07  retn
```
