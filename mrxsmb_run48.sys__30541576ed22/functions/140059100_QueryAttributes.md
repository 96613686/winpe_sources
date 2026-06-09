# QueryAttributes

- ea: `0x140059100`
- end: `0x14005932f`
- name: `QueryAttributes`
- size: `559`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140059338`
- `0x1400593c8`

## callees

- `0x140058c00`
- `0x140059100`
- `0x140059dc0`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14005929f`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14005929f`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14005928d`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14005928d`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140059276`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140059276`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059163`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059199`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400591c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400591f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059220`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059163`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059199`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400591c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400591f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140059220`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059238`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400592ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400592f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059238`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400592ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400592f1`

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
  UNICODE_STRING DestinationString[4]; // [rsp+40h] [rbp-19h] BYREF

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
0x140059100  mov     [rsp-8+arg_8], rbx
0x140059105  mov     [rsp-8+arg_18], rsi
0x14005910a  push    rbp
0x14005910b  push    rdi
0x14005910c  push    r12
0x14005910e  push    r14
0x140059110  push    r15
0x140059112  lea     rbp, [rsp-37h]
0x140059117  sub     rsp, 90h
0x14005911e  mov     rax, cs:__security_cookie
0x140059125  xor     rax, rsp
0x140059128  mov     [rbp+57h+var_30], rax
0x14005912c  mov     edi, edx
0x14005912e  mov     r12, r8
0x140059131  xor     edx, edx; Val
0x140059133  mov     r15, rcx
0x140059136  lea     rcx, [rbp+57h+DestinationString]; void *
0x14005913a  lea     r8d, [rdx+40h]; Size
0x14005913e  call    memset
0x140059143  xor     r14d, r14d
0x140059146  mov     [rbp+57h+var_80], r14d
0x14005914a  mov     [r12], r14
0x14005914e  test    dil, 1
0x140059152  jz      short loc_140059174
0x140059154  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x14005915b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14005915f  lea     ebx, [r14+64h]
0x140059163  call    cs:__imp_RtlInitUnicodeString
0x14005916a  nop     dword ptr [rax+rax+00h]
0x14005916f  lea     esi, [rbx-63h]
0x140059172  jmp     short loc_140059179
0x140059174  xor     esi, esi
0x140059176  lea     ebx, [rsi+10h]
0x140059179  test    dil, 2
0x14005917d  jz      short loc_1400591A7
0x14005917f  mov     eax, esi
0x140059181  lea     rcx, [rbp+57h+DestinationString]
0x140059185  shl     rax, 4
0x140059189  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x140059190  add     rcx, rax; DestinationString
0x140059193  add     ebx, 98h
0x140059199  call    cs:__imp_RtlInitUnicodeString
0x1400591a0  nop     dword ptr [rax+rax+00h]
0x1400591a5  inc     esi
0x1400591a7  test    dil, 4
0x1400591ab  jz      short loc_1400591D5
0x1400591ad  mov     eax, esi
0x1400591af  lea     rcx, [rbp+57h+DestinationString]
0x1400591b3  shl     rax, 4
0x1400591b7  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x1400591be  add     rcx, rax; DestinationString
0x1400591c1  add     ebx, 98h
0x1400591c7  call    cs:__imp_RtlInitUnicodeString
0x1400591ce  nop     dword ptr [rax+rax+00h]
0x1400591d3  inc     esi
0x1400591d5  test    dil, 8
0x1400591d9  jz      short loc_140059200
0x1400591db  mov     eax, esi
0x1400591dd  lea     rcx, [rbp+57h+DestinationString]
0x1400591e1  shl     rax, 4
0x1400591e5  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1400591ec  add     rcx, rax; DestinationString
0x1400591ef  add     ebx, 54h ; 'T'
0x1400591f2  call    cs:__imp_RtlInitUnicodeString
0x1400591f9  nop     dword ptr [rax+rax+00h]
0x1400591fe  inc     esi
0x140059200  test    dil, 10h
0x140059204  jz      short loc_14005922E
0x140059206  mov     eax, esi
0x140059208  lea     rcx, [rbp+57h+DestinationString]
0x14005920c  shl     rax, 4
0x140059210  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x140059217  add     rcx, rax; DestinationString
0x14005921a  add     ebx, 98h
0x140059220  call    cs:__imp_RtlInitUnicodeString
0x140059227  nop     dword ptr [rax+rax+00h]
0x14005922c  inc     esi
0x14005922e  test    r14, r14
0x140059231  jz      short loc_140059244
0x140059233  xor     edx, edx; Tag
0x140059235  mov     rcx, r14; P
0x140059238  call    cs:__imp_ExFreePoolWithTag
0x14005923f  nop     dword ptr [rax+rax+00h]
0x140059244  mov     ecx, ebx
0x140059246  call    EnterpriseContextLibMemAlloc
0x14005924b  mov     r14, rax
0x14005924e  test    rax, rax
0x140059251  jz      loc_1400592FF
0x140059257  mov     rcx, [r15]
0x14005925a  lea     rax, [rbp+57h+var_80]
0x14005925e  mov     [rsp+0B0h+var_88], rax
0x140059263  mov     r9, r14
0x140059266  mov     [rsp+0B0h+var_90], ebx
0x14005926a  mov     r8d, esi
0x14005926d  lea     rdx, [rbp+57h+DestinationString]
0x140059271  test    rcx, rcx
0x140059274  jz      short loc_140059284
0x140059276  call    cs:__imp_SeQuerySecurityAttributesToken
0x14005927d  nop     dword ptr [rax+rax+00h]
0x140059282  jmp     short loc_1400592AB
0x140059284  mov     rcx, [r15+18h]
0x140059288  test    rcx, rcx
0x14005928b  jz      short loc_14005929B
0x14005928d  call    cs:__imp_ZwQuerySecurityAttributesToken
0x140059294  nop     dword ptr [rax+rax+00h]
0x140059299  jmp     short loc_1400592AB
0x14005929b  mov     rcx, [r15+10h]
0x14005929f  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x1400592a6  nop     dword ptr [rax+rax+00h]
0x1400592ab  mov     edi, eax
0x1400592ad  cmp     eax, 0C0000023h
0x1400592b2  jnz     short loc_1400592C1
0x1400592b4  cmp     ebx, [rbp+57h+var_80]
0x1400592b7  jnb     short loc_1400592EC
0x1400592b9  mov     ebx, [rbp+57h+var_80]
0x1400592bc  jmp     loc_14005922E
0x1400592c1  cmp     edi, 0C0000225h
0x1400592c7  jnz     short loc_1400592E2
0x1400592c9  xor     edx, edx; Tag
0x1400592cb  mov     rcx, r14; P
0x1400592ce  call    cs:__imp_ExFreePoolWithTag
0x1400592d5  nop     dword ptr [rax+rax+00h]
0x1400592da  xor     edi, edi
0x1400592dc  mov     [r12], rdi
0x1400592e0  jmp     short loc_140059304
0x1400592e2  test    edi, edi
0x1400592e4  js      short loc_1400592EC
0x1400592e6  mov     [r12], r14
0x1400592ea  jmp     short loc_140059304
0x1400592ec  xor     edx, edx; Tag
0x1400592ee  mov     rcx, r14; P
0x1400592f1  call    cs:__imp_ExFreePoolWithTag
0x1400592f8  nop     dword ptr [rax+rax+00h]
0x1400592fd  jmp     short loc_140059304
0x1400592ff  mov     edi, 0C0000017h
0x140059304  mov     eax, edi
0x140059306  mov     rcx, [rbp+57h+var_30]
0x14005930a  xor     rcx, rsp; StackCookie
0x14005930d  call    __security_check_cookie
0x140059312  lea     r11, [rsp+0B0h+var_20]
0x14005931a  mov     rbx, [r11+38h]
0x14005931e  mov     rsi, [r11+48h]
0x140059322  mov     rsp, r11
0x140059325  pop     r15
0x140059327  pop     r14
0x140059329  pop     r12
0x14005932b  pop     rdi
0x14005932c  pop     rbp
0x14005932d  retn
```
