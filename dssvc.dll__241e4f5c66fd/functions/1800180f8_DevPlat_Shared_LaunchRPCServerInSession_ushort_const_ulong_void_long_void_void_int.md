# DevPlat::Shared::LaunchRPCServerInSession(ushort const *,ulong,void *,long (*)(void *,void *),int)

- ea: `0x1800180f8`
- end: `0x180018419`
- name: `?LaunchRPCServerInSession@Shared@DevPlat@@YAJPEBGKPEAXP6AJ11@ZH@Z`
- size: `801`
- prototype: `__int64 __fastcall(DevPlat::Shared *this, const unsigned __int16 *, __int64, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b700`

## callees

- `0x18000602c`
- `0x1800065e8`
- `0x18000c93c`
- `0x180018020`
- `0x18001807c`
- `0x1800180d8`
- `0x1800180f8`
- `0x1800184ec`
- `0x18001b30a`
- `0x18001b340`

## import_xrefs

- `RPCRT4!RpcEpRegisterW` at `0x1800183fe`
- `RPCRT4!RpcEpRegisterW` at `0x1800183fe`
- `RPCRT4!RpcServerInqBindings` at `0x1800182c8`
- `RPCRT4!RpcServerInqBindings` at `0x1800182c8`
- `RPCRT4!RpcBindingVectorFree` at `0x180018254`
- `RPCRT4!RpcBindingVectorFree` at `0x180018254`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800183e2`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800183e2`
- `RPCRT4!RpcServerUseProtseqW` at `0x180018220`
- `RPCRT4!RpcServerUseProtseqW` at `0x180018220`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800181dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001837b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800181dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001837b`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180018183`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180018320`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180018183`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180018320`

## string_xrefs

- `0x18001815f`: `DefaultRpcAccess`

## pseudocode

```c
__int64 __fastcall DevPlat::Shared::LaunchRPCServerInSession(
        DevPlat::Shared *this,
        const unsigned __int16 *a2,
        __int64 a3,
        void *a4)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  int LastError; // ebx
  void *v8; // r8
  BOOL v9; // ebx
  const char *v10; // r9
  RPC_STATUS v11; // eax
  bool v12; // cc
  int v14; // ebx
  __int64 v15; // rax
  BOOL v16; // ebx
  const char *v17; // r9
  bool v18; // cc
  ULONG SecurityDescriptorSize; // [rsp+40h] [rbp-C0h] BYREF
  void **v20; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  char v22; // [rsp+58h] [rbp-A8h]
  RPC_BINDING_VECTOR *BindingVector; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  void *v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  void *v27; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+98h] [rbp-68h]
  __int64 v30; // [rsp+9Ch] [rbp-64h]
  int v31; // [rsp+A4h] [rbp-5Ch]
  unsigned __int16 v32[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  BindingVector = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  memset_0(v32, 0, 0x208u);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  SecurityDescriptor = 0;
  v20 = &v27;
  v22 = 1;
  v28 = 0;
  v4 = QueryTransientObjectSecurityDescriptor(8, L"DefaultRpcAccess", &SecurityDescriptor);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v20);
  LastError = v4 | 0x10000000;
  if ( LastError < 0 )
  {
    if ( LastError != -805306316 )
      goto LABEL_12;
    SecurityDescriptorSize = 0;
    v20 = &v25;
    SecurityDescriptor = 0;
    v22 = 1;
    v9 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:(A;;0x111FFFFF;;;CO)(A;;0x111FFFFF;;;SY)(A;;0x111FFFFF;;;BA)(A;;GR;;;IU)(A;;GR;;;AU)(A;;GR;;;AC)(A;;GR;;;S-"
            "1-15-3-1024-2405443489-874036122-4286035555-1823921565-1746547431-2453885448-3625952902-991631256)",
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v20);
    if ( !v9 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x39,
                    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\rpcutils.cpp",
                    v10);
      if ( LastError < 0 )
        goto LABEL_12;
    }
    v8 = v25;
  }
  else
  {
    v8 = v27;
  }
  v11 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, v8);
  LastError = v11;
  if ( v11 && v11 != 1740 )
  {
    v12 = v11 <= 0;
    goto LABEL_10;
  }
  v11 = RpcServerInqBindings(&BindingVector);
  LastError = v11;
  v12 = v11 <= 0;
  if ( v11 )
  {
LABEL_10:
    if ( v12 )
      goto LABEL_12;
    goto LABEL_11;
  }
  LastError = StringCchPrintfW(v32, 0x104u, L"%s\\Interface", L"Dssvc");
  if ( LastError >= 0 )
  {
    SecurityDescriptor = 0;
    v20 = (void **)&v26;
    v22 = 1;
    v14 = QueryTransientObjectSecurityDescriptor(9, v32, &SecurityDescriptor);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v20);
    LastError = v14 | 0x10000000;
    if ( LastError < 0 )
    {
      if ( LastError != -805306316 )
        goto LABEL_12;
      SecurityDescriptorSize = 0;
      v20 = (void **)&v24;
      SecurityDescriptor = 0;
      v22 = 1;
      v16 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"D:(A;;0x111FFFFF;;;CO)(A;;0x111FFFFF;;;SY)(A;;0x111FFFFF;;;BA)(A;;GA;;;IU)(A;;GA;;;AU)(A;;GA;;;AC)",
              1u,
              &SecurityDescriptor,
              &SecurityDescriptorSize);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v20);
      if ( v16 )
      {
        LastError = 0;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x44,
                      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\rpcutils.cpp",
                      v17);
        if ( LastError < 0 )
          goto LABEL_12;
      }
      v15 = v24;
    }
    else
    {
      v15 = v26;
    }
    v11 = RpcServerRegisterIf3(qword_18001D8E0, 0, 0, 41, 1234, 0, 0, v15);
    v18 = v11 <= 0;
    if ( v11 || (v11 = RpcEpRegisterW(qword_18001D8E0, BindingVector, 0, 0), v18 = v11 <= 0, v11) )
    {
      if ( !v18 )
      {
LABEL_11:
        LastError = (unsigned __int16)v11 | 0x80070000;
        goto LABEL_12;
      }
      LastError = v11;
    }
  }
LABEL_12:
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  if ( LastError < 0 && (byte_18002B304 & 2) != 0 )
    McTemplateU0zd_EventWriteTransfer(v6, v5, L"DevPlat::Shared::LaunchRPCServerInSession", (unsigned int)LastError);
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&v24);
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&v25);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v27);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800180f8  mov     [rsp-8+arg_0], rbx
0x1800180fd  mov     [rsp-8+arg_8], rdi
0x180018102  push    rbp
0x180018103  lea     rbp, [rsp-1D0h]
0x18001810b  sub     rsp, 2D0h
0x180018112  mov     rax, cs:__security_cookie
0x180018119  xor     rax, rsp
0x18001811c  mov     [rbp+1D0h+var_10], rax
0x180018123  xor     edi, edi
0x180018125  lea     rcx, [rbp+1D0h+var_220]; void *
0x180018129  xor     edx, edx; Val
0x18001812b  mov     [rsp+2D0h+BindingVector], rdi
0x180018130  mov     r8d, 208h; Size
0x180018136  mov     [rbp+1D0h+var_250], rdi
0x18001813a  mov     [rsp+2D0h+var_258], rdi
0x18001813f  mov     [rsp+2D0h+var_260], rdi
0x180018144  mov     [rsp+2D0h+var_268], rdi
0x180018149  call    memset_0
0x18001814e  xor     eax, eax
0x180018150  mov     [rbp+1D0h+var_238], edi
0x180018153  mov     [rbp+1D0h+var_234], rax
0x180018157  lea     r8, [rsp+2D0h+SecurityDescriptor]
0x18001815c  mov     [rbp+1D0h+var_22C], eax
0x18001815f  lea     rdx, aDefaultrpcacce; "DefaultRpcAccess"
0x180018166  lea     rax, [rbp+1D0h+var_250]
0x18001816a  mov     [rsp+2D0h+SecurityDescriptor], rdi
0x18001816f  xorps   xmm0, xmm0
0x180018172  mov     [rsp+2D0h+var_288], rax
0x180018177  lea     ecx, [rdi+8]
0x18001817a  mov     [rsp+2D0h+var_278], 1
0x18001817f  movups  [rbp+1D0h+var_248], xmm0
0x180018183  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180018189  lea     rcx, [rsp+2D0h+var_288]
0x18001818e  mov     ebx, eax
0x180018190  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180018195  or      ebx, 10000000h
0x18001819b  js      short loc_1800181A3
0x18001819d  mov     r8, [rbp+1D0h+var_250]
0x1800181a1  jmp     short loc_180018214
0x1800181a3  cmp     ebx, 0D0000034h
0x1800181a9  jnz     loc_180018248
0x1800181af  lea     rax, [rsp+2D0h+var_260]
0x1800181b4  mov     [rsp+2D0h+SecurityDescriptorSize], edi
0x1800181b8  lea     r9, [rsp+2D0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800181bd  mov     [rsp+2D0h+var_288], rax
0x1800181c2  lea     r8, [rsp+2D0h+SecurityDescriptor]; SecurityDescriptor
0x1800181c7  mov     [rsp+2D0h+SecurityDescriptor], rdi
0x1800181cc  mov     edx, 1; StringSDRevision
0x1800181d1  mov     [rsp+2D0h+var_278], 1
0x1800181d6  lea     rcx, StringSecurityDescriptor; "D:(A;;0x111FFFFF;;;CO)(A;;0x111FFFFF;;;"...
0x1800181dd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800181e3  lea     rcx, [rsp+2D0h+var_288]
0x1800181e8  mov     ebx, eax
0x1800181ea  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800181ef  test    ebx, ebx
0x1800181f1  jnz     short loc_18001820F
0x1800181f3  mov     rcx, [rbp+1D8h]; this
0x1800181fa  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180018201  lea     edx, [rbx+39h]; void *
0x180018204  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018209  mov     ebx, eax
0x18001820b  test    eax, eax
0x18001820d  js      short loc_180018248
0x18001820f  mov     r8, [rsp+2D0h+var_260]; SecurityDescriptor
0x180018214  mov     edx, 0Ah; MaxCalls
0x180018219  lea     rcx, Protseq; "ncalrpc"
0x180018220  call    cs:__imp_RpcServerUseProtseqW
0x180018226  mov     ebx, eax
0x180018228  test    eax, eax
0x18001822a  jz      loc_1800182C3
0x180018230  cmp     eax, 6CCh
0x180018235  jz      loc_1800182C3
0x18001823b  test    eax, eax
0x18001823d  jle     short loc_180018248
0x18001823f  movzx   ebx, ax
0x180018242  or      ebx, 80070000h
0x180018248  cmp     [rsp+2D0h+BindingVector], rdi
0x18001824d  jz      short loc_18001825A
0x18001824f  lea     rcx, [rsp+2D0h+BindingVector]; BindingVector
0x180018254  call    cs:__imp_RpcBindingVectorFree
0x18001825a  test    ebx, ebx
0x18001825c  jns     short loc_180018276
0x18001825e  test    cs:byte_18002B304, 2
0x180018265  jz      short loc_180018276
0x180018267  mov     r9d, ebx
0x18001826a  lea     r8, aDevplatSharedL; "DevPlat::Shared::LaunchRPCServerInSessi"...
0x180018271  call    McTemplateU0zd_EventWriteTransfer
0x180018276  lea     rcx, [rsp+2D0h+var_268]
0x18001827b  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180018280  lea     rcx, [rsp+2D0h+var_260]
0x180018285  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x18001828a  lea     rcx, [rsp+2D0h+var_258]
0x18001828f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180018294  lea     rcx, [rbp+1D0h+var_250]
0x180018298  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001829d  mov     eax, ebx
0x18001829f  mov     rcx, [rbp+1D0h+var_10]
0x1800182a6  xor     rcx, rsp; StackCookie
0x1800182a9  call    __security_check_cookie
0x1800182ae  lea     r11, [rsp+2D0h+var_s0]
0x1800182b6  mov     rbx, [r11+10h]
0x1800182ba  mov     rdi, [r11+18h]
0x1800182be  mov     rsp, r11
0x1800182c1  pop     rbp
0x1800182c2  retn
0x1800182c3  lea     rcx, [rsp+2D0h+BindingVector]; BindingVector
0x1800182c8  call    cs:__imp_RpcServerInqBindings
0x1800182ce  mov     ebx, eax
0x1800182d0  test    eax, eax
0x1800182d2  jnz     loc_18001823D
0x1800182d8  lea     r9, aDssvc; "Dssvc"
0x1800182df  mov     edx, 104h; unsigned __int64
0x1800182e4  lea     r8, aSInterface; "%s\\Interface"
0x1800182eb  lea     rcx, [rbp+1D0h+var_220]; unsigned __int16 *
0x1800182ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800182f4  mov     ebx, eax
0x1800182f6  test    eax, eax
0x1800182f8  js      loc_180018248
0x1800182fe  lea     rax, [rsp+2D0h+var_258]
0x180018303  mov     [rsp+2D0h+SecurityDescriptor], rdi
0x180018308  lea     r8, [rsp+2D0h+SecurityDescriptor]
0x18001830d  mov     [rsp+2D0h+var_288], rax
0x180018312  lea     rdx, [rbp+1D0h+var_220]
0x180018316  mov     [rsp+2D0h+var_278], 1
0x18001831b  mov     ecx, 9
0x180018320  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180018326  lea     rcx, [rsp+2D0h+var_288]
0x18001832b  mov     ebx, eax
0x18001832d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180018332  or      ebx, 10000000h
0x180018338  js      short loc_180018341
0x18001833a  mov     rax, [rsp+2D0h+var_258]
0x18001833f  jmp     short loc_1800183BA
0x180018341  cmp     ebx, 0D0000034h
0x180018347  jnz     loc_180018248
0x18001834d  lea     rax, [rsp+2D0h+var_268]
0x180018352  mov     [rsp+2D0h+SecurityDescriptorSize], edi
0x180018356  lea     r9, [rsp+2D0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18001835b  mov     [rsp+2D0h+var_288], rax
0x180018360  lea     r8, [rsp+2D0h+SecurityDescriptor]; SecurityDescriptor
0x180018365  mov     [rsp+2D0h+SecurityDescriptor], rdi
0x18001836a  mov     edx, 1; StringSDRevision
0x18001836f  mov     [rsp+2D0h+var_278], 1
0x180018374  lea     rcx, aDA0x111fffffCo; "D:(A;;0x111FFFFF;;;CO)(A;;0x111FFFFF;;;"...
0x18001837b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180018381  lea     rcx, [rsp+2D0h+var_288]
0x180018386  mov     ebx, eax
0x180018388  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18001838d  test    ebx, ebx
0x18001838f  jnz     short loc_1800183B3
0x180018391  mov     rcx, [rbp+1D8h]; this
0x180018398  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18001839f  lea     edx, [rbx+44h]; void *
0x1800183a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800183a7  mov     ebx, eax
0x1800183a9  test    eax, eax
0x1800183ab  js      loc_180018248
0x1800183b1  jmp     short loc_1800183B5
0x1800183b3  mov     ebx, edi
0x1800183b5  mov     rax, [rsp+2D0h+var_268]
0x1800183ba  mov     [rsp+2D0h+var_298], rax
0x1800183bf  lea     rcx, qword_18001D8E0
0x1800183c6  mov     [rsp+2D0h+var_2A0], rdi
0x1800183cb  mov     r9d, 29h ; ')'
0x1800183d1  mov     [rsp+2D0h+var_2A8], edi
0x1800183d5  xor     r8d, r8d
0x1800183d8  xor     edx, edx
0x1800183da  mov     [rsp+2D0h+var_2B0], 4D2h
0x1800183e2  call    cs:__imp_RpcServerRegisterIf3
0x1800183e8  test    eax, eax
0x1800183ea  jnz     short loc_18001840C
0x1800183ec  mov     rdx, [rsp+2D0h+BindingVector]; BindingVector
0x1800183f1  lea     rcx, qword_18001D8E0; IfSpec
0x1800183f8  xor     r9d, r9d; Annotation
0x1800183fb  xor     r8d, r8d; UuidVector
0x1800183fe  call    cs:__imp_RpcEpRegisterW
0x180018404  test    eax, eax
0x180018406  jz      loc_180018248
0x18001840c  jg      loc_18001823F
0x180018412  mov     ebx, eax
0x180018414  jmp     loc_180018248
```
