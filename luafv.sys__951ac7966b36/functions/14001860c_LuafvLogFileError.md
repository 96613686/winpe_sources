# LuafvLogFileError

- ea: `0x14001860c`
- end: `0x140018677`
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
- `0x140017cc0`
- `0x140018700`
- `0x140018f70`
- `0x14001fc90`
- `0x140022de8`
- `0x140025350`
- `0x1400258a0`

## callees

- `0x140005f30`
- `0x14001897c`

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
0x14001860c  mov     r11, rsp
0x14001860f  mov     [r11+20h], r9d
0x140018613  sub     rsp, 0D8h
0x14001861a  mov     rax, cs:__security_cookie
0x140018621  xor     rax, rsp
0x140018624  mov     [rsp+0D8h+var_18], rax
0x14001862c  lea     rax, [r11+20h]
0x140018630  mov     [rsp+0D8h+UserDataCount], 8; UserDataCount
0x140018638  mov     [r11-28h], rax
0x14001863c  xor     r9d, r9d; int
0x14001863f  lea     rax, [rsp+0D8h+var_98]
0x140018644  mov     qword ptr [r11-20h], 4
0x14001864c  mov     [rsp+0D8h+var_B0], rax; PEVENT_DATA_DESCRIPTOR
0x140018651  mov     [rsp+0D8h+EventDescriptor], r8; EventDescriptor
0x140018656  xor     r8d, r8d; int
0x140018659  call    LuafvLogFileEvent
0x14001865e  mov     rcx, [rsp+0D8h+var_18]
0x140018666  xor     rcx, rsp; StackCookie
0x140018669  call    __security_check_cookie
0x14001866e  add     rsp, 0D8h
0x140018675  retn
```
