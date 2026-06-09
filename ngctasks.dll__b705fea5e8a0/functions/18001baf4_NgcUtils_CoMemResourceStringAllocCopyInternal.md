# NgcUtils::CoMemResourceStringAllocCopyInternal

- ea: `0x18001baf4`
- end: `0x18001bbab`
- name: `NgcUtils::CoMemResourceStringAllocCopyInternal`
- size: `183`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ba8c`

## callees

- `0x180002e70`
- `0x180008c54`
- `0x18001b850`
- `0x18001baf4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001bb15`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001bb15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bb1f`

## pseudocode

```c
__int64 __fastcall NgcUtils::CoMemResourceStringAllocCopyInternal(HINSTANCE a1, UINT a2, _QWORD *a3)
{
  int StringW; // eax
  const char *v5; // r9
  signed int LastError; // ebx
  void *v8; // [rsp+50h] [rbp+18h] BYREF
  char *Buffer; // [rsp+58h] [rbp+20h] BYREF

  *a3 = 0;
  Buffer = 0;
  StringW = LoadStringW(a1, a2, (LPWSTR)&Buffer, 0);
  if ( StringW )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v8,
      Buffer,
      StringW,
      v5);
    if ( v8 )
    {
      *a3 = v8;
      LastError = 0;
      v8 = 0;
    }
    else
    {
      LastError = -2147024882;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180031038 > 2 )
    {
      LODWORD(v8) = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180031038,
        (__int64)&byte_180029B6F);
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001baf4  push    rbx
0x18001baf6  sub     rsp, 30h
0x18001bafa  mov     rbx, r8
0x18001bafd  mov     qword ptr [r8], 0
0x18001bb04  lea     r8, [rsp+38h+Buffer]; lpBuffer
0x18001bb09  mov     [rsp+38h+Buffer], 0
0x18001bb12  xor     r9d, r9d; cchBufferMax
0x18001bb15  call    cs:__imp_LoadStringW
0x18001bb1b  test    eax, eax
0x18001bb1d  jnz     short loc_18001BB68
0x18001bb1f  call    cs:__imp_GetLastError
0x18001bb25  mov     ebx, eax
0x18001bb27  mov     eax, cs:dword_180031038
0x18001bb2d  cmp     eax, 2
0x18001bb30  jbe     short loc_18001BB59
0x18001bb32  lea     rax, [rsp+38h+arg_10]
0x18001bb37  mov     dword ptr [rsp+38h+arg_10], ebx
0x18001bb3b  xor     r9d, r9d
0x18001bb3e  mov     [rsp+38h+var_18], rax
0x18001bb43  xor     r8d, r8d
0x18001bb46  lea     rdx, byte_180029B6F
0x18001bb4d  lea     rcx, dword_180031038
0x18001bb54  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001bb59  test    ebx, ebx
0x18001bb5b  jle     short loc_18001BBA3
0x18001bb5d  movzx   ebx, bx
0x18001bb60  or      ebx, 80070000h
0x18001bb66  jmp     short loc_18001BBA3
0x18001bb68  mov     rdx, [rsp+38h+Buffer]
0x18001bb6d  lea     rcx, [rsp+38h+arg_10]
0x18001bb72  movsxd  r8, eax
0x18001bb75  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001bb7a  mov     rax, [rsp+38h+arg_10]
0x18001bb7f  test    rax, rax
0x18001bb82  jnz     short loc_18001BB8B
0x18001bb84  mov     ebx, 8007000Eh
0x18001bb89  jmp     short loc_18001BB99
0x18001bb8b  mov     [rbx], rax
0x18001bb8e  xor     ebx, ebx
0x18001bb90  mov     [rsp+38h+arg_10], 0
0x18001bb99  lea     rcx, [rsp+38h+arg_10]
0x18001bb9e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001bba3  mov     eax, ebx
0x18001bba5  add     rsp, 30h
0x18001bba9  pop     rbx
0x18001bbaa  retn
```
