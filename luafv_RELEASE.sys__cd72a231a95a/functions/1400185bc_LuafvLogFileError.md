# LuafvLogFileError

- ea: `0x1400185bc`
- end: `0x140018627`
- name: `LuafvLogFileError`
- size: `107`
- prototype: `__int64 __fastcall(int, int, const EVENT_DESCRIPTOR *EventDescriptor, int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x140001440`
- `0x140015388`
- `0x1400157d4`
- `0x140017c70`
- `0x1400186b0`
- `0x140018f20`
- `0x14001fc40`
- `0x140022d98`
- `0x140025300`
- `0x140025820`

## callees

- `0x140005bb0`
- `0x14001892c`

## pseudocode

```c
__int64 __fastcall LuafvLogFileError(int a1, int a2, const EVENT_DESCRIPTOR *EventDescriptor, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+40h] [rbp-98h] BYREF
  int *v6; // [rsp+B0h] [rbp-28h]
  __int64 v7; // [rsp+B8h] [rbp-20h]
  int v8; // [rsp+F8h] [rbp+20h] BYREF

  v8 = a4;
  v6 = &v8;
  v7 = 4;
  return LuafvLogFileEvent(a1, a2, 0, 0, EventDescriptor, &v5, 8u);
}

```

## disassembly

```asm
0x1400185bc  mov     r11, rsp
0x1400185bf  mov     [r11+20h], r9d
0x1400185c3  sub     rsp, 0D8h
0x1400185ca  mov     rax, cs:__security_cookie
0x1400185d1  xor     rax, rsp
0x1400185d4  mov     [rsp+0D8h+var_18], rax
0x1400185dc  lea     rax, [r11+20h]
0x1400185e0  mov     [rsp+0D8h+UserDataCount], 8; UserDataCount
0x1400185e8  mov     [r11-28h], rax
0x1400185ec  xor     r9d, r9d; int
0x1400185ef  lea     rax, [rsp+0D8h+var_98]
0x1400185f4  mov     qword ptr [r11-20h], 4
0x1400185fc  mov     [rsp+0D8h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x140018601  mov     [rsp+0D8h+EventDescriptor], r8; EventDescriptor
0x140018606  xor     r8d, r8d; int
0x140018609  call    LuafvLogFileEvent
0x14001860e  mov     rcx, [rsp+0D8h+var_18]
0x140018616  xor     rcx, rsp; StackCookie
0x140018619  call    __security_check_cookie
0x14001861e  add     rsp, 0D8h
0x140018625  retn
```
