# McTemplateU0zq_EventWriteTransfer

- ea: `0x1800268f0`
- end: `0x180026986`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180021b10`
- `0x1800285a0`
- `0x18002aae8`
- `0x18002b4e0`

## callees

- `0x18001ada8`
- `0x1800268f0`
- `0x180031040`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 3u, &v7);
}

```

## disassembly

```asm
0x1800268f0  mov     [rsp+arg_18], r9d
0x1800268f5  sub     rsp, 78h
0x1800268f9  mov     rax, cs:__security_cookie
0x180026900  xor     rax, rsp
0x180026903  mov     [rsp+78h+var_18], rax
0x180026908  xor     r9d, r9d
0x18002690b  test    r8, r8
0x18002690e  jz      short loc_180026927
0x180026910  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026914  inc     rax
0x180026917  cmp     [r8+rax*2], r9w
0x18002691c  jnz     short loc_180026914
0x18002691e  lea     eax, ds:2[rax*2]
0x180026925  jmp     short loc_18002692C
0x180026927  mov     eax, 0Ah
0x18002692c  mov     [rsp+78h+var_30], eax
0x180026930  lea     rcx, aNull_0; "NULL"
0x180026937  lea     rax, [rsp+78h+arg_18]
0x18002693f  mov     [rsp+78h+var_2C], r9d
0x180026944  test    r8, r8
0x180026947  mov     [rsp+78h+var_28], rax
0x18002694c  lea     rax, [rsp+78h+var_48]
0x180026951  mov     [rsp+78h+var_20], 4
0x18002695a  cmovz   r8, rcx
0x18002695e  mov     [rsp+78h+var_58], rax
0x180026963  mov     r9d, 3
0x180026969  mov     [rsp+78h+var_38], r8
0x18002696e  call    McGenEventWrite_EventWriteTransfer
0x180026973  mov     rcx, [rsp+78h+var_18]
0x180026978  xor     rcx, rsp; StackCookie
0x18002697b  call    __security_check_cookie
0x180026980  add     rsp, 78h
0x180026984  retn
```
