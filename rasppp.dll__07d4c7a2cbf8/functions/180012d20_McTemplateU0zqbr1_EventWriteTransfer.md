# McTemplateU0zqbr1_EventWriteTransfer

- ea: `0x180012d20`
- end: `0x180012dc3`
- name: `McTemplateU0zqbr1_EventWriteTransfer`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001238c`

## callees

- `0x180001460`
- `0x1800030b4`
- `0x180012d20`

## pseudocode

```c
ULONG __fastcall McTemplateU0zqbr1_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        int a4,
        __int64 a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-40h]
  int v10; // [rsp+48h] [rbp-38h]
  int v11; // [rsp+4Ch] [rbp-34h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  __int64 v14; // [rsp+60h] [rbp-20h]
  int v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+6Ch] [rbp-14h]
  int v17; // [rsp+A8h] [rbp+28h] BYREF

  v17 = a4;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v6 = 2 * v5 + 2;
  }
  else
  {
    v6 = 10;
  }
  v10 = v6;
  v15 = a4;
  v11 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v12 = &v17;
  v9 = a3;
  v14 = a5;
  v13 = 4;
  v16 = 0;
  return McGenEventWrite_EventWriteTransfer(a1, a2, 4, 4u, &v8);
}

```

## disassembly

```asm
0x180012d20  mov     [rsp-8+arg_18], r9d
0x180012d25  push    rbp
0x180012d26  mov     rbp, rsp
0x180012d29  sub     rsp, 80h
0x180012d30  mov     rax, cs:__security_cookie
0x180012d37  xor     rax, rsp
0x180012d3a  mov     [rbp+var_10], rax
0x180012d3e  xor     r11d, r11d
0x180012d41  test    r8, r8
0x180012d44  jz      short loc_180012D5D
0x180012d46  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012d4a  inc     rax
0x180012d4d  cmp     [r8+rax*2], r11w
0x180012d52  jnz     short loc_180012D4A
0x180012d54  lea     eax, ds:2[rax*2]
0x180012d5b  jmp     short loc_180012D62
0x180012d5d  mov     eax, 0Ah
0x180012d62  mov     [rbp+var_38], eax
0x180012d65  lea     r10, aNull; "NULL"
0x180012d6c  test    r8, r8
0x180012d6f  mov     [rbp+var_18], r9d
0x180012d73  lea     rax, [rbp+arg_18]
0x180012d77  mov     [rbp+var_34], r11d
0x180012d7b  cmovz   r8, r10
0x180012d7f  mov     [rbp+var_30], rax
0x180012d83  mov     rax, [rbp+arg_20]
0x180012d87  mov     [rbp+var_40], r8
0x180012d8b  mov     r8d, 4
0x180012d91  mov     [rbp+var_20], rax
0x180012d95  mov     r9d, r8d
0x180012d98  lea     rax, [rbp+var_50]
0x180012d9c  mov     [rbp+var_28], r8
0x180012da0  mov     [rsp+80h+var_60], rax
0x180012da5  mov     [rbp+var_14], r11d
0x180012da9  call    McGenEventWrite_EventWriteTransfer
0x180012dae  mov     rcx, [rbp+var_10]
0x180012db2  xor     rcx, rsp; StackCookie
0x180012db5  call    __security_check_cookie
0x180012dba  add     rsp, 80h
0x180012dc1  pop     rbp
0x180012dc2  retn
```
