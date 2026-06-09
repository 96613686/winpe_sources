# ORCompareStrings

- ea: `0x140026984`
- end: `0x140026ad9`
- name: `ORCompareStrings`
- size: `341`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140024888`
- `0x140024f20`
- `0x14002593c`
- `0x14002a1ac`

## callees

- `0x1400268ac`
- `0x140026984`
- `0x140026ae0`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x140026a0e`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140026a35`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140026a0e`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140026a35`

## pseudocode

```c
__int64 __fastcall ORCompareStrings(int a1, __int64 a2, unsigned __int64 a3, int a4, __int64 a5, unsigned __int64 a6)
{
  __int64 v6; // rax
  __int64 v9; // r12
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  bool v12; // zf
  unsigned int v13; // ebx
  unsigned int v14; // r14d
  unsigned int v15; // r15d
  _QWORD v17[2]; // [rsp+20h] [rbp-28h] BYREF
  __int128 v18; // [rsp+30h] [rbp-18h] BYREF

  v6 = a5;
  v18 = 0;
  if ( !a4 )
  {
    LOWORD(v18) = a6;
    WORD1(v18) = a6;
    *((_QWORD *)&v18 + 1) = a5;
  }
  if ( a1 )
  {
    if ( a4 )
    {
      v9 = 0;
      v10 = a3;
      v11 = a6;
      v12 = a3 == 0;
      v13 = 1;
      while ( 1 )
      {
        *(_QWORD *)&v18 = v11;
        v17[0] = v10;
        if ( v12 || !v11 )
          break;
        v14 = *(unsigned __int8 *)(v9 + a2);
        v15 = *(unsigned __int8 *)(v6 + v9);
        if ( (_WORD)v14 != (_WORD)v15 )
        {
          if ( v14 >= 0x61 )
          {
            if ( v14 <= 0x7A )
              LOWORD(v14) = v14 - 32;
            else
              LOWORD(v14) = RtlUpcaseUnicodeChar(*(unsigned __int8 *)(v9 + a2));
          }
          if ( v15 >= 0x61 )
          {
            if ( v15 <= 0x7A )
              LOWORD(v15) = v15 - 32;
            else
              LOWORD(v15) = RtlUpcaseUnicodeChar(v15);
          }
          if ( (unsigned __int16)v14 < (unsigned __int16)v15 )
            return (unsigned int)-1;
          if ( (unsigned __int16)v14 > (unsigned __int16)v15 )
            return v13;
          v6 = a5;
          v11 = v18;
          v10 = v17[0];
        }
        --v10;
        --v11;
        ++v9;
        v12 = v10 == 0;
      }
      if ( a3 <= a6 )
        return (unsigned int)-(a3 < a6);
      return v13;
    }
    else
    {
      return (unsigned int)-ORCompareCompressedString(&v18, a2, a3);
    }
  }
  else
  {
    LOWORD(v17[0]) = a3;
    HIDWORD(v17[0]) = 0;
    WORD1(v17[0]) = a3;
    v17[1] = a2;
    if ( a4 )
      return ORCompareCompressedString(v17, a5, a6);
    else
      return ORCompareUnicodeString(v17, &v18);
  }
}

```

## disassembly

```asm
0x140026984  push    rbp
0x140026986  push    rbx
0x140026987  push    rsi
0x140026988  push    rdi
0x140026989  push    r12
0x14002698b  push    r13
0x14002698d  push    r14
0x14002698f  push    r15
0x140026991  mov     rbp, rsp
0x140026994  sub     rsp, 48h
0x140026998  mov     rsi, [rbp+arg_28]
0x14002699c  xorps   xmm0, xmm0
0x14002699f  mov     rax, [rbp+arg_20]
0x1400269a3  mov     rdi, r8
0x1400269a6  mov     r13, rdx
0x1400269a9  movups  [rbp+var_18], xmm0
0x1400269ad  test    r9d, r9d
0x1400269b0  jnz     short loc_1400269BE
0x1400269b2  mov     word ptr [rbp+var_18], si
0x1400269b6  mov     word ptr [rbp+var_18+2], si
0x1400269ba  mov     qword ptr [rbp+var_18+8], rax
0x1400269be  test    ecx, ecx
0x1400269c0  jz      loc_140026A97
0x1400269c6  test    r9d, r9d
0x1400269c9  jz      loc_140026A8A
0x1400269cf  xor     r12d, r12d
0x1400269d2  mov     rdx, rdi
0x1400269d5  mov     rcx, rsi
0x1400269d8  test    rdi, rdi
0x1400269db  lea     ebx, [r12+1]
0x1400269e0  jmp     loc_140026A6C
0x1400269e5  test    rcx, rcx
0x1400269e8  jz      loc_140026A7A
0x1400269ee  movzx   r14d, byte ptr [r12+r13]
0x1400269f3  movzx   r15d, byte ptr [rax+r12]
0x1400269f8  cmp     r14w, r15w
0x1400269fc  jz      short loc_140026A60
0x1400269fe  cmp     r14d, 61h ; 'a'
0x140026a02  jb      short loc_140026A25
0x140026a04  cmp     r14d, 7Ah ; 'z'
0x140026a08  jbe     short loc_140026A20
0x140026a0a  movzx   ecx, r14w; Source
0x140026a0e  call    cs:__imp_RtlUpcaseUnicodeChar
0x140026a15  nop     dword ptr [rax+rax+00h]
0x140026a1a  movzx   r14d, ax
0x140026a1e  jmp     short loc_140026A25
0x140026a20  sub     r14w, 20h ; ' '
0x140026a25  cmp     r15d, 61h ; 'a'
0x140026a29  jb      short loc_140026A4C
0x140026a2b  cmp     r15d, 7Ah ; 'z'
0x140026a2f  jbe     short loc_140026A47
0x140026a31  movzx   ecx, r15w; Source
0x140026a35  call    cs:__imp_RtlUpcaseUnicodeChar
0x140026a3c  nop     dword ptr [rax+rax+00h]
0x140026a41  movzx   r15d, ax
0x140026a45  jmp     short loc_140026A4C
0x140026a47  sub     r15w, 20h ; ' '
0x140026a4c  cmp     r14w, r15w
0x140026a50  jb      short loc_140026A85
0x140026a52  ja      short loc_140026A81
0x140026a54  mov     rax, [rbp+arg_20]
0x140026a58  mov     rcx, qword ptr [rbp+var_18]
0x140026a5c  mov     rdx, [rbp+var_28]
0x140026a60  sub     rdx, rbx
0x140026a63  sub     rcx, rbx
0x140026a66  add     r12, rbx
0x140026a69  test    rdx, rdx
0x140026a6c  mov     qword ptr [rbp+var_18], rcx
0x140026a70  mov     [rbp+var_28], rdx
0x140026a74  jnz     loc_1400269E5
0x140026a7a  cmp     rdi, rsi
0x140026a7d  ja      short loc_140026A81
0x140026a7f  sbb     ebx, ebx
0x140026a81  mov     eax, ebx
0x140026a83  jmp     short loc_140026AC7
0x140026a85  or      ebx, 0FFFFFFFFh
0x140026a88  jmp     short loc_140026A81
0x140026a8a  lea     rcx, [rbp+var_18]
0x140026a8e  call    ORCompareCompressedString
0x140026a93  neg     eax
0x140026a95  jmp     short loc_140026AC7
0x140026a97  xor     ecx, ecx
0x140026a99  mov     word ptr [rbp+var_28], di
0x140026a9d  mov     dword ptr [rbp+var_28+4], ecx
0x140026aa0  lea     rcx, [rbp+var_28]
0x140026aa4  mov     word ptr [rbp+var_28+2], di
0x140026aa8  mov     [rbp+var_20], r13
0x140026aac  test    r9d, r9d
0x140026aaf  jz      short loc_140026ABE
0x140026ab1  mov     r8, rsi
0x140026ab4  mov     rdx, rax
0x140026ab7  call    ORCompareCompressedString
0x140026abc  jmp     short loc_140026AC7
0x140026abe  lea     rdx, [rbp+var_18]
0x140026ac2  call    ORCompareUnicodeString
0x140026ac7  add     rsp, 48h
0x140026acb  pop     r15
0x140026acd  pop     r14
0x140026acf  pop     r13
0x140026ad1  pop     r12
0x140026ad3  pop     rdi
0x140026ad4  pop     rsi
0x140026ad5  pop     rbx
0x140026ad6  pop     rbp
0x140026ad7  retn
```
