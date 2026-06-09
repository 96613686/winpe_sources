# RfspServerNameEqualDnsName

- ea: `0x140016ff8`
- end: `0x14001716d`
- name: `RfspServerNameEqualDnsName`
- size: `373`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140017f00`
- `0x140018520`
- `0x14001a8d0`
- `0x14001e980`

## callees

- `0x140016ff8`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14001706e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001706e`

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
0x140016ff8  push    rbp
0x140016ffa  mov     rbp, rsp
0x140016ffd  sub     rsp, 50h
0x140017001  movzx   r9d, word ptr [rdx+10h]
0x140017006  movzx   r10d, word ptr [rcx+10h]
0x14001700b  cmp     r10w, r9w
0x14001700f  jnz     short loc_14001707F
0x140017011  mov     rax, [rdx+18h]
0x140017015  cmp     [rcx+18h], rax
0x140017019  jnz     loc_140017164
0x14001701f  mov     rax, [rcx+8]
0x140017023  mov     [rbp+String2.Buffer], rax
0x140017027  mov     rax, [rdx+8]
0x14001702b  lea     rdx, [rbp+String2]; String2
0x14001702f  mov     dword ptr [rbp+String2+4], 0
0x140017036  mov     [rbp+String2.MaximumLength], r10w
0x14001703b  mov     [rbp+String2.Length], r10w
0x140017040  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x140017044  mov     [rbp+String2.Buffer], rax
0x140017048  mov     dword ptr [rbp+String2+4], 0
0x14001704f  mov     [rbp+String2.MaximumLength], r9w
0x140017054  mov     [rbp+String2.Length], r9w
0x140017059  movdqa  xmmword ptr [rbp+String1.Length], xmm0
0x14001705e  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x140017062  movdqa  xmmword ptr [rbp+String2.Length], xmm0
0x140017067  lea     rcx, [rbp+String1]; String1
0x14001706b  mov     r8b, 1; CaseInSensitive
0x14001706e  call    cs:__imp_RtlEqualUnicodeString
0x140017075  nop     dword ptr [rax+rax+00h]
0x14001707a  jmp     loc_140017166
0x14001707f  test    r8b, r8b
0x140017082  jnz     loc_140017164
0x140017088  cmp     r10w, r9w
0x14001708c  jnb     short loc_1400170FE
0x14001708e  movzx   r8d, word ptr [rcx+12h]
0x140017093  cmp     r8w, r10w
0x140017097  jnz     loc_140017164
0x14001709d  mov     rax, [rdx+20h]
0x1400170a1  cmp     [rcx+20h], rax
0x1400170a5  jnz     loc_140017164
0x1400170ab  mov     rax, [rcx+8]
0x1400170af  xorps   xmm1, xmm1
0x1400170b2  mov     [rbp+String2.Buffer], rax
0x1400170b6  lea     rcx, [rbp+var_10]
0x1400170ba  mov     rax, [rdx+8]
0x1400170be  mov     dword ptr [rbp+String2+4], 0
0x1400170c5  mov     [rbp+String2.MaximumLength], r8w
0x1400170ca  mov     [rbp+String2.Length], r8w
0x1400170cf  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x1400170d3  movups  xmmword ptr [rbp+String2.Length], xmm1
0x1400170d7  mov     [rbp+String2.Buffer], rax
0x1400170db  movzx   eax, word ptr [rdx+12h]
0x1400170df  lea     rdx, [rbp+String1]
0x1400170e3  mov     [rbp+String2.MaximumLength], ax
0x1400170e7  mov     [rbp+String2.Length], ax
0x1400170eb  movdqa  [rbp+var_10], xmm0
0x1400170f0  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x1400170f4  movdqa  xmmword ptr [rbp+String1.Length], xmm0
0x1400170f9  jmp     loc_14001706B
0x1400170fe  jbe     short loc_140017164
0x140017100  movzx   r8d, word ptr [rdx+12h]
0x140017105  cmp     r8w, r9w
0x140017109  jnz     short loc_140017164
0x14001710b  mov     rax, [rdx+20h]
0x14001710f  cmp     [rcx+20h], rax
0x140017113  jnz     short loc_140017164
0x140017115  mov     rax, [rcx+8]
0x140017119  xorps   xmm0, xmm0
0x14001711c  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140017120  mov     [rbp+String2.Buffer], rax
0x140017124  movzx   eax, word ptr [rcx+12h]
0x140017128  mov     [rbp+String2.MaximumLength], ax
0x14001712c  mov     [rbp+String2.Length], ax
0x140017130  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x140017134  mov     rax, [rdx+8]
0x140017138  lea     rdx, [rbp+var_10]
0x14001713c  movdqa  xmmword ptr [rbp+String1.Length], xmm0
0x140017141  mov     [rbp+String2.Buffer], rax
0x140017145  mov     dword ptr [rbp+String2+4], 0
0x14001714c  mov     [rbp+String2.MaximumLength], r8w
0x140017151  mov     [rbp+String2.Length], r8w
0x140017156  movaps  xmm0, xmmword ptr [rbp+String2.Length]
0x14001715a  movdqa  [rbp+var_10], xmm0
0x14001715f  jmp     loc_140017067
0x140017164  xor     al, al
0x140017166  add     rsp, 50h
0x14001716a  pop     rbp
0x14001716b  retn
```
