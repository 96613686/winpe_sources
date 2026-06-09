# McTemplateU0z_EventWriteTransfer

- ea: `0x180003314`
- end: `0x18000338e`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `122`
- prototype: `ULONG __fastcall(REGHANDLE *, const EVENT_DESCRIPTOR *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002f28`

## callees

- `0x180001460`
- `0x1800032c0`
- `0x180003314`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(REGHANDLE *a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
{
  __int64 v3; // rax
  int v4; // eax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = 2 * v3 + 2;
  }
  else
  {
    v4 = 10;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v7 = a3;
  return McGenEventWrite_EventWriteTransfer(a1, a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x180003314  sub     rsp, 68h
0x180003318  mov     rax, cs:__security_cookie
0x18000331f  xor     rax, rsp
0x180003322  mov     [rsp+68h+var_18], rax
0x180003327  xor     r10d, r10d
0x18000332a  test    r8, r8
0x18000332d  jz      short loc_180003346
0x18000332f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003333  inc     rax
0x180003336  cmp     [r8+rax*2], r10w
0x18000333b  jnz     short loc_180003333
0x18000333d  lea     eax, ds:2[rax*2]
0x180003344  jmp     short loc_18000334B
0x180003346  mov     eax, 0Ah
0x18000334b  lea     r9, aNull; "NULL"
0x180003352  mov     [rsp+68h+var_20], eax
0x180003356  test    r8, r8
0x180003359  mov     [rsp+68h+var_1C], r10d
0x18000335e  lea     rax, [rsp+68h+var_38]
0x180003363  cmovz   r8, r9
0x180003367  mov     [rsp+68h+var_48], rax
0x18000336c  mov     r9d, 2
0x180003372  mov     [rsp+68h+var_28], r8
0x180003377  call    McGenEventWrite_EventWriteTransfer
0x18000337c  mov     rcx, [rsp+68h+var_18]
0x180003381  xor     rcx, rsp; StackCookie
0x180003384  call    __security_check_cookie
0x180003389  add     rsp, 68h
0x18000338d  retn
```
