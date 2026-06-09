# cxl::SecurityDescriptor::SecurityDescriptor(void *)

- ea: `0x1800a72d8`
- end: `0x1800a7413`
- name: `??0SecurityDescriptor@cxl@@QEAA@PEAX@Z`
- size: `315`
- prototype: `_QWORD(cxl::SecurityDescriptor *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a7d5c`

## callees

- `0x180002f50`
- `0x180003bfc`
- `0x180003c44`
- `0x18001cc2c`
- `0x180023704`
- `0x180027494`
- `0x180091a0c`
- `0x18009c728`
- `0x18009c85c`
- `0x1800a72d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a73c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a73c7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800a733a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800a733a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800a7357`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800a7357`

## string_xrefs

- `0x1800a73b4`: `GetSecurityDescriptorControl(selfRelativeSD, &sdControl, &sdRevision)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
cxl::SecurityDescriptor *__fastcall cxl::SecurityDescriptor::SecurityDescriptor(
        cxl::SecurityDescriptor *this,
        void *a2)
{
  DWORD SecurityDescriptorLength; // ebx
  unsigned int v5; // edx
  void *v6; // rdi
  __int64 v8; // rbx
  DWORD LastError; // eax
  __int64 v10; // rax
  WORD pControl[2]; // [rsp+20h] [rbp-89h] BYREF
  DWORD dwRevision; // [rsp+24h] [rbp-85h] BYREF
  cxl::SecurityDescriptor *v13; // [rsp+28h] [rbp-81h]
  _BYTE v14[8]; // [rsp+30h] [rbp-79h] BYREF
  __int64 v15; // [rsp+38h] [rbp-71h]
  _BYTE v16[32]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE pExceptionObject[112]; // [rsp+70h] [rbp-39h] BYREF

  v13 = this;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &cxl::SecurityDescriptor::`vftable';
  if ( a2 )
  {
    pControl[0] = 0;
    dwRevision = 0;
    if ( !GetSecurityDescriptorControl(a2, pControl, &dwRevision) )
    {
      v8 = std::wstring::wstring(v16, L"GetSecurityDescriptorControl(selfRelativeSD, &sdControl, &sdRevision)");
      LastError = GetLastError();
      v10 = cxl::WinError(v14, LastError);
      cxl::Error(pExceptionObject, v10, v8);
      throw (cxl::Exception *)pExceptionObject;
    }
    if ( (pControl[0] & 0x8000u) == 0 )
    {
      std::wstring::wstring(v14, L"(sdControl & SE_SELF_RELATIVE) != 0 is false");
      cxl::Throw::AssertionFailed(v14);
    }
    SecurityDescriptorLength = GetSecurityDescriptorLength(a2);
    v6 = cxl::LocalHeap::Alloc(SecurityDescriptorLength, v5);
    memcpy_0(v6, a2, SecurityDescriptorLength);
    v15 = 0;
    *((_QWORD *)this + 2) = v6;
    cxl::LocalHeapPtr<void>::Clear(v14);
  }
  return this;
}

```

## disassembly

```asm
0x1800a72d8  mov     [rsp-8+arg_10], rbx
0x1800a72dd  mov     [rsp-8+arg_18], rsi
0x1800a72e2  push    rbp
0x1800a72e3  push    rdi
0x1800a72e4  push    r14
0x1800a72e6  lea     rbp, [rsp-47h]
0x1800a72eb  sub     rsp, 0F0h
0x1800a72f2  mov     rax, cs:__security_cookie
0x1800a72f9  xor     rax, rsp
0x1800a72fc  mov     [rbp+57h+var_20], rax
0x1800a7300  mov     r14, rdx
0x1800a7303  mov     rsi, rcx
0x1800a7306  mov     [rsp+100h+var_D8], rcx
0x1800a730b  mov     qword ptr [rcx+10h], 0
0x1800a7313  lea     rax, ??_7SecurityDescriptor@cxl@@6B@; const cxl::SecurityDescriptor::`vftable'
0x1800a731a  mov     [rcx], rax
0x1800a731d  test    rdx, rdx
0x1800a7320  jz      short loc_1800A738D
0x1800a7322  xor     eax, eax
0x1800a7324  mov     [rsp+100h+pControl], ax
0x1800a7329  mov     [rsp+100h+dwRevision], eax
0x1800a732d  lea     r8, [rsp+100h+dwRevision]; lpdwRevision
0x1800a7332  lea     rdx, [rsp+100h+pControl]; pControl
0x1800a7337  mov     rcx, r14; pSecurityDescriptor
0x1800a733a  call    cs:__imp_GetSecurityDescriptorControl
0x1800a7340  test    eax, eax
0x1800a7342  jz      short loc_1800A73B4
0x1800a7344  mov     eax, 8000h
0x1800a7349  test    [rsp+100h+pControl], ax
0x1800a734e  jz      loc_1800A73F8
0x1800a7354  mov     rcx, r14; pSecurityDescriptor
0x1800a7357  call    cs:__imp_GetSecurityDescriptorLength
0x1800a735d  mov     ebx, eax
0x1800a735f  mov     ecx, eax; uBytes
0x1800a7361  call    ?Alloc@LocalHeap@cxl@@SAPEAX_KK@Z; cxl::LocalHeap::Alloc(unsigned __int64,ulong)
0x1800a7366  mov     rdi, rax
0x1800a7369  mov     r8d, ebx; Size
0x1800a736c  mov     rdx, r14; Src
0x1800a736f  mov     rcx, rax; void *
0x1800a7372  call    memcpy_0
0x1800a7377  mov     [rbp+57h+var_C8], 0
0x1800a737f  mov     [rsi+10h], rdi
0x1800a7383  lea     rcx, [rbp+57h+var_D0]
0x1800a7387  call    ?Clear@?$LocalHeapPtr@X@cxl@@QEAAXXZ; cxl::LocalHeapPtr<void>::Clear(void)
0x1800a738c  nop
0x1800a738d  mov     rax, rsi
0x1800a7390  mov     rcx, [rbp+57h+var_20]
0x1800a7394  xor     rcx, rsp; StackCookie
0x1800a7397  call    __security_check_cookie
0x1800a739c  lea     r11, [rsp+100h+var_10]
0x1800a73a4  mov     rbx, [r11+30h]
0x1800a73a8  mov     rsi, [r11+38h]
0x1800a73ac  mov     rsp, r11
0x1800a73af  pop     r14
0x1800a73b1  pop     rdi
0x1800a73b2  pop     rbp
0x1800a73b3  retn
0x1800a73b4  lea     rdx, aGetsecuritydes_0; "GetSecurityDescriptorControl(selfRelati"...
0x1800a73bb  lea     rcx, [rbp+57h+var_B0]
0x1800a73bf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a73c4  mov     rbx, rax
0x1800a73c7  call    cs:__imp_GetLastError
0x1800a73cd  mov     edx, eax
0x1800a73cf  lea     rcx, [rbp+57h+var_D0]
0x1800a73d3  call    ?WinError@cxl@@YA?AVErrorCode@1@H@Z; cxl::WinError(int)
0x1800a73d8  mov     r8, rbx
0x1800a73db  mov     rdx, rax
0x1800a73de  lea     rcx, [rbp+57h+pExceptionObject]
0x1800a73e2  call    ?Error@cxl@@YA?AVException@1@AEBVErrorCode@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Error(cxl::ErrorCode const &,std::wstring const &)
0x1800a73e7  lea     rdx, _TI2?AVException@cxl@@; pThrowInfo
0x1800a73ee  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800a73f2  call    _CxxThrowException_0
0x1800a73f8  lea     rdx, aSdcontrolSeSel; "(sdControl & SE_SELF_RELATIVE) != 0 is "...
0x1800a73ff  lea     rcx, [rbp+57h+var_D0]
0x1800a7403  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800a7408  nop
0x1800a7409  lea     rcx, [rbp+57h+var_D0]
0x1800a740d  call    ?AssertionFailed@Throw@cxl@@YAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; cxl::Throw::AssertionFailed(std::wstring const &)
```
