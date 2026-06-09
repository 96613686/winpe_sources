# McTemplateU0ss_EventWriteTransfer

- ea: `0x180016b04`
- end: `0x180016bb3`
- name: `McTemplateU0ss_EventWriteTransfer`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007370`
- `0x18000b9b4`

## callees

- `0x180013b20`
- `0x180016ab0`
- `0x180016b04`

## pseudocode

```c
ULONG __fastcall McTemplateU0ss_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const char *a3,
        const char *a4)
{
  __int64 v4; // rax
  int v6; // edx
  __int64 v7; // rcx
  int v8; // ecx
  bool v9; // zf
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-48h] BYREF
  const char *v12; // [rsp+40h] [rbp-38h]
  int v13; // [rsp+48h] [rbp-30h]
  int v14; // [rsp+4Ch] [rbp-2Ch]
  const char *v15; // [rsp+50h] [rbp-28h]
  int v16; // [rsp+58h] [rbp-20h]
  int v17; // [rsp+5Ch] [rbp-1Ch]

  v4 = -1;
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
      ++v4;
    while ( a4[v4] );
    v6 = v4 + 1;
    v9 = a4 == 0;
  }
  if ( v9 )
    a4 = "NULL";
  v16 = v6;
  v15 = a4;
  v17 = 0;
  return McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_EapMethods_RasChap_Context, a2, (__int64)a3, 3u, &v11);
}

```

## disassembly

```asm
0x180016b04  push    rbx
0x180016b06  sub     rsp, 70h
0x180016b0a  mov     rax, cs:__security_cookie
0x180016b11  xor     rax, rsp
0x180016b14  mov     [rsp+78h+var_18], rax
0x180016b19  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016b1d  xor     r11d, r11d
0x180016b20  mov     r10, rdx
0x180016b23  mov     edx, 5
0x180016b28  test    r8, r8
0x180016b2b  jz      short loc_180016B3D
0x180016b2d  mov     rcx, rax
0x180016b30  inc     rcx
0x180016b33  cmp     [r8+rcx], r11b
0x180016b37  jnz     short loc_180016B30
0x180016b39  inc     ecx
0x180016b3b  jmp     short loc_180016B3F
0x180016b3d  mov     ecx, edx
0x180016b3f  test    r8, r8
0x180016b42  mov     [rsp+78h+var_30], ecx
0x180016b46  lea     rbx, aNull; "NULL"
0x180016b4d  mov     [rsp+78h+var_2C], r11d
0x180016b52  cmovz   r8, rbx
0x180016b56  mov     [rsp+78h+var_38], r8
0x180016b5b  test    r9, r9
0x180016b5e  jz      short loc_180016B6F
0x180016b60  inc     rax
0x180016b63  cmp     [r9+rax], r11b
0x180016b67  jnz     short loc_180016B60
0x180016b69  lea     edx, [rax+1]
0x180016b6c  test    r9, r9
0x180016b6f  cmovz   r9, rbx
0x180016b73  mov     [rsp+78h+var_20], edx
0x180016b77  mov     [rsp+78h+var_28], r9
0x180016b7c  lea     rax, [rsp+78h+var_48]
0x180016b81  mov     r9d, 3
0x180016b87  mov     [rsp+78h+var_1C], r11d
0x180016b8c  mov     rdx, r10
0x180016b8f  mov     [rsp+78h+var_58], rax
0x180016b94  lea     rcx, Microsoft_Windows_EapMethods_RasChap_Context
0x180016b9b  call    McGenEventWrite_EventWriteTransfer
0x180016ba0  mov     rcx, [rsp+78h+var_18]
0x180016ba5  xor     rcx, rsp; StackCookie
0x180016ba8  call    __security_check_cookie
0x180016bad  add     rsp, 70h
0x180016bb1  pop     rbx
0x180016bb2  retn
```
