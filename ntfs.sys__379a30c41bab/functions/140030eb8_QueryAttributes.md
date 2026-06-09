# QueryAttributes

- ea: `0x140030eb8`
- end: `0x140031121`
- name: `QueryAttributes`
- size: `617`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140030c38`
- `0x140030ce4`

## callees

- `0x140030eb8`
- `0x140031128`
- `0x1400592c0`
- `0x140059740`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140030f1f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030f4e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030f83`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400310b1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400310de`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030f1f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030f4e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140030f83`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400310b1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400310de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031007`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031043`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400310f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031007`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031043`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400310f6`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140030fda`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x140030fda`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140031067`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x140031067`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14003107c`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14003107c`

## pseudocode

```c
__int64 __fastcall QueryAttributes(_QWORD *a1, char a2, _QWORD *a3)
{
  void *v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // esi
  int SecurityAttributesToken; // eax
  unsigned int v10; // edi
  __int64 v12; // rcx
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
      v12 = a1[3];
      SecurityAttributesToken = v12
                              ? ZwQuerySecurityAttributesToken(v12, DestinationString, v8, v6, v7, v13)
                              : SeQuerySecurityAttributesTokenAccessInformation(
                                  a1[2],
                                  DestinationString,
                                  v8,
                                  v6,
                                  v7,
                                  v13);
    }
    v10 = SecurityAttributesToken;
    if ( SecurityAttributesToken != -1073741789 )
      break;
    if ( v7 >= v13[0] )
      goto LABEL_19;
    v7 = v13[0];
  }
  if ( SecurityAttributesToken == -1073741275 )
  {
    ExFreePoolWithTag(v6, 0);
    v10 = 0;
    *a3 = 0;
  }
  else
  {
    if ( SecurityAttributesToken < 0 )
    {
LABEL_19:
      ExFreePoolWithTag(v6, 0);
      return v10;
    }
    *a3 = v6;
  }
  return v10;
}

```

## disassembly

```asm
0x140030eb8  mov     [rsp-8+arg_8], rbx
0x140030ebd  mov     [rsp-8+arg_18], rsi
0x140030ec2  push    rbp
0x140030ec3  push    rdi
0x140030ec4  push    r12
0x140030ec6  push    r14
0x140030ec8  push    r15
0x140030eca  lea     rbp, [rsp-37h]
0x140030ecf  sub     rsp, 90h
0x140030ed6  mov     rax, cs:__security_cookie
0x140030edd  xor     rax, rsp
0x140030ee0  mov     [rbp+57h+var_30], rax
0x140030ee4  mov     edi, edx
0x140030ee6  mov     r12, r8
0x140030ee9  xor     edx, edx; Val
0x140030eeb  mov     r15, rcx
0x140030eee  lea     rcx, [rbp+57h+DestinationString]; void *
0x140030ef2  lea     r8d, [rdx+40h]; Size
0x140030ef6  call    memset
0x140030efb  xor     r14d, r14d
0x140030efe  mov     [rbp+57h+var_80], r14d
0x140030f02  mov     [r12], r14
0x140030f06  test    dil, 1
0x140030f0a  jz      loc_14003108D
0x140030f10  lea     rdx, SourceString; "EDP://PolicyFlags"
0x140030f17  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140030f1b  lea     ebx, [r14+64h]
0x140030f1f  call    cs:__imp_RtlInitUnicodeString
0x140030f26  nop     dword ptr [rax+rax+00h]
0x140030f2b  lea     esi, [rbx-63h]
0x140030f2e  test    dil, 2
0x140030f32  jz      short loc_140030F5C
0x140030f34  mov     eax, esi
0x140030f36  lea     rcx, [rbp+57h+DestinationString]
0x140030f3a  shl     rax, 4
0x140030f3e  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x140030f45  add     rcx, rax; DestinationString
0x140030f48  add     ebx, 98h
0x140030f4e  call    cs:__imp_RtlInitUnicodeString
0x140030f55  nop     dword ptr [rax+rax+00h]
0x140030f5a  inc     esi
0x140030f5c  test    dil, 4
0x140030f60  jnz     loc_140031097
0x140030f66  test    dil, 8
0x140030f6a  jz      short loc_140030F91
0x140030f6c  mov     eax, esi
0x140030f6e  lea     rcx, [rbp+57h+DestinationString]
0x140030f72  shl     rax, 4
0x140030f76  lea     rdx, Source2; "EDP://EvaluationFlags"
0x140030f7d  add     rcx, rax; DestinationString
0x140030f80  add     ebx, 54h ; 'T'
0x140030f83  call    cs:__imp_RtlInitUnicodeString
0x140030f8a  nop     dword ptr [rax+rax+00h]
0x140030f8f  inc     esi
0x140030f91  test    dil, 10h
0x140030f95  jnz     loc_1400310C4
0x140030f9b  test    r14, r14
0x140030f9e  jnz     loc_1400310F1
0x140030fa4  mov     ecx, ebx
0x140030fa6  call    EnterpriseContextLibMemAlloc
0x140030fab  mov     r14, rax
0x140030fae  test    rax, rax
0x140030fb1  jz      loc_140031057
0x140030fb7  mov     rcx, [r15]
0x140030fba  lea     rax, [rbp+57h+var_80]
0x140030fbe  mov     [rsp+0B0h+var_88], rax
0x140030fc3  mov     r9, r14
0x140030fc6  mov     [rsp+0B0h+var_90], ebx
0x140030fca  mov     r8d, esi
0x140030fcd  lea     rdx, [rbp+57h+DestinationString]
0x140030fd1  test    rcx, rcx
0x140030fd4  jz      loc_14003105E
0x140030fda  call    cs:__imp_SeQuerySecurityAttributesToken
0x140030fe1  nop     dword ptr [rax+rax+00h]
0x140030fe6  mov     edi, eax
0x140030fe8  cmp     eax, 0C0000023h
0x140030fed  jz      loc_140031107
0x140030ff3  cmp     eax, 0C0000225h
0x140030ff8  jz      short loc_14003103E
0x140030ffa  test    eax, eax
0x140030ffc  jns     loc_140031118
0x140031002  xor     edx, edx; Tag
0x140031004  mov     rcx, r14; P
0x140031007  call    cs:__imp_ExFreePoolWithTag
0x14003100e  nop     dword ptr [rax+rax+00h]
0x140031013  mov     eax, edi
0x140031015  mov     rcx, [rbp+57h+var_30]
0x140031019  xor     rcx, rsp; StackCookie
0x14003101c  call    __security_check_cookie
0x140031021  lea     r11, [rsp+0B0h+var_20]
0x140031029  mov     rbx, [r11+38h]
0x14003102d  mov     rsi, [r11+48h]
0x140031031  mov     rsp, r11
0x140031034  pop     r15
0x140031036  pop     r14
0x140031038  pop     r12
0x14003103a  pop     rdi
0x14003103b  pop     rbp
0x14003103c  retn
0x14003103e  xor     edx, edx; Tag
0x140031040  mov     rcx, r14; P
0x140031043  call    cs:__imp_ExFreePoolWithTag
0x14003104a  nop     dword ptr [rax+rax+00h]
0x14003104f  xor     edi, edi
0x140031051  mov     [r12], rdi
0x140031055  jmp     short loc_140031013
0x140031057  mov     edi, 0C0000017h
0x14003105c  jmp     short loc_140031013
0x14003105e  mov     rcx, [r15+18h]
0x140031062  test    rcx, rcx
0x140031065  jz      short loc_140031078
0x140031067  call    cs:__imp_ZwQuerySecurityAttributesToken
0x14003106e  nop     dword ptr [rax+rax+00h]
0x140031073  jmp     loc_140030FE6
0x140031078  mov     rcx, [r15+10h]
0x14003107c  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x140031083  nop     dword ptr [rax+rax+00h]
0x140031088  jmp     loc_140030FE6
0x14003108d  xor     esi, esi
0x14003108f  lea     ebx, [rsi+10h]
0x140031092  jmp     loc_140030F2E
0x140031097  mov     eax, esi
0x140031099  lea     rcx, [rbp+57h+DestinationString]
0x14003109d  shl     rax, 4
0x1400310a1  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x1400310a8  add     rcx, rax; DestinationString
0x1400310ab  add     ebx, 98h
0x1400310b1  call    cs:__imp_RtlInitUnicodeString
0x1400310b8  nop     dword ptr [rax+rax+00h]
0x1400310bd  inc     esi
0x1400310bf  jmp     loc_140030F66
0x1400310c4  mov     eax, esi
0x1400310c6  lea     rcx, [rbp+57h+DestinationString]
0x1400310ca  shl     rax, 4
0x1400310ce  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x1400310d5  add     rcx, rax; DestinationString
0x1400310d8  add     ebx, 98h
0x1400310de  call    cs:__imp_RtlInitUnicodeString
0x1400310e5  nop     dword ptr [rax+rax+00h]
0x1400310ea  inc     esi
0x1400310ec  jmp     loc_140030F9B
0x1400310f1  xor     edx, edx; Tag
0x1400310f3  mov     rcx, r14; P
0x1400310f6  call    cs:__imp_ExFreePoolWithTag
0x1400310fd  nop     dword ptr [rax+rax+00h]
0x140031102  jmp     loc_140030FA4
0x140031107  cmp     ebx, [rbp+57h+var_80]
0x14003110a  jnb     loc_140031002
0x140031110  mov     ebx, [rbp+57h+var_80]
0x140031113  jmp     loc_140030F9B
0x140031118  mov     [r12], r14
0x14003111c  jmp     loc_140031013
```
