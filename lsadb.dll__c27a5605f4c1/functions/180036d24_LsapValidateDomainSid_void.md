# LsapValidateDomainSid(void *)

- ea: `0x180036d24`
- end: `0x180036dc1`
- name: `?LsapValidateDomainSid@@YAEPEAX@Z`
- size: `157`
- prototype: `unsigned __int8 __fastcall(PSID Sid1)`
- caller_count: `9`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d4b0`
- `0x18000d5e0`
- `0x18000e920`
- `0x18000fb10`
- `0x180027614`
- `0x180027a34`
- `0x180035c68`
- `0x180035ccc`
- `0x180035d6c`

## callees

- `0x180001670`
- `0x180036d24`
- `0x180036e30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180036d6f`
- `api-ms-win-security-base-l1-1-0!GetWindowsAccountDomainSid` at `0x180036d6f`
- `ntdll!RtlEqualSid` at `0x180036d81`
- `ntdll!RtlEqualSid` at `0x180036d81`

## pseudocode

```c
bool __fastcall LsapValidateDomainSid(PSID Sid1)
{
  char v2; // bl
  DWORD cbDomainSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pDomainSid[80]; // [rsp+30h] [rbp-68h] BYREF

  v2 = 0;
  if ( Sid1 )
  {
    cbDomainSid[0] = 68;
    if ( LsapValidateSid(Sid1) )
    {
      if ( GetWindowsAccountDomainSid(Sid1, pDomainSid, cbDomainSid) )
        return RtlEqualSid(Sid1, pDomainSid) != 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180036d24  mov     [rsp+arg_8], rbx
0x180036d29  push    rdi
0x180036d2a  sub     rsp, 90h
0x180036d31  mov     rax, cs:__security_cookie
0x180036d38  xor     rax, rsp
0x180036d3b  mov     [rsp+98h+var_18], rax
0x180036d43  mov     rdi, rcx
0x180036d46  xor     bl, bl
0x180036d48  mov     [rsp+98h+var_78], bl
0x180036d4c  test    rcx, rcx
0x180036d4f  jz      short loc_180036D98
0x180036d51  mov     [rsp+98h+cbDomainSid], 44h ; 'D'
0x180036d59  call    ?LsapValidateSid@@YAEPEAX@Z; LsapValidateSid(void *)
0x180036d5e  test    al, al
0x180036d60  jz      short loc_180036D98
0x180036d62  lea     r8, [rsp+98h+cbDomainSid]; cbDomainSid
0x180036d67  lea     rdx, [rsp+98h+pDomainSid]; pDomainSid
0x180036d6c  mov     rcx, rdi; pSid
0x180036d6f  call    cs:__imp_GetWindowsAccountDomainSid
0x180036d75  test    eax, eax
0x180036d77  jz      short loc_180036D98
0x180036d79  lea     rdx, [rsp+98h+pDomainSid]; Sid2
0x180036d7e  mov     rcx, rdi; Sid1
0x180036d81  call    cs:__imp_RtlEqualSid
0x180036d87  movzx   ebx, bl
0x180036d8a  mov     ecx, 1
0x180036d8f  test    al, al
0x180036d91  cmovnz  ebx, ecx
0x180036d94  mov     [rsp+98h+var_78], bl
0x180036d98  jmp     short loc_180036D9E
0x180036d9a  mov     bl, [rsp+98h+var_78]
0x180036d9e  mov     al, bl
0x180036da0  mov     rcx, [rsp+98h+var_18]
0x180036da8  xor     rcx, rsp; StackCookie
0x180036dab  call    __security_check_cookie
0x180036db0  mov     rbx, [rsp+98h+arg_8]
0x180036db8  add     rsp, 90h
0x180036dbf  pop     rdi
0x180036dc0  retn
```
