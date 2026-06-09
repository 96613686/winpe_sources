# CngSetDeviceSecurity

- ea: `0x180066f7c`
- end: `0x180066fc4`
- name: `CngSetDeviceSecurity`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180067098`

## callees

- `0x18001155c`
- `0x180066f7c`

## import_xrefs

- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x180066f8e`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x180066f8e`

## string_xrefs

- `0x180066fa6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`

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
0x180066f7c  push    rbx
0x180066f7e  sub     rsp, 20h
0x180066f82  lea     r8, g_HardCodedSd
0x180066f89  mov     edx, 1Fh
0x180066f8e  call    cs:__imp_ObSetSecurityObjectByPointer
0x180066f95  nop     dword ptr [rax+rax+00h]
0x180066f9a  mov     ebx, eax
0x180066f9c  test    eax, eax
0x180066f9e  jns     short loc_180066FBD
0x180066fa0  mov     r9d, 32Bh
0x180066fa6  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066fad  lea     rdx, aNtstatus; "ntStatus"
0x180066fb4  mov     ecx, eax
0x180066fb6  call    DebugTraceError
0x180066fbb  mov     eax, ebx
0x180066fbd  add     rsp, 20h
0x180066fc1  pop     rbx
0x180066fc2  retn
```
