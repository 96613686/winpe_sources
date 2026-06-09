# McTemplateK0hzr0qzr2qhzr5_EtwWriteTransfer

- ea: `0x1400044bc`
- end: `0x140004586`
- name: `McTemplateK0hzr0qzr2qhzr5_EtwWriteTransfer`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140016050`

## callees

- `0x140004158`
- `0x1400054a0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0hzr0qzr2qhzr5_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        char a8,
        unsigned __int16 a9,
        __int64 a10)
{
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-69h] BYREF
  __int16 *v12; // [rsp+40h] [rbp-59h]
  __int64 v13; // [rsp+48h] [rbp-51h]
  __int64 v14; // [rsp+50h] [rbp-49h]
  int v15; // [rsp+58h] [rbp-41h]
  int v16; // [rsp+5Ch] [rbp-3Dh]
  int *v17; // [rsp+60h] [rbp-39h]
  __int64 v18; // [rsp+68h] [rbp-31h]
  __int64 v19; // [rsp+70h] [rbp-29h]
  int v20; // [rsp+78h] [rbp-21h]
  int v21; // [rsp+7Ch] [rbp-1Dh]
  char *v22; // [rsp+80h] [rbp-19h]
  __int64 v23; // [rsp+88h] [rbp-11h]
  unsigned __int16 *v24; // [rsp+90h] [rbp-9h]
  __int64 v25; // [rsp+98h] [rbp-1h]
  __int64 v26; // [rsp+A0h] [rbp+7h]
  int v27; // [rsp+A8h] [rbp+Fh]
  int v28; // [rsp+ACh] [rbp+13h]
  unsigned __int16 v29; // [rsp+E8h] [rbp+4Fh] BYREF

  v29 = a4;
  v13 = 2;
  v16 = 0;
  v12 = (__int16 *)&v29;
  v14 = a5;
  v18 = 4;
  v15 = 2 * a4;
  v17 = &a6;
  v19 = a7;
  v21 = 0;
  v20 = 2 * a6;
  v22 = &a8;
  v24 = &a9;
  v26 = a10;
  v23 = 4;
  v27 = 2 * a9;
  v25 = 2;
  v28 = 0;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, a3, 8u, &v11);
}

```

## disassembly

```asm
0x1400044bc  mov     [rsp-8+arg_18], r9w
0x1400044c2  push    rbp
0x1400044c3  lea     rbp, [rsp-27h]
0x1400044c8  sub     rsp, 0C0h
0x1400044cf  mov     rax, cs:__security_cookie
0x1400044d6  xor     rax, rsp
0x1400044d9  mov     [rbp+27h+var_10], rax
0x1400044dd  xor     r10d, r10d
0x1400044e0  mov     [rbp+27h+var_78], 2
0x1400044e8  lea     rax, [rbp+27h+arg_18]
0x1400044ec  mov     [rbp+27h+var_64], r10d
0x1400044f0  mov     [rbp+27h+var_80], rax
0x1400044f4  mov     rax, [rbp+27h+arg_20]
0x1400044f8  mov     [rbp+27h+var_70], rax
0x1400044fc  movzx   eax, r9w
0x140004500  lea     r9d, [r10+8]
0x140004504  add     eax, eax
0x140004506  mov     [rbp+27h+var_58], 4
0x14000450e  mov     [rbp+27h+var_68], eax
0x140004511  lea     rax, [rbp+27h+arg_28]
0x140004515  mov     [rbp+27h+var_60], rax
0x140004519  mov     rax, [rbp+27h+arg_30]
0x14000451d  mov     [rbp+27h+var_50], rax
0x140004521  mov     eax, [rbp+27h+arg_28]
0x140004524  add     eax, eax
0x140004526  mov     [rbp+27h+var_44], r10d
0x14000452a  mov     [rbp+27h+var_48], eax
0x14000452d  lea     rax, [rbp+27h+arg_38]
0x140004531  mov     [rbp+27h+var_40], rax
0x140004535  lea     rax, [rbp+27h+arg_40]
0x140004539  mov     [rbp+27h+var_30], rax
0x14000453d  mov     rax, [rbp+27h+arg_48]
0x140004541  mov     [rbp+27h+var_20], rax
0x140004545  movzx   eax, [rbp+27h+arg_40]
0x140004549  add     eax, eax
0x14000454b  mov     [rbp+27h+var_38], 4
0x140004553  mov     [rbp+27h+var_18], eax
0x140004556  lea     rax, [rbp+27h+var_90]
0x14000455a  mov     [rsp+0C0h+var_A0], rax
0x14000455f  mov     [rbp+27h+var_28], 2
0x140004567  mov     [rbp+27h+var_14], r10d
0x14000456b  call    McGenEventWrite_EtwWriteTransfer
0x140004570  mov     rcx, [rbp+27h+var_10]
0x140004574  xor     rcx, rsp; StackCookie
0x140004577  call    __security_check_cookie
0x14000457c  add     rsp, 0C0h
0x140004583  pop     rbp
0x140004584  retn
```
