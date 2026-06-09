# SspiDeleteSecurityContextAsync

- ea: `0x180025d80`
- end: `0x180025da7`
- name: `SspiDeleteSecurityContextAsync`
- size: `39`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *AsyncContext, PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180025d80`
- `0x180025db0`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiDeleteSecurityContextAsync(SspiAsyncContext *AsyncContext, PCtxtHandle phContext)
{
  if ( !AsyncContext || *((_DWORD *)AsyncContext + 5) == 590696 )
    return -2146892963;
  else
    return DeleteSecurityContextInternal((LARGE_INTEGER *)AsyncContext, (__int64)phContext, phContext);
}

```

## disassembly

```asm
0x180025d80  sub     rsp, 28h
0x180025d84  test    rcx, rcx
0x180025d87  jz      short loc_180025DA0
0x180025d89  cmp     dword ptr [rcx+14h], 90368h
0x180025d90  jz      short loc_180025DA0
0x180025d92  mov     r8, rdx
0x180025d95  call    DeleteSecurityContextInternal
0x180025d9a  add     rsp, 28h
0x180025d9e  retn
0x180025da0  mov     eax, 8009035Dh
0x180025da5  jmp     short loc_180025D9A
```
