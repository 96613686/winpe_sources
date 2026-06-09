# win_dox::OpcDigitalSignatureImpl::GetSignatureXml(void)

- ea: `0x1800be110`
- end: `0x1800be20e`
- name: `?GetSignatureXml@OpcDigitalSignatureImpl@win_dox@@QEAA?AU?$SMART_VECTOR@V?$scope@PEAEU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@2@XZ`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800fbfb0`

## callees

- `0x18002db70`
- `0x1800be110`
- `0x1800cd6fc`
- `0x1800d6348`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be169`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be169`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be17a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800be17a`

## string_xrefs

- `0x1800be1c8`: `Unable to copy string`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::OpcDigitalSignatureImpl::GetSignatureXml(__int64 a1, __int64 a2)
{
  LPVOID v4; // rax
  void *v5; // rcx
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = 0;
  v4 = CoTaskMemAlloc(*(unsigned int *)(a1 + 224));
  v5 = *(void **)a2;
  *(_QWORD *)a2 = v4;
  if ( v5 )
    CoTaskMemFree(v5);
  if ( !*(_QWORD *)a2 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x8Du,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to copy string");
    throw (SplException::THResultException *)pExceptionObject;
  }
  memcpy_0(*(void **)a2, *(const void **)(a1 + 216), *(unsigned int *)(a1 + 224));
  *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 224);
  return a2;
}

```

## disassembly

```asm
0x1800be110  mov     rax, rsp
0x1800be113  push    rdi
0x1800be114  sub     rsp, 110h
0x1800be11b  mov     [rsp+118h+var_D0], 0FFFFFFFFFFFFFFFEh
0x1800be124  mov     [rax+18h], rbx
0x1800be128  mov     rax, cs:__security_cookie
0x1800be12f  xor     rax, rsp
0x1800be132  mov     [rsp+118h+var_18], rax
0x1800be13a  mov     rbx, rdx
0x1800be13d  mov     rdi, rcx
0x1800be140  mov     [rsp+118h+var_C8], rdx
0x1800be145  mov     [rsp+118h+var_D8], 0
0x1800be14d  mov     qword ptr [rdx], 0
0x1800be154  mov     dword ptr [rdx+8], 0
0x1800be15b  mov     [rsp+118h+var_D8], 1
0x1800be163  mov     ecx, [rcx+0E0h]; cb
0x1800be169  call    cs:__imp_CoTaskMemAlloc
0x1800be16f  mov     rcx, [rbx]; pv
0x1800be172  mov     [rbx], rax
0x1800be175  test    rcx, rcx
0x1800be178  jz      short loc_1800BE180
0x1800be17a  call    cs:__imp_CoTaskMemFree
0x1800be180  mov     rcx, [rbx]; void *
0x1800be183  test    rcx, rcx
0x1800be186  jz      short loc_1800BE1C8
0x1800be188  mov     r8d, [rdi+0E0h]; Size
0x1800be18f  mov     rdx, [rdi+0D8h]; Src
0x1800be196  call    memcpy_0
0x1800be19b  mov     ecx, [rdi+0E0h]
0x1800be1a1  mov     [rbx+8], ecx
0x1800be1a4  mov     rax, rbx
0x1800be1a7  mov     rcx, [rsp+118h+var_18]
0x1800be1af  xor     rcx, rsp; StackCookie
0x1800be1b2  call    __security_check_cookie
0x1800be1b7  mov     rbx, [rsp+118h+arg_10]
0x1800be1bf  add     rsp, 110h
0x1800be1c6  pop     rdi
0x1800be1c7  retn
0x1800be1c8  lea     rax, aUnableToCopySt; "Unable to copy string"
0x1800be1cf  mov     [rsp+118h+var_E8], rax; struct win_musl::TStringEllipseBase *
0x1800be1d4  mov     [rsp+118h+var_F0], 8007000Eh; unsigned int
0x1800be1dc  mov     [rsp+118h+var_F8], 8Dh; unsigned int
0x1800be1e4  lea     r9, word_180139126
0x1800be1eb  lea     r8, aNoFilename; "(no filename)"
0x1800be1f2  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1800be1f7  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be1fc  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be203  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x1800be208  call    _CxxThrowException_0
```
