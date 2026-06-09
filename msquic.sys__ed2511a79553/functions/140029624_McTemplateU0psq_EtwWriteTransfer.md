# McTemplateU0psq_EtwWriteTransfer

- ea: `0x140029624`
- end: `0x1400296bf`
- name: `McTemplateU0psq_EtwWriteTransfer`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400010b0`
- `0x140040ca8`

## callees

- `0x140029624`
- `0x14003c8e0`
- `0x14003e8c4`

## pseudocode

```c
NTSTATUS __fastcall McTemplateU0psq_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        const char *a4,
        char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  __int64 *v9; // [rsp+40h] [rbp-40h]
  __int64 v10; // [rsp+48h] [rbp-38h]
  const char *v11; // [rsp+50h] [rbp-30h]
  int v12; // [rsp+58h] [rbp-28h]
  int v13; // [rsp+5Ch] [rbp-24h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  __int64 v16; // [rsp+A0h] [rbp+20h] BYREF

  v16 = a3;
  v10 = 8;
  v9 = &v16;
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  v12 = v6;
  v13 = 0;
  if ( !a4 )
    a4 = "NULL";
  v11 = a4;
  v14 = &a5;
  v15 = 4;
  return McGenEventWrite_EtwWriteTransfer((__int64)"NULL", a2, 0, 4u, &v8);
}

```

## disassembly

```asm
0x140029624  mov     [rsp-8+arg_10], r8
0x140029629  push    rbp
0x14002962a  mov     rbp, rsp
0x14002962d  sub     rsp, 80h
0x140029634  mov     rax, cs:__security_cookie
0x14002963b  xor     rax, rsp
0x14002963e  mov     [rbp+var_10], rax
0x140029642  xor     r8d, r8d
0x140029645  mov     [rbp+var_38], 8
0x14002964d  lea     rax, [rbp+arg_10]
0x140029651  mov     [rbp+var_40], rax
0x140029655  test    r9, r9
0x140029658  jz      short loc_14002966B
0x14002965a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002965e  inc     rax
0x140029661  cmp     [r9+rax], r8b
0x140029665  jnz     short loc_14002965E
0x140029667  inc     eax
0x140029669  jmp     short loc_140029670
0x14002966b  mov     eax, 5
0x140029670  test    r9, r9
0x140029673  mov     [rbp+var_28], eax
0x140029676  lea     rcx, aNull; "NULL"
0x14002967d  mov     [rbp+var_24], r8d
0x140029681  cmovz   r9, rcx
0x140029685  lea     rax, [rbp+arg_20]
0x140029689  mov     [rbp+var_30], r9
0x14002968d  mov     r9d, 4
0x140029693  mov     [rbp+var_20], rax
0x140029697  lea     rax, [rbp+var_50]
0x14002969b  mov     [rbp+var_18], r9
0x14002969f  mov     [rsp+80h+var_60], rax
0x1400296a4  call    McGenEventWrite_EtwWriteTransfer
0x1400296a9  mov     rcx, [rbp+var_10]
0x1400296ad  xor     rcx, rsp; StackCookie
0x1400296b0  call    __security_check_cookie
0x1400296b5  add     rsp, 80h
0x1400296bc  pop     rbp
0x1400296bd  retn
```
