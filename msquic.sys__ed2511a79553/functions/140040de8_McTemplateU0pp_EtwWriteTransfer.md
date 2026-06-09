# McTemplateU0pp_EtwWriteTransfer

- ea: `0x140040de8`
- end: `0x140040e51`
- name: `McTemplateU0pp_EtwWriteTransfer`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x140003b60`
- `0x140008338`
- `0x14000a6f0`
- `0x14000bad0`
- `0x140015480`
- `0x140018050`
- `0x1400258c0`
- `0x140026770`
- `0x140027154`
- `0x14002b964`
- `0x140040908`
- `0x140040ca8`
- `0x140041220`
- `0x1400436c8`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS McTemplateU0pp_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, ...)
{
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+30h] [rbp-48h] BYREF
  va_list v4; // [rsp+40h] [rbp-38h]
  int v5; // [rsp+48h] [rbp-30h]
  int v6; // [rsp+4Ch] [rbp-2Ch]
  va_list v7; // [rsp+50h] [rbp-28h]
  int v8; // [rsp+58h] [rbp-20h]
  int v9; // [rsp+5Ch] [rbp-1Ch]
  va_list va; // [rsp+90h] [rbp+18h]
  __int64 v11; // [rsp+90h] [rbp+18h] BYREF
  va_list va1; // [rsp+98h] [rbp+20h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v11 = va_arg(va1, _QWORD);
  va_copy(v4, va);
  v6 = 0;
  v5 = 8;
  va_copy(v7, va1);
  v9 = 0;
  v8 = 8;
  return McGenEventWrite_EtwWriteTransfer(8, a2, v11, 3u, &v3);
}

```

## disassembly

```asm
0x140040de8  mov     r11, rsp
0x140040deb  mov     [r11+20h], r9
0x140040def  mov     [r11+18h], r8
0x140040df3  sub     rsp, 78h
0x140040df7  mov     rax, cs:__security_cookie
0x140040dfe  xor     rax, rsp
0x140040e01  mov     [rsp+78h+var_18], rax
0x140040e06  mov     ecx, 8
0x140040e0b  lea     rax, [r11+18h]
0x140040e0f  mov     [r11-38h], rax
0x140040e13  lea     rax, [r11+20h]
0x140040e17  and     [rsp+78h+var_2C], 0
0x140040e1c  mov     [rsp+78h+var_30], ecx
0x140040e20  mov     [r11-28h], rax
0x140040e24  lea     r9d, [rcx-5]
0x140040e28  and     [rsp+78h+var_1C], 0
0x140040e2d  lea     rax, [r11-48h]
0x140040e31  mov     [r11-58h], rax
0x140040e35  mov     [rsp+78h+var_20], ecx
0x140040e39  call    McGenEventWrite_EtwWriteTransfer
0x140040e3e  mov     rcx, [rsp+78h+var_18]
0x140040e43  xor     rcx, rsp; StackCookie
0x140040e46  call    __security_check_cookie
0x140040e4b  add     rsp, 78h
0x140040e4f  retn
```
