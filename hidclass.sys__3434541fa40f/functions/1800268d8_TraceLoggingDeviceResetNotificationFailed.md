# TraceLoggingDeviceResetNotificationFailed

- ea: `0x1800268d8`
- end: `0x1800269d1`
- name: `TraceLoggingDeviceResetNotificationFailed`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180025f64`

## callees

- `0x180013f44`
- `0x1800142c4`
- `0x180019664`
- `0x1800268d8`
- `0x180027ba0`

## string_xrefs

- `0x18002695a`: `Device being removed`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingDeviceResetNotificationFailed(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v2; // r8
  __int16 v3; // ax
  __int16 v4; // ax
  __int16 v5; // [rsp+30h] [rbp-29h] BYREF
  __int16 v6; // [rsp+34h] [rbp-25h] BYREF
  int v7; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-19h] BYREF
  __int16 *v9; // [rsp+60h] [rbp+7h]
  __int64 v10; // [rsp+68h] [rbp+Fh]
  __int16 *v11; // [rsp+70h] [rbp+17h]
  __int64 v12; // [rsp+78h] [rbp+1Fh]
  int *v13; // [rsp+80h] [rbp+27h]
  __int64 v14; // [rsp+88h] [rbp+2Fh]
  _BYTE v15[16]; // [rsp+90h] [rbp+37h] BYREF

  result = dword_1800310D8;
  if ( (unsigned int)dword_1800310D8 > 5 )
  {
    result = tlgKeywordOn(&dword_1800310D8, 0x400000000000LL, a1);
    if ( (_BYTE)result )
    {
      if ( v2 )
        v3 = *(_WORD *)(v2 + 108);
      else
        v3 = 0;
      v5 = v3;
      v9 = &v5;
      v10 = 2;
      if ( v2 )
        v4 = *(_WORD *)(v2 + 110);
      else
        v4 = 0;
      v6 = v4;
      v12 = 2;
      v11 = &v6;
      v7 = -1073741823;
      v13 = &v7;
      v14 = 4;
      tlgCreate1Sz_char(v15, "Device being removed");
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_1800310D8,
               (unsigned __int8 *)&dword_18002D424,
               0,
               0,
               6u,
               &v8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800268d8  push    rbp
0x1800268da  lea     rbp, [rsp-57h]
0x1800268df  sub     rsp, 0B0h
0x1800268e6  mov     rax, cs:__security_cookie
0x1800268ed  xor     rax, rsp
0x1800268f0  mov     [rbp+57h+var_10], rax
0x1800268f4  mov     eax, cs:dword_1800310D8
0x1800268fa  mov     r8, rcx
0x1800268fd  cmp     eax, 5
0x180026900  jbe     loc_1800269BB
0x180026906  mov     rdx, 400000000000h
0x180026910  lea     rcx, dword_1800310D8
0x180026917  call    _tlgKeywordOn
0x18002691c  xor     ecx, ecx
0x18002691e  test    al, al
0x180026920  jz      loc_1800269BB
0x180026926  test    r8, r8
0x180026929  jz      short loc_180026932
0x18002692b  movzx   eax, word ptr [r8+6Ch]
0x180026930  jmp     short loc_180026934
0x180026932  mov     eax, ecx
0x180026934  mov     [rbp+57h+var_80], ax
0x180026938  lea     rax, [rbp+57h+var_80]
0x18002693c  mov     [rbp+57h+var_50], rax
0x180026940  mov     [rbp+57h+var_48], 2
0x180026948  test    r8, r8
0x18002694b  jz      short loc_180026954
0x18002694d  movzx   eax, word ptr [r8+6Eh]
0x180026952  jmp     short loc_180026956
0x180026954  mov     eax, ecx
0x180026956  mov     [rbp+57h+var_7C], ax
0x18002695a  lea     rdx, aDeviceBeingRem; "Device being removed"
0x180026961  lea     rax, [rbp+57h+var_7C]
0x180026965  mov     [rbp+57h+var_38], 2
0x18002696d  mov     [rbp+57h+var_40], rax
0x180026971  lea     rcx, [rbp+57h+var_20]
0x180026975  lea     rax, [rbp+57h+var_78]
0x180026979  mov     [rbp+57h+var_78], 0C0000001h
0x180026980  mov     [rbp+57h+var_30], rax
0x180026984  mov     [rbp+57h+var_28], 4
0x18002698c  call    _tlgCreate1Sz_char
0x180026991  lea     r8, [rbp+57h+var_70]
0x180026995  xor     r9d, r9d
0x180026998  mov     [rsp+0B0h+var_88], r8
0x18002699d  lea     rdx, dword_18002D424
0x1800269a4  xor     r8d, r8d
0x1800269a7  mov     [rsp+0B0h+var_90], 6
0x1800269af  lea     rcx, dword_1800310D8
0x1800269b6  call    _tlgWriteTransfer_EtwWriteTransfer
0x1800269bb  mov     rcx, [rbp+57h+var_10]
0x1800269bf  xor     rcx, rsp; StackCookie
0x1800269c2  call    __security_check_cookie
0x1800269c7  add     rsp, 0B0h
0x1800269ce  pop     rbp
0x1800269cf  retn
```
