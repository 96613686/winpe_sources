# azure::storage::core::xml::xml_writer::initialize(std::basic_ostream<char,std::char_traits<char>> &)

- ea: `0x18009caf0`
- end: `0x18009cd9a`
- name: `?initialize@xml_writer@xml@core@storage@azure@@IEAAXAEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z`
- size: `682`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18009dbb0`

## callees

- `0x180019000`
- `0x180019024`
- `0x180019ff4`
- `0x18001a39b`
- `0x18001afc0`
- `0x18009caf0`
- `0x1800e66dc`
- `0x1800e79e0`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cbf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ccf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cd45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cbf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ccf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cd45`

## string_xrefs

- `0x18009cc48`: `XML writer IStream creation failed`
- `0x18009cca3`: `XML writer CreateXmlWriter failed`
- `0x18009ccf8`: `XML writer SetOutput failed`
- `0x18009cd4d`: `XML writer SetProperty failed`
- `0x18009cbfb`: `XML writer WriteStartDocument failed`

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
0x18009caf0  push    rbp
0x18009caf2  push    rbx
0x18009caf3  push    rsi
0x18009caf4  push    rdi
0x18009caf5  mov     rbp, rsp
0x18009caf8  sub     rsp, 68h
0x18009cafc  mov     rax, cs:__security_cookie
0x18009cb03  xor     rax, rsp
0x18009cb06  mov     [rbp+var_18], rax
0x18009cb0a  mov     rsi, rdx
0x18009cb0d  mov     rdi, rcx
0x18009cb10  mov     [rbp+var_48], 0
0x18009cb18  mov     ecx, 18h; Size
0x18009cb1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009cb22  mov     rbx, rax
0x18009cb25  mov     [rbp+var_48], rax
0x18009cb29  test    rax, rax
0x18009cb2c  jz      short loc_18009CB4F
0x18009cb2e  lea     rax, ??_7xmlstring_stream@xml@core@storage@azure@@6B@; const azure::storage::core::xml::xmlstring_stream::`vftable'
0x18009cb35  mov     [rbx], rax
0x18009cb38  mov     dword ptr [rbx+8], 1
0x18009cb3f  lea     rax, ??_7xmlstring_ostream@xml@core@storage@azure@@6B@; const azure::storage::core::xml::xmlstring_ostream::`vftable'
0x18009cb46  mov     [rbx], rax
0x18009cb49  mov     [rbx+10h], rsi
0x18009cb4d  jmp     short loc_18009CB51
0x18009cb4f  xor     ebx, ebx
0x18009cb51  mov     [rbp+var_48], rbx
0x18009cb55  test    rbx, rbx
0x18009cb58  jz      loc_18009CC48
0x18009cb5e  xor     r8d, r8d; pMalloc
0x18009cb61  lea     rdx, [rdi+8]; ppvObject
0x18009cb65  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18009cb6c  call    CreateXmlWriter_0
0x18009cb71  test    eax, eax
0x18009cb73  js      loc_18009CC9B
0x18009cb79  mov     rcx, [rdi+8]
0x18009cb7d  mov     rax, [rcx]
0x18009cb80  mov     rdx, rbx
0x18009cb83  mov     rax, [rax+18h]
0x18009cb87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cb8c  test    eax, eax
0x18009cb8e  js      loc_18009CCF0
0x18009cb94  mov     rcx, [rdi+8]
0x18009cb98  mov     rax, [rcx]
0x18009cb9b  mov     edx, 1
0x18009cba0  mov     r8d, edx
0x18009cba3  mov     rax, [rax+28h]
0x18009cba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cbac  test    eax, eax
0x18009cbae  js      loc_18009CD45
0x18009cbb4  mov     rcx, [rdi+8]
0x18009cbb8  mov     rax, [rcx]
0x18009cbbb  xor     edx, edx
0x18009cbbd  mov     rax, [rax+0D0h]
0x18009cbc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cbc9  test    eax, eax
0x18009cbcb  js      short loc_18009CBF2
0x18009cbcd  mov     rax, [rbx]
0x18009cbd0  mov     rcx, rbx
0x18009cbd3  mov     rax, [rax+10h]
0x18009cbd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cbdc  nop
0x18009cbdd  mov     rcx, [rbp+var_18]
0x18009cbe1  xor     rcx, rsp; StackCookie
0x18009cbe4  call    __security_check_cookie
0x18009cbe9  add     rsp, 68h
0x18009cbed  pop     rdi
0x18009cbee  pop     rsi
0x18009cbef  pop     rbx
0x18009cbf0  pop     rbp
0x18009cbf1  retn
0x18009cbf2  call    cs:__imp_GetLastError
0x18009cbf8  nop
0x18009cbf9  mov     ebx, eax
0x18009cbfb  lea     rdx, aXmlWriterWrite_1; "XML writer WriteStartDocument failed"
0x18009cc02  lea     rcx, [rbp+pExceptionObject]
0x18009cc06  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cc0b  nop
0x18009cc0c  mov     rcx, [rdi]
0x18009cc0f  mov     rax, [rcx+8]
0x18009cc13  mov     r8d, ebx
0x18009cc16  lea     rdx, [rbp+pExceptionObject]
0x18009cc1a  mov     rcx, rdi
0x18009cc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cc22  nop
0x18009cc23  lea     rcx, [rbp+pExceptionObject]; this
0x18009cc27  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cc2c  mov     edx, ebx
0x18009cc2e  lea     rcx, [rbp+pExceptionObject]
0x18009cc32  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cc37  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cc3e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cc42  call    _CxxThrowException_0
0x18009cc48  lea     rdx, aXmlWriterIstre; "XML writer IStream creation failed"
0x18009cc4f  lea     rcx, [rbp+pExceptionObject]
0x18009cc53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cc58  nop
0x18009cc59  mov     rax, [rdi]
0x18009cc5c  mov     r8d, 8
0x18009cc62  lea     rdx, [rbp+pExceptionObject]
0x18009cc66  mov     rcx, rdi
0x18009cc69  mov     rax, [rax+8]
0x18009cc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cc72  nop
0x18009cc73  lea     rcx, [rbp+pExceptionObject]; this
0x18009cc77  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cc7c  mov     edx, 8
0x18009cc81  lea     rcx, [rbp+pExceptionObject]
0x18009cc85  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cc8a  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cc91  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cc95  call    _CxxThrowException_0
0x18009cc9b  call    cs:__imp_GetLastError
0x18009cca1  mov     ebx, eax
0x18009cca3  lea     rdx, aXmlWriterCreat; "XML writer CreateXmlWriter failed"
0x18009ccaa  lea     rcx, [rbp+pExceptionObject]
0x18009ccae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009ccb3  nop
0x18009ccb4  mov     rcx, [rdi]
0x18009ccb7  mov     rax, [rcx+8]
0x18009ccbb  mov     r8d, ebx
0x18009ccbe  lea     rdx, [rbp+pExceptionObject]
0x18009ccc2  mov     rcx, rdi
0x18009ccc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ccca  nop
0x18009cccb  lea     rcx, [rbp+pExceptionObject]; this
0x18009cccf  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009ccd4  mov     edx, ebx
0x18009ccd6  lea     rcx, [rbp+pExceptionObject]
0x18009ccda  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009ccdf  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cce6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009ccea  call    _CxxThrowException_0
0x18009ccf0  call    cs:__imp_GetLastError
0x18009ccf6  mov     ebx, eax
0x18009ccf8  lea     rdx, aXmlWriterSetou; "XML writer SetOutput failed"
0x18009ccff  lea     rcx, [rbp+pExceptionObject]
0x18009cd03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cd08  nop
0x18009cd09  mov     rcx, [rdi]
0x18009cd0c  mov     rax, [rcx+8]
0x18009cd10  mov     r8d, ebx
0x18009cd13  lea     rdx, [rbp+pExceptionObject]
0x18009cd17  mov     rcx, rdi
0x18009cd1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cd1f  nop
0x18009cd20  lea     rcx, [rbp+pExceptionObject]; this
0x18009cd24  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cd29  mov     edx, ebx
0x18009cd2b  lea     rcx, [rbp+pExceptionObject]
0x18009cd2f  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cd34  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cd3b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cd3f  call    _CxxThrowException_0
0x18009cd45  call    cs:__imp_GetLastError
0x18009cd4b  mov     ebx, eax
0x18009cd4d  lea     rdx, aXmlWriterSetpr; "XML writer SetProperty failed"
0x18009cd54  lea     rcx, [rbp+pExceptionObject]
0x18009cd58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cd5d  nop
0x18009cd5e  mov     rcx, [rdi]
0x18009cd61  mov     rax, [rcx+8]
0x18009cd65  mov     r8d, ebx
0x18009cd68  lea     rdx, [rbp+pExceptionObject]
0x18009cd6c  mov     rcx, rdi
0x18009cd6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cd74  nop
0x18009cd75  lea     rcx, [rbp+pExceptionObject]; this
0x18009cd79  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cd7e  mov     edx, ebx
0x18009cd80  lea     rcx, [rbp+pExceptionObject]
0x18009cd84  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cd89  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cd90  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cd94  call    _CxxThrowException_0
```
