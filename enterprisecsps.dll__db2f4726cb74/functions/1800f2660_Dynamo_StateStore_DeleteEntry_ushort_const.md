# Dynamo::StateStore::DeleteEntry(ushort const *)

- ea: `0x1800f2660`
- end: `0x1800f2859`
- name: `?DeleteEntry@StateStore@Dynamo@@UEAAXPEBG@Z`
- size: `505`
- prototype: `void __fastcall(Dynamo::StateStore *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180019fbc`
- `0x180023874`
- `0x180025a78`
- `0x180025ac0`
- `0x18002dc38`
- `0x18002dcc8`
- `0x180056fbc`
- `0x180056fd8`
- `0x180056ff0`
- `0x18005714c`
- `0x18006006c`
- `0x1800eaa40`
- `0x1800f2660`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f277b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800f277b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800f27b9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800f27b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f271f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f271f`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x1800f275c`
- `DMCmnUtils!OmDmRegistryAllocAndGetString` at `0x1800f275c`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x1800f26a5`
- `DMCmnUtils!OmaDmRegistryGetAllSubKeys` at `0x1800f26a5`

## string_xrefs

- `0x1800f2751`: `NodeUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Dynamo::StateStore::DeleteEntry(HKEY *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned __int16 ***v6; // r8
  int AllSubKeys; // eax
  const WCHAR **v8; // rbx
  __int64 v9; // rdi
  const WCHAR *v10; // rsi
  unsigned int v11; // eax
  int String; // eax
  unsigned int v13; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  _QWORD v15[2]; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v16[16]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  HKEY v18; // [rsp+80h] [rbp+30h] BYREF
  __int64 v19; // [rsp+90h] [rbp+40h] BYREF

  std::_Ptr_base<CCertificateStore>::_Ptr_base<CCertificateStore>(v15);
  v4 = wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(v15);
  v5 = wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<unsigned long>::size_address_ptr<unsigned long>(
         v16,
         v15,
         v4);
  AllSubKeys = OmaDmRegistryGetAllSubKeys(this[3], (unsigned int *)(v5 + 8), v6);
  if ( AllSubKeys < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
      (const char *)(unsigned int)AllSubKeys,
      phkResult);
  wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<unsigned long>::~size_address_ptr<unsigned long>(v16);
  v8 = (const WCHAR **)v15[0];
  v9 = wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::end(v15);
  while ( 1 )
  {
    if ( v8 == (const WCHAR **)v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7E,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
        (const char *)2,
        phkResult);
    v10 = *v8;
    v18 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v18,
      0);
    v11 = RegOpenKeyExW(this[3], v10, 0, 0x20019u, &v18);
    if ( v11 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
        (const char *)v11,
        phkResult);
    v19 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v19,
      0);
    String = OmDmRegistryAllocAndGetString(v18, L"NodeUri", 0, &v19);
    if ( String < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
        (const char *)(unsigned int)String,
        phkResult);
    if ( !(unsigned int)_o__wcsicmp(a2, v19) )
      break;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
    ++v8;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v18,
    0);
  v13 = RegDeleteTreeW(this[3], v10);
  if ( v13 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\statestore.cpp",
      (const char *)v13,
      phkResult);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
  wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>(v15);
}

```

## disassembly

```asm
0x1800f2660  mov     [rsp-28h+arg_8], rbx
0x1800f2665  push    rbp
0x1800f2666  push    rsi
0x1800f2667  push    rdi
0x1800f2668  push    r14
0x1800f266a  push    r15
0x1800f266c  mov     rbp, rsp
0x1800f266f  sub     rsp, 50h
0x1800f2673  mov     r15, rdx
0x1800f2676  mov     r14, rcx
0x1800f2679  lea     rcx, [rbp+var_20]
0x1800f267d  call    ??0?$_Ptr_base@VCCertificateStore@@@std@@IEAA@XZ; std::_Ptr_base<CCertificateStore>::_Ptr_base<CCertificateStore>(void)
0x1800f2682  nop
0x1800f2683  lea     rcx, [rbp+var_20]
0x1800f2687  call    ??I?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAPEAPEAPEAGXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::operator&(void)
0x1800f268c  mov     r8, rax
0x1800f268f  lea     rdx, [rbp+var_20]
0x1800f2693  lea     rcx, [rbp+var_10]
0x1800f2697  call    ??0?$size_address_ptr@K@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@AEAV12@@Z; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<ulong>::size_address_ptr<ulong>(wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64> &)
0x1800f269c  nop
0x1800f269d  lea     rdx, [rax+8]
0x1800f26a1  mov     rcx, [r14+18h]
0x1800f26a5  call    cs:__imp_?OmaDmRegistryGetAllSubKeys@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z; OmaDmRegistryGetAllSubKeys(HKEY__ *,ulong *,ushort * * *)
0x1800f26ac  nop     dword ptr [rax+rax+00h]
0x1800f26b1  mov     rcx, [rbp+28h]; this
0x1800f26b5  test    eax, eax
0x1800f26b7  jns     short loc_1800F26CE
0x1800f26b9  mov     r9d, eax; char *
0x1800f26bc  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f26c3  mov     edx, 6Ch ; 'l'; void *
0x1800f26c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f26ce  lea     rcx, [rbp+var_10]
0x1800f26d2  call    ??1?$size_address_ptr@K@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::size_address_ptr<ulong>::~size_address_ptr<ulong>(void)
0x1800f26d7  mov     rbx, [rbp+var_20]
0x1800f26db  lea     rcx, [rbp+var_20]
0x1800f26df  call    ?end@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAPEAPEAGXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::end(void)
0x1800f26e4  mov     rdi, rax
0x1800f26e7  cmp     rbx, rdi
0x1800f26ea  jz      loc_1800F283E
0x1800f26f0  mov     rsi, [rbx]
0x1800f26f3  mov     [rbp+arg_0], 0
0x1800f26fb  xor     edx, edx
0x1800f26fd  lea     rcx, [rbp+arg_0]
0x1800f2701  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800f2706  lea     rax, [rbp+arg_0]
0x1800f270a  mov     qword ptr [rsp+50h+phkResult], rax; unsigned int
0x1800f270f  mov     r9d, 20019h; samDesired
0x1800f2715  xor     r8d, r8d; ulOptions
0x1800f2718  mov     rdx, rsi; lpSubKey
0x1800f271b  mov     rcx, [r14+18h]; hKey
0x1800f271f  call    cs:__imp_RegOpenKeyExW
0x1800f2726  nop     dword ptr [rax+rax+00h]
0x1800f272b  mov     rcx, [rbp+28h]; this
0x1800f272f  test    eax, eax
0x1800f2731  jnz     loc_1800F2829
0x1800f2737  mov     [rbp+arg_10], 0
0x1800f273f  xor     edx, edx
0x1800f2741  lea     rcx, [rbp+arg_10]
0x1800f2745  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800f274a  lea     r9, [rbp+arg_10]
0x1800f274e  xor     r8d, r8d
0x1800f2751  lea     rdx, aNodeuri; "NodeUri"
0x1800f2758  mov     rcx, [rbp+arg_0]
0x1800f275c  call    cs:__imp_?OmDmRegistryAllocAndGetString@@YAJPEAUHKEY__@@PEBGW4AllocFunction@@PEAPEAG@Z; OmDmRegistryAllocAndGetString(HKEY__ *,ushort const *,AllocFunction,ushort * *)
0x1800f2763  nop     dword ptr [rax+rax+00h]
0x1800f2768  mov     rcx, [rbp+28h]; this
0x1800f276c  test    eax, eax
0x1800f276e  js      loc_1800F2814
0x1800f2774  mov     rdx, [rbp+arg_10]
0x1800f2778  mov     rcx, r15
0x1800f277b  call    cs:__imp__o__wcsicmp
0x1800f2782  nop     dword ptr [rax+rax+00h]
0x1800f2787  test    eax, eax
0x1800f2789  jz      short loc_1800F27A7
0x1800f278b  lea     rcx, [rbp+arg_10]
0x1800f278f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f2794  nop
0x1800f2795  lea     rcx, [rbp+arg_0]
0x1800f2799  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f279e  add     rbx, 8
0x1800f27a2  jmp     loc_1800F26E7
0x1800f27a7  xor     edx, edx
0x1800f27a9  lea     rcx, [rbp+arg_0]
0x1800f27ad  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800f27b2  mov     rdx, rsi; lpSubKey
0x1800f27b5  mov     rcx, [r14+18h]; hKey
0x1800f27b9  call    cs:__imp_RegDeleteTreeW
0x1800f27c0  nop     dword ptr [rax+rax+00h]
0x1800f27c5  mov     rcx, [rbp+28h]; this
0x1800f27c9  test    eax, eax
0x1800f27cb  jz      short loc_1800F27E2
0x1800f27cd  mov     r9d, eax; char *
0x1800f27d0  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f27d7  mov     edx, 78h ; 'x'; void *
0x1800f27dc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800f27e2  lea     rcx, [rbp+arg_10]
0x1800f27e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f27eb  nop
0x1800f27ec  lea     rcx, [rbp+arg_0]
0x1800f27f0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f27f5  nop
0x1800f27f6  lea     rcx, [rbp+var_20]
0x1800f27fa  call    ??1?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x1800f27ff  mov     rbx, [rsp+50h+arg_8]
0x1800f2807  add     rsp, 50h
0x1800f280b  pop     r15
0x1800f280d  pop     r14
0x1800f280f  pop     rdi
0x1800f2810  pop     rsi
0x1800f2811  pop     rbp
0x1800f2812  retn
0x1800f2814  mov     r9d, eax; char *
0x1800f2817  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f281e  mov     edx, 73h ; 's'; void *
0x1800f2823  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f2829  mov     r9d, eax; char *
0x1800f282c  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f2833  mov     edx, 70h ; 'p'; void *
0x1800f2838  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800f283e  mov     rcx, [rbp+28h]; this
0x1800f2842  mov     r9d, 2; char *
0x1800f2848  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f284f  lea     edx, [r9+7Ch]; void *
0x1800f2853  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
