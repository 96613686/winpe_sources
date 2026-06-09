# QuicStreamRemoveOutFlowBlockedReason

- ea: `0x14000d6d0`
- end: `0x14000d79a`
- name: `QuicStreamRemoveOutFlowBlockedReason`
- size: `202`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b3f4`
- `0x14001d238`
- `0x14001da4c`
- `0x140027154`
- `0x14002e87c`

## callees

- `0x14000d6d0`
- `0x140010820`
- `0x14003e884`
- `0x1400426e8`

## pseudocode

```c
char __fastcall QuicStreamRemoveOutFlowBlockedReason(__int64 a1, __int64 a2)
{
  char v2; // di
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  char v7; // r8
  char v8; // di

  v2 = a2;
  if ( ((unsigned __int8)a2 & *(_BYTE *)(a1 + 98)) == 0 )
    return 0;
  v4 = QuicTimePlat(a1, a2);
  v5 = QuicTimePlatToUs64(v4);
  v7 = *(_BYTE *)(a1 + 98);
  if ( (v7 & 0x40) != 0 && (v2 & 0x40) != 0 )
  {
    v6 = v5 - *(_QWORD *)(a1 + 864);
    *(_QWORD *)(a1 + 856) += v6;
    *(_QWORD *)(a1 + 864) = 0;
  }
  if ( v7 < 0 && v2 < 0 )
  {
    *(_QWORD *)(a1 + 872) += v5 - *(_QWORD *)(a1 + 880);
    *(_QWORD *)(a1 + 880) = 0;
  }
  if ( (v7 & 0x20) != 0 && (v2 & 0x20) != 0 )
  {
    *(_QWORD *)(a1 + 840) += v5 - *(_QWORD *)(a1 + 848);
    *(_QWORD *)(a1 + 848) = 0;
  }
  v8 = v7 & ~v2;
  *(_BYTE *)(a1 + 98) = v8;
  if ( (byte_14005C48C & 4) != 0 )
    McTemplateU0pu_EtwWriteTransfer(v6, (const EVENT_DESCRIPTOR *)QuicStreamOutFlowBlocked, a1, v8);
  return 1;
}

```

## disassembly

```asm
0x14000d6d0  mov     [rsp+arg_0], rbx
0x14000d6d5  push    rdi
0x14000d6d6  sub     rsp, 20h
0x14000d6da  mov     edi, edx
0x14000d6dc  mov     rbx, rcx
0x14000d6df  test    [rcx+62h], dl
0x14000d6e2  jz      loc_14000D78C
0x14000d6e8  call    QuicTimePlat
0x14000d6ed  mov     rcx, rax
0x14000d6f0  call    QuicTimePlatToUs64
0x14000d6f5  mov     r8b, [rbx+62h]
0x14000d6f9  xor     r9d, r9d
0x14000d6fc  mov     rdx, rax
0x14000d6ff  test    r8b, 40h
0x14000d703  jz      short loc_14000D723
0x14000d705  test    dil, 40h
0x14000d709  jz      short loc_14000D723
0x14000d70b  mov     rcx, rax
0x14000d70e  sub     rcx, [rbx+360h]
0x14000d715  add     [rbx+358h], rcx
0x14000d71c  mov     [rbx+360h], r9
0x14000d723  test    r8b, r8b
0x14000d726  jns     short loc_14000D742
0x14000d728  test    dil, dil
0x14000d72b  jns     short loc_14000D742
0x14000d72d  sub     rax, [rbx+370h]
0x14000d734  add     [rbx+368h], rax
0x14000d73b  mov     [rbx+370h], r9
0x14000d742  test    r8b, 20h
0x14000d746  jz      short loc_14000D763
0x14000d748  test    dil, 20h
0x14000d74c  jz      short loc_14000D763
0x14000d74e  sub     rdx, [rbx+350h]
0x14000d755  add     [rbx+348h], rdx
0x14000d75c  mov     [rbx+350h], r9
0x14000d763  not     dil
0x14000d766  and     dil, r8b
0x14000d769  mov     [rbx+62h], dil
0x14000d76d  mov     r9b, dil
0x14000d770  test    cs:byte_14005C48C, 4
0x14000d777  jz      short loc_14000D788
0x14000d779  mov     r8, rbx
0x14000d77c  lea     rdx, QuicStreamOutFlowBlocked
0x14000d783  call    McTemplateU0pu_EtwWriteTransfer
0x14000d788  mov     al, 1
0x14000d78a  jmp     short loc_14000D78E
0x14000d78c  xor     al, al
0x14000d78e  mov     rbx, [rsp+28h+arg_0]
0x14000d793  add     rsp, 20h
0x14000d797  pop     rdi
0x14000d798  retn
```
