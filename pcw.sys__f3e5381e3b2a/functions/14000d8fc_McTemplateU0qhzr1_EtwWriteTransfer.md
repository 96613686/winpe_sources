# McTemplateU0qhzr1_EtwWriteTransfer

- ea: `0x14000d8fc`
- end: `0x14000d985`
- name: `McTemplateU0qhzr1_EtwWriteTransfer`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000dc00`

## callees

- `0x140001370`
- `0x14000acd0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0qhzr1_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-50h] BYREF
  int *v7; // [rsp+40h] [rbp-40h]
  __int64 v8; // [rsp+48h] [rbp-38h]
  __int16 *v9; // [rsp+50h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-28h]
  __int64 v11; // [rsp+60h] [rbp-20h]
  int v12; // [rsp+68h] [rbp-18h]
  int v13; // [rsp+6Ch] [rbp-14h]
  int v14; // [rsp+A0h] [rbp+20h] BYREF
  unsigned __int16 v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v14 = a3;
  v10 = 2;
  v8 = 4;
  v7 = &v14;
  v13 = 0;
  v9 = (__int16 *)&v15;
  v11 = a5;
  v12 = 2 * a4;
  return McGenEventWrite_EtwWriteTransfer(0, (const EVENT_DESCRIPTOR *)PcwRegisterFail, a3, 4u, &v6);
}

```

## disassembly

```asm
0x14000d8fc  mov     [rsp-8+arg_18], r9w
0x14000d902  mov     [rsp-8+arg_10], r8d
0x14000d907  push    rbp
0x14000d908  mov     rbp, rsp
0x14000d90b  sub     rsp, 80h
0x14000d912  mov     rax, cs:__security_cookie
0x14000d919  xor     rax, rsp
0x14000d91c  mov     [rbp+var_10], rax
0x14000d920  mov     edx, 4
0x14000d925  mov     [rbp+var_28], 2
0x14000d92d  lea     rax, [rbp+arg_10]
0x14000d931  mov     [rbp+var_38], rdx
0x14000d935  mov     [rbp+var_40], rax
0x14000d939  xor     ecx, ecx
0x14000d93b  lea     rax, [rbp+arg_18]
0x14000d93f  mov     [rbp+var_14], ecx
0x14000d942  mov     [rbp+var_30], rax
0x14000d946  mov     rax, [rbp+arg_20]
0x14000d94a  mov     [rbp+var_20], rax
0x14000d94e  movzx   eax, r9w
0x14000d952  mov     r9d, edx
0x14000d955  add     eax, eax
0x14000d957  lea     rdx, PcwRegisterFail
0x14000d95e  mov     [rbp+var_18], eax
0x14000d961  lea     rax, [rbp+var_50]
0x14000d965  mov     [rsp+80h+var_60], rax
0x14000d96a  call    McGenEventWrite_EtwWriteTransfer
0x14000d96f  mov     rcx, [rbp+var_10]
0x14000d973  xor     rcx, rsp; StackCookie
0x14000d976  call    __security_check_cookie
0x14000d97b  add     rsp, 80h
0x14000d982  pop     rbp
0x14000d983  retn
```
