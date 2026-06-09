# McTemplateK0qdds_EtwWriteTransfer

- ea: `0x140003674`
- end: `0x14000372c`
- name: `McTemplateK0qdds_EtwWriteTransfer`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a014`

## callees

- `0x140003674`
- `0x140004300`
- `0x140010f20`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0qdds_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        const char *a7)
{
  const char *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-21h] BYREF
  int *v12; // [rsp+40h] [rbp-11h]
  __int64 v13; // [rsp+48h] [rbp-9h]
  char *v14; // [rsp+50h] [rbp-1h]
  __int64 v15; // [rsp+58h] [rbp+7h]
  char *v16; // [rsp+60h] [rbp+Fh]
  __int64 v17; // [rsp+68h] [rbp+17h]
  const char *v18; // [rsp+70h] [rbp+1Fh]
  int v19; // [rsp+78h] [rbp+27h]
  int v20; // [rsp+7Ch] [rbp+2Bh]
  int v21; // [rsp+B8h] [rbp+67h] BYREF

  v21 = a4;
  v7 = a7;
  v12 = &v21;
  v13 = 4;
  v14 = &a5;
  v16 = &a6;
  v15 = 4;
  v17 = 4;
  if ( a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a7[v8] );
    v9 = v8 + 1;
  }
  else
  {
    v9 = 5;
  }
  v19 = v9;
  v20 = 0;
  if ( !a7 )
    v7 = "NULL";
  v18 = v7;
  return McGenEventWrite_EtwWriteTransfer((__int64)v7, (const EVENT_DESCRIPTOR *)WakeNotificationWorkItem, 0, 5u, &v11);
}

```

## disassembly

```asm
0x140003674  mov     [rsp-8+arg_18], r9d
0x140003679  push    rbp
0x14000367a  lea     rbp, [rsp-3Fh]
0x14000367f  sub     rsp, 90h
0x140003686  mov     rax, cs:__security_cookie
0x14000368d  xor     rax, rsp
0x140003690  mov     [rbp+3Fh+var_10], rax
0x140003694  mov     rcx, [rbp+3Fh+arg_30]
0x140003698  lea     rax, [rbp+3Fh+arg_18]
0x14000369c  mov     [rbp+3Fh+var_50], rax
0x1400036a0  xor     r8d, r8d
0x1400036a3  mov     [rbp+3Fh+var_48], 4
0x1400036ab  lea     rax, [rbp+3Fh+arg_20]
0x1400036af  mov     [rbp+3Fh+var_40], rax
0x1400036b3  lea     rax, [rbp+3Fh+arg_28]
0x1400036b7  mov     [rbp+3Fh+var_30], rax
0x1400036bb  mov     [rbp+3Fh+var_38], 4
0x1400036c3  lea     r9d, [r8+5]
0x1400036c7  mov     [rbp+3Fh+var_28], 4
0x1400036cf  test    rcx, rcx
0x1400036d2  jz      short loc_1400036E5
0x1400036d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400036d8  inc     rax
0x1400036db  cmp     [rcx+rax], r8b
0x1400036df  jnz     short loc_1400036D8
0x1400036e1  inc     eax
0x1400036e3  jmp     short loc_1400036E8
0x1400036e5  mov     eax, r9d
0x1400036e8  test    rcx, rcx
0x1400036eb  mov     [rbp+3Fh+var_18], eax
0x1400036ee  lea     rdx, aNull; "NULL"
0x1400036f5  mov     [rbp+3Fh+var_14], r8d
0x1400036f9  cmovz   rcx, rdx
0x1400036fd  lea     rax, [rbp+3Fh+var_60]
0x140003701  lea     rdx, WakeNotificationWorkItem
0x140003708  mov     [rbp+3Fh+var_20], rcx
0x14000370c  mov     [rsp+90h+var_70], rax
0x140003711  call    McGenEventWrite_EtwWriteTransfer
0x140003716  mov     rcx, [rbp+3Fh+var_10]
0x14000371a  xor     rcx, rsp; StackCookie
0x14000371d  call    __security_check_cookie
0x140003722  add     rsp, 90h
0x140003729  pop     rbp
0x14000372a  retn
```
