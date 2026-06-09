# QueryAttributes

- ea: `0x14010acb0`
- end: `0x14010aedf`
- name: `QueryAttributes`
- size: `559`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14010aee8`
- `0x14010af78`

## callees

- `0x14010a8d0`
- `0x14010acb0`
- `0x1401e9ce0`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14010ad13`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010ad49`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010ad77`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010ada2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010add0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010ad13`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010ad49`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010ad77`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010ada2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14010add0`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14010ae26`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x14010ae26`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14010ae3d`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x14010ae3d`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14010ae4f`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x14010ae4f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010ade8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010ae7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010aea1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010ade8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010ae7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010aea1`

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
0x14010acb0  mov     [rsp-8+arg_8], rbx
0x14010acb5  mov     [rsp-8+arg_18], rsi
0x14010acba  push    rbp
0x14010acbb  push    rdi
0x14010acbc  push    r12
0x14010acbe  push    r14
0x14010acc0  push    r15
0x14010acc2  lea     rbp, [rsp-37h]
0x14010acc7  sub     rsp, 90h
0x14010acce  mov     rax, cs:__security_cookie
0x14010acd5  xor     rax, rsp
0x14010acd8  mov     [rbp+57h+var_30], rax
0x14010acdc  mov     edi, edx
0x14010acde  mov     r12, r8
0x14010ace1  xor     edx, edx; Val
0x14010ace3  mov     r15, rcx
0x14010ace6  lea     rcx, [rbp+57h+DestinationString]; void *
0x14010acea  lea     r8d, [rdx+40h]; Size
0x14010acee  call    memset
0x14010acf3  xor     r14d, r14d
0x14010acf6  mov     [rbp+57h+var_80], r14d
0x14010acfa  mov     [r12], r14
0x14010acfe  test    dil, 1
0x14010ad02  jz      short loc_14010AD24
0x14010ad04  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x14010ad0b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14010ad0f  lea     ebx, [r14+64h]
0x14010ad13  call    cs:__imp_RtlInitUnicodeString
0x14010ad1a  nop     dword ptr [rax+rax+00h]
0x14010ad1f  lea     esi, [rbx-63h]
0x14010ad22  jmp     short loc_14010AD29
0x14010ad24  xor     esi, esi
0x14010ad26  lea     ebx, [rsi+10h]
0x14010ad29  test    dil, 2
0x14010ad2d  jz      short loc_14010AD57
0x14010ad2f  mov     eax, esi
0x14010ad31  lea     rcx, [rbp+57h+DestinationString]
0x14010ad35  shl     rax, 4
0x14010ad39  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x14010ad40  add     rcx, rax; DestinationString
0x14010ad43  add     ebx, 98h
0x14010ad49  call    cs:__imp_RtlInitUnicodeString
0x14010ad50  nop     dword ptr [rax+rax+00h]
0x14010ad55  inc     esi
0x14010ad57  test    dil, 4
0x14010ad5b  jz      short loc_14010AD85
0x14010ad5d  mov     eax, esi
0x14010ad5f  lea     rcx, [rbp+57h+DestinationString]
0x14010ad63  shl     rax, 4
0x14010ad67  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x14010ad6e  add     rcx, rax; DestinationString
0x14010ad71  add     ebx, 98h
0x14010ad77  call    cs:__imp_RtlInitUnicodeString
0x14010ad7e  nop     dword ptr [rax+rax+00h]
0x14010ad83  inc     esi
0x14010ad85  test    dil, 8
0x14010ad89  jz      short loc_14010ADB0
0x14010ad8b  mov     eax, esi
0x14010ad8d  lea     rcx, [rbp+57h+DestinationString]
0x14010ad91  shl     rax, 4
0x14010ad95  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x14010ad9c  add     rcx, rax; DestinationString
0x14010ad9f  add     ebx, 54h ; 'T'
0x14010ada2  call    cs:__imp_RtlInitUnicodeString
0x14010ada9  nop     dword ptr [rax+rax+00h]
0x14010adae  inc     esi
0x14010adb0  test    dil, 10h
0x14010adb4  jz      short loc_14010ADDE
0x14010adb6  mov     eax, esi
0x14010adb8  lea     rcx, [rbp+57h+DestinationString]
0x14010adbc  shl     rax, 4
0x14010adc0  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x14010adc7  add     rcx, rax; DestinationString
0x14010adca  add     ebx, 98h
0x14010add0  call    cs:__imp_RtlInitUnicodeString
0x14010add7  nop     dword ptr [rax+rax+00h]
0x14010addc  inc     esi
0x14010adde  test    r14, r14
0x14010ade1  jz      short loc_14010ADF4
0x14010ade3  xor     edx, edx; Tag
0x14010ade5  mov     rcx, r14; P
0x14010ade8  call    cs:__imp_ExFreePoolWithTag
0x14010adef  nop     dword ptr [rax+rax+00h]
0x14010adf4  mov     ecx, ebx
0x14010adf6  call    EnterpriseContextLibMemAlloc
0x14010adfb  mov     r14, rax
0x14010adfe  test    rax, rax
0x14010ae01  jz      loc_14010AEAF
0x14010ae07  mov     rcx, [r15]
0x14010ae0a  lea     rax, [rbp+57h+var_80]
0x14010ae0e  mov     [rsp+0B0h+var_88], rax
0x14010ae13  mov     r9, r14
0x14010ae16  mov     [rsp+0B0h+var_90], ebx
0x14010ae1a  mov     r8d, esi
0x14010ae1d  lea     rdx, [rbp+57h+DestinationString]
0x14010ae21  test    rcx, rcx
0x14010ae24  jz      short loc_14010AE34
0x14010ae26  call    cs:__imp_SeQuerySecurityAttributesToken
0x14010ae2d  nop     dword ptr [rax+rax+00h]
0x14010ae32  jmp     short loc_14010AE5B
0x14010ae34  mov     rcx, [r15+18h]
0x14010ae38  test    rcx, rcx
0x14010ae3b  jz      short loc_14010AE4B
0x14010ae3d  call    cs:__imp_ZwQuerySecurityAttributesToken
0x14010ae44  nop     dword ptr [rax+rax+00h]
0x14010ae49  jmp     short loc_14010AE5B
0x14010ae4b  mov     rcx, [r15+10h]
0x14010ae4f  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x14010ae56  nop     dword ptr [rax+rax+00h]
0x14010ae5b  mov     edi, eax
0x14010ae5d  cmp     eax, 0C0000023h
0x14010ae62  jnz     short loc_14010AE71
0x14010ae64  cmp     ebx, [rbp+57h+var_80]
0x14010ae67  jnb     short loc_14010AE9C
0x14010ae69  mov     ebx, [rbp+57h+var_80]
0x14010ae6c  jmp     loc_14010ADDE
0x14010ae71  cmp     edi, 0C0000225h
0x14010ae77  jnz     short loc_14010AE92
0x14010ae79  xor     edx, edx; Tag
0x14010ae7b  mov     rcx, r14; P
0x14010ae7e  call    cs:__imp_ExFreePoolWithTag
0x14010ae85  nop     dword ptr [rax+rax+00h]
0x14010ae8a  xor     edi, edi
0x14010ae8c  mov     [r12], rdi
0x14010ae90  jmp     short loc_14010AEB4
0x14010ae92  test    edi, edi
0x14010ae94  js      short loc_14010AE9C
0x14010ae96  mov     [r12], r14
0x14010ae9a  jmp     short loc_14010AEB4
0x14010ae9c  xor     edx, edx; Tag
0x14010ae9e  mov     rcx, r14; P
0x14010aea1  call    cs:__imp_ExFreePoolWithTag
0x14010aea8  nop     dword ptr [rax+rax+00h]
0x14010aead  jmp     short loc_14010AEB4
0x14010aeaf  mov     edi, 0C0000017h
0x14010aeb4  mov     eax, edi
0x14010aeb6  mov     rcx, [rbp+57h+var_30]
0x14010aeba  xor     rcx, rsp; StackCookie
0x14010aebd  call    __security_check_cookie
0x14010aec2  lea     r11, [rsp+0B0h+var_20]
0x14010aeca  mov     rbx, [r11+38h]
0x14010aece  mov     rsi, [r11+48h]
0x14010aed2  mov     rsp, r11
0x14010aed5  pop     r15
0x14010aed7  pop     r14
0x14010aed9  pop     r12
0x14010aedb  pop     rdi
0x14010aedc  pop     rbp
0x14010aedd  retn
```
