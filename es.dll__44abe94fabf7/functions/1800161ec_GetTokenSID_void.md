# GetTokenSID(void *)

- ea: `0x1800161ec`
- end: `0x18001628f`
- name: `?GetTokenSID@@YAPEAGPEAX@Z`
- size: `163`
- prototype: `unsigned __int16 *__fastcall(HANDLE TokenHandle)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180012bcc`
- `0x18001612c`
- `0x180016548`

## callees

- `0x1800161ec`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016225`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001625c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180016225`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001625c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001622f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001622f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800444a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800444a8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001626a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001626a`

## pseudocode

```c
LPWSTR __fastcall GetTokenSID(HANDLE TokenHandle)
{
  PSID *v2; // rbx
  SIZE_T cb; // [rsp+58h] [rbp+10h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+18h] BYREF

  StringSid = 0;
  LODWORD(cb) = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&cb);
  v2 = (PSID *)CoTaskMemAlloc((unsigned int)cb);
  if ( v2 )
  {
    GetTokenInformation(TokenHandle, TokenUser, v2, cb, (PDWORD)&cb);
    ConvertSidToStringSidW(*v2, &StringSid);
    CoTaskMemFree(v2);
  }
  return StringSid;
}

```

## disassembly

```asm
0x1800161ec  mov     rax, rsp
0x1800161ef  mov     [rax+8], rbx
0x1800161f3  push    rdi
0x1800161f4  sub     rsp, 40h
0x1800161f8  mov     rdi, rcx
0x1800161fb  mov     qword ptr [rax-18h], 0
0x180016203  mov     qword ptr [rax+18h], 0
0x18001620b  mov     dword ptr [rax+10h], 0
0x180016212  lea     rax, [rax+10h]
0x180016216  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001621b  xor     r9d, r9d; TokenInformationLength
0x18001621e  xor     r8d, r8d; TokenInformation
0x180016221  lea     edx, [r9+1]; TokenInformationClass
0x180016225  call    cs:__imp_GetTokenInformation
0x18001622b  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x18001622f  call    cs:__imp_CoTaskMemAlloc
0x180016235  mov     rbx, rax
0x180016238  mov     [rsp+48h+var_18], rax
0x18001623d  test    rax, rax
0x180016240  jz      short loc_180016271
0x180016242  lea     rax, [rsp+48h+cb]
0x180016247  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001624c  mov     r9d, dword ptr [rsp+48h+cb]; TokenInformationLength
0x180016251  mov     r8, rbx; TokenInformation
0x180016254  mov     edx, 1; TokenInformationClass
0x180016259  mov     rcx, rdi; TokenHandle
0x18001625c  call    cs:__imp_GetTokenInformation
0x180016262  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180016267  mov     rcx, [rbx]; Sid
0x18001626a  call    cs:__imp_ConvertSidToStringSidW
0x180016270  nop
0x180016271  test    rbx, rbx
0x180016274  jz      short loc_18001627F
0x180016276  mov     rcx, rbx; pv
0x180016279  call    cs:__imp_CoTaskMemFree
0x18001627f  mov     rax, [rsp+48h+StringSid]
0x180016284  mov     rbx, [rsp+48h+arg_0]
0x180016289  add     rsp, 40h
0x18001628d  pop     rdi
0x18001628e  retn
0x180044496  push    rbp
0x180044498  sub     rsp, 30h
0x18004449c  mov     rbp, rdx
0x18004449f  mov     rcx, [rbp+30h]; pv
0x1800444a3  test    rcx, rcx
0x1800444a6  jz      short loc_1800444AF
0x1800444a8  call    cs:__imp_CoTaskMemFree
0x1800444ae  nop
0x1800444af  add     rsp, 30h
0x1800444b3  pop     rbp
0x1800444b4  retn
```
