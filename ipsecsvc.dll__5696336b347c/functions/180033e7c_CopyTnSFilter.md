# CopyTnSFilter

- ea: `0x180033e7c`
- end: `0x1800340df`
- name: `CopyTnSFilter`
- size: `611`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800342e8`
- `0x1800344cc`
- `0x180034b38`

## callees

- `0x18000e510`
- `0x180016398`
- `0x1800171d0`
- `0x1800173d0`
- `0x1800175dc`
- `0x180033e7c`

## pseudocode

```c
__int64 __fastcall CopyTnSFilter(__int64 a1, __int64 a2)
{
  _QWORD *v2; // r14
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 result; // rax

  v2 = (_QWORD *)(a2 + 24);
  *(_DWORD *)a2 = *(_DWORD *)a1;
  *(_OWORD *)(a2 + 4) = *(_OWORD *)(a1 + 4);
  v5 = CopyName(*(STRSAFE_LPCWSTR *)(a1 + 24), (_QWORD *)(a2 + 24));
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_22;
    v7 = 27;
    goto LABEL_21;
  }
  *(_DWORD *)(a2 + 32) = *(_DWORD *)(a1 + 32);
  *(_DWORD *)(a2 + 36) = 0;
  *(_DWORD *)(a2 + 40) = *(_DWORD *)(a1 + 36);
  v5 = CopyIntToOldExtAddresses(a1 + 40, a2 + 48);
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_22;
    v7 = 28;
    goto LABEL_21;
  }
  v5 = CopyIntToOldExtAddresses(a1 + 80, a2 + 80);
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_22;
    v7 = 29;
    goto LABEL_21;
  }
  v5 = CopyIntToOldExtAddresses(a1 + 120, a2 + 136);
  if ( v5 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_22;
    v7 = 30;
    goto LABEL_21;
  }
  v5 = CopyIntToOldExtAddresses(a1 + 160, a2 + 168);
  if ( !v5 )
  {
    *(_QWORD *)(a2 + 112) = *(_QWORD *)(a1 + 200);
    CopyPortsToOld(a1 + 208, a2 + 120);
    CopyPortsToOld(a1 + 216, a2 + 128);
    *(_DWORD *)(a2 + 200) = *(_DWORD *)(a1 + 224);
    *(_DWORD *)(a2 + 204) = *(_DWORD *)(a1 + 228);
    *(_DWORD *)(a2 + 208) = *(_DWORD *)(a1 + 236);
    *(_DWORD *)(a2 + 212) = *(_DWORD *)(a1 + 240);
    result = 0;
    *(_OWORD *)(a2 + 216) = *(_OWORD *)(a1 + 244);
    return result;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v7 = 31;
LABEL_21:
    WPP_SF_d(v6[2], v7, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids, v5);
  }
LABEL_22:
  if ( *v2 )
  {
    SPDApiBufferFree(*v2);
    *v2 = 0;
  }
  v8 = *(_QWORD *)(a2 + 64);
  if ( v8 )
  {
    SPDApiBufferFree(v8);
    *(_QWORD *)(a2 + 64) = 0;
  }
  v9 = *(_QWORD *)(a2 + 96);
  if ( v9 )
  {
    SPDApiBufferFree(v9);
    *(_QWORD *)(a2 + 96) = 0;
  }
  v10 = *(_QWORD *)(a2 + 152);
  if ( v10 )
  {
    SPDApiBufferFree(v10);
    *(_QWORD *)(a2 + 152) = 0;
  }
  v11 = *(_QWORD *)(a2 + 184);
  if ( v11 )
  {
    SPDApiBufferFree(v11);
    *(_QWORD *)(a2 + 184) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180033e7c  push    rbx
0x180033e7e  push    rsi
0x180033e7f  push    rdi
0x180033e80  push    r14
0x180033e82  sub     rsp, 28h
0x180033e86  mov     eax, [rcx]
0x180033e88  lea     r14, [rdx+18h]
0x180033e8c  mov     [rdx], eax
0x180033e8e  mov     rbx, rdx
0x180033e91  movups  xmm0, xmmword ptr [rcx+4]
0x180033e95  mov     rsi, rcx
0x180033e98  movdqu  xmmword ptr [rdx+4], xmm0
0x180033e9d  mov     rcx, [rcx+18h]; pszSrc
0x180033ea1  mov     rdx, r14
0x180033ea4  call    CopyName
0x180033ea9  mov     edi, eax
0x180033eab  test    eax, eax
0x180033ead  jz      short loc_180033EDA
0x180033eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180033eb6  lea     rax, WPP_GLOBAL_Control
0x180033ebd  cmp     rcx, rax
0x180033ec0  jz      loc_180033FEA
0x180033ec6  test    byte ptr [rcx+1Ch], 10h
0x180033eca  jz      loc_180033FEA
0x180033ed0  mov     edx, 1Bh
0x180033ed5  jmp     loc_180033FD7
0x180033eda  mov     eax, [rsi+20h]
0x180033edd  lea     rdx, [rbx+30h]
0x180033ee1  mov     [rbx+20h], eax
0x180033ee4  lea     rcx, [rsi+28h]
0x180033ee8  mov     dword ptr [rbx+24h], 0
0x180033eef  mov     eax, [rsi+24h]
0x180033ef2  mov     [rbx+28h], eax
0x180033ef5  call    CopyIntToOldExtAddresses
0x180033efa  mov     edi, eax
0x180033efc  test    eax, eax
0x180033efe  jz      short loc_180033F2B
0x180033f00  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f07  lea     rax, WPP_GLOBAL_Control
0x180033f0e  cmp     rcx, rax
0x180033f11  jz      loc_180033FEA
0x180033f17  test    byte ptr [rcx+1Ch], 10h
0x180033f1b  jz      loc_180033FEA
0x180033f21  mov     edx, 1Ch
0x180033f26  jmp     loc_180033FD7
0x180033f2b  lea     rdx, [rbx+50h]
0x180033f2f  lea     rcx, [rsi+50h]
0x180033f33  call    CopyIntToOldExtAddresses
0x180033f38  mov     edi, eax
0x180033f3a  test    eax, eax
0x180033f3c  jz      short loc_180033F66
0x180033f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f45  lea     rax, WPP_GLOBAL_Control
0x180033f4c  cmp     rcx, rax
0x180033f4f  jz      loc_180033FEA
0x180033f55  test    byte ptr [rcx+1Ch], 10h
0x180033f59  jz      loc_180033FEA
0x180033f5f  mov     edx, 1Dh
0x180033f64  jmp     short loc_180033FD7
0x180033f66  lea     rdx, [rbx+88h]
0x180033f6d  lea     rcx, [rsi+78h]
0x180033f71  call    CopyIntToOldExtAddresses
0x180033f76  mov     edi, eax
0x180033f78  test    eax, eax
0x180033f7a  jz      short loc_180033F9C
0x180033f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f83  lea     rax, WPP_GLOBAL_Control
0x180033f8a  cmp     rcx, rax
0x180033f8d  jz      short loc_180033FEA
0x180033f8f  test    byte ptr [rcx+1Ch], 10h
0x180033f93  jz      short loc_180033FEA
0x180033f95  mov     edx, 1Eh
0x180033f9a  jmp     short loc_180033FD7
0x180033f9c  lea     rdx, [rbx+0A8h]
0x180033fa3  lea     rcx, [rsi+0A0h]
0x180033faa  call    CopyIntToOldExtAddresses
0x180033faf  mov     edi, eax
0x180033fb1  test    eax, eax
0x180033fb3  jz      loc_180034066
0x180033fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180033fc0  lea     rax, WPP_GLOBAL_Control
0x180033fc7  cmp     rcx, rax
0x180033fca  jz      short loc_180033FEA
0x180033fcc  test    byte ptr [rcx+1Ch], 10h
0x180033fd0  jz      short loc_180033FEA
0x180033fd2  mov     edx, 1Fh
0x180033fd7  mov     rcx, [rcx+10h]
0x180033fdb  lea     r8, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids
0x180033fe2  mov     r9d, edi
0x180033fe5  call    WPP_SF_d
0x180033fea  mov     rcx, [r14]
0x180033fed  test    rcx, rcx
0x180033ff0  jz      short loc_180033FFE
0x180033ff2  call    SPDApiBufferFree
0x180033ff7  mov     qword ptr [r14], 0
0x180033ffe  mov     rcx, [rbx+40h]
0x180034002  test    rcx, rcx
0x180034005  jz      short loc_180034014
0x180034007  call    SPDApiBufferFree
0x18003400c  mov     qword ptr [rbx+40h], 0
0x180034014  mov     rcx, [rbx+60h]
0x180034018  test    rcx, rcx
0x18003401b  jz      short loc_18003402A
0x18003401d  call    SPDApiBufferFree
0x180034022  mov     qword ptr [rbx+60h], 0
0x18003402a  mov     rcx, [rbx+98h]
0x180034031  test    rcx, rcx
0x180034034  jz      short loc_180034046
0x180034036  call    SPDApiBufferFree
0x18003403b  mov     qword ptr [rbx+98h], 0
0x180034046  mov     rcx, [rbx+0B8h]
0x18003404d  test    rcx, rcx
0x180034050  jz      short loc_180034062
0x180034052  call    SPDApiBufferFree
0x180034057  mov     qword ptr [rbx+0B8h], 0
0x180034062  mov     eax, edi
0x180034064  jmp     short loc_1800340D5
0x180034066  mov     rax, [rsi+0C8h]
0x18003406d  lea     rdx, [rbx+78h]
0x180034071  lea     rcx, [rsi+0D0h]
0x180034078  mov     [rbx+70h], rax
0x18003407c  call    CopyPortsToOld
0x180034081  lea     rdx, [rbx+80h]
0x180034088  lea     rcx, [rsi+0D8h]
0x18003408f  call    CopyPortsToOld
0x180034094  mov     ecx, [rsi+0E0h]
0x18003409a  mov     [rbx+0C8h], ecx
0x1800340a0  mov     eax, [rsi+0E4h]
0x1800340a6  mov     [rbx+0CCh], eax
0x1800340ac  mov     eax, [rsi+0ECh]
0x1800340b2  mov     [rbx+0D0h], eax
0x1800340b8  mov     eax, [rsi+0F0h]
0x1800340be  mov     [rbx+0D4h], eax
0x1800340c4  xor     eax, eax
0x1800340c6  movups  xmm0, xmmword ptr [rsi+0F4h]
0x1800340cd  movdqu  xmmword ptr [rbx+0D8h], xmm0
0x1800340d5  add     rsp, 28h
0x1800340d9  pop     r14
0x1800340db  pop     rdi
0x1800340dc  pop     rsi
0x1800340dd  pop     rbx
0x1800340de  retn
```
