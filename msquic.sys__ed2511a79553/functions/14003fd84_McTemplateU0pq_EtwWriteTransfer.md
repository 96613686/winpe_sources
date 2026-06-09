# McTemplateU0pq_EtwWriteTransfer

- ea: `0x14003fd84`
- end: `0x14003fdf2`
- name: `McTemplateU0pq_EtwWriteTransfer`
- size: `110`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x140005184`
- `0x14000c5b0`
- `0x14000ca70`
- `0x14000d230`
- `0x14000d490`
- `0x14000d638`
- `0x14000edc0`
- `0x140013b30`
- `0x140014d80`
- `0x140016210`
- `0x1400211bc`
- `0x140022528`
- `0x14002e380`
- `0x14002e654`
- `0x1400401b4`
- `0x1400436c8`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0pq_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, int a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v6; // [rsp+40h] [rbp-38h]
  int v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+4Ch] [rbp-2Ch]
  int *v9; // [rsp+50h] [rbp-28h]
  int v10; // [rsp+58h] [rbp-20h]
  int v11; // [rsp+5Ch] [rbp-1Ch]
  __int64 v12; // [rsp+90h] [rbp+18h] BYREF
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  v12 = a3;
  v6 = &v12;
  v8 = 0;
  v7 = 8;
  v9 = &v13;
  v11 = 0;
  v10 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 3u, &v5);
}

```

## disassembly

```asm
0x14003fd84  mov     r11, rsp
0x14003fd87  mov     [r11+20h], r9d
0x14003fd8b  mov     [r11+18h], r8
0x14003fd8f  sub     rsp, 78h
0x14003fd93  mov     rax, cs:__security_cookie
0x14003fd9a  xor     rax, rsp
0x14003fd9d  mov     [rsp+78h+var_18], rax
0x14003fda2  lea     rax, [r11+18h]
0x14003fda6  mov     r9d, 3
0x14003fdac  mov     [r11-38h], rax
0x14003fdb0  lea     rax, [r11+20h]
0x14003fdb4  and     [rsp+78h+var_2C], 0
0x14003fdb9  mov     [rsp+78h+var_30], 8
0x14003fdc1  mov     [r11-28h], rax
0x14003fdc5  lea     rax, [r11-48h]
0x14003fdc9  and     [rsp+78h+var_1C], 0
0x14003fdce  mov     [r11-58h], rax
0x14003fdd2  mov     [rsp+78h+var_20], 4
0x14003fdda  call    McGenEventWrite_EtwWriteTransfer
0x14003fddf  mov     rcx, [rsp+78h+var_18]
0x14003fde4  xor     rcx, rsp; StackCookie
0x14003fde7  call    __security_check_cookie
0x14003fdec  add     rsp, 78h
0x14003fdf0  retn
```
