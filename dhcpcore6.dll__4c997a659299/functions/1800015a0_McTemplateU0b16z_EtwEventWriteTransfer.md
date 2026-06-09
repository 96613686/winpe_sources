# McTemplateU0b16z_EtwEventWriteTransfer

- ea: `0x1800015a0`
- end: `0x180001635`
- name: `McTemplateU0b16z_EtwEventWriteTransfer`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001225c`

## callees

- `0x1800015a0`
- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0b16z_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4)
{
  __int64 v4; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v8; // [rsp+40h] [rbp-38h]
  __int64 v9; // [rsp+48h] [rbp-30h]
  const wchar_t *v10; // [rsp+50h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-20h]
  int v12; // [rsp+5Ch] [rbp-1Ch]

  v8 = a3;
  v9 = 16;
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
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, (__int64)AddingV6Address, a3, 3, (__int64)v7);
}

```

## disassembly

```asm
0x1800015a0  sub     rsp, 78h
0x1800015a4  mov     rax, cs:__security_cookie
0x1800015ab  xor     rax, rsp
0x1800015ae  mov     [rsp+78h+var_18], rax
0x1800015b3  xor     edx, edx
0x1800015b5  mov     [rsp+78h+var_38], r8
0x1800015ba  mov     [rsp+78h+var_30], 10h
0x1800015c3  test    r9, r9
0x1800015c6  jz      short loc_1800015DF
0x1800015c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800015cc  inc     rax
0x1800015cf  cmp     [r9+rax*2], dx
0x1800015d4  jnz     short loc_1800015CC
0x1800015d6  lea     eax, ds:2[rax*2]
0x1800015dd  jmp     short loc_1800015E4
0x1800015df  mov     eax, 0Ah
0x1800015e4  test    r9, r9
0x1800015e7  mov     [rsp+78h+var_20], eax
0x1800015eb  lea     rcx, aNull_0; "NULL"
0x1800015f2  mov     [rsp+78h+var_1C], edx
0x1800015f6  cmovz   r9, rcx
0x1800015fa  lea     rax, [rsp+78h+var_48]
0x1800015ff  mov     [rsp+78h+var_28], r9
0x180001604  lea     rdx, AddingV6Address
0x18000160b  mov     r9d, 3
0x180001611  mov     [rsp+78h+var_58], rax
0x180001616  lea     rcx, Dhcpv6_Context
0x18000161d  call    McGenEventWrite_EtwEventWriteTransfer
0x180001622  mov     rcx, [rsp+78h+var_18]
0x180001627  xor     rcx, rsp; StackCookie
0x18000162a  call    __security_check_cookie
0x18000162f  add     rsp, 78h
0x180001633  retn
```
