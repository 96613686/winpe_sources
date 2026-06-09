# ACCreateCursor

- ea: `0x140004cb4`
- end: `0x140004d5b`
- name: `ACCreateCursor`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140003d84`
- `0x140004cb4`
- `0x14000b5d8`
- `0x14001a564`
- `0x140024bf0`

## pseudocode

```c
__int64 __fastcall ACCreateCursor(__int64 a1, __int64 a2, __int64 a3, const struct CQueueBase *a4)
{
  int v7; // eax
  unsigned int v8; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 90, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a4);
  }
  v7 = CQueueBase::Validate(a4);
  v8 = v7;
  if ( v7 >= 0 )
    return (*(__int64 (__fastcall **)(const struct CQueueBase *, __int64, __int64))(*(_QWORD *)a4 + 48LL))(a4, a2, a3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_Dq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      91,
      WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      (unsigned int)v7,
      a4);
  }
  return v8;
}

```

## disassembly

```asm
0x140004cb4  push    rbx
0x140004cb6  push    rbp
0x140004cb7  push    rsi
0x140004cb8  push    rdi
0x140004cb9  push    r14
0x140004cbb  sub     rsp, 30h
0x140004cbf  mov     rdi, r9
0x140004cc2  mov     rsi, r8
0x140004cc5  mov     rbp, rdx
0x140004cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ccf  lea     r14, WPP_GLOBAL_Control
0x140004cd6  cmp     rcx, r14
0x140004cd9  jz      short loc_140004CF7
0x140004cdb  mov     eax, [rcx+6Ch]
0x140004cde  test    al, 4
0x140004ce0  jz      short loc_140004CF7
0x140004ce2  mov     rcx, [rcx+58h]
0x140004ce6  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004ced  mov     edx, 5Ah ; 'Z'
0x140004cf2  call    WPP_SF_q
0x140004cf7  mov     rcx, rdi; struct CQueueBase *
0x140004cfa  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140004cff  mov     ebx, eax
0x140004d01  test    eax, eax
0x140004d03  jns     short loc_140004D3A
0x140004d05  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d0c  cmp     rcx, r14
0x140004d0f  jz      short loc_140004D36
0x140004d11  mov     edx, [rcx+6Ch]
0x140004d14  test    dl, 1
0x140004d17  jz      short loc_140004D36
0x140004d19  mov     rcx, [rcx+58h]
0x140004d1d  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004d24  mov     edx, 5Bh ; '['
0x140004d29  mov     [rsp+58h+var_38], rdi
0x140004d2e  mov     r9d, eax
0x140004d31  call    WPP_SF_Dq
0x140004d36  mov     eax, ebx
0x140004d38  jmp     short loc_140004D4F
0x140004d3a  mov     rax, [rdi]
0x140004d3d  mov     r8, rsi
0x140004d40  mov     rdx, rbp
0x140004d43  mov     rcx, rdi
0x140004d46  mov     rax, [rax+30h]
0x140004d4a  call    _guard_dispatch_icall
0x140004d4f  add     rsp, 30h
0x140004d53  pop     r14
0x140004d55  pop     rdi
0x140004d56  pop     rsi
0x140004d57  pop     rbp
0x140004d58  pop     rbx
0x140004d59  retn
```
