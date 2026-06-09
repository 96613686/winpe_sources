# McTemplateK0qqqbr2_EtwWriteTransfer

- ea: `0x140004860`
- end: `0x1400048f2`
- name: `McTemplateK0qqqbr2_EtwWriteTransfer`
- size: `146`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD, char, _DWORD, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400029b0`

## callees

- `0x1400048f8`
- `0x140006630`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qqqbr2_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        int a6,
        __int64 a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-21h] BYREF
  int *v9; // [rsp+40h] [rbp-11h]
  __int64 v10; // [rsp+48h] [rbp-9h]
  char *v11; // [rsp+50h] [rbp-1h]
  __int64 v12; // [rsp+58h] [rbp+7h]
  int *v13; // [rsp+60h] [rbp+Fh]
  __int64 v14; // [rsp+68h] [rbp+17h]
  __int64 v15; // [rsp+70h] [rbp+1Fh]
  int v16; // [rsp+78h] [rbp+27h]
  int v17; // [rsp+7Ch] [rbp+2Bh]
  int v18; // [rsp+B8h] [rbp+67h] BYREF

  v18 = a4;
  v10 = 4;
  v17 = 0;
  v9 = &v18;
  v11 = &a5;
  v13 = &a6;
  v15 = a7;
  v16 = a6;
  v12 = 4;
  v14 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)"9'", a3, 5u, &v8);
}

```

## disassembly

```asm
0x140004860  mov     [rsp-8+arg_18], r9d
0x140004865  push    rbp
0x140004866  lea     rbp, [rsp-3Fh]
0x14000486b  sub     rsp, 90h
0x140004872  mov     rax, cs:__security_cookie
0x140004879  xor     rax, rsp
0x14000487c  mov     [rbp+3Fh+var_10], rax
0x140004880  xor     edx, edx
0x140004882  mov     [rbp+3Fh+var_48], 4
0x14000488a  lea     rax, [rbp+3Fh+arg_18]
0x14000488e  mov     [rbp+3Fh+var_14], edx
0x140004891  mov     [rbp+3Fh+var_50], rax
0x140004895  lea     rax, [rbp+3Fh+arg_20]
0x140004899  mov     [rbp+3Fh+var_40], rax
0x14000489d  lea     rax, [rbp+3Fh+arg_28]
0x1400048a1  mov     [rbp+3Fh+var_30], rax
0x1400048a5  lea     r9d, [rdx+5]
0x1400048a9  mov     rax, [rbp+3Fh+arg_30]
0x1400048ad  lea     rdx, LldpduReceived; "9'"
0x1400048b4  mov     [rbp+3Fh+var_20], rax
0x1400048b8  mov     eax, [rbp+3Fh+arg_28]
0x1400048bb  mov     [rbp+3Fh+var_18], eax
0x1400048be  lea     rax, [rbp+3Fh+var_60]
0x1400048c2  mov     [rsp+90h+var_70], rax
0x1400048c7  mov     [rbp+3Fh+var_38], 4
0x1400048cf  mov     [rbp+3Fh+var_28], 4
0x1400048d7  call    McGenEventWrite_EtwWriteTransfer
0x1400048dc  mov     rcx, [rbp+3Fh+var_10]
0x1400048e0  xor     rcx, rsp; StackCookie
0x1400048e3  call    __security_check_cookie
0x1400048e8  add     rsp, 90h
0x1400048ef  pop     rbp
0x1400048f0  retn
```
