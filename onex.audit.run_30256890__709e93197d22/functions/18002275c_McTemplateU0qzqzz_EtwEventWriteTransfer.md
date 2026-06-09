# McTemplateU0qzqzz_EtwEventWriteTransfer

- ea: `0x18002275c`
- end: `0x180022870`
- name: `McTemplateU0qzqzz_EtwEventWriteTransfer`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ac0`

## callees

- `0x1800053e0`
- `0x180020250`
- `0x18002275c`

## pseudocode

```c
__int64 __fastcall McTemplateU0qzqzz_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        int a3,
        const wchar_t *a4,
        char a5,
        const wchar_t *a6,
        const wchar_t *a7)
{
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // rcx
  int v10; // ecx
  const wchar_t *v11; // rcx
  __int64 v12; // rdx
  int v13; // edx
  const wchar_t *v14; // rcx
  bool v15; // zf
  _BYTE v17[16]; // [rsp+30h] [rbp-31h] BYREF
  int *v18; // [rsp+40h] [rbp-21h]
  __int64 v19; // [rsp+48h] [rbp-19h]
  const wchar_t *v20; // [rsp+50h] [rbp-11h]
  int v21; // [rsp+58h] [rbp-9h]
  int v22; // [rsp+5Ch] [rbp-5h]
  char *v23; // [rsp+60h] [rbp-1h]
  __int64 v24; // [rsp+68h] [rbp+7h]
  const wchar_t *v25; // [rsp+70h] [rbp+Fh]
  int v26; // [rsp+78h] [rbp+17h]
  int v27; // [rsp+7Ch] [rbp+1Bh]
  const wchar_t *v28; // [rsp+80h] [rbp+1Fh]
  int v29; // [rsp+88h] [rbp+27h]
  int v30; // [rsp+8Ch] [rbp+2Bh]
  int v31; // [rsp+C0h] [rbp+5Fh] BYREF

  v31 = a3;
  v19 = 4;
  v18 = &v31;
  v7 = -1;
  v8 = 10;
  if ( a4 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a4[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v21 = v10;
  v22 = 0;
  v23 = &a5;
  v11 = a6;
  if ( !a4 )
    a4 = L"NULL";
  v24 = 4;
  v20 = a4;
  if ( a6 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a6[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v13 = 10;
  }
  v26 = v13;
  v27 = 0;
  if ( !a6 )
    v11 = L"NULL";
  v25 = v11;
  v14 = a7;
  v15 = a7 == 0;
  if ( a7 )
  {
    do
      ++v7;
    while ( a7[v7] );
    v8 = (unsigned int)(2 * v7 + 2);
    v15 = a7 == 0;
  }
  if ( v15 )
    v14 = L"NULL";
  v29 = v8;
  v28 = v14;
  v30 = 0;
  return McGenEventWrite_EtwEventWriteTransfer((__int64)v14, (__int64)OneXUserIdentified, v8, 6, (__int64)v17);
}

```

## disassembly

```asm
0x18002275c  mov     [rsp-8+arg_10], r8d
0x180022761  push    rbp
0x180022762  lea     rbp, [rsp-3Fh]
0x180022767  sub     rsp, 0A0h
0x18002276e  mov     rax, cs:__security_cookie
0x180022775  xor     rax, rsp
0x180022778  mov     [rbp+3Fh+var_10], rax
0x18002277c  lea     rax, [rbp+3Fh+arg_10]
0x180022780  mov     [rbp+3Fh+var_58], 4
0x180022788  xor     r10d, r10d
0x18002278b  mov     [rbp+3Fh+var_60], rax
0x18002278f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022793  lea     r8d, [r10+0Ah]
0x180022797  test    r9, r9
0x18002279a  jz      short loc_1800227B2
0x18002279c  mov     rcx, rax
0x18002279f  inc     rcx
0x1800227a2  cmp     [r9+rcx*2], r10w
0x1800227a7  jnz     short loc_18002279F
0x1800227a9  lea     ecx, ds:2[rcx*2]
0x1800227b0  jmp     short loc_1800227B5
0x1800227b2  mov     ecx, r8d
0x1800227b5  mov     [rbp+3Fh+var_48], ecx
0x1800227b8  lea     r11, aNull_0; "NULL"
0x1800227bf  lea     rcx, [rbp+3Fh+arg_20]
0x1800227c3  mov     [rbp+3Fh+var_44], r10d
0x1800227c7  test    r9, r9
0x1800227ca  mov     [rbp+3Fh+var_40], rcx
0x1800227ce  mov     rcx, [rbp+3Fh+arg_28]
0x1800227d2  cmovz   r9, r11
0x1800227d6  mov     [rbp+3Fh+var_38], 4
0x1800227de  mov     [rbp+3Fh+var_50], r9
0x1800227e2  test    rcx, rcx
0x1800227e5  jz      short loc_1800227FD
0x1800227e7  mov     rdx, rax
0x1800227ea  inc     rdx
0x1800227ed  cmp     [rcx+rdx*2], r10w
0x1800227f2  jnz     short loc_1800227EA
0x1800227f4  lea     edx, ds:2[rdx*2]
0x1800227fb  jmp     short loc_180022800
0x1800227fd  mov     edx, r8d
0x180022800  test    rcx, rcx
0x180022803  mov     [rbp+3Fh+var_28], edx
0x180022806  mov     [rbp+3Fh+var_24], r10d
0x18002280a  cmovz   rcx, r11
0x18002280e  mov     [rbp+3Fh+var_30], rcx
0x180022812  mov     rcx, [rbp+3Fh+arg_30]
0x180022816  test    rcx, rcx
0x180022819  jz      short loc_180022830
0x18002281b  inc     rax
0x18002281e  cmp     [rcx+rax*2], r10w
0x180022823  jnz     short loc_18002281B
0x180022825  lea     r8d, ds:2[rax*2]
0x18002282d  test    rcx, rcx
0x180022830  cmovz   rcx, r11
0x180022834  mov     [rbp+3Fh+var_18], r8d
0x180022838  lea     rax, [rbp+3Fh+var_70]
0x18002283c  mov     [rbp+3Fh+var_20], rcx
0x180022840  mov     r9d, 6
0x180022846  mov     [rsp+0A0h+var_80], rax
0x18002284b  lea     rdx, OneXUserIdentified
0x180022852  mov     [rbp+3Fh+var_14], r10d
0x180022856  call    McGenEventWrite_EtwEventWriteTransfer
0x18002285b  mov     rcx, [rbp+3Fh+var_10]
0x18002285f  xor     rcx, rsp; StackCookie
0x180022862  call    __security_check_cookie
0x180022867  add     rsp, 0A0h
0x18002286e  pop     rbp
0x18002286f  retn
```
