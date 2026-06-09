# NtlmCredIsoInProc::PasswordValidateNetwork(uchar,_NETLOGON_NETWORK_INFO *,_MSV1_0_SECRETS_WRAPPER *,ulong *,_USER_SESSION_KEY *,_CLEAR_BLOCK *,int *)

- ea: `0x180052b80`
- end: `0x180052c48`
- name: `?PasswordValidateNetwork@NtlmCredIsoInProc@@UEAAJEPEAU_NETLOGON_NETWORK_INFO@@PEAU_MSV1_0_SECRETS_WRAPPER@@PEAKPEAU_USER_SESSION_KEY@@PEAU_CLEAR_BLOCK@@PEAH@Z`
- size: `200`
- prototype: `__int64 __fastcall(NtlmCredIsoInProc *__hidden this, unsigned __int8, struct _NETLOGON_NETWORK_INFO *, struct _MSV1_0_SECRETS_WRAPPER *, unsigned int *, struct _USER_SESSION_KEY *, struct _CLEAR_BLOCK *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ed70`
- `0x18002fb50`

## import_xrefs

- `NtlmShared!MsvpPasswordValidate` at `0x180052c05`
- `NtlmShared!MsvpPasswordValidate` at `0x180052c05`
- `NtlmShared!MsvpCredentialToCachePasswords` at `0x180052be0`
- `NtlmShared!MsvpCredentialToCachePasswords` at `0x180052be0`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoInProc::PasswordValidateNetwork(
        NtlmCredIsoInProc *this,
        char a2,
        struct _NETLOGON_NETWORK_INFO *a3,
        struct _MSV1_0_SECRETS_WRAPPER *a4,
        unsigned int *a5,
        struct _USER_SESSION_KEY *a6,
        struct _CLEAR_BLOCK *a7,
        int *a8)
{
  __int64 v10; // rcx
  _BYTE v12[35]; // [rsp+40h] [rbp-58h] BYREF

  memset(v12, 0, sizeof(v12));
  MsvpCredentialToCachePasswords(a4, v12);
  LOBYTE(v10) = a2;
  *a8 = (unsigned __int8)MsvpPasswordValidate(v10, 2, a3, v12, a5, a6, a7);
  NtlmTraceStatusViaWpp_0("NtlmCredIsoInProc::PasswordValidateNetwork", 240, 0);
  return 0;
}

```

## disassembly

```asm
0x180052b80  mov     [rsp+arg_0], rbx
0x180052b85  push    rbp
0x180052b86  push    rsi
0x180052b87  push    rdi
0x180052b88  push    r14
0x180052b8a  push    r15
0x180052b8c  sub     rsp, 70h
0x180052b90  mov     rax, cs:__security_cookie
0x180052b97  xor     rax, rsp
0x180052b9a  mov     [rsp+98h+var_30], rax
0x180052b9f  mov     rsi, [rsp+98h+arg_20]
0x180052ba7  xorps   xmm0, xmm0
0x180052baa  mov     rdi, [rsp+98h+arg_28]
0x180052bb2  mov     r15b, dl
0x180052bb5  mov     rbx, [rsp+98h+arg_30]
0x180052bbd  lea     rdx, [rsp+98h+var_58]
0x180052bc2  mov     r14, [rsp+98h+arg_38]
0x180052bca  xor     eax, eax
0x180052bcc  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180052bd1  mov     rcx, r9
0x180052bd4  mov     dword ptr [rsp+98h+var_48+0Fh], eax
0x180052bd8  mov     rbp, r8
0x180052bdb  movups  [rsp+98h+var_58], xmm0
0x180052be0  call    cs:__imp_MsvpCredentialToCachePasswords
0x180052be6  mov     [rsp+98h+var_68], rbx
0x180052beb  lea     r9, [rsp+98h+var_58]
0x180052bf0  mov     [rsp+98h+var_70], rdi
0x180052bf5  mov     r8, rbp
0x180052bf8  mov     edx, 2
0x180052bfd  mov     [rsp+98h+var_78], rsi
0x180052c02  mov     cl, r15b
0x180052c05  call    cs:__imp_MsvpPasswordValidate
0x180052c0b  movzx   eax, al
0x180052c0e  xor     r8d, r8d
0x180052c11  lea     rcx, aNtlmcredisoinp; "NtlmCredIsoInProc::PasswordValidateNetw"...
0x180052c18  mov     [r14], eax
0x180052c1b  mov     edx, 0F0h
0x180052c20  call    NtlmTraceStatusViaWpp_0
0x180052c25  xor     eax, eax
0x180052c27  mov     rcx, [rsp+98h+var_30]
0x180052c2c  xor     rcx, rsp; StackCookie
0x180052c2f  call    __security_check_cookie
0x180052c34  mov     rbx, [rsp+98h+arg_0]
0x180052c3c  add     rsp, 70h
0x180052c40  pop     r15
0x180052c42  pop     r14
0x180052c44  pop     rdi
0x180052c45  pop     rsi
0x180052c46  pop     rbp
0x180052c47  retn
```
