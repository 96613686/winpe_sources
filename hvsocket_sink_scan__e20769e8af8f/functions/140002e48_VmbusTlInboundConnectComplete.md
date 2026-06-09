# VmbusTlInboundConnectComplete

- ea: `0x140002e48`
- end: `0x140002f2e`
- name: `VmbusTlInboundConnectComplete`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400023b0`

## callees

- `0x14000227c`
- `0x140002e48`
- `0x1400058d0`
- `0x140005d74`
- `0x14000975c`
- `0x140009834`
- `0x14000a048`

## string_xrefs

- `0x140002ebe`: `VmbusTlCommonRevertSuccessfulConnection`
- `0x140002e84`: `VmbusTlInboundConnectComplete`

## pseudocode

```c
__int64 __fastcall VmbusTlInboundConnectComplete(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  signed __int64 v5; // rax
  bool v6; // cc

  VmbusTlCommonPrepareSuccessfulConnection(a1);
  result = VmbusTlNotifyListenerAccept(*(_QWORD *)(a1 + 944), a1);
  *a2 = result;
  if ( (int)result < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointError("VmbusTlInboundConnectComplete", 651, (unsigned int)result, a1);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"VmbusTlCommonRevertSuccessfulConnection",
        564,
        a1,
        *(_QWORD *)(a1 + 304),
        (__int64)"Connection reference. (deref)");
    v5 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 304), 0xFFFFFFFFFFFFFFFFuLL);
    v6 = v5 <= 1;
    result = v5 - 1;
    if ( v6 )
    {
      if ( result )
        __fastfail(0xEu);
      if ( (unsigned int)dword_140013058 > 4 )
        HvsocketTraceEndpointEvent("VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", a1, 9);
      return VmbusTlQueueEndpointAction(a1, a1 + 200, 9, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002e48  mov     [rsp+arg_0], rbx
0x140002e4d  push    rdi
0x140002e4e  sub     rsp, 30h
0x140002e52  mov     rbx, rdx
0x140002e55  mov     rdi, rcx
0x140002e58  call    VmbusTlCommonPrepareSuccessfulConnection
0x140002e5d  mov     rcx, [rdi+3B0h]
0x140002e64  mov     rdx, rdi
0x140002e67  call    VmbusTlNotifyListenerAccept
0x140002e6c  mov     [rbx], eax
0x140002e6e  test    eax, eax
0x140002e70  jns     loc_140002F22
0x140002e76  mov     edx, cs:dword_140013058
0x140002e7c  cmp     edx, 2
0x140002e7f  jbe     short loc_140002E98
0x140002e81  mov     r9, rdi
0x140002e84  lea     rcx, aVmbustlinbound; "VmbusTlInboundConnectComplete"
0x140002e8b  mov     r8d, eax
0x140002e8e  mov     edx, 28Bh
0x140002e93  call    HvsocketTraceEndpointError
0x140002e98  mov     eax, cs:dword_140013058
0x140002e9e  cmp     eax, 5
0x140002ea1  jbe     short loc_140002ECA
0x140002ea3  mov     r9, [rdi+130h]
0x140002eaa  lea     rax, aConnectionRefe; "Connection reference. (deref)"
0x140002eb1  mov     r8, rdi
0x140002eb4  mov     [rsp+38h+var_18], rax
0x140002eb9  mov     edx, 234h
0x140002ebe  lea     rcx, aVmbustlcommonr; "VmbusTlCommonRevertSuccessfulConnection"
0x140002ec5  call    HvsocketTraceReferenceCount
0x140002eca  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002ece  lock xadd [rdi+130h], rax
0x140002ed7  sub     rax, 1
0x140002edb  jg      short loc_140002F22
0x140002edd  test    rax, rax
0x140002ee0  jz      short loc_140002EEB
0x140002ee2  mov     ecx, 0Eh
0x140002ee7  int     29h; Win8: RtlFailFast(ecx)
0x140002ee9  jmp     short loc_140002F22
0x140002eeb  mov     eax, cs:dword_140013058
0x140002ef1  mov     ebx, 9
0x140002ef6  cmp     eax, 4
0x140002ef9  jbe     short loc_140002F0D
0x140002efb  mov     r8d, ebx
0x140002efe  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x140002f05  mov     rdx, rdi
0x140002f08  call    HvsocketTraceEndpointEvent
0x140002f0d  lea     rdx, [rdi+0C8h]
0x140002f14  xor     r9d, r9d
0x140002f17  mov     r8d, ebx
0x140002f1a  mov     rcx, rdi
0x140002f1d  call    VmbusTlQueueEndpointAction
0x140002f22  mov     rbx, [rsp+38h+arg_0]
0x140002f27  add     rsp, 30h
0x140002f2b  pop     rdi
0x140002f2c  retn
```
