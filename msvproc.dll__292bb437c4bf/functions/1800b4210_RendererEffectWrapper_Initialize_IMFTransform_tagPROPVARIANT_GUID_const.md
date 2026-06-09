# RendererEffectWrapper::Initialize(IMFTransform *,tagPROPVARIANT *,_GUID const &)

- ea: `0x1800b4210`
- end: `0x1800b4438`
- name: `?Initialize@RendererEffectWrapper@@QEAAJPEAUIMFTransform@@PEAUtagPROPVARIANT@@AEBU_GUID@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(RendererEffectWrapper *__hidden this, struct IMFTransform *, struct tagPROPVARIANT *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800300ac`
- `0x18003c920`

## callees

- `0x18000a09c`
- `0x18000a954`
- `0x18000c9d0`
- `0x18000caec`
- `0x18000ec20`
- `0x18000ecf0`
- `0x180014be0`
- `0x180027338`
- `0x18003639c`
- `0x1800444ec`
- `0x180052250`
- `0x180058e0c`
- `0x18005b5a4`
- `0x180065c10`
- `0x1800b3270`
- `0x1800b40a4`
- `0x1800b4210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b4239`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b4239`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b441c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b441c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b426a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800b426a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800b4262`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800b4262`

## pseudocode

```c
__int64 __fastcall RendererEffectWrapper::Initialize(
        RendererEffectWrapper *this,
        struct IMFTransform *a2,
        struct tagPROPVARIANT *a3,
        const struct _GUID *a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  PROPVARIANT *v9; // rcx
  unsigned int *v10; // r8
  int v11; // eax
  struct IMFAttributes *v12; // rcx
  unsigned int v13; // ebx
  int v14; // ebx
  CallStackTracing *v15; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  PCNZWCH *p_sourceString; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v19; // [rsp+38h] [rbp-18h] BYREF
  char v20; // [rsp+40h] [rbp-10h]
  char v21; // [rsp+80h] [rbp+30h] BYREF
  PCNZWCH sourceString; // [rsp+90h] [rbp+40h] BYREF
  struct IMFAttributes *v23; // [rsp+98h] [rbp+48h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 728);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 728));
  v23 = 0;
  Microsoft::WRL::ComPtr<IMFTransform>::operator=((char *)this + 152, a2);
  v9 = (PROPVARIANT *)((char *)this + 64);
  if ( a3 )
    PropVariantCopy(v9, a3);
  else
    PropVariantClear(v9);
  *(struct _GUID *)((char *)this + 88) = *a4;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::GetImpl'::`2'::impl) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
    if ( (int)RendererEffectWrapper::GetAttributes(this, &v23) >= 0 )
    {
      v11 = MFGetAttributeUINT32(v23, MF_SA_D3D11_AWARE, 0);
      v12 = v23;
      *((_BYTE *)this + 104) = v11 != 0;
      *((_BYTE *)this + 105) = (unsigned int)MFGetAttributeUINT32(v12, MF_SA_D3D12_AWARE, 0) != 0;
    }
  }
  if ( *((_QWORD *)this + 24) )
  {
    sourceString = 0;
    p_sourceString = &sourceString;
    v19 = 0;
    v20 = 1;
    v13 = (unsigned int)RendererEffectWrapper::GetAssociatedAppServiceName(this, &v19, v10) >> 31;
    wil::details::out_param_ptr_t<unsigned short * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_ptr_t<unsigned short * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_sourceString);
    if ( (unsigned __int8)v13 != 1 )
    {
      if ( (int)RendererEffectWrapper::ConnectToAppService(this, sourceString, 0) < 0 )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v21, "RendererEffectWrapper::Initialize", 328);
        v14 = RendererEffectWrapper::ConnectToAppService(this, sourceString, 1);
        if ( v14 < 0 )
        {
          v15 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v15 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v15 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v15);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v14 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "RendererEffectWrapper::Initialize", 328, v14);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              35,
              &WPP_e7b63f7618733801a471ab74d0df161d_Traceguids,
              this,
              v14);
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
          goto LABEL_21;
        }
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v21);
      }
      StringCchCopyW((unsigned __int16 *)this + 104, 0x100u, sourceString);
    }
LABEL_21:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&sourceString);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  if ( v4 )
    LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x1800b4210  mov     [rsp-28h+arg_8], rbx
0x1800b4215  push    rbp
0x1800b4216  push    rsi
0x1800b4217  push    rdi
0x1800b4218  push    r14
0x1800b421a  push    r15
0x1800b421c  mov     rbp, rsp
0x1800b421f  sub     rsp, 50h
0x1800b4223  lea     rsi, [rcx+2D8h]
0x1800b422a  mov     rdi, rcx
0x1800b422d  mov     rcx, rsi; lpCriticalSection
0x1800b4230  mov     r15, r9
0x1800b4233  mov     r14, r8
0x1800b4236  mov     rbx, rdx
0x1800b4239  call    cs:__imp_EnterCriticalSection
0x1800b423f  lea     rcx, [rdi+98h]
0x1800b4246  mov     [rbp+arg_18], 0
0x1800b424e  mov     rdx, rbx
0x1800b4251  call    ??4?$ComPtr@UIMFTransform@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFTransform@@@Z; Microsoft::WRL::ComPtr<IMFTransform>::operator=(IMFTransform *)
0x1800b4256  lea     rcx, [rdi+40h]; pvar
0x1800b425a  test    r14, r14
0x1800b425d  jz      short loc_1800B426A
0x1800b425f  mov     rdx, r14; pvarSrc
0x1800b4262  call    cs:__imp_PropVariantCopy
0x1800b4268  jmp     short loc_1800B4270
0x1800b426a  call    cs:__imp_PropVariantClear
0x1800b4270  movups  xmm0, xmmword ptr [r15]
0x1800b4274  movdqu  xmmword ptr [rdi+58h], xmm0
0x1800b4279  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects> `wil::Feature<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::GetImpl(void)'::`2'::impl
0x1800b4280  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CrossDeviceRendererEffects@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CrossDeviceRendererEffects>::__private_IsEnabled(void)
0x1800b4285  test    al, al
0x1800b4287  jz      short loc_1800B42D8
0x1800b4289  lea     rcx, [rbp+arg_18]
0x1800b428d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4292  lea     rdx, [rbp+arg_18]; struct IMFAttributes **
0x1800b4296  mov     rcx, rdi; this
0x1800b4299  call    ?GetAttributes@RendererEffectWrapper@@QEAAJPEAPEAUIMFAttributes@@@Z; RendererEffectWrapper::GetAttributes(IMFAttributes * *)
0x1800b429e  test    eax, eax
0x1800b42a0  js      short loc_1800B42D8
0x1800b42a2  mov     rcx, [rbp+arg_18]
0x1800b42a6  lea     rdx, MF_SA_D3D11_AWARE
0x1800b42ad  xor     r8d, r8d
0x1800b42b0  call    MFGetAttributeUINT32
0x1800b42b5  mov     rcx, [rbp+arg_18]
0x1800b42b9  lea     rdx, MF_SA_D3D12_AWARE
0x1800b42c0  test    eax, eax
0x1800b42c2  setnz   al
0x1800b42c5  xor     r8d, r8d
0x1800b42c8  mov     [rdi+68h], al
0x1800b42cb  call    MFGetAttributeUINT32
0x1800b42d0  test    eax, eax
0x1800b42d2  setnz   al
0x1800b42d5  mov     [rdi+69h], al
0x1800b42d8  cmp     qword ptr [rdi+0C0h], 0
0x1800b42e0  jz      loc_1800B440B
0x1800b42e6  lea     rax, [rbp+sourceString]
0x1800b42ea  mov     [rbp+sourceString], 0
0x1800b42f2  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x1800b42f6  mov     [rbp+var_20], rax
0x1800b42fa  mov     rcx, rdi; this
0x1800b42fd  mov     [rbp+var_18], 0
0x1800b4305  mov     [rbp+var_10], 1
0x1800b4309  call    ?GetAssociatedAppServiceName@RendererEffectWrapper@@QEAAJPEAPEAGPEAI@Z; RendererEffectWrapper::GetAssociatedAppServiceName(ushort * *,uint *)
0x1800b430e  mov     ebx, eax
0x1800b4310  lea     rcx, [rbp+var_20]
0x1800b4314  shr     ebx, 1Fh
0x1800b4317  call    ??1?$out_param_ptr_t@PEAPEAGV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<ushort * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_ptr_t<ushort * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800b431c  xor     bl, 1
0x1800b431f  jz      loc_1800B4402
0x1800b4325  mov     rdx, [rbp+sourceString]; sourceString
0x1800b4329  xor     r8d, r8d; int
0x1800b432c  mov     rcx, rdi; this
0x1800b432f  call    ?ConnectToAppService@RendererEffectWrapper@@QEAAJPEAGH@Z; RendererEffectWrapper::ConnectToAppService(ushort *,int)
0x1800b4334  test    eax, eax
0x1800b4336  jns     loc_1800B43ED
0x1800b433c  mov     r14d, 148h
0x1800b4342  lea     rdx, aRenderereffect; "RendererEffectWrapper::Initialize"
0x1800b4349  mov     r8d, r14d; int
0x1800b434c  lea     rcx, [rbp+arg_0]; this
0x1800b4350  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b4355  mov     rdx, [rbp+sourceString]; sourceString
0x1800b4359  mov     r8d, 1; int
0x1800b435f  mov     rcx, rdi; this
0x1800b4362  call    ?ConnectToAppService@RendererEffectWrapper@@QEAAJPEAGH@Z; RendererEffectWrapper::ConnectToAppService(ushort *,int)
0x1800b4367  mov     ebx, eax
0x1800b4369  test    eax, eax
0x1800b436b  jns     short loc_1800B43E4
0x1800b436d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b4374  test    rcx, rcx
0x1800b4377  jnz     short loc_1800B4385
0x1800b4379  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800b437e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800b4385  cmp     byte ptr [rcx+8], 0
0x1800b4389  jz      short loc_1800B43AD
0x1800b438b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b4390  cmp     [rax+7CCh], ebx
0x1800b4396  jz      short loc_1800B43AD
0x1800b4398  mov     r9d, ebx; int
0x1800b439b  lea     rdx, aRenderereffect; "RendererEffectWrapper::Initialize"
0x1800b43a2  mov     r8d, r14d; int
0x1800b43a5  mov     rcx, rax; this
0x1800b43a8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b43ad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800b43b4  jb      short loc_1800B43D9
0x1800b43b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b43bd  lea     r8, WPP_e7b63f7618733801a471ab74d0df161d_Traceguids
0x1800b43c4  mov     edx, 23h ; '#'
0x1800b43c9  mov     [rsp+50h+var_30], ebx
0x1800b43cd  mov     r9, rdi
0x1800b43d0  mov     rcx, [rcx+10h]
0x1800b43d4  call    WPP_SF_qD
0x1800b43d9  lea     rcx, [rbp+arg_0]; this
0x1800b43dd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b43e2  jmp     short loc_1800B4402
0x1800b43e4  lea     rcx, [rbp+arg_0]; this
0x1800b43e8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b43ed  mov     r8, [rbp+sourceString]; unsigned __int16 *
0x1800b43f1  lea     rcx, [rdi+0D0h]; unsigned __int16 *
0x1800b43f8  mov     edx, 100h; unsigned __int64
0x1800b43fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b4402  lea     rcx, [rbp+sourceString]
0x1800b4406  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b440b  lea     rcx, [rbp+arg_18]
0x1800b440f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4414  test    rsi, rsi
0x1800b4417  jz      short loc_1800B4422
0x1800b4419  mov     rcx, rsi; lpCriticalSection
0x1800b441c  call    cs:__imp_LeaveCriticalSection
0x1800b4422  mov     rbx, [rsp+50h+arg_8]
0x1800b442a  xor     eax, eax
0x1800b442c  add     rsp, 50h
0x1800b4430  pop     r15
0x1800b4432  pop     r14
0x1800b4434  pop     rdi
0x1800b4435  pop     rsi
0x1800b4436  pop     rbp
0x1800b4437  retn
```
