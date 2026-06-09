# McTemplateK0hzr0qzr2_EtwWriteTransfer

- ea: `0x14000426c`
- end: `0x1400042fe`
- name: `McTemplateK0hzr0qzr2_EtwWriteTransfer`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140015930`
- `0x140016050`

## callees

- `0x140004158`
- `0x1400054a0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0hzr0qzr2_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        int a6,
        __int64 a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-21h] BYREF
  __int16 *v9; // [rsp+40h] [rbp-11h]
  __int64 v10; // [rsp+48h] [rbp-9h]
  __int64 v11; // [rsp+50h] [rbp-1h]
  int v12; // [rsp+58h] [rbp+7h]
  int v13; // [rsp+5Ch] [rbp+Bh]
  int *v14; // [rsp+60h] [rbp+Fh]
  __int64 v15; // [rsp+68h] [rbp+17h]
  __int64 v16; // [rsp+70h] [rbp+1Fh]
  int v17; // [rsp+78h] [rbp+27h]
  int v18; // [rsp+7Ch] [rbp+2Bh]
  unsigned __int16 v19; // [rsp+B8h] [rbp+67h] BYREF

  v19 = a4;
  v10 = 2;
  v13 = 0;
  v9 = (__int16 *)&v19;
  v11 = a5;
  v15 = 4;
  v12 = 2 * a4;
  v14 = &a6;
  v16 = a7;
  v18 = 0;
  v17 = 2 * a6;
  return McGenEventWrite_EtwWriteTransfer(0, a2, a3, 5u, &v8);
}

```

## disassembly

```asm
0x14000426c  mov     [rsp-8+arg_18], r9w
0x140004272  push    rbp
0x140004273  lea     rbp, [rsp-3Fh]
0x140004278  sub     rsp, 90h
0x14000427f  mov     rax, cs:__security_cookie
0x140004286  xor     rax, rsp
0x140004289  mov     [rbp+3Fh+var_10], rax
0x14000428d  xor     ecx, ecx
0x14000428f  mov     [rbp+3Fh+var_48], 2
0x140004297  lea     rax, [rbp+3Fh+arg_18]
0x14000429b  mov     [rbp+3Fh+var_34], ecx
0x14000429e  mov     [rbp+3Fh+var_50], rax
0x1400042a2  mov     rax, [rbp+3Fh+arg_20]
0x1400042a6  mov     [rbp+3Fh+var_40], rax
0x1400042aa  movzx   eax, r9w
0x1400042ae  lea     r9d, [rcx+5]
0x1400042b2  add     eax, eax
0x1400042b4  mov     [rbp+3Fh+var_28], 4
0x1400042bc  mov     [rbp+3Fh+var_38], eax
0x1400042bf  lea     rax, [rbp+3Fh+arg_28]
0x1400042c3  mov     [rbp+3Fh+var_30], rax
0x1400042c7  mov     rax, [rbp+3Fh+arg_30]
0x1400042cb  mov     [rbp+3Fh+var_20], rax
0x1400042cf  mov     eax, [rbp+3Fh+arg_28]
0x1400042d2  add     eax, eax
0x1400042d4  mov     [rbp+3Fh+var_14], ecx
0x1400042d7  mov     [rbp+3Fh+var_18], eax
0x1400042da  lea     rax, [rbp+3Fh+var_60]
0x1400042de  mov     [rsp+90h+var_70], rax
0x1400042e3  call    McGenEventWrite_EtwWriteTransfer
0x1400042e8  mov     rcx, [rbp+3Fh+var_10]
0x1400042ec  xor     rcx, rsp; StackCookie
0x1400042ef  call    __security_check_cookie
0x1400042f4  add     rsp, 90h
0x1400042fb  pop     rbp
0x1400042fc  retn
```
