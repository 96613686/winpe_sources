# azure::storage::core::xml::xml_reader::initialize(Concurrency::streams::basic_istream<uchar>)

- ea: `0x18009c950`
- end: `0x18009cc89`
- name: `?initialize@xml_reader@xml@core@storage@azure@@IEAAXV?$basic_istream@E@streams@Concurrency@@@Z`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180095d60`

## callees

- `0x180019080`
- `0x1800190a4`
- `0x18001a084`
- `0x18001a437`
- `0x18001b0a0`
- `0x180048c30`
- `0x18009c950`
- `0x1800e68b0`
- `0x1800e7ba0`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cbdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cb36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cbdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc34`

## string_xrefs

- `0x18009cb8c`: `XML reader IStream creation failed`
- `0x18009cbe7`: `XML reader CreateXmlReader failed`
- `0x18009cc3c`: `XML reader SetProperty failed`
- `0x18009cb3f`: `XML reader SetInput failed`

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
0x18009c950  mov     [rsp-28h+arg_10], rbx
0x18009c955  push    rbp
0x18009c956  push    rsi
0x18009c957  push    rdi
0x18009c958  push    r14
0x18009c95a  push    r15
0x18009c95c  mov     rbp, rsp
0x18009c95f  sub     rsp, 70h
0x18009c963  mov     rax, cs:__security_cookie
0x18009c96a  xor     rax, rsp
0x18009c96d  mov     [rbp+var_8], rax
0x18009c971  mov     r14, rdx
0x18009c974  mov     r15, rcx
0x18009c977  mov     [rbp+var_38], rdx
0x18009c97b  mov     [rbp+var_40], 0
0x18009c983  xorps   xmm0, xmm0
0x18009c986  movdqu  [rbp+pExceptionObject], xmm0
0x18009c98b  mov     rax, [rdx+8]
0x18009c98f  test    rax, rax
0x18009c992  jz      short loc_18009C998
0x18009c994  lock inc dword ptr [rax+8]
0x18009c998  mov     rax, [rdx]
0x18009c99b  mov     qword ptr [rbp+pExceptionObject], rax
0x18009c99f  mov     rax, [rdx+8]
0x18009c9a3  mov     qword ptr [rbp+pExceptionObject+8], rax
0x18009c9a7  lea     rax, [rbp+pExceptionObject]
0x18009c9ab  mov     [rbp+var_50], rax
0x18009c9af  mov     ecx, 20h ; ' '; Size
0x18009c9b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009c9b9  mov     rdi, rax
0x18009c9bc  mov     [rbp+var_50], rax
0x18009c9c0  mov     esi, 0FFFFFFFFh
0x18009c9c5  test    rax, rax
0x18009c9c8  jz      loc_18009CA60
0x18009c9ce  mov     rbx, qword ptr [rbp+pExceptionObject+8]
0x18009c9d2  test    rbx, rbx
0x18009c9d5  jz      short loc_18009C9DF
0x18009c9d7  lock inc dword ptr [rbx+8]
0x18009c9db  mov     rbx, qword ptr [rbp+pExceptionObject+8]
0x18009c9df  mov     rax, qword ptr [rbp+pExceptionObject]
0x18009c9e3  lea     rcx, ??_7xmlstring_stream@xml@core@storage@azure@@6B@; const azure::storage::core::xml::xmlstring_stream::`vftable'
0x18009c9ea  mov     [rdi], rcx
0x18009c9ed  mov     dword ptr [rdi+8], 1
0x18009c9f4  lea     rcx, ??_7xmlstring_istream@xml@core@storage@azure@@6B@; const azure::storage::core::xml::xmlstring_istream::`vftable'
0x18009c9fb  mov     [rdi], rcx
0x18009c9fe  mov     qword ptr [rdi+10h], 0
0x18009ca06  mov     qword ptr [rdi+18h], 0
0x18009ca0e  test    rbx, rbx
0x18009ca11  jz      short loc_18009CA56
0x18009ca13  lock inc dword ptr [rbx+8]
0x18009ca17  mov     [rdi+10h], rax
0x18009ca1b  mov     [rdi+18h], rbx
0x18009ca1f  mov     eax, esi
0x18009ca21  lock xadd [rbx+8], eax
0x18009ca26  cmp     eax, 1
0x18009ca29  jnz     short loc_18009CA62
0x18009ca2b  mov     rax, [rbx]
0x18009ca2e  mov     rcx, rbx
0x18009ca31  mov     rax, [rax]
0x18009ca34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca39  mov     eax, esi
0x18009ca3b  lock xadd [rbx+0Ch], eax
0x18009ca40  cmp     eax, 1
0x18009ca43  jnz     short loc_18009CA62
0x18009ca45  mov     rax, [rbx]
0x18009ca48  mov     rcx, rbx
0x18009ca4b  mov     rax, [rax+8]
0x18009ca4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca54  jmp     short loc_18009CA62
0x18009ca56  mov     [rdi+10h], rax
0x18009ca5a  mov     [rdi+18h], rbx
0x18009ca5e  jmp     short loc_18009CA62
0x18009ca60  xor     edi, edi
0x18009ca62  mov     rbx, qword ptr [rbp+pExceptionObject+8]
0x18009ca66  test    rbx, rbx
0x18009ca69  jz      short loc_18009CA9F
0x18009ca6b  mov     eax, esi
0x18009ca6d  lock xadd [rbx+8], eax
0x18009ca72  cmp     eax, 1
0x18009ca75  jnz     short loc_18009CA9F
0x18009ca77  mov     rax, [rbx]
0x18009ca7a  mov     rcx, rbx
0x18009ca7d  mov     rax, [rax]
0x18009ca80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca85  lock xadd [rbx+0Ch], esi
0x18009ca8a  cmp     esi, 1
0x18009ca8d  jnz     short loc_18009CA9F
0x18009ca8f  mov     rax, [rbx]
0x18009ca92  mov     rcx, rbx
0x18009ca95  mov     rax, [rax+8]
0x18009ca99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ca9e  nop
0x18009ca9f  mov     [rbp+var_40], rdi
0x18009caa3  test    rdi, rdi
0x18009caa6  jz      loc_18009CB8C
0x18009caac  xor     r8d, r8d; pMalloc
0x18009caaf  lea     rdx, [r15+8]; ppvObject
0x18009cab3  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18009caba  call    CreateXmlReader_0
0x18009cabf  test    eax, eax
0x18009cac1  js      loc_18009CBDF
0x18009cac7  mov     rcx, [r15+8]
0x18009cacb  mov     rax, [rcx]
0x18009cace  xor     r8d, r8d
0x18009cad1  mov     edx, 4
0x18009cad6  mov     rax, [rax+28h]
0x18009cada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cadf  test    eax, eax
0x18009cae1  js      loc_18009CC34
0x18009cae7  mov     rcx, [r15+8]
0x18009caeb  mov     rax, [rcx]
0x18009caee  mov     rdx, rdi
0x18009caf1  mov     rax, [rax+18h]
0x18009caf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cafa  test    eax, eax
0x18009cafc  js      short loc_18009CB36
0x18009cafe  mov     rax, [rdi]
0x18009cb01  mov     rcx, rdi
0x18009cb04  mov     rax, [rax+10h]
0x18009cb08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cb0d  nop
0x18009cb0e  mov     rcx, r14
0x18009cb11  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x18009cb16  mov     rcx, [rbp+var_8]
0x18009cb1a  xor     rcx, rsp; StackCookie
0x18009cb1d  call    __security_check_cookie
0x18009cb22  mov     rbx, [rsp+70h+arg_10]
0x18009cb2a  add     rsp, 70h
0x18009cb2e  pop     r15
0x18009cb30  pop     r14
0x18009cb32  pop     rdi
0x18009cb33  pop     rsi
0x18009cb34  pop     rbp
0x18009cb35  retn
0x18009cb36  call    cs:__imp_GetLastError
0x18009cb3c  nop
0x18009cb3d  mov     ebx, eax
0x18009cb3f  lea     rdx, aXmlReaderSetin; "XML reader SetInput failed"
0x18009cb46  lea     rcx, [rbp+pExceptionObject]
0x18009cb4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cb4f  nop
0x18009cb50  mov     rcx, [r15]
0x18009cb53  mov     rax, [rcx+20h]
0x18009cb57  mov     r8d, ebx
0x18009cb5a  lea     rdx, [rbp+pExceptionObject]
0x18009cb5e  mov     rcx, r15
0x18009cb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cb66  nop
0x18009cb67  lea     rcx, [rbp+pExceptionObject]; this
0x18009cb6b  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cb70  mov     edx, ebx
0x18009cb72  lea     rcx, [rbp+pExceptionObject]
0x18009cb76  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cb7b  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cb82  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cb86  call    _CxxThrowException_0
0x18009cb8c  lea     rdx, aXmlReaderIstre; "XML reader IStream creation failed"
0x18009cb93  lea     rcx, [rbp+pExceptionObject]
0x18009cb97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cb9c  nop
0x18009cb9d  mov     rax, [r15]
0x18009cba0  mov     r8d, 8
0x18009cba6  lea     rdx, [rbp+pExceptionObject]
0x18009cbaa  mov     rcx, r15
0x18009cbad  mov     rax, [rax+20h]
0x18009cbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cbb6  nop
0x18009cbb7  lea     rcx, [rbp+pExceptionObject]; this
0x18009cbbb  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cbc0  mov     edx, 8
0x18009cbc5  lea     rcx, [rbp+pExceptionObject]
0x18009cbc9  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cbce  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cbd5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cbd9  call    _CxxThrowException_0
0x18009cbdf  call    cs:__imp_GetLastError
0x18009cbe5  mov     ebx, eax
0x18009cbe7  lea     rdx, aXmlReaderCreat; "XML reader CreateXmlReader failed"
0x18009cbee  lea     rcx, [rbp+pExceptionObject]
0x18009cbf2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cbf7  nop
0x18009cbf8  mov     rcx, [r15]
0x18009cbfb  mov     rax, [rcx+20h]
0x18009cbff  mov     r8d, ebx
0x18009cc02  lea     rdx, [rbp+pExceptionObject]
0x18009cc06  mov     rcx, r15
0x18009cc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cc0e  nop
0x18009cc0f  lea     rcx, [rbp+pExceptionObject]; this
0x18009cc13  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cc18  mov     edx, ebx
0x18009cc1a  lea     rcx, [rbp+pExceptionObject]
0x18009cc1e  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cc23  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cc2a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cc2e  call    _CxxThrowException_0
0x18009cc34  call    cs:__imp_GetLastError
0x18009cc3a  mov     ebx, eax
0x18009cc3c  lea     rdx, aXmlReaderSetpr; "XML reader SetProperty failed"
0x18009cc43  lea     rcx, [rbp+pExceptionObject]
0x18009cc47  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009cc4c  nop
0x18009cc4d  mov     rcx, [r15]
0x18009cc50  mov     rax, [rcx+20h]
0x18009cc54  mov     r8d, ebx
0x18009cc57  lea     rdx, [rbp+pExceptionObject]
0x18009cc5b  mov     rcx, r15
0x18009cc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cc63  nop
0x18009cc64  lea     rcx, [rbp+pExceptionObject]; this
0x18009cc68  call    ??1DeviceOrUserTargetId@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId(void)
0x18009cc6d  mov     edx, ebx
0x18009cc6f  lea     rcx, [rbp+pExceptionObject]
0x18009cc73  call    ?create_system_error@details@utility@@YA?AVsystem_error@std@@K@Z; utility::details::create_system_error(ulong)
0x18009cc78  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18009cc7f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18009cc83  call    _CxxThrowException_0
```
