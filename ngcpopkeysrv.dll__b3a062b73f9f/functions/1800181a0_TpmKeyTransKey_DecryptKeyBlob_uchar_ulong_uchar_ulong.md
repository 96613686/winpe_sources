# TpmKeyTransKey::DecryptKeyBlob(uchar *,ulong,uchar * *,ulong *)

- ea: `0x1800181a0`
- end: `0x180018517`
- name: `?DecryptKeyBlob@TpmKeyTransKey@@MEAAJPEAEKPEAPEAEPEAK@Z`
- size: `887`
- prototype: `__int64 __fastcall(TpmKeyTransKey *__hidden this, unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800012e8`
- `0x18000132c`
- `0x180004de0`
- `0x180006415`
- `0x18000b0fc`
- `0x18000da94`
- `0x18000dad8`
- `0x18000db5c`
- `0x18001070c`
- `0x180010730`
- `0x180010784`
- `0x180013270`
- `0x1800136d4`
- `0x180013e3c`
- `0x1800142e0`
- `0x180014f80`
- `0x180017f0c`
- `0x1800181a0`
- `0x180018560`
- `0x1800202c4`

## string_xrefs

- `0x180018287`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\tpmkeytranskey.cpp`
- `0x18001836c`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\tpmkeytranskey.cpp`
- `0x180018403`: `onecore\ds\security\ngc\ngcpopkey\keytranskey\tpmkeytranskey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TpmKeyTransKey::DecryptKeyBlob(
        TpmKeyTransKey *this,
        unsigned __int8 *a2,
        int a3,
        size_t *a4,
        unsigned int *a5)
{
  _DWORD *v9; // r9
  struct TpmKeysManager *v10; // rbx
  __int64 v11; // rax
  int TpmHmacKeyHandle; // eax
  unsigned int v13; // ebx
  int v14; // edx
  struct TpmKeysManager *v15; // rbx
  __int64 v16; // rax
  int v17; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  unsigned __int16 **v21; // r9
  int NCryptStringProperty; // eax
  __int64 v23; // r9
  __int64 v24; // rdx
  void *v25; // rbx
  __int64 v26; // rax
  size_t v27; // rdi
  unsigned int v28; // eax
  size_t v29; // r15
  unsigned int v30; // r14d
  size_t v31; // rsi
  int v33; // [rsp+20h] [rbp-81h]
  int v34; // [rsp+20h] [rbp-81h]
  int v35; // [rsp+20h] [rbp-81h]
  unsigned int *v36; // [rsp+28h] [rbp-79h]
  unsigned int *v37; // [rsp+28h] [rbp-79h]
  void *Src; // [rsp+30h] [rbp-71h] BYREF
  void *v39; // [rsp+38h] [rbp-69h] BYREF
  size_t Size; // [rsp+40h] [rbp-61h] BYREF
  NCRYPT_KEY_HANDLE hKey; // [rsp+48h] [rbp-59h] BYREF
  void **v42; // [rsp+50h] [rbp-51h] BYREF
  unsigned int v43[2]; // [rsp+58h] [rbp-49h] BYREF
  char v44; // [rsp+60h] [rbp-41h]
  int *v45; // [rsp+70h] [rbp-31h] BYREF
  __int16 v46; // [rsp+78h] [rbp-29h]
  int v47; // [rsp+80h] [rbp-21h] BYREF
  char v48; // [rsp+84h] [rbp-1Dh]
  _BYTE v49[16]; // [rsp+88h] [rbp-19h] BYREF
  _DWORD v50[4]; // [rsp+98h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v47 = 0;
  v48 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v47);
  if ( (unsigned int)dword_180037000 > 5 )
  {
    if ( v48 && (v50[0] || v50[1] || v50[2] || v50[3]) )
      v9 = v50;
    else
      v9 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180037000,
      byte_18002EBF1,
      v49,
      v9);
  }
  v45 = &v47;
  v46 = 256;
  hKey = 0;
  v10 = TpmKeysManager::Instance();
  v11 = std::wstring::wstring(&v42, *((_QWORD *)this + 4));
  LOBYTE(v33) = 0;
  TpmHmacKeyHandle = TpmKeysManager::GetTpmHmacKeyHandle((__int64)v10, v11, (__int64)a2, a3, v33, (__int64)&hKey);
  v13 = TpmHmacKeyHandle;
  if ( TpmHmacKeyHandle >= 0 )
  {
    LODWORD(Size) = 0;
    v39 = 0;
    v42 = &v39;
    *(_QWORD *)v43 = 0;
    v44 = 1;
    v13 = NgcUtils::ExportNCryptKey(hKey, L"OpaqueTransport", 0x800u, (unsigned int)v43, (unsigned __int8 **)&Size, v36);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v42);
    if ( v13 == -2144795614 || NgcUtils::ShouldReloadTpmHandle((NgcUtils *)v13, v14) )
    {
      if ( (unsigned int)dword_180037000 > 4 )
      {
        LODWORD(Src) = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180037000,
          (unsigned int)byte_18002EBB1,
          0,
          0,
          (__int64)&Src);
      }
      v15 = TpmKeysManager::Instance();
      v16 = std::wstring::wstring(&v42, *((_QWORD *)this + 4));
      LOBYTE(v35) = 1;
      v17 = TpmKeysManager::GetTpmHmacKeyHandle((__int64)v15, v16, (__int64)a2, a3, v35, (__int64)&hKey);
      v13 = v17;
      if ( v17 < 0 )
      {
        v18 = (unsigned int)v17;
        v19 = 152;
        goto LABEL_18;
      }
      v42 = &v39;
      *(_QWORD *)v43 = 0;
      v44 = 1;
      v13 = NgcUtils::ExportNCryptKey(
              hKey,
              L"OpaqueTransport",
              0x800u,
              (unsigned int)v43,
              (unsigned __int8 **)&Size,
              v37);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v42);
    }
    if ( (v13 & 0x80000000) == 0 )
    {
      Src = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &Src,
        0);
      NCryptStringProperty = NgcUtils::GetNCryptStringProperty(
                               *((NgcUtils **)this + 1),
                               v20,
                               (const unsigned __int16 *)&Src,
                               v21);
      v13 = NCryptStringProperty;
      if ( NCryptStringProperty >= 0 )
      {
        v25 = Src;
        v26 = -1;
        do
          ++v26;
        while ( *((_WORD *)Src + v26) );
        v27 = (unsigned int)(2 * v26 + 2);
        v28 = 2 * v26 + 14;
        if ( v28 >= 0xC )
        {
          v29 = (unsigned int)Size;
          v30 = v28 + Size;
          if ( v28 + (unsigned int)Size >= v28 )
          {
            wil::make_unique_hlocal_nothrow<unsigned char [0]>(&Size, v30);
            v31 = Size;
            if ( Size )
            {
              *(_DWORD *)Size = 1;
              *(_DWORD *)(v31 + 8) = v29;
              *(_DWORD *)(v31 + 4) = v27;
              memcpy_0((void *)(v31 + 12), v25, v27);
              memcpy_0((void *)(v27 + v31 + 12), v39, v29);
              *a4 = v31;
              *a5 = v30;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Src);
              wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
                &v39,
                0);
              v13 = 0;
              goto LABEL_35;
            }
            v13 = -2147024882;
            v23 = 2147942414LL;
            v24 = 175;
          }
          else
          {
            v13 = -2146893819;
            v23 = 2148073477LL;
            v24 = 172;
          }
        }
        else
        {
          v13 = -2146893819;
          v23 = 2148073477LL;
          v24 = 171;
        }
      }
      else
      {
        v23 = (unsigned int)NCryptStringProperty;
        v24 = 167;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\tpmkeytranskey.cpp",
        (const char *)v23,
        v35);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Src);
      goto LABEL_19;
    }
    v18 = v13;
    v19 = 161;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\tpmkeytranskey.cpp",
      (const char *)v18,
      v35);
LABEL_19:
    wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(&v39, 0);
    goto LABEL_35;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7E,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\keytranskey\\tpmkeytranskey.cpp",
    (const char *)(unsigned int)TpmHmacKeyHandle,
    v34);
LABEL_35:
  wil::details::ScopeExitFnGuard__lambda_2956302556b4326badb9c69f95faa1fc___::operator()(&v45);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v47);
  return v13;
}

```

## disassembly

```asm
0x1800181a0  push    rbp
0x1800181a2  push    rbx
0x1800181a3  push    rsi
0x1800181a4  push    rdi
0x1800181a5  push    r12
0x1800181a7  push    r13
0x1800181a9  push    r14
0x1800181ab  push    r15
0x1800181ad  lea     rbp, [rsp-17h]
0x1800181b2  sub     rsp, 0B8h
0x1800181b9  mov     rax, cs:__security_cookie
0x1800181c0  xor     rax, rsp
0x1800181c3  mov     [rbp+4Fh+var_48], rax
0x1800181c7  mov     r12, r9
0x1800181ca  mov     r14d, r8d
0x1800181cd  mov     rsi, rdx
0x1800181d0  mov     rdi, rcx
0x1800181d3  mov     r13, [rbp+4Fh+arg_20]
0x1800181d7  xor     r15d, r15d
0x1800181da  mov     [rbp+4Fh+var_70], r15d
0x1800181de  mov     [rbp+4Fh+var_6C], r15b
0x1800181e2  lea     rcx, [rbp+4Fh+var_70]
0x1800181e6  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800181eb  mov     eax, cs:dword_180037000
0x1800181f1  cmp     eax, 5
0x1800181f4  jbe     short loc_180018234
0x1800181f6  cmp     [rbp+4Fh+var_6C], r15b
0x1800181fa  jz      short loc_18001821A
0x1800181fc  cmp     [rbp+4Fh+var_58], r15d
0x180018200  jnz     short loc_180018214
0x180018202  cmp     [rbp+4Fh+var_54], r15d
0x180018206  jnz     short loc_180018214
0x180018208  cmp     [rbp+4Fh+var_50], r15d
0x18001820c  jnz     short loc_180018214
0x18001820e  cmp     [rbp+4Fh+var_4C], r15d
0x180018212  jz      short loc_18001821A
0x180018214  lea     r9, [rbp+4Fh+var_58]
0x180018218  jmp     short loc_18001821D
0x18001821a  mov     r9, r15
0x18001821d  lea     r8, [rbp+4Fh+var_68]
0x180018221  lea     rdx, byte_18002EBF1
0x180018228  lea     rcx, dword_180037000
0x18001822f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180018234  lea     rax, [rbp+4Fh+var_70]
0x180018238  mov     [rbp+4Fh+var_80], rax
0x18001823c  mov     [rbp+4Fh+var_78], 100h
0x180018242  mov     [rbp+4Fh+hKey], r15
0x180018246  call    ?Instance@TpmKeysManager@@SAAEAV1@XZ; TpmKeysManager::Instance(void)
0x18001824b  mov     rbx, rax
0x18001824e  mov     rdx, [rdi+20h]
0x180018252  lea     rcx, [rbp+4Fh+var_A0]
0x180018256  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001825b  lea     rcx, [rbp+4Fh+hKey]
0x18001825f  mov     [rsp+0F0h+var_C8], rcx; unsigned int *
0x180018264  mov     byte ptr [rsp+0F0h+var_D0], r15b; int
0x180018269  mov     r9d, r14d
0x18001826c  mov     r8, rsi
0x18001826f  mov     rdx, rax
0x180018272  mov     rcx, rbx
0x180018275  call    ?GetTpmHmacKeyHandle@TpmKeysManager@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAEK_NPEA_K@Z; TpmKeysManager::GetTpmHmacKeyHandle(std::wstring,uchar *,ulong,bool,unsigned __int64 *)
0x18001827a  mov     ebx, eax
0x18001827c  test    eax, eax
0x18001827e  jns     short loc_18001829D
0x180018280  mov     rcx, [rbp+57h]; this
0x180018284  mov     r9d, eax; char *
0x180018287  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001828e  mov     edx, 7Eh ; '~'; void *
0x180018293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018298  jmp     loc_1800184E2
0x18001829d  mov     dword ptr [rbp+4Fh+Size], r15d
0x1800182a1  mov     [rbp+4Fh+var_B8], r15
0x1800182a5  lea     rax, [rbp+4Fh+var_B8]
0x1800182a9  mov     [rbp+4Fh+var_A0], rax
0x1800182ad  mov     qword ptr [rbp+4Fh+var_98], r15
0x1800182b1  mov     [rbp+4Fh+var_90], 1
0x1800182b5  lea     rax, [rbp+4Fh+Size]
0x1800182b9  mov     [rsp+0F0h+var_D0], rax; unsigned __int8 **
0x1800182be  lea     r9, [rbp+4Fh+var_98]; unsigned int
0x1800182c2  mov     r8d, 800h; dwFlags
0x1800182c8  lea     rdx, pszBlobType; "OpaqueTransport"
0x1800182cf  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800182d3  call    ?ExportNCryptKey@NgcUtils@@YAJ_KPEBGKPEAPEAEPEAK@Z; NgcUtils::ExportNCryptKey(unsigned __int64,ushort const *,ulong,uchar * *,ulong *)
0x1800182d8  mov     ebx, eax
0x1800182da  lea     rcx, [rbp+4Fh+var_A0]
0x1800182de  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800182e3  cmp     ebx, 80290422h
0x1800182e9  jz      short loc_1800182FA
0x1800182eb  mov     ecx, ebx; this
0x1800182ed  call    ?ShouldReloadTpmHandle@NgcUtils@@YA_NJ@Z; NgcUtils::ShouldReloadTpmHandle(long)
0x1800182f2  test    al, al
0x1800182f4  jz      loc_1800183CB
0x1800182fa  mov     ecx, cs:dword_180037000
0x180018300  cmp     ecx, 4
0x180018303  jbe     short loc_18001832A
0x180018305  mov     dword ptr [rbp+4Fh+Src], ebx
0x180018308  lea     rax, [rbp+4Fh+Src]
0x18001830c  mov     [rsp+0F0h+var_D0], rax
0x180018311  xor     r9d, r9d
0x180018314  xor     r8d, r8d
0x180018317  lea     rdx, byte_18002EBB1
0x18001831e  lea     rcx, dword_180037000
0x180018325  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001832a  call    ?Instance@TpmKeysManager@@SAAEAV1@XZ; TpmKeysManager::Instance(void)
0x18001832f  mov     rbx, rax
0x180018332  mov     rdx, [rdi+20h]
0x180018336  lea     rcx, [rbp+4Fh+var_A0]
0x18001833a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001833f  lea     rcx, [rbp+4Fh+hKey]
0x180018343  mov     [rsp+0F0h+var_C8], rcx; unsigned int *
0x180018348  mov     byte ptr [rsp+0F0h+var_D0], 1; int
0x18001834d  mov     r9d, r14d
0x180018350  mov     r8, rsi
0x180018353  mov     rdx, rax
0x180018356  mov     rcx, rbx
0x180018359  call    ?GetTpmHmacKeyHandle@TpmKeysManager@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAEK_NPEA_K@Z; TpmKeysManager::GetTpmHmacKeyHandle(std::wstring,uchar *,ulong,bool,unsigned __int64 *)
0x18001835e  mov     ebx, eax
0x180018360  test    eax, eax
0x180018362  jns     short loc_18001838D
0x180018364  mov     r9d, eax; char *
0x180018367  mov     edx, 98h; void *
0x18001836c  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x180018373  mov     rcx, [rbp+57h]; this
0x180018377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001837c  nop
0x18001837d  xor     edx, edx
0x18001837f  lea     rcx, [rbp+4Fh+var_B8]
0x180018383  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x180018388  jmp     loc_1800184E2
0x18001838d  lea     rax, [rbp+4Fh+var_B8]
0x180018391  mov     [rbp+4Fh+var_A0], rax
0x180018395  mov     qword ptr [rbp+4Fh+var_98], r15
0x180018399  mov     [rbp+4Fh+var_90], 1
0x18001839d  lea     rax, [rbp+4Fh+Size]
0x1800183a1  mov     [rsp+0F0h+var_D0], rax; int
0x1800183a6  lea     r9, [rbp+4Fh+var_98]; unsigned int
0x1800183aa  mov     r8d, 800h; dwFlags
0x1800183b0  lea     rdx, pszBlobType; "OpaqueTransport"
0x1800183b7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800183bb  call    ?ExportNCryptKey@NgcUtils@@YAJ_KPEBGKPEAPEAEPEAK@Z; NgcUtils::ExportNCryptKey(unsigned __int64,ushort const *,ulong,uchar * *,ulong *)
0x1800183c0  mov     ebx, eax
0x1800183c2  lea     rcx, [rbp+4Fh+var_A0]
0x1800183c6  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800183cb  test    ebx, ebx
0x1800183cd  jns     short loc_1800183D9
0x1800183cf  mov     r9d, ebx
0x1800183d2  mov     edx, 0A1h
0x1800183d7  jmp     short loc_18001836C
0x1800183d9  mov     [rbp+4Fh+Src], r15
0x1800183dd  xor     edx, edx
0x1800183df  lea     rcx, [rbp+4Fh+Src]
0x1800183e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800183e8  lea     r8, [rbp+4Fh+Src]; unsigned __int16 *
0x1800183ec  mov     rcx, [rdi+8]; this
0x1800183f0  call    ?GetNCryptStringProperty@NgcUtils@@YAJ_KPEBGPEAPEAG@Z; NgcUtils::GetNCryptStringProperty(unsigned __int64,ushort const *,ushort * *)
0x1800183f5  mov     ebx, eax
0x1800183f7  test    eax, eax
0x1800183f9  jns     short loc_180018421
0x1800183fb  mov     r9d, eax; char *
0x1800183fe  mov     edx, 0A7h; void *
0x180018403  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001840a  mov     rcx, [rbp+57h]; this
0x18001840e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018413  lea     rcx, [rbp+4Fh+Src]
0x180018417  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001841c  jmp     loc_18001837D
0x180018421  mov     rbx, [rbp+4Fh+Src]
0x180018425  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018429  inc     rax
0x18001842c  cmp     [rbx+rax*2], r15w
0x180018431  jnz     short loc_180018429
0x180018433  lea     edi, ds:2[rax*2]
0x18001843a  lea     eax, [rdi+0Ch]
0x18001843d  cmp     eax, 0Ch
0x180018440  jnb     short loc_180018451
0x180018442  mov     ebx, 80090005h
0x180018447  mov     r9d, ebx
0x18001844a  mov     edx, 0ABh
0x18001844f  jmp     short loc_180018403
0x180018451  mov     r15d, dword ptr [rbp+4Fh+Size]
0x180018455  lea     r14d, [rax+r15]
0x180018459  cmp     r14d, eax
0x18001845c  jnb     short loc_18001846D
0x18001845e  mov     ebx, 80090005h
0x180018463  mov     r9d, ebx
0x180018466  mov     edx, 0ACh
0x18001846b  jmp     short loc_180018403
0x18001846d  mov     edx, r14d
0x180018470  lea     rcx, [rbp+4Fh+Size]
0x180018474  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180018479  mov     rsi, [rbp+4Fh+Size]
0x18001847d  test    rsi, rsi
0x180018480  jnz     short loc_180018494
0x180018482  mov     ebx, 8007000Eh
0x180018487  mov     r9d, ebx
0x18001848a  mov     edx, 0AFh
0x18001848f  jmp     loc_180018403
0x180018494  mov     dword ptr [rsi], 1
0x18001849a  mov     [rsi+8], r15d
0x18001849e  mov     [rsi+4], edi
0x1800184a1  lea     rcx, [rsi+0Ch]; void *
0x1800184a5  mov     r8, rdi; Size
0x1800184a8  mov     rdx, rbx; Src
0x1800184ab  call    memcpy_0
0x1800184b0  mov     r8, r15; Size
0x1800184b3  lea     rcx, [rsi+0Ch]
0x1800184b7  add     rcx, rdi; void *
0x1800184ba  mov     rdx, [rbp+4Fh+var_B8]; Src
0x1800184be  call    memcpy_0
0x1800184c3  mov     [r12], rsi
0x1800184c7  mov     [r13+0], r14d
0x1800184cb  lea     rcx, [rbp+4Fh+Src]
0x1800184cf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800184d4  nop
0x1800184d5  xor     edx, edx
0x1800184d7  lea     rcx, [rbp+4Fh+var_B8]
0x1800184db  call    ?reset@?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(uchar *)
0x1800184e0  xor     ebx, ebx
0x1800184e2  lea     rcx, [rbp+4Fh+var_80]
0x1800184e6  call    wil__details__ScopeExitFnGuard__lambda_2956302556b4326badb9c69f95faa1fc_____operator__
0x1800184eb  nop
0x1800184ec  lea     rcx, [rbp+4Fh+var_70]
0x1800184f0  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x1800184f5  mov     eax, ebx
0x1800184f7  mov     rcx, [rbp+4Fh+var_48]
0x1800184fb  xor     rcx, rsp; StackCookie
0x1800184fe  call    __security_check_cookie
0x180018503  add     rsp, 0B8h
0x18001850a  pop     r15
0x18001850c  pop     r14
0x18001850e  pop     r13
0x180018510  pop     r12
0x180018512  pop     rdi
0x180018513  pop     rsi
0x180018514  pop     rbx
0x180018515  pop     rbp
0x180018516  retn
```
