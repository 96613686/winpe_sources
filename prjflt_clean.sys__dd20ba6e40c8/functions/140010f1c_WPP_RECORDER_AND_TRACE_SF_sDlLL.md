# WPP_RECORDER_AND_TRACE_SF_sDlLL

- ea: `0x140010f1c`
- end: `0x140011045`
- name: `WPP_RECORDER_AND_TRACE_SF_sDlLL`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000420c`

## callees

- `0x140005cf4`
- `0x140010f1c`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140011029`
- `WppRecorder!WppAutoLogTrace` at `0x140011029`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDlLL(
        _DWORD a1,
        char a2,
        char a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        ...)
{
  int v12; // [rsp+20h] [rbp-98h]
  _QWORD v13[7]; // [rsp+80h] [rbp-38h] BYREF
  __int64 v14; // [rsp+110h] [rbp+58h] BYREF
  va_list va; // [rsp+110h] [rbp+58h]
  __int64 v16; // [rsp+118h] [rbp+60h] BYREF
  va_list va1; // [rsp+118h] [rbp+60h]
  va_list va2; // [rsp+120h] [rbp+68h] BYREF

  va_start(va2, a10);
  va_start(va1, a10);
  va_start(va, a10);
  v14 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v16 = va_arg(va2, _QWORD);
  LODWORD(v13[0]) = 1871;
  if ( a2 )
    FastWppTraceMessage(
      526,
      0x46u,
      (ULONGLONG)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      43,
      v13,
      4,
      va,
      4,
      va1,
      4,
      va2,
      4,
      0);
  if ( a3 )
  {
    LOWORD(v12) = 70;
    WppAutoLogTrace(
      a4,
      2,
      14,
      &WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      v12,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      43,
      v13,
      4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      4,
      va2,
      4,
      0,
      v13[0],
      v13[1],
      v13[2],
      v13[3],
      v13[4],
      v13[5]);
  }
}

```

## disassembly

```asm
0x140010f1c  mov     r11, rsp
0x140010f1f  push    rbx
0x140010f20  push    rsi
0x140010f21  push    rdi
0x140010f22  push    r14
0x140010f24  push    r15
0x140010f26  sub     rsp, 90h
0x140010f2d  mov     dword ptr [r11-38h], 74Fh
0x140010f35  mov     esi, 4
0x140010f3a  lea     r15, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140010f41  mov     rdi, r9
0x140010f44  mov     bl, r8b
0x140010f47  lea     r14d, [rsi+42h]
0x140010f4b  test    dl, dl
0x140010f4d  jz      short loc_140010FA9
0x140010f4f  mov     qword ptr [r11-50h], 0
0x140010f57  lea     rax, [r11+68h]
0x140010f5b  mov     [r11-58h], rsi
0x140010f5f  lea     r8, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140010f66  mov     [r11-60h], rax
0x140010f6a  mov     ecx, 20Eh
0x140010f6f  mov     [r11-68h], rsi
0x140010f73  lea     rax, [r11+60h]
0x140010f77  mov     [r11-70h], rax
0x140010f7b  mov     r9, r15
0x140010f7e  mov     [r11-78h], rsi
0x140010f82  lea     rax, [r11+58h]
0x140010f86  mov     [r11-80h], rax
0x140010f8a  mov     edx, r14d
0x140010f8d  lea     rax, [r11-38h]
0x140010f91  mov     [rsp+0B8h+var_88], rsi
0x140010f96  mov     [rsp+0B8h+var_90], rax
0x140010f9b  mov     [rsp+0B8h+var_98], 2Bh ; '+'
0x140010fa4  call    FastWppTraceMessage
0x140010fa9  test    bl, bl
0x140010fab  jz      loc_140011035
0x140010fb1  mov     [rsp+0B8h+var_40], 0
0x140010fba  lea     rax, [rsp+0B8h+arg_60]
0x140010fc2  mov     [rsp+0B8h+var_48], rsi
0x140010fc7  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140010fce  mov     [rsp+0B8h+var_50], rax
0x140010fd3  mov     edx, 2
0x140010fd8  mov     [rsp+0B8h+var_58], rsi
0x140010fdd  lea     rax, [rsp+0B8h+arg_58]
0x140010fe5  mov     [rsp+0B8h+var_60], rax
0x140010fea  mov     rcx, rdi
0x140010fed  mov     [rsp+0B8h+var_68], rsi
0x140010ff2  lea     rax, [rsp+0B8h+arg_50]
0x140010ffa  mov     [rsp+0B8h+var_70], rax
0x140010fff  lea     r8d, [rdx+0Ch]
0x140011003  mov     [rsp+0B8h+var_78], rsi
0x140011008  lea     rax, [rsp+0B8h+var_38]
0x140011010  mov     [rsp+0B8h+var_80], rax
0x140011015  mov     [rsp+0B8h+var_88], 2Bh ; '+'
0x14001101e  mov     [rsp+0B8h+var_90], r15
0x140011023  mov     word ptr [rsp+0B8h+var_98], r14w
0x140011029  call    cs:__imp_WppAutoLogTrace
0x140011030  nop     dword ptr [rax+rax+00h]
0x140011035  add     rsp, 90h
0x14001103c  pop     r15
0x14001103e  pop     r14
0x140011040  pop     rdi
0x140011041  pop     rsi
0x140011042  pop     rbx
0x140011043  retn
```
