# McTemplateU0zqqd_EventWriteTransfer

- ea: `0x14000ce84`
- end: `0x14000cf3b`
- name: `McTemplateU0zqqd_EventWriteTransfer`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b774`
- `0x14000bca4`

## callees

- `0x14000cd7c`
- `0x14000ce84`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall McTemplateU0zqqd_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        int a4,
        char a5,
        char a6)
{
  __int64 v6; // rax
  int v7; // eax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v10; // [rsp+40h] [rbp-9h]
  int v11; // [rsp+48h] [rbp-1h]
  int v12; // [rsp+4Ch] [rbp+3h]
  int *v13; // [rsp+50h] [rbp+7h]
  __int64 v14; // [rsp+58h] [rbp+Fh]
  char *v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+68h] [rbp+1Fh]
  char *v17; // [rsp+70h] [rbp+27h]
  __int64 v18; // [rsp+78h] [rbp+2Fh]
  int v19; // [rsp+B8h] [rbp+6Fh] BYREF

  v19 = a4;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  v11 = v7;
  v12 = 0;
  v13 = &v19;
  v14 = 4;
  v15 = &a5;
  if ( !a3 )
    a3 = L"NULL";
  v10 = a3;
  v17 = &a6;
  v16 = 4;
  v18 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 5u, &v9);
}

```

## disassembly

```asm
0x14000ce84  mov     [rsp-8+arg_18], r9d
0x14000ce89  push    rbp
0x14000ce8a  lea     rbp, [rsp-47h]
0x14000ce8f  sub     rsp, 90h
0x14000ce96  mov     rax, cs:__security_cookie
0x14000ce9d  xor     rax, rsp
0x14000cea0  mov     [rbp+47h+var_10], rax
0x14000cea4  xor     r9d, r9d
0x14000cea7  test    r8, r8
0x14000ceaa  jz      short loc_14000CEC3
0x14000ceac  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ceb0  inc     rax
0x14000ceb3  cmp     [r8+rax*2], r9w
0x14000ceb8  jnz     short loc_14000CEB0
0x14000ceba  lea     eax, ds:2[rax*2]
0x14000cec1  jmp     short loc_14000CEC8
0x14000cec3  mov     eax, 0Ah
0x14000cec8  mov     [rbp+47h+var_48], eax
0x14000cecb  lea     rcx, aNull; "NULL"
0x14000ced2  lea     rax, [rbp+47h+arg_18]
0x14000ced6  mov     [rbp+47h+var_44], r9d
0x14000ceda  mov     [rbp+47h+var_40], rax
0x14000cede  test    r8, r8
0x14000cee1  lea     rax, [rbp+47h+arg_20]
0x14000cee5  mov     [rbp+47h+var_38], 4
0x14000ceed  mov     [rbp+47h+var_30], rax
0x14000cef1  cmovz   r8, rcx
0x14000cef5  lea     rax, [rbp+47h+arg_28]
0x14000cef9  mov     [rbp+47h+var_50], r8
0x14000cefd  mov     [rbp+47h+var_20], rax
0x14000cf01  mov     r9d, 5
0x14000cf07  lea     rax, [rbp+47h+var_60]
0x14000cf0b  mov     [rbp+47h+var_28], 4
0x14000cf13  mov     [rsp+90h+var_70], rax
0x14000cf18  mov     [rbp+47h+var_18], 4
0x14000cf20  call    McGenEventWrite_EventWriteTransfer
0x14000cf25  mov     rcx, [rbp+47h+var_10]
0x14000cf29  xor     rcx, rsp; StackCookie
0x14000cf2c  call    __security_check_cookie
0x14000cf31  add     rsp, 90h
0x14000cf38  pop     rbp
0x14000cf39  retn
```
