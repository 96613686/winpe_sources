# McTemplateK0qpqd_EtwWriteTransfer

- ea: `0x140026804`
- end: `0x140026895`
- name: `McTemplateK0qpqd_EtwWriteTransfer`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400180f4`
- `0x14005fe50`

## callees

- `0x1400062a0`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qpqd_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        int a4,
        char a5,
        char a6,
        char a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-21h] BYREF
  int *v9; // [rsp+40h] [rbp-11h]
  __int64 v10; // [rsp+48h] [rbp-9h]
  char *v11; // [rsp+50h] [rbp-1h]
  __int64 v12; // [rsp+58h] [rbp+7h]
  char *v13; // [rsp+60h] [rbp+Fh]
  __int64 v14; // [rsp+68h] [rbp+17h]
  char *v15; // [rsp+70h] [rbp+1Fh]
  __int64 v16; // [rsp+78h] [rbp+27h]
  int v17; // [rsp+B8h] [rbp+67h] BYREF

  v17 = a4;
  v10 = 4;
  v9 = &v17;
  v12 = 8;
  v11 = &a5;
  v14 = 4;
  v13 = &a6;
  v15 = &a7;
  v16 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)EventEnumerationComplete, a3, 5u, &v8);
}

```

## disassembly

```asm
0x140026804  mov     [rsp-8+arg_18], r9d
0x140026809  push    rbp
0x14002680a  lea     rbp, [rsp-3Fh]
0x14002680f  sub     rsp, 90h
0x140026816  mov     rax, cs:__security_cookie
0x14002681d  xor     rax, rsp
0x140026820  mov     [rbp+3Fh+var_10], rax
0x140026824  lea     rax, [rbp+3Fh+arg_18]
0x140026828  mov     [rbp+3Fh+var_48], 4
0x140026830  mov     [rbp+3Fh+var_50], rax
0x140026834  lea     rdx, EventEnumerationComplete
0x14002683b  lea     rax, [rbp+3Fh+arg_20]
0x14002683f  mov     [rbp+3Fh+var_38], 8
0x140026847  mov     [rbp+3Fh+var_40], rax
0x14002684b  mov     r9d, 5
0x140026851  lea     rax, [rbp+3Fh+arg_28]
0x140026855  mov     [rbp+3Fh+var_28], 4
0x14002685d  mov     [rbp+3Fh+var_30], rax
0x140026861  lea     rax, [rbp+3Fh+arg_30]
0x140026865  mov     [rbp+3Fh+var_20], rax
0x140026869  lea     rax, [rbp+3Fh+var_60]
0x14002686d  mov     [rsp+90h+var_70], rax
0x140026872  mov     [rbp+3Fh+var_18], 4
0x14002687a  call    McGenEventWrite_EtwWriteTransfer
0x14002687f  mov     rcx, [rbp+3Fh+var_10]
0x140026883  xor     rcx, rsp; StackCookie
0x140026886  call    __security_check_cookie
0x14002688b  add     rsp, 90h
0x140026892  pop     rbp
0x140026893  retn
```
