# McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer

- ea: `0x140004304`
- end: `0x1400043e4`
- name: `McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer`
- size: `224`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140015eb0`
- `0x1400160a0`

## callees

- `0x140004158`
- `0x1400054a0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0hzr0qzr2hzr4hzr6_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        unsigned __int16 a8,
        __int64 a9,
        unsigned __int16 a10,
        __int64 a11)
{
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-81h] BYREF
  __int16 *v13; // [rsp+40h] [rbp-71h]
  __int64 v14; // [rsp+48h] [rbp-69h]
  __int64 v15; // [rsp+50h] [rbp-61h]
  int v16; // [rsp+58h] [rbp-59h]
  int v17; // [rsp+5Ch] [rbp-55h]
  int *v18; // [rsp+60h] [rbp-51h]
  __int64 v19; // [rsp+68h] [rbp-49h]
  __int64 v20; // [rsp+70h] [rbp-41h]
  int v21; // [rsp+78h] [rbp-39h]
  int v22; // [rsp+7Ch] [rbp-35h]
  unsigned __int16 *v23; // [rsp+80h] [rbp-31h]
  __int64 v24; // [rsp+88h] [rbp-29h]
  __int64 v25; // [rsp+90h] [rbp-21h]
  int v26; // [rsp+98h] [rbp-19h]
  int v27; // [rsp+9Ch] [rbp-15h]
  unsigned __int16 *v28; // [rsp+A0h] [rbp-11h]
  __int64 v29; // [rsp+A8h] [rbp-9h]
  __int64 v30; // [rsp+B0h] [rbp-1h]
  int v31; // [rsp+B8h] [rbp+7h]
  int v32; // [rsp+BCh] [rbp+Bh]
  unsigned __int16 v33; // [rsp+F8h] [rbp+47h] BYREF

  v33 = a4;
  v14 = 2;
  v17 = 0;
  v13 = (__int16 *)&v33;
  v15 = a5;
  v19 = 4;
  v16 = 2 * a4;
  v18 = &a6;
  v20 = a7;
  v22 = 0;
  v21 = 2 * a6;
  v23 = &a8;
  v25 = a9;
  v24 = 2;
  v26 = 2 * a8;
  v28 = &a10;
  v30 = a11;
  v27 = 0;
  v31 = 2 * a10;
  v29 = 2;
  v32 = 0;
  return McGenEventWrite_EtwWriteTransfer(a1, a2, 0, 9u, &v12);
}

```

## disassembly

```asm
0x140004304  mov     [rsp-8+arg_18], r9w
0x14000430a  push    rbp
0x14000430b  lea     rbp, [rsp-1Fh]
0x140004310  sub     rsp, 0D0h
0x140004317  mov     rax, cs:__security_cookie
0x14000431e  xor     rax, rsp
0x140004321  mov     [rbp+1Fh+var_10], rax
0x140004325  xor     r8d, r8d
0x140004328  mov     [rbp+1Fh+var_88], 2
0x140004330  lea     rax, [rbp+1Fh+arg_18]
0x140004334  mov     [rbp+1Fh+var_74], r8d
0x140004338  mov     [rbp+1Fh+var_90], rax
0x14000433c  mov     rax, [rbp+1Fh+arg_20]
0x140004340  mov     [rbp+1Fh+var_80], rax
0x140004344  movzx   eax, r9w
0x140004348  lea     r9d, [r8+9]
0x14000434c  add     eax, eax
0x14000434e  mov     [rbp+1Fh+var_68], 4
0x140004356  mov     [rbp+1Fh+var_78], eax
0x140004359  lea     rax, [rbp+1Fh+arg_28]
0x14000435d  mov     [rbp+1Fh+var_70], rax
0x140004361  mov     rax, [rbp+1Fh+arg_30]
0x140004365  mov     [rbp+1Fh+var_60], rax
0x140004369  mov     eax, [rbp+1Fh+arg_28]
0x14000436c  add     eax, eax
0x14000436e  mov     [rbp+1Fh+var_54], r8d
0x140004372  mov     [rbp+1Fh+var_58], eax
0x140004375  lea     rax, [rbp+1Fh+arg_38]
0x140004379  mov     [rbp+1Fh+var_50], rax
0x14000437d  mov     rax, [rbp+1Fh+arg_40]
0x140004381  mov     [rbp+1Fh+var_40], rax
0x140004385  movzx   eax, [rbp+1Fh+arg_38]
0x140004389  add     eax, eax
0x14000438b  mov     [rbp+1Fh+var_48], 2
0x140004393  mov     [rbp+1Fh+var_38], eax
0x140004396  lea     rax, [rbp+1Fh+arg_48]
0x14000439a  mov     [rbp+1Fh+var_30], rax
0x14000439e  mov     rax, [rbp+1Fh+arg_50]
0x1400043a2  mov     [rbp+1Fh+var_20], rax
0x1400043a6  movzx   eax, [rbp+1Fh+arg_48]
0x1400043aa  add     eax, eax
0x1400043ac  mov     [rbp+1Fh+var_34], r8d
0x1400043b0  mov     [rbp+1Fh+var_18], eax
0x1400043b3  lea     rax, [rsp+0D0h+var_A0]
0x1400043b8  mov     [rsp+0D0h+var_B0], rax
0x1400043bd  mov     [rbp+1Fh+var_28], 2
0x1400043c5  mov     [rbp+1Fh+var_14], r8d
0x1400043c9  call    McGenEventWrite_EtwWriteTransfer
0x1400043ce  mov     rcx, [rbp+1Fh+var_10]
0x1400043d2  xor     rcx, rsp; StackCookie
0x1400043d5  call    __security_check_cookie
0x1400043da  add     rsp, 0D0h
0x1400043e1  pop     rbp
0x1400043e2  retn
```
