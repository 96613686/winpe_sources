# McTemplateU0pdds_EventWriteTransfer

- ea: `0x1800048ec`
- end: `0x18000499f`
- name: `McTemplateU0pdds_EventWriteTransfer`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004778`

## callees

- `0x180002cb0`
- `0x18000488c`
- `0x1800048ec`

## pseudocode

```c
ULONG __fastcall McTemplateU0pdds_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        const char *a6)
{
  const char *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v11; // [rsp+40h] [rbp-9h]
  __int64 v12; // [rsp+48h] [rbp-1h]
  int *v13; // [rsp+50h] [rbp+7h]
  __int64 v14; // [rsp+58h] [rbp+Fh]
  char *v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+68h] [rbp+1Fh]
  const char *v17; // [rsp+70h] [rbp+27h]
  int v18; // [rsp+78h] [rbp+2Fh]
  int v19; // [rsp+7Ch] [rbp+33h]
  __int64 v20; // [rsp+B0h] [rbp+67h] BYREF
  int v21; // [rsp+B8h] [rbp+6Fh] BYREF

  v21 = a4;
  v20 = a3;
  v6 = a6;
  v11 = &v20;
  v12 = 8;
  v13 = &v21;
  v15 = &a5;
  v14 = 4;
  v16 = 4;
  if ( a6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a6[v7] );
    v8 = v7 + 1;
  }
  else
  {
    v8 = 5;
  }
  v18 = v8;
  v19 = 0;
  if ( !a6 )
    v6 = "NULL";
  v17 = v6;
  return McGenEventWrite_EventWriteTransfer((__int64)v6, (__int64)"NULL", 0, a4, &v10);
}

```

## disassembly

```asm
0x1800048ec  mov     [rsp-8+arg_18], r9d
0x1800048f1  mov     [rsp-8+arg_10], r8
0x1800048f6  push    rbp
0x1800048f7  lea     rbp, [rsp-47h]
0x1800048fc  sub     rsp, 90h
0x180004903  mov     rax, cs:__security_cookie
0x18000490a  xor     rax, rsp
0x18000490d  mov     [rbp+47h+var_10], rax
0x180004911  mov     rcx, [rbp+47h+arg_28]
0x180004915  lea     rax, [rbp+47h+arg_10]
0x180004919  mov     [rbp+47h+var_50], rax
0x18000491d  xor     r8d, r8d; int
0x180004920  mov     [rbp+47h+var_48], 8
0x180004928  lea     rax, [rbp+47h+arg_18]
0x18000492c  mov     [rbp+47h+var_40], rax
0x180004930  lea     rax, [rbp+47h+arg_20]
0x180004934  mov     [rbp+47h+var_30], rax
0x180004938  mov     [rbp+47h+var_38], 4
0x180004940  mov     [rbp+47h+var_28], 4
0x180004948  test    rcx, rcx
0x18000494b  jz      short loc_18000495E
0x18000494d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004951  inc     rax
0x180004954  cmp     [rcx+rax], r8b
0x180004958  jnz     short loc_180004951
0x18000495a  inc     eax
0x18000495c  jmp     short loc_180004963
0x18000495e  mov     eax, 5
0x180004963  test    rcx, rcx
0x180004966  mov     [rbp+47h+var_18], eax
0x180004969  lea     rdx, aNull; "NULL"
0x180004970  mov     [rbp+47h+var_14], r8d
0x180004974  cmovz   rcx, rdx; int
0x180004978  lea     rax, [rbp+47h+var_60]
0x18000497c  mov     [rbp+47h+var_20], rcx
0x180004980  mov     [rsp+90h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x180004985  call    McGenEventWrite_EventWriteTransfer
0x18000498a  mov     rcx, [rbp+47h+var_10]
0x18000498e  xor     rcx, rsp; StackCookie
0x180004991  call    __security_check_cookie
0x180004996  add     rsp, 90h
0x18000499d  pop     rbp
0x18000499e  retn
```
