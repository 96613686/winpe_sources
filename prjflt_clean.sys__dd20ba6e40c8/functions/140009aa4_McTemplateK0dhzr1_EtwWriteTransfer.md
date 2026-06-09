# McTemplateK0dhzr1_EtwWriteTransfer

- ea: `0x140009aa4`
- end: `0x140009b25`
- name: `McTemplateK0dhzr1_EtwWriteTransfer`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003f240`

## callees

- `0x140004100`
- `0x14000ba20`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0dhzr1_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int16 a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-50h] BYREF
  int *v8; // [rsp+40h] [rbp-40h]
  __int64 v9; // [rsp+48h] [rbp-38h]
  unsigned __int16 *v10; // [rsp+50h] [rbp-30h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  __int64 v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+68h] [rbp-18h]
  int v14; // [rsp+6Ch] [rbp-14h]
  int v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v11 = 2;
  v8 = &v15;
  v10 = &a5;
  v12 = a6;
  v9 = 4;
  v13 = 2 * a5;
  v14 = 0;
  return McGenEventWrite_EtwWriteTransfer(0, &ProjFsInstanceAttachFailure, a3, 4u, &v7);
}

```

## disassembly

```asm
0x140009aa4  mov     [rsp-8+arg_18], r9d
0x140009aa9  push    rbp
0x140009aaa  mov     rbp, rsp
0x140009aad  sub     rsp, 80h
0x140009ab4  mov     rax, cs:__security_cookie
0x140009abb  xor     rax, rsp
0x140009abe  mov     [rbp+var_10], rax
0x140009ac2  lea     rax, [rbp+arg_18]
0x140009ac6  mov     [rbp+var_28], 2
0x140009ace  mov     [rbp+var_40], rax
0x140009ad2  lea     rdx, ProjFsInstanceAttachFailure
0x140009ad9  lea     rax, [rbp+arg_20]
0x140009add  mov     r9d, 4
0x140009ae3  mov     [rbp+var_30], rax
0x140009ae7  xor     ecx, ecx
0x140009ae9  mov     rax, [rbp+arg_28]
0x140009aed  mov     [rbp+var_20], rax
0x140009af1  movzx   eax, [rbp+arg_20]
0x140009af5  add     eax, eax
0x140009af7  mov     [rbp+var_38], r9
0x140009afb  mov     [rbp+var_18], eax
0x140009afe  lea     rax, [rbp+var_50]
0x140009b02  mov     [rsp+80h+var_60], rax
0x140009b07  mov     [rbp+var_14], ecx
0x140009b0a  call    McGenEventWrite_EtwWriteTransfer
0x140009b0f  mov     rcx, [rbp+var_10]
0x140009b13  xor     rcx, rsp; StackCookie
0x140009b16  call    __security_check_cookie
0x140009b1b  add     rsp, 80h
0x140009b22  pop     rbp
0x140009b23  retn
```
