# VmbusTlCommonPrepareSuccessfulConnection

- ea: `0x14000227c`
- end: `0x1400022dc`
- name: `VmbusTlCommonPrepareSuccessfulConnection`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400023b0`
- `0x140002e48`

## callees

- `0x14000227c`
- `0x14000a048`

## string_xrefs

- `0x1400022a6`: `VmbusTlCommonPrepareSuccessfulConnection`

## pseudocode

```c
__int64 __fastcall VmbusTlCommonPrepareSuccessfulConnection(__int64 a1)
{
  __int64 result; // rax

  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlCommonPrepareSuccessfulConnection",
      552,
      a1,
      *(_QWORD *)(a1 + 304),
      (__int64)"Connection reference.");
  result = _InterlockedIncrement64((volatile signed __int64 *)(a1 + 304));
  if ( result <= 1 )
    __fastfail(0xEu);
  return result;
}

```

## disassembly

```asm
0x14000227c  push    rbx
0x14000227e  sub     rsp, 30h
0x140002282  mov     eax, cs:dword_140013058
0x140002288  mov     rbx, rcx
0x14000228b  cmp     eax, 5
0x14000228e  jbe     short loc_1400022B7
0x140002290  mov     r9, [rcx+130h]
0x140002297  lea     rax, aConnectionRefe_0; "Connection reference."
0x14000229e  mov     r8, rcx
0x1400022a1  mov     [rsp+38h+var_18], rax
0x1400022a6  lea     rcx, aVmbustlcommonp_0; "VmbusTlCommonPrepareSuccessfulConnectio"...
0x1400022ad  mov     edx, 228h
0x1400022b2  call    HvsocketTraceReferenceCount
0x1400022b7  mov     eax, 1
0x1400022bc  lock xadd [rbx+130h], rax
0x1400022c5  inc     rax
0x1400022c8  cmp     rax, 1
0x1400022cc  jg      short loc_1400022D5
0x1400022ce  mov     ecx, 0Eh
0x1400022d3  int     29h; Win8: RtlFailFast(ecx)
0x1400022d5  add     rsp, 30h
0x1400022d9  pop     rbx
0x1400022da  retn
```
