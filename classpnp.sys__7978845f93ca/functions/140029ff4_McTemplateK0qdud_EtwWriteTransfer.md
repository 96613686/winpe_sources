# McTemplateK0qdud_EtwWriteTransfer

- ea: `0x140029ff4`
- end: `0x14002a088`
- name: `McTemplateK0qdud_EtwWriteTransfer`
- size: `148`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400024b0`
- `0x140002844`
- `0x140002d30`
- `0x140015890`
- `0x14001ccb0`
- `0x14001e2f0`

## callees

- `0x1400062a0`
- `0x14003e430`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qdud_EtwWriteTransfer(__int64 a1, __int64 a2, const GUID *a3, int a4, char a5, char a6)
{
  int v7; // [rsp+30h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-21h] BYREF
  int *v9; // [rsp+50h] [rbp-11h]
  __int64 v10; // [rsp+58h] [rbp-9h]
  char *v11; // [rsp+60h] [rbp-1h]
  __int64 v12; // [rsp+68h] [rbp+7h]
  char *v13; // [rsp+70h] [rbp+Fh]
  __int64 v14; // [rsp+78h] [rbp+17h]
  int *v15; // [rsp+80h] [rbp+1Fh]
  __int64 v16; // [rsp+88h] [rbp+27h]
  int v17; // [rsp+C8h] [rbp+67h] BYREF

  v17 = a4;
  v10 = 4;
  v7 = 0;
  v9 = &v17;
  v11 = &a5;
  v13 = &a6;
  v12 = 4;
  v15 = &v7;
  v14 = 1;
  v16 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)EventQueue, a3, 5u, &v8);
}

```

## disassembly

```asm
0x140029ff4  mov     [rsp-8+arg_18], r9d
0x140029ff9  push    rbp
0x140029ffa  lea     rbp, [rsp-3Fh]
0x140029fff  sub     rsp, 0A0h
0x14002a006  mov     rax, cs:__security_cookie
0x14002a00d  xor     rax, rsp
0x14002a010  mov     [rbp+3Fh+var_10], rax
0x14002a014  xor     edx, edx
0x14002a016  mov     [rbp+3Fh+var_48], 4
0x14002a01e  lea     rax, [rbp+3Fh+arg_18]
0x14002a022  mov     [rbp+3Fh+var_70], edx
0x14002a025  mov     [rbp+3Fh+var_50], rax
0x14002a029  lea     rax, [rbp+3Fh+arg_20]
0x14002a02d  mov     [rbp+3Fh+var_40], rax
0x14002a031  lea     rax, [rbp+3Fh+arg_28]
0x14002a035  mov     [rbp+3Fh+var_30], rax
0x14002a039  lea     r9d, [rdx+5]
0x14002a03d  lea     rax, [rbp+3Fh+var_70]
0x14002a041  mov     [rbp+3Fh+var_38], 4
0x14002a049  mov     [rbp+3Fh+var_20], rax
0x14002a04d  lea     rdx, EventQueue
0x14002a054  lea     rax, [rbp+3Fh+var_60]
0x14002a058  mov     [rbp+3Fh+var_28], 1
0x14002a060  mov     [rsp+0A0h+var_80], rax
0x14002a065  mov     [rbp+3Fh+var_18], 4
0x14002a06d  call    McGenEventWrite_EtwWriteTransfer
0x14002a072  mov     rcx, [rbp+3Fh+var_10]
0x14002a076  xor     rcx, rsp; StackCookie
0x14002a079  call    __security_check_cookie
0x14002a07e  add     rsp, 0A0h
0x14002a085  pop     rbp
0x14002a086  retn
```
