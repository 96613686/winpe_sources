# McTemplateK0qp_EtwWriteTransfer

- ea: `0x14000c14c`
- end: `0x14000c1af`
- name: `McTemplateK0qp_EtwWriteTransfer`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140005454`
- `0x1400072cc`

## callees

- `0x140004300`
- `0x140010f20`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qp_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  int *v7; // [rsp+40h] [rbp-38h]
  __int64 v8; // [rsp+48h] [rbp-30h]
  __int64 *v9; // [rsp+50h] [rbp-28h]
  __int64 v10; // [rsp+58h] [rbp-20h]
  int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = a4;
  v8 = 4;
  v7 = &v11;
  v10 = 8;
  v9 = &a5;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, 0, 3u, &v6);
}

```

## disassembly

```asm
0x14000c14c  mov     r11, rsp
0x14000c14f  mov     [r11+20h], r9d
0x14000c153  sub     rsp, 78h
0x14000c157  mov     rax, cs:__security_cookie
0x14000c15e  xor     rax, rsp
0x14000c161  mov     [rsp+78h+var_18], rax
0x14000c166  lea     rax, [r11+20h]
0x14000c16a  mov     qword ptr [r11-30h], 4
0x14000c172  mov     [r11-38h], rax
0x14000c176  mov     r9d, 3
0x14000c17c  lea     rax, [r11+28h]
0x14000c180  mov     qword ptr [r11-20h], 8
0x14000c188  mov     [r11-28h], rax
0x14000c18c  xor     r8d, r8d
0x14000c18f  lea     rax, [r11-48h]
0x14000c193  mov     [r11-58h], rax
0x14000c197  call    McGenEventWrite_EtwWriteTransfer
0x14000c19c  mov     rcx, [rsp+78h+var_18]
0x14000c1a1  xor     rcx, rsp; StackCookie
0x14000c1a4  call    __security_check_cookie
0x14000c1a9  add     rsp, 78h
0x14000c1ad  retn
```
