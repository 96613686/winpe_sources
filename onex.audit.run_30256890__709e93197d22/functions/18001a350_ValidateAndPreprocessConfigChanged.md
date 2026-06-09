# ValidateAndPreprocessConfigChanged

- ea: `0x18001a350`
- end: `0x18001a4d6`
- name: `ValidateAndPreprocessConfigChanged`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180001190`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180013560`
- `0x18001a350`
- `0x1800214f0`
- `0x18002f6f9`

## pseudocode

```c
__int64 __fastcall ValidateAndPreprocessConfigChanged(__int64 a1, _DWORD *a2)
{
  __int64 v2; // rdi
  unsigned int v5; // r12d
  unsigned int v6; // r15d
  _DWORD *v7; // r14
  _DWORD *v8; // rbp
  _QWORD *v9; // rbx
  BOOL v10; // ebp
  unsigned int v11; // ebx
  unsigned int updated; // eax
  _QWORD *v13; // rcx

  v2 = *(_QWORD *)(a1 + 24);
  v5 = *(_DWORD *)(v2 + 20);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 15, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids);
  *a2 = 0;
  v6 = *(_DWORD *)(a1 + 44);
  v7 = *(_DWORD **)(a1 + 48);
  v8 = *(_DWORD **)(v2 + 2744);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 23, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = v8[1] != v7[1] || memcmp_0(v8, v7, (unsigned int)v8[1]) != 0;
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(v9[7], 24, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, 0);
  v11 = 0;
  if ( !v10 )
    goto LABEL_20;
  if ( *(_DWORD *)(v2 + 2400) != 1 )
  {
    *a2 = 1;
LABEL_21:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  updated = PortMgrUpdatePortCharacterstics((_DWORD *)v2, v6, (__int64)v7, 0);
  v11 = updated;
  if ( !updated )
  {
LABEL_20:
    *a2 = 0;
    goto LABEL_21;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v5, updated);
    goto LABEL_21;
  }
LABEL_22:
  if ( v13 != &WPP_GLOBAL_Control && (*((_DWORD *)v13 + 17) & 0x800) != 0 )
    WPP_SF_D(v13[7], 18, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18001a350  push    rbx
0x18001a352  push    rbp
0x18001a353  push    rsi
0x18001a354  push    rdi
0x18001a355  push    r12
0x18001a357  push    r13
0x18001a359  push    r14
0x18001a35b  push    r15
0x18001a35d  sub     rsp, 38h
0x18001a361  mov     rdi, [rcx+18h]
0x18001a365  mov     rsi, rdx
0x18001a368  mov     rbx, rcx
0x18001a36b  mov     r12d, [rdi+14h]
0x18001a36f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a376  lea     r13, WPP_GLOBAL_Control
0x18001a37d  cmp     rcx, r13
0x18001a380  jz      short loc_18001A3A0
0x18001a382  test    dword ptr [rcx+44h], 800h
0x18001a389  jz      short loc_18001A3A0
0x18001a38b  mov     rcx, [rcx+38h]
0x18001a38f  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x18001a396  mov     edx, 0Fh
0x18001a39b  call    WPP_SF_
0x18001a3a0  mov     dword ptr [rsi], 0
0x18001a3a6  mov     r15d, [rbx+2Ch]
0x18001a3aa  mov     r14, [rbx+30h]
0x18001a3ae  mov     rbp, [rdi+0AB8h]
0x18001a3b5  mov     rbx, cs:WPP_GLOBAL_Control
0x18001a3bc  cmp     rbx, r13
0x18001a3bf  jz      short loc_18001A3E6
0x18001a3c1  test    dword ptr [rbx+44h], 800h
0x18001a3c8  jz      short loc_18001A3E6
0x18001a3ca  mov     rcx, [rbx+38h]
0x18001a3ce  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18001a3d5  mov     edx, 17h
0x18001a3da  call    WPP_SF_
0x18001a3df  mov     rbx, cs:WPP_GLOBAL_Control
0x18001a3e6  mov     eax, [rbp+4]
0x18001a3e9  cmp     eax, [r14+4]
0x18001a3ed  jz      short loc_18001A3F6
0x18001a3ef  mov     ebp, 1
0x18001a3f4  jmp     short loc_18001A40C
0x18001a3f6  mov     r8, rax; Size
0x18001a3f9  mov     rdx, r14; Buf2
0x18001a3fc  mov     rcx, rbp; Buf1
0x18001a3ff  call    memcmp_0
0x18001a404  xor     ebp, ebp
0x18001a406  test    eax, eax
0x18001a408  setnz   bpl
0x18001a40c  cmp     rbx, r13
0x18001a40f  jz      short loc_18001A432
0x18001a411  test    dword ptr [rbx+44h], 800h
0x18001a418  jz      short loc_18001A432
0x18001a41a  mov     rcx, [rbx+38h]
0x18001a41e  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18001a425  mov     edx, 18h
0x18001a42a  xor     r9d, r9d
0x18001a42d  call    WPP_SF_D
0x18001a432  xor     ebx, ebx
0x18001a434  test    ebp, ebp
0x18001a436  jz      short loc_18001A490
0x18001a438  cmp     dword ptr [rdi+960h], 1
0x18001a43f  jz      short loc_18001A449
0x18001a441  mov     dword ptr [rsi], 1
0x18001a447  jmp     short loc_18001A496
0x18001a449  xor     r9d, r9d
0x18001a44c  mov     r8, r14
0x18001a44f  mov     edx, r15d
0x18001a452  mov     rcx, rdi
0x18001a455  call    PortMgrUpdatePortCharacterstics
0x18001a45a  mov     ebx, eax
0x18001a45c  test    eax, eax
0x18001a45e  jz      short loc_18001A490
0x18001a460  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a467  cmp     rcx, r13
0x18001a46a  jz      short loc_18001A4C3
0x18001a46c  test    byte ptr [rcx+44h], 1
0x18001a470  jz      short loc_18001A49D
0x18001a472  mov     rcx, [rcx+38h]
0x18001a476  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x18001a47d  mov     edx, 11h
0x18001a482  mov     [rsp+78h+var_58], eax
0x18001a486  mov     r9d, r12d
0x18001a489  call    WPP_SF_dd
0x18001a48e  jmp     short loc_18001A496
0x18001a490  mov     dword ptr [rsi], 0
0x18001a496  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a49d  cmp     rcx, r13
0x18001a4a0  jz      short loc_18001A4C3
0x18001a4a2  test    dword ptr [rcx+44h], 800h
0x18001a4a9  jz      short loc_18001A4C3
0x18001a4ab  mov     rcx, [rcx+38h]
0x18001a4af  lea     r8, WPP_ef27ed7cc63433545d14975404ab22f2_Traceguids
0x18001a4b6  mov     edx, 12h
0x18001a4bb  mov     r9d, ebx
0x18001a4be  call    WPP_SF_D
0x18001a4c3  mov     eax, ebx
0x18001a4c5  add     rsp, 38h
0x18001a4c9  pop     r15
0x18001a4cb  pop     r14
0x18001a4cd  pop     r13
0x18001a4cf  pop     r12
0x18001a4d1  pop     rdi
0x18001a4d2  pop     rsi
0x18001a4d3  pop     rbp
0x18001a4d4  pop     rbx
0x18001a4d5  retn
```
