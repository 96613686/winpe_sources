# McTemplateU0zp_EventWriteTransfer

- ea: `0x1400167e4`
- end: `0x140016873`
- name: `McTemplateU0zp_EventWriteTransfer`
- size: `143`
- prototype: `ULONG(__int64, const EVENT_DESCRIPTOR *, const char *, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400160d8`

## callees

- `0x140001570`
- `0x140016788`
- `0x1400167e4`

## pseudocode

```c
ULONG McTemplateU0zp_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const char *a3, ...)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  const char *v7; // [rsp+40h] [rbp-38h]
  int v8; // [rsp+48h] [rbp-30h]
  int v9; // [rsp+4Ch] [rbp-2Ch]
  va_list v10; // [rsp+50h] [rbp-28h]
  __int64 v11; // [rsp+58h] [rbp-20h]
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)&a3[2 * v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  va_copy(v10, va);
  v11 = 8;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 0, &v6);
}

```

## disassembly

```asm
0x1400167e4  mov     [rsp+arg_18], r9
0x1400167e9  sub     rsp, 78h
0x1400167ed  mov     rax, cs:__security_cookie
0x1400167f4  xor     rax, rsp
0x1400167f7  mov     [rsp+78h+var_18], rax
0x1400167fc  xor     r9d, r9d; int
0x1400167ff  test    r8, r8
0x140016802  jz      short loc_14001681B
0x140016804  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016808  inc     rax
0x14001680b  cmp     [r8+rax*2], r9w
0x140016810  jnz     short loc_140016808
0x140016812  lea     eax, ds:2[rax*2]
0x140016819  jmp     short loc_140016820
0x14001681b  mov     eax, 0Ah
0x140016820  mov     [rsp+78h+var_30], eax
0x140016824  lea     rcx, aNull; "NULL"
0x14001682b  lea     rax, [rsp+78h+arg_18]
0x140016833  mov     [rsp+78h+var_2C], r9d
0x140016838  test    r8, r8
0x14001683b  mov     [rsp+78h+var_28], rax
0x140016840  lea     rax, [rsp+78h+var_48]
0x140016845  mov     [rsp+78h+var_20], 8
0x14001684e  cmovz   r8, rcx; int
0x140016852  mov     [rsp+78h+var_58], rax; PEVENT_DATA_DESCRIPTOR
0x140016857  mov     [rsp+78h+var_38], r8
0x14001685c  call    McGenEventWrite_EventWriteTransfer
0x140016861  mov     rcx, [rsp+78h+var_18]
0x140016866  xor     rcx, rsp; StackCookie
0x140016869  call    __security_check_cookie
0x14001686e  add     rsp, 78h
0x140016872  retn
```
