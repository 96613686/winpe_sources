# QuicBindingRegisterListener

- ea: `0x140002ca4`
- end: `0x140002e86`
- name: `QuicBindingRegisterListener`
- size: `482`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140002840`

## callees

- `0x1400017c8`
- `0x140002ca4`
- `0x1400036c0`
- `0x14003c8e0`
- `0x14003ead8`
- `0x140040b2c`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140002de9`
- `ntoskrnl!_snprintf_s` at `0x140002de9`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140002e28`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140002e28`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140002ceb`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140002ceb`

## string_xrefs

- `0x140002dcf`: `[bind][%p] Listener (%p) already registered on ALPN`

## pseudocode

```c
__int64 __fastcall QuicBindingRegisterListener(__int64 a1, __int64 a2)
{
  unsigned __int16 v2; // r12
  unsigned int v3; // r14d
  bool v4; // r15
  _QWORD *v7; // r13
  _QWORD *i; // rdi
  _QWORD *v9; // rbp
  unsigned __int16 v10; // ax
  char v11; // cl
  _QWORD *v12; // rdx
  _QWORD *v13; // rax
  bool v14; // zf
  __int64 v15; // rcx
  _QWORD *v16; // rax
  char v18; // [rsp+30h] [rbp-D8h]
  KIRQL OldIrql; // [rsp+31h] [rbp-D7h]
  char DstBuf[128]; // [rsp+40h] [rbp-C8h] BYREF

  v2 = *(_WORD *)(a2 + 112);
  v3 = 0;
  v4 = 0;
  v18 = *(_BYTE *)(a2 + 16);
  v7 = (_QWORD *)(a1 + 48);
  OldIrql = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 40));
  for ( i = (_QWORD *)*v7; ; i = (_QWORD *)*i )
  {
    if ( i == v7 || (v9 = i - 4, v10 = *((_WORD *)i + 40), v11 = *((_BYTE *)i - 16), v2 > v10) )
    {
LABEL_6:
      v12 = (_QWORD *)(a2 + 32);
      v4 = *(_QWORD *)(a1 + 48) == a1 + 48;
      if ( i == (_QWORD *)(a1 + 48) )
      {
        v13 = *(_QWORD **)(a1 + 56);
        *v12 = a1 + 48;
        *(_QWORD *)(a2 + 40) = v13;
        *v13 = v12;
        *(_QWORD *)(a1 + 56) = v12;
      }
      else
      {
        *v12 = i;
        v16 = (_QWORD *)i[1];
        *(_QWORD *)(a2 + 40) = v16;
        *v16 = v12;
        i[1] = v12;
      }
      goto LABEL_23;
    }
    if ( v2 == v10 )
    {
      if ( v18 )
      {
        if ( v18 != v11 )
          continue;
      }
      else if ( v11 )
      {
        goto LABEL_6;
      }
      if ( !v2 )
        goto LABEL_29;
      if ( *(_WORD *)(a2 + 112) == 2 )
      {
        v14 = *(_DWORD *)(a2 + 116) == *((_DWORD *)v9 + 29);
      }
      else
      {
        if ( *(_QWORD *)(a2 + 120) != v9[15] )
          continue;
        v14 = *(_QWORD *)(a2 + 128) == v9[16];
      }
      if ( v14 )
      {
LABEL_29:
        if ( QuicListenerFindAlpnInList(a2, *((_WORD *)v9 + 88), (unsigned __int8 *)v9[23]) )
          break;
      }
    }
  }
  if ( (byte_14005C48E & 0x20) != 0 )
  {
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "[bind][%p] Listener (%p) already registered on ALPN",
      (const void *)a1,
      i - 4);
    McTemplateU0s_EtwWriteTransfer(v15, (const EVENT_DESCRIPTOR *)QuicLogWarning, DstBuf);
  }
  v3 = -1071382519;
LABEL_23:
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 40), OldIrql);
  if ( v4 && !(unsigned __int8)QuicLookupMaximizePartitioning(a1 + 64) )
  {
    QuicBindingUnregisterListener(a1, a2);
    return (unsigned int)-1073741801;
  }
  return v3;
}

```

## disassembly

```asm
0x140002ca4  mov     [rsp+arg_10], rbx
0x140002ca9  push    rbp
0x140002caa  push    rsi
0x140002cab  push    rdi
0x140002cac  push    r12
0x140002cae  push    r13
0x140002cb0  push    r14
0x140002cb2  push    r15
0x140002cb4  sub     rsp, 0D0h
0x140002cbb  mov     rax, cs:__security_cookie
0x140002cc2  xor     rax, rsp
0x140002cc5  mov     [rsp+108h+var_48], rax
0x140002ccd  movzx   r12d, word ptr [rdx+70h]
0x140002cd2  xor     eax, eax
0x140002cd4  mov     r14d, eax
0x140002cd7  mov     r15b, al
0x140002cda  mov     al, [rdx+10h]
0x140002cdd  mov     rbx, rcx
0x140002ce0  add     rcx, 28h ; '('; SpinLock
0x140002ce4  mov     [rsp+108h+var_D8], al
0x140002ce8  mov     rsi, rdx
0x140002ceb  call    cs:__imp_ExAcquireSpinLockExclusive
0x140002cf2  nop     dword ptr [rax+rax+00h]
0x140002cf7  lea     r13, [rbx+30h]
0x140002cfb  mov     [rsp+108h+OldIrql], al
0x140002cff  mov     rdi, [r13+0]
0x140002d03  jmp     loc_140002DB3
0x140002d08  lea     rbp, [rdi-20h]
0x140002d0c  movzx   eax, word ptr [rbp+70h]
0x140002d10  mov     cl, [rbp+10h]
0x140002d13  cmp     r12w, ax
0x140002d17  ja      short loc_140002D2B
0x140002d19  jnz     loc_140002DB0
0x140002d1f  mov     al, [rsp+108h+var_D8]
0x140002d23  test    al, al
0x140002d25  jnz     short loc_140002D62
0x140002d27  test    cl, cl
0x140002d29  jz      short loc_140002D66
0x140002d2b  lea     rax, [rbx+30h]
0x140002d2f  cmp     [rax], rax
0x140002d32  lea     rdx, [rsi+20h]
0x140002d36  lea     rax, [rbx+30h]
0x140002d3a  setz    r15b
0x140002d3e  cmp     rdi, rax
0x140002d41  jnz     loc_140002E0E
0x140002d47  lea     rcx, [rbx+30h]
0x140002d4b  mov     rax, [rcx+8]
0x140002d4f  mov     [rdx], rcx
0x140002d52  mov     [rdx+8], rax
0x140002d56  mov     [rax], rdx
0x140002d59  mov     [rcx+8], rdx
0x140002d5d  jmp     loc_140002E20
0x140002d62  cmp     al, cl
0x140002d64  jnz     short loc_140002DB0
0x140002d66  test    r12w, r12w
0x140002d6a  jz      short loc_140002D95
0x140002d6c  cmp     word ptr [rsi+70h], 2
0x140002d71  jnz     short loc_140002D7B
0x140002d73  mov     eax, [rsi+74h]
0x140002d76  cmp     eax, [rbp+74h]
0x140002d79  jmp     short loc_140002D93
0x140002d7b  mov     rax, [rsi+78h]
0x140002d7f  cmp     rax, [rbp+78h]
0x140002d83  jnz     short loc_140002DB0
0x140002d85  mov     rax, [rsi+80h]
0x140002d8c  cmp     rax, [rbp+80h]
0x140002d93  jnz     short loc_140002DB0
0x140002d95  mov     r8, [rbp+0B8h]
0x140002d9c  mov     rcx, rsi
0x140002d9f  movzx   edx, word ptr [rbp+0B0h]
0x140002da6  call    QuicListenerFindAlpnInList
0x140002dab  test    rax, rax
0x140002dae  jnz     short loc_140002DC1
0x140002db0  mov     rdi, [rdi]
0x140002db3  cmp     rdi, r13
0x140002db6  jnz     loc_140002D08
0x140002dbc  jmp     loc_140002D2B
0x140002dc1  test    cs:byte_14005C48E, 20h
0x140002dc8  jz      short loc_140002E06
0x140002dca  mov     [rsp+108h+var_E0], rbp
0x140002dcf  lea     r9, aBindPListenerP; "[bind][%p] Listener (%p) already regist"...
0x140002dd6  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140002dda  mov     [rsp+108h+var_E8], rbx
0x140002ddf  mov     edx, 80h; SizeInBytes
0x140002de4  lea     rcx, [rsp+108h+DstBuf]; DstBuf
0x140002de9  call    cs:__imp__snprintf_s
0x140002df0  nop     dword ptr [rax+rax+00h]
0x140002df5  lea     r8, [rsp+108h+DstBuf]
0x140002dfa  lea     rdx, QuicLogWarning
0x140002e01  call    McTemplateU0s_EtwWriteTransfer
0x140002e06  mov     r14d, 0C0240009h
0x140002e0c  jmp     short loc_140002E20
0x140002e0e  mov     [rdx], rdi
0x140002e11  mov     rax, [rdi+8]
0x140002e15  mov     [rsi+28h], rax
0x140002e19  mov     [rax], rdx
0x140002e1c  mov     [rdi+8], rdx
0x140002e20  mov     dl, [rsp+108h+OldIrql]; OldIrql
0x140002e24  lea     rcx, [rbx+28h]; SpinLock
0x140002e28  call    cs:__imp_ExReleaseSpinLockExclusive
0x140002e2f  nop     dword ptr [rax+rax+00h]
0x140002e34  test    r15b, r15b
0x140002e37  jz      short loc_140002E57
0x140002e39  lea     rcx, [rbx+40h]
0x140002e3d  call    QuicLookupMaximizePartitioning
0x140002e42  test    al, al
0x140002e44  jnz     short loc_140002E57
0x140002e46  mov     rdx, rsi
0x140002e49  mov     rcx, rbx
0x140002e4c  call    QuicBindingUnregisterListener
0x140002e51  mov     r14d, 0C0000017h
0x140002e57  mov     eax, r14d
0x140002e5a  mov     rcx, [rsp+108h+var_48]
0x140002e62  xor     rcx, rsp; StackCookie
0x140002e65  call    __security_check_cookie
0x140002e6a  mov     rbx, [rsp+108h+arg_10]
0x140002e72  add     rsp, 0D0h
0x140002e79  pop     r15
0x140002e7b  pop     r14
0x140002e7d  pop     r13
0x140002e7f  pop     r12
0x140002e81  pop     rdi
0x140002e82  pop     rsi
0x140002e83  pop     rbp
0x140002e84  retn
```
