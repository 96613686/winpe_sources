# McTemplateU0dd_EventWriteTransfer

- ea: `0x1800067a0`
- end: `0x180006803`
- name: `McTemplateU0dd_EventWriteTransfer`
- size: `99`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061e0`
- `0x180006240`

## callees

- `0x180001a70`
- `0x180004968`

## pseudocode

```c
ULONG __fastcall McTemplateU0dd_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, int a4)
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
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 3u, &v5);
}

```

## disassembly

```asm
0x1800067a0  mov     r11, rsp
0x1800067a3  mov     [r11+20h], r9d
0x1800067a7  mov     [r11+18h], r8d
0x1800067ab  sub     rsp, 78h
0x1800067af  mov     rax, cs:__security_cookie
0x1800067b6  xor     rax, rsp
0x1800067b9  mov     [rsp+78h+var_18], rax
0x1800067be  lea     rax, [r11+18h]
0x1800067c2  mov     qword ptr [r11-30h], 4
0x1800067ca  mov     [r11-38h], rax
0x1800067ce  mov     r9d, 3
0x1800067d4  lea     rax, [r11+20h]
0x1800067d8  mov     qword ptr [r11-20h], 4
0x1800067e0  mov     [r11-28h], rax
0x1800067e4  lea     rax, [r11-48h]
0x1800067e8  mov     [r11-58h], rax
0x1800067ec  call    McGenEventWrite_EventWriteTransfer
0x1800067f1  mov     rcx, [rsp+78h+var_18]
0x1800067f6  xor     rcx, rsp; StackCookie
0x1800067f9  call    __security_check_cookie
0x1800067fe  add     rsp, 78h
0x180006802  retn
```
