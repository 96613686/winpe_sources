# QueryAttributes

- ea: `0x14000b040`
- end: `0x14000b26f`
- name: `QueryAttributes`
- size: `559`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b278`
- `0x14000b308`

## callees

- `0x14000ac60`
- `0x14000b040`
- `0x14000c230`
- `0x14000c680`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000b0a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b0d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b107`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b132`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b160`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b0a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b0d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b107`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b132`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000b160`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b178`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b20e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b231`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b178`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b20e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b231`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14000b1b6`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14000b1b6`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14000b1cd`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14000b1cd`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14000b1df`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14000b1df`

## pseudocode

```c
__int64 __fastcall QueryAttributes(_QWORD *a1, char a2, _QWORD *a3)
{
  void *v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // esi
  int SecurityAttributesToken; // eax
  __int64 v10; // rcx
  unsigned int v11; // edi
  _DWORD v13[4]; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString[4]; // [rsp+40h] [rbp-19h] BYREF

  memset(DestinationString, 0, sizeof(DestinationString));
  v6 = 0;
  v13[0] = 0;
  *a3 = 0;
  if ( (a2 & 1) != 0 )
  {
    v7 = 100;
    RtlInitUnicodeString(DestinationString, L"EDP://PolicyFlags");
    v8 = 1;
  }
  else
  {
    v8 = 0;
    v7 = 16;
  }
  if ( (a2 & 2) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EnterpriseIds");
  }
  if ( (a2 & 4) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"PEDP://IntentEnterpriseId");
  }
  if ( (a2 & 8) != 0 )
  {
    v7 += 84;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EvaluationFlags");
  }
  if ( (a2 & 0x10) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://ExemptEnterpriseIds");
  }
  while ( 1 )
  {
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
    v6 = (void *)EnterpriseContextLibMemAlloc(v7);
    if ( !v6 )
      return (unsigned int)-1073741801;
    if ( *a1 )
    {
      SecurityAttributesToken = SeQuerySecurityAttributesToken(*a1, DestinationString, v8, v6, v7, v13);
    }
    else
    {
      v10 = a1[3];
      if ( v10 )
        SecurityAttributesToken = ZwQuerySecurityAttributesToken(v10, DestinationString, v8, v6, v7, v13);
      else
        SecurityAttributesToken = SeQuerySecurityAttributesTokenAccessInformation(
                                    a1[2],
                                    DestinationString,
                                    v8,
                                    v6,
                                    v7,
                                    v13);
    }
    v11 = SecurityAttributesToken;
    if ( SecurityAttributesToken != -1073741789 )
    {
      if ( SecurityAttributesToken == -1073741275 )
      {
        ExFreePoolWithTag(v6, 0);
        v11 = 0;
        *a3 = 0;
        return v11;
      }
      if ( SecurityAttributesToken >= 0 )
      {
        *a3 = v6;
        return v11;
      }
LABEL_27:
      ExFreePoolWithTag(v6, 0);
      return v11;
    }
    if ( v7 >= v13[0] )
      goto LABEL_27;
    v7 = v13[0];
  }
}

```

## disassembly

```asm
0x14000b040  mov     [rsp-8+arg_8], rbx
0x14000b045  mov     [rsp-8+arg_18], rsi
0x14000b04a  push    rbp
0x14000b04b  push    rdi
0x14000b04c  push    r12
0x14000b04e  push    r14
0x14000b050  push    r15
0x14000b052  lea     rbp, [rsp-37h]
0x14000b057  sub     rsp, 90h
0x14000b05e  mov     rax, cs:__security_cookie
0x14000b065  xor     rax, rsp
0x14000b068  mov     [rbp+57h+var_30], rax
0x14000b06c  mov     edi, edx
0x14000b06e  mov     r12, r8
0x14000b071  xor     edx, edx; Val
0x14000b073  mov     r15, rcx
0x14000b076  lea     rcx, [rbp+57h+DestinationString]; void *
0x14000b07a  lea     r8d, [rdx+40h]; Size
0x14000b07e  call    memset
0x14000b083  xor     r14d, r14d
0x14000b086  mov     [rbp+57h+var_80], r14d
0x14000b08a  mov     [r12], r14
0x14000b08e  test    dil, 1
0x14000b092  jz      short loc_14000B0B4
0x14000b094  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x14000b09b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000b09f  lea     ebx, [r14+64h]
0x14000b0a3  call    cs:__imp_RtlInitUnicodeString
0x14000b0aa  nop     dword ptr [rax+rax+00h]
0x14000b0af  lea     esi, [rbx-63h]
0x14000b0b2  jmp     short loc_14000B0B9
0x14000b0b4  xor     esi, esi
0x14000b0b6  lea     ebx, [rsi+10h]
0x14000b0b9  test    dil, 2
0x14000b0bd  jz      short loc_14000B0E7
0x14000b0bf  mov     eax, esi
0x14000b0c1  lea     rcx, [rbp+57h+DestinationString]
0x14000b0c5  shl     rax, 4
0x14000b0c9  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x14000b0d0  add     rcx, rax; DestinationString
0x14000b0d3  add     ebx, 98h
0x14000b0d9  call    cs:__imp_RtlInitUnicodeString
0x14000b0e0  nop     dword ptr [rax+rax+00h]
0x14000b0e5  inc     esi
0x14000b0e7  test    dil, 4
0x14000b0eb  jz      short loc_14000B115
0x14000b0ed  mov     eax, esi
0x14000b0ef  lea     rcx, [rbp+57h+DestinationString]
0x14000b0f3  shl     rax, 4
0x14000b0f7  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x14000b0fe  add     rcx, rax; DestinationString
0x14000b101  add     ebx, 98h
0x14000b107  call    cs:__imp_RtlInitUnicodeString
0x14000b10e  nop     dword ptr [rax+rax+00h]
0x14000b113  inc     esi
0x14000b115  test    dil, 8
0x14000b119  jz      short loc_14000B140
0x14000b11b  mov     eax, esi
0x14000b11d  lea     rcx, [rbp+57h+DestinationString]
0x14000b121  shl     rax, 4
0x14000b125  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x14000b12c  add     rcx, rax; DestinationString
0x14000b12f  add     ebx, 54h ; 'T'
0x14000b132  call    cs:__imp_RtlInitUnicodeString
0x14000b139  nop     dword ptr [rax+rax+00h]
0x14000b13e  inc     esi
0x14000b140  test    dil, 10h
0x14000b144  jz      short loc_14000B16E
0x14000b146  mov     eax, esi
0x14000b148  lea     rcx, [rbp+57h+DestinationString]
0x14000b14c  shl     rax, 4
0x14000b150  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x14000b157  add     rcx, rax; DestinationString
0x14000b15a  add     ebx, 98h
0x14000b160  call    cs:__imp_RtlInitUnicodeString
0x14000b167  nop     dword ptr [rax+rax+00h]
0x14000b16c  inc     esi
0x14000b16e  test    r14, r14
0x14000b171  jz      short loc_14000B184
0x14000b173  xor     edx, edx; Tag
0x14000b175  mov     rcx, r14; P
0x14000b178  call    cs:__imp_ExFreePoolWithTag
0x14000b17f  nop     dword ptr [rax+rax+00h]
0x14000b184  mov     ecx, ebx
0x14000b186  call    EnterpriseContextLibMemAlloc
0x14000b18b  mov     r14, rax
0x14000b18e  test    rax, rax
0x14000b191  jz      loc_14000B23F
0x14000b197  mov     rcx, [r15]
0x14000b19a  lea     rax, [rbp+57h+var_80]
0x14000b19e  mov     [rsp+0B0h+var_88], rax
0x14000b1a3  mov     r9, r14
0x14000b1a6  mov     [rsp+0B0h+var_90], ebx
0x14000b1aa  mov     r8d, esi
0x14000b1ad  lea     rdx, [rbp+57h+DestinationString]
0x14000b1b1  test    rcx, rcx
0x14000b1b4  jz      short loc_14000B1C4
0x14000b1b6  call    cs:__imp_SeQuerySecurityAttributesToken
0x14000b1bd  nop     dword ptr [rax+rax+00h]
0x14000b1c2  jmp     short loc_14000B1EB
0x14000b1c4  mov     rcx, [r15+18h]
0x14000b1c8  test    rcx, rcx
0x14000b1cb  jz      short loc_14000B1DB
0x14000b1cd  call    cs:__imp_ZwQuerySecurityAttributesToken
0x14000b1d4  nop     dword ptr [rax+rax+00h]
0x14000b1d9  jmp     short loc_14000B1EB
0x14000b1db  mov     rcx, [r15+10h]
0x14000b1df  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x14000b1e6  nop     dword ptr [rax+rax+00h]
0x14000b1eb  mov     edi, eax
0x14000b1ed  cmp     eax, 0C0000023h
0x14000b1f2  jnz     short loc_14000B201
0x14000b1f4  cmp     ebx, [rbp+57h+var_80]
0x14000b1f7  jnb     short loc_14000B22C
0x14000b1f9  mov     ebx, [rbp+57h+var_80]
0x14000b1fc  jmp     loc_14000B16E
0x14000b201  cmp     edi, 0C0000225h
0x14000b207  jnz     short loc_14000B222
0x14000b209  xor     edx, edx; Tag
0x14000b20b  mov     rcx, r14; P
0x14000b20e  call    cs:__imp_ExFreePoolWithTag
0x14000b215  nop     dword ptr [rax+rax+00h]
0x14000b21a  xor     edi, edi
0x14000b21c  mov     [r12], rdi
0x14000b220  jmp     short loc_14000B244
0x14000b222  test    edi, edi
0x14000b224  js      short loc_14000B22C
0x14000b226  mov     [r12], r14
0x14000b22a  jmp     short loc_14000B244
0x14000b22c  xor     edx, edx; Tag
0x14000b22e  mov     rcx, r14; P
0x14000b231  call    cs:__imp_ExFreePoolWithTag
0x14000b238  nop     dword ptr [rax+rax+00h]
0x14000b23d  jmp     short loc_14000B244
0x14000b23f  mov     edi, 0C0000017h
0x14000b244  mov     eax, edi
0x14000b246  mov     rcx, [rbp+57h+var_30]
0x14000b24a  xor     rcx, rsp; StackCookie
0x14000b24d  call    __security_check_cookie
0x14000b252  lea     r11, [rsp+0B0h+var_20]
0x14000b25a  mov     rbx, [r11+38h]
0x14000b25e  mov     rsi, [r11+48h]
0x14000b262  mov     rsp, r11
0x14000b265  pop     r15
0x14000b267  pop     r14
0x14000b269  pop     r12
0x14000b26b  pop     rdi
0x14000b26c  pop     rbp
0x14000b26d  retn
```
