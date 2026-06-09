# McTemplateU0zz_EventWriteTransfer

- ea: `0x18000b200`
- end: `0x18000b2b4`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007d5c`

## callees

- `0x18000b06c`
- `0x18000b200`
- `0x1800136b0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  __int64 v4; // rax
  int v6; // edx
  __int64 v7; // rcx
  __int64 v8; // rcx
  bool v9; // zf
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v12; // [rsp+40h] [rbp-38h]
  int v13; // [rsp+48h] [rbp-30h]
  int v14; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v15; // [rsp+50h] [rbp-28h]
  int v16; // [rsp+58h] [rbp-20h]
  int v17; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  v6 = 10;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = (unsigned int)(2 * v7 + 2);
  }
  else
  {
    v8 = 10;
  }
  v13 = v8;
  v14 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v12 = a3;
  v9 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v6 = 2 * v4 + 2;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = L"NULL";
  v16 = v6;
  v15 = a4;
  v17 = 0;
  return McGenEventWrite_EventWriteTransfer(v8, a2, (__int64)a3, 3u, &v11);
}

```

## disassembly

```asm
0x18000b200  push    rbx
0x18000b202  sub     rsp, 70h
0x18000b206  mov     rax, cs:__security_cookie
0x18000b20d  xor     rax, rsp
0x18000b210  mov     [rsp+78h+var_18], rax
0x18000b215  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b219  xor     r11d, r11d
0x18000b21c  mov     r10, rdx
0x18000b21f  mov     edx, 0Ah
0x18000b224  test    r8, r8
0x18000b227  jz      short loc_18000B23F
0x18000b229  mov     rcx, rax
0x18000b22c  inc     rcx
0x18000b22f  cmp     [r8+rcx*2], r11w
0x18000b234  jnz     short loc_18000B22C
0x18000b236  lea     ecx, ds:2[rcx*2]
0x18000b23d  jmp     short loc_18000B241
0x18000b23f  mov     ecx, edx
0x18000b241  test    r8, r8
0x18000b244  mov     [rsp+78h+var_30], ecx
0x18000b248  lea     rbx, aNull; "NULL"
0x18000b24f  mov     [rsp+78h+var_2C], r11d
0x18000b254  cmovz   r8, rbx
0x18000b258  mov     [rsp+78h+var_38], r8
0x18000b25d  test    r9, r9
0x18000b260  jz      short loc_18000B276
0x18000b262  inc     rax
0x18000b265  cmp     [r9+rax*2], r11w
0x18000b26a  jnz     short loc_18000B262
0x18000b26c  lea     edx, ds:2[rax*2]
0x18000b273  test    r9, r9
0x18000b276  cmovz   r9, rbx
0x18000b27a  mov     [rsp+78h+var_20], edx
0x18000b27e  mov     [rsp+78h+var_28], r9
0x18000b283  lea     rax, [rsp+78h+var_48]
0x18000b288  mov     r9d, 3
0x18000b28e  mov     [rsp+78h+var_1C], r11d
0x18000b293  mov     rdx, r10
0x18000b296  mov     [rsp+78h+var_58], rax
0x18000b29b  call    McGenEventWrite_EventWriteTransfer
0x18000b2a0  mov     rcx, [rsp+78h+var_18]
0x18000b2a5  xor     rcx, rsp; StackCookie
0x18000b2a8  call    __security_check_cookie
0x18000b2ad  add     rsp, 70h
0x18000b2b1  pop     rbx
0x18000b2b2  retn
```
