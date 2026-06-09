# RfspServerNameEqualDnsName

- ea: `0x140017048`
- end: `0x1400171bd`
- name: `RfspServerNameEqualDnsName`
- size: `373`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140017f50`
- `0x140018570`
- `0x14001a920`
- `0x14001e9d0`

## callees

- `0x140017048`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1400170be`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400170be`

## pseudocode

```c
BOOLEAN __fastcall RfspServerNameEqualDnsName(__int64 a1, __int64 a2, char a3)
{
  USHORT v3; // r9
  USHORT v4; // r10
  WCHAR *v5; // rax
  UNICODE_STRING *p_String2; // rdx
  UNICODE_STRING v7; // xmm0
  UNICODE_STRING *p_String1; // rcx
  USHORT v10; // r8
  WCHAR *v11; // rax
  UNICODE_STRING v12; // xmm0
  USHORT v13; // r8
  WCHAR *v14; // rax
  WCHAR *v15; // rax
  UNICODE_STRING String2; // [rsp+20h] [rbp-30h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING v18; // [rsp+40h] [rbp-10h] BYREF

  v3 = *(_WORD *)(a2 + 16);
  v4 = *(_WORD *)(a1 + 16);
  if ( v4 == v3 )
  {
    if ( *(_QWORD *)(a1 + 24) == *(_QWORD *)(a2 + 24) )
    {
      String2.Buffer = *(PWSTR *)(a1 + 8);
      v5 = *(WCHAR **)(a2 + 8);
      p_String2 = &String2;
      *(_DWORD *)(&String2.MaximumLength + 1) = 0;
      String2.MaximumLength = v4;
      String2.Length = v4;
      v7 = String2;
      String2.Buffer = v5;
      *(_DWORD *)(&String2.MaximumLength + 1) = 0;
      String2.MaximumLength = v3;
      String2.Length = v3;
      String1 = v7;
LABEL_4:
      p_String1 = &String1;
      return RtlEqualUnicodeString(p_String1, p_String2, 1u);
    }
  }
  else if ( !a3 )
  {
    if ( v4 >= v3 )
    {
      if ( v4 > v3 )
      {
        v13 = *(_WORD *)(a2 + 18);
        if ( v13 == v3 && *(_QWORD *)(a1 + 32) == *(_QWORD *)(a2 + 32) )
        {
          v14 = *(WCHAR **)(a1 + 8);
          *(_QWORD *)&String2.Length = 0;
          String2.Buffer = v14;
          String2.MaximumLength = *(_WORD *)(a1 + 18);
          String2.Length = String2.MaximumLength;
          v15 = *(WCHAR **)(a2 + 8);
          p_String2 = &v18;
          String1 = String2;
          String2.Buffer = v15;
          String2.MaximumLength = v13;
          String2.Length = v13;
          v18 = String2;
          goto LABEL_4;
        }
      }
    }
    else
    {
      v10 = *(_WORD *)(a1 + 18);
      if ( v10 == v4 && *(_QWORD *)(a1 + 32) == *(_QWORD *)(a2 + 32) )
      {
        String2.Buffer = *(PWSTR *)(a1 + 8);
        p_String1 = &v18;
        v11 = *(WCHAR **)(a2 + 8);
        *(_DWORD *)(&String2.MaximumLength + 1) = 0;
        String2.MaximumLength = v10;
        String2.Length = v10;
        v12 = String2;
        *(_QWORD *)&String2.Length = 0;
        String2.Buffer = v11;
        LOWORD(v11) = *(_WORD *)(a2 + 18);
        p_String2 = &String1;
        String2.MaximumLength = (unsigned __int16)v11;
        String2.Length = (unsigned __int16)v11;
        v18 = v12;
        String1 = String2;
        return RtlEqualUnicodeString(p_String1, p_String2, 1u);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140017048  push    rbp
0x14001704a  mov     rbp, rsp
0x14001704d  sub     rsp, 50h
0x140017051  movzx   r9d, word ptr [rdx+10h]
0x140017056  movzx   r10d, word ptr [rcx+10h]
0x14001705b  cmp     r10w, r9w
0x14001705f  jnz     short loc_1400170CF
0x140017061  mov     rax, [rdx+18h]
0x140017065  cmp     [rcx+18h], rax
0x140017069  jnz     loc_1400171B4
0x14001706f  mov     rax, [rcx+8]
0x140017073  mov     [rbp+String2.Buffer], rax
0x140017077  mov     rax, [rdx+8]
0x14001707b  lea     rdx, [rbp+String2]; String2
0x14001707f  mov     dword ptr [rbp+String2+4], 0
0x140017086  mov     [rbp+String2.MaximumLength], r10w
0x14001708b  mov     [rbp+String2.Length], r10w
0x140017090  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x140017094  mov     [rbp+String2.Buffer], rax
0x140017098  mov     dword ptr [rbp+String2+4], 0
0x14001709f  mov     [rbp+String2.MaximumLength], r9w
0x1400170a4  mov     [rbp+String2.Length], r9w
0x1400170a9  movdqa  xmmword ptr [rbp+String1.Length], xmm0
0x1400170ae  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x1400170b2  movdqa  xmmword ptr [rbp+String2.Length], xmm0
0x1400170b7  lea     rcx, [rbp+String1]; String1
0x1400170bb  mov     r8b, 1; CaseInSensitive
0x1400170be  call    cs:__imp_RtlEqualUnicodeString
0x1400170c5  nop     dword ptr [rax+rax+00h]
0x1400170ca  jmp     loc_1400171B6
0x1400170cf  test    r8b, r8b
0x1400170d2  jnz     loc_1400171B4
0x1400170d8  cmp     r10w, r9w
0x1400170dc  jnb     short loc_14001714E
0x1400170de  movzx   r8d, word ptr [rcx+12h]
0x1400170e3  cmp     r8w, r10w
0x1400170e7  jnz     loc_1400171B4
0x1400170ed  mov     rax, [rdx+20h]
0x1400170f1  cmp     [rcx+20h], rax
0x1400170f5  jnz     loc_1400171B4
0x1400170fb  mov     rax, [rcx+8]
0x1400170ff  xorps   xmm1, xmm1
0x140017102  mov     [rbp+String2.Buffer], rax
0x140017106  lea     rcx, [rbp+var_10]
0x14001710a  mov     rax, [rdx+8]
0x14001710e  mov     dword ptr [rbp+String2+4], 0
0x140017115  mov     [rbp+String2.MaximumLength], r8w
0x14001711a  mov     [rbp+String2.Length], r8w
0x14001711f  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x140017123  movups  xmmword ptr [rbp+String2.Length], xmm1
0x140017127  mov     [rbp+String2.Buffer], rax
0x14001712b  movzx   eax, word ptr [rdx+12h]
0x14001712f  lea     rdx, [rbp+String1]
0x140017133  mov     [rbp+String2.MaximumLength], ax
0x140017137  mov     [rbp+String2.Length], ax
0x14001713b  movdqa  [rbp+var_10], xmm0
0x140017140  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x140017144  movdqa  xmmword ptr [rbp+String1.Length], xmm0
0x140017149  jmp     loc_1400170BB
0x14001714e  jbe     short loc_1400171B4
0x140017150  movzx   r8d, word ptr [rdx+12h]
0x140017155  cmp     r8w, r9w
0x140017159  jnz     short loc_1400171B4
0x14001715b  mov     rax, [rdx+20h]
0x14001715f  cmp     [rcx+20h], rax
0x140017163  jnz     short loc_1400171B4
0x140017165  mov     rax, [rcx+8]
0x140017169  xorps   xmm0, xmm0
0x14001716c  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140017170  mov     [rbp+String2.Buffer], rax
0x140017174  movzx   eax, word ptr [rcx+12h]
0x140017178  mov     [rbp+String2.MaximumLength], ax
0x14001717c  mov     [rbp+String2.Length], ax
0x140017180  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x140017184  mov     rax, [rdx+8]
0x140017188  lea     rdx, [rbp+var_10]
0x14001718c  movdqa  xmmword ptr [rbp+String1.Length], xmm0
0x140017191  mov     [rbp+String2.Buffer], rax
0x140017195  mov     dword ptr [rbp+String2+4], 0
0x14001719c  mov     [rbp+String2.MaximumLength], r8w
0x1400171a1  mov     [rbp+String2.Length], r8w
0x1400171a6  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x1400171aa  movdqa  [rbp+var_10], xmm0
0x1400171af  jmp     loc_1400170B7
0x1400171b4  xor     al, al
0x1400171b6  add     rsp, 50h
0x1400171ba  pop     rbp
0x1400171bb  retn
```
