# CSharingConfiguration::_GetSid(DEF_SHARE_ID,ushort * *)

- ea: `0x18005530c`
- end: `0x18005539b`
- name: `?_GetSid@CSharingConfiguration@@AEAAJW4DEF_SHARE_ID@@PEAPEAG@Z`
- size: `143`
- prototype: `int(CSharingConfiguration *__hidden this, enum DEF_SHARE_ID, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180054470`

## callees

- `0x1800098dc`
- `0x18005530c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180055357`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180055357`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005533d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005533d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005538a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005538a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180055372`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180055372`

## pseudocode

```c
__int64 __fastcall CSharingConfiguration::_GetSid(
        CSharingConfiguration *this,
        enum DEF_SHARE_ID a2,
        unsigned __int16 **a3)
{
  WELL_KNOWN_SID_TYPE v4; // esi
  int Error; // ebx
  HLOCAL v6; // rax
  void *v7; // rdi
  DWORD cbSid; // [rsp+58h] [rbp+10h] BYREF

  v4 = WinBuiltinAdministratorsSid;
  if ( (unsigned int)(a2 - 1) <= 1 )
    v4 = WinWorldSid;
  Error = -2147024882;
  cbSid = 68;
  v6 = LocalAlloc(0x40u, 0x44u);
  v7 = v6;
  if ( v6 )
  {
    if ( CreateWellKnownSid(v4, 0, v6, &cbSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( ConvertSidToStringSidW(v7, a3) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
    }
    LocalFree(v7);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18005530c  push    rbx
0x18005530e  push    rbp
0x18005530f  push    rsi
0x180055310  push    rdi
0x180055311  sub     rsp, 28h
0x180055315  mov     rbp, r8
0x180055318  mov     esi, 1Ah
0x18005531d  sub     edx, 1
0x180055320  jz      short loc_180055327
0x180055322  cmp     edx, 1
0x180055325  jnz     short loc_18005532C
0x180055327  mov     esi, 1
0x18005532c  mov     edx, 44h ; 'D'; uBytes
0x180055331  mov     ebx, 8007000Eh
0x180055336  mov     [rsp+48h+cbSid], edx
0x18005533a  lea     ecx, [rdx-4]; uFlags
0x18005533d  call    cs:__imp_LocalAlloc
0x180055343  mov     rdi, rax
0x180055346  test    rax, rax
0x180055349  jz      short loc_180055390
0x18005534b  lea     r9, [rsp+48h+cbSid]; cbSid
0x180055350  mov     r8, rax; pSid
0x180055353  xor     edx, edx; DomainSid
0x180055355  mov     ecx, esi; WellKnownSidType
0x180055357  call    cs:__imp_CreateWellKnownSid
0x18005535d  test    eax, eax
0x18005535f  jnz     short loc_18005536C
0x180055361  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055366  mov     ebx, eax
0x180055368  test    eax, eax
0x18005536a  js      short loc_180055387
0x18005536c  mov     rdx, rbp; StringSid
0x18005536f  mov     rcx, rdi; Sid
0x180055372  call    cs:__imp_ConvertSidToStringSidW
0x180055378  test    eax, eax
0x18005537a  jz      short loc_180055380
0x18005537c  xor     ebx, ebx
0x18005537e  jmp     short loc_180055387
0x180055380  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180055385  mov     ebx, eax
0x180055387  mov     rcx, rdi; hMem
0x18005538a  call    cs:__imp_LocalFree
0x180055390  mov     eax, ebx
0x180055392  add     rsp, 28h
0x180055396  pop     rdi
0x180055397  pop     rsi
0x180055398  pop     rbp
0x180055399  pop     rbx
0x18005539a  retn
```
