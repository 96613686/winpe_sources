# McTemplateU0qzq_EventWriteTransfer

- ea: `0x180012740`
- end: `0x1800127e5`
- name: `McTemplateU0qzq_EventWriteTransfer`
- size: `165`
- prototype: `ULONG __fastcall(__int64, __int64, int, const wchar_t *, char)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ee0`
- `0x180010ec4`
- `0x180011f80`

## callees

- `0x180004c2c`
- `0x180012740`
- `0x18001cc70`

## pseudocode

```c
ULONG __fastcall McTemplateU0qzq_EventWriteTransfer(__int64 a1, __int64 a2, int a3, const wchar_t *a4, char a5)
{
  __int64 v5; // rax
  int v6; // eax
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-50h] BYREF
  int *v9; // [rsp+40h] [rbp-40h]
  __int64 v10; // [rsp+48h] [rbp-38h]
  const wchar_t *v11; // [rsp+50h] [rbp-30h]
  int v12; // [rsp+58h] [rbp-28h]
  int v13; // [rsp+5Ch] [rbp-24h]
  char *v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+A0h] [rbp+20h] BYREF

  v16 = a3;
  v9 = &v16;
  v10 = 4;
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
  v15 = 4;
  v11 = a4;
  v14 = &a5;
  return McGenEventWrite_EventWriteTransfer((__int64)L"NULL", (const EVENT_DESCRIPTOR *)ProbeEnd, 4, 4u, &v8);
}

```

## disassembly

```asm
0x180012740  mov     [rsp-8+arg_10], r8d
0x180012745  push    rbp
0x180012746  mov     rbp, rsp
0x180012749  sub     rsp, 80h
0x180012750  mov     rax, cs:__security_cookie
0x180012757  xor     rax, rsp
0x18001275a  mov     [rbp+var_10], rax
0x18001275e  xor     edx, edx
0x180012760  lea     rax, [rbp+arg_10]
0x180012764  mov     [rbp+var_40], rax
0x180012768  mov     r8d, 4
0x18001276e  mov     [rbp+var_38], r8
0x180012772  test    r9, r9
0x180012775  jz      short loc_18001278E
0x180012777  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001277b  inc     rax
0x18001277e  cmp     [r9+rax*2], dx
0x180012783  jnz     short loc_18001277B
0x180012785  lea     eax, ds:2[rax*2]
0x18001278c  jmp     short loc_180012793
0x18001278e  mov     eax, 0Ah
0x180012793  test    r9, r9
0x180012796  mov     [rbp+var_28], eax
0x180012799  lea     rcx, aNull_0; "NULL"
0x1800127a0  mov     [rbp+var_24], edx
0x1800127a3  cmovz   r9, rcx
0x1800127a7  mov     [rbp+var_18], r8
0x1800127ab  lea     rax, [rbp+arg_20]
0x1800127af  mov     [rbp+var_30], r9
0x1800127b3  mov     [rbp+var_20], rax
0x1800127b7  lea     rdx, ProbeEnd
0x1800127be  lea     rax, [rbp+var_50]
0x1800127c2  mov     r9d, r8d
0x1800127c5  mov     [rsp+80h+var_60], rax
0x1800127ca  call    McGenEventWrite_EventWriteTransfer
0x1800127cf  mov     rcx, [rbp+var_10]
0x1800127d3  xor     rcx, rsp; StackCookie
0x1800127d6  call    __security_check_cookie
0x1800127db  add     rsp, 80h
0x1800127e2  pop     rbp
0x1800127e3  retn
```
