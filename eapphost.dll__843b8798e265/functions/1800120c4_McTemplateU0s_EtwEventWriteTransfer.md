# McTemplateU0s_EtwEventWriteTransfer

- ea: `0x1800120c4`
- end: `0x18001213a`
- name: `McTemplateU0s_EtwEventWriteTransfer`
- size: `118`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `33`
- callee_count: `3`
- tags: ``

## callers

- `0x1800115b4`
- `0x18001177c`
- `0x180011d28`
- `0x180013090`
- `0x180013770`
- `0x180013980`
- `0x1800145f0`
- `0x1800149c0`
- `0x180014b20`
- `0x180014c8c`
- `0x180015270`
- `0x180015980`
- `0x1800160f0`
- `0x180016300`
- `0x180016660`
- `0x180016880`
- `0x180016ad0`
- `0x180016e90`
- `0x1800170e0`
- `0x180017500`
- `0x1800176e0`
- `0x1800178b0`
- `0x180017aa0`
- `0x180018850`
- `0x180025770`
- `0x180026488`
- `0x180026850`
- `0x1800279b8`
- `0x180027bcc`
- `0x180028f50`
- `0x1800291a8`
- `0x180029d84`
- `0x18002a2fc`

## callees

- `0x180002af0`
- `0x180009fe4`
- `0x1800120c4`

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
0x1800120c4  sub     rsp, 68h
0x1800120c8  mov     rax, cs:__security_cookie
0x1800120cf  xor     rax, rsp
0x1800120d2  mov     [rsp+68h+var_18], rax
0x1800120d7  test    r8, r8
0x1800120da  jz      short loc_1800120EE
0x1800120dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800120e0  inc     rax
0x1800120e3  cmp     byte ptr [r8+rax], 0
0x1800120e8  jnz     short loc_1800120E0
0x1800120ea  inc     eax
0x1800120ec  jmp     short loc_1800120F3
0x1800120ee  mov     eax, 5
0x1800120f3  lea     r9, aNull; "NULL"
0x1800120fa  mov     [rsp+68h+var_20], eax
0x1800120fe  test    r8, r8
0x180012101  mov     [rsp+68h+var_1C], 0
0x180012109  lea     rax, [rsp+68h+var_38]
0x18001210e  cmovz   r8, r9
0x180012112  mov     [rsp+68h+var_48], rax
0x180012117  mov     r9d, 2
0x18001211d  mov     [rsp+68h+var_28], r8
0x180012122  call    McGenEventWrite_EtwEventWriteTransfer
0x180012127  mov     rcx, [rsp+68h+var_18]
0x18001212c  xor     rcx, rsp; StackCookie
0x18001212f  call    __security_check_cookie
0x180012134  add     rsp, 68h
0x180012138  retn
```
