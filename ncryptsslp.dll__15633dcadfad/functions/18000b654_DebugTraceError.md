# DebugTraceError

- ea: `0x18000b654`
- end: `0x18000b692`
- name: `DebugTraceError`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `119`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001690`
- `0x180001930`
- `0x180001acc`
- `0x180001de8`
- `0x1800022a0`
- `0x180002510`
- `0x1800029e0`
- `0x180003050`
- `0x1800037a0`
- `0x180003f10`
- `0x180004570`
- `0x180005240`
- `0x1800058e0`
- `0x180005cb0`
- `0x180005ec0`
- `0x180006070`
- `0x180006904`
- `0x180006b60`
- `0x180007990`
- `0x180007de4`
- `0x1800081a8`
- `0x18000860c`
- `0x180008810`
- `0x180008b80`
- `0x1800091e0`
- `0x1800097f0`
- `0x180009ca0`
- `0x180009fb0`
- `0x18000a120`
- `0x18000a960`
- `0x18000ae00`
- `0x18000b360`
- `0x18000b6a0`
- `0x18000bb90`
- `0x18000be50`
- `0x18000c1c0`
- `0x18000cc40`
- `0x18000cfb0`
- `0x18000d2b0`
- `0x18000d6cc`
- `0x18000d9f0`
- `0x18000da9c`
- `0x18000dea0`
- `0x18000e320`
- `0x18000ec00`
- `0x18000eea0`
- `0x18000f2d0`
- `0x18000fc08`
- `0x1800100a0`

## callees

- `0x18000b594`
- `0x18000b654`

## pseudocode

```c
__int64 __fastcall DebugTraceError(unsigned int a1, int a2, __int64 a3, char a4)
{
  __int64 result; // rax

  result = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return WPP_SF_sDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, a1, a3, a4);
  return result;
}

```

## disassembly

```asm
0x18000b654  sub     rsp, 48h
0x18000b658  mov     eax, ecx
0x18000b65a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b661  lea     r10, WPP_GLOBAL_Control
0x18000b668  cmp     rcx, r10
0x18000b66b  jz      short loc_18000B68D
0x18000b66d  test    byte ptr [rcx+1Ch], 1
0x18000b671  jz      short loc_18000B68D
0x18000b673  mov     rcx, [rcx+10h]
0x18000b677  mov     [rsp+48h+var_18], r9d
0x18000b67c  mov     r9, rdx
0x18000b67f  mov     [rsp+48h+var_20], r8
0x18000b684  mov     [rsp+48h+var_28], eax
0x18000b688  call    WPP_SF_sDsd
0x18000b68d  add     rsp, 48h
0x18000b691  retn
```
