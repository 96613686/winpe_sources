# McTemplateU0zq_EventWriteTransfer

- ea: `0x180007878`
- end: `0x18000790d`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e70`
- `0x180007920`
- `0x18000e100`
- `0x180012890`
- `0x180013954`
- `0x180013d28`
- `0x1800156f5`

## callees

- `0x180001770`
- `0x1800077a0`
- `0x180007878`

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
0x180007878  mov     [rsp+arg_18], r9d
0x18000787d  sub     rsp, 78h
0x180007881  mov     rax, cs:__security_cookie
0x180007888  xor     rax, rsp
0x18000788b  mov     [rsp+78h+var_18], rax
0x180007890  xor     r9d, r9d
0x180007893  test    r8, r8
0x180007896  jz      short loc_1800078AF
0x180007898  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000789c  inc     rax
0x18000789f  cmp     [r8+rax*2], r9w
0x1800078a4  jnz     short loc_18000789C
0x1800078a6  lea     eax, ds:2[rax*2]
0x1800078ad  jmp     short loc_1800078B4
0x1800078af  mov     eax, 0Ah
0x1800078b4  mov     [rsp+78h+var_30], eax
0x1800078b8  lea     rcx, aNull; "NULL"
0x1800078bf  lea     rax, [rsp+78h+arg_18]
0x1800078c7  mov     [rsp+78h+var_2C], r9d
0x1800078cc  test    r8, r8
0x1800078cf  mov     [rsp+78h+var_28], rax
0x1800078d4  lea     rax, [rsp+78h+var_48]
0x1800078d9  mov     [rsp+78h+var_20], 4
0x1800078e2  cmovz   r8, rcx
0x1800078e6  mov     [rsp+78h+var_58], rax
0x1800078eb  mov     r9d, 3
0x1800078f1  mov     [rsp+78h+var_38], r8
0x1800078f6  call    McGenEventWrite_EventWriteTransfer
0x1800078fb  mov     rcx, [rsp+78h+var_18]
0x180007900  xor     rcx, rsp; StackCookie
0x180007903  call    __security_check_cookie
0x180007908  add     rsp, 78h
0x18000790c  retn
```
