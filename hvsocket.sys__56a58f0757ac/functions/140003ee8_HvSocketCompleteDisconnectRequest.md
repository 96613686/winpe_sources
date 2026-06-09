# HvSocketCompleteDisconnectRequest

- ea: `0x140003ee8`
- end: `0x140003fd8`
- name: `HvSocketCompleteDisconnectRequest`
- size: `240`
- prototype: `void __fastcall(__int64, unsigned int, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400020c4`
- `0x14000440c`
- `0x140004690`
- `0x1400049a0`

## callees

- `0x140003ee8`
- `0x1400058d0`
- `0x140009834`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140003f36`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140003f36`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003f13`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140003f13`

## string_xrefs

- `0x140003f68`: `HvSocketCompleteDisconnectRequest`

## pseudocode

```c
void __fastcall HvSocketCompleteDisconnectRequest(__int64 a1, unsigned int a2, __int64 a3)
{
  void (__fastcall *v3)(_QWORD, _QWORD, _QWORD); // rbp
  signed __int64 v7; // rax
  bool v8; // cc
  signed __int64 v9; // rax

  v3 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))a3;
  *(_QWORD *)a3 = 0;
  if ( v3 )
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a1 + 72));
    v3(*(_QWORD *)(a3 + 8), a2, *(_QWORD *)(a3 + 56));
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 72));
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (unsigned int)"HvSocketCompleteDisconnectRequest",
        193,
        a1,
        *(_QWORD *)(a1 + 304),
        (__int64)"Disconnect request. (deref)");
    v7 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 304), 0xFFFFFFFFFFFFFFFFuLL);
    v8 = v7 <= 1;
    v9 = v7 - 1;
    if ( v8 )
    {
      if ( v9 )
        __fastfail(0xEu);
      if ( (unsigned int)dword_140013058 > 4 )
        HvsocketTraceEndpointEvent("VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", a1, 9);
      VmbusTlQueueEndpointAction(a1, a1 + 200, 9);
    }
  }
}

```

## disassembly

```asm
0x140003ee8  push    rbx
0x140003eea  push    rbp
0x140003eeb  push    rsi
0x140003eec  push    rdi
0x140003eed  push    r14
0x140003eef  sub     rsp, 30h
0x140003ef3  mov     rbp, [r8]
0x140003ef6  mov     rsi, r8
0x140003ef9  mov     qword ptr [r8], 0
0x140003f00  mov     r14d, edx
0x140003f03  mov     rdi, rcx
0x140003f06  test    rbp, rbp
0x140003f09  jz      loc_140003FCC
0x140003f0f  add     rcx, 48h ; 'H'; SpinLock
0x140003f13  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140003f1a  nop     dword ptr [rax+rax+00h]
0x140003f1f  mov     r8, [rsi+38h]
0x140003f23  mov     edx, r14d
0x140003f26  mov     rcx, [rsi+8]
0x140003f2a  mov     rax, rbp
0x140003f2d  call    _guard_dispatch_icall
0x140003f32  lea     rcx, [rdi+48h]; SpinLock
0x140003f36  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140003f3d  nop     dword ptr [rax+rax+00h]
0x140003f42  mov     eax, cs:dword_140013058
0x140003f48  cmp     eax, 5
0x140003f4b  jbe     short loc_140003F74
0x140003f4d  mov     r9, [rdi+130h]
0x140003f54  lea     rax, aDisconnectRequ_0; "Disconnect request. (deref)"
0x140003f5b  mov     r8, rdi
0x140003f5e  mov     [rsp+58h+var_38], rax
0x140003f63  mov     edx, 0C1h
0x140003f68  lea     rcx, aHvsocketcomple; "HvSocketCompleteDisconnectRequest"
0x140003f6f  call    HvsocketTraceReferenceCount
0x140003f74  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003f78  lock xadd [rdi+130h], rax
0x140003f81  sub     rax, 1
0x140003f85  jg      short loc_140003FCC
0x140003f87  test    rax, rax
0x140003f8a  jz      short loc_140003F95
0x140003f8c  mov     ecx, 0Eh
0x140003f91  int     29h; Win8: RtlFailFast(ecx)
0x140003f93  jmp     short loc_140003FCC
0x140003f95  mov     eax, cs:dword_140013058
0x140003f9b  mov     ebx, 9
0x140003fa0  cmp     eax, 4
0x140003fa3  jbe     short loc_140003FB7
0x140003fa5  mov     r8d, ebx
0x140003fa8  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x140003faf  mov     rdx, rdi
0x140003fb2  call    HvsocketTraceEndpointEvent
0x140003fb7  lea     rdx, [rdi+0C8h]
0x140003fbe  xor     r9d, r9d
0x140003fc1  mov     r8d, ebx
0x140003fc4  mov     rcx, rdi
0x140003fc7  call    VmbusTlQueueEndpointAction
0x140003fcc  add     rsp, 30h
0x140003fd0  pop     r14
0x140003fd2  pop     rdi
0x140003fd3  pop     rsi
0x140003fd4  pop     rbp
0x140003fd5  pop     rbx
0x140003fd6  retn
```
