# McTemplateU0zzz_EventWriteTransfer

- ea: `0x18002ba2c`
- end: `0x18002bb21`
- name: `McTemplateU0zzz_EventWriteTransfer`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800291e4`

## callees

- `0x18001ada8`
- `0x18002ba2c`
- `0x180031040`

## pseudocode

```c
ULONG __fastcall McTemplateU0zzz_EventWriteTransfer(
        __int64 a1,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  const wchar_t *v5; // r10
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rcx
  __int64 v11; // rcx
  bool v12; // zf
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v15; // [rsp+40h] [rbp-48h]
  int v16; // [rsp+48h] [rbp-40h]
  int v17; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v18; // [rsp+50h] [rbp-38h]
  int v19; // [rsp+58h] [rbp-30h]
  int v20; // [rsp+5Ch] [rbp-2Ch]
  const wchar_t *v21; // [rsp+60h] [rbp-28h]
  int v22; // [rsp+68h] [rbp-20h]
  int v23; // [rsp+6Ch] [rbp-1Ch]

  v5 = a5;
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
  v16 = v9;
  v17 = 0;
  if ( !a3 )
    a3 = L"NULL";
  v15 = a3;
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = (unsigned int)(2 * v10 + 2);
  }
  else
  {
    v11 = 10;
  }
  v19 = v11;
  v20 = 0;
  if ( !a4 )
    a4 = L"NULL";
  v18 = a4;
  v12 = a5 == 0;
  if ( a5 )
  {
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
    v12 = a5 == 0;
  }
  if ( v12 )
    v5 = L"NULL";
  v22 = v7;
  v21 = v5;
  v23 = 0;
  return McGenEventWrite_EventWriteTransfer(v11, (const EVENT_DESCRIPTOR *)RediscoveredKDC, (__int64)a3, 4u, &v14);
}

```

## disassembly

```asm
0x18002ba2c  push    rbx
0x18002ba2e  sub     rsp, 80h
0x18002ba35  mov     rax, cs:__security_cookie
0x18002ba3c  xor     rax, rsp
0x18002ba3f  mov     [rsp+88h+var_18], rax
0x18002ba44  mov     r10, [rsp+88h+arg_20]
0x18002ba4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ba50  xor     r11d, r11d
0x18002ba53  mov     edx, 0Ah
0x18002ba58  test    r8, r8
0x18002ba5b  jz      short loc_18002BA73
0x18002ba5d  mov     rcx, rax
0x18002ba60  inc     rcx
0x18002ba63  cmp     [r8+rcx*2], r11w
0x18002ba68  jnz     short loc_18002BA60
0x18002ba6a  lea     ecx, ds:2[rcx*2]
0x18002ba71  jmp     short loc_18002BA75
0x18002ba73  mov     ecx, edx
0x18002ba75  test    r8, r8
0x18002ba78  mov     [rsp+88h+var_40], ecx
0x18002ba7c  lea     rbx, aNull_0; "NULL"
0x18002ba83  mov     [rsp+88h+var_3C], r11d
0x18002ba88  cmovz   r8, rbx
0x18002ba8c  mov     [rsp+88h+var_48], r8
0x18002ba91  test    r9, r9
0x18002ba94  jz      short loc_18002BAAC
0x18002ba96  mov     rcx, rax
0x18002ba99  inc     rcx
0x18002ba9c  cmp     [r9+rcx*2], r11w
0x18002baa1  jnz     short loc_18002BA99
0x18002baa3  lea     ecx, ds:2[rcx*2]
0x18002baaa  jmp     short loc_18002BAAE
0x18002baac  mov     ecx, edx
0x18002baae  test    r9, r9
0x18002bab1  mov     [rsp+88h+var_30], ecx
0x18002bab5  mov     [rsp+88h+var_2C], r11d
0x18002baba  cmovz   r9, rbx
0x18002babe  mov     [rsp+88h+var_38], r9
0x18002bac3  test    r10, r10
0x18002bac6  jz      short loc_18002BADC
0x18002bac8  inc     rax
0x18002bacb  cmp     [r10+rax*2], r11w
0x18002bad0  jnz     short loc_18002BAC8
0x18002bad2  lea     edx, ds:2[rax*2]
0x18002bad9  test    r10, r10
0x18002badc  cmovz   r10, rbx
0x18002bae0  mov     [rsp+88h+var_20], edx
0x18002bae4  lea     rax, [rsp+88h+var_58]
0x18002bae9  mov     [rsp+88h+var_28], r10
0x18002baee  lea     rdx, RediscoveredKDC
0x18002baf5  mov     [rsp+88h+var_68], rax
0x18002bafa  mov     r9d, 4
0x18002bb00  mov     [rsp+88h+var_1C], r11d
0x18002bb05  call    McGenEventWrite_EventWriteTransfer
0x18002bb0a  mov     rcx, [rsp+88h+var_18]
0x18002bb0f  xor     rcx, rsp; StackCookie
0x18002bb12  call    __security_check_cookie
0x18002bb17  add     rsp, 80h
0x18002bb1e  pop     rbx
0x18002bb1f  retn
```
