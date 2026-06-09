# McTemplateU0zqbr1_EtwEventWriteTransfer

- ea: `0x18000175c`
- end: `0x180001806`
- name: `McTemplateU0zqbr1_EtwEventWriteTransfer`
- size: `170`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180014070`
- `0x180014590`
- `0x180029fe4`

## callees

- `0x18000175c`
- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0zqbr1_EtwEventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        int a4,
        __int64 a5)
{
  __int64 v5; // rax
  int v6; // eax
  _BYTE v8[16]; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v9; // [rsp+40h] [rbp-40h]
  int v10; // [rsp+48h] [rbp-38h]
  int v11; // [rsp+4Ch] [rbp-34h]
  int *v12; // [rsp+50h] [rbp-30h]
  __int64 v13; // [rsp+58h] [rbp-28h]
  __int64 v14; // [rsp+60h] [rbp-20h]
  int v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+6Ch] [rbp-14h]
  int v17; // [rsp+A8h] [rbp+28h] BYREF

  v17 = a4;
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
  v15 = a4;
  v12 = &v17;
  if ( !a3 )
    a3 = L"NULL";
  v14 = a5;
  v9 = a3;
  v13 = 4;
  v11 = 0;
  v16 = 0;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, (__int64)a3, 4, (__int64)v8);
}

```

## disassembly

```asm
0x18000175c  mov     [rsp-8+arg_18], r9d
0x180001761  push    rbp
0x180001762  mov     rbp, rsp
0x180001765  sub     rsp, 80h
0x18000176c  mov     rax, cs:__security_cookie
0x180001773  xor     rax, rsp
0x180001776  mov     [rbp+var_10], rax
0x18000177a  xor     r10d, r10d
0x18000177d  test    r8, r8
0x180001780  jz      short loc_180001799
0x180001782  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001786  inc     rax
0x180001789  cmp     [r8+rax*2], r10w
0x18000178e  jnz     short loc_180001786
0x180001790  lea     eax, ds:2[rax*2]
0x180001797  jmp     short loc_18000179E
0x180001799  mov     eax, 0Ah
0x18000179e  mov     [rbp+var_38], eax
0x1800017a1  lea     rcx, aNull_0; "NULL"
0x1800017a8  lea     rax, [rbp+arg_18]
0x1800017ac  mov     [rbp+var_18], r9d
0x1800017b0  mov     [rbp+var_30], rax
0x1800017b4  test    r8, r8
0x1800017b7  mov     rax, [rbp+arg_20]
0x1800017bb  cmovz   r8, rcx
0x1800017bf  mov     [rbp+var_20], rax
0x1800017c3  mov     ecx, 4
0x1800017c8  mov     [rbp+var_40], r8
0x1800017cc  lea     rax, [rbp+var_50]
0x1800017d0  mov     [rbp+var_28], rcx
0x1800017d4  mov     r9d, ecx
0x1800017d7  mov     [rsp+80h+var_60], rax
0x1800017dc  lea     rcx, Dhcpv6_Context
0x1800017e3  mov     [rbp+var_34], r10d
0x1800017e7  mov     [rbp+var_14], r10d
0x1800017eb  call    McGenEventWrite_EtwEventWriteTransfer
0x1800017f0  mov     rcx, [rbp+var_10]
0x1800017f4  xor     rcx, rsp; StackCookie
0x1800017f7  call    __security_check_cookie
0x1800017fc  add     rsp, 80h
0x180001803  pop     rbp
0x180001804  retn
```
