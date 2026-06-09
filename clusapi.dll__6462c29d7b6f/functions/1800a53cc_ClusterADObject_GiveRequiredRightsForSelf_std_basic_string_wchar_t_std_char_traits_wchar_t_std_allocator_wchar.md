# ClusterADObject::GiveRequiredRightsForSelf(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800a53cc`
- end: `0x1800a54aa`
- name: `?GiveRequiredRightsForSelf@ClusterADObject@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180074b2c`

## callees

- `0x180002f50`
- `0x180029978`
- `0x180038494`
- `0x1800a53cc`
- `0x1800a54b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5412`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5443`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a5408`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800a5408`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a5439`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a5439`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall ClusterADObject::GiveRequiredRightsForSelf(ClusterADObject *this, __int64 a2)
{
  signed int result; // eax
  __int64 v5; // r8
  signed int LastError; // eax
  unsigned int v7; // ebx
  LPWSTR v8; // rcx
  LPWSTR StringSid; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid; // [rsp+28h] [rbp-70h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  cbSid = 68;
  if ( CreateWellKnownSid(WinSelfSid, 0, pSid, &cbSid) )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(pSid, &StringSid) )
    {
      std::wstring::assign(a2, StringSid, v5);
      v7 = ClusterADObject::GiveRequiredRightsForSid(this);
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    v8 = StringSid;
    StringSid = 0;
    CTSmartPtr_PolicyLocalMem::DestroyMem(v8);
    return v7;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800a53cc  mov     [rsp+arg_10], rbx
0x1800a53d1  push    rdi
0x1800a53d2  sub     rsp, 90h
0x1800a53d9  mov     rax, cs:__security_cookie
0x1800a53e0  xor     rax, rsp
0x1800a53e3  mov     [rsp+98h+var_18], rax
0x1800a53eb  mov     rbx, rdx
0x1800a53ee  mov     rdi, rcx
0x1800a53f1  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800a53f9  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800a53fe  lea     r8, [rsp+98h+pSid]; pSid
0x1800a5403  xor     edx, edx; DomainSid
0x1800a5405  lea     ecx, [rdx+10h]; WellKnownSidType
0x1800a5408  call    cs:__imp_CreateWellKnownSid
0x1800a540e  test    eax, eax
0x1800a5410  jnz     short loc_1800A5426
0x1800a5412  call    cs:__imp_GetLastError
0x1800a5418  test    eax, eax
0x1800a541a  jle     short loc_1800A5489
0x1800a541c  movzx   eax, ax
0x1800a541f  or      eax, 80070000h
0x1800a5424  jmp     short loc_1800A5489
0x1800a5426  mov     [rsp+98h+StringSid], 0
0x1800a542f  lea     rdx, [rsp+98h+StringSid]; StringSid
0x1800a5434  lea     rcx, [rsp+98h+pSid]; Sid
0x1800a5439  call    cs:__imp_ConvertSidToStringSidW
0x1800a543f  test    eax, eax
0x1800a5441  jnz     short loc_1800A545A
0x1800a5443  call    cs:__imp_GetLastError
0x1800a5449  mov     ebx, eax
0x1800a544b  test    eax, eax
0x1800a544d  jle     short loc_1800A5474
0x1800a544f  movzx   ebx, ax
0x1800a5452  or      ebx, 80070000h
0x1800a5458  jmp     short loc_1800A5474
0x1800a545a  mov     rdx, [rsp+98h+StringSid]
0x1800a545f  mov     rcx, rbx
0x1800a5462  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800a5467  mov     rdx, rbx
0x1800a546a  mov     rcx, rdi; this
0x1800a546d  call    ?GiveRequiredRightsForSid@ClusterADObject@@QEAAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; ClusterADObject::GiveRequiredRightsForSid(std::wstring const &)
0x1800a5472  mov     ebx, eax
0x1800a5474  mov     rcx, [rsp+98h+StringSid]; void *
0x1800a5479  mov     [rsp+98h+StringSid], 0
0x1800a5482  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800a5487  mov     eax, ebx
0x1800a5489  mov     rcx, [rsp+98h+var_18]
0x1800a5491  xor     rcx, rsp; StackCookie
0x1800a5494  call    __security_check_cookie
0x1800a5499  mov     rbx, [rsp+98h+arg_10]
0x1800a54a1  add     rsp, 90h
0x1800a54a8  pop     rdi
0x1800a54a9  retn
```
