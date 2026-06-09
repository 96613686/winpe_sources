# McTemplateU0qz_EtwEventWriteTransfer

- ea: `0x1800235a4`
- end: `0x18002363a`
- name: `McTemplateU0qz_EtwEventWriteTransfer`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001fb58`

## callees

- `0x1800053e0`
- `0x180020250`
- `0x1800235a4`

## pseudocode

```c
__int64 __fastcall McTemplateU0qz_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF
  int *v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const wchar_t *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]
  int v13; // [rsp+90h] [rbp+18h] BYREF

  v13 = a3;
  v9 = 4;
  v8 = &v13;
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v11 = v5;
  v12 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v10 = a4;
  return McGenEventWrite_EtwEventWriteTransfer((__int64)L"NULL", (__int64)PortInitialized, a3, 3, (__int64)v7);
}

```

## disassembly

```asm
0x1800235a4  mov     r11, rsp
0x1800235a7  mov     [r11+18h], r8d
0x1800235ab  sub     rsp, 78h
0x1800235af  mov     rax, cs:__security_cookie
0x1800235b6  xor     rax, rsp
0x1800235b9  mov     [rsp+78h+var_18], rax
0x1800235be  xor     edx, edx
0x1800235c0  mov     qword ptr [r11-30h], 4
0x1800235c8  lea     rax, [r11+18h]
0x1800235cc  mov     [r11-38h], rax
0x1800235d0  test    r9, r9
0x1800235d3  jz      short loc_1800235EC
0x1800235d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800235d9  inc     rax
0x1800235dc  cmp     [r9+rax*2], dx
0x1800235e1  jnz     short loc_1800235D9
0x1800235e3  lea     eax, ds:2[rax*2]
0x1800235ea  jmp     short loc_1800235F1
0x1800235ec  mov     eax, 0Ah
0x1800235f1  test    r9, r9
0x1800235f4  mov     [rsp+78h+var_20], eax
0x1800235f8  lea     rcx, aNull_0; "NULL"
0x1800235ff  mov     [rsp+78h+var_1C], edx
0x180023603  cmovz   r9, rcx
0x180023607  lea     rax, [rsp+78h+var_48]
0x18002360c  mov     [rsp+78h+var_28], r9
0x180023611  lea     rdx, PortInitialized
0x180023618  mov     r9d, 3
0x18002361e  mov     [rsp+78h+var_58], rax
0x180023623  call    McGenEventWrite_EtwEventWriteTransfer
0x180023628  mov     rcx, [rsp+78h+var_18]
0x18002362d  xor     rcx, rsp; StackCookie
0x180023630  call    __security_check_cookie
0x180023635  add     rsp, 78h
0x180023639  retn
```
