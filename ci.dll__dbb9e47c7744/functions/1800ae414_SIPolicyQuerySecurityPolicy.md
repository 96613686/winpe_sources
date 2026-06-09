# SIPolicyQuerySecurityPolicy

- ea: `0x1800ae414`
- end: `0x1800ae540`
- name: `SIPolicyQuerySecurityPolicy`
- size: `300`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING String1@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING@<r8>, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007a2b4`
- `0x1800ae2d0`

## callees

- `0x180058cc8`
- `0x180058d44`
- `0x18009fca0`
- `0x1800a2194`
- `0x1800ae414`
- `0x1800e8d5c`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae445`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae497`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae4b4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae445`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae497`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae4b4`

## pseudocode

```c
__int64 __fastcall SIPolicyQuerySecurityPolicy(
        PCUNICODE_STRING String1,
        PCUNICODE_STRING a2,
        PCUNICODE_STRING a3,
        int *a4,
        char *a5,
        unsigned int *a6)
{
  unsigned int FoundSecureSetting; // eax
  unsigned int v11; // ebx
  __int64 v13[7]; // [rsp+60h] [rbp-38h] BYREF

  v13[0] = SIPolicyGetActiveState();
  if ( RtlEqualUnicodeString(a3, &stru_18002EF18, 1u) )
  {
    FoundSecureSetting = SIPolicyInternalEnterpriseDefinesClassIDSecureSettingRollup(
                           v13[0],
                           (int)String1,
                           (int)a2,
                           (__int64)a3,
                           a4,
                           a5,
                           a6);
  }
  else if ( RtlEqualUnicodeString(String1, &stru_180030E58, 1u) && RtlEqualUnicodeString(a2, &stru_180030E68, 1u) )
  {
    FoundSecureSetting = SIPolicyInternalBooleanSecureSettingRollup(
                           v13[0],
                           (_DWORD)String1,
                           (_DWORD)a2,
                           (_DWORD)a3,
                           (__int64)a4,
                           (__int64)a5,
                           (__int64)a6);
  }
  else
  {
    FoundSecureSetting = SIPolicyInternalReturnFirstFoundSecureSetting(
                           v13[0],
                           (_DWORD)String1,
                           (_DWORD)a2,
                           (_DWORD)a3,
                           (__int64)a4,
                           (__int64)a5,
                           (__int64)a6);
  }
  v11 = FoundSecureSetting;
  SIPolicyReleaseState(v13);
  return v11;
}

```

## disassembly

```asm
0x1800ae414  push    rbx
0x1800ae416  push    rbp
0x1800ae417  push    rsi
0x1800ae418  push    rdi
0x1800ae419  push    r14
0x1800ae41b  sub     rsp, 70h
0x1800ae41f  mov     r14, r9
0x1800ae422  mov     rsi, r8
0x1800ae425  mov     rbx, rdx
0x1800ae428  mov     rdi, rcx
0x1800ae42b  call    SIPolicyGetActiveState
0x1800ae430  mov     r8b, 1; CaseInSensitive
0x1800ae433  mov     [rsp+98h+var_38], rax
0x1800ae438  lea     rdx, stru_18002EF18; String2
0x1800ae43f  mov     rcx, rsi; String1
0x1800ae442  mov     rbp, rax
0x1800ae445  call    cs:__imp_RtlEqualUnicodeString
0x1800ae44c  nop     dword ptr [rax+rax+00h]
0x1800ae451  test    al, al
0x1800ae453  jz      short loc_1800AE48A
0x1800ae455  mov     rcx, [rsp+98h+arg_28]
0x1800ae45d  mov     r9, rsi
0x1800ae460  mov     [rsp+98h+var_68], rcx
0x1800ae465  mov     r8, rbx
0x1800ae468  mov     rcx, [rsp+98h+arg_20]
0x1800ae470  mov     rdx, rdi
0x1800ae473  mov     [rsp+98h+var_70], rcx
0x1800ae478  mov     rcx, rbp
0x1800ae47b  mov     [rsp+98h+var_78], r14
0x1800ae480  call    SIPolicyInternalEnterpriseDefinesClassIDSecureSettingRollup
0x1800ae485  jmp     loc_1800AE526
0x1800ae48a  mov     r8b, 1; CaseInSensitive
0x1800ae48d  lea     rdx, stru_180030E58; String2
0x1800ae494  mov     rcx, rdi; String1
0x1800ae497  call    cs:__imp_RtlEqualUnicodeString
0x1800ae49e  nop     dword ptr [rax+rax+00h]
0x1800ae4a3  test    al, al
0x1800ae4a5  jz      short loc_1800AE4F6
0x1800ae4a7  mov     r8b, 1; CaseInSensitive
0x1800ae4aa  lea     rdx, stru_180030E68; String2
0x1800ae4b1  mov     rcx, rbx; String1
0x1800ae4b4  call    cs:__imp_RtlEqualUnicodeString
0x1800ae4bb  nop     dword ptr [rax+rax+00h]
0x1800ae4c0  test    al, al
0x1800ae4c2  jz      short loc_1800AE4F6
0x1800ae4c4  mov     rax, [rsp+98h+arg_28]
0x1800ae4cc  mov     r9, rsi
0x1800ae4cf  mov     [rsp+98h+var_68], rax
0x1800ae4d4  mov     r8, rbx
0x1800ae4d7  mov     rax, [rsp+98h+arg_20]
0x1800ae4df  mov     rdx, rdi
0x1800ae4e2  mov     [rsp+98h+var_70], rax
0x1800ae4e7  mov     rcx, rbp
0x1800ae4ea  mov     [rsp+98h+var_78], r14
0x1800ae4ef  call    SIPolicyInternalBooleanSecureSettingRollup
0x1800ae4f4  jmp     short loc_1800AE526
0x1800ae4f6  mov     rax, [rsp+98h+arg_28]
0x1800ae4fe  mov     r9, rsi
0x1800ae501  mov     [rsp+98h+var_68], rax
0x1800ae506  mov     r8, rbx
0x1800ae509  mov     rax, [rsp+98h+arg_20]
0x1800ae511  mov     rdx, rdi
0x1800ae514  mov     [rsp+98h+var_70], rax
0x1800ae519  mov     rcx, rbp
0x1800ae51c  mov     [rsp+98h+var_78], r14
0x1800ae521  call    SIPolicyInternalReturnFirstFoundSecureSetting
0x1800ae526  mov     ebx, eax
0x1800ae528  lea     rcx, [rsp+98h+var_38]
0x1800ae52d  call    SIPolicyReleaseState
0x1800ae532  mov     eax, ebx
0x1800ae534  add     rsp, 70h
0x1800ae538  pop     r14
0x1800ae53a  pop     rdi
0x1800ae53b  pop     rsi
0x1800ae53c  pop     rbp
0x1800ae53d  pop     rbx
0x1800ae53e  retn
```
