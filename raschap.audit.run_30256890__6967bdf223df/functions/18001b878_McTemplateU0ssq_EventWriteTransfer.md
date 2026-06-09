# McTemplateU0ssq_EventWriteTransfer

- ea: `0x18001b878`
- end: `0x18001b93d`
- name: `McTemplateU0ssq_EventWriteTransfer`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007370`

## callees

- `0x180013b20`
- `0x180016ab0`
- `0x18001b878`

## pseudocode

```c
ULONG __fastcall McTemplateU0ssq_EventWriteTransfer(__int64 a1, __int64 a2, const char *a3, const char *a4, char a5)
{
  __int64 v5; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  bool v9; // zf
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-58h] BYREF
  const char *v12; // [rsp+40h] [rbp-48h]
  int v13; // [rsp+48h] [rbp-40h]
  int v14; // [rsp+4Ch] [rbp-3Ch]
  const char *v15; // [rsp+50h] [rbp-38h]
  int v16; // [rsp+58h] [rbp-30h]
  int v17; // [rsp+5Ch] [rbp-2Ch]
  char *v18; // [rsp+60h] [rbp-28h]
  __int64 v19; // [rsp+68h] [rbp-20h]

  v5 = -1;
  v6 = 5;
  if ( a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a3[v7] );
    v8 = v7 + 1;
  }
  else
  {
    v8 = 5;
  }
  v13 = v8;
  v14 = 0;
  if ( !a3 )
    a3 = "NULL";
  v12 = a3;
  v9 = a4 == 0;
  if ( a4 )
  {
    do
      ++v5;
    while ( a4[v5] );
    v6 = v5 + 1;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = "NULL";
  v16 = v6;
  v15 = a4;
  v18 = &a5;
  v17 = 0;
  v19 = 4;
  return McGenEventWrite_EventWriteTransfer(
           &Microsoft_Windows_EapMethods_RasChap_Context,
           (const EVENT_DESCRIPTOR *)AUTH_FAILED,
           (__int64)a3,
           4u,
           &v11);
}

```

## disassembly

```asm
0x18001b878  sub     rsp, 88h
0x18001b87f  mov     rax, cs:__security_cookie
0x18001b886  xor     rax, rsp
0x18001b889  mov     [rsp+88h+var_18], rax
0x18001b88e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b892  xor     r10d, r10d
0x18001b895  mov     edx, 5
0x18001b89a  test    r8, r8
0x18001b89d  jz      short loc_18001B8AF
0x18001b89f  mov     rcx, rax
0x18001b8a2  inc     rcx
0x18001b8a5  cmp     [r8+rcx], r10b
0x18001b8a9  jnz     short loc_18001B8A2
0x18001b8ab  inc     ecx
0x18001b8ad  jmp     short loc_18001B8B1
0x18001b8af  mov     ecx, edx
0x18001b8b1  test    r8, r8
0x18001b8b4  mov     [rsp+88h+var_40], ecx
0x18001b8b8  lea     r11, aNull; "NULL"
0x18001b8bf  mov     [rsp+88h+var_3C], r10d
0x18001b8c4  cmovz   r8, r11
0x18001b8c8  mov     [rsp+88h+var_48], r8
0x18001b8cd  test    r9, r9
0x18001b8d0  jz      short loc_18001B8E1
0x18001b8d2  inc     rax
0x18001b8d5  cmp     [r9+rax], r10b
0x18001b8d9  jnz     short loc_18001B8D2
0x18001b8db  lea     edx, [rax+1]
0x18001b8de  test    r9, r9
0x18001b8e1  cmovz   r9, r11
0x18001b8e5  mov     [rsp+88h+var_30], edx
0x18001b8e9  lea     rax, [rsp+88h+arg_20]
0x18001b8f1  mov     [rsp+88h+var_38], r9
0x18001b8f6  mov     [rsp+88h+var_28], rax
0x18001b8fb  lea     rdx, AUTH_FAILED
0x18001b902  mov     r9d, 4
0x18001b908  mov     [rsp+88h+var_2C], r10d
0x18001b90d  lea     rax, [rsp+88h+var_58]
0x18001b912  mov     [rsp+88h+var_20], r9
0x18001b917  lea     rcx, Microsoft_Windows_EapMethods_RasChap_Context
0x18001b91e  mov     [rsp+88h+var_68], rax
0x18001b923  call    McGenEventWrite_EventWriteTransfer
0x18001b928  mov     rcx, [rsp+88h+var_18]
0x18001b92d  xor     rcx, rsp; StackCookie
0x18001b930  call    __security_check_cookie
0x18001b935  add     rsp, 88h
0x18001b93c  retn
```
