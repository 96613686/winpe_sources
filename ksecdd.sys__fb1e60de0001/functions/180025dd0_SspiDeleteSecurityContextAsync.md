# SspiDeleteSecurityContextAsync

- ea: `0x180025dd0`
- end: `0x180025df7`
- name: `SspiDeleteSecurityContextAsync`
- size: `39`
- prototype: `SECURITY_STATUS __stdcall(SspiAsyncContext *AsyncContext, PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180025dd0`
- `0x180025e00`

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
0x180025dd0  sub     rsp, 28h
0x180025dd4  test    rcx, rcx
0x180025dd7  jz      short loc_180025DF0
0x180025dd9  cmp     dword ptr [rcx+14h], 90368h
0x180025de0  jz      short loc_180025DF0
0x180025de2  mov     r8, rdx
0x180025de5  call    DeleteSecurityContextInternal
0x180025dea  add     rsp, 28h
0x180025dee  retn
0x180025df0  mov     eax, 8009035Dh
0x180025df5  jmp     short loc_180025DEA
```
