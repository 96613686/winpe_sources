# ResumePrinting

- ea: `0x1800063b4`
- end: `0x1800064dc`
- name: `ResumePrinting`
- size: `296`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007354`

## callees

- `0x180002e7c`
- `0x180003d4c`
- `0x1800063b4`

## import_xrefs

- `WINSPOOL!OpenPrinterA` at `0x180006432`
- `WINSPOOL!OpenPrinterA` at `0x180006432`
- `WINSPOOL!SetPrinterA` at `0x180006467`
- `WINSPOOL!SetPrinterA` at `0x180006467`

## pseudocode

```c
__int64 __fastcall ResumePrinting(__int64 a1)
{
  _BYTE *v2; // rcx
  __int64 v3; // rdx
  HANDLE v4; // rcx
  __int64 result; // rax
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF
  HANDLE phPrinter; // [rsp+40h] [rbp+8h] BYREF

  phPrinter = 0;
  v6 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !*(_QWORD *)(a1 + 88) )
  {
    if ( v2 == (_BYTE *)&WPP_GLOBAL_Control || (v2[28] & 8) == 0 )
      return 20004;
    v3 = 11;
LABEL_16:
    WPP_SF_(*((_QWORD *)v2 + 2), v3, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    return 20004;
  }
  if ( !OpenPrinterA(*(LPSTR *)(a1 + 88), &phPrinter, 0) )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 20004;
    v3 = 12;
    goto LABEL_16;
  }
  v4 = phPrinter;
  *(_QWORD *)(a1 + 96) = phPrinter;
  if ( !SetPrinterA(v4, 0, 0, 2u) )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 20004;
    v3 = 13;
    goto LABEL_16;
  }
  *(_QWORD *)&v6 = a1 + 120;
  *((_QWORD *)&v6 + 1) = *(_QWORD *)(a1 + 88);
  LpdReportEvent(0x80000FA2, 2u, (LPCSTR *)&v6, 0);
  result = 0;
  *(_WORD *)(a1 + 20) = 10;
  return result;
}

```

## disassembly

```asm
0x1800063b4  mov     rax, rsp
0x1800063b7  mov     [rax+10h], rbx
0x1800063bb  mov     [rax+18h], rbp
0x1800063bf  push    rdi
0x1800063c0  sub     rsp, 30h
0x1800063c4  xorps   xmm0, xmm0
0x1800063c7  mov     qword ptr [rax+8], 0
0x1800063cf  movups  xmmword ptr [rax-18h], xmm0
0x1800063d3  mov     rbx, rcx
0x1800063d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063dd  lea     rdi, WPP_GLOBAL_Control
0x1800063e4  mov     ebp, 0Ah
0x1800063e9  cmp     rcx, rdi
0x1800063ec  jz      short loc_18000640D
0x1800063ee  test    byte ptr [rcx+1Ch], 1
0x1800063f2  jz      short loc_18000640D
0x1800063f4  mov     rcx, [rcx+10h]
0x1800063f8  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x1800063ff  mov     edx, ebp
0x180006401  call    WPP_SF_
0x180006406  mov     rcx, cs:WPP_GLOBAL_Control
0x18000640d  cmp     qword ptr [rbx+58h], 0
0x180006412  jnz     short loc_180006426
0x180006414  cmp     rcx, rdi
0x180006417  jz      short loc_180006496
0x180006419  test    byte ptr [rcx+1Ch], 8
0x18000641d  jz      short loc_180006496
0x18000641f  mov     edx, 0Bh
0x180006424  jmp     short loc_180006486
0x180006426  mov     rcx, [rbx+58h]; pPrinterName
0x18000642a  lea     rdx, [rsp+38h+phPrinter]; phPrinter
0x18000642f  xor     r8d, r8d; pDefault
0x180006432  call    cs:__imp_OpenPrinterA
0x180006438  test    eax, eax
0x18000643a  jnz     short loc_180006453
0x18000643c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006443  cmp     rcx, rdi
0x180006446  jz      short loc_180006496
0x180006448  test    byte ptr [rcx+1Ch], 8
0x18000644c  jz      short loc_180006496
0x18000644e  lea     edx, [rax+0Ch]
0x180006451  jmp     short loc_180006486
0x180006453  mov     rcx, [rsp+38h+phPrinter]; hPrinter
0x180006458  mov     r9d, 2; Command
0x18000645e  xor     r8d, r8d; pPrinter
0x180006461  mov     [rbx+60h], rcx
0x180006465  xor     edx, edx; Level
0x180006467  call    cs:__imp_SetPrinterA
0x18000646d  test    eax, eax
0x18000646f  jnz     short loc_18000649D
0x180006471  mov     rcx, cs:WPP_GLOBAL_Control
0x180006478  cmp     rcx, rdi
0x18000647b  jz      short loc_180006496
0x18000647d  test    byte ptr [rcx+1Ch], 8
0x180006481  jz      short loc_180006496
0x180006483  lea     edx, [rax+0Dh]
0x180006486  mov     rcx, [rcx+10h]
0x18000648a  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006491  call    WPP_SF_
0x180006496  mov     eax, 4E24h
0x18000649b  jmp     short loc_1800064CC
0x18000649d  lea     rax, [rbx+78h]
0x1800064a1  mov     edx, 2
0x1800064a6  mov     [rsp+38h+var_18], rax
0x1800064ab  lea     r8, [rsp+38h+var_18]
0x1800064b0  mov     rax, [rbx+58h]
0x1800064b4  xor     r9d, r9d
0x1800064b7  mov     ecx, 80000FA2h; dwEventID
0x1800064bc  mov     [rsp+38h+var_10], rax
0x1800064c1  call    LpdReportEvent
0x1800064c6  xor     eax, eax
0x1800064c8  mov     [rbx+14h], bp
0x1800064cc  mov     rbx, [rsp+38h+arg_8]
0x1800064d1  mov     rbp, [rsp+38h+arg_10]
0x1800064d6  add     rsp, 30h
0x1800064da  pop     rdi
0x1800064db  retn
```
