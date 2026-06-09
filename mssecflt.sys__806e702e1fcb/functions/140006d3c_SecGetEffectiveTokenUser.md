# SecGetEffectiveTokenUser

- ea: `0x140006d3c`
- end: `0x140006ec4`
- name: `SecGetEffectiveTokenUser`
- size: `392`
- prototype: `__int64 __usercall@<rax>(PETHREAD Thread@<rcx>, __int64)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400057a8`
- `0x140005a90`
- `0x140007db4`
- `0x140023e10`
- `0x140026a80`
- `0x140026d08`
- `0x140026ec4`
- `0x140027278`
- `0x1400275b4`
- `0x14002792c`
- `0x140027c2c`
- `0x140027ec4`
- `0x1400280f8`
- `0x14002b3a4`
- `0x14002bc14`
- `0x14002be2c`
- `0x14002c080`
- `0x14002ec70`
- `0x14003205c`
- `0x140036860`
- `0x140036df4`
- `0x14003715c`
- `0x1400373fc`
- `0x1400376ec`
- `0x140037a04`
- `0x140037d30`
- `0x140038164`
- `0x14003fd54`

## callees

- `0x140006d3c`
- `0x140011650`

## import_xrefs

- `ntoskrnl!PsGetThreadProcess` at `0x140006e13`
- `ntoskrnl!PsGetThreadProcess` at `0x140006e13`
- `ntoskrnl!SeQueryInformationToken` at `0x140006dd9`
- `ntoskrnl!SeQueryInformationToken` at `0x140006e48`
- `ntoskrnl!SeQueryInformationToken` at `0x140006dd9`
- `ntoskrnl!SeQueryInformationToken` at `0x140006e48`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140006e22`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140006e22`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140006e98`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140011ccb`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140006e98`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140011ccb`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140006dab`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140006dab`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140006e8a`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140011cbd`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140006e8a`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140011cbd`

## pseudocode

```c
__int64 __fastcall SecGetEffectiveTokenUser(PETHREAD Thread, __int64 a2, PVOID *a3, _BYTE *a4, char *a5)
{
  NTSTATUS v8; // edi
  char v9; // si
  PACCESS_TOKEN v10; // rax
  void *v11; // rbx
  struct _KPROCESS *ThreadProcess; // rax
  PACCESS_TOKEN v13; // rax
  PVOID TokenInformation; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int8 v17; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int8 v18[3]; // [rsp+51h] [rbp-47h] BYREF
  int v19; // [rsp+54h] [rbp-44h] BYREF

  v18[0] = 0;
  v17 = 0;
  v19 = 0;
  v8 = 0;
  TokenInformation = 0;
  v9 = 0;
  v10 = PsReferenceImpersonationToken(Thread, v18, &v17, (PSECURITY_IMPERSONATION_LEVEL)&v19);
  v11 = v10;
  if ( v10 )
  {
    v9 = 1;
    v8 = SeQueryInformationToken(v10, TokenUser, &TokenInformation);
    if ( v8 >= 0 )
      *a4 = 1;
  }
  else if ( a2 && *(_QWORD *)(a2 + 296) )
  {
    TokenInformation = *(PVOID *)(a2 + 296);
    *a4 = 0;
  }
  else
  {
    ThreadProcess = PsGetThreadProcess(Thread);
    v13 = PsReferencePrimaryToken(ThreadProcess);
    v11 = v13;
    if ( v13 )
    {
      v8 = SeQueryInformationToken(v13, TokenUser, &TokenInformation);
      if ( v8 >= 0 )
        *a4 = 1;
    }
  }
  if ( a5 )
    *a5 = v9;
  if ( TokenInformation )
    *a3 = TokenInformation;
  if ( v11 )
  {
    if ( v9 )
      PsDereferenceImpersonationToken(v11);
    else
      PsDereferencePrimaryToken(v11);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140006d3c  mov     r11, rsp
0x140006d3f  push    rbx
0x140006d40  push    rsi
0x140006d41  push    rdi
0x140006d42  push    r12
0x140006d44  push    r13
0x140006d46  push    r14
0x140006d48  push    r15
0x140006d4a  sub     rsp, 60h
0x140006d4e  mov     rax, cs:__security_cookie
0x140006d55  xor     rax, rsp
0x140006d58  mov     [rsp+98h+var_40], rax
0x140006d5d  mov     r14, r9
0x140006d60  mov     rax, r8
0x140006d63  mov     [rsp+98h+var_68], rax
0x140006d68  mov     r15, rdx
0x140006d6b  mov     r13, rcx
0x140006d6e  mov     [rsp+98h+var_58], rax
0x140006d73  mov     r12, [rsp+98h+arg_20]
0x140006d7b  mov     [rsp+98h+var_60], r12
0x140006d80  xor     eax, eax
0x140006d82  mov     [r11-70h], rax
0x140006d86  mov     [rsp+98h+var_47], al
0x140006d8a  mov     [rsp+98h+var_48], al
0x140006d8e  mov     [rsp+98h+var_44], eax
0x140006d92  mov     edi, eax
0x140006d94  mov     [r11-50h], rax
0x140006d98  mov     sil, al
0x140006d9b  mov     [rsp+98h+var_78], al
0x140006d9f  lea     r9, [r11-44h]; ImpersonationLevel
0x140006da3  lea     r8, [r11-48h]; EffectiveOnly
0x140006da7  lea     rdx, [r11-47h]; CopyOnOpen
0x140006dab  call    cs:__imp_PsReferenceImpersonationToken
0x140006db2  nop     dword ptr [rax+rax+00h]
0x140006db7  mov     rbx, rax
0x140006dba  mov     [rsp+98h+var_70], rax
0x140006dbf  test    rax, rax
0x140006dc2  jz      short loc_140006DF4
0x140006dc4  mov     sil, 1
0x140006dc7  mov     [rsp+98h+var_78], sil
0x140006dcc  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x140006dd1  mov     edx, 1; TokenInformationClass
0x140006dd6  mov     rcx, rax; Token
0x140006dd9  call    cs:__imp_SeQueryInformationToken
0x140006de0  nop     dword ptr [rax+rax+00h]
0x140006de5  mov     edi, eax
0x140006de7  mov     [rsp+98h+var_74], eax
0x140006deb  test    eax, eax
0x140006ded  js      short loc_140006E62
0x140006def  mov     [r14], sil
0x140006df2  jmp     short loc_140006E62
0x140006df4  test    r15, r15
0x140006df7  jz      short loc_140006E10
0x140006df9  mov     rax, [r15+128h]
0x140006e00  test    rax, rax
0x140006e03  jz      short loc_140006E10
0x140006e05  mov     [rsp+98h+TokenInformation], rax
0x140006e0a  mov     byte ptr [r14], 0
0x140006e0e  jmp     short loc_140006E62
0x140006e10  mov     rcx, r13; Thread
0x140006e13  call    cs:__imp_PsGetThreadProcess
0x140006e1a  nop     dword ptr [rax+rax+00h]
0x140006e1f  mov     rcx, rax; Process
0x140006e22  call    cs:__imp_PsReferencePrimaryToken
0x140006e29  nop     dword ptr [rax+rax+00h]
0x140006e2e  mov     rbx, rax
0x140006e31  mov     [rsp+98h+var_70], rax
0x140006e36  test    rax, rax
0x140006e39  jz      short loc_140006E62
0x140006e3b  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x140006e40  mov     edx, 1; TokenInformationClass
0x140006e45  mov     rcx, rax; Token
0x140006e48  call    cs:__imp_SeQueryInformationToken
0x140006e4f  nop     dword ptr [rax+rax+00h]
0x140006e54  mov     edi, eax
0x140006e56  mov     [rsp+98h+var_74], eax
0x140006e5a  test    eax, eax
0x140006e5c  js      short loc_140006E62
0x140006e5e  mov     byte ptr [r14], 1
0x140006e62  test    r12, r12
0x140006e65  jz      short loc_140006E6B
0x140006e67  mov     [r12], sil
0x140006e6b  mov     rax, [rsp+98h+TokenInformation]
0x140006e70  test    rax, rax
0x140006e73  jz      short loc_140006E7D
0x140006e75  mov     rcx, [rsp+98h+var_68]
0x140006e7a  mov     [rcx], rax
0x140006e7d  test    rbx, rbx
0x140006e80  jz      short loc_140006EA4
0x140006e82  mov     rcx, rbx; PrimaryToken
0x140006e85  test    sil, sil
0x140006e88  jz      short loc_140006E98
0x140006e8a  call    cs:__imp_PsDereferenceImpersonationToken
0x140006e91  nop     dword ptr [rax+rax+00h]
0x140006e96  jmp     short loc_140006EA4
0x140006e98  call    cs:__imp_PsDereferencePrimaryToken
0x140006e9f  nop     dword ptr [rax+rax+00h]
0x140006ea4  mov     eax, edi
0x140006ea6  mov     rcx, [rsp+98h+var_40]
0x140006eab  xor     rcx, rsp; StackCookie
0x140006eae  call    __security_check_cookie
0x140006eb3  add     rsp, 60h
0x140006eb7  pop     r15
0x140006eb9  pop     r14
0x140006ebb  pop     r13
0x140006ebd  pop     r12
0x140006ebf  pop     rdi
0x140006ec0  pop     rsi
0x140006ec1  pop     rbx
0x140006ec2  retn
0x140011c87  push    rbp
0x140011c89  sub     rsp, 20h
0x140011c8d  mov     rbp, rdx
0x140011c90  mov     rcx, [rbp+38h]
0x140011c94  test    rcx, rcx
0x140011c97  jz      short loc_140011C9E
0x140011c99  mov     al, [rbp+20h]
0x140011c9c  mov     [rcx], al
0x140011c9e  mov     rcx, [rbp+48h]
0x140011ca2  test    rcx, rcx
0x140011ca5  jz      short loc_140011CAE
0x140011ca7  mov     rax, [rbp+40h]
0x140011cab  mov     [rax], rcx
0x140011cae  mov     rcx, [rbp+28h]; PrimaryToken
0x140011cb2  test    rcx, rcx
0x140011cb5  jz      short loc_140011CD8
0x140011cb7  cmp     byte ptr [rbp+20h], 0
0x140011cbb  jz      short loc_140011CCB
0x140011cbd  call    cs:__imp_PsDereferenceImpersonationToken
0x140011cc4  nop     dword ptr [rax+rax+00h]
0x140011cc9  jmp     short loc_140011CD8
0x140011ccb  call    cs:__imp_PsDereferencePrimaryToken
0x140011cd2  nop     dword ptr [rax+rax+00h]
0x140011cd7  nop
0x140011cd8  add     rsp, 20h
0x140011cdc  pop     rbp
0x140011cdd  retn
```
