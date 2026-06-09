# McTemplateU0zzq_EtwEventWriteTransfer

- ea: `0x180012df0`
- end: `0x180012ebb`
- name: `McTemplateU0zzq_EtwEventWriteTransfer`
- size: `203`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180011d10`
- `0x1800126c8`
- `0x18001277c`
- `0x1800136b0`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x180012df0`

## pseudocode

```c
__int64 __fastcall McTemplateU0zzq_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char a5)
{
  __int64 v5; // rax
  int v7; // edx
  __int64 v8; // rcx
  __int64 v9; // rcx
  bool v10; // zf
  _BYTE v12[16]; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v13; // [rsp+40h] [rbp-48h]
  int v14; // [rsp+48h] [rbp-40h]
  int v15; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v16; // [rsp+50h] [rbp-38h]
  int v17; // [rsp+58h] [rbp-30h]
  int v18; // [rsp+5Ch] [rbp-2Ch]
  char *v19; // [rsp+60h] [rbp-28h]
  __int64 v20; // [rsp+68h] [rbp-20h]

  v5 = -1;
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
      ++v5;
    while ( a4[v5] );
    v7 = 2 * v5 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  v17 = v7;
  v16 = a4;
  v19 = &a5;
  v20 = 4;
  v18 = 0;
  return McGenEventWrite_EtwEventWriteTransfer(v9, a2, (__int64)a3, 4, (__int64)v12);
}

```

## disassembly

```asm
0x180012df0  push    rbx
0x180012df2  sub     rsp, 80h
0x180012df9  mov     rax, cs:__security_cookie
0x180012e00  xor     rax, rsp
0x180012e03  mov     [rsp+88h+var_18], rax
0x180012e08  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012e0c  xor     r11d, r11d
0x180012e0f  mov     r10, rdx
0x180012e12  mov     edx, 0Ah
0x180012e17  test    r8, r8
0x180012e1a  jz      short loc_180012E32
0x180012e1c  mov     rcx, rax
0x180012e1f  inc     rcx
0x180012e22  cmp     [r8+rcx*2], r11w
0x180012e27  jnz     short loc_180012E1F
0x180012e29  lea     ecx, ds:2[rcx*2]
0x180012e30  jmp     short loc_180012E34
0x180012e32  mov     ecx, edx
0x180012e34  test    r8, r8
0x180012e37  mov     [rsp+88h+var_40], ecx
0x180012e3b  lea     rbx, aNull_0; "NULL"
0x180012e42  mov     [rsp+88h+var_3C], r11d
0x180012e47  cmovz   r8, rbx
0x180012e4b  mov     [rsp+88h+var_48], r8
0x180012e50  test    r9, r9
0x180012e53  jz      short loc_180012E69
0x180012e55  inc     rax
0x180012e58  cmp     [r9+rax*2], r11w
0x180012e5d  jnz     short loc_180012E55
0x180012e5f  lea     edx, ds:2[rax*2]
0x180012e66  test    r9, r9
0x180012e69  cmovz   r9, rbx
0x180012e6d  mov     [rsp+88h+var_30], edx
0x180012e71  lea     rax, [rsp+88h+arg_20]
0x180012e79  mov     [rsp+88h+var_38], r9
0x180012e7e  mov     [rsp+88h+var_28], rax
0x180012e83  mov     r9d, 4
0x180012e89  lea     rax, [rsp+88h+var_58]
0x180012e8e  mov     [rsp+88h+var_20], r9
0x180012e93  mov     rdx, r10
0x180012e96  mov     [rsp+88h+var_68], rax
0x180012e9b  mov     [rsp+88h+var_2C], r11d
0x180012ea0  call    McGenEventWrite_EtwEventWriteTransfer
0x180012ea5  mov     rcx, [rsp+88h+var_18]
0x180012eaa  xor     rcx, rsp; StackCookie
0x180012ead  call    __security_check_cookie
0x180012eb2  add     rsp, 80h
0x180012eb9  pop     rbx
0x180012eba  retn
```
