# ACSetSequenceAck

- ea: `0x140008dec`
- end: `0x140008ee8`
- name: `ACSetSequenceAck`
- size: `252`
- prototype: `__int64 __fastcall(struct CQueueBase *, volatile void *Address)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x140003d84`
- `0x140008dec`
- `0x14001a564`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140008e7d`
- `ntoskrnl!ProbeForRead` at `0x140008e7d`

## pseudocode

```c
__int64 __fastcall ACSetSequenceAck(struct CQueueBase *a1, _QWORD *Address)
{
  int v4; // edi
  int v6; // ecx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 167, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a1);
  }
  v4 = CQueueBase::Validate(a1);
  if ( v4 >= 0 )
  {
    ProbeForRead(Address, 0x10u, 1u);
    v6 = *((_DWORD *)Address + 2);
    *((_QWORD *)a1 + 41) = *Address;
    *((_DWORD *)a1 + 80) = v6;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 168, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a1);
    }
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x140008dec  mov     [rsp+arg_0], rcx
0x140008df1  push    rbx
0x140008df2  push    rsi
0x140008df3  push    rdi
0x140008df4  push    r14
0x140008df6  sub     rsp, 38h
0x140008dfa  mov     rsi, rdx
0x140008dfd  mov     rbx, rcx
0x140008e00  lea     r14, WPP_GLOBAL_Control
0x140008e07  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e0e  cmp     rcx, r14
0x140008e11  jz      short loc_140008E33
0x140008e13  mov     eax, [rcx+6Ch]
0x140008e16  test    al, 4
0x140008e18  jz      short loc_140008E33
0x140008e1a  mov     edx, 0A7h
0x140008e1f  mov     r9, rbx
0x140008e22  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140008e29  mov     rcx, [rcx+58h]
0x140008e2d  call    WPP_SF_q
0x140008e32  nop
0x140008e33  mov     rcx, rbx; struct CQueueBase *
0x140008e36  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140008e3b  mov     edi, eax
0x140008e3d  test    eax, eax
0x140008e3f  jns     short loc_140008E71
0x140008e41  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e48  cmp     rcx, r14
0x140008e4b  jz      short loc_140008E6D
0x140008e4d  mov     edx, [rcx+6Ch]
0x140008e50  test    dl, 1
0x140008e53  jz      short loc_140008E6D
0x140008e55  mov     edx, 0A8h
0x140008e5a  mov     r9, rbx
0x140008e5d  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140008e64  mov     rcx, [rcx+58h]
0x140008e68  call    WPP_SF_q
0x140008e6d  mov     eax, edi
0x140008e6f  jmp     short loc_140008EDD
0x140008e71  mov     edx, 10h; Length
0x140008e76  lea     r8d, [rdx-0Fh]; Alignment
0x140008e7a  mov     rcx, rsi; Address
0x140008e7d  call    cs:__imp_ProbeForRead
0x140008e84  nop     dword ptr [rax+rax+00h]
0x140008e89  mov     ecx, [rsi+8]
0x140008e8c  mov     rax, [rsi]
0x140008e8f  mov     [rbx+148h], rax
0x140008e96  mov     [rbx+140h], ecx
0x140008e9c  xor     eax, eax
0x140008e9e  jmp     short loc_140008EDD
0x140008ea0  mov     ebx, eax
0x140008ea2  lea     rax, WPP_GLOBAL_Control
0x140008ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x140008eb0  cmp     rcx, rax
0x140008eb3  jz      short loc_140008EDB
0x140008eb5  mov     edx, [rcx+6Ch]
0x140008eb8  test    dl, 1
0x140008ebb  jz      short loc_140008EDB
0x140008ebd  mov     edx, 0A9h
0x140008ec2  mov     [rsp+58h+var_38], ebx
0x140008ec6  mov     r9, [rsp+58h+arg_0]
0x140008ecb  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140008ed2  mov     rcx, [rcx+58h]
0x140008ed6  call    WPP_SF_qD
0x140008edb  mov     eax, ebx
0x140008edd  add     rsp, 38h
0x140008ee1  pop     r14
0x140008ee3  pop     rdi
0x140008ee4  pop     rsi
0x140008ee5  pop     rbx
0x140008ee6  retn
```
