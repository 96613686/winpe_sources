# PAProcessQMNFAUpdate

- ea: `0x18002ada0`
- end: `0x18002ae73`
- name: `PAProcessQMNFAUpdate`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18002b314`

## callees

- `0x18000cd90`
- `0x18000cfa8`
- `0x18000cfdc`
- `0x18002a120`
- `0x18002a170`
- `0x18002a6c8`
- `0x18002aa24`
- `0x18002acb8`
- `0x18002ada0`

## pseudocode

```c
__int64 __fastcall PAProcessQMNFAUpdate(__int64 a1, __int64 a2, unsigned int a3)
{
  _QWORD *v4; // rcx
  _QWORD *v6; // rdx
  __int64 v8; // rax
  __int64 result; // rax
  __int64 v10; // rbp
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = 0;
  v4 = *(_QWORD **)(a1 + 104);
  v6 = *(_QWORD **)(a2 + 104);
  v8 = *v4 - *v6;
  if ( *v4 == *v6 )
    v8 = v4[1] - v6[1];
  if ( v8 )
  {
    PADeleteQMInfoForNFA(a1);
    return PAAddQMInfoForNFA(a2, a3);
  }
  result = PAProcessNegPolUpdate(a1, a2, &v15, a3);
  if ( !v15 )
  {
    v10 = *(_QWORD *)(a2 + 104);
    v11 = EqualFilterKeysInNegPols(*(_QWORD *)(a1 + 104), v10);
    v12 = a1;
    if ( !v11 )
    {
LABEL_7:
      PADeleteQMFilterSpecs(v12);
      return PAAddQMFilterSpecs(a2, a3);
    }
    if ( !(unsigned int)EqualFilterKeysInNFAs(a1, a2) )
    {
      v12 = a1;
      goto LABEL_7;
    }
    v14 = *(_QWORD *)(v10 + 32) - 0x11D16C3762F49E13LL;
    if ( *(_QWORD *)(v10 + 32) == 0x11D16C3762F49E13LL )
      v14 = *(_QWORD *)(v10 + 40) - 2736016518LL;
    if ( v14 )
      return PAProcessQMFilterDataForNFAs(a1, v13, a3);
    else
      return 87;
  }
  return result;
}

```

## disassembly

```asm
0x18002ada0  push    rbx
0x18002ada2  push    rbp
0x18002ada3  push    rsi
0x18002ada4  push    rdi
0x18002ada5  sub     rsp, 28h
0x18002ada9  mov     rdi, rcx
0x18002adac  mov     [rsp+48h+arg_0], 0
0x18002adb4  mov     rcx, [rcx+68h]
0x18002adb8  mov     rbx, rdx
0x18002adbb  mov     rdx, [rdx+68h]
0x18002adbf  mov     esi, r8d
0x18002adc2  mov     rax, [rcx]
0x18002adc5  sub     rax, [rdx]
0x18002adc8  jnz     short loc_18002ADD2
0x18002adca  mov     rax, [rcx+8]
0x18002adce  sub     rax, [rdx+8]
0x18002add2  mov     rcx, rdi
0x18002add5  test    rax, rax
0x18002add8  jz      short loc_18002ADEB
0x18002adda  call    PADeleteQMInfoForNFA
0x18002addf  mov     edx, esi
0x18002ade1  mov     rcx, rbx
0x18002ade4  call    PAAddQMInfoForNFA
0x18002ade9  jmp     short loc_18002AE6A
0x18002adeb  mov     r9d, esi
0x18002adee  lea     r8, [rsp+48h+arg_0]
0x18002adf3  mov     rdx, rbx
0x18002adf6  call    PAProcessNegPolUpdate
0x18002adfb  cmp     [rsp+48h+arg_0], 0
0x18002ae00  jnz     short loc_18002AE6A
0x18002ae02  mov     rbp, [rbx+68h]
0x18002ae06  mov     rcx, [rdi+68h]
0x18002ae0a  mov     rdx, rbp
0x18002ae0d  call    EqualFilterKeysInNegPols
0x18002ae12  mov     rcx, rdi
0x18002ae15  test    eax, eax
0x18002ae17  jnz     short loc_18002AE2A
0x18002ae19  call    PADeleteQMFilterSpecs
0x18002ae1e  mov     edx, esi
0x18002ae20  mov     rcx, rbx
0x18002ae23  call    PAAddQMFilterSpecs
0x18002ae28  jmp     short loc_18002AE6A
0x18002ae2a  mov     rdx, rbx
0x18002ae2d  call    EqualFilterKeysInNFAs
0x18002ae32  test    eax, eax
0x18002ae34  jnz     short loc_18002AE3B
0x18002ae36  mov     rcx, rdi
0x18002ae39  jmp     short loc_18002AE19
0x18002ae3b  mov     rax, [rbp+20h]
0x18002ae3f  sub     rax, cs:qword_180059FD8
0x18002ae46  jnz     short loc_18002AE53
0x18002ae48  mov     rax, [rbp+28h]
0x18002ae4c  sub     rax, cs:qword_180059FE0
0x18002ae53  test    rax, rax
0x18002ae56  jnz     short loc_18002AE5F
0x18002ae58  mov     eax, 57h ; 'W'
0x18002ae5d  jmp     short loc_18002AE6A
0x18002ae5f  mov     r8d, esi
0x18002ae62  mov     rcx, rdi
0x18002ae65  call    PAProcessQMFilterDataForNFAs
0x18002ae6a  add     rsp, 28h
0x18002ae6e  pop     rdi
0x18002ae6f  pop     rsi
0x18002ae70  pop     rbp
0x18002ae71  pop     rbx
0x18002ae72  retn
```
