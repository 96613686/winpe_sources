# McTemplateU0z_EventWriteTransfer

- ea: `0x18000b17c`
- end: `0x18000b1f7`
- name: `McTemplateU0z_EventWriteTransfer`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007d5c`

## callees

- `0x18000b06c`
- `0x18000b17c`
- `0x1800136b0`

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
0x18000b17c  sub     rsp, 68h
0x18000b180  mov     rax, cs:__security_cookie
0x18000b187  xor     rax, rsp
0x18000b18a  mov     [rsp+68h+var_18], rax
0x18000b18f  xor     r9d, r9d
0x18000b192  test    r8, r8
0x18000b195  jz      short loc_18000B1AE
0x18000b197  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b19b  inc     rax
0x18000b19e  cmp     [r8+rax*2], r9w
0x18000b1a3  jnz     short loc_18000B19B
0x18000b1a5  lea     eax, ds:2[rax*2]
0x18000b1ac  jmp     short loc_18000B1B3
0x18000b1ae  mov     eax, 0Ah
0x18000b1b3  test    r8, r8
0x18000b1b6  mov     [rsp+68h+var_20], eax
0x18000b1ba  lea     rcx, aNull; "NULL"
0x18000b1c1  mov     [rsp+68h+var_1C], r9d
0x18000b1c6  cmovz   r8, rcx
0x18000b1ca  lea     rax, [rsp+68h+var_38]
0x18000b1cf  mov     r9d, 2
0x18000b1d5  mov     [rsp+68h+var_28], r8
0x18000b1da  mov     [rsp+68h+var_48], rax
0x18000b1df  call    McGenEventWrite_EventWriteTransfer
0x18000b1e4  mov     rcx, [rsp+68h+var_18]
0x18000b1e9  xor     rcx, rsp; StackCookie
0x18000b1ec  call    __security_check_cookie
0x18000b1f1  add     rsp, 68h
0x18000b1f5  retn
```
