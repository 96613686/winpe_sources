# McTemplateK0zzqbr2_EtwWriteTransfer

- ea: `0x14000d99c`
- end: `0x14000da7e`
- name: `McTemplateK0zzqbr2_EtwWriteTransfer`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e208`

## callees

- `0x14000d93c`
- `0x14000d99c`
- `0x1400161f0`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zzqbr2_EtwWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const GUID *a3,
        const char *a4,
        const char *a5,
        int a6,
        __int64 a7)
{
  __int64 v7; // rax
  int v9; // edx
  __int64 v10; // rcx
  int v11; // ecx
  const char *v12; // rcx
  bool v13; // zf
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-21h] BYREF
  const char *v16; // [rsp+40h] [rbp-11h]
  int v17; // [rsp+48h] [rbp-9h]
  int v18; // [rsp+4Ch] [rbp-5h]
  const char *v19; // [rsp+50h] [rbp-1h]
  int v20; // [rsp+58h] [rbp+7h]
  int v21; // [rsp+5Ch] [rbp+Bh]
  int *v22; // [rsp+60h] [rbp+Fh]
  __int64 v23; // [rsp+68h] [rbp+17h]
  __int64 v24; // [rsp+70h] [rbp+1Fh]
  int v25; // [rsp+78h] [rbp+27h]
  int v26; // [rsp+7Ch] [rbp+2Bh]

  v7 = -1;
  v9 = 10;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&a4[2 * v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  v17 = v11;
  v12 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v18 = 0;
  v16 = a4;
  v13 = a5 == 0;
  if ( a5 )
  {
    do
      ++v7;
    while ( *(_WORD *)&a5[2 * v7] );
    v9 = 2 * v7 + 2;
    v13 = a5 == 0;
  }
  v20 = v9;
  v22 = &a6;
  if ( v13 )
    v12 = L"NULL";
  v24 = a7;
  v25 = a6;
  v19 = v12;
  v21 = 0;
  v23 = 4;
  v26 = 0;
  return McGenEventWrite_EtwWriteTransfer((__int64)v12, a2, a3, (__int64)a4, &v15);
}

```

## disassembly

```asm
0x14000d99c  mov     [rsp-8+arg_0], rbx
0x14000d9a1  push    rbp
0x14000d9a2  lea     rbp, [rsp-3Fh]
0x14000d9a7  sub     rsp, 90h
0x14000d9ae  mov     rax, cs:__security_cookie
0x14000d9b5  xor     rax, rsp
0x14000d9b8  mov     [rbp+3Fh+var_10], rax
0x14000d9bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d9c0  xor     r11d, r11d
0x14000d9c3  mov     r10, rdx
0x14000d9c6  mov     edx, 0Ah
0x14000d9cb  test    r9, r9
0x14000d9ce  jz      short loc_14000D9E6
0x14000d9d0  mov     rcx, rax
0x14000d9d3  inc     rcx
0x14000d9d6  cmp     [r9+rcx*2], r11w
0x14000d9db  jnz     short loc_14000D9D3
0x14000d9dd  lea     ecx, ds:2[rcx*2]
0x14000d9e4  jmp     short loc_14000D9E8
0x14000d9e6  mov     ecx, edx
0x14000d9e8  test    r9, r9
0x14000d9eb  mov     [rbp+3Fh+var_48], ecx
0x14000d9ee  mov     rcx, [rbp+3Fh+arg_20]
0x14000d9f2  lea     rbx, aNull_0; "NULL"
0x14000d9f9  cmovz   r9, rbx; int
0x14000d9fd  mov     [rbp+3Fh+var_44], r11d
0x14000da01  mov     [rbp+3Fh+var_50], r9
0x14000da05  test    rcx, rcx
0x14000da08  jz      short loc_14000DA1E
0x14000da0a  inc     rax
0x14000da0d  cmp     [rcx+rax*2], r11w
0x14000da12  jnz     short loc_14000DA0A
0x14000da14  lea     edx, ds:2[rax*2]
0x14000da1b  test    rcx, rcx
0x14000da1e  lea     rax, [rbp+3Fh+arg_28]
0x14000da22  mov     [rbp+3Fh+var_38], edx
0x14000da25  mov     [rbp+3Fh+var_30], rax
0x14000da29  cmovz   rcx, rbx; int
0x14000da2d  mov     rax, [rbp+3Fh+arg_30]
0x14000da31  mov     rdx, r10; int
0x14000da34  mov     [rbp+3Fh+var_20], rax
0x14000da38  mov     eax, [rbp+3Fh+arg_28]
0x14000da3b  mov     [rbp+3Fh+var_18], eax
0x14000da3e  lea     rax, [rbp+3Fh+var_60]
0x14000da42  mov     [rsp+90h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x14000da47  mov     [rbp+3Fh+var_40], rcx
0x14000da4b  mov     [rbp+3Fh+var_34], r11d
0x14000da4f  mov     [rbp+3Fh+var_28], 4
0x14000da57  mov     [rbp+3Fh+var_14], r11d
0x14000da5b  call    McGenEventWrite_EtwWriteTransfer
0x14000da60  mov     rcx, [rbp+3Fh+var_10]
0x14000da64  xor     rcx, rsp; StackCookie
0x14000da67  call    __security_check_cookie
0x14000da6c  mov     rbx, [rsp+90h+arg_0]
0x14000da74  add     rsp, 90h
0x14000da7b  pop     rbp
0x14000da7c  retn
```
