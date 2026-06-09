# RasFreeEapMethodInfo

- ea: `0x180008094`
- end: `0x18000814b`
- name: `RasFreeEapMethodInfo`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180008094`
- `0x180008154`

## callees

- `0x180008000`
- `0x180008094`
- `0x180008518`

## pseudocode

```c
ULONG __fastcall RasFreeEapMethodInfo(__int64 a1)
{
  _UNKNOWN **v2; // rcx
  ULONG result; // eax
  BYTE *v4; // rcx
  BYTE *v5; // rcx

  v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xEu, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v4 = *(BYTE **)(a1 + 16);
    if ( v4 )
      RasFreeEapMemory(v4);
    v5 = *(BYTE **)(a1 + 24);
    if ( v5 )
      RasFreeEapMemory(v5);
    if ( *(_QWORD *)(a1 + 40) )
      RasFreeEapMethodInfo();
    result = RasFreeEapMemory((BYTE *)a1);
    v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    return WPP_SF_((TRACEHANDLE)v2[2], 0xFu, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180008094  mov     [rsp+arg_0], rbx
0x180008099  push    rdi
0x18000809a  sub     rsp, 20h
0x18000809e  mov     rbx, rcx
0x1800080a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080a8  lea     rdi, WPP_GLOBAL_Control
0x1800080af  cmp     rcx, rdi
0x1800080b2  jz      short loc_1800080DC
0x1800080b4  test    byte ptr [rcx+1Ch], 2
0x1800080b8  jz      short loc_1800080DC
0x1800080ba  cmp     byte ptr [rcx+19h], 6
0x1800080be  jb      short loc_1800080DC
0x1800080c0  mov     rcx, [rcx+10h]
0x1800080c4  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x1800080cb  mov     edx, 0Eh
0x1800080d0  call    WPP_SF_
0x1800080d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080dc  test    rbx, rbx
0x1800080df  jz      short loc_18000811A
0x1800080e1  mov     rcx, [rbx+10h]; pData
0x1800080e5  test    rcx, rcx
0x1800080e8  jz      short loc_1800080EF
0x1800080ea  call    RasFreeEapMemory
0x1800080ef  mov     rcx, [rbx+18h]; pData
0x1800080f3  test    rcx, rcx
0x1800080f6  jz      short loc_1800080FD
0x1800080f8  call    RasFreeEapMemory
0x1800080fd  mov     rcx, [rbx+28h]
0x180008101  test    rcx, rcx
0x180008104  jz      short loc_18000810B
0x180008106  call    RasFreeEapMethodInfo
0x18000810b  mov     rcx, rbx; pData
0x18000810e  call    RasFreeEapMemory
0x180008113  mov     rcx, cs:WPP_GLOBAL_Control
0x18000811a  cmp     rcx, rdi
0x18000811d  jz      short loc_180008140
0x18000811f  test    byte ptr [rcx+1Ch], 2
0x180008123  jz      short loc_180008140
0x180008125  cmp     byte ptr [rcx+19h], 6
0x180008129  jb      short loc_180008140
0x18000812b  mov     rcx, [rcx+10h]
0x18000812f  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids
0x180008136  mov     edx, 0Fh
0x18000813b  call    WPP_SF_
0x180008140  mov     rbx, [rsp+28h+arg_0]
0x180008145  add     rsp, 20h
0x180008149  pop     rdi
0x18000814a  retn
```
