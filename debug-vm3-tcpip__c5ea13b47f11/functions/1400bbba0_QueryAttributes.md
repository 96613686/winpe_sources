# QueryAttributes

- ea: `0x1400bbba0`
- end: `0x1400bbe42`
- name: `QueryAttributes`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400bb6a0`

## callees

- `0x1400bbba0`
- `0x1401bf4d0`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1400bbe27`
- `ntoskrnl!ZwQuerySecurityAttributesToken` at `0x1400bbe27`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1400bbd04`
- `ntoskrnl!SeQuerySecurityAttributesTokenAccessInformation` at `0x1400bbd04`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bbc9b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bbc9b`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1400bbd67`
- `ntoskrnl!SeQuerySecurityAttributesToken` at `0x1400bbd67`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbc0c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbc3e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbc74`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbde6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbe14`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbc0c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbc3e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbc74`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbde6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400bbe14`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbd29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbd82`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbdba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbd29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbd82`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbdba`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbcba`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbcba`

## pseudocode

```c
__int64 __fastcall QueryAttributes(_QWORD *a1, char a2, _QWORD *a3)
{
  void *Pool2; // rbp
  unsigned int v7; // esi
  unsigned int v8; // ebx
  KIRQL CurrentIrql; // al
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 result; // rax
  unsigned int v13; // edi
  _DWORD v14[4]; // [rsp+30h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString[4]; // [rsp+40h] [rbp-88h] BYREF

  memset(DestinationString, 0, sizeof(DestinationString));
  v14[0] = 0;
  Pool2 = 0;
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
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    CurrentIrql = KeGetCurrentIrql();
    v10 = 258;
    if ( CurrentIrql > 1u )
      v10 = 66;
    Pool2 = (void *)ExAllocatePool2(v10, v7, 1950576197);
    if ( !Pool2 )
      return 3221225495LL;
    if ( *a1 )
    {
      LODWORD(result) = SeQuerySecurityAttributesToken(*a1, DestinationString, v8, Pool2, v7, v14);
    }
    else
    {
      v11 = a1[3];
      LODWORD(result) = v11
                      ? ZwQuerySecurityAttributesToken(v11, DestinationString, v8, Pool2, v7, v14)
                      : (unsigned int)SeQuerySecurityAttributesTokenAccessInformation(
                                        a1[2],
                                        DestinationString,
                                        v8,
                                        Pool2,
                                        v7,
                                        v14);
    }
    v13 = result;
    if ( (_DWORD)result != -1073741789 )
      break;
    if ( v7 >= v14[0] )
      goto LABEL_24;
    v7 = v14[0];
  }
  if ( (_DWORD)result == -1073741275 )
  {
    ExFreePoolWithTag(Pool2, 0);
    result = 0;
    *a3 = 0;
    return result;
  }
  if ( (int)result < 0 )
  {
LABEL_24:
    ExFreePoolWithTag(Pool2, 0);
    return v13;
  }
  *a3 = Pool2;
  return (unsigned int)result;
}

```

## disassembly

```asm
0x1400bbba0  mov     [rsp+arg_8], rbx
0x1400bbba5  push    rbp
0x1400bbba6  push    rsi
0x1400bbba7  push    rdi
0x1400bbba8  push    r12
0x1400bbbaa  push    r13
0x1400bbbac  push    r14
0x1400bbbae  push    r15
0x1400bbbb0  sub     rsp, 90h
0x1400bbbb7  mov     rax, cs:__security_cookie
0x1400bbbbe  xor     rax, rsp
0x1400bbbc1  mov     [rsp+0C8h+var_48], rax
0x1400bbbc9  mov     r15, r8
0x1400bbbcc  mov     edi, edx
0x1400bbbce  mov     r14, rcx
0x1400bbbd1  xor     edx, edx; Val
0x1400bbbd3  mov     r8d, 40h ; '@'; Size
0x1400bbbd9  lea     rcx, [rsp+0C8h+DestinationString]; void *
0x1400bbbde  call    memset
0x1400bbbe3  xor     r12d, r12d
0x1400bbbe6  mov     [rsp+0C8h+var_98], r12d
0x1400bbbeb  mov     ebp, r12d
0x1400bbbee  mov     [r15], r12
0x1400bbbf1  test    dil, 1
0x1400bbbf5  jz      loc_1400BBD99
0x1400bbbfb  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x1400bbc02  mov     esi, 64h ; 'd'
0x1400bbc07  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1400bbc0c  call    cs:__imp_RtlInitUnicodeString
0x1400bbc13  nop     dword ptr [rax+rax+00h]
0x1400bbc18  mov     ebx, 1
0x1400bbc1d  test    dil, 2
0x1400bbc21  jz      short loc_1400BBC4C
0x1400bbc23  mov     eax, ebx
0x1400bbc25  lea     rcx, [rsp+0C8h+DestinationString]
0x1400bbc2a  shl     rax, 4
0x1400bbc2e  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x1400bbc35  add     rcx, rax; DestinationString
0x1400bbc38  add     esi, 98h
0x1400bbc3e  call    cs:__imp_RtlInitUnicodeString
0x1400bbc45  nop     dword ptr [rax+rax+00h]
0x1400bbc4a  inc     ebx
0x1400bbc4c  test    dil, 4
0x1400bbc50  jnz     loc_1400BBDCB
0x1400bbc56  test    dil, 8
0x1400bbc5a  jz      short loc_1400BBC82
0x1400bbc5c  mov     eax, ebx
0x1400bbc5e  lea     rcx, [rsp+0C8h+DestinationString]
0x1400bbc63  shl     rax, 4
0x1400bbc67  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1400bbc6e  add     rcx, rax; DestinationString
0x1400bbc71  add     esi, 54h ; 'T'
0x1400bbc74  call    cs:__imp_RtlInitUnicodeString
0x1400bbc7b  nop     dword ptr [rax+rax+00h]
0x1400bbc80  inc     ebx
0x1400bbc82  test    dil, 10h
0x1400bbc86  jnz     loc_1400BBDF9
0x1400bbc8c  mov     r13d, 42h ; 'B'
0x1400bbc92  test    rbp, rbp
0x1400bbc95  jnz     loc_1400BBDB5
0x1400bbc9b  call    cs:__imp_KeGetCurrentIrql
0x1400bbca2  nop     dword ptr [rax+rax+00h]
0x1400bbca7  mov     ecx, 102h
0x1400bbcac  mov     edx, esi
0x1400bbcae  cmp     al, 1
0x1400bbcb0  mov     r8d, 74436E45h
0x1400bbcb6  cmova   rcx, r13
0x1400bbcba  call    cs:__imp_ExAllocatePool2
0x1400bbcc1  nop     dword ptr [rax+rax+00h]
0x1400bbcc6  mov     rbp, rax
0x1400bbcc9  test    rax, rax
0x1400bbccc  jz      loc_1400BBD92
0x1400bbcd2  mov     rcx, [r14]
0x1400bbcd5  lea     rax, [rsp+0C8h+var_98]
0x1400bbcda  mov     [rsp+0C8h+var_A0], rax
0x1400bbcdf  mov     r9, rbp
0x1400bbce2  mov     [rsp+0C8h+var_A8], esi
0x1400bbce6  mov     r8d, ebx
0x1400bbce9  lea     rdx, [rsp+0C8h+DestinationString]
0x1400bbcee  test    rcx, rcx
0x1400bbcf1  jnz     short loc_1400BBD67
0x1400bbcf3  mov     rcx, [r14+18h]
0x1400bbcf7  test    rcx, rcx
0x1400bbcfa  jnz     loc_1400BBE27
0x1400bbd00  mov     rcx, [r14+10h]
0x1400bbd04  call    cs:__imp_SeQuerySecurityAttributesTokenAccessInformation
0x1400bbd0b  nop     dword ptr [rax+rax+00h]
0x1400bbd10  mov     edi, eax
0x1400bbd12  cmp     eax, 0C0000023h
0x1400bbd17  jz      loc_1400BBDA6
0x1400bbd1d  cmp     eax, 0C0000225h
0x1400bbd22  jnz     short loc_1400BBD75
0x1400bbd24  xor     edx, edx; Tag
0x1400bbd26  mov     rcx, rbp; P
0x1400bbd29  call    cs:__imp_ExFreePoolWithTag
0x1400bbd30  nop     dword ptr [rax+rax+00h]
0x1400bbd35  mov     eax, r12d
0x1400bbd38  mov     [r15], r12
0x1400bbd3b  mov     rcx, [rsp+0C8h+var_48]
0x1400bbd43  xor     rcx, rsp; StackCookie
0x1400bbd46  call    __security_check_cookie
0x1400bbd4b  mov     rbx, [rsp+0C8h+arg_8]
0x1400bbd53  add     rsp, 90h
0x1400bbd5a  pop     r15
0x1400bbd5c  pop     r14
0x1400bbd5e  pop     r13
0x1400bbd60  pop     r12
0x1400bbd62  pop     rdi
0x1400bbd63  pop     rsi
0x1400bbd64  pop     rbp
0x1400bbd65  retn
0x1400bbd67  call    cs:__imp_SeQuerySecurityAttributesToken
0x1400bbd6e  nop     dword ptr [rax+rax+00h]
0x1400bbd73  jmp     short loc_1400BBD10
0x1400bbd75  test    edi, edi
0x1400bbd77  jns     loc_1400BBE38
0x1400bbd7d  xor     edx, edx; Tag
0x1400bbd7f  mov     rcx, rbp; P
0x1400bbd82  call    cs:__imp_ExFreePoolWithTag
0x1400bbd89  nop     dword ptr [rax+rax+00h]
0x1400bbd8e  mov     eax, edi
0x1400bbd90  jmp     short loc_1400BBD3B
0x1400bbd92  mov     eax, 0C0000017h
0x1400bbd97  jmp     short loc_1400BBD3B
0x1400bbd99  mov     ebx, r12d
0x1400bbd9c  mov     esi, 10h
0x1400bbda1  jmp     loc_1400BBC1D
0x1400bbda6  mov     eax, [rsp+0C8h+var_98]
0x1400bbdaa  cmp     esi, eax
0x1400bbdac  jnb     short loc_1400BBD7D
0x1400bbdae  mov     esi, eax
0x1400bbdb0  jmp     loc_1400BBC92
0x1400bbdb5  xor     edx, edx; Tag
0x1400bbdb7  mov     rcx, rbp; P
0x1400bbdba  call    cs:__imp_ExFreePoolWithTag
0x1400bbdc1  nop     dword ptr [rax+rax+00h]
0x1400bbdc6  jmp     loc_1400BBC9B
0x1400bbdcb  mov     eax, ebx
0x1400bbdcd  lea     rcx, [rsp+0C8h+DestinationString]
0x1400bbdd2  shl     rax, 4
0x1400bbdd6  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x1400bbddd  add     rcx, rax; DestinationString
0x1400bbde0  add     esi, 98h
0x1400bbde6  call    cs:__imp_RtlInitUnicodeString
0x1400bbded  nop     dword ptr [rax+rax+00h]
0x1400bbdf2  inc     ebx
0x1400bbdf4  jmp     loc_1400BBC56
0x1400bbdf9  mov     eax, ebx
0x1400bbdfb  lea     rcx, [rsp+0C8h+DestinationString]
0x1400bbe00  shl     rax, 4
0x1400bbe04  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x1400bbe0b  add     rcx, rax; DestinationString
0x1400bbe0e  add     esi, 98h
0x1400bbe14  call    cs:__imp_RtlInitUnicodeString
0x1400bbe1b  nop     dword ptr [rax+rax+00h]
0x1400bbe20  inc     ebx
0x1400bbe22  jmp     loc_1400BBC8C
0x1400bbe27  call    cs:__imp_ZwQuerySecurityAttributesToken
0x1400bbe2e  nop     dword ptr [rax+rax+00h]
0x1400bbe33  jmp     loc_1400BBD10
0x1400bbe38  mov     [r15], rbp
0x1400bbe3b  mov     eax, edi
0x1400bbe3d  jmp     loc_1400BBD3B
```
