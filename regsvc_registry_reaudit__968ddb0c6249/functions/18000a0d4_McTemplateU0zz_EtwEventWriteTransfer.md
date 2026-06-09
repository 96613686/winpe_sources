# McTemplateU0zz_EtwEventWriteTransfer

- ea: `0x18000a0d4`
- end: `0x18000a187`
- name: `McTemplateU0zz_EtwEventWriteTransfer`
- size: `179`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800093a8`
- `0x18000b8a0`
- `0x180011d10`
- `0x18001277c`
- `0x1800136b0`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x18000a0d4`

## pseudocode

```c
__int64 __fastcall McTemplateU0zz_EtwEventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v6; // edx
  __int64 v7; // rcx
  __int64 v8; // rcx
  bool v9; // zf
  _BYTE v11[16]; // [rsp+30h] [rbp-48h] BYREF
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
  return McGenEventWrite_EtwEventWriteTransfer(v8, a2, (__int64)a3, 3, (__int64)v11);
}

```

## disassembly

```asm
0x18000a0d4  push    rbx
0x18000a0d6  sub     rsp, 70h
0x18000a0da  mov     rax, cs:__security_cookie
0x18000a0e1  xor     rax, rsp
0x18000a0e4  mov     [rsp+78h+var_18], rax
0x18000a0e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a0ed  xor     r11d, r11d
0x18000a0f0  mov     r10, rdx
0x18000a0f3  mov     edx, 0Ah
0x18000a0f8  test    r8, r8
0x18000a0fb  jz      short loc_18000A113
0x18000a0fd  mov     rcx, rax
0x18000a100  inc     rcx
0x18000a103  cmp     [r8+rcx*2], r11w
0x18000a108  jnz     short loc_18000A100
0x18000a10a  lea     ecx, ds:2[rcx*2]
0x18000a111  jmp     short loc_18000A115
0x18000a113  mov     ecx, edx
0x18000a115  test    r8, r8
0x18000a118  mov     [rsp+78h+var_30], ecx
0x18000a11c  lea     rbx, aNull_0; "NULL"
0x18000a123  mov     [rsp+78h+var_2C], r11d
0x18000a128  cmovz   r8, rbx
0x18000a12c  mov     [rsp+78h+var_38], r8
0x18000a131  test    r9, r9
0x18000a134  jz      short loc_18000A14A
0x18000a136  inc     rax
0x18000a139  cmp     [r9+rax*2], r11w
0x18000a13e  jnz     short loc_18000A136
0x18000a140  lea     edx, ds:2[rax*2]
0x18000a147  test    r9, r9
0x18000a14a  cmovz   r9, rbx
0x18000a14e  mov     [rsp+78h+var_20], edx
0x18000a152  mov     [rsp+78h+var_28], r9
0x18000a157  lea     rax, [rsp+78h+var_48]
0x18000a15c  mov     r9d, 3
0x18000a162  mov     [rsp+78h+var_1C], r11d
0x18000a167  mov     rdx, r10
0x18000a16a  mov     [rsp+78h+var_58], rax
0x18000a16f  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a174  mov     rcx, [rsp+78h+var_18]
0x18000a179  xor     rcx, rsp; StackCookie
0x18000a17c  call    __security_check_cookie
0x18000a181  add     rsp, 70h
0x18000a185  pop     rbx
0x18000a186  retn
```
