# McTemplateU0zzqbr2_EtwEventWriteTransfer

- ea: `0x180001ac0`
- end: `0x180001bb2`
- name: `McTemplateU0zzqbr2_EtwEventWriteTransfer`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011e04`

## callees

- `0x180001ac0`
- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0zzqbr2_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  bool v11; // zf
  _BYTE v13[16]; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-9h]
  int v15; // [rsp+48h] [rbp-1h]
  int v16; // [rsp+4Ch] [rbp+3h]
  const wchar_t *v17; // [rsp+50h] [rbp+7h]
  int v18; // [rsp+58h] [rbp+Fh]
  int v19; // [rsp+5Ch] [rbp+13h]
  int *v20; // [rsp+60h] [rbp+17h]
  __int64 v21; // [rsp+68h] [rbp+1Fh]
  __int64 v22; // [rsp+70h] [rbp+27h]
  int v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+7Ch] [rbp+33h]

  v6 = -1;
  v8 = 10;
  if ( a3 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2 * v9 + 2;
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
  v22 = a6;
  v23 = a5;
  v19 = 0;
  v21 = 4;
  v24 = 0;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, (__int64)a3, 5, (__int64)v13);
}

```

## disassembly

```asm
0x180001ac0  mov     [rsp-8+arg_0], rbx
0x180001ac5  push    rbp
0x180001ac6  lea     rbp, [rsp-47h]
0x180001acb  sub     rsp, 90h
0x180001ad2  mov     rax, cs:__security_cookie
0x180001ad9  xor     rax, rsp
0x180001adc  mov     [rbp+47h+var_10], rax
0x180001ae0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001ae4  xor     r11d, r11d
0x180001ae7  mov     r10, rdx
0x180001aea  mov     edx, 0Ah
0x180001aef  test    r8, r8
0x180001af2  jz      loc_180001BAB
0x180001af8  mov     rcx, rax
0x180001afb  inc     rcx
0x180001afe  cmp     [r8+rcx*2], r11w
0x180001b03  jnz     short loc_180001AFB
0x180001b05  lea     ecx, ds:2[rcx*2]
0x180001b0c  test    r8, r8
0x180001b0f  mov     [rbp+47h+var_48], ecx
0x180001b12  lea     rbx, aNull_0; "NULL"
0x180001b19  mov     [rbp+47h+var_44], r11d
0x180001b1d  cmovz   r8, rbx
0x180001b21  mov     [rbp+47h+var_50], r8
0x180001b25  test    r9, r9
0x180001b28  jz      short loc_180001B3E
0x180001b2a  inc     rax
0x180001b2d  cmp     [r9+rax*2], r11w
0x180001b32  jnz     short loc_180001B2A
0x180001b34  lea     edx, ds:2[rax*2]
0x180001b3b  test    r9, r9
0x180001b3e  cmovz   r9, rbx
0x180001b42  mov     [rbp+47h+var_38], edx
0x180001b45  lea     rax, [rbp+47h+arg_20]
0x180001b49  mov     [rbp+47h+var_40], r9
0x180001b4d  mov     [rbp+47h+var_30], rax
0x180001b51  lea     rcx, Dhcpv6_Context
0x180001b58  mov     rax, [rbp+47h+arg_28]
0x180001b5c  mov     r9d, 5
0x180001b62  mov     [rbp+47h+var_20], rax
0x180001b66  mov     rdx, r10
0x180001b69  mov     eax, [rbp+47h+arg_20]
0x180001b6c  mov     [rbp+47h+var_18], eax
0x180001b6f  lea     rax, [rbp+47h+var_60]
0x180001b73  mov     [rsp+90h+var_70], rax
0x180001b78  mov     [rbp+47h+var_34], r11d
0x180001b7c  mov     [rbp+47h+var_28], 4
0x180001b84  mov     [rbp+47h+var_14], r11d
0x180001b88  call    McGenEventWrite_EtwEventWriteTransfer
0x180001b8d  mov     rcx, [rbp+47h+var_10]
0x180001b91  xor     rcx, rsp; StackCookie
0x180001b94  call    __security_check_cookie
0x180001b99  mov     rbx, [rsp+90h+arg_0]
0x180001ba1  add     rsp, 90h
0x180001ba8  pop     rbp
0x180001ba9  retn
0x180001bab  mov     ecx, edx
0x180001bad  jmp     loc_180001B0C
```
