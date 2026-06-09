# WPP_RECORDER_SF_SD

- ea: `0x14000a7b8`
- end: `0x14000a8e1`
- name: `WPP_RECORDER_SF_SD`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400183a4`
- `0x14001aa98`

## callees

- `0x14000a7b8`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000a8c5`
- `WppRecorder!WppAutoLogTrace` at `0x14000a8c5`

## pseudocode

```c
__int64 WPP_RECORDER_SF_SD(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, __int64 a5, const wchar_t *a6, ...)
{
  const wchar_t *v6; // rbx
  __int64 v7; // rdi
  __int64 v10; // rax
  __int64 v11; // rdx
  const wchar_t *v12; // rcx
  bool v13; // zf
  int v15; // [rsp+20h] [rbp-68h]
  va_list va; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va, a6);
  v6 = a6;
  v7 = -1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
  {
    if ( a6 )
    {
      v10 = -1;
      do
        ++v10;
      while ( a6[v10] );
      v11 = 2 * v10 + 2;
    }
    else
    {
      v11 = 10;
    }
    v12 = a6;
    if ( !a6 )
      v12 = L"NULL";
    pfnWppTraceMessage(WPP_GLOBAL_Control->AttachedDevice, 43, a5, a4, v12, v11, va);
  }
  v13 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v13 = a6 == 0;
  }
  if ( v13 )
    v6 = L"NULL";
  LOWORD(v15) = a4;
  return WppAutoLogTrace(a1, 0, 17, a5, v15, v6);
}

```

## disassembly

```asm
0x14000a7b8  push    rbx
0x14000a7ba  push    rbp
0x14000a7bb  push    rsi
0x14000a7bc  push    rdi
0x14000a7bd  push    r13
0x14000a7bf  push    r14
0x14000a7c1  push    r15
0x14000a7c3  sub     rsp, 50h
0x14000a7c7  mov     rax, cs:WPP_GLOBAL_Control
0x14000a7ce  lea     r13, aNull_0; "NULL"
0x14000a7d5  mov     rbx, [rsp+88h+arg_28]
0x14000a7dd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000a7e1  xor     r15d, r15d
0x14000a7e4  movzx   ebp, r9w
0x14000a7e8  mov     r14, rcx
0x14000a7eb  test    dword ptr [rax+2Ch], 10000h
0x14000a7f2  lea     esi, [rdi+0Bh]
0x14000a7f5  jz      short loc_14000A86C
0x14000a7f7  test    rbx, rbx
0x14000a7fa  jz      short loc_14000A813
0x14000a7fc  mov     rax, rdi
0x14000a7ff  inc     rax
0x14000a802  cmp     [rbx+rax*2], r15w
0x14000a807  jnz     short loc_14000A7FF
0x14000a809  lea     rdx, ds:2[rax*2]
0x14000a811  jmp     short loc_14000A816
0x14000a813  mov     rdx, rsi
0x14000a816  mov     rax, cs:pfnWppTraceMessage
0x14000a81d  lea     r8, [rsp+88h+arg_30]
0x14000a825  mov     [rsp+88h+var_48], r15
0x14000a82a  test    rbx, rbx
0x14000a82d  mov     [rsp+88h+var_50], 4
0x14000a836  mov     rcx, rbx
0x14000a839  cmovz   rcx, r13
0x14000a83d  mov     [rsp+88h+var_58], r8
0x14000a842  mov     r8, [rsp+88h+arg_20]
0x14000a84a  mov     r9d, ebp
0x14000a84d  mov     [rsp+88h+var_60], rdx
0x14000a852  mov     edx, 2Bh ; '+'
0x14000a857  mov     [rsp+88h+var_68], rcx
0x14000a85c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a863  mov     rcx, [rcx+18h]
0x14000a867  call    _guard_dispatch_icall
0x14000a86c  test    rbx, rbx
0x14000a86f  jz      short loc_14000A886
0x14000a871  inc     rdi
0x14000a874  cmp     [rbx+rdi*2], r15w
0x14000a879  jnz     short loc_14000A871
0x14000a87b  lea     rsi, ds:2[rdi*2]
0x14000a883  test    rbx, rbx
0x14000a886  mov     r9, [rsp+88h+arg_20]
0x14000a88e  lea     rax, [rsp+88h+arg_30]
0x14000a896  mov     [rsp+88h+var_40], r15
0x14000a89b  cmovz   rbx, r13
0x14000a89f  mov     [rsp+88h+var_48], 4
0x14000a8a8  xor     edx, edx
0x14000a8aa  mov     [rsp+88h+var_50], rax
0x14000a8af  mov     rcx, r14
0x14000a8b2  mov     [rsp+88h+var_58], rsi
0x14000a8b7  mov     [rsp+88h+var_60], rbx
0x14000a8bc  lea     r8d, [rdx+11h]
0x14000a8c0  mov     word ptr [rsp+88h+var_68], bp
0x14000a8c5  call    cs:__imp_WppAutoLogTrace
0x14000a8cc  nop     dword ptr [rax+rax+00h]
0x14000a8d1  add     rsp, 50h
0x14000a8d5  pop     r15
0x14000a8d7  pop     r14
0x14000a8d9  pop     r13
0x14000a8db  pop     rdi
0x14000a8dc  pop     rsi
0x14000a8dd  pop     rbp
0x14000a8de  pop     rbx
0x14000a8df  retn
```
