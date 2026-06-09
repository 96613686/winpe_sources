# WPP_RECORDER_SF_qqsd

- ea: `0x140002e68`
- end: `0x140002fe5`
- name: `WPP_RECORDER_SF_qqsd`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002050`

## callees

- `0x140002e68`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002fc9`
- `WppRecorder!WppAutoLogTrace` at `0x140002fc9`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqsd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v8; // rax
  __int64 v9; // rdx
  const char *v10; // rcx
  int v12; // [rsp+20h] [rbp-88h]
  __int64 v13; // [rsp+D8h] [rbp+30h] BYREF
  va_list va; // [rsp+D8h] [rbp+30h]
  __int64 v15; // [rsp+E0h] [rbp+38h] BYREF
  va_list va1; // [rsp+E0h] [rbp+38h]
  const char *v17; // [rsp+E8h] [rbp+40h]
  va_list va2; // [rsp+F0h] [rbp+48h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  v17 = va_arg(va2, const char *);
  v5 = (__int64)v17;
  v6 = -1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    if ( v17 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v17[v8] );
      v9 = v8 + 1;
    }
    else
    {
      v9 = 5;
    }
    v10 = v17;
    if ( !v17 )
      v10 = "NULL";
    pfnWppTraceMessage(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids,
      30,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      v10,
      v9,
      va2,
      4,
      0);
  }
  if ( v5 )
  {
    do
      ++v6;
    while ( *(_BYTE *)(v5 + v6) );
  }
  LOWORD(v12) = 30;
  return WppAutoLogTrace(a1, 4, 4, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x140002e68  push    rbx
0x140002e6a  push    rbp
0x140002e6b  push    rsi
0x140002e6c  push    rdi
0x140002e6d  push    r12
0x140002e6f  push    r13
0x140002e71  push    r15
0x140002e73  sub     rsp, 70h
0x140002e77  mov     rdx, cs:WPP_GLOBAL_Control
0x140002e7e  lea     r13, aNull; "NULL"
0x140002e85  mov     rbx, [rsp+0A8h+arg_38]
0x140002e8d  mov     r15d, 4
0x140002e93  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140002e97  mov     rbp, rcx
0x140002e9a  mov     eax, [rdx+2Ch]
0x140002e9d  lea     r12d, [r15+4]
0x140002ea1  lea     esi, [rdi+6]
0x140002ea4  lea     r9d, [r15+1Ah]
0x140002ea8  test    r12b, al
0x140002eab  jz      loc_140002F51
0x140002eb1  cmp     [rdx+29h], r15b
0x140002eb5  jb      loc_140002F51
0x140002ebb  test    rbx, rbx
0x140002ebe  jz      short loc_140002ED2
0x140002ec0  mov     rax, rdi
0x140002ec3  inc     rax
0x140002ec6  cmp     byte ptr [rbx+rax], 0
0x140002eca  jnz     short loc_140002EC3
0x140002ecc  lea     rdx, [rax+1]
0x140002ed0  jmp     short loc_140002ED5
0x140002ed2  mov     rdx, rsi
0x140002ed5  mov     rax, cs:pfnWppTraceMessage
0x140002edc  lea     r8, [rsp+0A8h+arg_40]
0x140002ee4  mov     [rsp+0A8h+var_48], 0
0x140002eed  test    rbx, rbx
0x140002ef0  mov     [rsp+0A8h+var_50], r15
0x140002ef5  mov     rcx, rbx
0x140002ef8  mov     [rsp+0A8h+var_58], r8
0x140002efd  cmovz   rcx, r13
0x140002f01  mov     [rsp+0A8h+var_60], rdx
0x140002f06  lea     r8, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002f0d  mov     [rsp+0A8h+var_68], rcx
0x140002f12  mov     edx, 2Bh ; '+'
0x140002f17  mov     [rsp+0A8h+var_70], r12
0x140002f1c  lea     rcx, [rsp+0A8h+arg_30]
0x140002f24  mov     [rsp+0A8h+var_78], rcx
0x140002f29  lea     rcx, [rsp+0A8h+arg_28]
0x140002f31  mov     [rsp+0A8h+var_80], r12
0x140002f36  mov     [rsp+0A8h+var_88], rcx
0x140002f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f42  mov     rcx, [rcx+18h]
0x140002f46  call    _guard_dispatch_icall
0x140002f4b  mov     r9d, 1Eh
0x140002f51  test    rbx, rbx
0x140002f54  jz      short loc_140002F66
0x140002f56  inc     rdi
0x140002f59  cmp     byte ptr [rbx+rdi], 0
0x140002f5d  jnz     short loc_140002F56
0x140002f5f  lea     rsi, [rdi+1]
0x140002f63  test    rbx, rbx
0x140002f66  mov     [rsp+0A8h+var_40], 0
0x140002f6f  lea     rax, [rsp+0A8h+arg_40]
0x140002f77  mov     [rsp+0A8h+var_48], r15
0x140002f7c  cmovz   rbx, r13
0x140002f80  mov     [rsp+0A8h+var_50], rax
0x140002f85  mov     r8d, r15d
0x140002f88  mov     [rsp+0A8h+var_58], rsi
0x140002f8d  lea     rax, [rsp+0A8h+arg_30]
0x140002f95  mov     [rsp+0A8h+var_60], rbx
0x140002f9a  mov     edx, r15d
0x140002f9d  mov     [rsp+0A8h+var_68], r12
0x140002fa2  mov     rcx, rbp
0x140002fa5  mov     [rsp+0A8h+var_70], rax
0x140002faa  lea     rax, [rsp+0A8h+arg_28]
0x140002fb2  mov     [rsp+0A8h+var_78], r12
0x140002fb7  mov     [rsp+0A8h+var_80], rax
0x140002fbc  mov     word ptr [rsp+0A8h+var_88], r9w
0x140002fc2  lea     r9, WPP_da562ded6bb73c5031c86e6f6181bb7a_Traceguids
0x140002fc9  call    cs:__imp_WppAutoLogTrace
0x140002fd0  nop     dword ptr [rax+rax+00h]
0x140002fd5  add     rsp, 70h
0x140002fd9  pop     r15
0x140002fdb  pop     r13
0x140002fdd  pop     r12
0x140002fdf  pop     rdi
0x140002fe0  pop     rsi
0x140002fe1  pop     rbp
0x140002fe2  pop     rbx
0x140002fe3  retn
```
