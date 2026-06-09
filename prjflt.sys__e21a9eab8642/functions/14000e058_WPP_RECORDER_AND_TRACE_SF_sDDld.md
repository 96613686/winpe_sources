# WPP_RECORDER_AND_TRACE_SF_sDDld

- ea: `0x14000e058`
- end: `0x14000e181`
- name: `WPP_RECORDER_AND_TRACE_SF_sDDld`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022320`

## callees

- `0x140005cf4`
- `0x14000e058`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000e165`
- `WppRecorder!WppAutoLogTrace` at `0x14000e165`

## string_xrefs

- `0x14000e076`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDDld(
        __int64 a1,
        char a2,
        char a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
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
  LODWORD(v13[0]) = 1676;
  if ( a2 )
    FastWppTraceMessage(
      517,
      0x26u,
      (ULONGLONG)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      42,
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
    LOWORD(v12) = 38;
    WppAutoLogTrace(
      a4,
      2,
      5,
      WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
      v12,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
      42,
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
0x14000e058  mov     r11, rsp
0x14000e05b  push    rbx
0x14000e05c  push    rsi
0x14000e05d  push    rdi
0x14000e05e  push    r14
0x14000e060  push    r15
0x14000e062  sub     rsp, 90h
0x14000e069  mov     dword ptr [r11-38h], 68Ch
0x14000e071  mov     esi, 4
0x14000e076  lea     r15, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000e07d  mov     rdi, r9
0x14000e080  mov     bl, r8b
0x14000e083  lea     r14d, [rsi+22h]
0x14000e087  test    dl, dl
0x14000e089  jz      short loc_14000E0E5
0x14000e08b  mov     qword ptr [r11-50h], 0
0x14000e093  lea     rax, [r11+68h]
0x14000e097  mov     [r11-58h], rsi
0x14000e09b  lea     r8, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e0a2  mov     [r11-60h], rax
0x14000e0a6  mov     ecx, 205h
0x14000e0ab  mov     [r11-68h], rsi
0x14000e0af  lea     rax, [r11+60h]
0x14000e0b3  mov     [r11-70h], rax
0x14000e0b7  mov     r9, r15
0x14000e0ba  mov     [r11-78h], rsi
0x14000e0be  lea     rax, [r11+58h]
0x14000e0c2  mov     [r11-80h], rax
0x14000e0c6  mov     edx, r14d
0x14000e0c9  lea     rax, [r11-38h]
0x14000e0cd  mov     [rsp+0B8h+var_88], rsi
0x14000e0d2  mov     [rsp+0B8h+var_90], rax
0x14000e0d7  mov     [rsp+0B8h+var_98], 2Ah ; '*'
0x14000e0e0  call    FastWppTraceMessage
0x14000e0e5  test    bl, bl
0x14000e0e7  jz      loc_14000E171
0x14000e0ed  mov     [rsp+0B8h+var_40], 0
0x14000e0f6  lea     rax, [rsp+0B8h+arg_60]
0x14000e0fe  mov     [rsp+0B8h+var_48], rsi
0x14000e103  lea     r9, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x14000e10a  mov     [rsp+0B8h+var_50], rax
0x14000e10f  mov     edx, 2
0x14000e114  mov     [rsp+0B8h+var_58], rsi
0x14000e119  lea     rax, [rsp+0B8h+arg_58]
0x14000e121  mov     [rsp+0B8h+var_60], rax
0x14000e126  mov     rcx, rdi
0x14000e129  mov     [rsp+0B8h+var_68], rsi
0x14000e12e  lea     rax, [rsp+0B8h+arg_50]
0x14000e136  mov     [rsp+0B8h+var_70], rax
0x14000e13b  lea     r8d, [rdx+3]
0x14000e13f  mov     [rsp+0B8h+var_78], rsi
0x14000e144  lea     rax, [rsp+0B8h+var_38]
0x14000e14c  mov     [rsp+0B8h+var_80], rax
0x14000e151  mov     [rsp+0B8h+var_88], 2Ah ; '*'
0x14000e15a  mov     [rsp+0B8h+var_90], r15
0x14000e15f  mov     word ptr [rsp+0B8h+var_98], r14w
0x14000e165  call    cs:__imp_WppAutoLogTrace
0x14000e16c  nop     dword ptr [rax+rax+00h]
0x14000e171  add     rsp, 90h
0x14000e178  pop     r15
0x14000e17a  pop     r14
0x14000e17c  pop     rdi
0x14000e17d  pop     rsi
0x14000e17e  pop     rbx
0x14000e17f  retn
```
