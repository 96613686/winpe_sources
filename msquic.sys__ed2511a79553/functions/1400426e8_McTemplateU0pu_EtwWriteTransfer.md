# McTemplateU0pu_EtwWriteTransfer

- ea: `0x1400426e8`
- end: `0x140042756`
- name: `McTemplateU0pu_EtwWriteTransfer`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x1400099b4`
- `0x14000a6f0`
- `0x14000b3f4`
- `0x14000ca70`
- `0x14000d6d0`
- `0x140014630`
- `0x140016210`
- `0x1400183d0`
- `0x14001d88c`
- `0x1400211bc`
- `0x1400216cc`
- `0x1400217f0`
- `0x140022dfc`
- `0x140026530`
- `0x14002e9ac`
- `0x140030670`
- `0x140031228`
- `0x140032d20`
- `0x140045264`
- `0x1400456a4`
- `0x140046774`
- `0x140049624`
- `0x1400498dc`

## callees

- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0pu_EtwWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, __int64 a3, char a4)
{
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v6; // [rsp+40h] [rbp-38h]
  int v7; // [rsp+48h] [rbp-30h]
  int v8; // [rsp+4Ch] [rbp-2Ch]
  char *v9; // [rsp+50h] [rbp-28h]
  int v10; // [rsp+58h] [rbp-20h]
  int v11; // [rsp+5Ch] [rbp-1Ch]
  __int64 v12; // [rsp+90h] [rbp+18h] BYREF
  char v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  v12 = a3;
  v6 = &v12;
  v8 = 0;
  v7 = 8;
  v9 = &v13;
  v11 = 0;
  v10 = 1;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 3u, &v5);
}

```

## disassembly

```asm
0x1400426e8  mov     r11, rsp
0x1400426eb  mov     [r11+20h], r9b
0x1400426ef  mov     [r11+18h], r8
0x1400426f3  sub     rsp, 78h
0x1400426f7  mov     rax, cs:__security_cookie
0x1400426fe  xor     rax, rsp
0x140042701  mov     [rsp+78h+var_18], rax
0x140042706  lea     rax, [r11+18h]
0x14004270a  mov     r9d, 3
0x140042710  mov     [r11-38h], rax
0x140042714  lea     rax, [r11+20h]
0x140042718  and     [rsp+78h+var_2C], 0
0x14004271d  mov     [rsp+78h+var_30], 8
0x140042725  mov     [r11-28h], rax
0x140042729  lea     rax, [r11-48h]
0x14004272d  and     [rsp+78h+var_1C], 0
0x140042732  mov     [r11-58h], rax
0x140042736  mov     [rsp+78h+var_20], 1
0x14004273e  call    McGenEventWrite_EtwWriteTransfer
0x140042743  mov     rcx, [rsp+78h+var_18]
0x140042748  xor     rcx, rsp; StackCookie
0x14004274b  call    __security_check_cookie
0x140042750  add     rsp, 78h
0x140042754  retn
```
