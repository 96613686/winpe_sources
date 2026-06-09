# McTemplateU0zzqq_EventWriteTransfer

- ea: `0x18002b94c`
- end: `0x18002ba23`
- name: `McTemplateU0zzqq_EventWriteTransfer`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180027de0`
- `0x1800280d8`

## callees

- `0x18001ada8`
- `0x18002b94c`
- `0x180031040`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzqq_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5,
        char a6)
{
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rcx
  bool v10; // zf
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-9h]
  int v14; // [rsp+48h] [rbp-1h]
  int v15; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v16; // [rsp+50h] [rbp+7h]
  int v17; // [rsp+58h] [rbp+Fh]
  int v18; // [rsp+5Ch] [rbp+13h]
  char *v19; // [rsp+60h] [rbp+17h]
  __int64 v20; // [rsp+68h] [rbp+1Fh]
  char *v21; // [rsp+70h] [rbp+27h]
  __int64 v22; // [rsp+78h] [rbp+2Fh]

  v6 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
  }
  else
  {
    v9 = 10;
  }
  v14 = v9;
  v15 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v13 = a3;
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  v17 = v7;
  v16 = a4;
  v19 = &a5;
  v18 = 0;
  v21 = &a6;
  v20 = 4;
  v22 = 4;
  return McGenEventWrite_EventWriteTransfer(v9, (const EVENT_DESCRIPTOR *)AccountLockedOut, (__int64)a3, 5u, &v12);
}

```

## disassembly

```asm
0x18002b94c  push    rbp
0x18002b94e  lea     rbp, [rsp-47h]
0x18002b953  sub     rsp, 90h
0x18002b95a  mov     rax, cs:__security_cookie
0x18002b961  xor     rax, rsp
0x18002b964  mov     [rbp+47h+var_10], rax
0x18002b968  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b96c  xor     r10d, r10d
0x18002b96f  mov     edx, 0Ah
0x18002b974  test    r8, r8
0x18002b977  jz      short loc_18002B98F
0x18002b979  mov     rcx, rax
0x18002b97c  inc     rcx
0x18002b97f  cmp     [r8+rcx*2], r10w
0x18002b984  jnz     short loc_18002B97C
0x18002b986  lea     ecx, ds:2[rcx*2]
0x18002b98d  jmp     short loc_18002B991
0x18002b98f  mov     ecx, edx
0x18002b991  test    r8, r8
0x18002b994  mov     [rbp+47h+var_48], ecx
0x18002b997  lea     r11, aNull_0; "NULL"
0x18002b99e  mov     [rbp+47h+var_44], r10d
0x18002b9a2  cmovz   r8, r11
0x18002b9a6  mov     [rbp+47h+var_50], r8
0x18002b9aa  test    r9, r9
0x18002b9ad  jz      short loc_18002B9C3
0x18002b9af  inc     rax
0x18002b9b2  cmp     [r9+rax*2], r10w
0x18002b9b7  jnz     short loc_18002B9AF
0x18002b9b9  lea     edx, ds:2[rax*2]
0x18002b9c0  test    r9, r9
0x18002b9c3  cmovz   r9, r11
0x18002b9c7  mov     [rbp+47h+var_38], edx
0x18002b9ca  lea     rax, [rbp+47h+arg_20]
0x18002b9ce  mov     [rbp+47h+var_40], r9
0x18002b9d2  mov     [rbp+47h+var_30], rax
0x18002b9d6  lea     rdx, AccountLockedOut
0x18002b9dd  lea     rax, [rbp+47h+arg_28]
0x18002b9e1  mov     [rbp+47h+var_34], r10d
0x18002b9e5  mov     [rbp+47h+var_20], rax
0x18002b9e9  mov     r9d, 5
0x18002b9ef  lea     rax, [rbp+47h+var_60]
0x18002b9f3  mov     [rbp+47h+var_28], 4
0x18002b9fb  mov     [rsp+90h+var_70], rax
0x18002ba00  mov     [rbp+47h+var_18], 4
0x18002ba08  call    McGenEventWrite_EventWriteTransfer
0x18002ba0d  mov     rcx, [rbp+47h+var_10]
0x18002ba11  xor     rcx, rsp; StackCookie
0x18002ba14  call    __security_check_cookie
0x18002ba19  add     rsp, 90h
0x18002ba20  pop     rbp
0x18002ba21  retn
```
