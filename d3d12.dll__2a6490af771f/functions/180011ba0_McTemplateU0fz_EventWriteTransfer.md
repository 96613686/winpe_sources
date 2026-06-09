# McTemplateU0fz_EventWriteTransfer

- ea: `0x180011ba0`
- end: `0x180011c3f`
- name: `McTemplateU0fz_EventWriteTransfer`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010770`

## callees

- `0x180007fdc`
- `0x18000b410`
- `0x180011ba0`

## pseudocode

```c
ULONG __fastcall McTemplateU0fz_EventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4)
{
  int v4; // xmm2_4
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-48h] BYREF
  int *v9; // [rsp+40h] [rbp-38h]
  __int64 v10; // [rsp+48h] [rbp-30h]
  const wchar_t *v11; // [rsp+50h] [rbp-28h]
  int v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+5Ch] [rbp-1Ch]
  int v14; // [rsp+90h] [rbp+18h] BYREF

  v14 = v4;
  v10 = 4;
  v9 = &v14;
  if ( a4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a4[v5] );
    v6 = 2 * v5 + 2;
  }
  else
  {
    v6 = 10;
  }
  v12 = v6;
  v13 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v11 = a4;
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)PIX_ETW_PROVIDER_Context,
           (const EVENT_DESCRIPTOR *)PIXReportCounterData,
           a3,
           3u,
           &v8);
}

```

## disassembly

```asm
0x180011ba0  movss   [rsp+arg_10], xmm2
0x180011ba6  mov     r11, rsp
0x180011ba9  sub     rsp, 78h
0x180011bad  mov     rax, cs:__security_cookie
0x180011bb4  xor     rax, rsp
0x180011bb7  mov     [rsp+78h+var_18], rax
0x180011bbc  xor     edx, edx
0x180011bbe  mov     qword ptr [r11-30h], 4
0x180011bc6  lea     rax, [r11+18h]
0x180011bca  mov     [r11-38h], rax
0x180011bce  test    r9, r9
0x180011bd1  jz      short loc_180011BEA
0x180011bd3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011bd7  inc     rax
0x180011bda  cmp     [r9+rax*2], dx
0x180011bdf  jnz     short loc_180011BD7
0x180011be1  lea     eax, ds:2[rax*2]
0x180011be8  jmp     short loc_180011BEF
0x180011bea  mov     eax, 0Ah
0x180011bef  test    r9, r9
0x180011bf2  mov     [rsp+78h+var_20], eax
0x180011bf6  lea     rcx, aNull_0; "NULL"
0x180011bfd  mov     [rsp+78h+var_1C], edx
0x180011c01  cmovz   r9, rcx
0x180011c05  lea     rax, [rsp+78h+var_48]
0x180011c0a  mov     [rsp+78h+var_28], r9
0x180011c0f  lea     rdx, PIXReportCounterData
0x180011c16  mov     r9d, 3
0x180011c1c  mov     [rsp+78h+var_58], rax
0x180011c21  lea     rcx, PIX_ETW_PROVIDER_Context
0x180011c28  call    McGenEventWrite_EventWriteTransfer
0x180011c2d  mov     rcx, [rsp+78h+var_18]
0x180011c32  xor     rcx, rsp; StackCookie
0x180011c35  call    __security_check_cookie
0x180011c3a  add     rsp, 78h
0x180011c3e  retn
```
