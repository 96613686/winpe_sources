# McTemplateU0zqd_EventWriteTransfer

- ea: `0x14000cddc`
- end: `0x14000ce7e`
- name: `McTemplateU0zqd_EventWriteTransfer`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000baec`

## callees

- `0x14000cd7c`
- `0x14000cddc`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall McTemplateU0zqd_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4, char a5)
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
           (const EVENT_DESCRIPTOR *)EnterpriseDiagnosticsOmaDmSessionRetryScheduled,
           (__int64)a3,
           4u,
           &v8);
}

```

## disassembly

```asm
0x14000cddc  mov     [rsp-8+arg_18], r9d
0x14000cde1  push    rbp
0x14000cde2  mov     rbp, rsp
0x14000cde5  sub     rsp, 80h
0x14000cdec  mov     rax, cs:__security_cookie
0x14000cdf3  xor     rax, rsp
0x14000cdf6  mov     [rbp+var_10], rax
0x14000cdfa  xor     edx, edx
0x14000cdfc  test    r8, r8
0x14000cdff  jz      short loc_14000CE18
0x14000ce01  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ce05  inc     rax
0x14000ce08  cmp     [r8+rax*2], dx
0x14000ce0d  jnz     short loc_14000CE05
0x14000ce0f  lea     eax, ds:2[rax*2]
0x14000ce16  jmp     short loc_14000CE1D
0x14000ce18  mov     eax, 0Ah
0x14000ce1d  mov     [rbp+var_38], eax
0x14000ce20  lea     rcx, aNull; "NULL"
0x14000ce27  mov     r9d, 4
0x14000ce2d  mov     [rbp+var_34], edx
0x14000ce30  lea     rax, [rbp+arg_18]
0x14000ce34  mov     [rbp+var_28], r9
0x14000ce38  mov     [rbp+var_30], rax
0x14000ce3c  lea     rdx, EnterpriseDiagnosticsOmaDmSessionRetryScheduled
0x14000ce43  lea     rax, [rbp+arg_20]
0x14000ce47  mov     [rbp+var_18], r9
0x14000ce4b  test    r8, r8
0x14000ce4e  mov     [rbp+var_20], rax
0x14000ce52  lea     rax, [rbp+var_50]
0x14000ce56  cmovz   r8, rcx
0x14000ce5a  mov     [rsp+80h+var_60], rax
0x14000ce5f  mov     [rbp+var_40], r8
0x14000ce63  call    McGenEventWrite_EventWriteTransfer
0x14000ce68  mov     rcx, [rbp+var_10]
0x14000ce6c  xor     rcx, rsp; StackCookie
0x14000ce6f  call    __security_check_cookie
0x14000ce74  add     rsp, 80h
0x14000ce7b  pop     rbp
0x14000ce7c  retn
```
