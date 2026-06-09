# McTemplateU0qzxxg_EventWriteTransfer

- ea: `0x140016b80`
- end: `0x140016c4e`
- name: `McTemplateU0qzxxg_EventWriteTransfer`
- size: `206`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, const wchar_t *, char, char, char)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140010814`

## callees

- `0x1400029a0`
- `0x140016058`
- `0x140016b80`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzxxg_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        char a5,
        char a6,
        char a7)
{
  __int64 v7; // rax
  int v8; // eax
  int v10; // [rsp+30h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-31h] BYREF
  int *v12; // [rsp+50h] [rbp-21h]
  __int64 v13; // [rsp+58h] [rbp-19h]
  const wchar_t *v14; // [rsp+60h] [rbp-11h]
  int v15; // [rsp+68h] [rbp-9h]
  int v16; // [rsp+6Ch] [rbp-5h]
  char *v17; // [rsp+70h] [rbp-1h]
  __int64 v18; // [rsp+78h] [rbp+7h]
  char *v19; // [rsp+80h] [rbp+Fh]
  __int64 v20; // [rsp+88h] [rbp+17h]
  char *v21; // [rsp+90h] [rbp+1Fh]
  __int64 v22; // [rsp+98h] [rbp+27h]

  v10 = 2;
  v13 = 4;
  v12 = &v10;
  if ( a4 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a4[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  v15 = v8;
  v16 = 0;
  v18 = 8;
  v17 = &a5;
  if ( !a4 )
    a4 = L"NULL";
  v20 = 8;
  v14 = a4;
  v19 = &a6;
  v22 = 8;
  v21 = &a7;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", (const EVENT_DESCRIPTOR *)CleanmgrInit, a3, 6u, &v11);
}

```

## disassembly

```asm
0x140016b80  push    rbp
0x140016b82  lea     rbp, [rsp-3Fh]
0x140016b87  sub     rsp, 0B0h
0x140016b8e  mov     rax, cs:__security_cookie
0x140016b95  xor     rax, rsp
0x140016b98  mov     [rbp+3Fh+var_10], rax
0x140016b9c  xor     edx, edx
0x140016b9e  mov     [rbp+3Fh+var_80], 2
0x140016ba5  mov     [rbp+3Fh+var_58], 4
0x140016bad  lea     rax, [rbp+3Fh+var_80]
0x140016bb1  mov     [rbp+3Fh+var_60], rax
0x140016bb5  test    r9, r9
0x140016bb8  jz      short loc_140016BD1
0x140016bba  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016bbe  inc     rax
0x140016bc1  cmp     [r9+rax*2], dx
0x140016bc6  jnz     short loc_140016BBE
0x140016bc8  lea     eax, ds:2[rax*2]
0x140016bcf  jmp     short loc_140016BD6
0x140016bd1  mov     eax, 0Ah
0x140016bd6  mov     [rbp+3Fh+var_48], eax
0x140016bd9  lea     rcx, aNull_0; "NULL"
0x140016be0  test    r9, r9
0x140016be3  mov     [rbp+3Fh+var_44], edx
0x140016be6  lea     rax, [rbp+3Fh+arg_20]
0x140016bea  mov     [rbp+3Fh+var_38], 8
0x140016bf2  mov     [rbp+3Fh+var_40], rax
0x140016bf6  lea     rdx, CleanmgrInit
0x140016bfd  cmovz   r9, rcx
0x140016c01  mov     [rbp+3Fh+var_28], 8
0x140016c09  lea     rax, [rbp+3Fh+arg_28]
0x140016c0d  mov     [rbp+3Fh+var_50], r9
0x140016c11  mov     [rbp+3Fh+var_30], rax
0x140016c15  mov     r9d, 6
0x140016c1b  lea     rax, [rbp+3Fh+arg_30]
0x140016c1f  mov     [rbp+3Fh+var_18], 8
0x140016c27  mov     [rbp+3Fh+var_20], rax
0x140016c2b  lea     rax, [rbp+3Fh+var_70]
0x140016c2f  mov     [rsp+0B0h+var_90], rax
0x140016c34  call    McGenEventWrite_EventWriteTransfer
0x140016c39  mov     rcx, [rbp+3Fh+var_10]
0x140016c3d  xor     rcx, rsp; StackCookie
0x140016c40  call    __security_check_cookie
0x140016c45  add     rsp, 0B0h
0x140016c4c  pop     rbp
0x140016c4d  retn
```
