# WPP_SF_d

- ea: `0x1400159fc`
- end: `0x140015a3a`
- name: `WPP_SF_d`
- size: `62`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int)`
- caller_count: `114`
- callee_count: `1`
- tags: ``

## callers

- `0x140001100`
- `0x140001760`
- `0x1400022c0`
- `0x1400029d0`
- `0x140003510`
- `0x140003bd0`
- `0x140004530`
- `0x140005de0`
- `0x1400070a0`
- `0x1400081f0`
- `0x140008e10`
- `0x140009440`
- `0x1400095b0`
- `0x140009b80`
- `0x140009f60`
- `0x14000adb0`
- `0x14000b900`
- `0x14000baf0`
- `0x14000be20`
- `0x14000c370`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000d4cc`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011298`
- `0x140011984`
- `0x1400124ec`
- `0x140012c40`
- `0x1400132cc`
- `0x140013c20`
- `0x140013dc0`
- `0x140014300`
- `0x140014760`
- `0x1400150f0`
- `0x140015674`
- `0x1400157d8`
- `0x140016b14`
- `0x140016cb8`
- `0x140017628`
- `0x140017770`
- `0x140017d40`
- `0x140018a7c`
- `0x140019044`
- `0x1400196a8`

## callees

- `0x14003abe0`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           0);
}

```

## disassembly

```asm
0x1400159fc  mov     r11, rsp
0x1400159ff  mov     [r11+20h], r9d
0x140015a03  sub     rsp, 48h
0x140015a07  mov     rax, cs:pfnWppTraceMessage
0x140015a0e  lea     r9, [r11+20h]
0x140015a12  mov     qword ptr [r11-18h], 0
0x140015a1a  mov     qword ptr [r11-20h], 4
0x140015a22  mov     [r11-28h], r9
0x140015a26  movzx   r9d, dx
0x140015a2a  mov     edx, 2Bh ; '+'
0x140015a2f  call    _guard_dispatch_icall
0x140015a34  add     rsp, 48h
0x140015a38  retn
```
