# McTemplateU0p_EtwWriteTransfer

- ea: `0x1400291f0`
- end: `0x140029245`
- name: `McTemplateU0p_EtwWriteTransfer`
- size: `85`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `28`
- callee_count: `2`
- tags: ``

## callers

- `0x14000524c`
- `0x140007b30`
- `0x1400099b4`
- `0x14000f660`
- `0x1400108c0`
- `0x140012630`
- `0x140014d80`
- `0x140017580`
- `0x14001c52c`
- `0x14001f0e0`
- `0x14001f640`
- `0x1400200d8`
- `0x140020880`
- `0x140020a04`
- `0x140022f70`
- `0x1400230c0`
- `0x1400262b4`
- `0x140027154`
- `0x14002bc40`
- `0x14002be60`
- `0x140031228`
- `0x140031440`
- `0x140031b70`
- `0x140032950`
- `0x140032d20`
- `0x14003c178`
- `0x1400436c8`
- `0x1400465f4`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0p_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3)
{
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+30h] [rbp-38h] BYREF
  __int64 *v5; // [rsp+40h] [rbp-28h]
  int v6; // [rsp+48h] [rbp-20h]
  int v7; // [rsp+4Ch] [rbp-1Ch]
  __int64 v8; // [rsp+80h] [rbp+18h] BYREF

  v8 = a3;
  v5 = &v8;
  v7 = 0;
  v6 = 8;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 2u, &v4);
}

```

## disassembly

```asm
0x1400291f0  mov     r11, rsp
0x1400291f3  mov     [r11+18h], r8
0x1400291f7  sub     rsp, 68h
0x1400291fb  mov     rax, cs:__security_cookie
0x140029202  xor     rax, rsp
0x140029205  mov     [rsp+68h+var_18], rax
0x14002920a  lea     rax, [r11+18h]
0x14002920e  mov     r9d, 2
0x140029214  mov     [r11-28h], rax
0x140029218  lea     rax, [r11-38h]
0x14002921c  and     [rsp+68h+var_1C], 0
0x140029221  mov     [r11-48h], rax
0x140029225  mov     [rsp+68h+var_20], 8
0x14002922d  call    McGenEventWrite_EtwWriteTransfer
0x140029232  mov     rcx, [rsp+68h+var_18]
0x140029237  xor     rcx, rsp; StackCookie
0x14002923a  call    __security_check_cookie
0x14002923f  add     rsp, 68h
0x140029243  retn
```
