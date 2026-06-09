# McTemplateU0zq_EtwEventWriteTransfer

- ea: `0x18000163c`
- end: `0x1800016d9`
- name: `McTemplateU0zq_EtwEventWriteTransfer`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000490c`
- `0x180004d78`
- `0x180005368`
- `0x180006904`
- `0x180010fd4`
- `0x180011400`
- `0x180011b98`

## callees

- `0x18000163c`
- `0x180001e78`
- `0x180019ad0`

## pseudocode

```c
__int64 __fastcall McTemplateU0zq_EtwEventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EtwEventWriteTransfer(&Dhcpv6_Context, a2, (__int64)a3, 3, (__int64)v7);
}

```

## disassembly

```asm
0x18000163c  mov     [rsp+arg_18], r9d
0x180001641  sub     rsp, 78h
0x180001645  mov     rax, cs:__security_cookie
0x18000164c  xor     rax, rsp
0x18000164f  mov     [rsp+78h+var_18], rax
0x180001654  xor     r9d, r9d
0x180001657  test    r8, r8
0x18000165a  jz      short loc_180001673
0x18000165c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180001660  inc     rax
0x180001663  cmp     [r8+rax*2], r9w
0x180001668  jnz     short loc_180001660
0x18000166a  lea     eax, ds:2[rax*2]
0x180001671  jmp     short loc_180001678
0x180001673  mov     eax, 0Ah
0x180001678  mov     [rsp+78h+var_30], eax
0x18000167c  lea     rcx, aNull_0; "NULL"
0x180001683  lea     rax, [rsp+78h+arg_18]
0x18000168b  mov     [rsp+78h+var_2C], r9d
0x180001690  test    r8, r8
0x180001693  mov     [rsp+78h+var_28], rax
0x180001698  lea     rax, [rsp+78h+var_48]
0x18000169d  mov     [rsp+78h+var_20], 4
0x1800016a6  cmovz   r8, rcx
0x1800016aa  mov     [rsp+78h+var_58], rax
0x1800016af  mov     r9d, 3
0x1800016b5  mov     [rsp+78h+var_38], r8
0x1800016ba  lea     rcx, Dhcpv6_Context
0x1800016c1  call    McGenEventWrite_EtwEventWriteTransfer
0x1800016c6  mov     rcx, [rsp+78h+var_18]
0x1800016cb  xor     rcx, rsp; StackCookie
0x1800016ce  call    __security_check_cookie
0x1800016d3  add     rsp, 78h
0x1800016d7  retn
```
