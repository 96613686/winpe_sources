# NFrameCommon::CreateControlSecurityDescriptor(void)

- ea: `0x140009d0c`
- end: `0x140009dc6`
- name: `?CreateControlSecurityDescriptor@NFrameCommon@@YAPEAXXZ`
- size: `186`
- prototype: `void *__fastcall(NFrameCommon *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400085d4`

## callees

- `0x140002070`
- `0x140002c74`
- `0x140004484`
- `0x140005358`
- `0x140009d0c`
- `0x140045ccc`
- `0x140045e7c`
- `0x140045ecc`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140009d41`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140009d41`

## string_xrefs

- `0x140009d71`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PSECURITY_DESCRIPTOR __fastcall NFrameCommon::CreateControlSecurityDescriptor(NFrameCommon *this)
{
  NCoreLibrary *v1; // rcx
  unsigned int LastErrorAsHResult; // eax
  const struct SplException::TSystemException *v3; // r8
  const struct _GUID *v4; // r9
  unsigned int v6; // [rsp+20h] [rbp-188h]
  const struct win_musl::TStringEllipseBase *v7; // [rsp+28h] [rbp-180h]
  HINSTANCE v8; // [rsp+30h] [rbp-178h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-168h] BYREF
  _BYTE v10[160]; // [rsp+50h] [rbp-158h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+F0h] [rbp-B8h] BYREF

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(NFrameCommon::szControlUsers, 1u, &SecurityDescriptor, 0) )
  {
    SplException::THResultException::THResultException((SplException::THResultException *)v10, "-", 0);
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v1);
    SplException::TSystemException::InternalInit(
      (SplException::TSystemException *)v10,
      LastErrorAsHResult,
      v3,
      v4,
      v6,
      v7,
      v8);
    SplException::TSystemException::Message(
      (SplException::TSystemException *)v10,
      "ConvertStringSecurityDescriptorToSecurityDescriptor failed.");
    SplException::THResultException::THResultException(
      (SplException::THResultException *)pExceptionObject,
      (const struct SplException::THResultException *)v10);
    throw (SplException::THResultException *)pExceptionObject;
  }
  return SecurityDescriptor;
}

```

## disassembly

```asm
0x140009d0c  sub     rsp, 1A8h
0x140009d13  mov     rax, cs:__security_cookie
0x140009d1a  xor     rax, rsp
0x140009d1d  mov     [rsp+1A8h+var_18], rax
0x140009d25  mov     [rsp+1A8h+SecurityDescriptor], 0
0x140009d2e  xor     r9d, r9d; SecurityDescriptorSize
0x140009d31  lea     r8, [rsp+1A8h+SecurityDescriptor]; SecurityDescriptor
0x140009d36  lea     edx, [r9+1]; StringSDRevision
0x140009d3a  lea     rcx, ?szControlUsers@NFrameCommon@@3PA_WA; "O:BAG:BAD:(A;;0xf0001;;;BA)(A;;0xf0001;"...
0x140009d41  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140009d47  test    eax, eax
0x140009d49  jnz     short loc_140009DA9
0x140009d4b  xor     r8d, r8d; unsigned int
0x140009d4e  lea     rdx, asc_1400696D8; "-"
0x140009d55  lea     rcx, [rsp+1A8h+var_158]; this
0x140009d5a  call    ??0THResultException@SplException@@QEAA@PEBDK@Z; SplException::THResultException::THResultException(char const *,ulong)
0x140009d5f  nop
0x140009d60  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140009d65  mov     edx, eax; unsigned int
0x140009d67  lea     rcx, [rsp+1A8h+var_158]; this
0x140009d6c  call    ?InternalInit@TSystemException@SplException@@IEAAXKPEBV12@AEBU_GUID@@KPEBVTStringEllipseBase@win_musl@@PEAUHINSTANCE__@@@Z; SplException::TSystemException::InternalInit(ulong,SplException::TSystemException const *,_GUID const &,ulong,win_musl::TStringEllipseBase const *,HINSTANCE__ *)
0x140009d71  lea     rdx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x140009d78  lea     rcx, [rsp+1A8h+var_158]; this
0x140009d7d  call    ?Message@TSystemException@SplException@@QEAAXPEBDZZ; SplException::TSystemException::Message(char const *,...)
0x140009d82  lea     rdx, [rsp+1A8h+var_158]; struct SplException::THResultException *
0x140009d87  lea     rcx, [rsp+1A8h+pExceptionObject]; this
0x140009d8f  call    ??0THResultException@SplException@@QEAA@AEBV01@@Z; SplException::THResultException::THResultException(SplException::THResultException const &)
0x140009d94  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x140009d9b  lea     rcx, [rsp+1A8h+pExceptionObject]; pExceptionObject
0x140009da3  call    _CxxThrowException_0
0x140009da9  mov     rax, [rsp+1A8h+SecurityDescriptor]
0x140009dae  mov     rcx, [rsp+1A8h+var_18]
0x140009db6  xor     rcx, rsp; StackCookie
0x140009db9  call    __security_check_cookie
0x140009dbe  add     rsp, 1A8h
0x140009dc5  retn
```
