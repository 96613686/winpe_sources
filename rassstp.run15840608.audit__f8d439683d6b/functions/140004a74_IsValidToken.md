# IsValidToken

- ea: `0x140004a74`
- end: `0x140004cba`
- name: `IsValidToken`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400034d0`

## callees

- `0x140002bd8`
- `0x140002c08`
- `0x140004a74`
- `0x140005e10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140004c40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004c40`
- `ntoskrnl!SeQueryInformationToken` at `0x140004b86`
- `ntoskrnl!SeQueryInformationToken` at `0x140004b86`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140004c56`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140004c56`
- `ntoskrnl!RtlEqualSid` at `0x140004bf9`
- `ntoskrnl!RtlEqualSid` at `0x140004c16`
- `ntoskrnl!RtlEqualSid` at `0x140004bf9`
- `ntoskrnl!RtlEqualSid` at `0x140004c16`
- `ntoskrnl!SeLockSubjectContext` at `0x140004b59`
- `ntoskrnl!SeLockSubjectContext` at `0x140004b59`

## pseudocode

```c
char __fastcall IsValidToken(__int64 a1, _BYTE *a2)
{
  char v2; // r14
  struct _SECURITY_SUBJECT_CONTEXT *v5; // rsi
  void *v6; // rcx
  unsigned int *v7; // rcx
  unsigned int i; // ebx
  PVOID TokenInformation; // [rsp+20h] [rbp-50h] BYREF
  _DWORD Sid1[8]; // [rsp+28h] [rbp-48h] BYREF
  _DWORD v12[8]; // [rsp+48h] [rbp-28h] BYREF

  Sid1[0] = 1537;
  v2 = 0;
  TokenInformation = 0;
  *a2 = 0;
  Sid1[1] = 83886080;
  Sid1[2] = 80;
  Sid1[3] = -859265410;
  Sid1[4] = 799518250;
  Sid1[5] = -503583807;
  Sid1[6] = -1066671174;
  Sid1[7] = -1356082982;
  v12[0] = 1537;
  v12[1] = 83886080;
  v12[2] = 80;
  v12[3] = -118600422;
  v12[4] = 305252471;
  v12[5] = -2038250239;
  v12[6] = -1580777525;
  v12[7] = -742434506;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids);
  v5 = (struct _SECURITY_SUBJECT_CONTEXT *)(a1 + 32);
  SeLockSubjectContext((PSECURITY_SUBJECT_CONTEXT)(a1 + 32));
  v6 = *(void **)(a1 + 32);
  if ( v6 )
  {
    if ( *(int *)(a1 + 40) <= 1 )
      goto LABEL_24;
  }
  else
  {
    v6 = *(void **)(a1 + 48);
  }
  if ( SeQueryInformationToken(v6, TokenGroups, &TokenInformation) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids);
    }
  }
  else
  {
    v7 = (unsigned int *)TokenInformation;
    for ( i = 0; i < *v7; ++i )
    {
      if ( (v7[4 * i + 4] & 0xC) == 0xC )
      {
        if ( RtlEqualSid(Sid1, *(PSID *)&v7[4 * i + 2]) )
        {
          *a2 = 1;
LABEL_21:
          v7 = (unsigned int *)TokenInformation;
          v2 = 1;
          break;
        }
        if ( RtlEqualSid(v12, *((PSID *)TokenInformation + 2 * i + 1)) )
          goto LABEL_21;
        v7 = (unsigned int *)TokenInformation;
      }
    }
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
  }
LABEL_24:
  SeUnlockSubjectContext(v5);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x140004a74  mov     [rsp-28h+arg_10], rbx
0x140004a79  mov     [rsp-28h+arg_18], rsi
0x140004a7e  push    rbp
0x140004a7f  push    rdi
0x140004a80  push    r12
0x140004a82  push    r14
0x140004a84  push    r15
0x140004a86  mov     rbp, rsp
0x140004a89  sub     rsp, 70h
0x140004a8d  mov     rax, cs:__security_cookie
0x140004a94  xor     rax, rsp
0x140004a97  mov     [rbp+var_8], rax
0x140004a9b  xor     r12d, r12d
0x140004a9e  mov     [rbp+Sid1], 601h
0x140004aa5  mov     r14b, r12b
0x140004aa8  mov     [rbp+TokenInformation], r12
0x140004aac  mov     [rdx], r12b
0x140004aaf  mov     r15, rdx
0x140004ab2  mov     rbx, rcx
0x140004ab5  mov     [rbp+var_44], 5000000h
0x140004abc  mov     [rbp+var_40], 50h ; 'P'
0x140004ac3  mov     [rbp+var_3C], 0CCC8A67Eh
0x140004aca  mov     [rbp+var_38], 2FA7AE2Ah
0x140004ad1  mov     [rbp+var_34], 0E1FBEBC1h
0x140004ad8  mov     [rbp+var_30], 0C06BE3BAh
0x140004adf  mov     [rbp+var_2C], 0AF2BD0DAh
0x140004ae6  mov     [rbp+var_28], 601h
0x140004aed  mov     [rbp+var_24], 5000000h
0x140004af4  mov     [rbp+var_20], 50h ; 'P'
0x140004afb  mov     [rbp+var_1C], 0F8EE4D1Ah
0x140004b02  mov     [rbp+var_18], 1231C877h
0x140004b09  mov     [rbp+var_14], 8682C501h
0x140004b10  mov     [rbp+var_10], 0A1C73FCBh
0x140004b17  mov     [rbp+var_C], 0D3BF5936h
0x140004b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b25  lea     rdi, WPP_GLOBAL_Control
0x140004b2c  cmp     rcx, rdi
0x140004b2f  jz      short loc_140004B52
0x140004b31  mov     eax, [rcx+2Ch]
0x140004b34  and     eax, 81h
0x140004b39  cmp     al, 81h
0x140004b3b  jnz     short loc_140004B52
0x140004b3d  mov     rcx, [rcx+18h]
0x140004b41  lea     edx, [r12+11h]
0x140004b46  lea     r8, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids
0x140004b4d  call    WPP_SF_
0x140004b52  lea     rsi, [rbx+20h]
0x140004b56  mov     rcx, rsi; SubjectContext
0x140004b59  call    cs:__imp_SeLockSubjectContext
0x140004b60  nop     dword ptr [rax+rax+00h]
0x140004b65  mov     rcx, [rsi]
0x140004b68  test    rcx, rcx
0x140004b6b  jz      short loc_140004B79
0x140004b6d  cmp     dword ptr [rbx+28h], 1
0x140004b71  jle     loc_140004C53
0x140004b77  jmp     short loc_140004B7D
0x140004b79  mov     rcx, [rbx+30h]; Token
0x140004b7d  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140004b81  mov     edx, 2; TokenInformationClass
0x140004b86  call    cs:__imp_SeQueryInformationToken
0x140004b8d  nop     dword ptr [rax+rax+00h]
0x140004b92  mov     r9d, eax
0x140004b95  test    eax, eax
0x140004b97  jz      short loc_140004BD5
0x140004b99  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ba0  cmp     rcx, rdi
0x140004ba3  jz      loc_140004C53
0x140004ba9  mov     eax, [rcx+2Ch]
0x140004bac  test    al, 1
0x140004bae  jz      loc_140004C53
0x140004bb4  cmp     byte ptr [rcx+29h], 1
0x140004bb8  jb      loc_140004C53
0x140004bbe  mov     rcx, [rcx+18h]
0x140004bc2  lea     r8, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids
0x140004bc9  mov     edx, 12h
0x140004bce  call    WPP_SF_d
0x140004bd3  jmp     short loc_140004C53
0x140004bd5  mov     rcx, [rbp+TokenInformation]
0x140004bd9  mov     ebx, r12d
0x140004bdc  cmp     ebx, [rcx]
0x140004bde  jnb     short loc_140004C39
0x140004be0  mov     edi, ebx
0x140004be2  add     rdi, rdi
0x140004be5  mov     eax, [rcx+rdi*8+10h]
0x140004be9  and     eax, 0Ch
0x140004bec  cmp     al, 0Ch
0x140004bee  jnz     short loc_140004C2A
0x140004bf0  mov     rdx, [rcx+rdi*8+8]; Sid2
0x140004bf5  lea     rcx, [rbp+Sid1]; Sid1
0x140004bf9  call    cs:__imp_RtlEqualSid
0x140004c00  nop     dword ptr [rax+rax+00h]
0x140004c05  test    al, al
0x140004c07  jnz     short loc_140004C2E
0x140004c09  mov     rdx, [rbp+TokenInformation]
0x140004c0d  lea     rcx, [rbp+var_28]; Sid1
0x140004c11  mov     rdx, [rdx+rdi*8+8]; Sid2
0x140004c16  call    cs:__imp_RtlEqualSid
0x140004c1d  nop     dword ptr [rax+rax+00h]
0x140004c22  test    al, al
0x140004c24  jnz     short loc_140004C32
0x140004c26  mov     rcx, [rbp+TokenInformation]
0x140004c2a  inc     ebx
0x140004c2c  jmp     short loc_140004BDC
0x140004c2e  mov     byte ptr [r15], 1
0x140004c32  mov     rcx, [rbp+TokenInformation]; P
0x140004c36  mov     r14b, 1
0x140004c39  test    rcx, rcx
0x140004c3c  jz      short loc_140004C4C
0x140004c3e  xor     edx, edx; Tag
0x140004c40  call    cs:__imp_ExFreePoolWithTag
0x140004c47  nop     dword ptr [rax+rax+00h]
0x140004c4c  lea     rdi, WPP_GLOBAL_Control
0x140004c53  mov     rcx, rsi; SubjectContext
0x140004c56  call    cs:__imp_SeUnlockSubjectContext
0x140004c5d  nop     dword ptr [rax+rax+00h]
0x140004c62  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c69  cmp     rcx, rdi
0x140004c6c  jz      short loc_140004C91
0x140004c6e  mov     edx, [rcx+2Ch]
0x140004c71  and     edx, 81h
0x140004c77  cmp     dl, 81h
0x140004c7a  jnz     short loc_140004C91
0x140004c7c  mov     rcx, [rcx+18h]
0x140004c80  lea     r8, WPP_b18e4254e1cd3db166f3c49730626150_Traceguids
0x140004c87  mov     edx, 13h
0x140004c8c  call    WPP_SF_
0x140004c91  mov     al, r14b
0x140004c94  mov     rcx, [rbp+var_8]
0x140004c98  xor     rcx, rsp; StackCookie
0x140004c9b  call    __security_check_cookie
0x140004ca0  lea     r11, [rsp+70h+var_s0]
0x140004ca5  mov     rbx, [r11+40h]
0x140004ca9  mov     rsi, [r11+48h]
0x140004cad  mov     rsp, r11
0x140004cb0  pop     r15
0x140004cb2  pop     r14
0x140004cb4  pop     r12
0x140004cb6  pop     rdi
0x140004cb7  pop     rbp
0x140004cb8  retn
```
