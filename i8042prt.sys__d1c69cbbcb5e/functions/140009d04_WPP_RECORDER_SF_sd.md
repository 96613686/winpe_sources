# WPP_RECORDER_SF_sd

- ea: `0x140009d04`
- end: `0x140009e22`
- name: `WPP_RECORDER_SF_sd`
- size: `286`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e700`
- `0x14001e870`

## callees

- `0x140009d04`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140009e08`
- `WppRecorder!WppAutoLogTrace` at `0x140009e08`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sd(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, const char *a6, ...)
{
  const char *v6; // rbx
  __int64 v7; // rdi
  __int64 v10; // rax
  __int64 v11; // rdx
  const char *v12; // rcx
  bool v13; // zf
  int v15; // [rsp+20h] [rbp-68h]
  va_list va; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va, a6);
  v6 = a6;
  v7 = -1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
  {
    if ( a6 )
    {
      v10 = -1;
      do
        ++v10;
      while ( a6[v10] );
      v11 = v10 + 1;
    }
    else
    {
      v11 = 5;
    }
    v12 = a6;
    if ( !a6 )
      v12 = "NULL";
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids,
      a4,
      v12,
      v11,
      va);
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
    v6 = "NULL";
  LOWORD(v15) = a4;
  return WppAutoLogTrace(a1, 0, 16, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids, v15, v6);
}

```

## disassembly

```asm
0x140009d04  push    rbx
0x140009d06  push    rbp
0x140009d07  push    rsi
0x140009d08  push    rdi
0x140009d09  push    r13
0x140009d0b  push    r14
0x140009d0d  sub     rsp, 58h
0x140009d11  mov     rax, cs:WPP_GLOBAL_Control
0x140009d18  lea     r13, aNull; "NULL"
0x140009d1f  mov     rbx, [rsp+88h+arg_28]
0x140009d27  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140009d2b  movzx   ebp, r9w
0x140009d2f  mov     r14, rcx
0x140009d32  test    dword ptr [rax+2Ch], 8000h
0x140009d39  lea     esi, [rdi+6]
0x140009d3c  jz      short loc_140009DB1
0x140009d3e  test    rbx, rbx
0x140009d41  jz      short loc_140009D55
0x140009d43  mov     rax, rdi
0x140009d46  inc     rax
0x140009d49  cmp     byte ptr [rbx+rax], 0
0x140009d4d  jnz     short loc_140009D46
0x140009d4f  lea     rdx, [rax+1]
0x140009d53  jmp     short loc_140009D58
0x140009d55  mov     rdx, rsi
0x140009d58  mov     rax, cs:pfnWppTraceMessage
0x140009d5f  lea     r8, [rsp+88h+arg_30]
0x140009d67  mov     [rsp+88h+var_48], 0
0x140009d70  test    rbx, rbx
0x140009d73  mov     [rsp+88h+var_50], 4
0x140009d7c  mov     rcx, rbx
0x140009d7f  cmovz   rcx, r13
0x140009d83  mov     [rsp+88h+var_58], r8
0x140009d88  mov     [rsp+88h+var_60], rdx
0x140009d8d  lea     r8, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x140009d94  mov     [rsp+88h+var_68], rcx
0x140009d99  mov     r9d, ebp
0x140009d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009da3  mov     edx, 2Bh ; '+'
0x140009da8  mov     rcx, [rcx+18h]
0x140009dac  call    _guard_dispatch_icall
0x140009db1  test    rbx, rbx
0x140009db4  jz      short loc_140009DC6
0x140009db6  inc     rdi
0x140009db9  cmp     byte ptr [rbx+rdi], 0
0x140009dbd  jnz     short loc_140009DB6
0x140009dbf  lea     rsi, [rdi+1]
0x140009dc3  test    rbx, rbx
0x140009dc6  mov     [rsp+88h+var_40], 0
0x140009dcf  lea     rax, [rsp+88h+arg_30]
0x140009dd7  mov     [rsp+88h+var_48], 4
0x140009de0  lea     r9, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x140009de7  mov     [rsp+88h+var_50], rax
0x140009dec  cmovz   rbx, r13
0x140009df0  xor     edx, edx
0x140009df2  mov     [rsp+88h+var_58], rsi
0x140009df7  mov     [rsp+88h+var_60], rbx
0x140009dfc  mov     rcx, r14
0x140009dff  mov     word ptr [rsp+88h+var_68], bp
0x140009e04  lea     r8d, [rdx+10h]
0x140009e08  call    cs:__imp_WppAutoLogTrace
0x140009e0f  nop     dword ptr [rax+rax+00h]
0x140009e14  add     rsp, 58h
0x140009e18  pop     r14
0x140009e1a  pop     r13
0x140009e1c  pop     rdi
0x140009e1d  pop     rsi
0x140009e1e  pop     rbp
0x140009e1f  pop     rbx
0x140009e20  retn
```
