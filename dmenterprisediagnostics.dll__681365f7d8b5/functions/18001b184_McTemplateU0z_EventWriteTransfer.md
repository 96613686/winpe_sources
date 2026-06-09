# McTemplateU0z_EventWriteTransfer

- ea: `0x18001b184`
- end: `0x18001b1ff`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a090`
- `0x18001a8b0`

## callees

- `0x180001800`
- `0x18001b0cc`
- `0x18001b184`

## pseudocode

```c
ULONG __fastcall McTemplateU0z_EventWriteTransfer(__int64 a1, const EVENT_DESCRIPTOR *a2, const wchar_t *a3)
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
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", a2, (__int64)a3, 2u, &v6);
}

```

## disassembly

```asm
0x18001b184  sub     rsp, 68h
0x18001b188  mov     rax, cs:__security_cookie
0x18001b18f  xor     rax, rsp
0x18001b192  mov     [rsp+68h+var_18], rax
0x18001b197  xor     r9d, r9d
0x18001b19a  test    r8, r8
0x18001b19d  jz      short loc_18001B1B6
0x18001b19f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b1a3  inc     rax
0x18001b1a6  cmp     [r8+rax*2], r9w
0x18001b1ab  jnz     short loc_18001B1A3
0x18001b1ad  lea     eax, ds:2[rax*2]
0x18001b1b4  jmp     short loc_18001B1BB
0x18001b1b6  mov     eax, 0Ah
0x18001b1bb  test    r8, r8
0x18001b1be  mov     [rsp+68h+var_20], eax
0x18001b1c2  lea     rcx, aNull; "NULL"
0x18001b1c9  mov     [rsp+68h+var_1C], r9d
0x18001b1ce  cmovz   r8, rcx
0x18001b1d2  lea     rax, [rsp+68h+var_38]
0x18001b1d7  mov     r9d, 2
0x18001b1dd  mov     [rsp+68h+var_28], r8
0x18001b1e2  mov     [rsp+68h+var_48], rax
0x18001b1e7  call    McGenEventWrite_EventWriteTransfer
0x18001b1ec  mov     rcx, [rsp+68h+var_18]
0x18001b1f1  xor     rcx, rsp; StackCookie
0x18001b1f4  call    __security_check_cookie
0x18001b1f9  add     rsp, 68h
0x18001b1fd  retn
```
