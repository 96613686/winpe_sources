# DoesPDCDriverExist

- ea: `0x180060250`
- end: `0x180060335`
- name: `DoesPDCDriverExist`
- size: `229`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000d09c`
- `0x180032558`

## callees

- `0x180029cf4`
- `0x18004c500`
- `0x180060250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800602dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800602dd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800602cd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800602cd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180060277`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180060277`

## pseudocode

```c
char DoesPDCDriverExist()
{
  SC_HANDLE v1; // rax
  DWORD v2; // eax
  __int64 v3; // r8
  __int64 v4; // r9
  DWORD LastError; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  char v8; // bl
  DWORD v9; // [rsp+40h] [rbp+8h] BYREF
  SC_HANDLE v10; // [rsp+48h] [rbp+10h] BYREF
  SC_HANDLE v11; // [rsp+50h] [rbp+18h] BYREF

  if ( byte_18009DABA )
    return 1;
  v1 = OpenSCManagerW(0, 0, 4u);
  v10 = v1;
  if ( v1 )
  {
    v11 = OpenServiceW(v1, L"PDC", 4u);
    if ( v11 )
    {
      v8 = 1;
      byte_18009DABA = 1;
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        v9 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)dword_18009A048,
          (unsigned __int8 *)&unk_180088330,
          v6,
          v7,
          (__int64)&v9);
      }
      v8 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v11);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
    return v8;
  }
  else
  {
    v2 = GetLastError();
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v9 = v2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)dword_18009A048,
        (unsigned __int8 *)&dword_180088364,
        v3,
        v4,
        (__int64)&v9);
    }
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v10);
    return 0;
  }
}

```

## disassembly

```asm
0x180060250  push    rbx
0x180060252  sub     rsp, 30h
0x180060256  mov     al, cs:byte_18009DABA
0x18006025c  nop
0x18006025d  test    al, al
0x18006025f  jz      short loc_18006026B
0x180060261  mov     eax, 1
0x180060266  jmp     loc_18006032F
0x18006026b  mov     ebx, 4
0x180060270  xor     edx, edx; lpDatabaseName
0x180060272  mov     r8d, ebx; dwDesiredAccess
0x180060275  xor     ecx, ecx; lpMachineName
0x180060277  call    cs:__imp_OpenSCManagerW
0x18006027d  mov     [rsp+38h+arg_8], rax
0x180060282  test    rax, rax
0x180060285  jnz     short loc_1800602C0
0x180060287  call    cs:__imp_GetLastError
0x18006028d  mov     ecx, cs:dword_18009A048
0x180060293  cmp     ecx, 5
0x180060296  jbe     short loc_1800602B2
0x180060298  mov     [rsp+38h+arg_0], eax
0x18006029c  lea     rdx, dword_180088364
0x1800602a3  lea     rax, [rsp+38h+arg_0]
0x1800602a8  mov     [rsp+38h+var_18], rax
0x1800602ad  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800602b2  lea     rcx, [rsp+38h+arg_8]
0x1800602b7  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800602bc  xor     al, al
0x1800602be  jmp     short loc_18006032F
0x1800602c0  mov     r8d, ebx; dwDesiredAccess
0x1800602c3  lea     rdx, aPdc; "PDC"
0x1800602ca  mov     rcx, rax; hSCManager
0x1800602cd  call    cs:__imp_OpenServiceW
0x1800602d3  mov     [rsp+38h+arg_10], rax
0x1800602d8  test    rax, rax
0x1800602db  jnz     short loc_18006030C
0x1800602dd  call    cs:__imp_GetLastError
0x1800602e3  mov     ecx, cs:dword_18009A048
0x1800602e9  cmp     ecx, 5
0x1800602ec  jbe     short loc_180060308
0x1800602ee  mov     [rsp+38h+arg_0], eax
0x1800602f2  lea     rdx, unk_180088330
0x1800602f9  lea     rax, [rsp+38h+arg_0]
0x1800602fe  mov     [rsp+38h+var_18], rax
0x180060303  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180060308  xor     bl, bl
0x18006030a  jmp     short loc_180060319
0x18006030c  mov     ebx, 1
0x180060311  mov     eax, ebx
0x180060313  xchg    al, cs:byte_18009DABA
0x180060319  lea     rcx, [rsp+38h+arg_10]
0x18006031e  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180060323  lea     rcx, [rsp+38h+arg_8]
0x180060328  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18006032d  mov     al, bl
0x18006032f  add     rsp, 30h
0x180060333  pop     rbx
0x180060334  retn
```
