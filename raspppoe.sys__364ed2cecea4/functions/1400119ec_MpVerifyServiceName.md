# MpVerifyServiceName

- ea: `0x1400119ec`
- end: `0x140011b16`
- name: `MpVerifyServiceName`
- size: `298`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1400108d4`
- `0x1400112e8`

## callees

- `0x1400024dc`
- `0x140002520`
- `0x140006c20`
- `0x1400119ec`
- `0x140014370`

## pseudocode

```c
bool __fastcall MpVerifyServiceName(__int64 a1, __int64 a2)
{
  bool v4; // bl
  void *Buf1; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int16 v7; // [rsp+80h] [rbp+18h] BYREF

  v7 = 0;
  Buf1 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, a2);
  }
  RetrieveTag(
    a2,
    257,
    (unsigned int)&v7,
    (unsigned int)&Buf1,
    0,
    0,
    (unsigned __int16)__ROR2__(*(_WORD *)(*(_QWORD *)(a2 + 112) + 18LL), 8),
    0);
  if ( v7 || !Buf1 )
  {
    v4 = 0;
    if ( v7 == *(_WORD *)(a1 + 410) )
      v4 = memcmp(Buf1, (const void *)(a1 + 153), v7) == 0;
  }
  else
  {
    v4 = 1;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, a2, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1400119ec  mov     rax, rsp
0x1400119ef  mov     [rax+8], rbx
0x1400119f3  mov     [rax+18h], r8b
0x1400119f7  push    rbp
0x1400119f8  push    rsi
0x1400119f9  push    rdi
0x1400119fa  push    r14
0x1400119fc  push    r15
0x1400119fe  sub     rsp, 40h
0x140011a02  xor     ebp, ebp
0x140011a04  mov     rdi, rdx
0x140011a07  mov     [rax+18h], bp
0x140011a0b  mov     rsi, rcx
0x140011a0e  mov     [rax+10h], rbp
0x140011a12  mov     rcx, cs:WPP_GLOBAL_Control
0x140011a19  lea     r15, WPP_GLOBAL_Control
0x140011a20  lea     r14d, [rbp+1]
0x140011a24  cmp     rcx, r15
0x140011a27  jz      short loc_140011A4D
0x140011a29  mov     eax, [rcx+2Ch]
0x140011a2c  test    r14b, al
0x140011a2f  jz      short loc_140011A4D
0x140011a31  cmp     byte ptr [rcx+29h], 4
0x140011a35  jb      short loc_140011A4D
0x140011a37  mov     rcx, [rcx+18h]
0x140011a3b  lea     edx, [rbp+7Ah]
0x140011a3e  mov     r9, rdi
0x140011a41  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140011a48  call    WPP_SF_q
0x140011a4d  mov     rax, [rdi+70h]
0x140011a51  lea     r9, [rsp+68h+Buf1]
0x140011a56  mov     [rsp+68h+var_30], bpl
0x140011a5b  lea     r8, [rsp+68h+arg_10]
0x140011a63  mov     edx, 101h
0x140011a68  movzx   ecx, word ptr [rax+12h]
0x140011a6c  ror     cx, 8
0x140011a70  movzx   eax, cx
0x140011a73  mov     rcx, rdi
0x140011a76  mov     [rsp+68h+var_38], eax
0x140011a7a  mov     [rsp+68h+var_40], rbp
0x140011a7f  mov     word ptr [rsp+68h+var_48], bp
0x140011a84  call    RetrieveTag
0x140011a89  movzx   eax, [rsp+68h+arg_10]
0x140011a91  mov     rcx, [rsp+68h+Buf1]; Buf1
0x140011a96  test    ax, ax
0x140011a99  jnz     short loc_140011AA5
0x140011a9b  test    rcx, rcx
0x140011a9e  jz      short loc_140011AA5
0x140011aa0  mov     bl, r14b
0x140011aa3  jmp     short loc_140011AC7
0x140011aa5  movzx   ebx, bpl
0x140011aa9  cmp     ax, [rsi+19Ah]
0x140011ab0  jnz     short loc_140011AC7
0x140011ab2  mov     r8, rax; Size
0x140011ab5  lea     rdx, [rsi+99h]; Buf2
0x140011abc  call    memcmp
0x140011ac1  test    eax, eax
0x140011ac3  cmovz   ebx, r14d
0x140011ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ace  cmp     rcx, r15
0x140011ad1  jz      short loc_140011B02
0x140011ad3  mov     eax, [rcx+2Ch]
0x140011ad6  test    r14b, al
0x140011ad9  jz      short loc_140011B02
0x140011adb  cmp     byte ptr [rcx+29h], 4
0x140011adf  jb      short loc_140011B02
0x140011ae1  mov     rcx, [rcx+18h]
0x140011ae5  lea     r8, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140011aec  movzx   r9d, bl
0x140011af0  mov     edx, 7Bh ; '{'
0x140011af5  mov     [rsp+68h+var_48], r9d
0x140011afa  mov     r9, rdi
0x140011afd  call    WPP_SF_qd
0x140011b02  mov     al, bl
0x140011b04  mov     rbx, [rsp+68h+arg_0]
0x140011b09  add     rsp, 40h
0x140011b0d  pop     r15
0x140011b0f  pop     r14
0x140011b11  pop     rdi
0x140011b12  pop     rsi
0x140011b13  pop     rbp
0x140011b14  retn
```
