# NcaReportErrorAsWinError

- ea: `0x1800199b4`
- end: `0x180019a34`
- name: `NcaReportErrorAsWinError`
- size: `128`
- prototype: `__int64 __fastcall(int, __int64, int)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x1800024b0`
- `0x1800026d0`
- `0x180002d50`
- `0x180003240`
- `0x180018ffc`
- `0x180019178`
- `0x1800193f8`
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

- `0x180004f04`
- `0x1800199b4`
- `0x180019e98`

## pseudocode

```c
__int64 __fastcall NcaReportErrorAsWinError(int a1, __int64 a2, int a3)
{
  int v3; // ebx
  PVOID *v6; // rcx

  v3 = a3;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
      WPP_SF_ssL((unsigned int)v6[2], a2, a3, a1, a2, v3);
  }
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800199b4  push    rbx
0x1800199b6  push    rbp
0x1800199b7  push    rsi
0x1800199b8  push    rdi
0x1800199b9  sub     rsp, 38h
0x1800199bd  mov     ebx, r8d
0x1800199c0  mov     rdi, rdx
0x1800199c3  mov     rsi, rcx
0x1800199c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199cd  lea     rbp, WPP_GLOBAL_Control
0x1800199d4  cmp     rcx, rbp
0x1800199d7  jz      short loc_180019A1B
0x1800199d9  test    byte ptr [rcx+1Ch], 8
0x1800199dd  jz      short loc_1800199FB
0x1800199df  mov     rcx, [rcx+10h]
0x1800199e3  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x1800199ea  mov     edx, 36h ; '6'
0x1800199ef  call    WPP_SF_
0x1800199f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199fb  cmp     rcx, rbp
0x1800199fe  jz      short loc_180019A1B
0x180019a00  test    byte ptr [rcx+1Ch], 1
0x180019a04  jz      short loc_180019A1B
0x180019a06  mov     rcx, [rcx+10h]
0x180019a0a  mov     r9, rsi
0x180019a0d  mov     [rsp+58h+var_30], ebx
0x180019a11  mov     [rsp+58h+var_38], rdi
0x180019a16  call    WPP_SF_ssL
0x180019a1b  test    ebx, ebx
0x180019a1d  jle     short loc_180019A28
0x180019a1f  movzx   ebx, bx
0x180019a22  or      ebx, 80070000h
0x180019a28  mov     eax, ebx
0x180019a2a  add     rsp, 38h
0x180019a2e  pop     rdi
0x180019a2f  pop     rsi
0x180019a30  pop     rbp
0x180019a31  pop     rbx
0x180019a32  retn
```
