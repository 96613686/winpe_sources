# WPP_SF_L

- ea: `0x140001ae0`
- end: `0x140001b27`
- name: `WPP_SF_L`
- size: `71`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `66`
- callee_count: `1`
- tags: ``

## callers

- `0x1400015a0`
- `0x140001bec`
- `0x14000a550`
- `0x14000a810`
- `0x14000a96c`
- `0x14000acd8`
- `0x14000adf0`
- `0x14000afb4`
- `0x14000b150`
- `0x14000b5e8`
- `0x14000bb40`
- `0x14000bcac`
- `0x14000be4c`
- `0x14000c2d4`
- `0x14000c528`
- `0x14000c9f8`
- `0x14000cb00`
- `0x14000cc30`
- `0x14000cd50`
- `0x14000cf1c`
- `0x14000d494`
- `0x14000d9a0`
- `0x14000db54`
- `0x14000e340`
- `0x14000ebe4`
- `0x14000ecbc`
- `0x14000f440`
- `0x14000f518`
- `0x14000f680`
- `0x14000ffc0`
- `0x14001045c`
- `0x140010800`
- `0x140010970`
- `0x140010d00`
- `0x140010e70`
- `0x140010ef0`
- `0x140011500`
- `0x1400119a0`
- `0x140012df0`
- `0x140012e60`
- `0x1400135a0`
- `0x140013a20`
- `0x140013e70`
- `0x1400147a0`
- `0x140014fc0`
- `0x140015d50`
- `0x1400168b0`
- `0x140016dc0`
- `0x140017540`
- `0x140017760`

## callees

- `0x140002db0`

## pseudocode

```c
__int64 __fastcall WPP_SF_L(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, int *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_f966253613f5301e392ffabe30ce75fd_Traceguids,
           a2,
           &v5,
           4,
           0);
}

```

## disassembly

```asm
0x140001ae0  mov     [rsp+arg_18], r9d
0x140001ae5  sub     rsp, 48h
0x140001ae9  mov     rax, cs:pfnWppTraceMessage
0x140001af0  lea     r8, [rsp+48h+arg_18]
0x140001af5  mov     [rsp+48h+var_18], 0
0x140001afe  movzx   r9d, dx
0x140001b02  mov     edx, 2Bh ; '+'
0x140001b07  mov     [rsp+48h+var_20], 4
0x140001b10  mov     [rsp+48h+var_28], r8
0x140001b15  lea     r8, WPP_f966253613f5301e392ffabe30ce75fd_Traceguids
0x140001b1c  call    _guard_dispatch_icall
0x140001b21  add     rsp, 48h
0x140001b25  retn
```
