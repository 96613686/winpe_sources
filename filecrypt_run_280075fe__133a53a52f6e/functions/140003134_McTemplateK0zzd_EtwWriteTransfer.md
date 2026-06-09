# McTemplateK0zzd_EtwWriteTransfer

- ea: `0x140003134`
- end: `0x140003206`
- name: `McTemplateK0zzd_EtwWriteTransfer`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f2f0`

## callees

- `0x140002f6c`
- `0x140003134`
- `0x140003540`

## pseudocode

```c
NTSTATUS __fastcall McTemplateK0zzd_EtwWriteTransfer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        const wchar_t *a5,
        char a6)
{
  __int64 v6; // rax
  int v7; // edx
  __int64 v8; // rcx
  int v9; // ecx
  const wchar_t *v10; // rcx
  bool v11; // zf
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-58h] BYREF
  const wchar_t *v14; // [rsp+40h] [rbp-48h]
  int v15; // [rsp+48h] [rbp-40h]
  int v16; // [rsp+4Ch] [rbp-3Ch]
  const wchar_t *v17; // [rsp+50h] [rbp-38h]
  int v18; // [rsp+58h] [rbp-30h]
  int v19; // [rsp+5Ch] [rbp-2Ch]
  char *v20; // [rsp+60h] [rbp-28h]
  __int64 v21; // [rsp+68h] [rbp-20h]

  v6 = -1;
  v7 = 10;
  if ( a4 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a4[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  v15 = v9;
  v10 = a5;
  if ( !a4 )
    a4 = L"NULL";
  v16 = 0;
  v14 = a4;
  v11 = a5 == 0;
  if ( a5 )
  {
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
    v11 = a5 == 0;
  }
  v18 = v7;
  v20 = &a6;
  v19 = 0;
  if ( v11 )
    v10 = L"NULL";
  v17 = v10;
  v21 = 4;
  return McGenEventWrite_EtwWriteTransfer((__int64)v10, (const EVENT_DESCRIPTOR *)MoveAcrossChamberFailure, 0, 4u, &v13);
}

```

## disassembly

```asm
0x140003134  sub     rsp, 88h
0x14000313b  mov     rax, cs:__security_cookie
0x140003142  xor     rax, rsp
0x140003145  mov     [rsp+88h+var_18], rax
0x14000314a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000314e  xor     r8d, r8d
0x140003151  mov     edx, 0Ah
0x140003156  test    r9, r9
0x140003159  jz      short loc_140003171
0x14000315b  mov     rcx, rax
0x14000315e  inc     rcx
0x140003161  cmp     [r9+rcx*2], r8w
0x140003166  jnz     short loc_14000315E
0x140003168  lea     ecx, ds:2[rcx*2]
0x14000316f  jmp     short loc_140003173
0x140003171  mov     ecx, edx
0x140003173  test    r9, r9
0x140003176  mov     [rsp+88h+var_40], ecx
0x14000317a  mov     rcx, [rsp+88h+arg_20]
0x140003182  lea     r10, aNull_1; "NULL"
0x140003189  cmovz   r9, r10
0x14000318d  mov     [rsp+88h+var_3C], r8d
0x140003192  mov     [rsp+88h+var_48], r9
0x140003197  test    rcx, rcx
0x14000319a  jz      short loc_1400031B0
0x14000319c  inc     rax
0x14000319f  cmp     [rcx+rax*2], r8w
0x1400031a4  jnz     short loc_14000319C
0x1400031a6  lea     edx, ds:2[rax*2]
0x1400031ad  test    rcx, rcx
0x1400031b0  lea     rax, [rsp+88h+arg_28]
0x1400031b8  mov     [rsp+88h+var_30], edx
0x1400031bc  mov     [rsp+88h+var_28], rax
0x1400031c1  lea     rdx, MoveAcrossChamberFailure
0x1400031c8  lea     rax, [rsp+88h+var_58]
0x1400031cd  mov     [rsp+88h+var_2C], r8d
0x1400031d2  cmovz   rcx, r10
0x1400031d6  mov     [rsp+88h+var_68], rax
0x1400031db  mov     r9d, 4
0x1400031e1  mov     [rsp+88h+var_38], rcx
0x1400031e6  mov     [rsp+88h+var_20], r9
0x1400031eb  call    McGenEventWrite_EtwWriteTransfer
0x1400031f0  mov     rcx, [rsp+88h+var_18]
0x1400031f5  xor     rcx, rsp; StackCookie
0x1400031f8  call    __security_check_cookie
0x1400031fd  add     rsp, 88h
0x140003204  retn
```
