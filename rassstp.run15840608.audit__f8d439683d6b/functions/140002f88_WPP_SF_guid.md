# WPP_SF__guid_

- ea: `0x140002f88`
- end: `0x140002fbe`
- name: `WPP_SF__guid_`
- size: `54`
- prototype: ``
- caller_count: `34`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x1400018b0`
- `0x1400042e0`
- `0x140010988`
- `0x140010c58`
- `0x140010fd4`
- `0x140011500`
- `0x140011b00`
- `0x140012290`
- `0x140013150`
- `0x1400133f0`
- `0x140013ad0`
- `0x1400144c4`
- `0x140014ef0`
- `0x1400150e0`
- `0x1400154e0`
- `0x1400155b0`
- `0x1400161b0`
- `0x140016414`
- `0x1400165a0`
- `0x140016734`
- `0x1400168d0`
- `0x1400169a4`
- `0x140016cf0`
- `0x140016e84`
- `0x140016f4c`
- `0x14001707c`
- `0x140017204`
- `0x140017388`
- `0x140017550`
- `0x140018c70`
- `0x140019040`
- `0x140019860`
- `0x140019ae0`

## callees

- `0x140005ef0`

## pseudocode

```c
__int64 __fastcall WPP_SF__guid_(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4)
{
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           16,
           0);
}

```

## disassembly

```asm
0x140002f88  sub     rsp, 48h
0x140002f8c  mov     rax, cs:pfnWppTraceMessage
0x140002f93  mov     [rsp+48h+var_18], 0
0x140002f9c  mov     [rsp+48h+var_20], 10h
0x140002fa5  mov     [rsp+48h+var_28], r9
0x140002faa  movzx   r9d, dx
0x140002fae  mov     edx, 2Bh ; '+'
0x140002fb3  call    _guard_dispatch_icall
0x140002fb8  add     rsp, 48h
0x140002fbc  retn
```
