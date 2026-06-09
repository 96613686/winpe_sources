# McTemplateU0qttx_EventWriteTransfer

- ea: `0x1800163cc`
- end: `0x180016461`
- name: `McTemplateU0qttx_EventWriteTransfer`
- size: `149`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, int, char, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180016678`
- `0x180016798`

## callees

- `0x180004c2c`
- `0x18001cc70`

## pseudocode

```c
ULONG __fastcall McTemplateU0qttx_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, char a5, char a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+38h] [rbp-19h] BYREF
  int *v8; // [rsp+48h] [rbp-9h]
  __int64 v9; // [rsp+50h] [rbp-1h]
  int *v10; // [rsp+58h] [rbp+7h]
  __int64 v11; // [rsp+60h] [rbp+Fh]
  char *v12; // [rsp+68h] [rbp+17h]
  __int64 v13; // [rsp+70h] [rbp+1Fh]
  char *v14; // [rsp+78h] [rbp+27h]
  __int64 v15; // [rsp+80h] [rbp+2Fh]
  int v16; // [rsp+B8h] [rbp+67h] BYREF
  int v17; // [rsp+C0h] [rbp+6Fh] BYREF

  v17 = a4;
  v16 = a3;
  v9 = 4;
  v8 = &v16;
  v11 = 4;
  v10 = &v17;
  v13 = 4;
  v12 = &a5;
  v14 = &a6;
  v15 = 8;
  return McGenEventWrite_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)EvCollUpdate, a3, 5u, &v7);
}

```

## disassembly

```asm
0x1800163cc  mov     r11, rsp
0x1800163cf  mov     [r11+20h], r9d
0x1800163d3  mov     [r11+18h], r8d
0x1800163d7  push    rbp
0x1800163d8  lea     rbp, [r11-4Fh]
0x1800163dc  sub     rsp, 90h
0x1800163e3  mov     rax, cs:__security_cookie
0x1800163ea  xor     rax, rsp
0x1800163ed  mov     [rbp+47h+var_10], rax
0x1800163f1  lea     rax, [rbp+47h+arg_10]
0x1800163f5  mov     [rbp+47h+var_48], 4
0x1800163fd  mov     [rbp+47h+var_50], rax
0x180016401  lea     rdx, EvCollUpdate
0x180016408  lea     rax, [rbp+47h+arg_18]
0x18001640c  mov     [rbp+47h+var_38], 4
0x180016414  mov     [rbp+47h+var_40], rax
0x180016418  mov     r9d, 5
0x18001641e  lea     rax, [rbp+47h+arg_20]
0x180016422  mov     [rbp+47h+var_28], 4
0x18001642a  mov     [rbp+47h+var_30], rax
0x18001642e  lea     rax, [rbp+47h+arg_28]
0x180016432  mov     [rbp+47h+var_20], rax
0x180016436  lea     rax, [rbp+47h+var_60]
0x18001643a  mov     [r11-78h], rax
0x18001643e  mov     [rbp+47h+var_18], 8
0x180016446  call    McGenEventWrite_EventWriteTransfer
0x18001644b  mov     rcx, [rbp+47h+var_10]
0x18001644f  xor     rcx, rsp; StackCookie
0x180016452  call    __security_check_cookie
0x180016457  add     rsp, 90h
0x18001645e  pop     rbp
0x18001645f  retn
```
