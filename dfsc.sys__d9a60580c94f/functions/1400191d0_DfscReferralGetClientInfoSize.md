# DfscReferralGetClientInfoSize

- ea: `0x1400191d0`
- end: `0x140019356`
- name: `DfscReferralGetClientInfoSize`
- size: `390`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, int, char, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140015520`

## callees

- `0x140018bb0`
- `0x1400191d0`
- `0x140020fd0`
- `0x140021820`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14001929c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400192bd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400192de`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001929c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400192bd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400192de`

## pseudocode

```c
__int64 __fastcall DfscReferralGetClientInfoSize(
        __int64 a1,
        unsigned __int16 *a2,
        int a3,
        char a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  int v7; // ebx
  int v10; // ecx
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  unsigned int v16; // edi
  const UNICODE_STRING *CurrentTarget; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  const UNICODE_STRING *v21; // r14
  int v22; // ebx
  __int64 result; // rax
  UNICODE_STRING String1; // [rsp+30h] [rbp-38h] BYREF
  UNICODE_STRING v25; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING v26; // [rsp+50h] [rbp-18h] BYREF

  v7 = *a2 + 2;
  v26 = 0;
  String1 = 0;
  v25 = 0;
  if ( a3 == 1 )
  {
    if ( a4 )
      v7 += 4;
    else
      v7 += 8;
    goto LABEL_26;
  }
  if ( a3 == 2 )
  {
    v7 += a4 != 0 ? 16 : 24;
    goto LABEL_26;
  }
  if ( a3 != 3 )
  {
    if ( a3 == 4 )
    {
      v10 = a4 != 0 ? 40 : 56;
      goto LABEL_7;
    }
LABEL_26:
    *a7 = v7;
    return 0;
  }
  v10 = a4 != 0 ? 20 : 32;
LABEL_7:
  v11 = v10 + v7;
  *(_WORD *)(a1 + 32) = -1;
  DfscCleanupGetClientInfoParameters(a5, a6, (unsigned int)&String1, (unsigned int)&v25, (__int64)&v26);
  v15 = DfscReferralIterate(a1, v12, v13, v14);
  v16 = 0;
  while ( v15 >= 0 )
  {
    CurrentTarget = (const UNICODE_STRING *)DfscReferralGetCurrentTarget(a1);
    v21 = CurrentTarget;
    if ( (!String1.Length || !RtlCompareUnicodeString(&String1, CurrentTarget + 1, 1u))
      && (!v25.Length || !RtlCompareUnicodeString(&v25, v21 + 2, 1u))
      && (!v26.Length || !RtlCompareUnicodeString(&v26, v21 + 3, 1u)) )
    {
      v22 = v21[6].Length + v11;
      if ( a4 )
        v11 = v22 + 14;
      else
        v11 = v22 + 26;
    }
    v15 = DfscReferralIterate(a1, v18, v19, v20);
  }
  if ( v15 != -2147483622 )
    v16 = v15;
  result = v16;
  *a7 = v11;
  return result;
}

```

## disassembly

```asm
0x1400191d0  push    rbp
0x1400191d2  push    rbx
0x1400191d3  push    rsi
0x1400191d4  push    rdi
0x1400191d5  push    r14
0x1400191d7  push    r15
0x1400191d9  mov     rbp, rsp
0x1400191dc  sub     rsp, 68h
0x1400191e0  movzx   ebx, word ptr [rdx]
0x1400191e3  xorps   xmm0, xmm0
0x1400191e6  add     ebx, 2
0x1400191e9  mov     eax, r8d
0x1400191ec  xorps   xmm1, xmm1
0x1400191ef  mov     sil, r9b
0x1400191f2  mov     r15, rcx
0x1400191f5  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x1400191f9  movups  xmmword ptr [rbp+String1.Length], xmm1
0x1400191fd  movups  xmmword ptr [rbp+var_28.Length], xmm0
0x140019201  sub     eax, 1
0x140019204  jz      loc_140019333
0x14001920a  sub     eax, 1
0x14001920d  jz      loc_140019324
0x140019213  sub     eax, 1
0x140019216  jz      short loc_14001923D
0x140019218  cmp     eax, 1
0x14001921b  jz      short loc_14001922E
0x14001921d  cmp     r8d, 3
0x140019221  jz      short loc_14001924C
0x140019223  cmp     r8d, 4
0x140019227  jz      short loc_14001924C
0x140019229  jmp     loc_140019340
0x14001922e  mov     al, sil
0x140019231  neg     al
0x140019233  sbb     ecx, ecx
0x140019235  and     ecx, 0FFFFFFF0h
0x140019238  add     ecx, 38h ; '8'
0x14001923b  jmp     short loc_14001924A
0x14001923d  mov     al, sil
0x140019240  neg     al
0x140019242  sbb     ecx, ecx
0x140019244  and     ecx, 0FFFFFFF4h
0x140019247  add     ecx, 20h ; ' '
0x14001924a  add     ebx, ecx
0x14001924c  mov     rdx, [rbp+arg_28]
0x140019250  lea     rax, [rbp+var_18]
0x140019254  mov     rcx, [rbp+arg_20]
0x140019258  lea     r9, [rbp+var_28]
0x14001925c  lea     r8, [rbp+String1]
0x140019260  mov     [rsp+68h+var_48], rax
0x140019265  mov     word ptr [r15+20h], 0FFFFh
0x14001926c  call    DfscCleanupGetClientInfoParameters
0x140019271  mov     rcx, r15
0x140019274  call    DfscReferralIterate
0x140019279  xor     edi, edi
0x14001927b  jmp     loc_14001930A
0x140019280  mov     rcx, r15
0x140019283  call    DfscReferralGetCurrentTarget
0x140019288  mov     r14, rax
0x14001928b  cmp     [rbp+String1.Length], di
0x14001928f  jz      short loc_1400192AC
0x140019291  lea     rdx, [rax+10h]; String2
0x140019295  mov     r8b, 1; CaseInSensitive
0x140019298  lea     rcx, [rbp+String1]; String1
0x14001929c  call    cs:__imp_RtlCompareUnicodeString
0x1400192a3  nop     dword ptr [rax+rax+00h]
0x1400192a8  test    eax, eax
0x1400192aa  jnz     short loc_140019302
0x1400192ac  cmp     [rbp+var_28.Length], di
0x1400192b0  jz      short loc_1400192CD
0x1400192b2  lea     rdx, [r14+20h]; String2
0x1400192b6  mov     r8b, 1; CaseInSensitive
0x1400192b9  lea     rcx, [rbp+var_28]; String1
0x1400192bd  call    cs:__imp_RtlCompareUnicodeString
0x1400192c4  nop     dword ptr [rax+rax+00h]
0x1400192c9  test    eax, eax
0x1400192cb  jnz     short loc_140019302
0x1400192cd  cmp     [rbp+var_18.Length], di
0x1400192d1  jz      short loc_1400192EE
0x1400192d3  lea     rdx, [r14+30h]; String2
0x1400192d7  mov     r8b, 1; CaseInSensitive
0x1400192da  lea     rcx, [rbp+var_18]; String1
0x1400192de  call    cs:__imp_RtlCompareUnicodeString
0x1400192e5  nop     dword ptr [rax+rax+00h]
0x1400192ea  test    eax, eax
0x1400192ec  jnz     short loc_140019302
0x1400192ee  movzx   eax, word ptr [r14+60h]
0x1400192f3  add     ebx, eax
0x1400192f5  test    sil, sil
0x1400192f8  jz      short loc_1400192FF
0x1400192fa  add     ebx, 0Eh
0x1400192fd  jmp     short loc_140019302
0x1400192ff  add     ebx, 1Ah
0x140019302  mov     rcx, r15
0x140019305  call    DfscReferralIterate
0x14001930a  test    eax, eax
0x14001930c  jns     loc_140019280
0x140019312  mov     rcx, [rbp+arg_30]
0x140019316  cmp     eax, 8000001Ah
0x14001931b  cmovnz  edi, eax
0x14001931e  mov     eax, edi
0x140019320  mov     [rcx], ebx
0x140019322  jmp     short loc_140019348
0x140019324  neg     sil
0x140019327  sbb     eax, eax
0x140019329  and     eax, 0FFFFFFF8h
0x14001932c  add     eax, 18h
0x14001932f  add     ebx, eax
0x140019331  jmp     short loc_140019340
0x140019333  test    sil, sil
0x140019336  jz      short loc_14001933D
0x140019338  add     ebx, 4
0x14001933b  jmp     short loc_140019340
0x14001933d  add     ebx, 8
0x140019340  mov     rax, [rbp+arg_30]
0x140019344  mov     [rax], ebx
0x140019346  xor     eax, eax
0x140019348  add     rsp, 68h
0x14001934c  pop     r15
0x14001934e  pop     r14
0x140019350  pop     rdi
0x140019351  pop     rsi
0x140019352  pop     rbx
0x140019353  pop     rbp
0x140019354  retn
```
