# ClusterGlobalData::BuildSCMParamsSD(void)

- ea: `0x180032f34`
- end: `0x180033025`
- name: `?BuildSCMParamsSD@ClusterGlobalData@@AEAAXXZ`
- size: `241`
- prototype: `void __fastcall(ClusterGlobalData *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003be68`
- `0x18007ab58`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18002fc00`
- `0x18003180c`
- `0x180032f34`
- `0x180040728`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032ffe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032ffe`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032f7d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032f7d`

## string_xrefs

- `0x180032f8f`: `Couldn't construct SCM Parameters security descriptor`

## pseudocode

```c
void __fastcall ClusterGlobalData::BuildSCMParamsSD(ClusterGlobalData *this)
{
  DWORD LastError; // eax
  unsigned __int64 i; // rdi
  _BYTE *v4; // rdx
  _BYTE *v5; // r8
  ULONG SecurityDescriptorSize; // [rsp+20h] [rbp-138h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+28h] [rbp-130h] BYREF
  _BYTE pExceptionObject[272]; // [rsp+30h] [rbp-128h] BYREF

  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAD:PAR(A;CI;KA;;;BA)(A;CI;KA;;;SY)(A;OI;KA;;;CO)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    ClusRtl::ExceptionMsg::ExceptionMsg(
      (ClusRtl::ExceptionMsg *)pExceptionObject,
      LastError,
      L"Couldn't construct SCM Parameters security descriptor");
    throw (ClusRtl::ExceptionMsg *)pExceptionObject;
  }
  std::vector<unsigned char>::reserve((char *)this + 40, SecurityDescriptorSize);
  for ( i = 0; i < SecurityDescriptorSize; ++i )
  {
    v4 = (_BYTE *)*((_QWORD *)this + 6);
    v5 = (char *)SecurityDescriptor + i;
    if ( v4 == *((_BYTE **)this + 7) )
    {
      std::vector<unsigned char>::_Emplace_reallocate<unsigned char const &>((char *)this + 40, v4, v5);
    }
    else
    {
      *v4 = *v5;
      ++*((_QWORD *)this + 6);
    }
  }
  LocalFree(SecurityDescriptor);
}

```

## disassembly

```asm
0x180032f34  mov     [rsp+arg_8], rbx
0x180032f39  push    rdi
0x180032f3a  sub     rsp, 150h
0x180032f41  mov     rax, cs:__security_cookie
0x180032f48  xor     rax, rsp
0x180032f4b  mov     [rsp+158h+var_18], rax
0x180032f53  mov     rbx, rcx
0x180032f56  mov     [rsp+158h+SecurityDescriptor], 0
0x180032f5f  lea     rcx, StringSecurityDescriptor; "O:BAD:PAR(A;CI;KA;;;BA)(A;CI;KA;;;SY)(A"...
0x180032f66  mov     [rsp+158h+SecurityDescriptorSize], 0
0x180032f6e  lea     r9, [rsp+158h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180032f73  mov     edx, 1; StringSDRevision
0x180032f78  lea     r8, [rsp+158h+SecurityDescriptor]; SecurityDescriptor
0x180032f7d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180032f83  test    eax, eax
0x180032f85  jnz     short loc_180032FB2
0x180032f87  call    cs:__imp_GetLastError
0x180032f8d  mov     edx, eax; int
0x180032f8f  lea     r8, aCouldnTConstru; "Couldn't construct SCM Parameters secur"...
0x180032f96  lea     rcx, [rsp+158h+pExceptionObject]; this
0x180032f9b  call    ??0ExceptionMsg@ClusRtl@@QEAA@HPEB_WZZ; ClusRtl::ExceptionMsg::ExceptionMsg(int,wchar_t const *,...)
0x180032fa0  lea     rdx, _TI1?AVExceptionMsg@ClusRtl@@; pThrowInfo
0x180032fa7  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x180032fac  call    _CxxThrowException_0
0x180032fb2  mov     edx, [rsp+158h+SecurityDescriptorSize]
0x180032fb6  lea     rcx, [rbx+28h]
0x180032fba  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x180032fbf  xor     edi, edi
0x180032fc1  cmp     [rsp+158h+SecurityDescriptorSize], edi
0x180032fc5  jbe     short loc_180032FF9
0x180032fc7  mov     r8, [rsp+158h+SecurityDescriptor]
0x180032fcc  mov     rdx, [rbx+30h]
0x180032fd0  add     r8, rdi
0x180032fd3  cmp     rdx, [rbx+38h]
0x180032fd7  jz      short loc_180032FE4
0x180032fd9  mov     al, [r8]
0x180032fdc  mov     [rdx], al
0x180032fde  inc     qword ptr [rbx+30h]
0x180032fe2  jmp     short loc_180032FED
0x180032fe4  lea     rcx, [rbx+28h]
0x180032fe8  call    ??$_Emplace_reallocate@AEBE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEBE@Z; std::vector<uchar>::_Emplace_reallocate<uchar const &>(uchar * const,uchar const &)
0x180032fed  mov     eax, [rsp+158h+SecurityDescriptorSize]
0x180032ff1  inc     rdi
0x180032ff4  cmp     rdi, rax
0x180032ff7  jb      short loc_180032FC7
0x180032ff9  mov     rcx, [rsp+158h+SecurityDescriptor]; hMem
0x180032ffe  call    cs:__imp_LocalFree
0x180033004  mov     rcx, [rsp+158h+var_18]
0x18003300c  xor     rcx, rsp; StackCookie
0x18003300f  call    __security_check_cookie
0x180033014  mov     rbx, [rsp+158h+arg_8]
0x18003301c  add     rsp, 150h
0x180033023  pop     rdi
0x180033024  retn
```
