# NcaReportReturnError

- ea: `0x1800033bc`
- end: `0x180003433`
- name: `NcaReportReturnError`
- size: `119`
- prototype: `__int64 __fastcall(int, unsigned int, int)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x1800024b0`
- `0x1800026d0`
- `0x180002d50`
- `0x180003240`
- `0x180004400`
- `0x180004680`
- `0x180004cec`
- `0x180018ffc`
- `0x180019178`
- `0x1800193f8`
- `0x180019520`
- `0x180019638`
- `0x180019b04`
- `0x180019c70`
- `0x180019f50`
- `0x18001a00c`
- `0x18001a0fc`
- `0x18001a38c`
- `0x18001a654`
- `0x18001a7c4`
- `0x18001a890`
- `0x18001a95c`
- `0x18001ab04`
- `0x18001ac78`

## callees

- `0x1800033bc`
- `0x180004f04`
- `0x180019e14`

## pseudocode

```c
__int64 __fastcall NcaReportReturnError(int a1, unsigned int a2, int a3)
{
  PVOID *v5; // rcx

  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
      WPP_SF_sD((unsigned int)v5[2], a2, a3, a1, a2);
  }
  return a2;
}

```

## disassembly

```asm
0x1800033bc  mov     [rsp+arg_0], rbx
0x1800033c1  mov     [rsp+arg_8], rsi
0x1800033c6  push    rdi
0x1800033c7  sub     rsp, 30h
0x1800033cb  mov     ebx, edx
0x1800033cd  mov     rdi, rcx
0x1800033d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033d7  lea     rsi, WPP_GLOBAL_Control
0x1800033de  cmp     rcx, rsi
0x1800033e1  jz      short loc_180003420
0x1800033e3  test    byte ptr [rcx+1Ch], 8
0x1800033e7  jz      short loc_180003405
0x1800033e9  mov     rcx, [rcx+10h]
0x1800033ed  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x1800033f4  mov     edx, 32h ; '2'
0x1800033f9  call    WPP_SF_
0x1800033fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180003405  cmp     rcx, rsi
0x180003408  jz      short loc_180003420
0x18000340a  test    byte ptr [rcx+1Ch], 1
0x18000340e  jz      short loc_180003420
0x180003410  mov     rcx, [rcx+10h]
0x180003414  mov     r9, rdi
0x180003417  mov     [rsp+38h+var_18], ebx
0x18000341b  call    WPP_SF_sD
0x180003420  mov     rsi, [rsp+38h+arg_8]
0x180003425  mov     eax, ebx
0x180003427  mov     rbx, [rsp+38h+arg_0]
0x18000342c  add     rsp, 30h
0x180003430  pop     rdi
0x180003431  retn
```
