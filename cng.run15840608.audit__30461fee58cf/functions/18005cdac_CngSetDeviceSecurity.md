# CngSetDeviceSecurity

- ea: `0x18005cdac`
- end: `0x18005cdf4`
- name: `CngSetDeviceSecurity`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005cec8`

## callees

- `0x18000743c`
- `0x18005cdac`

## import_xrefs

- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x18005cdbe`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x18005cdbe`

## string_xrefs

- `0x18005cdd6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\cng.cxx`

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
0x18005cdac  push    rbx
0x18005cdae  sub     rsp, 20h
0x18005cdb2  lea     r8, g_HardCodedSd
0x18005cdb9  mov     edx, 1Fh
0x18005cdbe  call    cs:__imp_ObSetSecurityObjectByPointer
0x18005cdc5  nop     dword ptr [rax+rax+00h]
0x18005cdca  mov     ebx, eax
0x18005cdcc  test    eax, eax
0x18005cdce  jns     short loc_18005CDED
0x18005cdd0  mov     r9d, 32Bh
0x18005cdd6  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005cddd  lea     rdx, aNtstatus; "ntStatus"
0x18005cde4  mov     ecx, eax
0x18005cde6  call    DebugTraceError
0x18005cdeb  mov     eax, ebx
0x18005cded  add     rsp, 20h
0x18005cdf1  pop     rbx
0x18005cdf2  retn
```
