# CopyTnMatchDefaults

- ea: `0x180033c9c`
- end: `0x180033e73`
- name: `CopyTnMatchDefaults`
- size: `471`
- prototype: `__int64 __fastcall(char, _QWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180034b38`

## callees

- `0x18000e510`
- `0x180017534`
- `0x180018194`
- `0x180018fdc`
- `0x180032508`
- `0x180033b40`
- `0x180033c9c`

## pseudocode

```c
__int64 __fastcall CopyTnMatchDefaults(char a1, _QWORD *a2, _QWORD *a3, _DWORD *a4)
{
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 result; // rax

  if ( !gpIniDefaultQMPolicy )
  {
    v8 = 13015;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids, 13015);
    goto LABEL_24;
  }
  v8 = SPDApiBufferAllocate(0xE8u);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v10 = 44;
    goto LABEL_23;
  }
  v8 = SPDApiBufferAllocate(0x30u);
  if ( v8 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v12 = 45;
    goto LABEL_13;
  }
  v8 = CopyDefaultTnFilter(0);
  if ( v8 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v12 = 46;
LABEL_13:
    WPP_SF_d(v11[2], v12, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids, v8);
    goto LABEL_24;
  }
  v8 = CopyQMPolicy(a1, (__int128 *)gpIniDefaultQMPolicy, 0);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_24;
    v10 = 47;
LABEL_23:
    WPP_SF_d(v9[2], v10, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids, v8);
LABEL_24:
    *a2 = 0;
    result = v8;
    *a3 = 0;
    *a4 = 0;
    return result;
  }
  *a2 = 0;
  result = 0;
  *a3 = 0;
  *a4 = 1;
  return result;
}

```

## disassembly

```asm
0x180033c9c  push    rbx
0x180033c9e  push    rbp
0x180033c9f  push    rsi
0x180033ca0  push    rdi
0x180033ca1  push    r12
0x180033ca3  push    r13
0x180033ca5  push    r14
0x180033ca7  push    r15
0x180033ca9  sub     rsp, 38h
0x180033cad  xor     esi, esi
0x180033caf  mov     r15, r9
0x180033cb2  cmp     cs:gpIniDefaultQMPolicy, rsi
0x180033cb9  mov     r12, r8
0x180033cbc  mov     r13, rdx
0x180033cbf  mov     [rsp+78h+var_50], rsi
0x180033cc4  mov     r14d, ecx
0x180033cc7  mov     [rsp+78h+var_58], rsi
0x180033ccc  mov     edi, esi
0x180033cce  jnz     short loc_180033D11
0x180033cd0  mov     ebx, 32D7h
0x180033cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180033cdc  lea     rax, WPP_GLOBAL_Control
0x180033ce3  cmp     rcx, rax
0x180033ce6  jz      loc_180033E42
0x180033cec  test    byte ptr [rcx+1Ch], 10h
0x180033cf0  jz      loc_180033E42
0x180033cf6  mov     rcx, [rcx+10h]
0x180033cfa  lea     edx, [rsi+2Bh]
0x180033cfd  mov     r9d, ebx
0x180033d00  lea     r8, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids
0x180033d07  call    WPP_SF_d
0x180033d0c  jmp     loc_180033E42
0x180033d11  lea     rdx, [rsp+78h+var_50]
0x180033d16  mov     ecx, 0E8h; Size
0x180033d1b  call    SPDApiBufferAllocate
0x180033d20  mov     rbp, [rsp+78h+var_50]
0x180033d25  mov     ebx, eax
0x180033d27  test    eax, eax
0x180033d29  jz      short loc_180033D56
0x180033d2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d32  lea     rax, WPP_GLOBAL_Control
0x180033d39  cmp     rcx, rax
0x180033d3c  jz      loc_180033E22
0x180033d42  test    byte ptr [rcx+1Ch], 10h
0x180033d46  jz      loc_180033E22
0x180033d4c  mov     edx, 2Ch ; ','
0x180033d51  jmp     loc_180033E0F
0x180033d56  lea     rdx, [rsp+78h+var_58]
0x180033d5b  mov     ecx, 30h ; '0'; Size
0x180033d60  call    SPDApiBufferAllocate
0x180033d65  mov     ebx, eax
0x180033d67  test    eax, eax
0x180033d69  jz      short loc_180033DA3
0x180033d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033d72  lea     rax, WPP_GLOBAL_Control
0x180033d79  cmp     rcx, rax
0x180033d7c  jz      short loc_180033D9C
0x180033d7e  test    byte ptr [rcx+1Ch], 10h
0x180033d82  jz      short loc_180033D9C
0x180033d84  mov     edx, 2Dh ; '-'
0x180033d89  mov     rcx, [rcx+10h]
0x180033d8d  lea     r8, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids
0x180033d94  mov     r9d, ebx
0x180033d97  call    WPP_SF_d
0x180033d9c  mov     rdi, [rsp+78h+var_58]
0x180033da1  jmp     short loc_180033E22
0x180033da3  mov     rcx, rbp
0x180033da6  call    CopyDefaultTnFilter
0x180033dab  mov     ebx, eax
0x180033dad  test    eax, eax
0x180033daf  jz      short loc_180033DD1
0x180033db1  mov     rcx, cs:WPP_GLOBAL_Control
0x180033db8  lea     rax, WPP_GLOBAL_Control
0x180033dbf  cmp     rcx, rax
0x180033dc2  jz      short loc_180033D9C
0x180033dc4  test    byte ptr [rcx+1Ch], 10h
0x180033dc8  jz      short loc_180033D9C
0x180033dca  mov     edx, 2Eh ; '.'
0x180033dcf  jmp     short loc_180033D89
0x180033dd1  mov     rdi, [rsp+78h+var_58]
0x180033dd6  mov     ecx, r14d
0x180033dd9  mov     rdx, cs:gpIniDefaultQMPolicy
0x180033de0  mov     r8, rdi
0x180033de3  call    CopyQMPolicy
0x180033de8  mov     ebx, eax
0x180033dea  test    eax, eax
0x180033dec  jz      short loc_180033E51
0x180033dee  mov     esi, 1
0x180033df3  mov     rcx, cs:WPP_GLOBAL_Control
0x180033dfa  lea     rax, WPP_GLOBAL_Control
0x180033e01  cmp     rcx, rax
0x180033e04  jz      short loc_180033E22
0x180033e06  test    byte ptr [rcx+1Ch], 10h
0x180033e0a  jz      short loc_180033E22
0x180033e0c  lea     edx, [rsi+2Eh]
0x180033e0f  mov     rcx, [rcx+10h]
0x180033e13  lea     r8, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids
0x180033e1a  mov     r9d, ebx
0x180033e1d  call    WPP_SF_d
0x180033e22  test    rbp, rbp
0x180033e25  jz      short loc_180033E31
0x180033e27  mov     rdx, rbp
0x180033e2a  mov     ecx, esi
0x180033e2c  call    FreeTnFilters
0x180033e31  xor     esi, esi
0x180033e33  test    rdi, rdi
0x180033e36  jz      short loc_180033E42
0x180033e38  mov     rdx, rdi
0x180033e3b  xor     ecx, ecx
0x180033e3d  call    FreeMMPolicies
0x180033e42  mov     [r13+0], rsi
0x180033e46  mov     eax, ebx
0x180033e48  mov     [r12], rsi
0x180033e4c  mov     [r15], esi
0x180033e4f  jmp     short loc_180033E62
0x180033e51  mov     [r13+0], rbp
0x180033e55  xor     eax, eax
0x180033e57  mov     [r12], rdi
0x180033e5b  mov     dword ptr [r15], 1
0x180033e62  add     rsp, 38h
0x180033e66  pop     r15
0x180033e68  pop     r14
0x180033e6a  pop     r13
0x180033e6c  pop     r12
0x180033e6e  pop     rdi
0x180033e6f  pop     rsi
0x180033e70  pop     rbp
0x180033e71  pop     rbx
0x180033e72  retn
```
