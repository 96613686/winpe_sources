# McTemplateU0zdzd_EventWriteTransfer

- ea: `0x18000ff78`
- end: `0x180010056`
- name: `McTemplateU0zdzd_EventWriteTransfer`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000de34`

## callees

- `0x180001a50`
- `0x180008570`
- `0x18000ff78`

## pseudocode

```c
ULONG __fastcall McTemplateU0zdzd_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        int a4,
        const wchar_t *a5,
        char a6)
{
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  const wchar_t *v10; // rcx
  bool v11; // zf
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-19h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-9h]
  int v15; // [rsp+48h] [rbp-1h]
  int v16; // [rsp+4Ch] [rbp+3h]
  int *v17; // [rsp+50h] [rbp+7h]
  __int64 v18; // [rsp+58h] [rbp+Fh]
  const wchar_t *v19; // [rsp+60h] [rbp+17h]
  int v20; // [rsp+68h] [rbp+1Fh]
  int v21; // [rsp+6Ch] [rbp+23h]
  char *v22; // [rsp+70h] [rbp+27h]
  __int64 v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+B8h] [rbp+6Fh] BYREF

  v24 = a4;
  v6 = -1;
  v7 = 10;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v15 = v9;
  v16 = 0;
  v17 = &v24;
  v10 = a5;
  if ( !a3 )
    a3 = L"NULL";
  v18 = 4;
  v14 = a3;
  v11 = a5 == 0;
  if ( a5 )
  {
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
    v11 = a5 == 0;
  }
  v20 = v7;
  v22 = &a6;
  v21 = 0;
  if ( v11 )
    v10 = L"NULL";
  v19 = v10;
  v23 = 4;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)v10,
           (const EVENT_DESCRIPTOR *)GetO365APIDataNetworkFailure,
           (__int64)a3,
           5u,
           &v13);
}

```

## disassembly

```asm
0x18000ff78  mov     [rsp-8+arg_18], r9d
0x18000ff7d  push    rbp
0x18000ff7e  lea     rbp, [rsp-47h]
0x18000ff83  sub     rsp, 90h
0x18000ff8a  mov     rax, cs:__security_cookie
0x18000ff91  xor     rax, rsp
0x18000ff94  mov     [rbp+47h+var_10], rax
0x18000ff98  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ff9c  xor     r9d, r9d
0x18000ff9f  mov     edx, 0Ah
0x18000ffa4  test    r8, r8
0x18000ffa7  jz      short loc_18000FFBF
0x18000ffa9  mov     rcx, rax
0x18000ffac  inc     rcx
0x18000ffaf  cmp     [r8+rcx*2], r9w
0x18000ffb4  jnz     short loc_18000FFAC
0x18000ffb6  lea     ecx, ds:2[rcx*2]
0x18000ffbd  jmp     short loc_18000FFC1
0x18000ffbf  mov     ecx, edx
0x18000ffc1  mov     [rbp+47h+var_48], ecx
0x18000ffc4  lea     r10, aNull; "NULL"
0x18000ffcb  lea     rcx, [rbp+47h+arg_18]
0x18000ffcf  mov     [rbp+47h+var_44], r9d
0x18000ffd3  test    r8, r8
0x18000ffd6  mov     [rbp+47h+var_40], rcx
0x18000ffda  mov     rcx, [rbp+47h+arg_20]
0x18000ffde  cmovz   r8, r10
0x18000ffe2  mov     [rbp+47h+var_38], 4
0x18000ffea  mov     [rbp+47h+var_50], r8
0x18000ffee  test    rcx, rcx
0x18000fff1  jz      short loc_180010007
0x18000fff3  inc     rax
0x18000fff6  cmp     [rcx+rax*2], r9w
0x18000fffb  jnz     short loc_18000FFF3
0x18000fffd  lea     edx, ds:2[rax*2]
0x180010004  test    rcx, rcx
0x180010007  lea     rax, [rbp+47h+arg_28]
0x18001000b  mov     [rbp+47h+var_28], edx
0x18001000e  mov     [rbp+47h+var_20], rax
0x180010012  lea     rdx, GetO365APIDataNetworkFailure
0x180010019  lea     rax, [rbp+47h+var_60]
0x18001001d  mov     [rbp+47h+var_24], r9d
0x180010021  cmovz   rcx, r10
0x180010025  mov     [rsp+90h+var_70], rax
0x18001002a  mov     r9d, 5
0x180010030  mov     [rbp+47h+var_30], rcx
0x180010034  mov     [rbp+47h+var_18], 4
0x18001003c  call    McGenEventWrite_EventWriteTransfer
0x180010041  mov     rcx, [rbp+47h+var_10]
0x180010045  xor     rcx, rsp; StackCookie
0x180010048  call    __security_check_cookie
0x18001004d  add     rsp, 90h
0x180010054  pop     rbp
0x180010055  retn
```
