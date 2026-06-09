# WPP_SF_dSD

- ea: `0x140002d54`
- end: `0x140002dfb`
- name: `WPP_SF_dSD`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002c48`

## callees

- `0x140002d54`
- `0x140003e00`

## pseudocode

```c
__int64 WPP_SF_dSD(__int64 a1, __int64 a2, __int64 a3, int a4, const wchar_t *a5, ...)
{
  const wchar_t *v5; // rdx
  __int64 v7; // rax
  __int64 v8; // rcx
  int v10; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v10 = a4;
  v5 = a5;
  if ( a5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a5[v7] );
    v8 = 2 * v7 + 2;
  }
  else
  {
    v8 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64, int *, __int64, const wchar_t *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_946236d2e182355298098a526199d40a_Traceguids,
           11,
           &v10,
           4,
           v5,
           v8,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x140002d54  mov     [rsp+arg_18], r9d
0x140002d59  sub     rsp, 68h
0x140002d5d  mov     rdx, [rsp+68h+arg_20]
0x140002d65  xor     r8d, r8d
0x140002d68  mov     r10, rcx
0x140002d6b  test    rdx, rdx
0x140002d6e  jz      short loc_140002D88
0x140002d70  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002d74  inc     rax
0x140002d77  cmp     [rdx+rax*2], r8w
0x140002d7c  jnz     short loc_140002D74
0x140002d7e  lea     rcx, ds:2[rax*2]
0x140002d86  jmp     short loc_140002D8D
0x140002d88  mov     ecx, 0Ah
0x140002d8d  mov     [rsp+68h+var_18], r8
0x140002d92  lea     rax, aNull_0; "NULL"
0x140002d99  mov     r11d, 0Bh
0x140002d9f  lea     r8, [rsp+68h+arg_28]
0x140002da7  test    rdx, rdx
0x140002daa  cmovz   rdx, rax
0x140002dae  mov     rax, cs:pfnWppTraceMessage
0x140002db5  lea     r9d, [r11-7]
0x140002db9  mov     [rsp+68h+var_20], r9
0x140002dbe  mov     [rsp+68h+var_28], r8
0x140002dc3  lea     r8, WPP_946236d2e182355298098a526199d40a_Traceguids
0x140002dca  mov     [rsp+68h+var_30], rcx
0x140002dcf  lea     rcx, [rsp+68h+arg_18]
0x140002dd7  mov     [rsp+68h+var_38], rdx
0x140002ddc  lea     edx, [r11+20h]
0x140002de0  mov     [rsp+68h+var_40], r9
0x140002de5  mov     r9d, r11d
0x140002de8  mov     [rsp+68h+var_48], rcx
0x140002ded  mov     rcx, r10
0x140002df0  call    _guard_dispatch_icall
0x140002df5  add     rsp, 68h
0x140002df9  retn
```
