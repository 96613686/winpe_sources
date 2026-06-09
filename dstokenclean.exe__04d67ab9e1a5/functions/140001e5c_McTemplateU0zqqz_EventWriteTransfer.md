# McTemplateU0zqqz_EventWriteTransfer

- ea: `0x140001e5c`
- end: `0x140001f33`
- name: `McTemplateU0zqqz_EventWriteTransfer`
- size: `215`
- prototype: `ULONG __fastcall(__int64, const EVENT_DESCRIPTOR *, const char *, int, char, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001b0c`
- `0x140001bcc`

## callees

- `0x140001e00`
- `0x140001e5c`
- `0x140001ff0`

## pseudocode

```c
ULONG __fastcall McTemplateU0zqqz_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        const char *a3,
        int a4,
        char a5,
        const char *a6)
{
  __int64 v6; // rax
  int v8; // edx
  __int64 v9; // rcx
  int v10; // ecx
  const char *v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-19h] BYREF
  const char *v15; // [rsp+40h] [rbp-9h]
  int v16; // [rsp+48h] [rbp-1h]
  int v17; // [rsp+4Ch] [rbp+3h]
  int *v18; // [rsp+50h] [rbp+7h]
  __int64 v19; // [rsp+58h] [rbp+Fh]
  char *v20; // [rsp+60h] [rbp+17h]
  __int64 v21; // [rsp+68h] [rbp+1Fh]
  const char *v22; // [rsp+70h] [rbp+27h]
  int v23; // [rsp+78h] [rbp+2Fh]
  int v24; // [rsp+7Ch] [rbp+33h]
  int v25; // [rsp+B8h] [rbp+6Fh] BYREF

  v25 = a4;
  v6 = -1;
  v8 = 10;
  if ( a3 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&a3[2 * v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v16 = v10;
  v17 = 0;
  v18 = &v25;
  v19 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v20 = &a5;
  v11 = a6;
  v15 = a3;
  v21 = 4;
  v12 = a6 == 0;
  if ( a6 )
  {
    do
      ++v6;
    while ( *(_WORD *)&a6[2 * v6] );
    v8 = 2 * v6 + 2;
    v12 = a6 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  v23 = v8;
  v22 = v11;
  v24 = 0;
  return McGenEventWrite_EventWriteTransfer((__int64)v11, a2, (__int64)a3, (__int64)a2, &v14);
}

```

## disassembly

```asm
0x140001e5c  mov     [rsp-8+arg_18], r9d
0x140001e61  push    rbp
0x140001e62  lea     rbp, [rsp-47h]
0x140001e67  sub     rsp, 90h
0x140001e6e  mov     rax, cs:__security_cookie
0x140001e75  xor     rax, rsp
0x140001e78  mov     [rbp+47h+var_10], rax
0x140001e7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001e80  xor     r10d, r10d
0x140001e83  mov     r9, rdx; int
0x140001e86  mov     edx, 0Ah
0x140001e8b  test    r8, r8
0x140001e8e  jz      short loc_140001EA6
0x140001e90  mov     rcx, rax
0x140001e93  inc     rcx
0x140001e96  cmp     [r8+rcx*2], r10w
0x140001e9b  jnz     short loc_140001E93
0x140001e9d  lea     ecx, ds:2[rcx*2]
0x140001ea4  jmp     short loc_140001EA8
0x140001ea6  mov     ecx, edx
0x140001ea8  mov     [rbp+47h+var_48], ecx
0x140001eab  lea     r11, aNull; "NULL"
0x140001eb2  lea     rcx, [rbp+47h+arg_18]
0x140001eb6  mov     [rbp+47h+var_44], r10d
0x140001eba  mov     [rbp+47h+var_40], rcx
0x140001ebe  test    r8, r8
0x140001ec1  lea     rcx, [rbp+47h+arg_20]
0x140001ec5  mov     [rbp+47h+var_38], 4
0x140001ecd  cmovz   r8, r11; int
0x140001ed1  mov     [rbp+47h+var_30], rcx
0x140001ed5  mov     rcx, [rbp+47h+arg_28]
0x140001ed9  mov     [rbp+47h+var_50], r8
0x140001edd  mov     [rbp+47h+var_28], 4
0x140001ee5  test    rcx, rcx
0x140001ee8  jz      short loc_140001EFE
0x140001eea  inc     rax
0x140001eed  cmp     [rcx+rax*2], r10w
0x140001ef2  jnz     short loc_140001EEA
0x140001ef4  lea     edx, ds:2[rax*2]
0x140001efb  test    rcx, rcx
0x140001efe  cmovz   rcx, r11; int
0x140001f02  mov     [rbp+47h+var_18], edx
0x140001f05  lea     rax, [rbp+47h+var_60]
0x140001f09  mov     [rbp+47h+var_20], rcx
0x140001f0d  mov     rdx, r9; int
0x140001f10  mov     [rsp+90h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x140001f15  mov     [rbp+47h+var_14], r10d
0x140001f19  call    McGenEventWrite_EventWriteTransfer
0x140001f1e  mov     rcx, [rbp+47h+var_10]
0x140001f22  xor     rcx, rsp; StackCookie
0x140001f25  call    __security_check_cookie
0x140001f2a  add     rsp, 90h
0x140001f31  pop     rbp
0x140001f32  retn
```
