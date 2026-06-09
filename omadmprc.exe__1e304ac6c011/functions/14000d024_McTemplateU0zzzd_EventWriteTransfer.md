# McTemplateU0zzzd_EventWriteTransfer

- ea: `0x14000d024`
- end: `0x14000d101`
- name: `McTemplateU0zzzd_EventWriteTransfer`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000beb8`

## callees

- `0x14000cd7c`
- `0x14000d024`
- `0x140015690`

## pseudocode

```c
ULONG McTemplateU0zzzd_EventWriteTransfer(
        _DWORD a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        _DWORD a4,
        const wchar_t *a5,
        ...)
{
  __int64 v5; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  const wchar_t *v10; // rcx
  bool v11; // zf
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-9h]
  int v15; // [rsp+48h] [rbp-1h]
  int v16; // [rsp+4Ch] [rbp+3h]
  const unsigned __int16 *v17; // [rsp+50h] [rbp+7h]
  __int64 v18; // [rsp+58h] [rbp+Fh]
  const wchar_t *v19; // [rsp+60h] [rbp+17h]
  int v20; // [rsp+68h] [rbp+1Fh]
  int v21; // [rsp+6Ch] [rbp+23h]
  va_list v22; // [rsp+70h] [rbp+27h]
  __int64 v23; // [rsp+78h] [rbp+2Fh]
  va_list va; // [rsp+C8h] [rbp+7Fh] BYREF

  va_start(va, a5);
  v5 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v15 = v9;
  v16 = 0;
  v17 = L"RetryRecovery";
  v10 = a5;
  if ( !a3 )
    a3 = L"NULL";
  v18 = 28;
  v14 = a3;
  v11 = a5 == 0;
  if ( a5 )
  {
    do
      ++v5;
    while ( a5[v5] );
    v7 = 2 * v5 + 2;
    v11 = a5 == 0;
  }
  v20 = v7;
  va_copy(v22, va);
  if ( v11 )
    v10 = L"NULL";
  v21 = 0;
  v19 = v10;
  v23 = 4;
  return McGenEventWrite_EventWriteTransfer((__int64)v10, a2, (__int64)a3, 5u, &v13);
}

```

## disassembly

```asm
0x14000d024  push    rbp
0x14000d026  lea     rbp, [rsp-47h]
0x14000d02b  sub     rsp, 90h
0x14000d032  mov     rax, cs:__security_cookie
0x14000d039  xor     rax, rsp
0x14000d03c  mov     [rbp+47h+var_10], rax
0x14000d040  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d044  xor     r9d, r9d
0x14000d047  mov     r10, rdx
0x14000d04a  mov     edx, 0Ah
0x14000d04f  test    r8, r8
0x14000d052  jz      short loc_14000D06A
0x14000d054  mov     rcx, rax
0x14000d057  inc     rcx
0x14000d05a  cmp     [r8+rcx*2], r9w
0x14000d05f  jnz     short loc_14000D057
0x14000d061  lea     ecx, ds:2[rcx*2]
0x14000d068  jmp     short loc_14000D06C
0x14000d06a  mov     ecx, edx
0x14000d06c  mov     [rbp+47h+var_48], ecx
0x14000d06f  lea     r11, aNull; "NULL"
0x14000d076  lea     rcx, aRetryrecovery; "RetryRecovery"
0x14000d07d  mov     [rbp+47h+var_44], r9d
0x14000d081  test    r8, r8
0x14000d084  mov     [rbp+47h+var_40], rcx
0x14000d088  mov     rcx, [rbp+47h+arg_20]
0x14000d08c  cmovz   r8, r11
0x14000d090  mov     [rbp+47h+var_38], 1Ch
0x14000d098  mov     [rbp+47h+var_50], r8
0x14000d09c  test    rcx, rcx
0x14000d09f  jz      short loc_14000D0B5
0x14000d0a1  inc     rax
0x14000d0a4  cmp     [rcx+rax*2], r9w
0x14000d0a9  jnz     short loc_14000D0A1
0x14000d0ab  lea     edx, ds:2[rax*2]
0x14000d0b2  test    rcx, rcx
0x14000d0b5  lea     rax, [rbp+47h+arg_28]
0x14000d0b9  mov     [rbp+47h+var_28], edx
0x14000d0bc  mov     [rbp+47h+var_20], rax
0x14000d0c0  cmovz   rcx, r11
0x14000d0c4  lea     rax, [rbp+47h+var_60]
0x14000d0c8  mov     [rbp+47h+var_24], r9d
0x14000d0cc  mov     r9d, 5
0x14000d0d2  mov     [rsp+90h+var_70], rax
0x14000d0d7  mov     rdx, r10
0x14000d0da  mov     [rbp+47h+var_30], rcx
0x14000d0de  mov     [rbp+47h+var_18], 4
0x14000d0e6  call    McGenEventWrite_EventWriteTransfer
0x14000d0eb  mov     rcx, [rbp+47h+var_10]
0x14000d0ef  xor     rcx, rsp; StackCookie
0x14000d0f2  call    __security_check_cookie
0x14000d0f7  add     rsp, 90h
0x14000d0fe  pop     rbp
0x14000d0ff  retn
```
