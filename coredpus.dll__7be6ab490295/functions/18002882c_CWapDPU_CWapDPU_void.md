# CWapDPU::~CWapDPU(void)

- ea: `0x18002882c`
- end: `0x18002890c`
- name: `??1CWapDPU@@UEAA@XZ`
- size: `224`
- prototype: `void __fastcall(CWapDPU *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800289d0`

## callees

- `0x180001190`
- `0x180010ae8`
- `0x1800110bc`
- `0x18002882c`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180028880`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180028880`
- `OLEAUT32!__imp_SysFreeString` at `0x18002885f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002885f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800288d2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800288d2`

## pseudocode

```c
void __fastcall CWapDPU::~CWapDPU(CWapDPU *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CWapDPU::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 296LL))(v2);
  SysFreeString(*((BSTR *)this + 7));
  if ( byte_18003ED84 )
    EventActivityIdControl(4u, &stru_18003ED98);
  WapDpuActivity = 2;
  if ( (unsigned int)dword_18003E080 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18003E080,
      byte_180037BDD,
      &stru_18003ED88,
      0);
  _InterlockedDecrement(&dword_18003EBFC);
  std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)this + 112);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((char *)this + 32);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((char *)this + 24);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((char *)this + 16);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((char *)this + 8);
}

```

## disassembly

```asm
0x18002882c  mov     [rsp+arg_0], rbx
0x180028831  push    rdi
0x180028832  sub     rsp, 20h
0x180028836  mov     rbx, rcx
0x180028839  lea     rax, ??_7CWapDPU@@6B@; const CWapDPU::`vftable'
0x180028840  mov     [rcx], rax
0x180028843  mov     rcx, [rcx+10h]
0x180028847  test    rcx, rcx
0x18002884a  jz      short loc_18002885B
0x18002884c  mov     rax, [rcx]
0x18002884f  mov     rax, [rax+128h]
0x180028856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002885b  mov     rcx, [rbx+38h]; bstrString
0x18002885f  call    cs:__imp_SysFreeString
0x180028866  nop     dword ptr [rax+rax+00h]
0x18002886b  cmp     cs:byte_18003ED84, 0
0x180028872  jz      short loc_18002888C
0x180028874  lea     rdx, stru_18003ED98; ActivityId
0x18002887b  mov     ecx, 4; ControlCode
0x180028880  call    cs:__imp_EventActivityIdControl
0x180028887  nop     dword ptr [rax+rax+00h]
0x18002888c  mov     cs:?WapDpuActivity@@3V?$TraceLoggingThreadActivity@$1?g_hWAPTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, 2; TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hWAPTraceLoggingProvider,0,5,_TlgReflectorTag_Param0IsHProvider> WapDpuActivity
0x180028896  mov     eax, cs:dword_18003E080
0x18002889c  cmp     eax, 5
0x18002889f  jbe     short loc_1800288BE
0x1800288a1  xor     r9d, r9d
0x1800288a4  lea     r8, stru_18003ED88
0x1800288ab  lea     rdx, byte_180037BDD
0x1800288b2  lea     rcx, dword_18003E080
0x1800288b9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800288be  lock dec cs:dword_18003EBFC
0x1800288c5  lea     rcx, [rbx+70h]
0x1800288c9  call    ??1?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x1800288ce  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800288d2  call    cs:__imp_DeleteCriticalSection
0x1800288d9  nop     dword ptr [rax+rax+00h]
0x1800288de  lea     rcx, [rbx+20h]
0x1800288e2  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800288e7  lea     rcx, [rbx+18h]
0x1800288eb  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800288f0  lea     rcx, [rbx+10h]
0x1800288f4  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800288f9  lea     rcx, [rbx+8]
0x1800288fd  mov     rbx, [rsp+28h+arg_0]
0x180028902  add     rsp, 20h
0x180028906  pop     rdi
0x180028907  jmp     ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
```
