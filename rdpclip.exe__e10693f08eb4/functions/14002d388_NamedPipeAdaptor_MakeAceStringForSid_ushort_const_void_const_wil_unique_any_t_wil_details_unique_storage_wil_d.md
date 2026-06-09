# NamedPipeAdaptor::MakeAceStringForSid(ushort * const,void * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x14002d388`
- end: `0x14002d433`
- name: `?MakeAceStringForSid@NamedPipeAdaptor@@AEAAJQEAGQEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `171`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002d05c`

## callees

- `0x140008168`
- `0x140008188`
- `0x14002bc24`
- `0x14002c054`
- `0x14002d388`
- `0x14002e6c8`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002d3c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002d3c0`

## string_xrefs

- `0x14002d3cf`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`
- `0x14002d3ff`: `clientcore\termsrv\rdpplatform\common\namedpipe\namedpipeadaptor.cpp`

## pseudocode

```c
__int64 NamedPipeAdaptor::MakeAceStringForSid(_QWORD a1, __int64 a2, void *a3, __int64 a4, ...)
{
  const char *v7; // r9
  unsigned int LastError; // ebx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF

  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  if ( ConvertSidToStringSidW(a3, &StringSid) )
  {
    v9 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           a4,
           a2,
           StringSid);
    LastError = v9;
    if ( v9 >= 0 )
      LastError = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x245,
        (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
        (const char *)(unsigned int)v9,
        v11);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x243,
                  (unsigned int)"clientcore\\termsrv\\rdpplatform\\common\\namedpipe\\namedpipeadaptor.cpp",
                  v7);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  return LastError;
}

```

## disassembly

```asm
0x14002d388  mov     rax, rsp
0x14002d38b  mov     [rax+10h], rbx
0x14002d38f  mov     [rax+18h], rsi
0x14002d393  mov     [rax+8], rcx
0x14002d397  push    rdi; int
0x14002d398  sub     rsp, 20h
0x14002d39c  mov     rsi, rdx
0x14002d39f  mov     qword ptr [rax+8], 0
0x14002d3a7  xor     edx, edx
0x14002d3a9  lea     rcx, [rax+8]
0x14002d3ad  mov     rdi, r9
0x14002d3b0  mov     rbx, r8
0x14002d3b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x14002d3b8  lea     rdx, [rsp+28h+StringSid]; StringSid
0x14002d3bd  mov     rcx, rbx; Sid
0x14002d3c0  call    cs:__imp_ConvertSidToStringSidW
0x14002d3c6  test    eax, eax
0x14002d3c8  jnz     short loc_14002D3E4
0x14002d3ca  mov     rcx, [rsp+28h]; this
0x14002d3cf  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d3d6  mov     edx, 243h; void *
0x14002d3db  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002d3e0  mov     ebx, eax
0x14002d3e2  jmp     short loc_14002D417
0x14002d3e4  mov     r8, [rsp+28h+StringSid]
0x14002d3e9  mov     rdx, rsi
0x14002d3ec  mov     rcx, rdi
0x14002d3ef  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x14002d3f4  mov     ebx, eax
0x14002d3f6  test    eax, eax
0x14002d3f8  jns     short loc_14002D415
0x14002d3fa  mov     rcx, [rsp+28h]; this
0x14002d3ff  lea     r8, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\commo"...
0x14002d406  mov     r9d, eax; char *
0x14002d409  mov     edx, 245h; void *
0x14002d40e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002d413  jmp     short loc_14002D417
0x14002d415  xor     ebx, ebx
0x14002d417  lea     rcx, [rsp+28h+StringSid]
0x14002d41c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14002d421  mov     rsi, [rsp+28h+arg_10]
0x14002d426  mov     eax, ebx
0x14002d428  mov     rbx, [rsp+28h+arg_8]
0x14002d42d  add     rsp, 20h
0x14002d431  pop     rdi
0x14002d432  retn
```
