# EfsOpenEncryptOnCloseFile

- ea: `0x140050050`
- end: `0x1400501bf`
- name: `EfsOpenEncryptOnCloseFile`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x14000b5d0`
- `0x140050050`
- `0x1400510ac`
- `0x140052fa0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140050173`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140050173`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005018a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005018a`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140050122`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x140050122`
- `ntoskrnl!SeQueryInformationToken` at `0x140050102`
- `ntoskrnl!SeQueryInformationToken` at `0x140050102`

## pseudocode

```c
__int64 __fastcall EfsOpenEncryptOnCloseFile(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 *a7)
{
  __int64 v7; // r15
  __int64 v8; // rdi
  int v9; // esi
  int v10; // r12d
  bool v12; // zf
  NTSTATUS v13; // ebx
  int v14; // eax
  __int64 ContextBlock; // rcx
  __int64 v16; // rdx
  void *v17; // rcx
  __int64 v19; // [rsp+40h] [rbp-20h] BYREF
  PVOID TokenInformation; // [rsp+48h] [rbp-18h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-10h] BYREF
  char v22; // [rsp+A0h] [rbp+40h] BYREF

  v7 = a5;
  v8 = 0;
  v19 = 0;
  v22 = 0;
  v9 = a4;
  TokenInformation = 0;
  v10 = a3;
  UnicodeString = 0;
  if ( a3 )
  {
    v12 = a4 == 0;
  }
  else
  {
    if ( a4 )
    {
LABEL_5:
      v13 = -1073741811;
      goto LABEL_16;
    }
    v12 = a5 == 0;
  }
  if ( v12 )
    goto LABEL_5;
  v14 = EfspFileRequiresEncryption(a1, a2, 0, a6, 2, (__int64)&v22, (__int64)&v19);
  v8 = v19;
  v13 = v14;
  if ( v14 >= 0 )
  {
    ContextBlock = 0;
    if ( !v22 )
    {
LABEL_15:
      *a7 = ContextBlock;
      goto LABEL_16;
    }
    v16 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
    v17 = *(void **)(v16 + 32);
    if ( !v17 )
      v17 = *(void **)(v16 + 48);
    v13 = SeQueryInformationToken(v17, TokenUser, &TokenInformation);
    if ( v13 >= 0 )
    {
      v13 = RtlConvertSidToUnicodeString(&UnicodeString, *(PSID *)TokenInformation, 1u);
      if ( v13 >= 0 )
      {
        ContextBlock = EdppCreateContextBlock(64, (unsigned int)&UnicodeString, v10, v9, v7, v8);
        if ( !ContextBlock )
        {
          v13 = -1073741801;
          goto LABEL_16;
        }
        goto LABEL_15;
      }
    }
  }
LABEL_16:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  if ( v8 )
    SrpDeleteEnterpriseId(v8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140050050  mov     [rsp-28h+arg_0], rbx
0x140050055  mov     [rsp-28h+arg_8], rsi
0x14005005a  push    rbp
0x14005005b  push    rdi
0x14005005c  push    r12
0x14005005e  push    r14
0x140050060  push    r15
0x140050062  mov     rbp, rsp
0x140050065  sub     rsp, 60h
0x140050069  mov     r15, [rbp+arg_20]
0x14005006d  xor     edi, edi
0x14005006f  mov     [rbp+var_20], rdi
0x140050073  xorps   xmm0, xmm0
0x140050076  mov     [rbp+arg_10], dil
0x14005007a  mov     rsi, r9
0x14005007d  mov     [rbp+TokenInformation], rdi
0x140050081  mov     r12, r8
0x140050084  mov     r14, rcx
0x140050087  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14005008b  test    r8, r8
0x14005008e  jnz     short loc_1400500A4
0x140050090  test    r9, r9
0x140050093  jnz     short loc_14005009A
0x140050095  test    r15, r15
0x140050098  jnz     short loc_1400500A9
0x14005009a  mov     ebx, 0C000000Dh
0x14005009f  jmp     loc_140050168
0x1400500a4  test    rsi, rsi
0x1400500a7  jmp     short loc_140050098
0x1400500a9  mov     r9, [rbp+arg_28]
0x1400500ad  lea     rax, [rbp+var_20]
0x1400500b1  mov     [rsp+60h+var_30], rax
0x1400500b6  xor     r8d, r8d
0x1400500b9  lea     rax, [rbp+arg_10]
0x1400500bd  mov     [rsp+60h+var_38], rax
0x1400500c2  mov     dword ptr [rsp+60h+var_40], 2
0x1400500ca  call    EfspFileRequiresEncryption
0x1400500cf  mov     rdi, [rbp+var_20]
0x1400500d3  mov     ebx, eax
0x1400500d5  test    eax, eax
0x1400500d7  js      loc_140050168
0x1400500dd  xor     ecx, ecx
0x1400500df  cmp     [rbp+arg_10], cl
0x1400500e2  jz      short loc_140050161
0x1400500e4  mov     rax, [r14+8]
0x1400500e8  mov     rdx, [rax+8]
0x1400500ec  mov     rcx, [rdx+20h]
0x1400500f0  test    rcx, rcx
0x1400500f3  jnz     short loc_1400500F9
0x1400500f5  mov     rcx, [rdx+30h]; Token
0x1400500f9  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1400500fd  mov     edx, 1; TokenInformationClass
0x140050102  call    cs:__imp_SeQueryInformationToken
0x140050109  nop     dword ptr [rax+rax+00h]
0x14005010e  mov     ebx, eax
0x140050110  test    eax, eax
0x140050112  js      short loc_140050168
0x140050114  mov     rdx, [rbp+TokenInformation]
0x140050118  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14005011c  mov     r8b, 1; AllocateDestinationString
0x14005011f  mov     rdx, [rdx]; Sid
0x140050122  call    cs:__imp_RtlConvertSidToUnicodeString
0x140050129  nop     dword ptr [rax+rax+00h]
0x14005012e  mov     ebx, eax
0x140050130  test    eax, eax
0x140050132  js      short loc_140050168
0x140050134  mov     [rsp+60h+var_38], rdi
0x140050139  lea     rdx, [rbp+UnicodeString]
0x14005013d  mov     r9, rsi
0x140050140  mov     [rsp+60h+var_40], r15
0x140050145  mov     r8, r12
0x140050148  mov     ecx, 40h ; '@'
0x14005014d  call    EdppCreateContextBlock
0x140050152  mov     rcx, rax
0x140050155  test    rax, rax
0x140050158  jnz     short loc_140050161
0x14005015a  mov     ebx, 0C0000017h
0x14005015f  jmp     short loc_140050168
0x140050161  mov     rax, [rbp+arg_30]
0x140050165  mov     [rax], rcx
0x140050168  cmp     [rbp+UnicodeString.Buffer], 0
0x14005016d  jz      short loc_14005017F
0x14005016f  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x140050173  call    cs:__imp_RtlFreeUnicodeString
0x14005017a  nop     dword ptr [rax+rax+00h]
0x14005017f  mov     rcx, [rbp+TokenInformation]; P
0x140050183  test    rcx, rcx
0x140050186  jz      short loc_140050196
0x140050188  xor     edx, edx; Tag
0x14005018a  call    cs:__imp_ExFreePoolWithTag
0x140050191  nop     dword ptr [rax+rax+00h]
0x140050196  test    rdi, rdi
0x140050199  jz      short loc_1400501A3
0x14005019b  mov     rcx, rdi
0x14005019e  call    SrpDeleteEnterpriseId
0x1400501a3  lea     r11, [rsp+60h+var_s0]
0x1400501a8  mov     eax, ebx
0x1400501aa  mov     rbx, [r11+30h]
0x1400501ae  mov     rsi, [r11+38h]
0x1400501b2  mov     rsp, r11
0x1400501b5  pop     r15
0x1400501b7  pop     r14
0x1400501b9  pop     r12
0x1400501bb  pop     rdi
0x1400501bc  pop     rbp
0x1400501bd  retn
```
