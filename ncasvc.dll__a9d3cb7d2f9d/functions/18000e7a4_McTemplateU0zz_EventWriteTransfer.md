# McTemplateU0zz_EventWriteTransfer

- ea: `0x18000e7a4`
- end: `0x18000e856`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `178`
- prototype: `ULONG __fastcall(__int64, __int64, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e85c`
- `0x18000f090`

## callees

- `0x180004c2c`
- `0x18000e7a4`
- `0x18001cc70`

## pseudocode

```c
ULONG __fastcall McTemplateU0zz_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // edx
  __int64 v6; // rcx
  __int64 v7; // rcx
  bool v8; // zf
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v11; // [rsp+40h] [rbp-38h]
  int v12; // [rsp+48h] [rbp-30h]
  int v13; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v14; // [rsp+50h] [rbp-28h]
  int v15; // [rsp+58h] [rbp-20h]
  int v16; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  v5 = 10;
  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    v7 = (unsigned int)(2 * v6 + 2);
  }
  else
  {
    v7 = 10;
  }
  v12 = v7;
  v13 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v11 = a3;
  v8 = a4 == 0;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
    v8 = a4 == 0;
  }
  if ( v8 )
    a4 = L"NULL";
  v15 = v5;
  v14 = a4;
  v16 = 0;
  return McGenEventWrite_EventWriteTransfer(v7, (const EVENT_DESCRIPTOR *)Trigger, (__int64)a3, 3u, &v10);
}

```

## disassembly

```asm
0x18000e7a4  sub     rsp, 78h
0x18000e7a8  mov     rax, cs:__security_cookie
0x18000e7af  xor     rax, rsp
0x18000e7b2  mov     [rsp+78h+var_18], rax
0x18000e7b7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e7bb  xor     r10d, r10d
0x18000e7be  mov     edx, 0Ah
0x18000e7c3  test    r8, r8
0x18000e7c6  jz      short loc_18000E7DE
0x18000e7c8  mov     rcx, rax
0x18000e7cb  inc     rcx
0x18000e7ce  cmp     [r8+rcx*2], r10w
0x18000e7d3  jnz     short loc_18000E7CB
0x18000e7d5  lea     ecx, ds:2[rcx*2]
0x18000e7dc  jmp     short loc_18000E7E0
0x18000e7de  mov     ecx, edx
0x18000e7e0  test    r8, r8
0x18000e7e3  mov     [rsp+78h+var_30], ecx
0x18000e7e7  lea     r11, aNull_0; "NULL"
0x18000e7ee  mov     [rsp+78h+var_2C], r10d
0x18000e7f3  cmovz   r8, r11
0x18000e7f7  mov     [rsp+78h+var_38], r8
0x18000e7fc  test    r9, r9
0x18000e7ff  jz      short loc_18000E815
0x18000e801  inc     rax
0x18000e804  cmp     [r9+rax*2], r10w
0x18000e809  jnz     short loc_18000E801
0x18000e80b  lea     edx, ds:2[rax*2]
0x18000e812  test    r9, r9
0x18000e815  cmovz   r9, r11
0x18000e819  mov     [rsp+78h+var_20], edx
0x18000e81d  mov     [rsp+78h+var_28], r9
0x18000e822  lea     rax, [rsp+78h+var_48]
0x18000e827  mov     r9d, 3
0x18000e82d  mov     [rsp+78h+var_1C], r10d
0x18000e832  lea     rdx, Trigger
0x18000e839  mov     [rsp+78h+var_58], rax
0x18000e83e  call    McGenEventWrite_EventWriteTransfer
0x18000e843  mov     rcx, [rsp+78h+var_18]
0x18000e848  xor     rcx, rsp; StackCookie
0x18000e84b  call    __security_check_cookie
0x18000e850  add     rsp, 78h
0x18000e854  retn
```
