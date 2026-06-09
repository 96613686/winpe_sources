# WPP_RECORDER_SF_qqsd

- ea: `0x140004130`
- end: `0x1400042c0`
- name: `WPP_RECORDER_SF_qqsd`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003b20`

## callees

- `0x140004130`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400042a6`
- `WppRecorder!WppAutoLogTrace` at `0x1400042a6`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqsd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  __int64 v5; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  bool v9; // zf
  __int64 v10; // rdx
  const char *v11; // rcx
  int v13; // [rsp+20h] [rbp-88h]
  __int64 v14; // [rsp+D8h] [rbp+30h] BYREF
  va_list va; // [rsp+D8h] [rbp+30h]
  __int64 v16; // [rsp+E0h] [rbp+38h] BYREF
  va_list va1; // [rsp+E0h] [rbp+38h]
  const char *v18; // [rsp+E8h] [rbp+40h]
  va_list va2; // [rsp+F0h] [rbp+48h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v14 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v16 = va_arg(va2, _QWORD);
  v18 = va_arg(va2, const char *);
  v5 = (__int64)v18;
  v7 = -1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    if ( v18 )
    {
      v8 = -1;
      do
        v9 = v18[++v8] == 0;
      while ( !v9 );
      v10 = v8 + 1;
    }
    else
    {
      v10 = 5;
    }
    v11 = v18;
    if ( !v18 )
      v11 = "NULL";
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids,
      22,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      v11,
      v10,
      va2,
      4,
      0);
  }
  if ( v5 )
  {
    do
      v9 = *(_BYTE *)(v5 + v7++ + 1) == 0;
    while ( !v9 );
  }
  LOWORD(v13) = 22;
  return WppAutoLogTrace(a1, 4, 4, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids, v13, (__int64 *)va);
}

```

## disassembly

```asm
0x140004130  push    rbx
0x140004132  push    rbp
0x140004133  push    rsi
0x140004134  push    rdi
0x140004135  push    r12
0x140004137  push    r15
0x140004139  sub     rsp, 78h
0x14000413d  mov     rdx, cs:WPP_GLOBAL_Control
0x140004144  lea     r15, aNull; "NULL"
0x14000414b  mov     rdi, [rsp+0A8h+arg_38]
0x140004153  mov     rbp, rcx
0x140004156  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14000415d  mov     esi, 5
0x140004162  mov     r12d, 16h
0x140004168  mov     eax, [rdx+2Ch]
0x14000416b  test    al, 8
0x14000416d  jz      loc_14000421E
0x140004173  cmp     byte ptr [rdx+29h], 4
0x140004177  jb      loc_14000421E
0x14000417d  test    rdi, rdi
0x140004180  jz      short loc_140004196
0x140004182  mov     rax, rbx
0x140004185  cmp     byte ptr [rdi+rax+1], 0
0x14000418a  lea     rax, [rax+1]
0x14000418e  jnz     short loc_140004185
0x140004190  lea     rdx, [rax+1]
0x140004194  jmp     short loc_140004199
0x140004196  mov     rdx, rsi
0x140004199  mov     rax, cs:pfnWppTraceMessage
0x1400041a0  lea     r8, [rsp+0A8h+arg_40]
0x1400041a8  mov     [rsp+0A8h+var_48], 0
0x1400041b1  test    rdi, rdi
0x1400041b4  mov     [rsp+0A8h+var_50], 4
0x1400041bd  mov     rcx, rdi
0x1400041c0  mov     [rsp+0A8h+var_58], r8
0x1400041c5  cmovz   rcx, r15
0x1400041c9  mov     [rsp+0A8h+var_60], rdx
0x1400041ce  lea     r8, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x1400041d5  mov     [rsp+0A8h+var_68], rcx
0x1400041da  mov     r9d, r12d
0x1400041dd  mov     [rsp+0A8h+var_70], 8
0x1400041e6  lea     rcx, [rsp+0A8h+arg_30]
0x1400041ee  mov     [rsp+0A8h+var_78], rcx
0x1400041f3  mov     edx, 2Bh ; '+'
0x1400041f8  lea     rcx, [rsp+0A8h+arg_28]
0x140004200  mov     [rsp+0A8h+var_80], 8
0x140004209  mov     [rsp+0A8h+var_88], rcx
0x14000420e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004215  mov     rcx, [rcx+18h]
0x140004219  call    _guard_dispatch_icall
0x14000421e  test    rdi, rdi
0x140004221  jz      short loc_140004235
0x140004223  cmp     byte ptr [rdi+rbx+1], 0
0x140004228  lea     rbx, [rbx+1]
0x14000422c  jnz     short loc_140004223
0x14000422e  lea     rsi, [rbx+1]
0x140004232  test    rdi, rdi
0x140004235  mov     [rsp+0A8h+var_40], 0
0x14000423e  lea     rax, [rsp+0A8h+arg_40]
0x140004246  mov     [rsp+0A8h+var_48], 4
0x14000424f  lea     r9, WPP_6ab2d906fdee3c84bc9e6e4168830b21_Traceguids
0x140004256  mov     [rsp+0A8h+var_50], rax
0x14000425b  cmovz   rdi, r15
0x14000425f  mov     [rsp+0A8h+var_58], rsi
0x140004264  lea     rax, [rsp+0A8h+arg_30]
0x14000426c  mov     [rsp+0A8h+var_60], rdi
0x140004271  mov     edx, 4
0x140004276  mov     [rsp+0A8h+var_68], 8
0x14000427f  mov     r8d, edx
0x140004282  mov     [rsp+0A8h+var_70], rax
0x140004287  mov     rcx, rbp
0x14000428a  lea     rax, [rsp+0A8h+arg_28]
0x140004292  mov     [rsp+0A8h+var_78], 8
0x14000429b  mov     [rsp+0A8h+var_80], rax
0x1400042a0  mov     word ptr [rsp+0A8h+var_88], r12w
0x1400042a6  call    cs:__imp_WppAutoLogTrace
0x1400042ad  nop     dword ptr [rax+rax+00h]
0x1400042b2  add     rsp, 78h
0x1400042b6  pop     r15
0x1400042b8  pop     r12
0x1400042ba  pop     rdi
0x1400042bb  pop     rsi
0x1400042bc  pop     rbp
0x1400042bd  pop     rbx
0x1400042be  retn
```
