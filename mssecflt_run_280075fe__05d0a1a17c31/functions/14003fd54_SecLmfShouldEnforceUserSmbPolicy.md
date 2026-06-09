# SecLmfShouldEnforceUserSmbPolicy

- ea: `0x14003fd54`
- end: `0x14003ff28`
- name: `SecLmfShouldEnforceUserSmbPolicy`
- size: `468`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003fa28`

## callees

- `0x140006d3c`
- `0x140011650`
- `0x140026a80`
- `0x140029598`
- `0x14003e93c`
- `0x14003fd54`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14003fed6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003fed6`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14003fe13`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14003fe13`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fef3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fef3`

## pseudocode

```c
bool __fastcall SecLmfShouldEnforceUserSmbPolicy(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  bool v3; // r14
  __int64 v4; // r8
  unsigned __int64 v5; // rbx
  int v6; // edi
  int v7; // eax
  unsigned __int64 v8; // rax
  PVOID P; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-38h] BYREF
  __int64 v12; // [rsp+48h] [rbp-28h]
  __int64 v13; // [rsp+50h] [rbp-20h]
  _BYTE v14[8]; // [rsp+58h] [rbp-18h] BYREF

  P = 0;
  UnicodeString = 0;
  v14[0] = 0;
  v3 = 0;
  v13 = 0;
  v12 = 0;
  if ( SecLmfInitialized
    && BYTE4(SecLmfPolicyConfig)
    && DWORD2(SecLmfPolicyConfig)
    && (unsigned int)SecPopulateFileShareContext(*(PFLT_FILTER *)(a2 + 8)) - 2 <= 1
    && (int)SecGetEffectiveTokenUser(CallbackData->Thread, 0, &P, v14, 0) >= 0
    && RtlConvertSidToUnicodeString(&UnicodeString, *(PSID *)P, 1u) >= 0 )
  {
    v5 = *((_QWORD *)&xmmword_14001B7A8 + 1);
    if ( (qword_14001B7B8 & 1) != 0 )
    {
      if ( *((_QWORD *)&xmmword_14001B7A8 + 1) )
        v5 = ((unsigned __int64)&xmmword_14001B7A8 + 8) ^ *((_QWORD *)&xmmword_14001B7A8 + 1);
      else
        v5 = 0;
    }
    v6 = qword_14001B7B8 & 1;
    if ( v5 )
    {
      do
      {
        v7 = SecLmfCompareUserPolicy(&UnicodeString, v5, v4);
        if ( v7 >= 0 )
        {
          if ( v7 <= 0 )
            break;
          v8 = *(_QWORD *)(v5 + 8);
        }
        else
        {
          v8 = *(_QWORD *)v5;
        }
        if ( v6 && v8 )
          v5 ^= v8;
        else
          v5 = v8;
      }
      while ( v5 );
      if ( v5 && (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & *(_DWORD *)(v5 + 48)) != 0 )
      {
        v3 = BYTE5(SecLmfPolicyConfig) == 0;
        SecAuditFileAccessBlock(CallbackData, 0, (__int64)&Event52);
      }
    }
  }
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( P && v14[0] )
    ExFreePoolWithTag(P, 0);
  return v3;
}

```

## disassembly

```asm
0x14003fd54  mov     [rsp-28h+arg_10], rbx
0x14003fd59  mov     [rsp-28h+arg_18], rsi
0x14003fd5e  push    rbp
0x14003fd5f  push    rdi
0x14003fd60  push    r12
0x14003fd62  push    r14
0x14003fd64  push    r15
0x14003fd66  mov     rbp, rsp
0x14003fd69  sub     rsp, 70h
0x14003fd6d  mov     rax, cs:__security_cookie
0x14003fd74  xor     rax, rsp
0x14003fd77  mov     [rbp+var_10], rax
0x14003fd7b  xor     r12d, r12d
0x14003fd7e  xorps   xmm0, xmm0
0x14003fd81  cmp     cs:SecLmfInitialized, r12b
0x14003fd88  mov     r15, rdx
0x14003fd8b  mov     rsi, rcx
0x14003fd8e  mov     [rbp+P], r12
0x14003fd92  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14003fd96  mov     [rbp+var_18], r12b
0x14003fd9a  mov     r14b, r12b
0x14003fd9d  mov     [rbp+var_20], r12
0x14003fda1  mov     [rbp+var_28], r12
0x14003fda5  jz      loc_14003FECC
0x14003fdab  cmp     byte ptr cs:SecLmfPolicyConfig+4, r12b
0x14003fdb2  jz      loc_14003FECC
0x14003fdb8  cmp     dword ptr cs:SecLmfPolicyConfig+8, r12d
0x14003fdbf  jz      loc_14003FECC
0x14003fdc5  mov     rdx, rcx
0x14003fdc8  lea     r9, [rbp+var_28]
0x14003fdcc  mov     rcx, [r15+8]; Filter
0x14003fdd0  lea     r8, [rbp+var_20]
0x14003fdd4  call    SecPopulateFileShareContext
0x14003fdd9  add     eax, 0FFFFFFFEh
0x14003fddc  cmp     eax, 1
0x14003fddf  ja      loc_14003FECC
0x14003fde5  mov     rcx, [rsi+8]; Thread
0x14003fde9  lea     r9, [rbp+var_18]
0x14003fded  lea     r8, [rbp+P]
0x14003fdf1  mov     [rsp+70h+var_50], r12; __int64
0x14003fdf6  xor     edx, edx
0x14003fdf8  call    SecGetEffectiveTokenUser
0x14003fdfd  test    eax, eax
0x14003fdff  js      loc_14003FECC
0x14003fe05  mov     rdx, [rbp+P]
0x14003fe09  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14003fe0d  mov     r8b, 1; AllocateDestinationString
0x14003fe10  mov     rdx, [rdx]; Sid
0x14003fe13  call    cs:__imp_RtlConvertSidToUnicodeString
0x14003fe1a  nop     dword ptr [rax+rax+00h]
0x14003fe1f  test    eax, eax
0x14003fe21  js      loc_14003FECC
0x14003fe27  mov     rax, cs:qword_14001B7B8
0x14003fe2e  mov     rbx, qword ptr cs:xmmword_14001B7A8+8
0x14003fe35  test    al, 1
0x14003fe37  jz      short loc_14003FE4D
0x14003fe39  test    rbx, rbx
0x14003fe3c  jz      short loc_14003FE4A
0x14003fe3e  lea     rcx, xmmword_14001B7A8+8
0x14003fe45  xor     rbx, rcx
0x14003fe48  jmp     short loc_14003FE4D
0x14003fe4a  mov     rbx, r12
0x14003fe4d  movzx   edi, al
0x14003fe50  and     edi, 1
0x14003fe53  test    rbx, rbx
0x14003fe56  jz      short loc_14003FECC
0x14003fe58  mov     rdx, rbx
0x14003fe5b  lea     rcx, [rbp+UnicodeString]
0x14003fe5f  call    SecLmfCompareUserPolicy
0x14003fe64  test    eax, eax
0x14003fe66  jns     short loc_14003FE6D
0x14003fe68  mov     rax, [rbx]
0x14003fe6b  jmp     short loc_14003FE73
0x14003fe6d  jle     short loc_14003FE89
0x14003fe6f  mov     rax, [rbx+8]
0x14003fe73  test    edi, edi
0x14003fe75  jz      short loc_14003FE81
0x14003fe77  test    rax, rax
0x14003fe7a  jz      short loc_14003FE81
0x14003fe7c  xor     rbx, rax
0x14003fe7f  jmp     short loc_14003FE84
0x14003fe81  mov     rbx, rax
0x14003fe84  test    rbx, rbx
0x14003fe87  jnz     short loc_14003FE58
0x14003fe89  test    rbx, rbx
0x14003fe8c  jz      short loc_14003FECC
0x14003fe8e  mov     rax, [rsi+10h]
0x14003fe92  mov     r8, [rax+18h]
0x14003fe96  mov     eax, [r8+10h]
0x14003fe9a  test    [rbx+30h], eax
0x14003fe9d  jz      short loc_14003FECC
0x14003fe9f  cmp     byte ptr cs:SecLmfPolicyConfig+5, r12b
0x14003fea6  lea     rax, Event52
0x14003fead  mov     [rsp+70h+var_48], rax; __int64
0x14003feb2  mov     r9b, 1
0x14003feb5  setz    r14b
0x14003feb9  mov     dword ptr [rsp+70h+var_50], r12d; int
0x14003febe  mov     r8b, r14b
0x14003fec1  mov     rdx, r15
0x14003fec4  mov     rcx, rsi; CallbackData
0x14003fec7  call    SecAuditFileAccessBlock
0x14003fecc  cmp     [rbp+UnicodeString.Buffer], r12
0x14003fed0  jz      short loc_14003FEE2
0x14003fed2  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14003fed6  call    cs:__imp_RtlFreeUnicodeString
0x14003fedd  nop     dword ptr [rax+rax+00h]
0x14003fee2  mov     rcx, [rbp+P]; P
0x14003fee6  test    rcx, rcx
0x14003fee9  jz      short loc_14003FEFF
0x14003feeb  cmp     [rbp+var_18], r12b
0x14003feef  jz      short loc_14003FEFF
0x14003fef1  xor     edx, edx; Tag
0x14003fef3  call    cs:__imp_ExFreePoolWithTag
0x14003fefa  nop     dword ptr [rax+rax+00h]
0x14003feff  mov     al, r14b
0x14003ff02  mov     rcx, [rbp+var_10]
0x14003ff06  xor     rcx, rsp; StackCookie
0x14003ff09  call    __security_check_cookie
0x14003ff0e  lea     r11, [rsp+70h+var_s0]
0x14003ff13  mov     rbx, [r11+40h]
0x14003ff17  mov     rsi, [r11+48h]
0x14003ff1b  mov     rsp, r11
0x14003ff1e  pop     r15
0x14003ff20  pop     r14
0x14003ff22  pop     r12
0x14003ff24  pop     rdi
0x14003ff25  pop     rbp
0x14003ff26  retn
```
