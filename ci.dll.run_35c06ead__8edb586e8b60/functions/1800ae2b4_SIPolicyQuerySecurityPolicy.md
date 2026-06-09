# SIPolicyQuerySecurityPolicy

- ea: `0x1800ae2b4`
- end: `0x1800ae3e0`
- name: `SIPolicyQuerySecurityPolicy`
- size: `300`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING String1@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING@<r8>, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007a5c4`
- `0x1800ae170`

## callees

- `0x180058bf0`
- `0x180058c6c`
- `0x180090f2c`
- `0x1800ad228`
- `0x1800ae2b4`
- `0x1800e9414`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae2e5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae337`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae354`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae2e5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae337`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800ae354`

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
  if ( RtlEqualUnicodeString(a3, &stru_18002E4C0, 1u) )
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
  else if ( RtlEqualUnicodeString(String1, &stru_180030E38, 1u) && RtlEqualUnicodeString(a2, &stru_180030E48, 1u) )
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
0x1800ae2b4  push    rbx
0x1800ae2b6  push    rbp
0x1800ae2b7  push    rsi
0x1800ae2b8  push    rdi
0x1800ae2b9  push    r14
0x1800ae2bb  sub     rsp, 70h
0x1800ae2bf  mov     r14, r9
0x1800ae2c2  mov     rsi, r8
0x1800ae2c5  mov     rbx, rdx
0x1800ae2c8  mov     rdi, rcx
0x1800ae2cb  call    SIPolicyGetActiveState
0x1800ae2d0  mov     r8b, 1; CaseInSensitive
0x1800ae2d3  mov     [rsp+98h+var_38], rax
0x1800ae2d8  lea     rdx, stru_18002E4C0; String2
0x1800ae2df  mov     rcx, rsi; String1
0x1800ae2e2  mov     rbp, rax
0x1800ae2e5  call    cs:__imp_RtlEqualUnicodeString
0x1800ae2ec  nop     dword ptr [rax+rax+00h]
0x1800ae2f1  test    al, al
0x1800ae2f3  jz      short loc_1800AE32A
0x1800ae2f5  mov     rcx, [rsp+98h+arg_28]
0x1800ae2fd  mov     r9, rsi
0x1800ae300  mov     [rsp+98h+var_68], rcx
0x1800ae305  mov     r8, rbx
0x1800ae308  mov     rcx, [rsp+98h+arg_20]
0x1800ae310  mov     rdx, rdi
0x1800ae313  mov     [rsp+98h+var_70], rcx
0x1800ae318  mov     rcx, rbp
0x1800ae31b  mov     [rsp+98h+var_78], r14
0x1800ae320  call    SIPolicyInternalEnterpriseDefinesClassIDSecureSettingRollup
0x1800ae325  jmp     loc_1800AE3C6
0x1800ae32a  mov     r8b, 1; CaseInSensitive
0x1800ae32d  lea     rdx, stru_180030E38; String2
0x1800ae334  mov     rcx, rdi; String1
0x1800ae337  call    cs:__imp_RtlEqualUnicodeString
0x1800ae33e  nop     dword ptr [rax+rax+00h]
0x1800ae343  test    al, al
0x1800ae345  jz      short loc_1800AE396
0x1800ae347  mov     r8b, 1; CaseInSensitive
0x1800ae34a  lea     rdx, stru_180030E48; String2
0x1800ae351  mov     rcx, rbx; String1
0x1800ae354  call    cs:__imp_RtlEqualUnicodeString
0x1800ae35b  nop     dword ptr [rax+rax+00h]
0x1800ae360  test    al, al
0x1800ae362  jz      short loc_1800AE396
0x1800ae364  mov     rax, [rsp+98h+arg_28]
0x1800ae36c  mov     r9, rsi
0x1800ae36f  mov     [rsp+98h+var_68], rax
0x1800ae374  mov     r8, rbx
0x1800ae377  mov     rax, [rsp+98h+arg_20]
0x1800ae37f  mov     rdx, rdi
0x1800ae382  mov     [rsp+98h+var_70], rax
0x1800ae387  mov     rcx, rbp
0x1800ae38a  mov     [rsp+98h+var_78], r14
0x1800ae38f  call    SIPolicyInternalBooleanSecureSettingRollup
0x1800ae394  jmp     short loc_1800AE3C6
0x1800ae396  mov     rax, [rsp+98h+arg_28]
0x1800ae39e  mov     r9, rsi
0x1800ae3a1  mov     [rsp+98h+var_68], rax
0x1800ae3a6  mov     r8, rbx
0x1800ae3a9  mov     rax, [rsp+98h+arg_20]
0x1800ae3b1  mov     rdx, rdi
0x1800ae3b4  mov     [rsp+98h+var_70], rax
0x1800ae3b9  mov     rcx, rbp
0x1800ae3bc  mov     [rsp+98h+var_78], r14
0x1800ae3c1  call    SIPolicyInternalReturnFirstFoundSecureSetting
0x1800ae3c6  mov     ebx, eax
0x1800ae3c8  lea     rcx, [rsp+98h+var_38]
0x1800ae3cd  call    SIPolicyReleaseState
0x1800ae3d2  mov     eax, ebx
0x1800ae3d4  add     rsp, 70h
0x1800ae3d8  pop     r14
0x1800ae3da  pop     rdi
0x1800ae3db  pop     rsi
0x1800ae3dc  pop     rbp
0x1800ae3dd  pop     rbx
0x1800ae3de  retn
```
