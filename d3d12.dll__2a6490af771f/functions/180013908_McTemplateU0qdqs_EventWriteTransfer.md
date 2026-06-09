# McTemplateU0qdqs_EventWriteTransfer

- ea: `0x180013908`
- end: `0x1800139cb`
- name: `McTemplateU0qdqs_EventWriteTransfer`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180013750`

## callees

- `0x180007fdc`
- `0x18000b410`
- `0x180013908`

## pseudocode

```c
ULONG __fastcall McTemplateU0qdqs_EventWriteTransfer(__int64 a1, __int64 a2, int a3, int a4, char a5, const char *a6)
{
  const char *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-19h] BYREF
  int *v11; // [rsp+40h] [rbp-9h]
  __int64 v12; // [rsp+48h] [rbp-1h]
  int *v13; // [rsp+50h] [rbp+7h]
  __int64 v14; // [rsp+58h] [rbp+Fh]
  char *v15; // [rsp+60h] [rbp+17h]
  __int64 v16; // [rsp+68h] [rbp+1Fh]
  const char *v17; // [rsp+70h] [rbp+27h]
  int v18; // [rsp+78h] [rbp+2Fh]
  int v19; // [rsp+7Ch] [rbp+33h]
  int v20; // [rsp+B0h] [rbp+67h] BYREF
  int v21; // [rsp+B8h] [rbp+6Fh] BYREF

  v21 = a4;
  v20 = a3;
  v6 = a6;
  v11 = &v20;
  v12 = 4;
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
  return McGenEventWrite_EventWriteTransfer(
           (REGHANDLE *)Direct3D12EtwProviderGuid_Context,
           (const EVENT_DESCRIPTOR *)EventD3D12JournalEntry,
           0,
           5u,
           &v10);
}

```

## disassembly

```asm
0x180013908  mov     [rsp-8+arg_18], r9d
0x18001390d  mov     [rsp-8+arg_10], r8d
0x180013912  push    rbp
0x180013913  lea     rbp, [rsp-47h]
0x180013918  sub     rsp, 90h
0x18001391f  mov     rax, cs:__security_cookie
0x180013926  xor     rax, rsp
0x180013929  mov     [rbp+47h+var_10], rax
0x18001392d  mov     rcx, [rbp+47h+arg_28]
0x180013931  lea     rax, [rbp+47h+arg_10]
0x180013935  mov     [rbp+47h+var_50], rax
0x180013939  xor     r8d, r8d
0x18001393c  mov     [rbp+47h+var_48], 4
0x180013944  lea     rax, [rbp+47h+arg_18]
0x180013948  mov     [rbp+47h+var_40], rax
0x18001394c  lea     rax, [rbp+47h+arg_20]
0x180013950  mov     [rbp+47h+var_30], rax
0x180013954  mov     [rbp+47h+var_38], 4
0x18001395c  lea     r9d, [r8+5]
0x180013960  mov     [rbp+47h+var_28], 4
0x180013968  test    rcx, rcx
0x18001396b  jz      short loc_18001397E
0x18001396d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013971  inc     rax
0x180013974  cmp     [rcx+rax], r8b
0x180013978  jnz     short loc_180013971
0x18001397a  inc     eax
0x18001397c  jmp     short loc_180013981
0x18001397e  mov     eax, r9d
0x180013981  test    rcx, rcx
0x180013984  mov     [rbp+47h+var_18], eax
0x180013987  lea     rdx, aNull; "NULL"
0x18001398e  mov     [rbp+47h+var_14], r8d
0x180013992  cmovz   rcx, rdx
0x180013996  lea     rax, [rbp+47h+var_60]
0x18001399a  mov     [rbp+47h+var_20], rcx
0x18001399e  lea     rdx, EventD3D12JournalEntry
0x1800139a5  lea     rcx, Direct3D12EtwProviderGuid_Context
0x1800139ac  mov     [rsp+90h+var_70], rax
0x1800139b1  call    McGenEventWrite_EventWriteTransfer
0x1800139b6  mov     rcx, [rbp+47h+var_10]
0x1800139ba  xor     rcx, rsp; StackCookie
0x1800139bd  call    __security_check_cookie
0x1800139c2  add     rsp, 90h
0x1800139c9  pop     rbp
0x1800139ca  retn
```
