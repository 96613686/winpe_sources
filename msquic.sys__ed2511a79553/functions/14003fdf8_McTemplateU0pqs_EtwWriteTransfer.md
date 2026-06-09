# McTemplateU0pqs_EtwWriteTransfer

- ea: `0x14003fdf8`
- end: `0x14003fe9d`
- name: `McTemplateU0pqs_EtwWriteTransfer`
- size: `165`
- prototype: ``
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x140001510`
- `0x140001d6c`
- `0x140002840`
- `0x140002e8c`
- `0x140003198`
- `0x140003fac`
- `0x14000554c`
- `0x14000577c`
- `0x140008568`
- `0x140008af8`
- `0x1400099b4`
- `0x14000db70`
- `0x1400108c0`
- `0x140017580`
- `0x14002f204`
- `0x140035c4c`
- `0x140036f1c`
- `0x1400385c0`
- `0x1400391c0`
- `0x14003a190`
- `0x14003b850`
- `0x14003c178`
- `0x14003c264`
- `0x1400465f4`

## callees

- `0x14003c8e0`
- `0x14003e8c4`
- `0x14003fdf8`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0pqs_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        int a4,
        const char *a5)
{
  const char *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v10; // [rsp+40h] [rbp-40h]
  __int64 v11; // [rsp+48h] [rbp-38h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  const char *v14; // [rsp+60h] [rbp-20h]
  int v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+6Ch] [rbp-14h]
  __int64 v17; // [rsp+A0h] [rbp+20h] BYREF
  int v18; // [rsp+A8h] [rbp+28h] BYREF

  v18 = a4;
  v17 = a3;
  v5 = a5;
  v10 = &v17;
  v11 = 8;
  v12 = &v18;
  v13 = 4;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = v6 + 1;
  }
  else
  {
    v7 = 5;
  }
  v15 = v7;
  v16 = 0;
  if ( !a5 )
    v5 = "NULL";
  v14 = v5;
  return McGenEventWrite_EtwWriteTransfer((__int64)v5, a2, (__int64)"NULL", 4u, &v9);
}

```

## disassembly

```asm
0x14003fdf8  mov     [rsp-8+arg_18], r9d
0x14003fdfd  mov     [rsp-8+arg_10], r8
0x14003fe02  push    rbp
0x14003fe03  mov     rbp, rsp
0x14003fe06  sub     rsp, 80h
0x14003fe0d  mov     rax, cs:__security_cookie
0x14003fe14  xor     rax, rsp
0x14003fe17  mov     [rbp+var_10], rax
0x14003fe1b  mov     rcx, [rbp+arg_20]
0x14003fe1f  lea     rax, [rbp+arg_10]
0x14003fe23  xor     r9d, r9d
0x14003fe26  mov     [rbp+var_40], rax
0x14003fe2a  mov     [rbp+var_38], 8
0x14003fe32  lea     rax, [rbp+arg_18]
0x14003fe36  mov     [rbp+var_30], rax
0x14003fe3a  lea     r10d, [r9+4]
0x14003fe3e  mov     [rbp+var_28], r10
0x14003fe42  test    rcx, rcx
0x14003fe45  jz      short loc_14003FE58
0x14003fe47  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003fe4b  inc     rax
0x14003fe4e  cmp     [rcx+rax], r9b
0x14003fe52  jnz     short loc_14003FE4B
0x14003fe54  inc     eax
0x14003fe56  jmp     short loc_14003FE5D
0x14003fe58  mov     eax, 5
0x14003fe5d  test    rcx, rcx
0x14003fe60  mov     [rbp+var_18], eax
0x14003fe63  lea     r8, aNull; "NULL"
0x14003fe6a  mov     [rbp+var_14], r9d
0x14003fe6e  cmovz   rcx, r8
0x14003fe72  lea     rax, [rbp+var_50]
0x14003fe76  mov     r9d, r10d
0x14003fe79  mov     [rbp+var_20], rcx
0x14003fe7d  mov     [rsp+80h+var_60], rax
0x14003fe82  call    McGenEventWrite_EtwWriteTransfer
0x14003fe87  mov     rcx, [rbp+var_10]
0x14003fe8b  xor     rcx, rsp; StackCookie
0x14003fe8e  call    __security_check_cookie
0x14003fe93  add     rsp, 80h
0x14003fe9a  pop     rbp
0x14003fe9b  retn
```
