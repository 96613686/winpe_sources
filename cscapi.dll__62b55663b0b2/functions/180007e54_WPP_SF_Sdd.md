# WPP_SF_Sdd

- ea: `0x180007e54`
- end: `0x180007ee1`
- name: `WPP_SF_Sdd`
- size: `141`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004000`
- `0x1800045b0`
- `0x180004cf0`
- `0x180004f10`
- `0x1800052f0`
- `0x1800057f0`

## callees

- `0x180007e54`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180007ed6`
- `ntdll!EtwTraceMessage` at `0x180007ed6`

## pseudocode

```c
__int64 WPP_SF_Sdd(__int64 a1, __int64 a2, __int64 a3, const wchar_t *a4, ...)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v7; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v7 = va_arg(va1, _QWORD);
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = 2 * v4 + 2;
  }
  else
  {
    v5 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids, 11, a4, v5, (__int64 *)va, 4, va1);
}

```

## disassembly

```asm
0x180007e54  sub     rsp, 68h
0x180007e58  xor     r8d, r8d
0x180007e5b  test    r9, r9
0x180007e5e  jz      short loc_180007E78
0x180007e60  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007e64  inc     rax
0x180007e67  cmp     [r9+rax*2], r8w
0x180007e6c  jnz     short loc_180007E64
0x180007e6e  lea     rax, ds:2[rax*2]
0x180007e76  jmp     short loc_180007E7D
0x180007e78  mov     eax, 0Ah
0x180007e7d  mov     [rsp+68h+var_18], r8
0x180007e82  lea     rdx, aNull_0; "NULL"
0x180007e89  mov     r10d, 0Bh
0x180007e8f  test    r9, r9
0x180007e92  cmovz   r9, rdx
0x180007e96  lea     rdx, [rsp+68h+arg_28]
0x180007e9e  lea     r8d, [r10-7]
0x180007ea2  mov     [rsp+68h+var_20], r8
0x180007ea7  mov     [rsp+68h+var_28], rdx
0x180007eac  lea     rdx, [rsp+68h+arg_20]
0x180007eb4  mov     [rsp+68h+var_30], r8
0x180007eb9  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x180007ec0  mov     [rsp+68h+var_38], rdx
0x180007ec5  lea     edx, [r10+20h]
0x180007ec9  mov     [rsp+68h+var_40], rax
0x180007ece  mov     [rsp+68h+var_48], r9
0x180007ed3  mov     r9d, r10d
0x180007ed6  call    cs:__imp_EtwTraceMessage
0x180007edc  add     rsp, 68h
0x180007ee0  retn
```
