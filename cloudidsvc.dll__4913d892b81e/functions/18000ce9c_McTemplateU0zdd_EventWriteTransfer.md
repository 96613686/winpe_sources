# McTemplateU0zdd_EventWriteTransfer

- ea: `0x18000ce9c`
- end: `0x18000cf3d`
- name: `McTemplateU0zdd_EventWriteTransfer`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ba60`

## callees

- `0x180001a50`
- `0x180008570`
- `0x18000ce9c`

## pseudocode

```c
ULONG __fastcall McTemplateU0zdd_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4, char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-40h]
  int v10; // [rsp+48h] [rbp-38h]
  int v11; // [rsp+4Ch] [rbp-34h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+A8h] [rbp+28h] BYREF

  v16 = a4;
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
  v11 = 0;
  v13 = 4;
  v12 = &v16;
  v15 = 4;
  v14 = &a5;
  if ( !a3 )
    a3 = L"NULL";
  v9 = a3;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)EndpointSyncFailure,
           (__int64)a3,
           4u,
           &v8);
}

```

## disassembly

```asm
0x18000ce9c  mov     [rsp-8+arg_18], r9d
0x18000cea1  push    rbp
0x18000cea2  mov     rbp, rsp
0x18000cea5  sub     rsp, 80h
0x18000ceac  mov     rax, cs:__security_cookie
0x18000ceb3  xor     rax, rsp
0x18000ceb6  mov     [rbp+var_10], rax
0x18000ceba  xor     edx, edx
0x18000cebc  test    r8, r8
0x18000cebf  jz      short loc_18000CED8
0x18000cec1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000cec5  inc     rax
0x18000cec8  cmp     [r8+rax*2], dx
0x18000cecd  jnz     short loc_18000CEC5
0x18000cecf  lea     eax, ds:2[rax*2]
0x18000ced6  jmp     short loc_18000CEDD
0x18000ced8  mov     eax, 0Ah
0x18000cedd  mov     [rbp+var_38], eax
0x18000cee0  lea     rcx, aNull; "NULL"
0x18000cee7  mov     r9d, 4
0x18000ceed  mov     [rbp+var_34], edx
0x18000cef0  lea     rax, [rbp+arg_18]
0x18000cef4  mov     [rbp+var_28], r9
0x18000cef8  mov     [rbp+var_30], rax
0x18000cefc  lea     rdx, EndpointSyncFailure
0x18000cf03  lea     rax, [rbp+arg_20]
0x18000cf07  mov     [rbp+var_18], r9
0x18000cf0b  test    r8, r8
0x18000cf0e  mov     [rbp+var_20], rax
0x18000cf12  lea     rax, [rbp+var_50]
0x18000cf16  cmovz   r8, rcx
0x18000cf1a  mov     [rsp+80h+var_60], rax
0x18000cf1f  mov     [rbp+var_40], r8
0x18000cf23  call    McGenEventWrite_EventWriteTransfer
0x18000cf28  mov     rcx, [rbp+var_10]
0x18000cf2c  xor     rcx, rsp; StackCookie
0x18000cf2f  call    __security_check_cookie
0x18000cf34  add     rsp, 80h
0x18000cf3b  pop     rbp
0x18000cf3c  retn
```
