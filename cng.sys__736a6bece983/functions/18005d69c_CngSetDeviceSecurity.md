# CngSetDeviceSecurity

- ea: `0x18005d69c`
- end: `0x18005d6e4`
- name: `CngSetDeviceSecurity`
- size: `72`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005d7b8`

## callees

- `0x18000743c`
- `0x18005d69c`

## import_xrefs

- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x18005d6ae`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x18005d6ae`

## string_xrefs

- `0x18005d6c6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`

## pseudocode

```c
__int64 __fastcall CngSetDeviceSecurity(__int64 a1)
{
  __int64 result; // rax
  unsigned int v2; // ebx

  result = ObSetSecurityObjectByPointer(a1, 31, g_HardCodedSd);
  v2 = result;
  if ( (int)result < 0 )
  {
    DebugTraceError(
      (unsigned int)result,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\cng.cxx",
      811);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18005d69c  push    rbx
0x18005d69e  sub     rsp, 20h
0x18005d6a2  lea     r8, g_HardCodedSd
0x18005d6a9  mov     edx, 1Fh
0x18005d6ae  call    cs:__imp_ObSetSecurityObjectByPointer
0x18005d6b5  nop     dword ptr [rax+rax+00h]
0x18005d6ba  mov     ebx, eax
0x18005d6bc  test    eax, eax
0x18005d6be  jns     short loc_18005D6DD
0x18005d6c0  mov     r9d, 32Bh
0x18005d6c6  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005d6cd  lea     rdx, aNtstatus; "ntStatus"
0x18005d6d4  mov     ecx, eax
0x18005d6d6  call    DebugTraceError
0x18005d6db  mov     eax, ebx
0x18005d6dd  add     rsp, 20h
0x18005d6e1  pop     rbx
0x18005d6e2  retn
```
