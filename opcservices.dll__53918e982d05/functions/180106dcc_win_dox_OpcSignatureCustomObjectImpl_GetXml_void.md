# win_dox::OpcSignatureCustomObjectImpl::GetXml(void)

- ea: `0x180106dcc`
- end: `0x180106e85`
- name: `?GetXml@OpcSignatureCustomObjectImpl@win_dox@@QEAA?AU?$SMART_VECTOR@V?$scope@PEAEU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@@2@XZ`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180104770`

## callees

- `0x1800cd6ca`
- `0x1800cd6fc`
- `0x1800d6348`
- `0x180106dcc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180106e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180106e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106e20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180106e20`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall win_dox::OpcSignatureCustomObjectImpl::GetXml(__int64 a1, __int64 a2)
{
  SIZE_T v4; // rdi
  LPVOID v5; // rax
  void *v6; // rcx
  _QWORD pExceptionObject[5]; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = 0;
  v4 = *(unsigned int *)(a1 + 16);
  v5 = CoTaskMemAlloc(v4);
  v6 = *(void **)a2;
  *(_QWORD *)a2 = v5;
  if ( v6 )
    CoTaskMemFree(v6);
  if ( !*(_QWORD *)a2 )
  {
    exception::exception((exception *)pExceptionObject, (const char *const *)&std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  memcpy_0(*(void **)a2, *(const void **)(a1 + 8), v4);
  *(_DWORD *)(a2 + 8) = v4;
  return a2;
}

```

## disassembly

```asm
0x180106dcc  mov     rax, rsp
0x180106dcf  mov     [rax+10h], rdx
0x180106dd3  push    rdi
0x180106dd4  sub     rsp, 50h
0x180106dd8  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x180106de0  mov     [rax+8], rbx
0x180106de4  mov     [rax+18h], rsi
0x180106de8  mov     rbx, rdx
0x180106deb  mov     rsi, rcx
0x180106dee  mov     dword ptr [rax-38h], 0
0x180106df5  mov     qword ptr [rdx], 0
0x180106dfc  mov     dword ptr [rdx+8], 0
0x180106e03  mov     dword ptr [rax-38h], 1
0x180106e0a  mov     edi, [rcx+10h]
0x180106e0d  mov     ecx, edi; cb
0x180106e0f  call    cs:__imp_CoTaskMemAlloc
0x180106e15  mov     rcx, [rbx]; pv
0x180106e18  mov     [rbx], rax
0x180106e1b  test    rcx, rcx
0x180106e1e  jz      short loc_180106E26
0x180106e20  call    cs:__imp_CoTaskMemFree
0x180106e26  mov     rcx, [rbx]; void *
0x180106e29  test    rcx, rcx
0x180106e2c  jz      short loc_180106E50
0x180106e2e  mov     r8, rdi; Size
0x180106e31  mov     rdx, [rsi+8]; Src
0x180106e35  call    memcpy_0
0x180106e3a  mov     [rbx+8], edi
0x180106e3d  mov     rax, rbx
0x180106e40  mov     rbx, [rsp+58h+arg_0]
0x180106e45  mov     rsi, [rsp+58h+arg_10]
0x180106e4a  add     rsp, 50h
0x180106e4e  pop     rdi
0x180106e4f  retn
0x180106e50  mov     r8d, 1; int
0x180106e56  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char **
0x180106e5d  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180106e62  call    ??0exception@@QEAA@AEBQEBDH@Z_0; exception::exception(char const * const &,int)
0x180106e67  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180106e6e  mov     [rsp+58h+pExceptionObject], rax
0x180106e73  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180106e7a  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180106e7f  call    _CxxThrowException_0
```
