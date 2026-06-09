# McTemplateU0zzqq_EtwEventWriteTransfer

- ea: `0x180012fac`
- end: `0x18001308d`
- name: `McTemplateU0zzqq_EtwEventWriteTransfer`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180011d10`
- `0x18001277c`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x180012fac`

## pseudocode

```c
__int64 __fastcall McTemplateU0zzqq_EtwEventWriteTransfer(
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
  v23 = 4;
  return McGenEventWrite_EtwEventWriteTransfer(v10, a2, (__int64)a3, 5, (__int64)v13);
}

```

## disassembly

```asm
0x180012fac  mov     [rsp-8+arg_0], rbx
0x180012fb1  push    rbp
0x180012fb2  lea     rbp, [rsp-47h]
0x180012fb7  sub     rsp, 90h
0x180012fbe  mov     rax, cs:__security_cookie
0x180012fc5  xor     rax, rsp
0x180012fc8  mov     [rbp+47h+var_10], rax
0x180012fcc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012fd0  xor     r11d, r11d
0x180012fd3  mov     r10, rdx
0x180012fd6  mov     edx, 0Ah
0x180012fdb  test    r8, r8
0x180012fde  jz      short loc_180012FF6
0x180012fe0  mov     rcx, rax
0x180012fe3  inc     rcx
0x180012fe6  cmp     [r8+rcx*2], r11w
0x180012feb  jnz     short loc_180012FE3
0x180012fed  lea     ecx, ds:2[rcx*2]
0x180012ff4  jmp     short loc_180012FF8
0x180012ff6  mov     ecx, edx
0x180012ff8  test    r8, r8
0x180012ffb  mov     [rbp+47h+var_48], ecx
0x180012ffe  lea     rbx, aNull_0; "NULL"
0x180013005  mov     [rbp+47h+var_44], r11d
0x180013009  cmovz   r8, rbx
0x18001300d  mov     [rbp+47h+var_50], r8
0x180013011  test    r9, r9
0x180013014  jz      short loc_18001302A
0x180013016  inc     rax
0x180013019  cmp     [r9+rax*2], r11w
0x18001301e  jnz     short loc_180013016
0x180013020  lea     edx, ds:2[rax*2]
0x180013027  test    r9, r9
0x18001302a  cmovz   r9, rbx
0x18001302e  mov     [rbp+47h+var_38], edx
0x180013031  lea     rax, [rbp+47h+arg_20]
0x180013035  mov     [rbp+47h+var_40], r9
0x180013039  mov     [rbp+47h+var_30], rax
0x18001303d  mov     r9d, 5
0x180013043  lea     rax, [rbp+47h+arg_28]
0x180013047  mov     [rbp+47h+var_34], r11d
0x18001304b  mov     [rbp+47h+var_20], rax
0x18001304f  mov     rdx, r10
0x180013052  lea     rax, [rbp+47h+var_60]
0x180013056  mov     [rbp+47h+var_28], 4
0x18001305e  mov     [rsp+90h+var_70], rax
0x180013063  mov     [rbp+47h+var_18], 4
0x18001306b  call    McGenEventWrite_EtwEventWriteTransfer
0x180013070  mov     rcx, [rbp+47h+var_10]
0x180013074  xor     rcx, rsp; StackCookie
0x180013077  call    __security_check_cookie
0x18001307c  mov     rbx, [rsp+90h+arg_0]
0x180013084  add     rsp, 90h
0x18001308b  pop     rbp
0x18001308c  retn
```
