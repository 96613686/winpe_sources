# CNodeChangeSetBuilder::BuildChangeSetXml(ushort const *,ushort const *,IConfigSession2 *,void * *)

- ea: `0x18005c930`
- end: `0x18005cd21`
- name: `?BuildChangeSetXml@CNodeChangeSetBuilder@@QEAAJPEBG0PEAUIConfigSession2@@PEAPEAX@Z`
- size: `1009`
- prototype: `__int64 __fastcall(CNodeChangeSetBuilder *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IConfigSession2 *, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800588bc`

## callees

- `0x180008de0`
- `0x18000b770`
- `0x18000caf4`
- `0x18000d4d4`
- `0x18003fb44`
- `0x18005ae90`
- `0x18005be0c`
- `0x18005be64`
- `0x18005c118`
- `0x18005c1b4`
- `0x18005c930`
- `0x18005ce1c`
- `0x18005ed9c`
- `0x18005eed4`
- `0x180107010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18005ca61`
- `XmlLite!CreateXmlWriter` at `0x18005ca61`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18005ca97`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x18005ca97`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18005cc6c`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x18005cc6c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18005c9f5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18005c9f5`

## string_xrefs

- `0x18005c96c`: `BuildChangeSetXmlActivity`
- `0x18005c9ac`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005ca16`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`
- `0x18005cc88`: `onecoreuap\admin\enterprisemgmt\enterprisecsps\v2\nodecache\nodechangesetbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CNodeChangeSetBuilder::BuildChangeSetXml(
        CNodeChangeSetBuilder *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IConfigSession2 *a4,
        void **a5)
{
  __int64 v8; // rdx
  int v9; // ebx
  HRESULT v10; // eax
  __int64 v11; // rdx
  unsigned __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rcx
  HRESULT HGlobalFromStream; // eax
  HGLOBAL v16; // rax
  int *v18; // [rsp+20h] [rbp-E0h]
  void *ppvObject; // [rsp+30h] [rbp-D0h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-C8h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  HGLOBAL phglobal[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[64]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v25[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v25);
  v25[0] = &NodeChangeSetBuilderProvider::BuildChangeSetXmlActivity::`vftable';
  NodeChangeSetBuilderProvider::BuildChangeSetXmlActivity::StartActivity((NodeChangeSetBuilderProvider::BuildChangeSetXmlActivity *)v25);
  if ( a5 )
  {
    if ( !a4 )
    {
      v8 = 166;
      goto LABEL_5;
    }
    ppvObject = 0;
    ppOutput = 0;
    ppstm = 0;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    v10 = CreateStreamOnHGlobal(0, 0, &ppstm);
    v9 = v10;
    if ( v10 >= 0 )
    {
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
      v10 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
      v9 = v10;
      if ( v10 >= 0 )
      {
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
        v10 = CreateXmlWriterOutputWithEncodingName((IUnknown *)ppstm, 0, L"UTF-16", &ppOutput);
        v9 = v10;
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2);
          v9 = v10;
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(
                    ppvObject,
                    ppOutput);
            v9 = v10;
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4, 1);
              v9 = v10;
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
                        ppvObject,
                        0,
                        L"Nodes",
                        0);
                v9 = v10;
                if ( v10 >= 0 )
                {
                  v22 = 0;
                  v13 = lambda_3ec2cfa3c724b0d9d88e869b5e29e31c_::_lambda_3ec2cfa3c724b0d9d88e869b5e29e31c_(
                          phglobal,
                          &ppvObject);
                  std::function_long___cdecl_unsigned_short___unsigned_short___tagVARIANT___enum_ConfigDataType__::function_long___cdecl_unsigned_short___unsigned_short___tagVARIANT___enum_ConfigDataType____lambda_3ec2cfa3c724b0d9d88e869b5e29e31c__0_(
                    v24,
                    v13);
                  v18 = &v22;
                  v9 = CNodeChangeSetBuilder::EnumerateCacheEntries(v14, a4, a2, a3);
                  std::function<long (unsigned short *,unsigned short *,tagVARIANT *,enum ConfigDataType)>::~function<long (unsigned short *,unsigned short *,tagVARIANT *,enum ConfigDataType)>(v24);
                  Microsoft::WRL::ComPtr<Windows::Networking::PushNotifications::IPushNotificationChannelManagerStatics>::~ComPtr<Windows::Networking::PushNotifications::IPushNotificationChannelManagerStatics>(phglobal);
                  if ( v9 < 0 )
                  {
                    v12 = (unsigned int)v9;
                    v11 = 216;
                    goto LABEL_9;
                  }
                  v10 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 136LL))(ppvObject);
                  v9 = v10;
                  if ( v10 >= 0 )
                  {
                    if ( v22 )
                    {
                      v10 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
                      v9 = v10;
                      if ( v10 < 0 )
                      {
                        v11 = 222;
                        goto LABEL_8;
                      }
                      v22 = 0;
                      v10 = (*(__int64 (__fastcall **)(LPSTREAM, const unsigned __int16 near *const *, __int64, int *))(*(_QWORD *)ppstm + 32LL))(
                              ppstm,
                              &CNodeChangeSetBuilder::c_szTerminator,
                              2,
                              &v22);
                      v9 = v10;
                      if ( v10 < 0 )
                      {
                        v11 = 226;
                        goto LABEL_8;
                      }
                      phglobal[0] = 0;
                      HGlobalFromStream = GetHGlobalFromStream(ppstm, phglobal);
                      v9 = HGlobalFromStream;
                      if ( HGlobalFromStream < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xE5,
                          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
                          (const char *)(unsigned int)HGlobalFromStream,
                          (int)&v22);
                        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(phglobal);
                        goto LABEL_10;
                      }
                      v16 = phglobal[0];
                      phglobal[0] = 0;
                      *a5 = v16;
                      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(phglobal);
                    }
                    wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v25);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
                    v9 = 0;
                    goto LABEL_36;
                  }
                  v11 = 218;
                }
                else
                {
                  v11 = 179;
                }
              }
              else
              {
                v11 = 177;
              }
            }
            else
            {
              v11 = 176;
            }
          }
          else
          {
            v11 = 175;
          }
        }
        else
        {
          v11 = 174;
        }
      }
      else
      {
        v11 = 173;
      }
    }
    else
    {
      v11 = 172;
    }
LABEL_8:
    v12 = (unsigned int)v10;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
      (const char *)v12,
      (int)v18);
LABEL_10:
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppstm);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppOutput);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&ppvObject);
    goto LABEL_36;
  }
  v8 = 165;
LABEL_5:
  v9 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\nodecache\\nodechangesetbuilder.cpp",
    (const char *)0x80070057LL,
    (int)v18);
LABEL_36:
  NodeChangeSetBuilderProvider::BuildChangeSetXmlActivity::~BuildChangeSetXmlActivity((NodeChangeSetBuilderProvider::BuildChangeSetXmlActivity *)v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18005c930  mov     [rsp-8+arg_0], rbx
0x18005c935  push    rbp
0x18005c936  push    rsi
0x18005c937  push    rdi
0x18005c938  push    r14
0x18005c93a  push    r15
0x18005c93c  lea     rbp, [rsp-100h]
0x18005c944  sub     rsp, 200h
0x18005c94b  mov     rax, cs:__security_cookie
0x18005c952  xor     rax, rsp
0x18005c955  mov     [rbp+120h+var_30], rax
0x18005c95c  mov     rdi, r9
0x18005c95f  mov     r15, r8
0x18005c962  mov     r14, rdx
0x18005c965  mov     rsi, [rbp+120h+arg_20]
0x18005c96c  lea     rdx, aBuildchangeset; "BuildChangeSetXmlActivity"
0x18005c973  lea     rcx, [rbp+120h+var_180]; struct wil::details::IFailureCallback *
0x18005c977  call    ??0?$ActivityBase@VNodeCacheProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18005c97c  lea     rax, ??_7BuildChangeSetXmlActivity@NodeChangeSetBuilderProvider@@6B@; const NodeChangeSetBuilderProvider::BuildChangeSetXmlActivity::`vftable'
0x18005c983  mov     [rbp+120h+var_180], rax
0x18005c987  lea     rcx, [rbp+120h+var_180]; this
0x18005c98b  call    ?StartActivity@BuildChangeSetXmlActivity@NodeChangeSetBuilderProvider@@QEAAXXZ; NodeChangeSetBuilderProvider::BuildChangeSetXmlActivity::StartActivity(void)
0x18005c990  nop
0x18005c991  test    rsi, rsi
0x18005c994  jnz     short loc_18005C99D
0x18005c996  mov     edx, 0A5h
0x18005c99b  jmp     short loc_18005C9A7
0x18005c99d  test    rdi, rdi
0x18005c9a0  jnz     short loc_18005C9C7
0x18005c9a2  mov     edx, 0A6h; void *
0x18005c9a7  mov     ebx, 80070057h
0x18005c9ac  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005c9b3  mov     r9d, ebx; char *
0x18005c9b6  mov     rcx, [rbp+128h]; this
0x18005c9bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c9c2  jmp     loc_18005CCEF
0x18005c9c7  mov     [rsp+220h+ppvObject], 0
0x18005c9d0  mov     [rsp+220h+ppOutput], 0
0x18005c9d9  mov     [rsp+220h+ppstm], 0
0x18005c9e2  lea     rcx, [rsp+220h+ppstm]
0x18005c9e7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005c9ec  lea     r8, [rsp+220h+ppstm]; ppstm
0x18005c9f1  xor     edx, edx; fDeleteOnRelease
0x18005c9f3  xor     ecx, ecx; hGlobal
0x18005c9f5  call    cs:__imp_CreateStreamOnHGlobal
0x18005c9fc  nop     dword ptr [rax+rax+00h]
0x18005ca01  mov     ebx, eax
0x18005ca03  test    eax, eax
0x18005ca05  jns     short loc_18005CA48
0x18005ca07  mov     edx, 0ACh; void *
0x18005ca0c  mov     r9d, eax; char *
0x18005ca0f  mov     rcx, [rbp+128h]; this
0x18005ca16  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005ca1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ca22  nop
0x18005ca23  lea     rcx, [rsp+220h+ppstm]
0x18005ca28  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005ca2d  nop
0x18005ca2e  lea     rcx, [rsp+220h+ppOutput]
0x18005ca33  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005ca38  nop
0x18005ca39  lea     rcx, [rsp+220h+ppvObject]
0x18005ca3e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005ca43  jmp     loc_18005CCEF
0x18005ca48  lea     rcx, [rsp+220h+ppvObject]
0x18005ca4d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005ca52  xor     r8d, r8d; pMalloc
0x18005ca55  lea     rdx, [rsp+220h+ppvObject]; ppvObject
0x18005ca5a  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18005ca61  call    cs:__imp_CreateXmlWriter
0x18005ca68  nop     dword ptr [rax+rax+00h]
0x18005ca6d  mov     ebx, eax
0x18005ca6f  test    eax, eax
0x18005ca71  jns     short loc_18005CA7A
0x18005ca73  mov     edx, 0ADh
0x18005ca78  jmp     short loc_18005CA0C
0x18005ca7a  lea     rcx, [rsp+220h+ppOutput]
0x18005ca7f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005ca84  lea     r9, [rsp+220h+ppOutput]; ppOutput
0x18005ca89  lea     r8, pwszEncodingName; "UTF-16"
0x18005ca90  xor     edx, edx; pMalloc
0x18005ca92  mov     rcx, [rsp+220h+ppstm]; pOutputStream
0x18005ca97  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x18005ca9e  nop     dword ptr [rax+rax+00h]
0x18005caa3  mov     ebx, eax
0x18005caa5  test    eax, eax
0x18005caa7  jns     short loc_18005CAB3
0x18005caa9  mov     edx, 0AEh
0x18005caae  jmp     loc_18005CA0C
0x18005cab3  mov     rcx, [rsp+220h+ppvObject]
0x18005cab8  mov     rax, [rcx]
0x18005cabb  xor     r8d, r8d
0x18005cabe  lea     edx, [r8+2]
0x18005cac2  mov     rax, [rax+28h]
0x18005cac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cacb  mov     ebx, eax
0x18005cacd  test    eax, eax
0x18005cacf  jns     short loc_18005CADB
0x18005cad1  mov     edx, 0AFh
0x18005cad6  jmp     loc_18005CA0C
0x18005cadb  mov     rcx, [rsp+220h+ppvObject]
0x18005cae0  mov     rax, [rcx]
0x18005cae3  mov     rdx, [rsp+220h+ppOutput]
0x18005cae8  mov     rax, [rax+18h]
0x18005caec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005caf1  mov     ebx, eax
0x18005caf3  test    eax, eax
0x18005caf5  jns     short loc_18005CB01
0x18005caf7  mov     edx, 0B0h
0x18005cafc  jmp     loc_18005CA0C
0x18005cb01  mov     rcx, [rsp+220h+ppvObject]
0x18005cb06  mov     rax, [rcx]
0x18005cb09  mov     edx, 4
0x18005cb0e  lea     r8d, [rdx-3]
0x18005cb12  mov     rax, [rax+28h]
0x18005cb16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb1b  mov     ebx, eax
0x18005cb1d  test    eax, eax
0x18005cb1f  jns     short loc_18005CB2B
0x18005cb21  mov     edx, 0B1h
0x18005cb26  jmp     loc_18005CA0C
0x18005cb2b  mov     rcx, [rsp+220h+ppvObject]
0x18005cb30  mov     rax, [rcx]
0x18005cb33  xor     r9d, r9d
0x18005cb36  lea     r8, aNodes; "Nodes"
0x18005cb3d  xor     edx, edx
0x18005cb3f  mov     rax, [rax+0D8h]
0x18005cb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb4b  mov     ebx, eax
0x18005cb4d  test    eax, eax
0x18005cb4f  jns     short loc_18005CB5B
0x18005cb51  mov     edx, 0B3h
0x18005cb56  jmp     loc_18005CA0C
0x18005cb5b  mov     [rsp+220h+var_1D8], 0
0x18005cb63  lea     rdx, [rsp+220h+ppvObject]
0x18005cb68  lea     rcx, [rsp+220h+phglobal]
0x18005cb6d  call    _lambda_3ec2cfa3c724b0d9d88e869b5e29e31c____lambda_3ec2cfa3c724b0d9d88e869b5e29e31c_
0x18005cb72  nop
0x18005cb73  mov     rdx, rax
0x18005cb76  lea     rcx, [rsp+220h+var_1C0]
0x18005cb7b  call    std__function_long___cdecl_unsigned_short___unsigned_short___tagVARIANT___enum_ConfigDataType____function_long___cdecl_unsigned_short___unsigned_short___tagVARIANT___enum_ConfigDataType____lambda_3ec2cfa3c724b0d9d88e869b5e29e31c__0_
0x18005cb80  nop
0x18005cb81  lea     rax, [rsp+220h+var_1C0]
0x18005cb86  mov     [rsp+220h+var_1F8], rax
0x18005cb8b  lea     rax, [rsp+220h+var_1D8]
0x18005cb90  mov     qword ptr [rsp+220h+var_200], rax; int
0x18005cb95  mov     r9, r15
0x18005cb98  mov     r8, r14
0x18005cb9b  mov     rdx, rdi
0x18005cb9e  call    ?EnumerateCacheEntries@CNodeChangeSetBuilder@@QEAAJPEAUIConfigSession2@@PEBG1PEAH$$QEAV?$function@$$A6AJPEAG0PEAUtagVARIANT@@W4ConfigDataType@@@Z@std@@@Z; CNodeChangeSetBuilder::EnumerateCacheEntries(IConfigSession2 *,ushort const *,ushort const *,int *,std::function<long (ushort *,ushort *,tagVARIANT *,ConfigDataType)> &&)
0x18005cba3  mov     ebx, eax
0x18005cba5  lea     rcx, [rsp+220h+var_1C0]
0x18005cbaa  call    ??1?$function@$$A6AJPEAG0PEAUtagVARIANT@@W4ConfigDataType@@@Z@std@@QEAA@XZ; std::function<long (ushort *,ushort *,tagVARIANT *,ConfigDataType)>::~function<long (ushort *,ushort *,tagVARIANT *,ConfigDataType)>(void)
0x18005cbaf  nop
0x18005cbb0  lea     rcx, [rsp+220h+phglobal]
0x18005cbb5  call    ??1?$ComPtr@UIPushNotificationChannelManagerStatics@PushNotifications@Networking@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Networking::PushNotifications::IPushNotificationChannelManagerStatics>::~ComPtr<Windows::Networking::PushNotifications::IPushNotificationChannelManagerStatics>(void)
0x18005cbba  test    ebx, ebx
0x18005cbbc  jns     short loc_18005CBCB
0x18005cbbe  mov     r9d, ebx
0x18005cbc1  mov     edx, 0D8h
0x18005cbc6  jmp     loc_18005CA0F
0x18005cbcb  mov     rcx, [rsp+220h+ppvObject]
0x18005cbd0  mov     rax, [rcx]
0x18005cbd3  mov     rax, [rax+88h]
0x18005cbda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cbdf  mov     ebx, eax
0x18005cbe1  test    eax, eax
0x18005cbe3  jns     short loc_18005CBEF
0x18005cbe5  mov     edx, 0DAh
0x18005cbea  jmp     loc_18005CA0C
0x18005cbef  cmp     [rsp+220h+var_1D8], 0
0x18005cbf4  jz      loc_18005CCC3
0x18005cbfa  mov     rcx, [rsp+220h+ppvObject]
0x18005cbff  mov     rax, [rcx]
0x18005cc02  mov     rax, [rax+0F8h]
0x18005cc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc0e  mov     ebx, eax
0x18005cc10  test    eax, eax
0x18005cc12  jns     short loc_18005CC1E
0x18005cc14  mov     edx, 0DEh
0x18005cc19  jmp     loc_18005CA0C
0x18005cc1e  mov     [rsp+220h+var_1D8], 0
0x18005cc26  mov     rcx, [rsp+220h+ppstm]
0x18005cc2b  mov     rax, [rcx]
0x18005cc2e  lea     r9, [rsp+220h+var_1D8]
0x18005cc33  mov     r8d, 2
0x18005cc39  lea     rdx, ?c_szTerminator@CNodeChangeSetBuilder@@2QBGB; ushort const near * const CNodeChangeSetBuilder::c_szTerminator
0x18005cc40  mov     rax, [rax+20h]
0x18005cc44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc49  mov     ebx, eax
0x18005cc4b  test    eax, eax
0x18005cc4d  jns     short loc_18005CC59
0x18005cc4f  mov     edx, 0E2h
0x18005cc54  jmp     loc_18005CA0C
0x18005cc59  mov     [rsp+220h+phglobal], 0
0x18005cc62  lea     rdx, [rsp+220h+phglobal]; phglobal
0x18005cc67  mov     rcx, [rsp+220h+ppstm]; pstm
0x18005cc6c  call    cs:__imp_GetHGlobalFromStream
0x18005cc73  nop     dword ptr [rax+rax+00h]
0x18005cc78  mov     ebx, eax
0x18005cc7a  test    eax, eax
0x18005cc7c  jns     short loc_18005CCA8
0x18005cc7e  mov     rcx, [rbp+128h]; this
0x18005cc85  mov     r9d, eax; char *
0x18005cc88  lea     r8, aOnecoreuapAdmi_46; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18005cc8f  mov     edx, 0E5h; void *
0x18005cc94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cc99  lea     rcx, [rsp+220h+phglobal]
0x18005cc9e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?GlobalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005cca3  jmp     loc_18005CA23
0x18005cca8  mov     rax, [rsp+220h+phglobal]
0x18005ccad  mov     [rsp+220h+phglobal], 0
0x18005ccb6  mov     [rsi], rax
0x18005ccb9  lea     rcx, [rsp+220h+phglobal]
0x18005ccbe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?GlobalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&GlobalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005ccc3  lea     rcx, [rbp+120h+var_180]
0x18005ccc7  call    ?Stop@?$ActivityBase@VNodeCacheProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NodeCacheProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18005cccc  nop
0x18005cccd  lea     rcx, [rsp+220h+ppstm]
0x18005ccd2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005ccd7  nop
0x18005ccd8  lea     rcx, [rsp+220h+ppOutput]
0x18005ccdd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005cce2  nop
0x18005cce3  lea     rcx, [rsp+220h+ppvObject]
0x18005cce8  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18005cced  xor     ebx, ebx
0x18005ccef  lea     rcx, [rbp+120h+var_180]; this
0x18005ccf3  call    ??1BuildChangeSetXmlActivity@NodeChangeSetBuilderProvider@@QEAA@XZ; NodeChangeSetBuilderProvider::BuildChangeSetXmlActivity::~BuildChangeSetXmlActivity(void)
0x18005ccf8  mov     eax, ebx
0x18005ccfa  mov     rcx, [rbp+120h+var_30]
0x18005cd01  xor     rcx, rsp; StackCookie
0x18005cd04  call    __security_check_cookie
0x18005cd09  mov     rbx, [rsp+220h+arg_0]
0x18005cd11  add     rsp, 200h
0x18005cd18  pop     r15
0x18005cd1a  pop     r14
0x18005cd1c  pop     rdi
0x18005cd1d  pop     rsi
0x18005cd1e  pop     rbp
0x18005cd1f  retn
```
