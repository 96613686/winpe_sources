# McTemplateK0uuuuuhhhhq_EtwWriteTransfer

- ea: `0x140003f78`
- end: `0x140004072`
- name: `McTemplateK0uuuuuhhhhq_EtwWriteTransfer`
- size: `250`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f804`
- `0x140012ca0`

## callees

- `0x140003c54`
- `0x140005bf0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0uuuuuhhhhq_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4,
        char a5,
        char a6,
        char a7,
        char a8,
        char a9,
        char a10,
        char a11,
        char a12,
        char a13)
{
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-B1h] BYREF
  char *v15; // [rsp+40h] [rbp-A1h]
  __int64 v16; // [rsp+48h] [rbp-99h]
  char *v17; // [rsp+50h] [rbp-91h]
  __int64 v18; // [rsp+58h] [rbp-89h]
  char *v19; // [rsp+60h] [rbp-81h]
  __int64 v20; // [rsp+68h] [rbp-79h]
  char *v21; // [rsp+70h] [rbp-71h]
  __int64 v22; // [rsp+78h] [rbp-69h]
  char *v23; // [rsp+80h] [rbp-61h]
  __int64 v24; // [rsp+88h] [rbp-59h]
  char *v25; // [rsp+90h] [rbp-51h]
  __int64 v26; // [rsp+98h] [rbp-49h]
  char *v27; // [rsp+A0h] [rbp-41h]
  __int64 v28; // [rsp+A8h] [rbp-39h]
  char *v29; // [rsp+B0h] [rbp-31h]
  __int64 v30; // [rsp+B8h] [rbp-29h]
  char *v31; // [rsp+C0h] [rbp-21h]
  __int64 v32; // [rsp+C8h] [rbp-19h]
  char *v33; // [rsp+D0h] [rbp-11h]
  __int64 v34; // [rsp+D8h] [rbp-9h]
  char v35; // [rsp+118h] [rbp+37h] BYREF

  v35 = a4;
  v16 = 1;
  v15 = &v35;
  v18 = 1;
  v17 = &a5;
  v20 = 1;
  v19 = &a6;
  v22 = 1;
  v21 = &a7;
  v23 = &a8;
  v25 = &a9;
  v27 = &a10;
  v29 = &a11;
  v31 = &a12;
  v33 = &a13;
  v24 = 1;
  v26 = 2;
  v28 = 2;
  v30 = 2;
  v32 = 2;
  v34 = 4;
  return McGenEventWrite_EtwWriteTransfer(a1, (const EVENT_DESCRIPTOR *)DiskCacheInfo, 0, 0xBu, &v14);
}

```

## disassembly

```asm
0x140003f78  mov     [rsp-8+arg_18], r9b
0x140003f7d  push    rbp
0x140003f7e  lea     rbp, [rsp-0Fh]
0x140003f83  sub     rsp, 0F0h
0x140003f8a  mov     rax, cs:__security_cookie
0x140003f91  xor     rax, rsp
0x140003f94  mov     [rbp+0Fh+var_10], rax
0x140003f98  lea     rax, [rbp+0Fh+arg_18]
0x140003f9c  mov     [rsp+0F0h+var_A8], 1
0x140003fa5  mov     [rsp+0F0h+var_B0], rax
0x140003faa  lea     rdx, DiskCacheInfo
0x140003fb1  lea     rax, [rbp+0Fh+arg_20]
0x140003fb5  mov     [rsp+0F0h+var_98], 1
0x140003fbe  mov     [rsp+0F0h+var_A0], rax
0x140003fc3  mov     r9d, 0Bh
0x140003fc9  lea     rax, [rbp+0Fh+arg_28]
0x140003fcd  mov     [rbp+0Fh+var_88], 1
0x140003fd5  mov     [rsp+0F0h+var_90], rax
0x140003fda  xor     r8d, r8d
0x140003fdd  lea     rax, [rbp+0Fh+arg_30]
0x140003fe1  mov     [rbp+0Fh+var_78], 1
0x140003fe9  mov     [rbp+0Fh+var_80], rax
0x140003fed  lea     rax, [rbp+0Fh+arg_38]
0x140003ff1  mov     [rbp+0Fh+var_70], rax
0x140003ff5  lea     rax, [rbp+0Fh+arg_40]
0x140003ff9  mov     [rbp+0Fh+var_60], rax
0x140003ffd  lea     rax, [rbp+0Fh+arg_48]
0x140004001  mov     [rbp+0Fh+var_50], rax
0x140004005  lea     rax, [rbp+0Fh+arg_50]
0x140004009  mov     [rbp+0Fh+var_40], rax
0x14000400d  lea     rax, [rbp+0Fh+arg_58]
0x140004011  mov     [rbp+0Fh+var_30], rax
0x140004015  lea     rax, [rbp+0Fh+arg_60]
0x140004019  mov     [rbp+0Fh+var_20], rax
0x14000401d  lea     rax, [rsp+0F0h+var_C0]
0x140004022  mov     [rsp+0F0h+var_D0], rax
0x140004027  mov     [rbp+0Fh+var_68], 1
0x14000402f  mov     [rbp+0Fh+var_58], 2
0x140004037  mov     [rbp+0Fh+var_48], 2
0x14000403f  mov     [rbp+0Fh+var_38], 2
0x140004047  mov     [rbp+0Fh+var_28], 2
0x14000404f  mov     [rbp+0Fh+var_18], 4
0x140004057  call    McGenEventWrite_EtwWriteTransfer
0x14000405c  mov     rcx, [rbp+0Fh+var_10]
0x140004060  xor     rcx, rsp; StackCookie
0x140004063  call    __security_check_cookie
0x140004068  add     rsp, 0F0h
0x14000406f  pop     rbp
0x140004070  retn
```
