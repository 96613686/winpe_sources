# ACHandleToFormatName

- ea: `0x140006d50`
- end: `0x140006e80`
- name: `ACHandleToFormatName`
- size: `304`
- prototype: `__int64 __fastcall(struct CQueueBase *, void *, unsigned int, volatile void *Address)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x140006d50`
- `0x14000770c`
- `0x14000b5d8`
- `0x14001a564`
- `0x140024bf0`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140006ded`
- `ntoskrnl!ProbeForWrite` at `0x140006ded`

## pseudocode

```c
__int64 __fastcall ACHandleToFormatName(struct CQueueBase *a1, void *a2, unsigned int a3, volatile void *Address)
{
  int v8; // edi
  __int64 v10; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 114, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a1);
  }
  v8 = CQueueBase::Validate(a1);
  if ( v8 >= 0 )
  {
    ProbeForWrite(Address, 4u, 1u);
    if ( a2 )
      ACProbeArrayElementsForWrite(a2, v10, a3);
    return (*(unsigned int (__fastcall **)(struct CQueueBase *, void *, _QWORD, volatile void *))(*(_QWORD *)a1 + 96LL))(
             a1,
             a2,
             a3,
             Address);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 115, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a1);
    }
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x140006d50  mov     [rsp+arg_0], rcx
0x140006d55  push    rbx
0x140006d56  push    rsi
0x140006d57  push    rdi
0x140006d58  push    r12
0x140006d5a  push    r14
0x140006d5c  push    r15
0x140006d5e  sub     rsp, 48h
0x140006d62  mov     r15, r9
0x140006d65  mov     r14d, r8d
0x140006d68  mov     rsi, rdx
0x140006d6b  mov     rbx, rcx
0x140006d6e  lea     r12, WPP_GLOBAL_Control
0x140006d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140006d7c  cmp     rcx, r12
0x140006d7f  jz      short loc_140006DA0
0x140006d81  mov     eax, [rcx+6Ch]
0x140006d84  test    al, 4
0x140006d86  jz      short loc_140006DA0
0x140006d88  mov     edx, 72h ; 'r'
0x140006d8d  mov     r9, rbx
0x140006d90  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006d97  mov     rcx, [rcx+58h]
0x140006d9b  call    WPP_SF_q
0x140006da0  mov     rcx, rbx; struct CQueueBase *
0x140006da3  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140006da8  mov     edi, eax
0x140006daa  test    eax, eax
0x140006dac  jns     short loc_140006DE1
0x140006dae  mov     rcx, cs:WPP_GLOBAL_Control
0x140006db5  cmp     rcx, r12
0x140006db8  jz      short loc_140006DDA
0x140006dba  mov     edx, [rcx+6Ch]
0x140006dbd  test    dl, 1
0x140006dc0  jz      short loc_140006DDA
0x140006dc2  mov     edx, 73h ; 's'
0x140006dc7  mov     r9, rbx
0x140006dca  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006dd1  mov     rcx, [rcx+58h]
0x140006dd5  call    WPP_SF_q
0x140006dda  mov     eax, edi
0x140006ddc  jmp     loc_140006E71
0x140006de1  mov     edx, 4; Length
0x140006de6  lea     r8d, [rdx-3]; Alignment
0x140006dea  mov     rcx, r15; Address
0x140006ded  call    cs:__imp_ProbeForWrite
0x140006df4  nop     dword ptr [rax+rax+00h]
0x140006df9  test    rsi, rsi
0x140006dfc  jz      short loc_140006E09
0x140006dfe  mov     r8d, r14d; unsigned int
0x140006e01  mov     rcx, rsi; void *
0x140006e04  call    ?ACProbeArrayElementsForWrite@@YAXPEAXKK@Z; ACProbeArrayElementsForWrite(void *,ulong,ulong)
0x140006e09  mov     rax, [rbx]
0x140006e0c  mov     rax, [rax+60h]
0x140006e10  mov     r9, r15
0x140006e13  mov     r8d, r14d
0x140006e16  mov     rdx, rsi
0x140006e19  mov     rcx, rbx
0x140006e1c  call    _guard_dispatch_icall
0x140006e21  mov     ebx, eax
0x140006e23  mov     [rsp+78h+var_48], eax
0x140006e27  jmp     short loc_140006E6F
0x140006e29  mov     ebx, eax
0x140006e2b  mov     [rsp+78h+var_48], eax
0x140006e2f  lea     rax, WPP_GLOBAL_Control
0x140006e36  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e3d  cmp     rcx, rax
0x140006e40  jz      short loc_140006E6F
0x140006e42  mov     eax, [rcx+6Ch]
0x140006e45  test    al, 1
0x140006e47  jz      short loc_140006E6F
0x140006e49  mov     edx, 74h ; 't'
0x140006e4e  mov     rax, [rsp+78h+arg_0]
0x140006e56  mov     [rsp+78h+var_58], rax
0x140006e5b  mov     r9d, ebx
0x140006e5e  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140006e65  mov     rcx, [rcx+58h]
0x140006e69  call    WPP_SF_Dq
0x140006e6e  nop
0x140006e6f  mov     eax, ebx
0x140006e71  add     rsp, 48h
0x140006e75  pop     r15
0x140006e77  pop     r14
0x140006e79  pop     r12
0x140006e7b  pop     rdi
0x140006e7c  pop     rsi
0x140006e7d  pop     rbx
0x140006e7e  retn
```
