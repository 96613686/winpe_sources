# McTemplateU0zzpq_EtwEventWriteTransfer

- ea: `0x180012d14`
- end: `0x180012dea`
- name: `McTemplateU0zzpq_EtwEventWriteTransfer`
- size: `214`
- prototype: `__int64 __fastcall(__int64, __int64, const wchar_t *, const wchar_t *, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011d10`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x180012d14`

## pseudocode

```c
__int64 __fastcall McTemplateU0zzpq_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5,
        char a6)
{
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rcx
  bool v10; // zf
  _BYTE v12[16]; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-9h]
  int v14; // [rsp+48h] [rbp-1h]
  int v15; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v16; // [rsp+50h] [rbp+7h]
  int v17; // [rsp+58h] [rbp+Fh]
  int v18; // [rsp+5Ch] [rbp+13h]
  char *v19; // [rsp+60h] [rbp+17h]
  __int64 v20; // [rsp+68h] [rbp+1Fh]
  char *v21; // [rsp+70h] [rbp+27h]
  __int64 v22; // [rsp+78h] [rbp+2Fh]

  v6 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
  }
  else
  {
    v9 = 10;
  }
  v14 = v9;
  v15 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v13 = a3;
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  v17 = v7;
  v16 = a4;
  v19 = &a5;
  v18 = 0;
  v21 = &a6;
  v20 = 8;
  v22 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(
           v9,
           (__int64)PERFLIB_BUFFER_ALIGNMENT_ERROR,
           (__int64)a3,
           5,
           (__int64)v12);
}

```

## disassembly

```asm
0x180012d14  push    rbp
0x180012d16  lea     rbp, [rsp-47h]
0x180012d1b  sub     rsp, 90h
0x180012d22  mov     rax, cs:__security_cookie
0x180012d29  xor     rax, rsp
0x180012d2c  mov     [rbp+47h+var_10], rax
0x180012d30  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012d34  xor     r10d, r10d
0x180012d37  mov     edx, 0Ah
0x180012d3c  test    r8, r8
0x180012d3f  jz      short loc_180012D57
0x180012d41  mov     rcx, rax
0x180012d44  inc     rcx
0x180012d47  cmp     [r8+rcx*2], r10w
0x180012d4c  jnz     short loc_180012D44
0x180012d4e  lea     ecx, ds:2[rcx*2]
0x180012d55  jmp     short loc_180012D59
0x180012d57  mov     ecx, edx
0x180012d59  test    r8, r8
0x180012d5c  mov     [rbp+47h+var_48], ecx
0x180012d5f  lea     r11, aNull_0; "NULL"
0x180012d66  mov     [rbp+47h+var_44], r10d
0x180012d6a  cmovz   r8, r11
0x180012d6e  mov     [rbp+47h+var_50], r8
0x180012d72  test    r9, r9
0x180012d75  jz      short loc_180012D8B
0x180012d77  inc     rax
0x180012d7a  cmp     [r9+rax*2], r10w
0x180012d7f  jnz     short loc_180012D77
0x180012d81  lea     edx, ds:2[rax*2]
0x180012d88  test    r9, r9
0x180012d8b  cmovz   r9, r11
0x180012d8f  mov     [rbp+47h+var_38], edx
0x180012d92  lea     rax, [rbp+47h+arg_20]
0x180012d96  mov     [rbp+47h+var_40], r9
0x180012d9a  mov     [rbp+47h+var_30], rax
0x180012d9e  lea     rdx, PERFLIB_BUFFER_ALIGNMENT_ERROR
0x180012da5  lea     rax, [rbp+47h+arg_28]
0x180012da9  mov     [rbp+47h+var_34], r10d
0x180012dad  mov     [rbp+47h+var_20], rax
0x180012db1  mov     r9d, 5
0x180012db7  lea     rax, [rbp+47h+var_60]
0x180012dbb  mov     [rbp+47h+var_28], 8
0x180012dc3  mov     [rsp+90h+var_70], rax
0x180012dc8  mov     [rbp+47h+var_18], 4
0x180012dd0  call    McGenEventWrite_EtwEventWriteTransfer
0x180012dd5  mov     rcx, [rbp+47h+var_10]
0x180012dd9  xor     rcx, rsp; StackCookie
0x180012ddc  call    __security_check_cookie
0x180012de1  add     rsp, 90h
0x180012de8  pop     rbp
0x180012de9  retn
```
