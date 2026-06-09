# NgcUtils::CoMemResourceFormatStringAllocCopy(HINSTANCE__ *,uint,ushort * *,...)

- ea: `0x18001b934`
- end: `0x18001ba86`
- name: `?CoMemResourceFormatStringAllocCopy@NgcUtils@@YAJPEAUHINSTANCE__@@IPEAPEAGZZ`
- size: `338`
- prototype: `__int64(NgcUtils *this, HINSTANCE, _QWORD *, unsigned __int16 **, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000f0f4`

## callees

- `0x180002e70`
- `0x180008c54`
- `0x180010310`
- `0x180014bcc`
- `0x18001b850`
- `0x18001b934`
- `0x18001ba8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b9c4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b9c4`

## pseudocode

```c
__int64 NgcUtils::CoMemResourceFormatStringAllocCopy(
        NgcUtils *this,
        HINSTANCE a2,
        _QWORD *a3,
        unsigned __int16 **a4,
        ...)
{
  signed int v5; // ebx
  DWORD v6; // eax
  const char *v7; // r9
  DWORD LastError; // eax
  void *v9; // rcx
  void *v10; // [rsp+40h] [rbp-28h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-20h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-18h] BYREF
  LPCVOID lpSource[2]; // [rsp+58h] [rbp-10h] BYREF
  unsigned __int16 **v15; // [rsp+98h] [rbp+30h] BYREF

  v15 = a4;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  lpSource[0] = 0;
  v5 = NgcUtils::CoMemResourceStringAllocCopy(this, a2, (unsigned int)lpSource, a4);
  if ( v5 >= 0 )
  {
    *(_QWORD *)Buffer = 0;
    va_copy(Arguments, (va_list)&v15);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      Buffer,
      0);
    v6 = FormatMessageW(0x500u, lpSource[0], 0, 0, Buffer, 0, &Arguments);
    Arguments = 0;
    if ( !v6 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( (unsigned int)dword_180031038 > 2 )
      {
        LODWORD(v10) = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180031038,
          (__int64)byte_180029B43);
      }
      if ( v5 > 0 )
        v5 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_12;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v10,
      *(char **)Buffer,
      0xFFFFFFFFFFFFFFFFuLL,
      v7);
    v9 = v10;
    if ( v10 )
    {
      v10 = 0;
      *a3 = v9;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)Buffer);
      goto LABEL_13;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)Buffer);
    v5 = -2147024882;
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)lpSource);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001b934  mov     [rsp-10h+arg_10], r8
0x18001b939  mov     [rsp-10h+arg_18], r9
0x18001b93e  push    rbp
0x18001b93f  push    rbx
0x18001b940  mov     rbp, rsp
0x18001b943  sub     rsp, 68h
0x18001b947  test    r8, r8
0x18001b94a  jnz     short loc_18001B956
0x18001b94c  mov     eax, 80004003h
0x18001b951  jmp     loc_18001BA7F
0x18001b956  mov     qword ptr [r8], 0
0x18001b95d  mov     [rbp+lpSource], 0
0x18001b965  lea     r8, [rbp+lpSource]; unsigned int
0x18001b969  call    ?CoMemResourceStringAllocCopy@NgcUtils@@YAJPEAUHINSTANCE__@@IPEAPEAG@Z; NgcUtils::CoMemResourceStringAllocCopy(HINSTANCE__ *,uint,ushort * *)
0x18001b96e  mov     ebx, eax
0x18001b970  test    eax, eax
0x18001b972  js      loc_18001BA74
0x18001b978  mov     qword ptr [rbp+Buffer], 0
0x18001b980  mov     [rbp+var_18], 0
0x18001b988  lea     rax, [rbp+arg_18]
0x18001b98c  mov     [rbp+var_18], rax
0x18001b990  xor     edx, edx
0x18001b992  lea     rcx, [rbp+Buffer]
0x18001b996  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001b99b  lea     rax, [rbp+var_18]
0x18001b99f  mov     [rsp+68h+Arguments], rax; Arguments
0x18001b9a4  mov     [rsp+68h+nSize], 0; nSize
0x18001b9ac  lea     rax, [rbp+Buffer]
0x18001b9b0  mov     [rsp+68h+lpBuffer], rax; lpBuffer
0x18001b9b5  xor     r9d, r9d; dwLanguageId
0x18001b9b8  xor     r8d, r8d; dwMessageId
0x18001b9bb  mov     rdx, [rbp+lpSource]; lpSource
0x18001b9bf  mov     ecx, 500h; dwFlags
0x18001b9c4  call    cs:__imp_FormatMessageW
0x18001b9ca  mov     [rbp+var_18], 0
0x18001b9d2  test    eax, eax
0x18001b9d4  jnz     short loc_18001BA1D
0x18001b9d6  call    cs:__imp_GetLastError
0x18001b9dc  mov     ebx, eax
0x18001b9de  mov     ecx, cs:dword_180031038
0x18001b9e4  cmp     ecx, 2
0x18001b9e7  jbe     short loc_18001BA0E
0x18001b9e9  mov     dword ptr [rbp+var_28], eax
0x18001b9ec  lea     rax, [rbp+var_28]
0x18001b9f0  mov     [rsp+68h+lpBuffer], rax
0x18001b9f5  xor     r9d, r9d
0x18001b9f8  xor     r8d, r8d
0x18001b9fb  lea     rdx, byte_180029B43
0x18001ba02  lea     rcx, dword_180031038
0x18001ba09  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001ba0e  test    ebx, ebx
0x18001ba10  jle     short loc_18001BA6A
0x18001ba12  movzx   ebx, bx
0x18001ba15  or      ebx, 80070000h
0x18001ba1b  jmp     short loc_18001BA6A
0x18001ba1d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001ba21  mov     rdx, qword ptr [rbp+Buffer]
0x18001ba25  lea     rcx, [rbp+var_28]
0x18001ba29  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001ba2e  mov     rcx, [rbp+var_28]
0x18001ba32  test    rcx, rcx
0x18001ba35  jnz     short loc_18001BA51
0x18001ba37  lea     rcx, [rbp+var_28]
0x18001ba3b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ba40  nop
0x18001ba41  lea     rcx, [rbp+Buffer]
0x18001ba45  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ba4a  mov     ebx, 8007000Eh
0x18001ba4f  jmp     short loc_18001BA74
0x18001ba51  mov     [rbp+var_28], 0
0x18001ba59  mov     rax, [rbp+arg_10]
0x18001ba5d  mov     [rax], rcx
0x18001ba60  lea     rcx, [rbp+var_28]
0x18001ba64  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ba69  nop
0x18001ba6a  lea     rcx, [rbp+Buffer]
0x18001ba6e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ba73  nop
0x18001ba74  lea     rcx, [rbp+lpSource]
0x18001ba78  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001ba7d  mov     eax, ebx
0x18001ba7f  add     rsp, 68h
0x18001ba83  pop     rbx
0x18001ba84  pop     rbp
0x18001ba85  retn
```
