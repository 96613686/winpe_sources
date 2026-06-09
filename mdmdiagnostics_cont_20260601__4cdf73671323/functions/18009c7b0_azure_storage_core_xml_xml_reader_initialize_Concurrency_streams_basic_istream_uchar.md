# azure::storage::core::xml::xml_reader::initialize(Concurrency::streams::basic_istream<uchar>)

- ea: `0x18009c7b0`
- end: `0x18009cae9`
- name: `?initialize@xml_reader@xml@core@storage@azure@@IEAAXV?$basic_istream@E@streams@Concurrency@@@Z`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180095bd0`

## callees

- `0x180019000`
- `0x180019024`
- `0x180019ff4`
- `0x18001a3a7`
- `0x18001afc0`
- `0x180048b10`
- `0x18009c7b0`
- `0x1800e66dc`
- `0x1800e79e0`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca94`

## string_xrefs

- `0x18009c9ec`: `XML reader IStream creation failed`
- `0x18009ca47`: `XML reader CreateXmlReader failed`
- `0x18009ca9c`: `XML reader SetProperty failed`
- `0x18009c99f`: `XML reader SetInput failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall azure::storage::core::xml::xml_reader::initialize(void **a1, __int64 a2)
{
  __int64 v4; // rax
  _DWORD *v5; // rdi
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rax
  DWORD v9; // ebx
  DWORD LastError; // ebx
  DWORD v11; // ebx
  _OWORD pExceptionObject[2]; // [rsp+40h] [rbp-30h] BYREF

  pExceptionObject[0] = 0;
  v4 = *(_QWORD *)(a2 + 8);
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  pExceptionObject[0] = *(_OWORD *)a2;
  v5 = operator new(0x20u);
  if ( v5 )
  {
    v6 = (volatile signed __int32 *)*((_QWORD *)&pExceptionObject[0] + 1);
    if ( *((_QWORD *)&pExceptionObject[0] + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&pExceptionObject[0] + 1) + 8LL));
      v6 = (volatile signed __int32 *)*((_QWORD *)&pExceptionObject[0] + 1);
    }
    v7 = *(_QWORD *)&pExceptionObject[0];
    *(_QWORD *)v5 = &azure::storage::core::xml::xmlstring_stream::`vftable';
    v5[2] = 1;
    *(_QWORD *)v5 = &azure::storage::core::xml::xmlstring_istream::`vftable';
    *((_QWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 3) = 0;
    if ( v6 )
    {
      _InterlockedIncrement(v6 + 2);
      *((_QWORD *)v5 + 2) = v7;
      *((_QWORD *)v5 + 3) = v6;
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    else
    {
      *((_QWORD *)v5 + 2) = v7;
      *((_QWORD *)v5 + 3) = 0;
    }
  }
  else
  {
    v5 = 0;
  }
  if ( *((_QWORD *)&pExceptionObject[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&pExceptionObject[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&pExceptionObject[0] + 1))(*((_QWORD *)&pExceptionObject[0] + 1));
      if ( _InterlockedExchangeAdd(
             (volatile signed __int32 *)(*((_QWORD *)&pExceptionObject[0] + 1) + 12LL),
             0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&pExceptionObject[0] + 1) + 8LL))(*((_QWORD *)&pExceptionObject[0]
                                                                                         + 1));
    }
  }
  if ( !v5 )
  {
    std::wstring::wstring(pExceptionObject, L"XML reader IStream creation failed");
    (*((void (__fastcall **)(void **, _OWORD *, __int64))*a1 + 4))(a1, pExceptionObject, 8);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)pExceptionObject);
    utility::details::create_system_error(pExceptionObject, 8);
    throw (std::system_error *)pExceptionObject;
  }
  if ( CreateXmlReader_0(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, a1 + 1, 0) < 0 )
  {
    LastError = GetLastError();
    std::wstring::wstring(pExceptionObject, L"XML reader CreateXmlReader failed");
    (*((void (__fastcall **)(void **, _OWORD *, _QWORD))*a1 + 4))(a1, pExceptionObject, LastError);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)pExceptionObject);
    utility::details::create_system_error(pExceptionObject, LastError);
    throw (std::system_error *)pExceptionObject;
  }
  if ( (*(int (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)a1[1] + 40LL))(a1[1], 4, 0) < 0 )
  {
    v11 = GetLastError();
    std::wstring::wstring(pExceptionObject, L"XML reader SetProperty failed");
    (*((void (__fastcall **)(void **, _OWORD *, _QWORD))*a1 + 4))(a1, pExceptionObject, v11);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)pExceptionObject);
    utility::details::create_system_error(pExceptionObject, v11);
    throw (std::system_error *)pExceptionObject;
  }
  if ( (*(int (__fastcall **)(void *, _DWORD *))(*(_QWORD *)a1[1] + 24LL))(a1[1], v5) < 0 )
  {
    v9 = GetLastError();
    std::wstring::wstring(pExceptionObject, L"XML reader SetInput failed");
    (*((void (__fastcall **)(void **, _OWORD *, _QWORD))*a1 + 4))(a1, pExceptionObject, v9);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)pExceptionObject);
    utility::details::create_system_error(pExceptionObject, v9);
    throw (std::system_error *)pExceptionObject;
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  return pplx::task<long>::~task<long>(a2);
}

```

## disassembly

```asm
0x18009c7b0  mov     [rsp-28h+arg_10], rbx
0x18009c7b5  push    rbp
0x18009c7b6  push    rsi
0x18009c7b7  push    rdi
0x18009c7b8  push    r14
0x18009c7ba  push    r15
0x18009c7bc  mov     rbp, rsp
0x18009c7bf  sub     rsp, 70h
0x18009c7c3  mov     rax, cs:__security_cookie
0x18009c7ca  xor     rax, rsp
0x18009c7cd  mov     [rbp+var_8], rax
0x18009c7d1  mov     r14, rdx
0x18009c7d4  mov     r15, rcx
0x18009c7d7  mov     [rbp+var_38], rdx
0x18009c7db  mov     [rbp+var_40], 0
0x18009c7e3  xorps   xmm0, xmm0
0x18009c7e6  movdqu  [rbp+pExceptionObject], xmm0
0x18009c7eb  mov     rax, [rdx+8]
0x18009c7ef  test    rax, rax
0x18009c7f2  jz      short loc_18009C7F8
0x18009c7f4  lock inc dword ptr [rax+8]
0x18009c7f8  mov     rax, [rdx]
0x18009c7fb  mov     qword ptr [rbp+pExceptionObject], rax
0x18009c7ff  mov     rax, [rdx+8]
0x18009c803  mov     qword ptr [rbp+pExceptionObject+8], rax
0x18009c807  lea     rax, [rbp+pExceptionObject]
0x18009c80b  mov     [rbp+var_50], rax
0x18009c80f  mov     ecx, 20h ; ' '; Size
0x18009c814  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009c819  mov     rdi, rax
0x18009c81c  mov     [rbp+var_50], rax
0x18009c820  mov     esi, 0FFFFFFFFh
0x18009c825  test    rax, rax
0x18009c828  jz      loc_18009C8C0
0x18009c82e  mov     rbx, qword ptr [rbp+pExceptionObject+8]
0x18009c832  test    rbx, rbx
0x18009c835  jz      short loc_18009C83F
0x18009c837  lock inc dword ptr [rbx+8]
0x18009c83b  mov     rbx, qword ptr [rbp+pExceptionObject+8]
0x18009c83f  mov     rax, qword ptr [rbp+pExceptionObject]
0x18009c843  lea     rcx, ??_7xmlstring_stream@xml@core@storage@azure@@6B@; const azure::storage::core::xml::xmlstring_stream::`vftable'
0x18009c84a  mov     [rdi], rcx
0x18009c84d  mov     dword ptr [rdi+8], 1
0x18009c854  lea     rcx, ??_7xmlstring_istream@xml@core@storage@azure@@6B@; const azure::storage::core::xml::xmlstring_istream::`vftable'
0x18009c85b  mov     [rdi], rcx
0x18009c85e  mov     qword ptr [rdi+10h], 0
0x18009c866  mov     qword ptr [rdi+18h], 0
0x18009c86e  test    rbx, rbx
0x18009c871  jz      short loc_18009C8B6
0x18009c873  lock inc dword ptr [rbx+8]
0x18009c877  mov     [rdi+10h], rax
0x18009c87b  mov     [rdi+18h], rbx
0x18009c87f  mov     eax, esi
0x18009c881  lock xadd [rbx+8], eax
0x18009c886  cmp     eax, 1
0x18009c889  jnz     short loc_18009C8C2
0x18009c88b  mov     rax, [rbx]
0x18009c88e  mov     rcx, rbx
0x18009c891  mov     rax, [rax]
0x18009c894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c899  mov     eax, esi
0x18009c89b  lock xadd [rbx+0Ch], eax
0x18009c8a0  cmp     eax, 1
0x18009c8a3  jnz     short loc_18009C8C2
0x18009c8a5  mov     rax, [rbx]
0x18009c8a8  mov     rcx, rbx
0x18009c8ab  mov     rax, [rax+8]
0x18009c8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c8b4  jmp     short loc_18009C8C2
0x18009c8b6  mov     [rdi+10h], rax
0x18009c8ba  mov     [rdi+18h], rbx
0x18009c8be  jmp     short loc_18009C8C2
0x18009c8c0  xor     edi, edi
0x18009c8c2  mov     rbx, qword ptr [rbp+pExceptionObject+8]
0x18009c8c6  test    rbx, rbx
0x18009c8c9  jz      short loc_18009C8FF
0x18009c8cb  mov     eax, esi
0x18009c8cd  lock xadd [rbx+8], eax
0x18009c8d2  cmp     eax, 1
0x18009c8d5  jnz     short loc_18009C8FF
0x18009c8d7  mov     rax, [rbx]
0x18009c8da  mov     rcx, rbx
0x18009c8dd  mov     rax, [rax]
0x18009c8e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c8e5  lock xadd [rbx+0Ch], esi
0x18009c8ea  cmp     esi, 1
0x18009c8ed  jnz     short loc_18009C8FF
0x18009c8ef  mov     rax, [rbx]
0x18009c8f2  mov     rcx, rbx
0x18009c8f5  mov     rax, [rax+8]
0x18009c8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c8fe  nop
0x18009c8ff  mov     [rbp+var_40], rdi
0x18009c903  test    rdi, rdi
0x18009c906  jz      loc_18009C9EC
0x18009c90c  xor     r8d, r8d; pMalloc
0x18009c90f  lea     rdx, [r15+8]; ppvObject
0x18009c913  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18009c91a  call    CreateXmlReader_0
0x18009c91f  test    eax, eax
0x18009c921  js      loc_18009CA3F
0x18009c927  mov     rcx, [r15+8]
0x18009c92b  mov     rax, [rcx]
0x18009c92e  xor     r8d, r8d
0x18009c931  mov     edx, 4
0x18009c936  mov     rax, [rax+28h]
0x18009c93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c93f  test    eax, eax
0x18009c941  js      loc_18009CA94
0x18009c947  mov     rcx, [r15+8]
0x18009c94b  mov     rax, [rcx]
0x18009c94e  mov     rdx, rdi
0x18009c951  mov     rax, [rax+18h]
0x18009c955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c95a  test    eax, eax
0x18009c95c  js      short loc_18009C996
0x18009c95e  mov     rax, [rdi]
0x18009c961  mov     rcx, rdi
0x18009c964  mov     rax, [rax+10h]
0x18009c968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c96d  nop
0x18009c96e  mov     rcx, r14
0x18009c971  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18009c976  mov     rcx, [rbp+var_8]
0x18009c97a  xor     rcx, rsp; StackCookie
0x18009c97d  call    __security_check_cookie
0x18009c982  mov     rbx, [rsp+70h+arg_10]
0x18009c98a  add     rsp, 70h
0x18009c98e  pop     r15
0x18009c990  pop     r14
0x18009c992  pop     rdi
0x18009c993  pop     rsi
0x18009c994  pop     rbp
0x18009c995  retn
0x18009c996  call    cs:__imp_GetLastError
0x18009c99c  nop
0x18009c99d  mov     ebx, eax
0x18009c99f  lea     rdx, aXmlReaderSetin; "XML reader SetInput failed"
0x18009c9a6  lea     rcx, [rbp+pExceptionObject]
0x18009c9aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009c9af  nop
0x18009c9b0  mov     rcx, [r15]
0x18009c9b3  mov     rax, [rcx+20h]
0x18009c9b7  mov     r8d, ebx
0x18009c9ba  lea     rdx, [rbp+pExceptionObject]
0x18009c9be  mov     rcx, r15
0x18009c9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c9c6  nop
0x18009c9c7  lea     rcx, [rbp+pExceptionObject]; this
0x18009c9cb  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009c9d0  mov     edx, ebx
0x18009c9d2  lea     rcx, [rbp+pExceptionObject]
0x18009c9d6  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009c9db  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009c9e2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009c9e6  call    _CxxThrowException_0
0x18009c9ec  lea     rdx, aXmlReaderIstre; "XML reader IStream creation failed"
0x18009c9f3  lea     rcx, [rbp+pExceptionObject]
0x18009c9f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009c9fc  nop
0x18009c9fd  mov     rax, [r15]
0x18009ca00  mov     r8d, 8
0x18009ca06  lea     rdx, [rbp+pExceptionObject]
0x18009ca0a  mov     rcx, r15
0x18009ca0d  mov     rax, [rax+20h]
0x18009ca11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca16  nop
0x18009ca17  lea     rcx, [rbp+pExceptionObject]; this
0x18009ca1b  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009ca20  mov     edx, 8
0x18009ca25  lea     rcx, [rbp+pExceptionObject]
0x18009ca29  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009ca2e  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009ca35  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009ca39  call    _CxxThrowException_0
0x18009ca3f  call    cs:__imp_GetLastError
0x18009ca45  mov     ebx, eax
0x18009ca47  lea     rdx, aXmlReaderCreat; "XML reader CreateXmlReader failed"
0x18009ca4e  lea     rcx, [rbp+pExceptionObject]
0x18009ca52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009ca57  nop
0x18009ca58  mov     rcx, [r15]
0x18009ca5b  mov     rax, [rcx+20h]
0x18009ca5f  mov     r8d, ebx
0x18009ca62  lea     rdx, [rbp+pExceptionObject]
0x18009ca66  mov     rcx, r15
0x18009ca69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca6e  nop
0x18009ca6f  lea     rcx, [rbp+pExceptionObject]; this
0x18009ca73  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009ca78  mov     edx, ebx
0x18009ca7a  lea     rcx, [rbp+pExceptionObject]
0x18009ca7e  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009ca83  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009ca8a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009ca8e  call    _CxxThrowException_0
0x18009ca94  call    cs:__imp_GetLastError
0x18009ca9a  mov     ebx, eax
0x18009ca9c  lea     rdx, aXmlReaderSetpr; "XML reader SetProperty failed"
0x18009caa3  lea     rcx, [rbp+pExceptionObject]
0x18009caa7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009caac  nop
0x18009caad  mov     rcx, [r15]
0x18009cab0  mov     rax, [rcx+20h]
0x18009cab4  mov     r8d, ebx
0x18009cab7  lea     rdx, [rbp+pExceptionObject]
0x18009cabb  mov     rcx, r15
0x18009cabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cac3  nop
0x18009cac4  lea     rcx, [rbp+pExceptionObject]; this
0x18009cac8  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cacd  mov     edx, ebx
0x18009cacf  lea     rcx, [rbp+pExceptionObject]
0x18009cad3  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cad8  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cadf  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cae3  call    _CxxThrowException_0
```
