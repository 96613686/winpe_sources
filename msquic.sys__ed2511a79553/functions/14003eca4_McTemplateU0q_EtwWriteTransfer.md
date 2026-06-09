# McTemplateU0q_EtwWriteTransfer

- ea: `0x14003eca4`
- end: `0x14003ecf9`
- name: `McTemplateU0q_EtwWriteTransfer`
- size: `85`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010b0`
- `0x1400018a0`
- `0x140002840`
- `0x14000af30`
- `0x14000b850`
- `0x14000bf30`
- `0x140020010`
- `0x140021b60`
- `0x140022710`
- `0x140023350`
- `0x1400258c0`
- `0x140026600`
- `0x140026770`
- `0x140028a3c`
- `0x140029810`
- `0x140029970`
- `0x140029a60`
- `0x140029bb0`
- `0x14002db50`
- `0x14003faf0`
- `0x140040e60`
- `0x1400410d0`
- `0x1400413f0`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0q_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  int *v5; // [rsp+40h] [rbp-28h]
  int v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+4Ch] [rbp-1Ch]
  int v8; // [rsp+80h] [rbp+18h] BYREF

  v8 = a3;
  v5 = &v8;
  v7 = 0;
  v6 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x14003eca4  mov     r11, rsp
0x14003eca7  mov     [r11+18h], r8d
0x14003ecab  sub     rsp, 68h
0x14003ecaf  mov     rax, cs:__security_cookie
0x14003ecb6  xor     rax, rsp
0x14003ecb9  mov     [rsp+68h+var_18], rax
0x14003ecbe  lea     rax, [r11+18h]
0x14003ecc2  mov     r9d, 2
0x14003ecc8  mov     [r11-28h], rax
0x14003eccc  lea     rax, [r11-38h]
0x14003ecd0  and     [rsp+68h+var_1C], 0
0x14003ecd5  mov     [r11-48h], rax
0x14003ecd9  mov     [rsp+68h+var_20], 4
0x14003ece1  call    McGenEventWrite_EtwWriteTransfer
0x14003ece6  mov     rcx, [rsp+68h+var_18]
0x14003eceb  xor     rcx, rsp; StackCookie
0x14003ecee  call    __security_check_cookie
0x14003ecf3  add     rsp, 68h
0x14003ecf7  retn
```
