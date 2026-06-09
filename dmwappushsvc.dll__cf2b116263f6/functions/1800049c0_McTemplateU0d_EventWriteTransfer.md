# McTemplateU0d_EventWriteTransfer

- ea: `0x1800049c0`
- end: `0x180004a0f`
- name: `McTemplateU0d_EventWriteTransfer`
- size: `79`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180003764`
- `0x180003808`
- `0x180003d3c`
- `0x180003e90`
- `0x180004ab4`
- `0x180005a1c`
- `0x180006124`
- `0x180006430`

## callees

- `0x180001a70`
- `0x180004968`

## pseudocode

```c
ULONG __fastcall McTemplateU0d_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  int *v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = a3;
  v6 = 4;
  v5 = &v7;
  return McGenEventWrite_EventWriteTransfer(a1, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x1800049c0  mov     r11, rsp
0x1800049c3  mov     [r11+18h], r8d
0x1800049c7  sub     rsp, 68h
0x1800049cb  mov     rax, cs:__security_cookie
0x1800049d2  xor     rax, rsp
0x1800049d5  mov     [rsp+68h+var_18], rax
0x1800049da  lea     rax, [r11+18h]
0x1800049de  mov     qword ptr [r11-20h], 4
0x1800049e6  mov     [r11-28h], rax
0x1800049ea  mov     r9d, 2
0x1800049f0  lea     rax, [r11-38h]
0x1800049f4  mov     [r11-48h], rax
0x1800049f8  call    McGenEventWrite_EventWriteTransfer
0x1800049fd  mov     rcx, [rsp+68h+var_18]
0x180004a02  xor     rcx, rsp; StackCookie
0x180004a05  call    __security_check_cookie
0x180004a0a  add     rsp, 68h
0x180004a0e  retn
```
