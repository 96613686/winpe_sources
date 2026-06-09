# WPP_RECORDER_AND_TRACE_SF_sDqDld

- ea: `0x14000ec4c`
- end: `0x14000ed9c`
- name: `WPP_RECORDER_AND_TRACE_SF_sDqDld`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022320`

## callees

- `0x140005cf4`
- `0x14000ec4c`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000ed81`
- `WppRecorder!WppAutoLogTrace` at `0x14000ed81`

## string_xrefs

- `0x14000ec67`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDqDld(
        __int16 a1,
        char a2,
        char a3,
        __int64 a4,
        unsigned __int8 a5,
        int a6,
        USHORT a7,
        int a8,
        int a9,
        ...)
{
  int v11; // [rsp+20h] [rbp-98h]
  __int64 v12; // [rsp+90h] [rbp-28h]
  __int64 v13; // [rsp+98h] [rbp-20h]
  __int64 v14; // [rsp+A0h] [rbp-18h]
  __int64 v15; // [rsp+A8h] [rbp-10h]
  __int64 v16; // [rsp+108h] [rbp+50h] BYREF
  va_list va; // [rsp+108h] [rbp+50h]
  __int64 v18; // [rsp+110h] [rbp+58h] BYREF
  va_list va1; // [rsp+110h] [rbp+58h]
  __int64 v20; // [rsp+118h] [rbp+60h] BYREF
  va_list va2; // [rsp+118h] [rbp+60h]
  __int64 v22; // [rsp+120h] [rbp+68h] BYREF
  va_list va3; // [rsp+120h] [rbp+68h]
  va_list va4; // [rsp+128h] [rbp+70h] BYREF

  va_start(va4, a9);
  va_start(va3, a9);
  va_start(va2, a9);
  va_start(va1, a9);
  va_start(va, a9);
  v16 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v18 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v20 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v22 = va_arg(va4, _QWORD);
  if ( a2 )
    FastWppTraceMessage(
      a1,
      a7,
      (ULONGLONG)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      42,
      va,
      4,
      va1,
      8,
      va2,
      4,
      va3,
      4,
      va4,
      4,
      0);
  if ( a3 )
  {
    LOWORD(v11) = a7;
    WppAutoLogTrace(
      a4,
      a5,
      5,
      WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      v11,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      42,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      8,
      (__int64 *)va2,
      4,
      (__int64 *)va3,
      4,
      va4,
      4,
      0,
      v12,
      v13,
      v14,
      v15);
  }
}

```

## disassembly

```asm
0x14000ec4c  mov     r11, rsp
0x14000ec4f  push    rbx
0x14000ec50  push    rbp
0x14000ec51  push    rsi
0x14000ec52  push    rdi
0x14000ec53  push    r12
0x14000ec55  sub     rsp, 90h
0x14000ec5c  movzx   edi, [rsp+0B8h+arg_30]
0x14000ec64  mov     rsi, r9
0x14000ec67  lea     r12, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000ec6e  mov     bl, r8b
0x14000ec71  mov     ebp, 4
0x14000ec76  test    dl, dl
0x14000ec78  jz      short loc_14000ECE1
0x14000ec7a  mov     qword ptr [r11-40h], 0
0x14000ec82  lea     rax, [r11+70h]
0x14000ec86  mov     [r11-48h], rbp
0x14000ec8a  lea     r8, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000ec91  mov     [r11-50h], rax
0x14000ec95  mov     r9, r12
0x14000ec98  mov     [r11-58h], rbp
0x14000ec9c  lea     rax, [r11+68h]
0x14000eca0  mov     [r11-60h], rax
0x14000eca4  mov     edx, edi
0x14000eca6  mov     [r11-68h], rbp
0x14000ecaa  lea     rax, [r11+60h]
0x14000ecae  mov     [r11-70h], rax
0x14000ecb2  lea     rax, [r11+58h]
0x14000ecb6  mov     qword ptr [r11-78h], 8
0x14000ecbe  mov     [r11-80h], rax
0x14000ecc2  lea     rax, [r11+50h]
0x14000ecc6  mov     [rsp+0B8h+var_88], rbp
0x14000eccb  mov     [rsp+0B8h+var_90], rax
0x14000ecd0  movzx   ecx, cx
0x14000ecd3  mov     [rsp+0B8h+var_98], 2Ah ; '*'
0x14000ecdc  call    FastWppTraceMessage
0x14000ece1  test    bl, bl
0x14000ece3  jz      loc_14000ED8D
0x14000ece9  movzx   edx, [rsp+0B8h+arg_20]
0x14000ecf1  lea     rax, [rsp+0B8h+arg_68]
0x14000ecf9  mov     [rsp+0B8h+var_30], 0
0x14000ed05  lea     r9, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000ed0c  mov     [rsp+0B8h+var_38], rbp
0x14000ed14  mov     r8d, 5
0x14000ed1a  mov     [rsp+0B8h+var_40], rax
0x14000ed1f  mov     rcx, rsi
0x14000ed22  mov     [rsp+0B8h+var_48], rbp
0x14000ed27  lea     rax, [rsp+0B8h+arg_60]
0x14000ed2f  mov     [rsp+0B8h+var_50], rax
0x14000ed34  lea     rax, [rsp+0B8h+arg_58]
0x14000ed3c  mov     [rsp+0B8h+var_58], rbp
0x14000ed41  mov     [rsp+0B8h+var_60], rax
0x14000ed46  lea     rax, [rsp+0B8h+arg_50]
0x14000ed4e  mov     [rsp+0B8h+var_68], 8
0x14000ed57  mov     [rsp+0B8h+var_70], rax
0x14000ed5c  lea     rax, [rsp+0B8h+arg_48]
0x14000ed64  mov     [rsp+0B8h+var_78], rbp
0x14000ed69  mov     [rsp+0B8h+var_80], rax
0x14000ed6e  mov     [rsp+0B8h+var_88], 2Ah ; '*'
0x14000ed77  mov     [rsp+0B8h+var_90], r12
0x14000ed7c  mov     word ptr [rsp+0B8h+var_98], di
0x14000ed81  call    cs:__imp_WppAutoLogTrace
0x14000ed88  nop     dword ptr [rax+rax+00h]
0x14000ed8d  add     rsp, 90h
0x14000ed94  pop     r12
0x14000ed96  pop     rdi
0x14000ed97  pop     rsi
0x14000ed98  pop     rbp
0x14000ed99  pop     rbx
0x14000ed9a  retn
```
