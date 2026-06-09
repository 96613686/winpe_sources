# IsCurrentUserSystem(int &)

- ea: `0x18001ebe4`
- end: `0x18001ecd5`
- name: `?IsCurrentUserSystem@@YAJAEAH@Z`
- size: `241`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027a74`
- `0x18002a7e8`
- `0x180034684`
- `0x1800414f8`
- `0x180054738`
- `0x1800a20a4`
- `0x1800a523c`
- `0x1800b138c`

## callees

- `0x1800084f4`
- `0x18001ebe4`
- `0x18001ecdc`
- `0x180044300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec4d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ecaf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ecaf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001ec43`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001ec43`

## string_xrefs

- `0x18001ec8b`: `CheckProcessForSid`
- `0x18001ec65`: `AllocateAndInitializeSid`

## pseudocode

```c
__int64 __fastcall IsCurrentUserSystem(PBOOL IsMember)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  int v4; // eax
  PSID pSid; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v7; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v7.Value[4] = 1280;
  pSid = 0;
  *(_DWORD *)v7.Value = 0;
  if ( AllocateAndInitializeSid(&v7, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
  {
    v4 = CheckProcessForSid(pSid, IsMember);
    v3 = v4;
    if ( v4 < 0 )
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"IsCurrentUserSystem",
        L"CheckProcessForSid",
        (unsigned int)v4);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"IsCurrentUserSystem",
      L"AllocateAndInitializeSid",
      v3);
  }
  if ( pSid )
    FreeSid(pSid);
  return v3;
}

```

## disassembly

```asm
0x18001ebe4  mov     r11, rsp
0x18001ebe7  mov     [r11+10h], rbx
0x18001ebeb  push    rdi
0x18001ebec  sub     rsp, 80h
0x18001ebf3  mov     rax, cs:__security_cookie
0x18001ebfa  xor     rax, rsp
0x18001ebfd  mov     [rsp+88h+var_18], rax
0x18001ec02  xor     edi, edi
0x18001ec04  mov     [rsp+88h+var_1C], 500h
0x18001ec0b  lea     rax, [r11-28h]
0x18001ec0f  mov     [r11-28h], rdi
0x18001ec13  mov     [r11-38h], rax
0x18001ec17  mov     rbx, rcx
0x18001ec1a  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x18001ec1e  lea     rcx, [r11-20h]; pIdentifierAuthority
0x18001ec22  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x18001ec26  lea     r8d, [rdi+12h]; nSubAuthority0
0x18001ec2a  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x18001ec2e  xor     r9d, r9d; nSubAuthority1
0x18001ec31  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x18001ec35  mov     dl, 1; nSubAuthorityCount
0x18001ec37  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x18001ec3b  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x18001ec3f  mov     [rsp+88h+var_20], edi
0x18001ec43  call    cs:__imp_AllocateAndInitializeSid
0x18001ec49  test    eax, eax
0x18001ec4b  jnz     short loc_18001EC75
0x18001ec4d  call    cs:__imp_GetLastError
0x18001ec53  mov     ebx, eax
0x18001ec55  test    eax, eax
0x18001ec57  jle     short loc_18001EC62
0x18001ec59  movzx   ebx, ax
0x18001ec5c  or      ebx, 80070000h
0x18001ec62  mov     r9d, ebx
0x18001ec65  lea     r8, aAllocateandini; "AllocateAndInitializeSid"
0x18001ec6c  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x18001ec73  jmp     short loc_18001EC99
0x18001ec75  mov     rcx, [rsp+88h+pSid]; SidToCheck
0x18001ec7a  mov     rdx, rbx; IsMember
0x18001ec7d  call    ?CheckProcessForSid@@YAJPEAXAEAH@Z; CheckProcessForSid(void *,int &)
0x18001ec82  mov     ebx, eax
0x18001ec84  test    eax, eax
0x18001ec86  jns     short loc_18001ECA5
0x18001ec88  mov     r9d, eax
0x18001ec8b  lea     r8, aCheckprocessfo; "CheckProcessForSid"
0x18001ec92  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18001ec99  lea     rdx, aIscurrentusers; "IsCurrentUserSystem"
0x18001eca0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001eca5  mov     rcx, [rsp+88h+pSid]; pSid
0x18001ecaa  test    rcx, rcx
0x18001ecad  jz      short loc_18001ECB5
0x18001ecaf  call    cs:__imp_FreeSid
0x18001ecb5  mov     eax, ebx
0x18001ecb7  mov     rcx, [rsp+88h+var_18]
0x18001ecbc  xor     rcx, rsp; StackCookie
0x18001ecbf  call    __security_check_cookie
0x18001ecc4  mov     rbx, [rsp+88h+arg_8]
0x18001eccc  add     rsp, 80h
0x18001ecd3  pop     rdi
0x18001ecd4  retn
```
