# VmbusTlCommonProviderCloseEndpoint

- ea: `0x1400051b0`
- end: `0x14000527a`
- name: `VmbusTlCommonProviderCloseEndpoint`
- size: `202`
- prototype: `__int64 __fastcall(__int64, _OWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002b00`

## callees

- `0x1400051b0`
- `0x1400058d0`
- `0x140009834`
- `0x140009b84`
- `0x14000a048`

## string_xrefs

- `0x14000520b`: `VmbusTlCommonProviderCloseEndpoint`

## pseudocode

```c
__int64 __fastcall VmbusTlCommonProviderCloseEndpoint(__int64 a1, _OWORD *a2, __int64 a3, __int64 a4)
{
  signed __int64 v5; // rax
  bool v6; // cc
  signed __int64 v7; // rax

  *(_OWORD *)(a1 + 256) = *a2;
  if ( (unsigned int)dword_140013058 > 4 )
    HvsocketTraceEndpointMessage((const int *)"Closing endpoint.", a1, a3, a4);
  *(_BYTE *)(a1 + 296) = 1;
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (const int *)"VmbusTlCommonProviderCloseEndpoint",
      152,
      a1,
      *(_QWORD *)(a1 + 304),
      (const int *)"Initial reference. (deref)");
  v5 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 304), 0xFFFFFFFFFFFFFFFFuLL);
  v6 = v5 <= 1;
  v7 = v5 - 1;
  if ( v6 )
  {
    if ( v7 )
      __fastfail(0xEu);
    if ( (unsigned int)dword_140013058 > 4 )
      HvsocketTraceEndpointEvent((const int *)"VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", a1, 9);
    VmbusTlQueueEndpointAction(a1, a1 + 200, 9);
  }
  return 259;
}

```

## disassembly

```asm
0x1400051b0  push    rbx
0x1400051b2  sub     rsp, 30h
0x1400051b6  movups  xmm0, xmmword ptr [rdx]
0x1400051b9  mov     rbx, rcx
0x1400051bc  movdqu  xmmword ptr [rcx+100h], xmm0
0x1400051c4  mov     eax, cs:dword_140013058
0x1400051ca  cmp     eax, 4
0x1400051cd  jbe     short loc_1400051DE
0x1400051cf  mov     rdx, rcx
0x1400051d2  lea     rcx, aClosingEndpoin; "Closing endpoint."
0x1400051d9  call    HvsocketTraceEndpointMessage
0x1400051de  mov     byte ptr [rbx+128h], 1
0x1400051e5  mov     eax, cs:dword_140013058
0x1400051eb  cmp     eax, 5
0x1400051ee  jbe     short loc_140005217
0x1400051f0  mov     r9, [rbx+130h]
0x1400051f7  lea     rax, aInitialReferen; "Initial reference. (deref)"
0x1400051fe  mov     r8, rbx
0x140005201  mov     [rsp+38h+var_18], rax
0x140005206  mov     edx, 98h
0x14000520b  lea     rcx, aVmbustlcommonp; "VmbusTlCommonProviderCloseEndpoint"
0x140005212  call    HvsocketTraceReferenceCount
0x140005217  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000521b  lock xadd [rbx+130h], rax
0x140005224  sub     rax, 1
0x140005228  jg      short loc_14000526E
0x14000522a  test    rax, rax
0x14000522d  jz      short loc_140005238
0x14000522f  mov     ecx, 0Eh
0x140005234  int     29h; Win8: RtlFailFast(ecx)
0x140005236  jmp     short loc_14000526E
0x140005238  mov     eax, cs:dword_140013058
0x14000523e  cmp     eax, 4
0x140005241  jbe     short loc_140005258
0x140005243  mov     r8d, 9
0x140005249  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x140005250  mov     rdx, rbx
0x140005253  call    HvsocketTraceEndpointEvent
0x140005258  xor     r9d, r9d
0x14000525b  lea     rdx, [rbx+0C8h]
0x140005262  mov     rcx, rbx
0x140005265  lea     r8d, [r9+9]
0x140005269  call    VmbusTlQueueEndpointAction
0x14000526e  mov     eax, 103h
0x140005273  add     rsp, 30h
0x140005277  pop     rbx
0x140005278  retn
```
