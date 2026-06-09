# ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)

- ea: `0x180086ccc`
- end: `0x180086e13`
- name: `??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ`
- size: `327`
- prototype: `_QWORD(ATL::CSid *__hidden this, const struct _SID_IDENTIFIER_AUTHORITY *, unsigned __int8, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180086b40`

## callees

- `0x180086ad8`
- `0x180086ccc`
- `0x180086e1c`
- `0x180086e54`
- `0x1800a5a68`
- `0x180106a60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180086da2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180086da2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180086db0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180086db0`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180086dc9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180086dc9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180086d8c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180086d8c`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180086d5a`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180086d5a`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180086d40`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180086d40`

## pseudocode

```c
ATL::CSid *ATL::CSid::CSid(ATL::CSid *this, struct _SID_IDENTIFIER_AUTHORITY *a2, UCHAR a3, ...)
{
  DWORD v5; // esi
  va_list v6; // r14
  DWORD v7; // ebx
  PDWORD SidSubAuthority; // rax
  DWORD LengthSid; // eax
  int Error; // eax
  _BYTE Sid[80]; // [rsp+30h] [rbp-29h] BYREF
  va_list va; // [rsp+D8h] [rbp+7Fh] BYREF

  va_start(va, a3);
  *((_BYTE *)this + 76) = 0;
  *(_QWORD *)this = &ATL::CSid::`vftable';
  *((_DWORD *)this + 20) = 7;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 88);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 96);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 104);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((char *)this + 112);
  if ( !a3 || GetSidLengthRequired(a3) > 0x44 )
    goto LABEL_12;
  if ( !InitializeSid(Sid, a2, a3) )
    ATL::AtlThrowLastWin32();
  v5 = 0;
  va_copy(v6, va);
  if ( a3 )
  {
    do
    {
      v6 += 8;
      v7 = *((_DWORD *)v6 - 2);
      SidSubAuthority = GetSidSubAuthority(Sid, v5++);
      *SidSubAuthority = v7;
    }
    while ( v5 < a3 );
  }
  if ( !IsValidSid(Sid) || (LengthSid = GetLengthSid(Sid), LengthSid > 0x44) )
LABEL_12:
    ATL::AtlThrowImpl(-2147024809);
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(LengthSid, (char *)this + 8, Sid) )
  {
    Error = ATL::AtlHresultFromLastError();
    *((_BYTE *)this + 76) = 0;
    ATL::AtlThrowImpl(Error);
  }
  *((_DWORD *)this + 20) = 8;
  return this;
}

```

## disassembly

```asm
0x180086ccc  mov     [rsp-8+nSubAuthorityCount], r8b
0x180086cd1  mov     [rsp-8+arg_18], r9
0x180086cd6  push    rbp
0x180086cd7  push    rbx
0x180086cd8  push    rsi
0x180086cd9  push    rdi
0x180086cda  push    r14
0x180086cdc  lea     rbp, [rsp-37h]
0x180086ce1  sub     rsp, 90h
0x180086ce8  mov     rax, cs:__security_cookie
0x180086cef  xor     rax, rsp
0x180086cf2  mov     [rbp+57h+var_30], rax
0x180086cf6  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x180086cfd  mov     byte ptr [rcx+4Ch], 0
0x180086d01  mov     [rcx], rax
0x180086d04  mov     rdi, rcx
0x180086d07  mov     dword ptr [rcx+50h], 7
0x180086d0e  mov     rbx, rdx
0x180086d11  add     rcx, 58h ; 'X'
0x180086d15  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180086d1a  lea     rcx, [rdi+60h]
0x180086d1e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180086d23  lea     rcx, [rdi+68h]
0x180086d27  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180086d2c  lea     rcx, [rdi+70h]
0x180086d30  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180086d35  mov     cl, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x180086d38  test    cl, cl
0x180086d3a  jz      loc_180086E08
0x180086d40  call    cs:__imp_GetSidLengthRequired
0x180086d46  cmp     eax, 44h ; 'D'
0x180086d49  ja      loc_180086E08
0x180086d4f  mov     r8b, [rbp+57h+nSubAuthorityCount]; nSubAuthorityCount
0x180086d53  lea     rcx, [rbp+57h+Sid]; Sid
0x180086d57  mov     rdx, rbx; pIdentifierAuthority
0x180086d5a  call    cs:__imp_InitializeSid
0x180086d60  test    eax, eax
0x180086d62  jnz     short loc_180086D6A
0x180086d64  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x180086d6a  xor     esi, esi
0x180086d6c  mov     [rbp+57h+var_90], 0
0x180086d74  lea     r14, [rbp+57h+arg_18]
0x180086d78  cmp     [rbp+57h+nSubAuthorityCount], sil
0x180086d7c  jbe     short loc_180086D9E
0x180086d7e  lea     r14, [r14+8]
0x180086d82  mov     edx, esi; nSubAuthority
0x180086d84  mov     ebx, [r14-8]
0x180086d88  lea     rcx, [rbp+57h+Sid]; pSid
0x180086d8c  call    cs:__imp_GetSidSubAuthority
0x180086d92  inc     esi
0x180086d94  mov     [rax], ebx
0x180086d96  movzx   eax, [rbp+57h+nSubAuthorityCount]
0x180086d9a  cmp     esi, eax
0x180086d9c  jb      short loc_180086D7E
0x180086d9e  lea     rcx, [rbp+57h+Sid]; pSid
0x180086da2  call    cs:__imp_IsValidSid
0x180086da8  test    eax, eax
0x180086daa  jz      short loc_180086E08
0x180086dac  lea     rcx, [rbp+57h+Sid]; pSid
0x180086db0  call    cs:__imp_GetLengthSid
0x180086db6  cmp     eax, 44h ; 'D'
0x180086db9  ja      short loc_180086E08
0x180086dbb  lea     rdx, [rdi+8]; pDestinationSid
0x180086dbf  mov     byte ptr [rdi+4Ch], 1
0x180086dc3  lea     r8, [rbp+57h+Sid]; pSourceSid
0x180086dc7  mov     ecx, eax; nDestinationSidLength
0x180086dc9  call    cs:__imp_CopySid
0x180086dcf  test    eax, eax
0x180086dd1  jnz     short loc_180086DE4
0x180086dd3  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180086dd8  mov     ecx, eax; int
0x180086dda  mov     byte ptr [rdi+4Ch], 0
0x180086dde  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180086de4  mov     dword ptr [rdi+50h], 8
0x180086deb  mov     rax, rdi
0x180086dee  mov     rcx, [rbp+57h+var_30]
0x180086df2  xor     rcx, rsp; StackCookie
0x180086df5  call    __security_check_cookie
0x180086dfa  add     rsp, 90h
0x180086e01  pop     r14
0x180086e03  pop     rdi
0x180086e04  pop     rsi
0x180086e05  pop     rbx
0x180086e06  pop     rbp
0x180086e07  retn
0x180086e08  mov     ecx, 80070057h; int
0x180086e0d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
