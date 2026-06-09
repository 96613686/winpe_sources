# PcpTraceLineUpDownEvent

- ea: `0x14000287c`
- end: `0x140002985`
- name: `PcpTraceLineUpDownEvent`
- size: `265`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140001010`
- `0x1400010e0`
- `0x1400029d0`
- `0x14000eca0`
- `0x14000ee88`
- `0x140020810`

## callees

- `0x14000287c`
- `0x140011670`

## pseudocode

```c
void __fastcall PcpTraceLineUpDownEvent(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, int a7)
{
  __int64 *v8; // rcx

  if ( PcgEventTraceEnabled )
  {
    v8 = QOS_EVENT_PACER_START;
    if ( a7 >= 16 )
      v8 = QOS_EVENT_PACER_STOP;
    PcpEtwWriteEventUlongPtr((const EVENT_DESCRIPTOR *)v8, 0, 0, 7u, a1);
  }
}

```

## disassembly

```asm
0x14000287c  mov     r11, rsp
0x14000287f  mov     [r11+8], rbx
0x140002883  mov     [rsp+arg_8], edx
0x140002887  push    rdi
0x140002888  sub     rsp, 0A0h
0x14000288f  mov     eax, cs:PcgEventTraceEnabled
0x140002895  mov     r10, rcx
0x140002898  test    eax, eax
0x14000289a  jz      loc_140002973
0x1400028a0  mov     edx, [rsp+0A8h+arg_28]
0x1400028a7  lea     rcx, ?EmptyString@?1??PcpTraceLineUpDownEvent@@9@9; `PcpTraceLineUpDownEvent'::`2'::EmptyString
0x1400028ae  mov     eax, r9d
0x1400028b1  mov     edi, 7
0x1400028b6  shr     eax, 1
0x1400028b8  mov     [r11-14h], eax
0x1400028bc  mov     eax, edx
0x1400028be  shr     eax, 1
0x1400028c0  mov     [r11-18h], eax
0x1400028c4  lea     ebx, [rdi-3]
0x1400028c7  mov     rax, [rsp+0A8h+arg_20]
0x1400028cf  lea     r11, QOS_EVENT_PACER_STOP
0x1400028d6  mov     [rsp+0A8h+var_20], rbx
0x1400028de  test    rax, rax
0x1400028e1  cmovz   rax, rcx
0x1400028e5  test    r8, r8
0x1400028e8  cmovz   r8, rcx
0x1400028ec  cmp     [rsp+0A8h+arg_30], 10h
0x1400028f4  lea     rcx, QOS_EVENT_PACER_START
0x1400028fb  cmovge  rcx, r11
0x1400028ff  lea     r11, [rsp+0A8h+arg_30]
0x140002907  mov     [rsp+0A8h+var_28], r11
0x14000290f  mov     [rsp+0A8h+var_30], edx
0x140002913  xor     edx, edx
0x140002915  mov     [rsp+0A8h+var_38], rax
0x14000291a  lea     rax, [rsp+0A8h+var_18]
0x140002922  mov     [rsp+0A8h+var_40], rbx
0x140002927  mov     [rsp+0A8h+var_48], rax
0x14000292c  lea     rax, [rsp+0A8h+var_14]
0x140002934  mov     [rsp+0A8h+var_50], r9d
0x140002939  mov     r9d, edi
0x14000293c  mov     [rsp+0A8h+var_58], r8
0x140002941  xor     r8d, r8d
0x140002944  mov     [rsp+0A8h+var_60], rbx
0x140002949  mov     [rsp+0A8h+var_68], rax
0x14000294e  lea     rax, [rsp+0A8h+arg_8]
0x140002956  mov     [rsp+0A8h+var_70], rbx
0x14000295b  mov     [rsp+0A8h+var_78], rax
0x140002960  mov     [rsp+0A8h+var_80], 8
0x140002969  mov     [rsp+0A8h+var_88], r10
0x14000296e  call    PcpEtwWriteEventUlongPtr
0x140002973  mov     rbx, [rsp+0A8h+arg_0]
0x14000297b  add     rsp, 0A0h
0x140002982  pop     rdi
0x140002983  retn
```
