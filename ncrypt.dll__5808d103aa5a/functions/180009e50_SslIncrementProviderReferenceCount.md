# SslIncrementProviderReferenceCount

- ea: `0x180009e50`
- end: `0x180009e93`
- name: `SslIncrementProviderReferenceCount`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009e50`
- `0x180009ea0`
- `0x18000e120`

## string_xrefs

- `0x180009e74`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
__int64 __fastcall SslIncrementProviderReferenceCount(__int64 a1)
{
  __int64 v1; // rax
  unsigned int v2; // ebx

  v1 = ValidateSslProvHandle(a1);
  if ( v1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v1 + 16));
    return 0;
  }
  else
  {
    v2 = -1073741816;
    DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3297);
  }
  return v2;
}

```

## disassembly

```asm
0x180009e50  push    rbx
0x180009e52  sub     rsp, 20h
0x180009e56  call    ValidateSslProvHandle
0x180009e5b  test    rax, rax
0x180009e5e  jz      short loc_180009E6E
0x180009e60  lock inc dword ptr [rax+10h]
0x180009e64  xor     ebx, ebx
0x180009e66  mov     eax, ebx
0x180009e68  add     rsp, 20h
0x180009e6c  pop     rbx
0x180009e6d  retn
0x180009e6e  mov     r9d, 0CE1h
0x180009e74  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009e7b  lea     rdx, aStatus; "Status"
0x180009e82  mov     ecx, 0C0000008h
0x180009e87  mov     ebx, 0C0000008h
0x180009e8c  call    DebugTraceError
0x180009e91  jmp     short loc_180009E66
```
