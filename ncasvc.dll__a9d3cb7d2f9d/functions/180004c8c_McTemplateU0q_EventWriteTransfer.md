# McTemplateU0q_EventWriteTransfer

- ea: `0x180004c8c`
- end: `0x180004ce3`
- name: `McTemplateU0q_EventWriteTransfer`
- size: `87`
- prototype: `ULONG __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024b0`
- `0x1800026d0`

## callees

- `0x180004c2c`
- `0x18001cc70`

## pseudocode

```c
ULONG __fastcall McTemplateU0q_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  int *v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = a3;
  v6 = 4;
  v5 = &v7;
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)StatusChanged, a3, 2u, &v4);
}

```

## disassembly

```asm
0x180004c8c  mov     r11, rsp
0x180004c8f  mov     [r11+18h], r8d
0x180004c93  sub     rsp, 68h
0x180004c97  mov     rax, cs:__security_cookie
0x180004c9e  xor     rax, rsp
0x180004ca1  mov     [rsp+68h+var_18], rax
0x180004ca6  lea     rax, [r11+18h]
0x180004caa  mov     qword ptr [r11-20h], 4
0x180004cb2  mov     [r11-28h], rax
0x180004cb6  lea     rdx, StatusChanged
0x180004cbd  lea     rax, [r11-38h]
0x180004cc1  mov     r9d, 2
0x180004cc7  mov     [r11-48h], rax
0x180004ccb  call    McGenEventWrite_EventWriteTransfer
0x180004cd0  mov     rcx, [rsp+68h+var_18]
0x180004cd5  xor     rcx, rsp; StackCookie
0x180004cd8  call    __security_check_cookie
0x180004cdd  add     rsp, 68h
0x180004ce1  retn
```
