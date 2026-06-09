# azure::storage::core::xml::xml_writer::initialize(std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x18009cc90`
- end: `0x18009cf3a`
- name: `?initialize@xml_writer@xml@core@storage@azure@@IEAAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009dd50`

## callees

- `0x180019080`
- `0x1800190a4`
- `0x18001a084`
- `0x18001a42b`
- `0x18001b0a0`
- `0x18009cc90`
- `0x1800e68b0`
- `0x1800e7ba0`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cd92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ce3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ce90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cd92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ce3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ce90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cee5`

## string_xrefs

- `0x18009cde8`: `XML writer IStream creation failed`
- `0x18009ce43`: `XML writer CreateXmlWriter failed`
- `0x18009ce98`: `XML writer SetOutput failed`
- `0x18009ceed`: `XML writer SetProperty failed`
- `0x18009cd9b`: `XML writer WriteStartDocument failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall azure::storage::core::xml::xml_writer::initialize(void **a1, __int64 a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  DWORD v7; // ebx
  DWORD LastError; // ebx
  DWORD v9; // ebx
  DWORD v10; // ebx
  _BYTE pExceptionObject[40]; // [rsp+28h] [rbp-40h] BYREF

  v4 = operator new(0x18u);
  v5 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = &azure::storage::core::xml::xmlstring_stream::`vftable';
    v4[2] = 1;
    *(_QWORD *)v4 = &azure::storage::core::xml::xmlstring_ostream::`vftable';
    *((_QWORD *)v4 + 2) = a2;
  }
  else
  {
    v5 = 0;
  }
  if ( !v5 )
  {
    std::wstring::wstring(pExceptionObject, L"XML writer IStream creation failed");
    (*((void (__fastcall **)(void **, _BYTE *, __int64))*a1 + 1))(a1, pExceptionObject, 8);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)pExceptionObject);
    utility::details::create_system_error(pExceptionObject, 8);
    throw (std::system_error *)pExceptionObject;
  }
  if ( CreateXmlWriter_0(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, a1 + 1, 0) < 0 )
  {
    LastError = GetLastError();
    std::wstring::wstring(pExceptionObject, L"XML writer CreateXmlWriter failed");
    (*((void (__fastcall **)(void **, _BYTE *, _QWORD))*a1 + 1))(a1, pExceptionObject, LastError);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)pExceptionObject);
    utility::details::create_system_error(pExceptionObject, LastError);
    throw (std::system_error *)pExceptionObject;
  }
  if ( (*(int (__fastcall **)(void *, _DWORD *))(*(_QWORD *)a1[1] + 24LL))(a1[1], v5) < 0 )
  {
    v9 = GetLastError();
    std::wstring::wstring(pExceptionObject, L"XML writer SetOutput failed");
    (*((void (__fastcall **)(void **, _BYTE *, _QWORD))*a1 + 1))(a1, pExceptionObject, v9);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)pExceptionObject);
    utility::details::create_system_error(pExceptionObject, v9);
    throw (std::system_error *)pExceptionObject;
  }
  if ( (*(int (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)a1[1] + 40LL))(a1[1], 1, 1) < 0 )
  {
    v10 = GetLastError();
    std::wstring::wstring(pExceptionObject, L"XML writer SetProperty failed");
    (*((void (__fastcall **)(void **, _BYTE *, _QWORD))*a1 + 1))(a1, pExceptionObject, v10);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)pExceptionObject);
    utility::details::create_system_error(pExceptionObject, v10);
    throw (std::system_error *)pExceptionObject;
  }
  if ( (*(int (__fastcall **)(void *, _QWORD))(*(_QWORD *)a1[1] + 208LL))(a1[1], 0) < 0 )
  {
    v7 = GetLastError();
    std::wstring::wstring(pExceptionObject, L"XML writer WriteStartDocument failed");
    (*((void (__fastcall **)(void **, _BYTE *, _QWORD))*a1 + 1))(a1, pExceptionObject, v7);
    Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)pExceptionObject);
    utility::details::create_system_error(pExceptionObject, v7);
    throw (std::system_error *)pExceptionObject;
  }
  return (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
}

```

## disassembly

```asm
0x18009cc90  push    rbp
0x18009cc92  push    rbx
0x18009cc93  push    rsi
0x18009cc94  push    rdi
0x18009cc95  mov     rbp, rsp
0x18009cc98  sub     rsp, 68h
0x18009cc9c  mov     rax, cs:__security_cookie
0x18009cca3  xor     rax, rsp
0x18009cca6  mov     [rbp+var_18], rax
0x18009ccaa  mov     rsi, rdx
0x18009ccad  mov     rdi, rcx
0x18009ccb0  mov     [rbp+var_48], 0
0x18009ccb8  mov     ecx, 18h; Size
0x18009ccbd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009ccc2  mov     rbx, rax
0x18009ccc5  mov     [rbp+var_48], rax
0x18009ccc9  test    rax, rax
0x18009cccc  jz      short loc_18009CCEF
0x18009ccce  lea     rax, ??_7xmlstring_stream@xml@core@storage@azure@@6B@; const azure::storage::core::xml::xmlstring_stream::`vftable'
0x18009ccd5  mov     [rbx], rax
0x18009ccd8  mov     dword ptr [rbx+8], 1
0x18009ccdf  lea     rax, ??_7xmlstring_ostream@xml@core@storage@azure@@6B@; const azure::storage::core::xml::xmlstring_ostream::`vftable'
0x18009cce6  mov     [rbx], rax
0x18009cce9  mov     [rbx+10h], rsi
0x18009cced  jmp     short loc_18009CCF1
0x18009ccef  xor     ebx, ebx
0x18009ccf1  mov     [rbp+var_48], rbx
0x18009ccf5  test    rbx, rbx
0x18009ccf8  jz      loc_18009CDE8
0x18009ccfe  xor     r8d, r8d; pMalloc
0x18009cd01  lea     rdx, [rdi+8]; ppvObject
0x18009cd05  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18009cd0c  call    CreateXmlWriter_0
0x18009cd11  test    eax, eax
0x18009cd13  js      loc_18009CE3B
0x18009cd19  mov     rcx, [rdi+8]
0x18009cd1d  mov     rax, [rcx]
0x18009cd20  mov     rdx, rbx
0x18009cd23  mov     rax, [rax+18h]
0x18009cd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cd2c  test    eax, eax
0x18009cd2e  js      loc_18009CE90
0x18009cd34  mov     rcx, [rdi+8]
0x18009cd38  mov     rax, [rcx]
0x18009cd3b  mov     edx, 1
0x18009cd40  mov     r8d, edx
0x18009cd43  mov     rax, [rax+28h]
0x18009cd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cd4c  test    eax, eax
0x18009cd4e  js      loc_18009CEE5
0x18009cd54  mov     rcx, [rdi+8]
0x18009cd58  mov     rax, [rcx]
0x18009cd5b  xor     edx, edx
0x18009cd5d  mov     rax, [rax+0D0h]
0x18009cd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cd69  test    eax, eax
0x18009cd6b  js      short loc_18009CD92
0x18009cd6d  mov     rax, [rbx]
0x18009cd70  mov     rcx, rbx
0x18009cd73  mov     rax, [rax+10h]
0x18009cd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cd7c  nop
0x18009cd7d  mov     rcx, [rbp+var_18]
0x18009cd81  xor     rcx, rsp; StackCookie
0x18009cd84  call    __security_check_cookie
0x18009cd89  add     rsp, 68h
0x18009cd8d  pop     rdi
0x18009cd8e  pop     rsi
0x18009cd8f  pop     rbx
0x18009cd90  pop     rbp
0x18009cd91  retn
0x18009cd92  call    cs:__imp_GetLastError
0x18009cd98  nop
0x18009cd99  mov     ebx, eax
0x18009cd9b  lea     rdx, aXmlWriterWrite_1; "XML writer WriteStartDocument failed"
0x18009cda2  lea     rcx, [rbp+pExceptionObject]
0x18009cda6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cdab  nop
0x18009cdac  mov     rcx, [rdi]
0x18009cdaf  mov     rax, [rcx+8]
0x18009cdb3  mov     r8d, ebx
0x18009cdb6  lea     rdx, [rbp+pExceptionObject]
0x18009cdba  mov     rcx, rdi
0x18009cdbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cdc2  nop
0x18009cdc3  lea     rcx, [rbp+pExceptionObject]; this
0x18009cdc7  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cdcc  mov     edx, ebx
0x18009cdce  lea     rcx, [rbp+pExceptionObject]
0x18009cdd2  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cdd7  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cdde  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cde2  call    _CxxThrowException_0
0x18009cde8  lea     rdx, aXmlWriterIstre; "XML writer IStream creation failed"
0x18009cdef  lea     rcx, [rbp+pExceptionObject]
0x18009cdf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cdf8  nop
0x18009cdf9  mov     rax, [rdi]
0x18009cdfc  mov     r8d, 8
0x18009ce02  lea     rdx, [rbp+pExceptionObject]
0x18009ce06  mov     rcx, rdi
0x18009ce09  mov     rax, [rax+8]
0x18009ce0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ce12  nop
0x18009ce13  lea     rcx, [rbp+pExceptionObject]; this
0x18009ce17  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009ce1c  mov     edx, 8
0x18009ce21  lea     rcx, [rbp+pExceptionObject]
0x18009ce25  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009ce2a  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009ce31  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009ce35  call    _CxxThrowException_0
0x18009ce3b  call    cs:__imp_GetLastError
0x18009ce41  mov     ebx, eax
0x18009ce43  lea     rdx, aXmlWriterCreat; "XML writer CreateXmlWriter failed"
0x18009ce4a  lea     rcx, [rbp+pExceptionObject]
0x18009ce4e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009ce53  nop
0x18009ce54  mov     rcx, [rdi]
0x18009ce57  mov     rax, [rcx+8]
0x18009ce5b  mov     r8d, ebx
0x18009ce5e  lea     rdx, [rbp+pExceptionObject]
0x18009ce62  mov     rcx, rdi
0x18009ce65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ce6a  nop
0x18009ce6b  lea     rcx, [rbp+pExceptionObject]; this
0x18009ce6f  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009ce74  mov     edx, ebx
0x18009ce76  lea     rcx, [rbp+pExceptionObject]
0x18009ce7a  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009ce7f  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009ce86  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009ce8a  call    _CxxThrowException_0
0x18009ce90  call    cs:__imp_GetLastError
0x18009ce96  mov     ebx, eax
0x18009ce98  lea     rdx, aXmlWriterSetou; "XML writer SetOutput failed"
0x18009ce9f  lea     rcx, [rbp+pExceptionObject]
0x18009cea3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cea8  nop
0x18009cea9  mov     rcx, [rdi]
0x18009ceac  mov     rax, [rcx+8]
0x18009ceb0  mov     r8d, ebx
0x18009ceb3  lea     rdx, [rbp+pExceptionObject]
0x18009ceb7  mov     rcx, rdi
0x18009ceba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cebf  nop
0x18009cec0  lea     rcx, [rbp+pExceptionObject]; this
0x18009cec4  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cec9  mov     edx, ebx
0x18009cecb  lea     rcx, [rbp+pExceptionObject]
0x18009cecf  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009ced4  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cedb  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cedf  call    _CxxThrowException_0
0x18009cee5  call    cs:__imp_GetLastError
0x18009ceeb  mov     ebx, eax
0x18009ceed  lea     rdx, aXmlWriterSetpr; "XML writer SetProperty failed"
0x18009cef4  lea     rcx, [rbp+pExceptionObject]
0x18009cef8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cefd  nop
0x18009cefe  mov     rcx, [rdi]
0x18009cf01  mov     rax, [rcx+8]
0x18009cf05  mov     r8d, ebx
0x18009cf08  lea     rdx, [rbp+pExceptionObject]
0x18009cf0c  mov     rcx, rdi
0x18009cf0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cf14  nop
0x18009cf15  lea     rcx, [rbp+pExceptionObject]; this
0x18009cf19  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cf1e  mov     edx, ebx
0x18009cf20  lea     rcx, [rbp+pExceptionObject]
0x18009cf24  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cf29  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cf30  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cf34  call    _CxxThrowException_0
```
