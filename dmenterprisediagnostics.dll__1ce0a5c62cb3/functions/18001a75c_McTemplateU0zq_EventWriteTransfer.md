# McTemplateU0zq_EventWriteTransfer

- ea: `0x18001a75c`
- end: `0x18001a7f6`
- name: `McTemplateU0zq_EventWriteTransfer`
- size: `154`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800193f0`

## callees

- `0x1800017e0`
- `0x18001a62c`
- `0x18001a75c`

## pseudocode

```c
ULONG __fastcall McTemplateU0zq_EventWriteTransfer(__int64 a1, __int64 a2, const wchar_t *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = L"NULL";
  v8 = a3;
  return McGenEventWrite_EventWriteTransfer(
           (__int64)L"NULL",
           (const EVENT_DESCRIPTOR *)TraceMerge_NGEN_BinaryNotFound,
           (__int64)a3,
           3u,
           &v7);
}

```

## disassembly

```asm
0x18001a75c  mov     [rsp+arg_18], r9d
0x18001a761  sub     rsp, 78h
0x18001a765  mov     rax, cs:__security_cookie
0x18001a76c  xor     rax, rsp
0x18001a76f  mov     [rsp+78h+var_18], rax
0x18001a774  xor     edx, edx
0x18001a776  test    r8, r8
0x18001a779  jz      short loc_18001A792
0x18001a77b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a77f  inc     rax
0x18001a782  cmp     [r8+rax*2], dx
0x18001a787  jnz     short loc_18001A77F
0x18001a789  lea     eax, ds:2[rax*2]
0x18001a790  jmp     short loc_18001A797
0x18001a792  mov     eax, 0Ah
0x18001a797  mov     [rsp+78h+var_30], eax
0x18001a79b  lea     rcx, aNull; "NULL"
0x18001a7a2  lea     rax, [rsp+78h+arg_18]
0x18001a7aa  mov     [rsp+78h+var_2C], edx
0x18001a7ae  test    r8, r8
0x18001a7b1  mov     [rsp+78h+var_28], rax
0x18001a7b6  lea     rax, [rsp+78h+var_48]
0x18001a7bb  mov     [rsp+78h+var_20], 4
0x18001a7c4  cmovz   r8, rcx
0x18001a7c8  mov     [rsp+78h+var_58], rax
0x18001a7cd  mov     r9d, 3
0x18001a7d3  mov     [rsp+78h+var_38], r8
0x18001a7d8  lea     rdx, TraceMerge_NGEN_BinaryNotFound
0x18001a7df  call    McGenEventWrite_EventWriteTransfer
0x18001a7e4  mov     rcx, [rsp+78h+var_18]
0x18001a7e9  xor     rcx, rsp; StackCookie
0x18001a7ec  call    __security_check_cookie
0x18001a7f1  add     rsp, 78h
0x18001a7f5  retn
```
