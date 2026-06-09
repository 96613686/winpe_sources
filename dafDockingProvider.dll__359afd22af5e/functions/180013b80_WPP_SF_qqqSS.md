# WPP_SF_qqqSS

- ea: `0x180013b80`
- end: `0x180013c77`
- name: `WPP_SF_qqqSS`
- size: `247`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, char, char, __int64, __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180011550`
- `0x180011d84`
- `0x1800123fc`
- `0x180012698`
- `0x180012860`

## callees

- `0x180013b80`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180013c60`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180013c60`

## pseudocode

```c
ULONG WPP_SF_qqqSS(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, __int64 a4, char a5, ...)
{
  const wchar_t *v5; // r9
  __int64 v6; // rax
  __int64 v8; // r10
  __int64 v9; // r8
  __int64 v10; // r8
  const wchar_t *v11; // rcx
  bool v12; // zf
  __int64 v14; // [rsp+A8h] [rbp+20h] BYREF
  __int64 v15; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  const wchar_t *v17; // [rsp+C0h] [rbp+38h]
  const wchar_t *v18; // [rsp+C8h] [rbp+40h]
  va_list va1; // [rsp+D0h] [rbp+48h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v15 = va_arg(va1, _QWORD);
  v17 = va_arg(va1, const wchar_t *);
  v18 = va_arg(va1, const wchar_t *);
  v14 = a4;
  v5 = v18;
  v6 = -1;
  v8 = 10;
  if ( v18 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v18[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v10 = 10;
  }
  v11 = v17;
  if ( !v18 )
    v5 = L"NULL";
  v12 = v17 == 0;
  if ( v17 )
  {
    do
      ++v6;
    while ( v17[v6] );
    v8 = 2 * v6 + 2;
    v12 = v17 == 0;
  }
  if ( v12 )
    v11 = L"NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
           a2,
           &v14,
           8,
           &a5,
           8,
           va,
           8,
           v11,
           v8,
           v5,
           v10,
           0);
}

```

## disassembly

```asm
0x180013b80  mov     [rsp+arg_0], rbx
0x180013b85  mov     [rsp+arg_18], r9
0x180013b8a  push    rdi
0x180013b8b  sub     rsp, 80h
0x180013b92  mov     r9, [rsp+88h+arg_38]
0x180013b9a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013b9e  xor     ebx, ebx
0x180013ba0  mov     r11, rcx
0x180013ba3  mov     r10d, 0Ah
0x180013ba9  test    r9, r9
0x180013bac  jz      short loc_180013BC5
0x180013bae  mov     r8, rax
0x180013bb1  inc     r8
0x180013bb4  cmp     [r9+r8*2], bx
0x180013bb9  jnz     short loc_180013BB1
0x180013bbb  lea     r8, ds:2[r8*2]
0x180013bc3  jmp     short loc_180013BC8
0x180013bc5  mov     r8, r10
0x180013bc8  mov     rcx, [rsp+88h+arg_30]
0x180013bd0  lea     rdi, aNull_0; "NULL"
0x180013bd7  test    r9, r9
0x180013bda  cmovz   r9, rdi
0x180013bde  test    rcx, rcx
0x180013be1  jz      short loc_180013BF7
0x180013be3  inc     rax
0x180013be6  cmp     [rcx+rax*2], bx
0x180013bea  jnz     short loc_180013BE3
0x180013bec  lea     r10, ds:2[rax*2]
0x180013bf4  test    rcx, rcx
0x180013bf7  mov     [rsp+88h+var_18], rbx
0x180013bfc  lea     rax, [rsp+88h+arg_28]
0x180013c04  mov     [rsp+88h+var_20], r8
0x180013c09  cmovz   rcx, rdi
0x180013c0d  mov     [rsp+88h+var_28], r9
0x180013c12  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids; MessageGuid
0x180013c19  mov     [rsp+88h+var_30], r10
0x180013c1e  mov     [rsp+88h+var_38], rcx
0x180013c23  mov     ecx, 8
0x180013c28  mov     [rsp+88h+var_40], rcx
0x180013c2d  mov     [rsp+88h+var_48], rax
0x180013c32  lea     rax, [rsp+88h+arg_20]
0x180013c3a  mov     [rsp+88h+var_50], rcx
0x180013c3f  mov     [rsp+88h+var_58], rax
0x180013c44  lea     rax, [rsp+88h+arg_18]
0x180013c4c  mov     [rsp+88h+var_60], rcx
0x180013c51  movzx   r9d, dx; MessageNumber
0x180013c55  lea     edx, [rcx+23h]; MessageFlags
0x180013c58  mov     rcx, r11; LoggerHandle
0x180013c5b  mov     [rsp+88h+var_68], rax
0x180013c60  call    cs:__imp_TraceMessage
0x180013c66  mov     rbx, [rsp+88h+arg_0]
0x180013c6e  add     rsp, 80h
0x180013c75  pop     rdi
0x180013c76  retn
```
