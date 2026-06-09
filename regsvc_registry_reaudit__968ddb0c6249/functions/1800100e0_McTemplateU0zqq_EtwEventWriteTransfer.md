# McTemplateU0zqq_EtwEventWriteTransfer

- ea: `0x1800100e0`
- end: `0x180010181`
- name: `McTemplateU0zqq_EtwEventWriteTransfer`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f640`

## callees

- `0x180007740`
- `0x18000a07c`
- `0x1800100e0`

## pseudocode

```c
__int64 __fastcall McTemplateU0zqq_EtwEventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4, char a5)
{
  __int64 v5; // rax
  int v6; // eax
  _BYTE v8[16]; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-40h]
  int v10; // [rsp+48h] [rbp-38h]
  int v11; // [rsp+4Ch] [rbp-34h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+A8h] [rbp+28h] BYREF

  v16 = a4;
  if ( a3 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a3[v5] );
    v6 = 2 * v5 + 2;
  }
  else
  {
    v6 = 10;
  }
  v10 = v6;
  v11 = 0;
  v13 = 4;
  v12 = &v16;
  v15 = 4;
  v14 = &a5;
  if ( !a3 )
    a3 = L"NULL";
  v9 = a3;
  return McGenEventWrite_EtwEventWriteTransfer(
           (__int64)L"NULL",
           (__int64)PERFLIB_NO_PERFORMANCE_SUBKEY,
           (__int64)a3,
           4,
           (__int64)v8);
}

```

## disassembly

```asm
0x1800100e0  mov     [rsp-8+arg_18], r9d
0x1800100e5  push    rbp
0x1800100e6  mov     rbp, rsp
0x1800100e9  sub     rsp, 80h
0x1800100f0  mov     rax, cs:__security_cookie
0x1800100f7  xor     rax, rsp
0x1800100fa  mov     [rbp+var_10], rax
0x1800100fe  xor     edx, edx
0x180010100  test    r8, r8
0x180010103  jz      short loc_18001011C
0x180010105  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010109  inc     rax
0x18001010c  cmp     [r8+rax*2], dx
0x180010111  jnz     short loc_180010109
0x180010113  lea     eax, ds:2[rax*2]
0x18001011a  jmp     short loc_180010121
0x18001011c  mov     eax, 0Ah
0x180010121  mov     [rbp+var_38], eax
0x180010124  lea     rcx, aNull_0; "NULL"
0x18001012b  mov     r9d, 4
0x180010131  mov     [rbp+var_34], edx
0x180010134  lea     rax, [rbp+arg_18]
0x180010138  mov     [rbp+var_28], r9
0x18001013c  mov     [rbp+var_30], rax
0x180010140  lea     rdx, PERFLIB_NO_PERFORMANCE_SUBKEY
0x180010147  lea     rax, [rbp+arg_20]
0x18001014b  mov     [rbp+var_18], r9
0x18001014f  test    r8, r8
0x180010152  mov     [rbp+var_20], rax
0x180010156  lea     rax, [rbp+var_50]
0x18001015a  cmovz   r8, rcx
0x18001015e  mov     [rsp+80h+var_60], rax
0x180010163  mov     [rbp+var_40], r8
0x180010167  call    McGenEventWrite_EtwEventWriteTransfer
0x18001016c  mov     rcx, [rbp+var_10]
0x180010170  xor     rcx, rsp; StackCookie
0x180010173  call    __security_check_cookie
0x180010178  add     rsp, 80h
0x18001017f  pop     rbp
0x180010180  retn
```
