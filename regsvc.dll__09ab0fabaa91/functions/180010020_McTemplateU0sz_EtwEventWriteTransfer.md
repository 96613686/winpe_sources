# McTemplateU0sz_EtwEventWriteTransfer

- ea: `0x180010020`
- end: `0x1800100d7`
- name: `McTemplateU0sz_EtwEventWriteTransfer`
- size: `183`
- prototype: `__int64 __fastcall(__int64, __int64, const char *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e1a8`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x180010020`

## pseudocode

```c
__int64 __fastcall McTemplateU0sz_EtwEventWriteTransfer(__int64 a1, __int64 a2, const char *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // ecx
  int v7; // eax
  _BYTE v9[16]; // [rsp+30h] [rbp-48h] BYREF
  const char *v10; // [rsp+40h] [rbp-38h]
  int v11; // [rsp+48h] [rbp-30h]
  int v12; // [rsp+4Ch] [rbp-2Ch]
  const wchar_t *v13; // [rsp+50h] [rbp-28h]
  int v14; // [rsp+58h] [rbp-20h]
  int v15; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v6 = v5 + 1;
  }
  else
  {
    v6 = 5;
  }
  v11 = v6;
  v12 = 0;
  if ( !a3 )
    a3 = "NULL";
  v10 = a3;
  if ( a4 )
  {
    do
      ++v4;
    while ( a4[v4] );
    v7 = 2 * v4 + 2;
  }
  else
  {
    v7 = 10;
  }
  v14 = v7;
  v15 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v13 = a4;
  return McGenEventWrite_EtwEventWriteTransfer(
           (__int64)L"NULL",
           (__int64)PERFLIB_PROC_NAME_NOT_FOUND,
           (__int64)a3,
           3,
           (__int64)v9);
}

```

## disassembly

```asm
0x180010020  sub     rsp, 78h
0x180010024  mov     rax, cs:__security_cookie
0x18001002b  xor     rax, rsp
0x18001002e  mov     [rsp+78h+var_18], rax
0x180010033  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010037  xor     r10d, r10d
0x18001003a  test    r8, r8
0x18001003d  jz      short loc_18001004F
0x18001003f  mov     rcx, rax
0x180010042  inc     rcx
0x180010045  cmp     [r8+rcx], r10b
0x180010049  jnz     short loc_180010042
0x18001004b  inc     ecx
0x18001004d  jmp     short loc_180010054
0x18001004f  mov     ecx, 5
0x180010054  test    r8, r8
0x180010057  mov     [rsp+78h+var_30], ecx
0x18001005b  lea     rdx, aNull; "NULL"
0x180010062  mov     [rsp+78h+var_2C], r10d
0x180010067  cmovz   r8, rdx
0x18001006b  mov     [rsp+78h+var_38], r8
0x180010070  test    r9, r9
0x180010073  jz      short loc_180010088
0x180010075  inc     rax
0x180010078  cmp     [r9+rax*2], r10w
0x18001007d  jnz     short loc_180010075
0x18001007f  lea     eax, ds:2[rax*2]
0x180010086  jmp     short loc_18001008D
0x180010088  mov     eax, 0Ah
0x18001008d  test    r9, r9
0x180010090  mov     [rsp+78h+var_20], eax
0x180010094  lea     rcx, aNull_0; "NULL"
0x18001009b  mov     [rsp+78h+var_1C], r10d
0x1800100a0  cmovz   r9, rcx
0x1800100a4  lea     rax, [rsp+78h+var_48]
0x1800100a9  mov     [rsp+78h+var_28], r9
0x1800100ae  lea     rdx, PERFLIB_PROC_NAME_NOT_FOUND
0x1800100b5  mov     r9d, 3
0x1800100bb  mov     [rsp+78h+var_58], rax
0x1800100c0  call    McGenEventWrite_EtwEventWriteTransfer
0x1800100c5  mov     rcx, [rsp+78h+var_18]
0x1800100ca  xor     rcx, rsp; StackCookie
0x1800100cd  call    __security_check_cookie
0x1800100d2  add     rsp, 78h
0x1800100d6  retn
```
