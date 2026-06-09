# McTemplateK0qq_EtwWriteTransfer

- ea: `0x14000c238`
- end: `0x14000c298`
- name: `McTemplateK0qq_EtwWriteTransfer`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140020778`
- `0x140020ba8`
- `0x140024f44`

## callees

- `0x140004300`
- `0x140010f20`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qq_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
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
  v10 = 4;
  v9 = &a5;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 3u, &v6);
}

```

## disassembly

```asm
0x14000c238  mov     r11, rsp
0x14000c23b  mov     [r11+20h], r9d
0x14000c23f  sub     rsp, 78h
0x14000c243  mov     rax, cs:__security_cookie
0x14000c24a  xor     rax, rsp
0x14000c24d  mov     [rsp+78h+var_18], rax
0x14000c252  lea     rax, [r11+20h]
0x14000c256  mov     qword ptr [r11-30h], 4
0x14000c25e  mov     [r11-38h], rax
0x14000c262  mov     r9d, 3
0x14000c268  lea     rax, [r11+28h]
0x14000c26c  mov     qword ptr [r11-20h], 4
0x14000c274  mov     [r11-28h], rax
0x14000c278  lea     rax, [r11-48h]
0x14000c27c  mov     [r11-58h], rax
0x14000c280  call    McGenEventWrite_EtwWriteTransfer
0x14000c285  mov     rcx, [rsp+78h+var_18]
0x14000c28a  xor     rcx, rsp; StackCookie
0x14000c28d  call    __security_check_cookie
0x14000c292  add     rsp, 78h
0x14000c296  retn
```
