# ClusterHandleConnector::ClusterHandleConnector(void *,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,_SEC_WINNT_AUTH_IDENTITY_W *)

- ea: `0x18001d0dc`
- end: `0x18001d1e1`
- name: `??0ClusterHandleConnector@@QEAA@PEAXKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAU_SEC_WINNT_AUTH_IDENTITY_W@@@Z`
- size: `261`
- prototype: `__int64 __usercall@<rax>(PHANDLE DuplicateTokenHandle@<rcx>, HANDLE ExistingTokenHandle@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c528`

## callees

- `0x180002f50`
- `0x180003c44`
- `0x18001cb44`
- `0x18001cc2c`
- `0x18001d0dc`
- `0x180023704`
- `0x180027494`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d170`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d170`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001d13b`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001d13b`

## string_xrefs

- `0x18001d17c`: `ClusterHandleConnector - Failed to duplicate the token - %d`
- `0x18001d19f`: `DuplicateToken Error`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PHANDLE __fastcall ClusterHandleConnector::ClusterHandleConnector(
        PHANDLE DuplicateTokenHandle,
        HANDLE ExistingTokenHandle,
        int a3,
        __int64 a4,
        void *a5)
{
  DWORD LastError; // ebx
  __int64 v9; // rax
  DWORD v10; // [rsp+28h] [rbp-C0h]
  _BYTE v12[8]; // [rsp+38h] [rbp-B0h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+60h] [rbp-88h] BYREF

  *DuplicateTokenHandle = (void *)-1LL;
  *((_DWORD *)DuplicateTokenHandle + 2) = a3;
  std::wstring::wstring(DuplicateTokenHandle + 2, a4);
  DuplicateTokenHandle[6] = a5;
  if ( ExistingTokenHandle != (HANDLE)-1LL
    && !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, DuplicateTokenHandle) )
  {
    *DuplicateTokenHandle = (void *)-1LL;
    LastError = GetLastError();
    v10 = LastError;
    TraceMsg(
      2,
      0,
      L"ClusterHandleConnector::ClusterHandleConnector",
      1495,
      L"ClusterHandleConnector - Failed to duplicate the token - %d",
      v10,
      DuplicateTokenHandle);
    std::wstring::wstring(v13, L"DuplicateToken Error");
    v9 = cxl::WinError(v12, LastError);
    cxl::Error(pExceptionObject, v9, v13);
    throw (cxl::Exception *)pExceptionObject;
  }
  return DuplicateTokenHandle;
}

```

## disassembly

```asm
0x18001d0dc  mov     [rsp+arg_10], rbx
0x18001d0e1  push    rdi
0x18001d0e2  sub     rsp, 0E0h
0x18001d0e9  mov     rax, cs:__security_cookie
0x18001d0f0  xor     rax, rsp
0x18001d0f3  mov     [rsp+0E8h+var_18], rax
0x18001d0fb  mov     rdi, rdx
0x18001d0fe  mov     rbx, rcx
0x18001d101  mov     [rsp+0E8h+var_B8], rcx
0x18001d106  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18001d10d  mov     [rcx+8], r8d
0x18001d111  add     rcx, 10h
0x18001d115  mov     rdx, r9
0x18001d118  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d11d  nop
0x18001d11e  mov     rax, [rsp+0E8h+arg_20]
0x18001d126  mov     [rbx+30h], rax
0x18001d12a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001d12e  jz      short loc_18001D145
0x18001d130  mov     r8, rbx; DuplicateTokenHandle
0x18001d133  mov     edx, 2; ImpersonationLevel
0x18001d138  mov     rcx, rdi; ExistingTokenHandle
0x18001d13b  call    cs:__imp_DuplicateToken
0x18001d141  test    eax, eax
0x18001d143  jz      short loc_18001D169
0x18001d145  mov     rax, rbx
0x18001d148  mov     rcx, [rsp+0E8h+var_18]
0x18001d150  xor     rcx, rsp; StackCookie
0x18001d153  call    __security_check_cookie
0x18001d158  mov     rbx, [rsp+0E8h+arg_10]
0x18001d160  add     rsp, 0E0h
0x18001d167  pop     rdi
0x18001d168  retn
0x18001d169  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18001d170  call    cs:__imp_GetLastError
0x18001d176  mov     ebx, eax
0x18001d178  mov     [rsp+0E8h+var_C0], eax
0x18001d17c  lea     rax, aClusterhandlec_2; "ClusterHandleConnector - Failed to dupl"...
0x18001d183  mov     [rsp+0E8h+var_C8], rax
0x18001d188  mov     r9d, 5D7h
0x18001d18e  lea     r8, aClusterhandlec_0; "ClusterHandleConnector::ClusterHandleCo"...
0x18001d195  xor     edx, edx
0x18001d197  lea     ecx, [rdx+2]
0x18001d19a  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18001d19f  lea     rdx, aDuplicatetoken; "DuplicateToken Error"
0x18001d1a6  lea     rcx, [rsp+0E8h+var_A8]
0x18001d1ab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d1b0  nop
0x18001d1b1  mov     edx, ebx
0x18001d1b3  lea     rcx, [rsp+0E8h+var_B0]
0x18001d1b8  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x18001d1bd  mov     rdx, rax
0x18001d1c0  lea     r8, [rsp+0E8h+var_A8]
0x18001d1c5  lea     rcx, [rsp+0E8h+pExceptionObject]
0x18001d1ca  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x18001d1cf  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x18001d1d6  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18001d1db  call    _CxxThrowException_0
```
