# I_NgcCreateContainer(ushort const *,HWND__ *,ushort const *,ushort const *,ulong,uchar const *,ulong,_GUID *,uchar * *,ulong *,unsigned __int64 *)

- ea: `0x18003cd8c`
- end: `0x18003d134`
- name: `?I_NgcCreateContainer@@YAJPEBGPEAUHWND__@@00KPEBEKPEAU_GUID@@PEAPEAEPEAKPEA_K@Z`
- size: `936`
- prototype: `__int64 __usercall@<rax>(LPCWSTR StringSid@<rcx>, HWND@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, char, const unsigned __int8 *, unsigned int, struct _GUID *, unsigned __int8 **, unsigned int *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180035144`
- `0x180036538`

## callees

- `0x1800046e0`
- `0x18000edb0`
- `0x1800158e0`
- `0x180015ae0`
- `0x180016818`
- `0x1800171fc`
- `0x180017df0`
- `0x180018790`
- `0x180025010`
- `0x18002b0f0`
- `0x18002e02c`
- `0x18003cd8c`
- `0x18003d3f8`
- `0x18004120c`
- `0x18004242c`
- `0x180046ce0`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cfb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cf84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cf84`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003cfa6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003cfa6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall I_NgcCreateContainer(
        LPCWSTR StringSid,
        HWND a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        char a5,
        const unsigned __int8 *a6,
        unsigned int a7,
        struct _GUID *a8,
        unsigned __int8 **a9,
        unsigned int *a10,
        unsigned __int64 *a11)
{
  __int64 v12; // rdx
  __int64 v13; // r8
  DWORD v14; // r9d
  __int64 v15; // rax
  int v16; // eax
  int Container; // esi
  void *v18; // rdx
  volatile signed __int32 *v19; // rdi
  bool v20; // zf
  char v21; // bl
  DWORD LastError; // eax
  GUID v23; // xmm0
  const unsigned __int8 *v25; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+68h] [rbp-98h]
  unsigned int v27; // [rsp+6Ch] [rbp-94h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-90h] BYREF
  HWND v29; // [rsp+78h] [rbp-88h] BYREF
  wil::details *v30; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v31; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID v32; // [rsp+90h] [rbp-70h] BYREF
  NgcUtils::RpcClient *v33; // [rsp+A0h] [rbp-60h] BYREF
  volatile signed __int32 *v34; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v35; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v36; // [rsp+B8h] [rbp-48h]
  struct _GUID v37; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR StringSecurityDescriptor[16]; // [rsp+D0h] [rbp-30h] BYREF

  v35 = a4;
  v36 = a3;
  v29 = a2;
  v25 = a6;
  *(_QWORD *)&v32.Data1 = operator new(0x60u);
  std::wstring::wstring(StringSecurityDescriptor, L"D:(A;;GR;;;LS)");
  v15 = NgcUtils::RpcClient::RpcClient(
          *(__int64 *)&v32.Data1,
          v12,
          v13,
          v14,
          3,
          StringSecurityDescriptor,
          qword_180057D18,
          (__int64)&qword_18004ECC0);
  std::shared_ptr<NgcUtils::RpcClient>::shared_ptr<NgcUtils::RpcClient>(&v33, v15);
  v26 = 0;
  std::wstring::~wstring(StringSecurityDescriptor);
  v16 = NgcUtils::RpcClient::Bind(v33);
  Container = v16;
  if ( v16 < 0 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v25) = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_1800615ED,
        0,
        0,
        (__int64)&v25);
    }
LABEL_28:
    v19 = v34;
    if ( !v34 )
      return (unsigned int)Container;
    v20 = _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1;
    goto LABEL_30;
  }
  v37 = 0;
  v30 = 0;
  v27 = 0;
  v31 = 0;
  Container = I_c_NgcRpcCreateContainer(
                (unsigned int)&v33,
                (_DWORD)StringSid,
                (_DWORD)v29,
                (_DWORD)v36,
                (__int64)v35,
                a5 & 1,
                (__int64)v25,
                a7,
                (__int64)&v37,
                (__int64)&v30,
                (__int64)&v27,
                (__int64)&v31);
  if ( Container >= 0 )
  {
    if ( (a5 & 2) == 0 )
    {
      hMem = 0;
      if ( ConvertStringSidToSidW(StringSid, &hMem) )
      {
        v29 = (HWND)hMem;
        LODWORD(v25) = 0;
        *(_QWORD *)&v32.Data1 = &v29;
        *(_QWORD *)v32.Data4 = &v25;
        lambda_dcc46b57e3b17782259cf4b8e691dc4d_::operator()(&v32);
        v21 = (char)v25;
      }
      else
      {
        v21 = 0;
        LastError = GetLastError();
        if ( (unsigned int)dword_18006E000 > 3 )
        {
          LODWORD(v25) = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_18006E000,
            (unsigned __int8 *)byte_1800615BF,
            0,
            0,
            (__int64)&v25);
        }
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
      if ( (v21 & 2) != 0 )
      {
        v23 = CLSID_NgcUtils_FaceCredentialProvider;
      }
      else
      {
        v23 = CLSID_NgcUtils_NgcPinProvider;
        if ( (v21 & 8) != 0 )
          v23 = CLSID_NgcUtils_WinBioCredentialProvider;
      }
      v32 = v23;
      Container = NgcMgmtSetLastCredProv(&v32, StringSid);
      if ( Container < 0 )
      {
        if ( (unsigned int)dword_18006E000 > 3 )
        {
          LODWORD(v25) = Container;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_18006E000,
            (unsigned __int8 *)byte_180061591,
            0,
            0,
            (__int64)&v25);
        }
        Container = 0;
      }
    }
    if ( a8 )
      *a8 = v37;
    if ( a9 && a10 )
    {
      *a9 = (unsigned __int8 *)v30;
      *a10 = v27;
    }
    else
    {
      wil::details::FreeProcessHeap(v30, v18);
    }
    if ( a11 )
      *a11 = v31;
    goto LABEL_28;
  }
  v19 = v34;
  if ( !v34 )
    return (unsigned int)Container;
  v20 = _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1;
LABEL_30:
  if ( v20 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
    if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
  }
  return (unsigned int)Container;
}

```

## disassembly

```asm
0x18003cd8c  push    rbp
0x18003cd8e  push    rbx
0x18003cd8f  push    rsi
0x18003cd90  push    rdi
0x18003cd91  push    r12
0x18003cd93  push    r13
0x18003cd95  push    r14
0x18003cd97  push    r15
0x18003cd99  lea     rbp, [rsp-8]
0x18003cd9e  sub     rsp, 108h
0x18003cda5  mov     rax, cs:__security_cookie
0x18003cdac  xor     rax, rsp
0x18003cdaf  mov     [rbp+40h+var_50], rax
0x18003cdb3  mov     [rbp+40h+var_90], r9
0x18003cdb7  mov     [rbp+40h+var_88], r8
0x18003cdbb  mov     [rsp+140h+var_C8], rdx
0x18003cdc0  mov     rdi, rcx
0x18003cdc3  mov     rax, [rbp+40h+arg_28]
0x18003cdc7  mov     [rsp+140h+var_E0], rax
0x18003cdcc  mov     r15, [rbp+40h+arg_38]
0x18003cdd3  mov     r12, [rbp+40h+arg_40]
0x18003cdda  mov     r13, [rbp+40h+arg_48]
0x18003cde1  mov     r14, [rbp+40h+arg_50]
0x18003cde8  mov     [rsp+140h+var_D8], 0
0x18003cdf0  mov     ecx, 60h ; '`'; Size
0x18003cdf5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003cdfa  mov     rbx, rax
0x18003cdfd  mov     qword ptr [rbp+40h+var_B0.Data1], rax
0x18003ce01  lea     rdx, aDAGrLs_0; "D:(A;;GR;;;LS)"
0x18003ce08  lea     rcx, [rbp+40h+var_70]
0x18003ce0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003ce11  nop
0x18003ce12  mov     esi, 1
0x18003ce17  mov     [rsp+140h+var_D8], esi
0x18003ce1b  lea     rax, qword_18004ECC0
0x18003ce22  mov     [rsp+140h+var_108], rax; __int64
0x18003ce27  lea     rax, qword_180057D18
0x18003ce2e  mov     [rsp+140h+pSid], rax; pSid
0x18003ce33  lea     rax, [rbp+40h+var_70]
0x18003ce37  mov     [rsp+140h+StringSecurityDescriptor], rax; StringSecurityDescriptor
0x18003ce3c  mov     [rsp+140h+var_120], 3; int
0x18003ce44  mov     rcx, rbx; int
0x18003ce47  call    ??0RpcClient@NgcUtils@@QEAA@KKKKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_SID@@QEAX@Z; NgcUtils::RpcClient::RpcClient(ulong,ulong,ulong,ulong,std::wstring const &,_SID const *,void * const)
0x18003ce4c  nop
0x18003ce4d  mov     rdx, rax
0x18003ce50  lea     rcx, [rbp+40h+var_A0]
0x18003ce54  call    ??$?0VRpcClient@NgcUtils@@$0A@@?$shared_ptr@VRpcClient@NgcUtils@@@std@@QEAA@PEAVRpcClient@NgcUtils@@@Z; std::shared_ptr<NgcUtils::RpcClient>::shared_ptr<NgcUtils::RpcClient>(NgcUtils::RpcClient *)
0x18003ce59  nop
0x18003ce5a  mov     eax, esi
0x18003ce5c  and     eax, 0FFFFFFFEh
0x18003ce5f  mov     [rsp+140h+var_D8], eax
0x18003ce63  lea     rcx, [rbp+40h+var_70]
0x18003ce67  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ce6c  mov     rcx, [rbp+40h+var_A0]; this
0x18003ce70  call    ?Bind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Bind(void)
0x18003ce75  mov     esi, eax
0x18003ce77  test    eax, eax
0x18003ce79  jns     short loc_18003CEB6
0x18003ce7b  mov     ecx, cs:dword_18006E000
0x18003ce81  cmp     ecx, 2
0x18003ce84  jbe     loc_18003D0D3
0x18003ce8a  mov     dword ptr [rsp+140h+var_E0], eax
0x18003ce8e  lea     rax, [rsp+140h+var_E0]
0x18003ce93  mov     qword ptr [rsp+140h+var_120], rax
0x18003ce98  xor     r9d, r9d
0x18003ce9b  xor     r8d, r8d
0x18003ce9e  lea     rdx, byte_1800615ED
0x18003cea5  lea     rcx, dword_18006E000
0x18003ceac  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003ceb1  jmp     loc_18003D0D3
0x18003ceb6  xorps   xmm0, xmm0
0x18003ceb9  movups  [rbp+40h+var_80], xmm0
0x18003cebd  mov     [rbp+40h+var_C0], 0
0x18003cec5  mov     [rsp+140h+var_D4], 0
0x18003cecd  mov     [rbp+40h+var_B8], 0
0x18003ced5  mov     cl, [rbp+40h+arg_20]
0x18003ced8  and     cl, 1
0x18003cedb  lea     rax, [rbp+40h+var_B8]
0x18003cedf  mov     [rsp+140h+var_E8], rax
0x18003cee4  lea     rax, [rsp+140h+var_D4]
0x18003cee9  mov     [rsp+140h+var_F0], rax
0x18003ceee  lea     rax, [rbp+40h+var_C0]
0x18003cef2  mov     [rsp+140h+var_F8], rax
0x18003cef7  lea     rax, [rbp+40h+var_80]
0x18003cefb  mov     [rsp+140h+var_100], rax
0x18003cf00  mov     eax, [rbp+40h+arg_30]
0x18003cf06  mov     dword ptr [rsp+140h+var_108], eax
0x18003cf0a  mov     rax, [rsp+140h+var_E0]
0x18003cf0f  mov     [rsp+140h+pSid], rax
0x18003cf14  mov     byte ptr [rsp+140h+StringSecurityDescriptor], cl
0x18003cf18  mov     rax, [rbp+40h+var_90]
0x18003cf1c  mov     qword ptr [rsp+140h+var_120], rax
0x18003cf21  mov     r9, [rbp+40h+var_88]
0x18003cf25  mov     r8, [rsp+140h+var_C8]
0x18003cf2a  mov     rdx, rdi
0x18003cf2d  lea     rcx, [rbp+40h+var_A0]
0x18003cf31  call    ?I_c_NgcRpcCreateContainer@@YAJAEBV?$shared_ptr@VRpcClient@NgcUtils@@@std@@PEBG_K11_NPEBEKPEAU_GUID@@PEAPEAEPEAKPEA_K@Z; I_c_NgcRpcCreateContainer(std::shared_ptr<NgcUtils::RpcClient> const &,ushort const *,unsigned __int64,ushort const *,ushort const *,bool,uchar const *,ulong,_GUID *,uchar * *,ulong *,unsigned __int64 *)
0x18003cf36  mov     esi, eax
0x18003cf38  test    eax, eax
0x18003cf3a  jns     short loc_18003CF5A
0x18003cf3c  mov     rdi, [rbp+40h+var_98]
0x18003cf40  test    rdi, rdi
0x18003cf43  jz      loc_18003D112
0x18003cf49  or      ebx, 0FFFFFFFFh
0x18003cf4c  mov     ecx, ebx
0x18003cf4e  lock xadd [rdi+8], ecx
0x18003cf53  add     ecx, ebx
0x18003cf55  jmp     loc_18003D0E8
0x18003cf5a  test    [rbp+40h+arg_20], 2
0x18003cf5e  jnz     loc_18003D094
0x18003cf64  mov     [rsp+140h+hMem], 0
0x18003cf6d  mov     rbx, [rsp+140h+hMem]
0x18003cf72  test    rbx, rbx
0x18003cf75  jz      short loc_18003CF95
0x18003cf77  lea     rcx, [rsp+140h+var_C8]; this
0x18003cf7c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003cf81  mov     rcx, rbx; hMem
0x18003cf84  call    cs:__imp_LocalFree
0x18003cf8a  lea     rcx, [rsp+140h+var_C8]; this
0x18003cf8f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003cf94  nop
0x18003cf95  mov     [rsp+140h+hMem], 0
0x18003cf9e  lea     rdx, [rsp+140h+hMem]; Sid
0x18003cfa3  mov     rcx, rdi; StringSid
0x18003cfa6  call    cs:__imp_ConvertStringSidToSidW
0x18003cfac  test    eax, eax
0x18003cfae  jnz     short loc_18003CFEC
0x18003cfb0  xor     ebx, ebx
0x18003cfb2  call    cs:__imp_GetLastError
0x18003cfb8  mov     ecx, cs:dword_18006E000
0x18003cfbe  cmp     ecx, 3
0x18003cfc1  jbe     short loc_18003D01D
0x18003cfc3  mov     dword ptr [rsp+140h+var_E0], eax
0x18003cfc7  lea     rax, [rsp+140h+var_E0]
0x18003cfcc  mov     qword ptr [rsp+140h+var_120], rax
0x18003cfd1  xor     r9d, r9d
0x18003cfd4  xor     r8d, r8d
0x18003cfd7  lea     rdx, byte_1800615BF
0x18003cfde  lea     rcx, dword_18006E000
0x18003cfe5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003cfea  jmp     short loc_18003D01D
0x18003cfec  mov     rax, [rsp+140h+hMem]
0x18003cff1  mov     [rsp+140h+var_C8], rax
0x18003cff6  mov     dword ptr [rsp+140h+var_E0], 0
0x18003cffe  lea     rax, [rsp+140h+var_C8]
0x18003d003  mov     qword ptr [rbp+40h+var_B0.Data1], rax
0x18003d007  lea     rax, [rsp+140h+var_E0]
0x18003d00c  mov     qword ptr [rbp+40h+var_B0.Data4], rax
0x18003d010  lea     rcx, [rbp+40h+var_B0]
0x18003d014  call    _lambda_dcc46b57e3b17782259cf4b8e691dc4d___operator__
0x18003d019  mov     ebx, dword ptr [rsp+140h+var_E0]
0x18003d01d  lea     rcx, [rsp+140h+hMem]; void *
0x18003d022  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003d027  nop
0x18003d028  test    bl, 2
0x18003d02b  jz      short loc_18003D036
0x18003d02d  movups  xmm0, xmmword ptr cs:CLSID_NgcUtils_FaceCredentialProvider.Data1
0x18003d034  jmp     short loc_18003D049
0x18003d036  movups  xmm0, xmmword ptr cs:CLSID_NgcUtils_NgcPinProvider.Data1
0x18003d03d  test    bl, 8
0x18003d040  jz      short loc_18003D049
0x18003d042  movups  xmm0, xmmword ptr cs:CLSID_NgcUtils_WinBioCredentialProvider.Data1
0x18003d049  movdqa  xmmword ptr [rbp+40h+var_B0.Data1], xmm0
0x18003d04e  mov     rdx, rdi; unsigned __int16 *
0x18003d051  lea     rcx, [rbp+40h+var_B0]; struct _GUID
0x18003d055  call    ?NgcMgmtSetLastCredProv@@YAJU_GUID@@PEBG@Z; NgcMgmtSetLastCredProv(_GUID,ushort const *)
0x18003d05a  mov     esi, eax
0x18003d05c  test    eax, eax
0x18003d05e  jns     short loc_18003D094
0x18003d060  mov     eax, cs:dword_18006E000
0x18003d066  cmp     eax, 3
0x18003d069  jbe     short loc_18003D092
0x18003d06b  mov     dword ptr [rsp+140h+var_E0], esi
0x18003d06f  lea     rax, [rsp+140h+var_E0]
0x18003d074  mov     qword ptr [rsp+140h+var_120], rax
0x18003d079  xor     r9d, r9d
0x18003d07c  xor     r8d, r8d
0x18003d07f  lea     rdx, byte_180061591
0x18003d086  lea     rcx, dword_18006E000
0x18003d08d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003d092  xor     esi, esi
0x18003d094  test    r15, r15
0x18003d097  jz      short loc_18003D0A2
0x18003d099  movups  xmm0, [rbp+40h+var_80]
0x18003d09d  movdqu  xmmword ptr [r15], xmm0
0x18003d0a2  test    r12, r12
0x18003d0a5  jz      short loc_18003D0BE
0x18003d0a7  test    r13, r13
0x18003d0aa  jz      short loc_18003D0BE
0x18003d0ac  mov     rax, [rbp+40h+var_C0]
0x18003d0b0  mov     [r12], rax
0x18003d0b4  mov     eax, [rsp+140h+var_D4]
0x18003d0b8  mov     [r13+0], eax
0x18003d0bc  jmp     short loc_18003D0C7
0x18003d0be  mov     rcx, [rbp+40h+var_C0]; this
0x18003d0c2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18003d0c7  test    r14, r14
0x18003d0ca  jz      short loc_18003D0D3
0x18003d0cc  mov     rax, [rbp+40h+var_B8]
0x18003d0d0  mov     [r14], rax
0x18003d0d3  mov     rdi, [rbp+40h+var_98]
0x18003d0d7  test    rdi, rdi
0x18003d0da  jz      short loc_18003D112
0x18003d0dc  or      ebx, 0FFFFFFFFh
0x18003d0df  mov     eax, ebx
0x18003d0e1  lock xadd [rdi+8], eax
0x18003d0e6  add     eax, ebx
0x18003d0e8  jnz     short loc_18003D112
0x18003d0ea  mov     rax, [rdi]
0x18003d0ed  mov     rcx, rdi
0x18003d0f0  mov     rax, [rax]
0x18003d0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0f8  mov     eax, ebx
0x18003d0fa  lock xadd [rdi+0Ch], eax
0x18003d0ff  add     eax, ebx
0x18003d101  jnz     short loc_18003D112
0x18003d103  mov     rax, [rdi]
0x18003d106  mov     rcx, rdi
0x18003d109  mov     rax, [rax+8]
0x18003d10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d112  mov     eax, esi
0x18003d114  mov     rcx, [rbp+40h+var_50]
0x18003d118  xor     rcx, rsp; StackCookie
0x18003d11b  call    __security_check_cookie
0x18003d120  add     rsp, 108h
0x18003d127  pop     r15
0x18003d129  pop     r14
0x18003d12b  pop     r13
0x18003d12d  pop     r12
0x18003d12f  pop     rdi
0x18003d130  pop     rsi
0x18003d131  pop     rbx
0x18003d132  pop     rbp
0x18003d133  retn
```
