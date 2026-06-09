# McTemplateU0zz_EventWriteTransfer

- ea: `0x18002b894`
- end: `0x18002b946`
- name: `McTemplateU0zz_EventWriteTransfer`
- size: `178`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800279f8`
- `0x180027af8`

## callees

- `0x18001ada8`
- `0x18002b894`
- `0x180031040`

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
  return McGenEventWrite_EventWriteTransfer(
           v7,
           (const EVENT_DESCRIPTOR *)UnprotectedPasswordBlocked,
           (__int64)a3,
           3u,
           &v10);
}

```

## disassembly

```asm
0x18002b894  sub     rsp, 78h
0x18002b898  mov     rax, cs:__security_cookie
0x18002b89f  xor     rax, rsp
0x18002b8a2  mov     [rsp+78h+var_18], rax
0x18002b8a7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b8ab  xor     r10d, r10d
0x18002b8ae  mov     edx, 0Ah
0x18002b8b3  test    r8, r8
0x18002b8b6  jz      short loc_18002B8CE
0x18002b8b8  mov     rcx, rax
0x18002b8bb  inc     rcx
0x18002b8be  cmp     [r8+rcx*2], r10w
0x18002b8c3  jnz     short loc_18002B8BB
0x18002b8c5  lea     ecx, ds:2[rcx*2]
0x18002b8cc  jmp     short loc_18002B8D0
0x18002b8ce  mov     ecx, edx
0x18002b8d0  test    r8, r8
0x18002b8d3  mov     [rsp+78h+var_30], ecx
0x18002b8d7  lea     r11, aNull_0; "NULL"
0x18002b8de  mov     [rsp+78h+var_2C], r10d
0x18002b8e3  cmovz   r8, r11
0x18002b8e7  mov     [rsp+78h+var_38], r8
0x18002b8ec  test    r9, r9
0x18002b8ef  jz      short loc_18002B905
0x18002b8f1  inc     rax
0x18002b8f4  cmp     [r9+rax*2], r10w
0x18002b8f9  jnz     short loc_18002B8F1
0x18002b8fb  lea     edx, ds:2[rax*2]
0x18002b902  test    r9, r9
0x18002b905  cmovz   r9, r11
0x18002b909  mov     [rsp+78h+var_20], edx
0x18002b90d  mov     [rsp+78h+var_28], r9
0x18002b912  lea     rax, [rsp+78h+var_48]
0x18002b917  mov     r9d, 3
0x18002b91d  mov     [rsp+78h+var_1C], r10d
0x18002b922  lea     rdx, UnprotectedPasswordBlocked
0x18002b929  mov     [rsp+78h+var_58], rax
0x18002b92e  call    McGenEventWrite_EventWriteTransfer
0x18002b933  mov     rcx, [rsp+78h+var_18]
0x18002b938  xor     rcx, rsp; StackCookie
0x18002b93b  call    __security_check_cookie
0x18002b940  add     rsp, 78h
0x18002b944  retn
```
