# McTemplateU0s_EtwEventWriteTransfer

- ea: `0x180011958`
- end: `0x1800119cd`
- name: `McTemplateU0s_EtwEventWriteTransfer`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `33`
- callee_count: `3`
- tags: ``

## callers

- `0x180010eb4`
- `0x180011064`
- `0x1800115e8`
- `0x180012900`
- `0x180012fc0`
- `0x1800131c0`
- `0x180013e00`
- `0x1800141c0`
- `0x180014310`
- `0x18001446c`
- `0x180014a50`
- `0x180015140`
- `0x1800158a0`
- `0x180015aa0`
- `0x180015df0`
- `0x180016010`
- `0x180016250`
- `0x180016610`
- `0x180016850`
- `0x180016c40`
- `0x180016e20`
- `0x180016fe0`
- `0x1800171d0`
- `0x180017ee0`
- `0x180024a8c`
- `0x180025760`
- `0x180025b18`
- `0x180026c54`
- `0x180026e60`
- `0x180028168`
- `0x1800283b8`
- `0x180028f64`
- `0x1800294c8`

## callees

- `0x180002a90`
- `0x180009b98`
- `0x180011958`

## pseudocode

```c
__int64 __fastcall McTemplateU0s_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, const char *a3)
{
  __int64 v3; // rax
  int v4; // eax
  _BYTE v6[16]; // [rsp+30h] [rbp-38h] BYREF
  const char *v7; // [rsp+40h] [rbp-28h]
  int v8; // [rsp+48h] [rbp-20h]
  int v9; // [rsp+4Ch] [rbp-1Ch]

  if ( a3 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a3[v3] );
    v4 = v3 + 1;
  }
  else
  {
    v4 = 5;
  }
  v8 = v4;
  v9 = 0;
  if ( !a3 )
    a3 = "NULL";
  v7 = a3;
  return McGenEventWrite_EtwEventWriteTransfer(a1, a2, (__int64)a3, 2, (__int64)v6);
}

```

## disassembly

```asm
0x180011958  sub     rsp, 68h
0x18001195c  mov     rax, cs:__security_cookie
0x180011963  xor     rax, rsp
0x180011966  mov     [rsp+68h+var_18], rax
0x18001196b  test    r8, r8
0x18001196e  jz      short loc_180011982
0x180011970  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011974  inc     rax
0x180011977  cmp     byte ptr [r8+rax], 0
0x18001197c  jnz     short loc_180011974
0x18001197e  inc     eax
0x180011980  jmp     short loc_180011987
0x180011982  mov     eax, 5
0x180011987  lea     r9, aNull; "NULL"
0x18001198e  mov     [rsp+68h+var_20], eax
0x180011992  test    r8, r8
0x180011995  mov     [rsp+68h+var_1C], 0
0x18001199d  lea     rax, [rsp+68h+var_38]
0x1800119a2  cmovz   r8, r9
0x1800119a6  mov     [rsp+68h+var_48], rax
0x1800119ab  mov     r9d, 2
0x1800119b1  mov     [rsp+68h+var_28], r8
0x1800119b6  call    McGenEventWrite_EtwEventWriteTransfer
0x1800119bb  mov     rcx, [rsp+68h+var_18]
0x1800119c0  xor     rcx, rsp; StackCookie
0x1800119c3  call    __security_check_cookie
0x1800119c8  add     rsp, 68h
0x1800119cc  retn
```
