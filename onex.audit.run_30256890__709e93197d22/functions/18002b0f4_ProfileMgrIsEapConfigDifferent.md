# ProfileMgrIsEapConfigDifferent

- ea: `0x18002b0f4`
- end: `0x18002b21c`
- name: `ProfileMgrIsEapConfigDifferent`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180022960`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x1800214f0`
- `0x180026874`
- `0x18002b0f4`

## pseudocode

```c
__int64 __fastcall ProfileMgrIsEapConfigDifferent(__int64 a1, __int64 a2, BOOL *a3)
{
  BOOL v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r10
  unsigned int IsDifferentConnectionData; // eax
  unsigned int v11; // ebx
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  LODWORD(v13) = 0;
  v6 = 1;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  v8 = a2 + *(unsigned int *)(a2 + 64);
  v9 = a1 + *(unsigned int *)(a1 + 64);
  if ( *(_BYTE *)(v9 + 4) != *(_BYTE *)(v8 + 4) || *(_DWORD *)v9 != *(_DWORD *)v8 )
  {
    v11 = 0;
    goto LABEL_13;
  }
  IsDifferentConnectionData = EapIsDifferentConnectionData(
                                *(unsigned int *)(v9 + 24),
                                (void *)(v9 + *(unsigned int *)(v9 + 28)),
                                (__int64)&v13);
  v11 = IsDifferentConnectionData;
  if ( !IsDifferentConnectionData )
  {
    v6 = v13 != 0;
    goto LABEL_10;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      26,
      WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids,
      IsDifferentConnectionData);
LABEL_10:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_13:
  *a3 = v6;
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
    WPP_SF_D(v7[7], 27, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x18002b0f4  mov     [rsp+arg_8], rbx
0x18002b0f9  mov     [rsp+arg_10], rbp
0x18002b0fe  push    rsi
0x18002b0ff  push    rdi
0x18002b100  push    r14
0x18002b102  sub     rsp, 30h
0x18002b106  mov     r14, r8
0x18002b109  mov     dword ptr [rsp+48h+arg_0], 0
0x18002b111  mov     rbx, rdx
0x18002b114  mov     rsi, rcx
0x18002b117  mov     edi, 1
0x18002b11c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b123  lea     rbp, WPP_GLOBAL_Control
0x18002b12a  cmp     rcx, rbp
0x18002b12d  jz      short loc_18002B152
0x18002b12f  test    dword ptr [rcx+44h], 800h
0x18002b136  jz      short loc_18002B152
0x18002b138  mov     rcx, [rcx+38h]
0x18002b13c  lea     edx, [rdi+18h]
0x18002b13f  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002b146  call    WPP_SF_
0x18002b14b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b152  mov     r8d, [rbx+40h]
0x18002b156  mov     r10d, [rsi+40h]
0x18002b15a  add     r8, rbx
0x18002b15d  add     r10, rsi
0x18002b160  mov     al, [r8+4]
0x18002b164  cmp     [r10+4], al
0x18002b168  jnz     short loc_18002B1DC
0x18002b16a  mov     eax, [r8]
0x18002b16d  cmp     [r10], eax
0x18002b170  jnz     short loc_18002B1DC
0x18002b172  mov     r9d, [r8+1Ch]
0x18002b176  lea     rax, [rsp+48h+arg_0]
0x18002b17b  mov     edx, [r10+1Ch]
0x18002b17f  add     r9, r8
0x18002b182  mov     r8d, [r8+18h]
0x18002b186  add     rdx, r10; Buf1
0x18002b189  mov     ecx, [r10+18h]; Size
0x18002b18d  mov     [rsp+48h+var_28], rax; __int64
0x18002b192  call    EapIsDifferentConnectionData
0x18002b197  mov     ebx, eax
0x18002b199  test    eax, eax
0x18002b19b  jz      short loc_18002B1D0
0x18002b19d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1a4  cmp     rcx, rbp
0x18002b1a7  jz      short loc_18002B1DE
0x18002b1a9  test    [rcx+44h], dil
0x18002b1ad  jz      short loc_18002B1DE
0x18002b1af  mov     rcx, [rcx+38h]
0x18002b1b3  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002b1ba  mov     edx, 1Ah
0x18002b1bf  mov     r9d, eax
0x18002b1c2  call    WPP_SF_d
0x18002b1c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1ce  jmp     short loc_18002B1DE
0x18002b1d0  mov     eax, dword ptr [rsp+48h+arg_0]
0x18002b1d4  neg     eax
0x18002b1d6  sbb     ecx, ecx
0x18002b1d8  and     edi, ecx
0x18002b1da  jmp     short loc_18002B1C7
0x18002b1dc  xor     ebx, ebx
0x18002b1de  mov     [r14], edi
0x18002b1e1  cmp     rcx, rbp
0x18002b1e4  jz      short loc_18002B207
0x18002b1e6  test    dword ptr [rcx+44h], 800h
0x18002b1ed  jz      short loc_18002B207
0x18002b1ef  mov     rcx, [rcx+38h]
0x18002b1f3  lea     r8, WPP_cf2b0dcf9cd735c0c1c863ae54fcb446_Traceguids
0x18002b1fa  mov     edx, 1Bh
0x18002b1ff  mov     r9d, ebx
0x18002b202  call    WPP_SF_D
0x18002b207  mov     rbp, [rsp+48h+arg_10]
0x18002b20c  mov     eax, ebx
0x18002b20e  mov     rbx, [rsp+48h+arg_8]
0x18002b213  add     rsp, 30h
0x18002b217  pop     r14
0x18002b219  pop     rdi
0x18002b21a  pop     rsi
0x18002b21b  retn
```
