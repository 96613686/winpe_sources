# DAS::DevnodeManagment::DevnodeManager::CleanupStaleUserDevnodes(unsigned __int64)

- ea: `0x180039cec`
- end: `0x18003a2ac`
- name: `?CleanupStaleUserDevnodes@DevnodeManager@DevnodeManagment@DAS@@AEAAJ_K@Z`
- size: `1472`
- prototype: `__int64 __fastcall(DAS::DevnodeManagment::DevnodeManager *this, unsigned __int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180039508`
- `0x1800397f4`

## callees

- `0x180005770`
- `0x1800074c0`
- `0x180013be0`
- `0x18001eae0`
- `0x1800240b4`
- `0x180024d60`
- `0x180025d10`
- `0x1800290c4`
- `0x180029884`
- `0x18002a948`
- `0x180039cec`
- `0x18003a2b4`
- `0x18003bc80`
- `0x180045df0`
- `0x18004f844`
- `0x18004fc30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a1f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a216`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a1f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a216`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a224`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180039e3b`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x180039e3b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180039e75`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180039f02`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180039f9b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18003a26a`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180039e75`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180039f02`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180039f9b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18003a26a`

## string_xrefs

- `0x180039d3d`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180039e52`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180039ed5`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180039f64`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x18003a151`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x18003a1d7`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::CleanupStaleUserDevnodes(
        DAS::DevnodeManagment::DevnodeManager *this,
        unsigned __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  __int64 v6; // rcx
  int Objects; // eax
  unsigned int v8; // ebx
  int v9; // [rsp+20h] [rbp-128h]
  unsigned __int16 *Src[2]; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v11; // [rsp+A8h] [rbp-A0h]
  DEVPROPKEY v12; // [rsp+B0h] [rbp-98h]
  int v13; // [rsp+C4h] [rbp-84h]
  __int64 v14; // [rsp+C8h] [rbp-80h]
  int v15; // [rsp+D0h] [rbp-78h]
  int v16; // [rsp+D4h] [rbp-74h]
  unsigned __int16 *v17; // [rsp+D8h] [rbp-70h]
  DEVPROPKEY v18; // [rsp+E0h] [rbp-68h] BYREF
  int v19; // [rsp+F4h] [rbp-54h]
  __int64 v20; // [rsp+F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  Src[0] = 0;
  v2 = DAS::DevnodeManagment::DevnodeManager::UserContextToSidString(a2, Src);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v18 = DEVPKEY_Aep_AepId;
    v19 = 0;
    v20 = 0;
    v11 = 2;
    v12 = DEVPKEY_Aep_PerUserSid;
    v13 = 0;
    v14 = 0;
    v15 = 18;
    v6 = -1;
    do
      ++v6;
    while ( Src[0][v6] );
    v16 = 2 * v6 + 2;
    v17 = Src[0];
    Src[1] = 0;
    Objects = DevGetObjects(3, 0, 1, &v18);
    v8 = Objects;
    if ( Objects >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Src);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
        (const char *)(unsigned int)Objects,
        1);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Src);
      result = v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14C,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
      (const char *)(unsigned int)v2,
      v9);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Src);
    result = v3;
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x19F,
                               (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
                               v4);
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x180039cec  mov     [rsp+arg_0], rbx
0x180039cf1  mov     [rsp+arg_10], rsi
0x180039cf6  push    rdi
0x180039cf7  push    r12
0x180039cf9  push    r14
0x180039cfb  sub     rsp, 130h
0x180039d02  mov     rax, cs:__security_cookie
0x180039d09  xor     rax, rsp
0x180039d0c  mov     [rsp+148h+var_28], rax
0x180039d14  mov     rax, rdx
0x180039d17  xor     r14d, r14d
0x180039d1a  mov     [rsp+148h+Src], r14
0x180039d1f  lea     rdx, [rsp+148h+Src]; unsigned __int16 **
0x180039d24  mov     rcx, rax; unsigned __int64
0x180039d27  call    ?UserContextToSidString@DevnodeManager@DevnodeManagment@DAS@@SAJ_KPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::UserContextToSidString(unsigned __int64,ushort * *)
0x180039d2c  mov     ebx, eax
0x180039d2e  test    eax, eax
0x180039d30  jns     short loc_180039D5F
0x180039d32  mov     rcx, [rsp+148h]; this
0x180039d3a  mov     r9d, eax; char *
0x180039d3d  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180039d44  mov     edx, 14Ch; void *
0x180039d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d4e  lea     rcx, [rsp+148h+Src]
0x180039d53  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039d58  mov     eax, ebx
0x180039d5a  jmp     loc_18003A282
0x180039d5f  movups  xmm0, xmmword ptr cs:DEVPKEY_Aep_AepId.fmtid.Data1
0x180039d66  movups  [rsp+148h+var_68], xmm0
0x180039d6e  mov     eax, cs:DEVPKEY_Aep_AepId.pid
0x180039d74  mov     [rsp+148h+var_58], eax
0x180039d7b  mov     [rsp+148h+var_54], r14d
0x180039d83  mov     [rsp+148h+var_50], r14
0x180039d8b  mov     [rsp+148h+var_A0], 2
0x180039d97  movups  xmm0, xmmword ptr cs:DEVPKEY_Aep_PerUserSid.fmtid.Data1
0x180039d9e  movups  [rsp+148h+var_98], xmm0
0x180039da6  mov     eax, cs:DEVPKEY_Aep_PerUserSid.pid
0x180039dac  mov     [rsp+148h+var_88], eax
0x180039db3  mov     [rsp+148h+var_84], r14d
0x180039dbb  mov     [rsp+148h+var_80], r14
0x180039dc3  mov     [rsp+148h+var_78], 12h
0x180039dce  mov     rax, [rsp+148h+Src]
0x180039dd3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180039dd7  inc     rcx
0x180039dda  cmp     [rax+rcx*2], r14w
0x180039ddf  jnz     short loc_180039DD7
0x180039de1  lea     ecx, ds:2[rcx*2]
0x180039de8  mov     [rsp+148h+var_74], ecx
0x180039def  mov     [rsp+148h+var_70], rax
0x180039df7  mov     [rsp+148h+var_F8], r14d
0x180039dfc  mov     [rsp+148h+var_E8], r14
0x180039e01  lea     rax, [rsp+148h+var_E8]
0x180039e06  mov     [rsp+148h+var_110], rax
0x180039e0b  lea     rax, [rsp+148h+var_F8]
0x180039e10  mov     [rsp+148h+var_118], rax
0x180039e15  lea     rax, [rsp+148h+var_A0]
0x180039e1d  mov     [rsp+148h+var_120], rax
0x180039e22  mov     dword ptr [rsp+148h+var_128], 1; int
0x180039e2a  lea     r9, [rsp+148h+var_68]
0x180039e32  xor     edx, edx
0x180039e34  lea     ecx, [rdx+3]
0x180039e37  lea     r8d, [rdx+1]
0x180039e3b  call    cs:__imp_DevGetObjects
0x180039e41  mov     ebx, eax
0x180039e43  test    eax, eax
0x180039e45  jns     short loc_180039E8C
0x180039e47  mov     rcx, [rsp+148h]; this
0x180039e4f  mov     r9d, eax; char *
0x180039e52  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180039e59  mov     edx, 15Ch; void *
0x180039e5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e63  mov     ecx, [rsp+148h+var_F8]
0x180039e67  test    ecx, ecx
0x180039e69  jz      short loc_180039E7B
0x180039e6b  mov     rdx, [rsp+148h+var_E8]
0x180039e70  test    rdx, rdx
0x180039e73  jz      short loc_180039E7B
0x180039e75  call    cs:__imp_DevFreeObjects
0x180039e7b  lea     rcx, [rsp+148h+Src]
0x180039e80  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039e85  mov     eax, ebx
0x180039e87  jmp     loc_18003A282
0x180039e8c  cmp     [rsp+148h+var_F8], r14d
0x180039e91  jnz     short loc_180039EA4
0x180039e93  lea     rcx, [rsp+148h+Src]
0x180039e98  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039e9d  xor     eax, eax
0x180039e9f  jmp     loc_18003A282
0x180039ea4  mov     [rsp+148h+var_E0], r14
0x180039ea9  xor     edx, edx
0x180039eab  lea     rcx, [rsp+148h+var_E0]
0x180039eb0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180039eb5  lea     rdx, [rsp+148h+var_E0]; unsigned __int16 **
0x180039eba  mov     rcx, [rsp+148h+Src]; Src
0x180039ebf  call    ?MakePerUserSubKey@DevnodeManager@DevnodeManagment@DAS@@SAJPEBGPEAPEAG@Z; DAS::DevnodeManagment::DevnodeManager::MakePerUserSubKey(ushort const *,ushort * *)
0x180039ec4  mov     ebx, eax
0x180039ec6  test    eax, eax
0x180039ec8  jns     short loc_180039F19
0x180039eca  mov     rcx, [rsp+148h]; this
0x180039ed2  mov     r9d, eax; char *
0x180039ed5  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180039edc  mov     edx, 165h; void *
0x180039ee1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ee6  lea     rcx, [rsp+148h+var_E0]
0x180039eeb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039ef0  mov     ecx, [rsp+148h+var_F8]
0x180039ef4  test    ecx, ecx
0x180039ef6  jz      short loc_180039F08
0x180039ef8  mov     rdx, [rsp+148h+var_E8]
0x180039efd  test    rdx, rdx
0x180039f00  jz      short loc_180039F08
0x180039f02  call    cs:__imp_DevFreeObjects
0x180039f08  lea     rcx, [rsp+148h+Src]
0x180039f0d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039f12  mov     eax, ebx
0x180039f14  jmp     loc_18003A282
0x180039f19  mov     [rsp+148h+var_D8], r14
0x180039f1e  mov     rbx, cs:?g_StoreManager@@3V?$unique_ptr@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@U?$default_delete@VPnpObjectStoreManager@Internal@Pnp@Devices@Windows@@@std@@@std@@A; std::unique_ptr<Windows::Devices::Pnp::Internal::PnpObjectStoreManager> g_StoreManager
0x180039f25  lea     rcx, [rsp+148h+var_D8]
0x180039f2a  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180039f2f  lea     rax, [rsp+148h+var_D8]
0x180039f34  mov     [rsp+148h+var_128], rax; int
0x180039f39  mov     r9d, 8
0x180039f3f  mov     r8, [rsp+148h+var_E0]
0x180039f44  mov     rdx, 0FFFFFFFF80000003h
0x180039f4b  mov     rcx, rbx
0x180039f4e  call    ?GetStore@PnpObjectStoreManager@Internal@Pnp@Devices@Windows@@QEAAJPEAUHKEY__@@PEBGW4_PNP_OBJECT_TYPE@@PEAPEAVPnpObjectStore@2345@@Z; Windows::Devices::Pnp::Internal::PnpObjectStoreManager::GetStore(HKEY__ *,ushort const *,_PNP_OBJECT_TYPE,Windows::Devices::Pnp::Internal::PnpObjectStore * *)
0x180039f53  mov     ebx, eax
0x180039f55  test    eax, eax
0x180039f57  jns     short loc_180039FB2
0x180039f59  mov     rcx, [rsp+148h]; this
0x180039f61  mov     r9d, eax; char *
0x180039f64  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180039f6b  mov     edx, 16Bh; void *
0x180039f70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039f75  lea     rcx, [rsp+148h+var_D8]
0x180039f7a  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x180039f7f  lea     rcx, [rsp+148h+var_E0]
0x180039f84  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039f89  mov     ecx, [rsp+148h+var_F8]
0x180039f8d  test    ecx, ecx
0x180039f8f  jz      short loc_180039FA1
0x180039f91  mov     rdx, [rsp+148h+var_E8]
0x180039f96  test    rdx, rdx
0x180039f99  jz      short loc_180039FA1
0x180039f9b  call    cs:__imp_DevFreeObjects
0x180039fa1  lea     rcx, [rsp+148h+Src]
0x180039fa6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180039fab  mov     eax, ebx
0x180039fad  jmp     loc_18003A282
0x180039fb2  mov     esi, r14d
0x180039fb5  cmp     [rsp+148h+var_F8], r14d
0x180039fba  jbe     loc_18003A244
0x180039fc0  lea     r12, WPP_RECORDER_INITIALIZED
0x180039fc7  mov     rdx, qword ptr cs:DEVPKEY_Aep_AepId.fmtid.Data4
0x180039fce  mov     r8, qword ptr cs:DEVPKEY_Aep_AepId.fmtid.Data1
0x180039fd5  mov     edi, esi
0x180039fd7  shl     rdi, 5
0x180039fdb  mov     rax, [rsp+148h+var_E8]
0x180039fe0  mov     rcx, [rdi+rax+18h]
0x180039fe5  test    rcx, rcx
0x180039fe8  jz      loc_18003A238
0x180039fee  cmp     dword ptr [rcx+10h], 8
0x180039ff2  jnz     loc_18003A238
0x180039ff8  mov     rax, [rcx]
0x180039ffb  sub     rax, r8
0x180039ffe  jnz     short loc_18003A007
0x18003a000  mov     rax, [rcx+8]
0x18003a004  sub     rax, rdx
0x18003a007  test    rax, rax
0x18003a00a  jnz     loc_18003A238
0x18003a010  mov     rbx, [rcx+28h]
0x18003a014  test    rbx, rbx
0x18003a017  jz      loc_18003A238
0x18003a01d  cmp     dword ptr [rcx+20h], 12h
0x18003a021  jnz     loc_18003A238
0x18003a027  movups  xmm0, cs:DEVPKEY_Aep_IsAssociated
0x18003a02e  movups  xmmword ptr [rsp+148h+var_48.Key.fmtid.Data1], xmm0
0x18003a036  mov     eax, cs:dword_18008C9A8
0x18003a03c  mov     [rsp+148h+var_48.Key.pid], eax
0x18003a043  mov     [rsp+148h+var_48.Store], 1
0x18003a04e  mov     [rsp+148h+var_48.LocaleName], r14
0x18003a056  xorps   xmm0, xmm0
0x18003a059  movups  xmmword ptr [rsp+148h+var_D0.CompKey.Key.fmtid.Data1], xmm0
0x18003a05e  movups  xmmword ptr [rsp+148h+var_D0.CompKey.Key.pid], xmm0
0x18003a066  movups  xmmword ptr [rsp+148h+var_D0.Type], xmm0
0x18003a06e  lea     rax, [rsp+148h+var_D0]
0x18003a073  mov     [rsp+148h+var_128], rax; int
0x18003a078  xor     r9d, r9d; unsigned __int16 *
0x18003a07b  lea     r8, [rsp+148h+var_48]; struct _DEVPROPCOMPKEY *
0x18003a083  mov     rdx, rbx; unsigned __int16 *
0x18003a086  mov     rcx, [rsp+148h+var_D8]; this
0x18003a08b  call    ?GetProperty@PnpObjectStore@Internal@Pnp@Devices@Windows@@QEAAJPEBGPEBU_DEVPROPCOMPKEY@@0PEAU_DEVPROPERTY@@@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::GetProperty(ushort const *,_DEVPROPCOMPKEY const *,ushort const *,_DEVPROPERTY *)
0x18003a090  mov     edx, eax
0x18003a092  cmp     eax, 80070490h
0x18003a097  jz      loc_18003A167
0x18003a09d  test    eax, eax
0x18003a09f  js      loc_18003A127
0x18003a0a5  cmp     [rsp+148h+var_D0.Type], 11h
0x18003a0ad  jnz     short loc_18003A127
0x18003a0af  mov     rcx, [rsp+148h+var_D0.Buffer]
0x18003a0b7  test    rcx, rcx
0x18003a0ba  jz      short loc_18003A0C5
0x18003a0bc  cmp     [rcx], r14b
0x18003a0bf  jz      loc_18003A167
0x18003a0c5  cmp     [rsp+148h+var_D0.Type], 11h
0x18003a0cd  jnz     short loc_18003A127
0x18003a0cf  mov     rcx, [rsp+148h+var_D0.Buffer]
0x18003a0d7  test    rcx, rcx
0x18003a0da  jz      short loc_18003A127
0x18003a0dc  cmp     byte ptr [rcx], 0FFh
0x18003a0df  jnz     short loc_18003A127
0x18003a0e1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003a0e8  jz      loc_18003A1E8
0x18003a0ee  mov     r9d, 10h
0x18003a0f4  mov     rax, [rsp+148h+Src]
0x18003a0f9  mov     [rsp+148h+var_110], rax
0x18003a0fe  mov     [rsp+148h+var_118], rbx
0x18003a103  mov     rax, [rsp+148h+var_E8]
0x18003a108  mov     rcx, [rdi+rax+8]
0x18003a10d  mov     [rsp+148h+var_120], rcx
0x18003a112  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a119  mov     rcx, [rcx+28h]
0x18003a11d  call    WPP_RECORDER_SF_SSS
0x18003a122  jmp     loc_18003A1E8
0x18003a127  mov     rcx, [rsp+148h]; this
0x18003a12f  mov     dword ptr [rsp+148h+var_110], edx
0x18003a133  mov     rax, [rsp+148h+Src]
0x18003a138  mov     [rsp+148h+var_118], rax
0x18003a13d  mov     [rsp+148h+var_120], rbx; char *
0x18003a142  lea     rax, aFailedToGetAep; "failed to get AEP %ls's property from %"...
0x18003a149  mov     [rsp+148h+var_128], rax; __int64
0x18003a14e  mov     r9d, edx; char *
0x18003a151  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18003a158  mov     edx, 198h; void *
0x18003a15d  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003a162  jmp     loc_18003A1E8
0x18003a167  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003a16e  jz      short loc_18003A1BB
0x18003a170  lea     rax, aAssociated; "associated"
0x18003a177  lea     rcx, aFound; "found"
0x18003a17e  cmp     edx, 80070490h
0x18003a184  cmovnz  rcx, rax
0x18003a188  mov     rax, [rsp+148h+Src]
0x18003a18d  mov     [rsp+148h+var_108], rax
0x18003a192  mov     [rsp+148h+var_110], rcx
0x18003a197  mov     [rsp+148h+var_118], rbx
0x18003a19c  mov     rax, [rsp+148h+var_E8]
0x18003a1a1  mov     rcx, [rdi+rax+8]
0x18003a1a6  mov     [rsp+148h+var_120], rcx
0x18003a1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a1b2  mov     rcx, [rcx+28h]
0x18003a1b6  call    WPP_RECORDER_SF_SSSS
0x18003a1bb  mov     r8, [rsp+148h+Src]; unsigned __int16 *
0x18003a1c0  mov     rdx, rbx; unsigned __int16 *
0x18003a1c3  call    ?UninstallDevnodesCommon@DevnodeManager@DevnodeManagment@DAS@@AEAAJPEBG0@Z; DAS::DevnodeManagment::DevnodeManager::UninstallDevnodesCommon(ushort const *,ushort const *)
0x18003a1c8  mov     rcx, [rsp+148h]; this
0x18003a1d0  test    eax, eax
0x18003a1d2  jns     short loc_18003A1E8
0x18003a1d4  mov     r9d, eax; char *
0x18003a1d7  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18003a1de  mov     edx, 18Eh; void *
0x18003a1e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a1e8  mov     rbx, [rsp+148h+var_D0.CompKey.LocaleName]
0x18003a1f0  test    rbx, rbx
0x18003a1f3  jz      short loc_18003A209
0x18003a1f5  call    cs:__imp_GetProcessHeap
0x18003a1fb  mov     r8, rbx; lpMem
0x18003a1fe  xor     edx, edx; dwFlags
0x18003a200  mov     rcx, rax; hHeap
0x18003a203  call    cs:__imp_HeapFree
0x18003a209  mov     rbx, [rsp+148h+var_D0.Buffer]
0x18003a211  test    rbx, rbx
0x18003a214  jz      short loc_18003A22A
0x18003a216  call    cs:__imp_GetProcessHeap
0x18003a21c  mov     r8, rbx; lpMem
0x18003a21f  xor     edx, edx; dwFlags
0x18003a221  mov     rcx, rax; hHeap
0x18003a224  call    cs:__imp_HeapFree
0x18003a22a  mov     r8, qword ptr cs:DEVPKEY_Aep_AepId.fmtid.Data1
0x18003a231  mov     rdx, qword ptr cs:DEVPKEY_Aep_AepId.fmtid.Data4
0x18003a238  inc     esi
0x18003a23a  cmp     esi, [rsp+148h+var_F8]
0x18003a23e  jb      loc_180039FD5
0x18003a244  lea     rcx, [rsp+148h+var_D8]
0x18003a249  call    ?InternalRelease@?$ComPtr@VCDevnodeManagementCallback@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CDevnodeManagementCallback>::InternalRelease(void)
0x18003a24e  lea     rcx, [rsp+148h+var_E0]
0x18003a253  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a258  mov     ecx, [rsp+148h+var_F8]
0x18003a25c  test    ecx, ecx
0x18003a25e  jz      short loc_18003A270
0x18003a260  mov     rdx, [rsp+148h+var_E8]
0x18003a265  test    rdx, rdx
0x18003a268  jz      short loc_18003A270
0x18003a26a  call    cs:__imp_DevFreeObjects
0x18003a270  lea     rcx, [rsp+148h+Src]
0x18003a275  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003a27a  xor     eax, eax
0x18003a27c  jmp     short loc_18003A282
0x18003a27e  mov     eax, [rsp+148h+var_F8]
  ... truncated ...
```
