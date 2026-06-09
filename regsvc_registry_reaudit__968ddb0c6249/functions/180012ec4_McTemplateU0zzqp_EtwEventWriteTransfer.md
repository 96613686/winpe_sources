# McTemplateU0zzqp_EtwEventWriteTransfer

- ea: `0x180012ec4`
- end: `0x180012fa5`
- name: `McTemplateU0zzqp_EtwEventWriteTransfer`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800119fc`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x180012ec4`

## pseudocode

```c
__int64 __fastcall McTemplateU0zzqp_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5,
        char a6)
{
  __int64 v6; // rax
  int v8; // edx
  __int64 v9; // rcx
  __int64 v10; // rcx
  bool v11; // zf
  _BYTE v13[16]; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-9h]
  int v15; // [rsp+48h] [rbp-1h]
  int v16; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v17; // [rsp+50h] [rbp+7h]
  int v18; // [rsp+58h] [rbp+Fh]
  int v19; // [rsp+5Ch] [rbp+13h]
  char *v20; // [rsp+60h] [rbp+17h]
  __int64 v21; // [rsp+68h] [rbp+1Fh]
  char *v22; // [rsp+70h] [rbp+27h]
  __int64 v23; // [rsp+78h] [rbp+2Fh]

  v6 = -1;
  v8 = 10;
  if ( a3 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = (unsigned int)(2 * v9 + 2);
  }
  else
  {
    v10 = 10;
  }
  v15 = v10;
  v16 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v14 = a3;
  v11 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v8 = 2 * v6 + 2;
    v11 = a4 == 0;
  }
  if ( v11 )
    a4 = L"NULL";
  v18 = v8;
  v17 = a4;
  v20 = &a5;
  v19 = 0;
  v22 = &a6;
  v21 = 4;
  v23 = 8;
  return McGenEventWrite_EtwEventWriteTransfer(v10, a2, (__int64)a3, 5, (__int64)v13);
}

```

## disassembly

```asm
0x180012ec4  mov     [rsp-8+arg_0], rbx
0x180012ec9  push    rbp
0x180012eca  lea     rbp, [rsp-47h]
0x180012ecf  sub     rsp, 90h
0x180012ed6  mov     rax, cs:__security_cookie
0x180012edd  xor     rax, rsp
0x180012ee0  mov     [rbp+47h+var_10], rax
0x180012ee4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012ee8  xor     r11d, r11d
0x180012eeb  mov     r10, rdx
0x180012eee  mov     edx, 0Ah
0x180012ef3  test    r8, r8
0x180012ef6  jz      short loc_180012F0E
0x180012ef8  mov     rcx, rax
0x180012efb  inc     rcx
0x180012efe  cmp     [r8+rcx*2], r11w
0x180012f03  jnz     short loc_180012EFB
0x180012f05  lea     ecx, ds:2[rcx*2]
0x180012f0c  jmp     short loc_180012F10
0x180012f0e  mov     ecx, edx
0x180012f10  test    r8, r8
0x180012f13  mov     [rbp+47h+var_48], ecx
0x180012f16  lea     rbx, aNull_0; "NULL"
0x180012f1d  mov     [rbp+47h+var_44], r11d
0x180012f21  cmovz   r8, rbx
0x180012f25  mov     [rbp+47h+var_50], r8
0x180012f29  test    r9, r9
0x180012f2c  jz      short loc_180012F42
0x180012f2e  inc     rax
0x180012f31  cmp     [r9+rax*2], r11w
0x180012f36  jnz     short loc_180012F2E
0x180012f38  lea     edx, ds:2[rax*2]
0x180012f3f  test    r9, r9
0x180012f42  cmovz   r9, rbx
0x180012f46  mov     [rbp+47h+var_38], edx
0x180012f49  lea     rax, [rbp+47h+arg_20]
0x180012f4d  mov     [rbp+47h+var_40], r9
0x180012f51  mov     [rbp+47h+var_30], rax
0x180012f55  mov     r9d, 5
0x180012f5b  lea     rax, [rbp+47h+arg_28]
0x180012f5f  mov     [rbp+47h+var_34], r11d
0x180012f63  mov     [rbp+47h+var_20], rax
0x180012f67  mov     rdx, r10
0x180012f6a  lea     rax, [rbp+47h+var_60]
0x180012f6e  mov     [rbp+47h+var_28], 4
0x180012f76  mov     [rsp+90h+var_70], rax
0x180012f7b  mov     [rbp+47h+var_18], 8
0x180012f83  call    McGenEventWrite_EtwEventWriteTransfer
0x180012f88  mov     rcx, [rbp+47h+var_10]
0x180012f8c  xor     rcx, rsp; StackCookie
0x180012f8f  call    __security_check_cookie
0x180012f94  mov     rbx, [rsp+90h+arg_0]
0x180012f9c  add     rsp, 90h
0x180012fa3  pop     rbp
0x180012fa4  retn
```
