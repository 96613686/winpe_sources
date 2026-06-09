# NtlmCredIsoInProc::PasswordValidateInteractive(uchar,_NETLOGON_INTERACTIVE_INFO *,_MSV1_0_SECRETS_WRAPPER *,ulong *,_USER_SESSION_KEY *,_CLEAR_BLOCK *,int *)

- ea: `0x180052ab0`
- end: `0x180052b78`
- name: `?PasswordValidateInteractive@NtlmCredIsoInProc@@UEAAJEPEAU_NETLOGON_INTERACTIVE_INFO@@PEAU_MSV1_0_SECRETS_WRAPPER@@PEAKPEAU_USER_SESSION_KEY@@PEAU_CLEAR_BLOCK@@PEAH@Z`
- size: `200`
- prototype: `__int64 __fastcall(NtlmCredIsoInProc *__hidden this, unsigned __int8, struct _NETLOGON_INTERACTIVE_INFO *, struct _MSV1_0_SECRETS_WRAPPER *, unsigned int *, struct _USER_SESSION_KEY *, struct _CLEAR_BLOCK *, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000ed70`
- `0x18002fb50`

## import_xrefs

- `NtlmShared!MsvpPasswordValidate` at `0x180052b35`
- `NtlmShared!MsvpPasswordValidate` at `0x180052b35`
- `NtlmShared!MsvpCredentialToCachePasswords` at `0x180052b10`
- `NtlmShared!MsvpCredentialToCachePasswords` at `0x180052b10`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoInProc::PasswordValidateInteractive(
        NtlmCredIsoInProc *this,
        char a2,
        struct _NETLOGON_INTERACTIVE_INFO *a3,
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
  *a8 = (unsigned __int8)MsvpPasswordValidate(v10, 1, a3, v12, a5, a6, a7);
  NtlmTraceStatusViaWpp_0("NtlmCredIsoInProc::PasswordValidateInteractive", 207, 0);
  return 0;
}

```

## disassembly

```asm
0x180052ab0  mov     [rsp+arg_0], rbx
0x180052ab5  push    rbp
0x180052ab6  push    rsi
0x180052ab7  push    rdi
0x180052ab8  push    r14
0x180052aba  push    r15
0x180052abc  sub     rsp, 70h
0x180052ac0  mov     rax, cs:__security_cookie
0x180052ac7  xor     rax, rsp
0x180052aca  mov     [rsp+98h+var_30], rax
0x180052acf  mov     rsi, [rsp+98h+arg_20]
0x180052ad7  xorps   xmm0, xmm0
0x180052ada  mov     rdi, [rsp+98h+arg_28]
0x180052ae2  mov     r15b, dl
0x180052ae5  mov     rbx, [rsp+98h+arg_30]
0x180052aed  lea     rdx, [rsp+98h+var_58]
0x180052af2  mov     r14, [rsp+98h+arg_38]
0x180052afa  xor     eax, eax
0x180052afc  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x180052b01  mov     rcx, r9
0x180052b04  mov     dword ptr [rsp+98h+var_48+0Fh], eax
0x180052b08  mov     rbp, r8
0x180052b0b  movups  [rsp+98h+var_58], xmm0
0x180052b10  call    cs:__imp_MsvpCredentialToCachePasswords
0x180052b16  mov     [rsp+98h+var_68], rbx
0x180052b1b  lea     r9, [rsp+98h+var_58]
0x180052b20  mov     [rsp+98h+var_70], rdi
0x180052b25  mov     r8, rbp
0x180052b28  mov     edx, 1
0x180052b2d  mov     [rsp+98h+var_78], rsi
0x180052b32  mov     cl, r15b
0x180052b35  call    cs:__imp_MsvpPasswordValidate
0x180052b3b  movzx   eax, al
0x180052b3e  xor     r8d, r8d
0x180052b41  lea     rcx, aNtlmcredisoinp_5; "NtlmCredIsoInProc::PasswordValidateInte"...
0x180052b48  mov     [r14], eax
0x180052b4b  mov     edx, 0CFh
0x180052b50  call    NtlmTraceStatusViaWpp_0
0x180052b55  xor     eax, eax
0x180052b57  mov     rcx, [rsp+98h+var_30]
0x180052b5c  xor     rcx, rsp; StackCookie
0x180052b5f  call    __security_check_cookie
0x180052b64  mov     rbx, [rsp+98h+arg_0]
0x180052b6c  add     rsp, 70h
0x180052b70  pop     r15
0x180052b72  pop     r14
0x180052b74  pop     rdi
0x180052b75  pop     rsi
0x180052b76  pop     rbp
0x180052b77  retn
```
