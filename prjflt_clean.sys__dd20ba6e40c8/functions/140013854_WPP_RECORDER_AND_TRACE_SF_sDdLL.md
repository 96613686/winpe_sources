# WPP_RECORDER_AND_TRACE_SF_sDdLL

- ea: `0x140013854`
- end: `0x14001397d`
- name: `WPP_RECORDER_AND_TRACE_SF_sDdLL`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400459d8`

## callees

- `0x140005cf4`
- `0x140013854`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140013961`
- `WppRecorder!WppAutoLogTrace` at `0x140013961`

## pseudocode

```c
void WPP_RECORDER_AND_TRACE_SF_sDdLL(
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
  LODWORD(v13[0]) = 441;
  if ( a2 )
    FastWppTraceMessage(
      532,
      0x15u,
      (ULONGLONG)&WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
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
    LOWORD(v12) = 21;
    WppAutoLogTrace(
      a4,
      2,
      20,
      &WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids,
      v12,
      "onecore\\base\\fs\\gvflt\\filter\\sys\\mapping.c",
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
0x140013854  mov     r11, rsp
0x140013857  push    rbx
0x140013858  push    rsi
0x140013859  push    rdi
0x14001385a  push    r14
0x14001385c  push    r15
0x14001385e  sub     rsp, 90h
0x140013865  mov     dword ptr [r11-38h], 1B9h
0x14001386d  mov     esi, 4
0x140013872  lea     r15, aOnecoreBaseFsG_11; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140013879  mov     rdi, r9
0x14001387c  mov     bl, r8b
0x14001387f  lea     r14d, [rsi+11h]
0x140013883  test    dl, dl
0x140013885  jz      short loc_1400138E1
0x140013887  mov     qword ptr [r11-50h], 0
0x14001388f  lea     rax, [r11+68h]
0x140013893  mov     [r11-58h], rsi
0x140013897  lea     r8, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x14001389e  mov     [r11-60h], rax
0x1400138a2  mov     ecx, 214h
0x1400138a7  mov     [r11-68h], rsi
0x1400138ab  lea     rax, [r11+60h]
0x1400138af  mov     [r11-70h], rax
0x1400138b3  mov     r9, r15
0x1400138b6  mov     [r11-78h], rsi
0x1400138ba  lea     rax, [r11+58h]
0x1400138be  mov     [r11-80h], rax
0x1400138c2  mov     edx, r14d
0x1400138c5  lea     rax, [r11-38h]
0x1400138c9  mov     [rsp+0B8h+var_88], rsi
0x1400138ce  mov     [rsp+0B8h+var_90], rax
0x1400138d3  mov     [rsp+0B8h+var_98], 2Bh ; '+'
0x1400138dc  call    FastWppTraceMessage
0x1400138e1  test    bl, bl
0x1400138e3  jz      loc_14001396D
0x1400138e9  mov     [rsp+0B8h+var_40], 0
0x1400138f2  lea     rax, [rsp+0B8h+arg_60]
0x1400138fa  mov     [rsp+0B8h+var_48], rsi
0x1400138ff  lea     r9, WPP_5c05f7cae5513ff3734adbc0d3bd9537_Traceguids
0x140013906  mov     [rsp+0B8h+var_50], rax
0x14001390b  mov     edx, 2
0x140013910  mov     [rsp+0B8h+var_58], rsi
0x140013915  lea     rax, [rsp+0B8h+arg_58]
0x14001391d  mov     [rsp+0B8h+var_60], rax
0x140013922  mov     rcx, rdi
0x140013925  mov     [rsp+0B8h+var_68], rsi
0x14001392a  lea     rax, [rsp+0B8h+arg_50]
0x140013932  mov     [rsp+0B8h+var_70], rax
0x140013937  lea     r8d, [rdx+12h]
0x14001393b  mov     [rsp+0B8h+var_78], rsi
0x140013940  lea     rax, [rsp+0B8h+var_38]
0x140013948  mov     [rsp+0B8h+var_80], rax
0x14001394d  mov     [rsp+0B8h+var_88], 2Bh ; '+'
0x140013956  mov     [rsp+0B8h+var_90], r15
0x14001395b  mov     word ptr [rsp+0B8h+var_98], r14w
0x140013961  call    cs:__imp_WppAutoLogTrace
0x140013968  nop     dword ptr [rax+rax+00h]
0x14001396d  add     rsp, 90h
0x140013974  pop     r15
0x140013976  pop     r14
0x140013978  pop     rdi
0x140013979  pop     rsi
0x14001397a  pop     rbx
0x14001397b  retn
```
