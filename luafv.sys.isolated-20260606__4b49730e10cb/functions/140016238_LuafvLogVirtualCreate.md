# LuafvLogVirtualCreate

- ea: `0x140016238`
- end: `0x1400162c5`
- name: `LuafvLogVirtualCreate`
- size: `141`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140022de8`
- `0x140025350`

## callees

- `0x140005f30`
- `0x14001897c`
- `0x140024058`

## pseudocode

```c
__int64 __fastcall LuafvLogVirtualCreate(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  UNICODE_STRING **v3; // r11
  struct _FLT_CALLBACK_DATA *v4; // r10
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v7; // [rsp+D0h] [rbp-28h]
  __int64 v8; // [rsp+D8h] [rbp-20h]

  v2 = *(_QWORD *)(a1 + 16) + 4LL;
  v8 = 1;
  v7 = v2;
  LuafvSetFileCreateEvent(a1, a2, &v6);
  return LuafvLogFileEvent(v4, *v3, (__int64)v3, 0, &LuafvVirtualCreateEvent, &v6, 0xAu);
}

```

## disassembly

```asm
0x140016238  sub     rsp, 0F8h
0x14001623f  mov     rax, cs:__security_cookie
0x140016246  xor     rax, rsp
0x140016249  mov     [rsp+0F8h+var_18], rax
0x140016251  mov     rax, [rcx+10h]
0x140016255  lea     r8, [rsp+0F8h+var_B8]
0x14001625a  add     rax, 4
0x14001625e  mov     [rsp+0F8h+var_20], 1
0x14001626a  mov     [rsp+0F8h+var_28], rax
0x140016272  mov     r11, rdx
0x140016275  mov     r10, rcx
0x140016278  call    LuafvSetFileCreateEvent
0x14001627d  mov     rdx, [r11]; int
0x140016280  lea     rax, [rsp+0F8h+var_B8]
0x140016285  mov     [rsp+0F8h+UserDataCount], 0Ah; UserDataCount
0x14001628d  xor     r9d, r9d; int
0x140016290  mov     [rsp+0F8h+var_D0], rax; PEVENT_DATA_DESCRIPTOR
0x140016295  mov     r8, r11; int
0x140016298  lea     rax, LuafvVirtualCreateEvent
0x14001629f  mov     rcx, r10; int
0x1400162a2  mov     [rsp+0F8h+EventDescriptor], rax; EventDescriptor
0x1400162a7  call    LuafvLogFileEvent
0x1400162ac  mov     rcx, [rsp+0F8h+var_18]
0x1400162b4  xor     rcx, rsp; StackCookie
0x1400162b7  call    __security_check_cookie
0x1400162bc  add     rsp, 0F8h
0x1400162c3  retn
```
