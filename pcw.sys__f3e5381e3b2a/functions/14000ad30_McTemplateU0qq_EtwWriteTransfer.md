# McTemplateU0qq_EtwWriteTransfer

- ea: `0x14000ad30`
- end: `0x14000ad94`
- name: `McTemplateU0qq_EtwWriteTransfer`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140009b60`
- `0x140012078`
- `0x140012200`

## callees

- `0x140001370`
- `0x14000acd0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0qq_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-48h] BYREF
  int *v6; // [rsp+40h] [rbp-38h]
  __int64 v7; // [rsp+48h] [rbp-30h]
  int *v8; // [rsp+50h] [rbp-28h]
  __int64 v9; // [rsp+58h] [rbp-20h]
  int v10; // [rsp+90h] [rbp+18h] BYREF
  int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = a4;
  v10 = a3;
  v7 = 4;
  v6 = &v10;
  v9 = 4;
  v8 = &v11;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 3u, &v5);
}

```

## disassembly

```asm
0x14000ad30  mov     r11, rsp
0x14000ad33  mov     [r11+20h], r9d
0x14000ad37  mov     [r11+18h], r8d
0x14000ad3b  sub     rsp, 78h
0x14000ad3f  mov     rax, cs:__security_cookie
0x14000ad46  xor     rax, rsp
0x14000ad49  mov     [rsp+78h+var_18], rax
0x14000ad4e  lea     rax, [r11+18h]
0x14000ad52  mov     qword ptr [r11-30h], 4
0x14000ad5a  mov     [r11-38h], rax
0x14000ad5e  mov     r9d, 3
0x14000ad64  lea     rax, [r11+20h]
0x14000ad68  mov     qword ptr [r11-20h], 4
0x14000ad70  mov     [r11-28h], rax
0x14000ad74  lea     rax, [r11-48h]
0x14000ad78  mov     [r11-58h], rax
0x14000ad7c  call    McGenEventWrite_EtwWriteTransfer
0x14000ad81  mov     rcx, [rsp+78h+var_18]
0x14000ad86  xor     rcx, rsp; StackCookie
0x14000ad89  call    __security_check_cookie
0x14000ad8e  add     rsp, 78h
0x14000ad92  retn
```
