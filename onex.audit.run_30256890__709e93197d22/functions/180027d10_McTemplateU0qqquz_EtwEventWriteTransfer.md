# McTemplateU0qqquz_EtwEventWriteTransfer

- ea: `0x180027d10`
- end: `0x180027de6`
- name: `McTemplateU0qqquz_EtwEventWriteTransfer`
- size: `214`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008d40`
- `0x18001d5b4`

## callees

- `0x1800053e0`
- `0x180020250`
- `0x180027d10`

## pseudocode

```c
__int64 __fastcall McTemplateU0qqquz_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        char a5,
        char a6,
        const wchar_t *a7)
{
  const wchar_t *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  _BYTE v11[16]; // [rsp+30h] [rbp-31h] BYREF
  int *v12; // [rsp+40h] [rbp-21h]
  __int64 v13; // [rsp+48h] [rbp-19h]
  int *v14; // [rsp+50h] [rbp-11h]
  __int64 v15; // [rsp+58h] [rbp-9h]
  char *v16; // [rsp+60h] [rbp-1h]
  __int64 v17; // [rsp+68h] [rbp+7h]
  char *v18; // [rsp+70h] [rbp+Fh]
  __int64 v19; // [rsp+78h] [rbp+17h]
  const wchar_t *v20; // [rsp+80h] [rbp+1Fh]
  int v21; // [rsp+88h] [rbp+27h]
  int v22; // [rsp+8Ch] [rbp+2Bh]
  int v23; // [rsp+C0h] [rbp+5Fh] BYREF
  int v24; // [rsp+C8h] [rbp+67h] BYREF

  v24 = a4;
  v23 = a3;
  v7 = a7;
  v12 = &v23;
  v13 = 4;
  v14 = &v24;
  v16 = &a5;
  v18 = &a6;
  v15 = 4;
  v17 = 4;
  v19 = 1;
  if ( a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a7[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v21 = v9;
  v22 = 0;
  if ( !a7 )
    v7 = L"NULL";
  v20 = v7;
  return McGenEventWrite_EtwEventWriteTransfer((__int64)v7, (__int64)EAPError, 0, 6, (__int64)v11);
}

```

## disassembly

```asm
0x180027d10  mov     [rsp-8+arg_18], r9d
0x180027d15  mov     [rsp-8+arg_10], r8d
0x180027d1a  push    rbp
0x180027d1b  lea     rbp, [rsp-3Fh]
0x180027d20  sub     rsp, 0A0h
0x180027d27  mov     rax, cs:__security_cookie
0x180027d2e  xor     rax, rsp
0x180027d31  mov     [rbp+3Fh+var_10], rax
0x180027d35  mov     rcx, [rbp+3Fh+arg_30]
0x180027d39  lea     rax, [rbp+3Fh+arg_10]
0x180027d3d  mov     [rbp+3Fh+var_60], rax
0x180027d41  xor     r8d, r8d
0x180027d44  mov     [rbp+3Fh+var_58], 4
0x180027d4c  lea     rax, [rbp+3Fh+arg_18]
0x180027d50  mov     [rbp+3Fh+var_50], rax
0x180027d54  lea     rax, [rbp+3Fh+arg_20]
0x180027d58  mov     [rbp+3Fh+var_40], rax
0x180027d5c  lea     rax, [rbp+3Fh+arg_28]
0x180027d60  mov     [rbp+3Fh+var_30], rax
0x180027d64  mov     [rbp+3Fh+var_48], 4
0x180027d6c  mov     [rbp+3Fh+var_38], 4
0x180027d74  mov     [rbp+3Fh+var_28], 1
0x180027d7c  test    rcx, rcx
0x180027d7f  jz      short loc_180027D98
0x180027d81  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027d85  inc     rax
0x180027d88  cmp     [rcx+rax*2], r8w
0x180027d8d  jnz     short loc_180027D85
0x180027d8f  lea     eax, ds:2[rax*2]
0x180027d96  jmp     short loc_180027D9D
0x180027d98  mov     eax, 0Ah
0x180027d9d  test    rcx, rcx
0x180027da0  mov     [rbp+3Fh+var_18], eax
0x180027da3  lea     rdx, aNull_0; "NULL"
0x180027daa  mov     [rbp+3Fh+var_14], r8d
0x180027dae  cmovz   rcx, rdx
0x180027db2  lea     rax, [rbp+3Fh+var_70]
0x180027db6  lea     rdx, EAPError
0x180027dbd  mov     [rbp+3Fh+var_20], rcx
0x180027dc1  mov     r9d, 6
0x180027dc7  mov     [rsp+0A0h+var_80], rax
0x180027dcc  call    McGenEventWrite_EtwEventWriteTransfer
0x180027dd1  mov     rcx, [rbp+3Fh+var_10]
0x180027dd5  xor     rcx, rsp; StackCookie
0x180027dd8  call    __security_check_cookie
0x180027ddd  add     rsp, 0A0h
0x180027de4  pop     rbp
0x180027de5  retn
```
