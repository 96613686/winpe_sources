# DfscReferralGetClientInfoMarshall

- ea: `0x140018d44`
- end: `0x1400191c7`
- name: `DfscReferralGetClientInfoMarshall`
- size: `1155`
- prototype: `__int64 __fastcall(__int64, const void **, int, char, __int64, __int64, char *, size_t Size)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140015520`

## callees

- `0x140006080`
- `0x140006380`
- `0x140018bb0`
- `0x140018d44`
- `0x140020fd0`
- `0x140021820`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140018f7f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018fa8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018fd1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018f7f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018fa8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140018fd1`

## pseudocode

```c
__int64 __fastcall DfscReferralGetClientInfoMarshall(
        __int64 a1,
        const void **a2,
        int a3,
        char a4,
        __int64 a5,
        __int64 a6,
        char *a7,
        size_t Size)
{
  unsigned int *v9; // rbx
  char *v11; // rsi
  size_t v12; // r8
  __int64 v13; // r13
  unsigned int v14; // edi
  __int64 v15; // rdx
  __int64 v16; // r8
  const UNICODE_STRING *v17; // r9
  unsigned int v18; // r13d
  int v19; // ecx
  const UNICODE_STRING *CurrentTarget; // rax
  __int16 v21; // r10
  LONG v22; // eax
  LONG v23; // eax
  _DWORD *v24; // rdx
  char *v25; // r8
  size_t Length; // r8
  unsigned int v27; // edi
  size_t v28; // r8
  int v29; // eax
  __int64 v30; // r10
  int v32; // r15d
  _DWORD *v33; // [rsp+30h] [rbp-50h]
  char *v34; // [rsp+38h] [rbp-48h]
  const UNICODE_STRING *v35; // [rsp+40h] [rbp-40h]
  UNICODE_STRING String1; // [rsp+50h] [rbp-30h] BYREF
  UNICODE_STRING v37; // [rsp+60h] [rbp-20h] BYREF
  UNICODE_STRING v38; // [rsp+70h] [rbp-10h] BYREF

  v9 = 0;
  v34 = 0;
  v33 = 0;
  v38 = 0;
  String1 = 0;
  v37 = 0;
  memset(a7, 0, (unsigned int)Size);
  if ( !a4 )
  {
    if ( (a3 != 4 || (unsigned int)Size >= 0x50) && (a3 != 3 || (unsigned int)Size >= 0x38) )
    {
      v11 = a7;
      if ( (unsigned int)(a3 - 1) > 1 || (unsigned int)Size >= 0x20 )
        goto LABEL_15;
    }
    return 2147483653LL;
  }
  if ( a3 == 4 && (unsigned int)Size < 0x34
    || a3 == 3 && (unsigned int)Size < 0x20
    || (unsigned int)(a3 - 1) <= 1 && (unsigned int)Size < 0x14 )
  {
    return 2147483653LL;
  }
  v11 = 0;
  v9 = (unsigned int *)a7;
LABEL_15:
  v12 = *(unsigned __int16 *)a2;
  v13 = *(_QWORD *)(a1 + 16);
  v14 = Size - v12 - 2;
  memmove(&a7[v14], a2[1], v12);
  switch ( a3 )
  {
    case 1:
      if ( a4 )
        *v9 = v14;
      else
        *(_QWORD *)v11 = v14;
      return 0;
    case 2:
      if ( a4 )
      {
        *v9 = v14;
        v9[1] = 0;
        v9[2] = 1;
        v9[3] = *(unsigned __int16 *)(v13 + 24);
      }
      else
      {
        *(_QWORD *)v11 = v14;
        *((_QWORD *)v11 + 1) = 0;
        *((_DWORD *)v11 + 4) = 1;
        *((_DWORD *)v11 + 5) = *(unsigned __int16 *)(v13 + 24);
      }
      return 0;
    case 3:
      if ( a4 )
      {
        *v9 = v14;
        v9[1] = 0;
        v9[2] = 1;
        v9[3] = *(unsigned __int16 *)(v13 + 24);
        v33 = v9 + 5;
        v9[4] = (_DWORD)v9 + 20 - (_DWORD)a7;
      }
      else
      {
        *(_QWORD *)v11 = v14;
        *((_QWORD *)v11 + 1) = 0;
        *((_DWORD *)v11 + 4) = 1;
        *((_DWORD *)v11 + 5) = *(unsigned __int16 *)(v13 + 24);
        v34 = v11 + 32;
        *((_QWORD *)v11 + 3) = (unsigned int)((_DWORD)v11 + 32 - (_DWORD)a7);
      }
      break;
    case 4:
      if ( a4 )
      {
        *v9 = v14;
        v9[1] = 0;
        v9[2] = 1;
        v9[3] = *(_DWORD *)(v13 + 40);
        v9[8] = *(unsigned __int16 *)(v13 + 24);
        v33 = v9 + 10;
        v9[9] = (_DWORD)v9 + 40 - (_DWORD)a7;
      }
      else
      {
        *(_QWORD *)v11 = v14;
        *((_QWORD *)v11 + 1) = 0;
        *((_DWORD *)v11 + 4) = 1;
        *((_DWORD *)v11 + 5) = *(_DWORD *)(v13 + 40);
        *((_DWORD *)v11 + 10) = *(unsigned __int16 *)(v13 + 24);
        v34 = v11 + 56;
        *((_QWORD *)v11 + 6) = (unsigned int)((_DWORD)v11 + 56 - (_DWORD)a7);
      }
      break;
    default:
      if ( (unsigned int)(a3 - 3) > 1 )
        return 0;
      break;
  }
  *(_WORD *)(a1 + 32) = -1;
  DfscCleanupGetClientInfoParameters(a5, a6, (unsigned int)&String1, (unsigned int)&v37, (__int64)&v38);
  v18 = 0;
  while ( 1 )
  {
    v19 = DfscReferralIterate(a1, v15, v16, v17);
    if ( v19 < 0 )
      break;
    CurrentTarget = (const UNICODE_STRING *)DfscReferralGetCurrentTarget(a1);
    v35 = CurrentTarget;
    if ( String1.Length == v21 )
    {
LABEL_32:
      if ( v37.Length == v21 || (v23 = RtlCompareUnicodeString(&v37, CurrentTarget + 2, 1u), v21 = 0, !v23) )
      {
        if ( v38.Length == v21 || !RtlCompareUnicodeString(&v38, v35 + 3, 1u) )
        {
          if ( a4 )
          {
            v24 = v33;
            *v33 = 2;
            if ( (unsigned int)Size < (unsigned __int64)((char *)v33 - a7 + 12) )
              return 2147483653LL;
            v25 = v34;
          }
          else
          {
            v25 = v34;
            if ( (unsigned int)Size < (unsigned __int64)(v34 - a7 + 24) )
              return 2147483653LL;
            v24 = v33;
            *(_DWORD *)v34 = 2;
          }
          if ( *(_WORD *)(a1 + 32) == *(_WORD *)(a1 + 26) )
          {
            if ( a4 )
              *v24 |= 4u;
            else
              *(_DWORD *)v25 |= 4u;
          }
          Length = v35[1].Length;
          v27 = v14 - Length - 2;
          memmove(&a7[v27], v35[1].Buffer, Length);
          if ( a4 )
            v33[1] = v27;
          else
            *((_QWORD *)v34 + 1) = v27;
          v28 = v35[2].Length;
          v29 = v35[3].Length;
          v14 = v27 - v28 - 2;
          if ( (_WORD)v29 )
            v14 = v14 - v29 - 2;
          memmove(&a7[v14], v35[2].Buffer, v28);
          v17 = v35;
          if ( v35[3].Length )
          {
            v30 = v14 + v35[2].Length;
            if ( (unsigned int)Size < (unsigned __int64)(v30 + 2) )
              return 2147483653LL;
            *(_WORD *)&a7[(v14 + v35[2].Length) & 0xFFFFFFFE] = 92;
            memmove(&a7[(unsigned int)(v30 + 2)], v35[3].Buffer, v35[3].Length);
          }
          if ( a4 )
          {
            v33[2] = v14;
            v33 += 3;
          }
          else
          {
            *((_QWORD *)v34 + 2) = v14;
            v34 += 24;
          }
          ++v18;
        }
      }
    }
    else
    {
      v22 = RtlCompareUnicodeString(&String1, CurrentTarget + 1, 1u);
      v21 = 0;
      if ( !v22 )
      {
        CurrentTarget = v35;
        goto LABEL_32;
      }
    }
  }
  if ( v19 == -2147483622 )
    v19 = 0;
  v32 = a3 - 3;
  if ( v32 )
  {
    if ( v32 == 1 )
    {
      if ( a4 )
        v9[8] = v18;
      else
        *((_DWORD *)v11 + 10) = v18;
    }
  }
  else if ( a4 )
  {
    v9[3] = v18;
  }
  else
  {
    *((_DWORD *)v11 + 5) = v18;
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x140018d44  mov     [rsp-38h+arg_10], rbx
0x140018d49  mov     [rsp-38h+arg_8], rdx
0x140018d4e  mov     [rsp-38h+arg_0], rcx
0x140018d53  push    rbp
0x140018d54  push    rsi
0x140018d55  push    rdi
0x140018d56  push    r12
0x140018d58  push    r13
0x140018d5a  push    r14
0x140018d5c  push    r15
0x140018d5e  mov     rbp, rsp
0x140018d61  sub     rsp, 80h
0x140018d68  mov     edi, dword ptr [rbp+Size]
0x140018d6b  xorps   xmm0, xmm0
0x140018d6e  mov     r13, [rbp+arg_30]
0x140018d72  mov     r15d, r8d
0x140018d75  xor     ebx, ebx
0x140018d77  mov     [rbp+var_38], rdi
0x140018d7b  xorps   xmm1, xmm1
0x140018d7e  mov     [rbp+var_48], rbx
0x140018d82  mov     r8d, edi; Size
0x140018d85  mov     [rbp+var_50], rbx
0x140018d89  mov     rcx, r13; void *
0x140018d8c  xor     edx, edx; Val
0x140018d8e  mov     r12b, r9b
0x140018d91  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x140018d95  movups  xmmword ptr [rbp+String1.Length], xmm1
0x140018d99  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140018d9d  call    memset
0x140018da2  test    r12b, r12b
0x140018da5  jz      short loc_140018DE5
0x140018da7  cmp     r15d, 4
0x140018dab  jnz     short loc_140018DB6
0x140018dad  cmp     edi, 34h ; '4'
0x140018db0  jb      loc_140019129
0x140018db6  cmp     r15d, 3
0x140018dba  jnz     short loc_140018DC5
0x140018dbc  cmp     edi, 20h ; ' '
0x140018dbf  jb      loc_140019129
0x140018dc5  lea     eax, [r15-1]
0x140018dc9  mov     r14d, 1
0x140018dcf  cmp     eax, r14d
0x140018dd2  ja      short loc_140018DDD
0x140018dd4  cmp     edi, 14h
0x140018dd7  jb      loc_140019129
0x140018ddd  mov     rsi, rbx
0x140018de0  mov     rbx, r13
0x140018de3  jmp     short loc_140018E1E
0x140018de5  cmp     r15d, 4
0x140018de9  jnz     short loc_140018DF4
0x140018deb  cmp     edi, 50h ; 'P'
0x140018dee  jb      loc_140019129
0x140018df4  cmp     r15d, 3
0x140018df8  jnz     short loc_140018E03
0x140018dfa  cmp     edi, 38h ; '8'
0x140018dfd  jb      loc_140019129
0x140018e03  lea     eax, [r15-1]
0x140018e07  mov     r14d, 1
0x140018e0d  mov     rsi, r13
0x140018e10  cmp     eax, r14d
0x140018e13  ja      short loc_140018E1E
0x140018e15  cmp     edi, 20h ; ' '
0x140018e18  jb      loc_140019129
0x140018e1e  mov     rdx, [rbp+arg_8]
0x140018e22  mov     r13, [rbp+arg_0]
0x140018e26  mov     rcx, [rbp+arg_30]
0x140018e2a  movzx   r8d, word ptr [rdx]; Size
0x140018e2e  mov     rdx, [rdx+8]; Src
0x140018e32  sub     edi, r8d
0x140018e35  mov     r13, [r13+10h]
0x140018e39  sub     edi, 2
0x140018e3c  mov     eax, edi
0x140018e3e  add     rcx, rax; void *
0x140018e41  call    memmove
0x140018e46  mov     eax, r15d
0x140018e49  sub     eax, 1
0x140018e4c  jz      loc_14001919B
0x140018e52  sub     eax, 1
0x140018e55  jz      loc_14001916A
0x140018e5b  sub     eax, 1
0x140018e5e  jz      short loc_140018ED3
0x140018e60  cmp     eax, 1
0x140018e63  jz      short loc_140018E77
0x140018e65  lea     eax, [r15-3]
0x140018e69  cmp     eax, r14d
0x140018e6c  jbe     loc_140018F1F
0x140018e72  jmp     loc_1400191A9
0x140018e77  xor     ecx, ecx
0x140018e79  test    r12b, r12b
0x140018e7c  jz      short loc_140018EA6
0x140018e7e  mov     [rbx], edi
0x140018e80  mov     [rbx+4], ecx
0x140018e83  mov     [rbx+8], r14d
0x140018e87  mov     eax, [r13+28h]
0x140018e8b  mov     [rbx+0Ch], eax
0x140018e8e  movzx   eax, word ptr [r13+18h]
0x140018e93  mov     [rbx+20h], eax
0x140018e96  lea     rax, [rbx+28h]
0x140018e9a  mov     [rbp+var_50], rax
0x140018e9e  sub     eax, dword ptr [rbp+arg_30]
0x140018ea1  mov     [rbx+24h], eax
0x140018ea4  jmp     short loc_140018F1F
0x140018ea6  mov     eax, edi
0x140018ea8  mov     [rsi], rax
0x140018eab  mov     [rsi+8], rcx
0x140018eaf  mov     [rsi+10h], r14d
0x140018eb3  mov     eax, [r13+28h]
0x140018eb7  mov     [rsi+14h], eax
0x140018eba  movzx   eax, word ptr [r13+18h]
0x140018ebf  mov     [rsi+28h], eax
0x140018ec2  lea     rax, [rsi+38h]
0x140018ec6  mov     [rbp+var_48], rax
0x140018eca  sub     eax, dword ptr [rbp+arg_30]
0x140018ecd  mov     [rsi+30h], rax
0x140018ed1  jmp     short loc_140018F1F
0x140018ed3  xor     ecx, ecx
0x140018ed5  test    r12b, r12b
0x140018ed8  jz      short loc_140018EFB
0x140018eda  mov     [rbx], edi
0x140018edc  mov     [rbx+4], ecx
0x140018edf  mov     [rbx+8], r14d
0x140018ee3  movzx   eax, word ptr [r13+18h]
0x140018ee8  mov     [rbx+0Ch], eax
0x140018eeb  lea     rax, [rbx+14h]
0x140018eef  mov     [rbp+var_50], rax
0x140018ef3  sub     eax, dword ptr [rbp+arg_30]
0x140018ef6  mov     [rbx+10h], eax
0x140018ef9  jmp     short loc_140018F1F
0x140018efb  mov     eax, edi
0x140018efd  mov     [rsi], rax
0x140018f00  mov     [rsi+8], rcx
0x140018f04  mov     [rsi+10h], r14d
0x140018f08  movzx   eax, word ptr [r13+18h]
0x140018f0d  mov     [rsi+14h], eax
0x140018f10  lea     rax, [rsi+20h]
0x140018f14  mov     [rbp+var_48], rax
0x140018f18  sub     eax, dword ptr [rbp+arg_30]
0x140018f1b  mov     [rsi+18h], rax
0x140018f1f  mov     rax, [rbp+arg_0]
0x140018f23  lea     r9, [rbp+var_20]
0x140018f27  mov     rdx, [rbp+arg_28]
0x140018f2b  lea     r8, [rbp+String1]
0x140018f2f  mov     rcx, [rbp+arg_20]
0x140018f33  mov     word ptr [rax+20h], 0FFFFh
0x140018f39  lea     rax, [rbp+var_10]
0x140018f3d  mov     [rsp+80h+var_60], rax
0x140018f42  call    DfscCleanupGetClientInfoParameters
0x140018f47  xor     r13d, r13d
0x140018f4a  mov     rcx, [rbp+arg_0]
0x140018f4e  call    DfscReferralIterate
0x140018f53  xor     r10d, r10d
0x140018f56  mov     ecx, eax
0x140018f58  test    eax, eax
0x140018f5a  js      loc_140019130
0x140018f60  mov     rcx, [rbp+arg_0]
0x140018f64  call    DfscReferralGetCurrentTarget
0x140018f69  mov     [rbp+var_40], rax
0x140018f6d  cmp     [rbp+String1.Length], r10w
0x140018f72  jz      short loc_140018F96
0x140018f74  lea     rdx, [rax+10h]; String2
0x140018f78  mov     r8b, r14b; CaseInSensitive
0x140018f7b  lea     rcx, [rbp+String1]; String1
0x140018f7f  call    cs:__imp_RtlCompareUnicodeString
0x140018f86  nop     dword ptr [rax+rax+00h]
0x140018f8b  xor     r10d, r10d
0x140018f8e  test    eax, eax
0x140018f90  jnz     short loc_140018F4A
0x140018f92  mov     rax, [rbp+var_40]
0x140018f96  cmp     [rbp+var_20.Length], r10w
0x140018f9b  jz      short loc_140018FBB
0x140018f9d  lea     rdx, [rax+20h]; String2
0x140018fa1  mov     r8b, r14b; CaseInSensitive
0x140018fa4  lea     rcx, [rbp+var_20]; String1
0x140018fa8  call    cs:__imp_RtlCompareUnicodeString
0x140018faf  nop     dword ptr [rax+rax+00h]
0x140018fb4  xor     r10d, r10d
0x140018fb7  test    eax, eax
0x140018fb9  jnz     short loc_140018F4A
0x140018fbb  cmp     [rbp+var_10.Length], r10w
0x140018fc0  jz      short loc_140018FE5
0x140018fc2  mov     rdx, [rbp+var_40]
0x140018fc6  lea     rcx, [rbp+var_10]; String1
0x140018fca  add     rdx, 30h ; '0'; String2
0x140018fce  mov     r8b, r14b; CaseInSensitive
0x140018fd1  call    cs:__imp_RtlCompareUnicodeString
0x140018fd8  nop     dword ptr [rax+rax+00h]
0x140018fdd  test    eax, eax
0x140018fdf  jnz     loc_140018F4A
0x140018fe5  mov     rcx, [rbp+arg_30]
0x140018fe9  test    r12b, r12b
0x140018fec  jz      short loc_140019012
0x140018fee  mov     rdx, [rbp+var_50]
0x140018ff2  mov     rax, rdx
0x140018ff5  sub     rax, rcx
0x140018ff8  add     rax, 0Ch
0x140018ffc  mov     dword ptr [rdx], 2
0x140019002  cmp     [rbp+var_38], rax
0x140019006  jb      loc_140019129
0x14001900c  mov     r8, [rbp+var_48]
0x140019010  jmp     short loc_140019035
0x140019012  mov     r8, [rbp+var_48]
0x140019016  mov     rax, r8
0x140019019  sub     rax, rcx
0x14001901c  add     rax, 18h
0x140019020  cmp     [rbp+var_38], rax
0x140019024  jb      loc_140019129
0x14001902a  mov     rdx, [rbp+var_50]
0x14001902e  mov     dword ptr [r8], 2
0x140019035  mov     r9, [rbp+arg_0]
0x140019039  movzx   eax, word ptr [r9+1Ah]
0x14001903e  cmp     [r9+20h], ax
0x140019043  jnz     short loc_140019053
0x140019045  test    r12b, r12b
0x140019048  jz      short loc_14001904F
0x14001904a  or      dword ptr [rdx], 4
0x14001904d  jmp     short loc_140019053
0x14001904f  or      dword ptr [r8], 4
0x140019053  mov     rax, [rbp+var_40]
0x140019057  movzx   r8d, word ptr [rax+10h]; Size
0x14001905c  sub     edi, r8d
0x14001905f  add     edi, 0FFFFFFFEh
0x140019062  mov     edx, edi
0x140019064  add     rcx, rdx; void *
0x140019067  mov     rdx, [rax+18h]; Src
0x14001906b  call    memmove
0x140019070  test    r12b, r12b
0x140019073  jz      short loc_14001907E
0x140019075  mov     rax, [rbp+var_50]
0x140019079  mov     [rax+4], edi
0x14001907c  jmp     short loc_140019088
0x14001907e  mov     rax, [rbp+var_48]
0x140019082  mov     ecx, edi
0x140019084  mov     [rax+8], rcx
0x140019088  mov     rdx, [rbp+var_40]
0x14001908c  movzx   r8d, word ptr [rdx+20h]; Size
0x140019091  movzx   eax, word ptr [rdx+30h]
0x140019095  sub     edi, r8d
0x140019098  add     edi, 0FFFFFFFEh
0x14001909b  test    ax, ax
0x14001909e  jz      short loc_1400190A5
0x1400190a0  sub     edi, eax
0x1400190a2  sub     edi, 2
0x1400190a5  mov     rdx, [rdx+28h]; Src
0x1400190a9  mov     ecx, edi
0x1400190ab  add     rcx, [rbp+arg_30]; void *
0x1400190af  call    memmove
0x1400190b4  mov     r9, [rbp+var_40]
0x1400190b8  xor     eax, eax
0x1400190ba  cmp     [r9+30h], ax
0x1400190bf  jz      short loc_1400190F9
0x1400190c1  movzx   r10d, word ptr [r9+20h]
0x1400190c6  add     r10d, edi
0x1400190c9  mov     ecx, r10d
0x1400190cc  lea     rax, [r10+2]
0x1400190d0  cmp     [rbp+var_38], rax
0x1400190d4  jb      short loc_140019129
0x1400190d6  mov     rdx, [rbp+arg_30]
0x1400190da  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1400190de  mov     word ptr [rcx+rdx], 5Ch ; '\'
0x1400190e4  lea     ecx, [r10+2]
0x1400190e8  movzx   r8d, word ptr [r9+30h]; Size
0x1400190ed  add     rcx, rdx; void *
0x1400190f0  mov     rdx, [r9+38h]; Src
0x1400190f4  call    memmove
0x1400190f9  test    r12b, r12b
0x1400190fc  jz      short loc_14001910F
0x1400190fe  mov     rax, [rbp+var_50]
0x140019102  mov     [rax+8], edi
0x140019105  add     rax, 0Ch
0x140019109  mov     [rbp+var_50], rax
0x14001910d  jmp     short loc_140019121
0x14001910f  mov     rax, [rbp+var_48]
0x140019113  mov     ecx, edi
0x140019115  mov     [rax+10h], rcx
0x140019119  add     rax, 18h
0x14001911d  mov     [rbp+var_48], rax
0x140019121  add     r13d, r14d
0x140019124  jmp     loc_140018F4A
0x140019129  mov     eax, 80000005h
0x14001912e  jmp     short loc_1400191AB
0x140019130  cmp     ecx, 8000001Ah
0x140019136  cmovz   ecx, r10d
0x14001913a  sub     r15d, 3
0x14001913e  jz      short loc_140019157
0x140019140  cmp     r15d, 1
0x140019144  jnz     short loc_140019166
0x140019146  test    r12b, r12b
0x140019149  jz      short loc_140019151
0x14001914b  mov     [rbx+20h], r13d
0x14001914f  jmp     short loc_140019166
0x140019151  mov     [rsi+28h], r13d
0x140019155  jmp     short loc_140019166
0x140019157  test    r12b, r12b
0x14001915a  jz      short loc_140019162
0x14001915c  mov     [rbx+0Ch], r13d
0x140019160  jmp     short loc_140019166
0x140019162  mov     [rsi+14h], r13d
0x140019166  mov     eax, ecx
0x140019168  jmp     short loc_1400191AB
0x14001916a  xor     ecx, ecx
  ... truncated ...
```
