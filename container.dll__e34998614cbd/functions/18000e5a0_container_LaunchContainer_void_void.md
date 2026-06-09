# container::LaunchContainer(void *,void *)

- ea: `0x18000e5a0`
- end: `0x18000eb43`
- name: `?LaunchContainer@container@@YAXPEAX0@Z`
- size: `1443`
- prototype: `void __fastcall(container *__hidden this, void *, void *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012570`

## callees

- `0x180002ad0`
- `0x18000362c`
- `0x180004b70`
- `0x180004b7c`
- `0x180005038`
- `0x1800051b0`
- `0x180006734`
- `0x180006e98`
- `0x180007c98`
- `0x18000b4bc`
- `0x18000c69c`
- `0x18000ca10`
- `0x18000d390`
- `0x18000d668`
- `0x18000e5a0`
- `0x18000f8f0`
- `0x18000fc98`
- `0x18001054c`
- `0x1800106b0`
- `0x18001203c`
- `0x1800128a8`
- `0x1800296a8`
- `0x180029888`

## import_xrefs

- `ntdll!NtSetInformationJobObject` at `0x18000ea0d`
- `ntdll!NtSetInformationJobObject` at `0x18000ea0d`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18000e7c2`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18000e7c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e899`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e8ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e936`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e899`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e8ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e936`

## string_xrefs

- `0x18000eb25`: `Base package is incompatible with host OS`
- `0x18000e805`: `\REGISTRY\MACHINE\SOFTWARE`
- `0x18000e851`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall container::LaunchContainer(container *this, void *a2, void *a3)
{
  char v5; // si
  unsigned int v6; // eax
  bool v7; // r15
  HKEY v8; // rbx
  HKEY v9; // rdi
  HKEY VirtualRootHandle; // rbx
  HKEY v11; // rdi
  unsigned int v12; // ebx
  NTSTATUS v13; // eax
  void *v14; // rdx
  unsigned int v15; // eax
  int v16; // [rsp+20h] [rbp-E0h]
  const char *v17; // [rsp+28h] [rbp-D8h]
  char v18; // [rsp+30h] [rbp-D0h] BYREF
  struct _GUID JobInformation; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v20; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+68h] [rbp-98h]
  unsigned int v24; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v25; // [rsp+7Ch] [rbp-84h] BYREF
  __int128 v26; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  char v28; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v29; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v30; // [rsp+ACh] [rbp-54h]
  _BYTE v31[32]; // [rsp+B0h] [rbp-50h] BYREF
  char v32; // [rsp+D0h] [rbp-30h]
  unsigned int v33; // [rsp+D8h] [rbp-28h]
  unsigned int v34; // [rsp+DCh] [rbp-24h]
  _OWORD v35[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v36; // [rsp+100h] [rbp+0h]
  void **v37; // [rsp+110h] [rbp+10h] BYREF
  int v38; // [rsp+118h] [rbp+18h] BYREF
  char v39; // [rsp+11Ch] [rbp+1Ch]
  int v40; // [rsp+140h] [rbp+40h] BYREF
  const char *v41; // [rsp+148h] [rbp+48h]
  __int64 v42; // [rsp+150h] [rbp+50h]
  char v43; // [rsp+158h] [rbp+58h]
  int v44; // [rsp+160h] [rbp+60h]
  char v45[152]; // [rsp+168h] [rbp+68h] BYREF
  __int128 v46; // [rsp+200h] [rbp+100h]
  int v47; // [rsp+210h] [rbp+110h]
  __int64 v48; // [rsp+218h] [rbp+118h]
  int *v49; // [rsp+220h] [rbp+120h]
  __int64 v50; // [rsp+228h] [rbp+128h]
  __int64 v51; // [rsp+230h] [rbp+130h]
  void ***v52; // [rsp+238h] [rbp+138h]
  __int64 v53; // [rsp+240h] [rbp+140h]
  int v54; // [rsp+248h] [rbp+148h]
  int *v55; // [rsp+250h] [rbp+150h]
  char v56; // [rsp+258h] [rbp+158h]
  _QWORD v57[42]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v58; // [rsp+3B0h] [rbp+2B0h] BYREF
  int v59; // [rsp+3B8h] [rbp+2B8h]
  const wchar_t *v60; // [rsp+3C0h] [rbp+2C0h]
  unsigned __int16 *p_Data2; // [rsp+3C8h] [rbp+2C8h]
  int v62; // [rsp+3D0h] [rbp+2D0h]
  __int64 v63; // [rsp+3D8h] [rbp+2D8h]
  int v64; // [rsp+3E0h] [rbp+2E0h]
  __int64 v65; // [rsp+3E8h] [rbp+2E8h]
  int v66; // [rsp+3F0h] [rbp+2F0h]
  const wchar_t *v67; // [rsp+3F8h] [rbp+2F8h]
  unsigned __int8 *Data4; // [rsp+400h] [rbp+300h]
  int v69; // [rsp+408h] [rbp+308h]
  __int64 v70; // [rsp+410h] [rbp+310h]
  int v71; // [rsp+418h] [rbp+318h]
  __int64 v72; // [rsp+420h] [rbp+320h]
  int v73; // [rsp+428h] [rbp+328h]
  const wchar_t *v74; // [rsp+430h] [rbp+330h]
  HKEY *v75; // [rsp+438h] [rbp+338h]
  int v76; // [rsp+440h] [rbp+340h]
  __int64 v77; // [rsp+448h] [rbp+348h]
  int v78; // [rsp+450h] [rbp+350h]
  __int64 v79; // [rsp+458h] [rbp+358h]
  int v80; // [rsp+460h] [rbp+360h]
  __int64 v81; // [rsp+468h] [rbp+368h]
  __int64 v82; // [rsp+470h] [rbp+370h]
  int v83; // [rsp+478h] [rbp+378h]
  __int64 v84; // [rsp+480h] [rbp+380h]
  int v85; // [rsp+488h] [rbp+388h]
  wil::details::in1diag3 *retaddr; // [rsp+4D8h] [rbp+3D8h]

  v38 = 0;
  v39 = 0;
  v43 = 0;
  v40 = 0;
  v41 = "ConvertToServerSilo";
  v42 = 0;
  v44 = 0;
  v46 = 0;
  memset_0(v45, 0, sizeof(v45));
  v5 = 1;
  v47 = 1;
  v48 = 0;
  v49 = &v38;
  v50 = 0;
  v51 = 0;
  v52 = &v37;
  v53 = 0;
  v54 = 0;
  v55 = &v40;
  v56 = 0;
  v37 = &ContainerProvider::ConvertToServerSilo::`vftable';
  ContainerProvider::ConvertToServerSilo::StartActivity((ContainerProvider::ConvertToServerSilo *)&v37, this);
  v26 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v26) = 0;
  v35[0] = 0;
  v35[1] = si128;
  LOWORD(v35[0]) = 0;
  *(_QWORD *)&JobInformation.Data1 = 0;
  v58 = 0;
  v59 = 288;
  v60 = L"ContainerMinimumLCU";
  p_Data2 = &JobInformation.Data2;
  v62 = 0x4000000;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 288;
  v67 = L"HostMinimumLCU";
  Data4 = JobInformation.Data4;
  v69 = 0x4000000;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 288;
  v74 = L"SkipVersionCheck";
  v75 = &v20;
  v76 = 0x4000000;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  *(_DWORD *)JobInformation.Data4 = 0;
  LODWORD(v20) = 0;
  v6 = RtlQueryRegistryValuesEx(2, L"Windows Containers", &v58, 0);
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741772 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x18F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_version.cpp",
      (const char *)v6,
      0);
  v7 = (_DWORD)v20 == 0;
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v22);
  v8 = (HKEY)container::Registry::OpenKey(&v22, 131097);
  v20 = v8;
  std::wstring::~wstring(&v22);
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v22);
  v9 = (HKEY)container::Registry::OpenKey(&v22, 131097);
  v21 = v9;
  std::wstring::~wstring(&v22);
  container_version::GetOsVersion(&v29, v8, v9);
  if ( v9 )
    RegCloseKey(v9);
  if ( v8 )
    RegCloseKey(v8);
  v33 = v29;
  v34 = v30;
  std::wstring::operator=(v35, v31);
  v36 = v32;
  std::wstring::~wstring(v31);
  VirtualRootHandle = (HKEY)container::RegistryProvider::GetVirtualRootHandle(this, 1);
  v21 = VirtualRootHandle;
  v11 = (HKEY)container::RegistryProvider::GetVirtualRootHandle(this, 2);
  v20 = v11;
  container_version::GetOsVersion(&v29, VirtualRootHandle, v11);
  if ( v11 )
    RegCloseKey(v11);
  if ( VirtualRootHandle )
    RegCloseKey(VirtualRootHandle);
  v24 = v29;
  v25 = v30;
  std::wstring::operator=(&v26, v31);
  v28 = v32;
  std::wstring::~wstring(v31);
  v12 = v24;
  if ( v7 && v24 != 26100 && v24 != 29599
    || *(_DWORD *)&JobInformation.Data2 && v25 < *(_DWORD *)&JobInformation.Data2
    || *(_DWORD *)JobInformation.Data4 && v34 < *(_DWORD *)JobInformation.Data4 )
  {
    v5 = 0;
  }
  v18 = v5;
  JobInformation = 0;
  container_runtime::GetContainerIdentifier(this, 0, &JobInformation, 0, 0);
  ContainerProvider::ConvertToServerSilo::ContainerImageVersion<unsigned long &,unsigned long &,bool &,bool &,_GUID &>(
    (unsigned int)&v24,
    (unsigned int)&v25,
    (unsigned int)&v28,
    (unsigned int)&v18,
    (__int64)&JobInformation);
  if ( !v5 )
  {
    v15 = wil::verify_hresult<long>(3224830209LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x264,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime_i.cpp",
      (const char *)v15,
      (int)"Base package is incompatible with host OS",
      v17);
  }
  *(_QWORD *)&JobInformation.Data1 = a2;
  *(_QWORD *)JobInformation.Data4 = v12;
  v13 = NtSetInformationJobObject(this, (JOBOBJECTINFOCLASS)40, &JobInformation, 0x10u);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime.cpp",
      (const char *)(unsigned int)v13,
      v16);
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(&v37);
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v57,
    "BootContainer");
  v57[0] = &ContainerProvider::BootContainer::`vftable';
  ContainerProvider::BootContainer::StartActivity((ContainerProvider::BootContainer *)v57, this);
  container_runtime::LaunchSmss(this, v14);
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v57);
  v57[0] = &ContainerProvider::BootContainer::`vftable';
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v57);
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v57);
  std::wstring::~wstring(v35);
  std::wstring::~wstring(&v26);
  ContainerProvider::ConvertToServerSilo::~ConvertToServerSilo((ContainerProvider::ConvertToServerSilo *)&v37);
}

```

## disassembly

```asm
0x18000e5a0  mov     [rsp-8+arg_10], rbx
0x18000e5a5  push    rbp
0x18000e5a6  push    rsi
0x18000e5a7  push    rdi
0x18000e5a8  push    r12
0x18000e5aa  push    r13
0x18000e5ac  push    r14
0x18000e5ae  push    r15
0x18000e5b0  lea     rbp, [rsp-3A0h]
0x18000e5b8  sub     rsp, 4A0h
0x18000e5bf  mov     rax, cs:__security_cookie
0x18000e5c6  xor     rax, rsp
0x18000e5c9  mov     [rbp+3D0h+var_40], rax
0x18000e5d0  mov     r12, rdx
0x18000e5d3  mov     r14, rcx
0x18000e5d6  xor     r13d, r13d
0x18000e5d9  mov     [rbp+3D0h+var_3B8], r13d
0x18000e5dd  mov     [rbp+3D0h+var_3B4], r13b
0x18000e5e1  mov     [rbp+3D0h+var_378], r13b
0x18000e5e5  mov     [rbp+3D0h+var_390], r13d
0x18000e5e9  lea     rax, aConverttoserve; "ConvertToServerSilo"
0x18000e5f0  mov     [rbp+3D0h+var_388], rax
0x18000e5f4  mov     [rbp+3D0h+var_380], r13
0x18000e5f8  mov     [rbp+3D0h+var_370], r13d
0x18000e5fc  xorps   xmm0, xmm0
0x18000e5ff  movdqa  [rbp+3D0h+var_2D0], xmm0
0x18000e607  xor     edx, edx; Val
0x18000e609  mov     r8d, 98h; Size
0x18000e60f  lea     rcx, [rbp+3D0h+var_368]; void *
0x18000e613  call    memset_0
0x18000e618  lea     esi, [r13+1]
0x18000e61c  mov     [rbp+3D0h+var_2C0], esi
0x18000e622  xor     eax, eax
0x18000e624  mov     [rbp+3D0h+var_2B8], rax
0x18000e62b  lea     rax, [rbp+3D0h+var_3B8]
0x18000e62f  mov     [rbp+3D0h+var_2B0], rax
0x18000e636  mov     [rbp+3D0h+var_2A8], r13
0x18000e63d  mov     [rbp+3D0h+var_2A0], r13
0x18000e644  lea     rax, [rbp+3D0h+var_3C0]
0x18000e648  mov     [rbp+3D0h+var_298], rax
0x18000e64f  mov     [rbp+3D0h+var_290], r13
0x18000e656  mov     [rbp+3D0h+var_288], r13d
0x18000e65d  lea     rax, [rbp+3D0h+var_390]
0x18000e661  mov     [rbp+3D0h+var_280], rax
0x18000e668  mov     [rbp+3D0h+var_278], r13b
0x18000e66f  lea     rax, ??_7ConvertToServerSilo@ContainerProvider@@6B@; const ContainerProvider::ConvertToServerSilo::`vftable'
0x18000e676  mov     [rbp+3D0h+var_3C0], rax
0x18000e67a  mov     rdx, r14; void *
0x18000e67d  lea     rcx, [rbp+3D0h+var_3C0]; this
0x18000e681  call    ?StartActivity@ConvertToServerSilo@ContainerProvider@@QEAAXPEAX@Z; ContainerProvider::ConvertToServerSilo::StartActivity(void *)
0x18000e686  nop
0x18000e687  xorps   xmm0, xmm0
0x18000e68a  movups  [rbp+3D0h+var_450], xmm0
0x18000e68e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000e696  movdqu  [rbp+3D0h+var_440], xmm1
0x18000e69b  mov     word ptr [rbp+3D0h+var_450], r13w
0x18000e6a0  movups  [rbp+3D0h+var_3F0], xmm0
0x18000e6a4  movdqu  [rbp+3D0h+var_3E0], xmm1
0x18000e6a9  mov     word ptr [rbp+3D0h+var_3F0], r13w
0x18000e6ae  mov     qword ptr [rsp+4D0h+JobInformation], r13
0x18000e6b3  mov     [rbp+3D0h+var_120], r13
0x18000e6ba  mov     edx, 120h
0x18000e6bf  mov     [rbp+3D0h+var_118], edx
0x18000e6c5  lea     rax, aContainerminim; "ContainerMinimumLCU"
0x18000e6cc  mov     [rbp+3D0h+var_110], rax
0x18000e6d3  lea     rax, [rsp+4D0h+JobInformation+4]
0x18000e6d8  mov     [rbp+3D0h+var_108], rax
0x18000e6df  mov     ecx, 4000000h
0x18000e6e4  mov     [rbp+3D0h+var_100], ecx
0x18000e6ea  mov     [rbp+3D0h+var_F8], r13
0x18000e6f1  mov     [rbp+3D0h+var_F0], r13d
0x18000e6f8  mov     [rbp+3D0h+var_E8], r13
0x18000e6ff  mov     [rbp+3D0h+var_E0], edx
0x18000e705  lea     rax, aHostminimumlcu; "HostMinimumLCU"
0x18000e70c  mov     [rbp+3D0h+var_D8], rax
0x18000e713  lea     rax, [rsp+4D0h+JobInformation+8]
0x18000e718  mov     [rbp+3D0h+var_D0], rax
0x18000e71f  mov     [rbp+3D0h+var_C8], ecx
0x18000e725  mov     [rbp+3D0h+var_C0], r13
0x18000e72c  mov     [rbp+3D0h+var_B8], r13d
0x18000e733  mov     [rbp+3D0h+var_B0], r13
0x18000e73a  mov     [rbp+3D0h+var_A8], edx
0x18000e740  lea     rax, aSkipversionche; "SkipVersionCheck"
0x18000e747  mov     [rbp+3D0h+var_A0], rax
0x18000e74e  lea     rax, [rsp+4D0h+var_488]
0x18000e753  mov     [rbp+3D0h+var_98], rax
0x18000e75a  mov     [rbp+3D0h+var_90], ecx
0x18000e760  mov     [rbp+3D0h+var_88], r13
0x18000e767  mov     [rbp+3D0h+var_80], r13d
0x18000e76e  mov     [rbp+3D0h+var_78], r13
0x18000e775  mov     [rbp+3D0h+var_70], r13d
0x18000e77c  mov     [rbp+3D0h+var_68], r13
0x18000e783  mov     [rbp+3D0h+var_60], r13
0x18000e78a  mov     [rbp+3D0h+var_58], r13d
0x18000e791  mov     [rbp+3D0h+var_50], r13
0x18000e798  mov     [rbp+3D0h+var_48], r13d
0x18000e79f  mov     dword ptr [rsp+4D0h+JobInformation+8], r13d
0x18000e7a4  mov     dword ptr [rsp+4D0h+var_488], r13d
0x18000e7a9  mov     [rsp+4D0h+var_4B0], r13; int
0x18000e7ae  xor     r9d, r9d
0x18000e7b1  lea     r8, [rbp+3D0h+var_120]
0x18000e7b8  lea     rdx, aWindowsContain; "Windows Containers"
0x18000e7bf  lea     ecx, [rsi+1]
0x18000e7c2  call    cs:__imp_RtlQueryRegistryValuesEx
0x18000e7c9  nop     dword ptr [rax+rax+00h]
0x18000e7ce  mov     edx, 80000000h
0x18000e7d3  lea     ecx, [rax+rdx]
0x18000e7d6  test    edx, ecx
0x18000e7d8  jnz     short loc_18000E7E5
0x18000e7da  cmp     eax, 0C0000034h
0x18000e7df  jnz     loc_18000EAF5
0x18000e7e5  cmp     dword ptr [rsp+4D0h+var_488], r13d
0x18000e7ea  setz    r15b
0x18000e7ee  xorps   xmm0, xmm0
0x18000e7f1  movups  [rsp+4D0h+var_478], xmm0
0x18000e7f6  xorps   xmm1, xmm1
0x18000e7f9  movdqu  [rsp+4D0h+var_468], xmm1
0x18000e7ff  mov     r8d, 1Ah
0x18000e805  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE"
0x18000e80c  lea     rcx, [rsp+4D0h+var_478]
0x18000e811  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e816  nop
0x18000e817  mov     edi, 20019h
0x18000e81c  mov     edx, edi
0x18000e81e  lea     rcx, [rsp+4D0h+var_478]
0x18000e823  call    ?OpenKey@Registry@container@@YAPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; container::Registry::OpenKey(std::wstring const &,ulong)
0x18000e828  mov     rbx, rax
0x18000e82b  mov     [rsp+4D0h+var_488], rax
0x18000e830  lea     rcx, [rsp+4D0h+var_478]
0x18000e835  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e83a  xorps   xmm0, xmm0
0x18000e83d  movups  [rsp+4D0h+var_478], xmm0
0x18000e842  xorps   xmm1, xmm1
0x18000e845  movdqu  [rsp+4D0h+var_468], xmm1
0x18000e84b  mov     r8d, 2Ah ; '*'
0x18000e851  lea     rdx, aRegistryMachin; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x18000e858  lea     rcx, [rsp+4D0h+var_478]
0x18000e85d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000e862  nop
0x18000e863  mov     edx, edi
0x18000e865  lea     rcx, [rsp+4D0h+var_478]
0x18000e86a  call    ?OpenKey@Registry@container@@YAPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; container::Registry::OpenKey(std::wstring const &,ulong)
0x18000e86f  mov     rdi, rax
0x18000e872  mov     [rsp+4D0h+var_480], rax
0x18000e877  lea     rcx, [rsp+4D0h+var_478]
0x18000e87c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e881  mov     r8, rdi
0x18000e884  mov     rdx, rbx
0x18000e887  lea     rcx, [rbp+3D0h+var_428]
0x18000e88b  call    ?GetOsVersion@container_version@@YA?AU_OS_VERSION@1@PEAUHKEY__@@0@Z; container_version::GetOsVersion(HKEY__ *,HKEY__ *)
0x18000e890  nop
0x18000e891  test    rdi, rdi
0x18000e894  jz      short loc_18000E8A6
0x18000e896  mov     rcx, rdi; hKey
0x18000e899  call    cs:__imp_RegCloseKey
0x18000e8a0  nop     dword ptr [rax+rax+00h]
0x18000e8a5  nop
0x18000e8a6  test    rbx, rbx
0x18000e8a9  jz      short loc_18000E8BA
0x18000e8ab  mov     rcx, rbx; hKey
0x18000e8ae  call    cs:__imp_RegCloseKey
0x18000e8b5  nop     dword ptr [rax+rax+00h]
0x18000e8ba  mov     eax, [rbp+3D0h+var_428]
0x18000e8bd  mov     [rbp+3D0h+var_3F8], eax
0x18000e8c0  mov     eax, [rbp+3D0h+var_424]
0x18000e8c3  mov     [rbp+3D0h+var_3F4], eax
0x18000e8c6  lea     rdx, [rbp+3D0h+var_420]
0x18000e8ca  lea     rcx, [rbp+3D0h+var_3F0]
0x18000e8ce  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e8d3  mov     al, [rbp+3D0h+var_400]
0x18000e8d6  mov     [rbp+3D0h+var_3D0], al
0x18000e8d9  lea     rcx, [rbp+3D0h+var_420]
0x18000e8dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e8e2  mov     edx, esi
0x18000e8e4  mov     rcx, r14
0x18000e8e7  call    ?GetVirtualRootHandle@RegistryProvider@container@@YAPEAXPEAXW4_VR_ROOT_KEY@@@Z; container::RegistryProvider::GetVirtualRootHandle(void *,_VR_ROOT_KEY)
0x18000e8ec  mov     rbx, rax
0x18000e8ef  mov     [rsp+4D0h+var_480], rax
0x18000e8f4  mov     edx, 2
0x18000e8f9  mov     rcx, r14
0x18000e8fc  call    ?GetVirtualRootHandle@RegistryProvider@container@@YAPEAXPEAXW4_VR_ROOT_KEY@@@Z; container::RegistryProvider::GetVirtualRootHandle(void *,_VR_ROOT_KEY)
0x18000e901  mov     rdi, rax
0x18000e904  mov     [rsp+4D0h+var_488], rax
0x18000e909  mov     r8, rax
0x18000e90c  mov     rdx, rbx
0x18000e90f  lea     rcx, [rbp+3D0h+var_428]
0x18000e913  call    ?GetOsVersion@container_version@@YA?AU_OS_VERSION@1@PEAUHKEY__@@0@Z; container_version::GetOsVersion(HKEY__ *,HKEY__ *)
0x18000e918  nop
0x18000e919  test    rdi, rdi
0x18000e91c  jz      short loc_18000E92E
0x18000e91e  mov     rcx, rdi; hKey
0x18000e921  call    cs:__imp_RegCloseKey
0x18000e928  nop     dword ptr [rax+rax+00h]
0x18000e92d  nop
0x18000e92e  test    rbx, rbx
0x18000e931  jz      short loc_18000E942
0x18000e933  mov     rcx, rbx; hKey
0x18000e936  call    cs:__imp_RegCloseKey
0x18000e93d  nop     dword ptr [rax+rax+00h]
0x18000e942  mov     eax, [rbp+3D0h+var_428]
0x18000e945  mov     [rsp+4D0h+var_458], eax
0x18000e949  mov     eax, [rbp+3D0h+var_424]
0x18000e94c  mov     [rsp+4D0h+var_454], eax
0x18000e950  lea     rdx, [rbp+3D0h+var_420]
0x18000e954  lea     rcx, [rbp+3D0h+var_450]
0x18000e958  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000e95d  mov     al, [rbp+3D0h+var_400]
0x18000e960  mov     [rbp+3D0h+var_430], al
0x18000e963  lea     rcx, [rbp+3D0h+var_420]
0x18000e967  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e96c  mov     ebx, [rsp+4D0h+var_458]
0x18000e970  test    r15b, r15b
0x18000e973  jz      short loc_18000E985
0x18000e975  cmp     ebx, 65F4h
0x18000e97b  jz      short loc_18000E985
0x18000e97d  cmp     ebx, 739Fh
0x18000e983  jnz     short loc_18000E9A0
0x18000e985  mov     eax, dword ptr [rsp+4D0h+JobInformation+4]
0x18000e989  test    eax, eax
0x18000e98b  jz      short loc_18000E993
0x18000e98d  cmp     [rsp+4D0h+var_454], eax
0x18000e991  jb      short loc_18000E9A0
0x18000e993  mov     eax, dword ptr [rsp+4D0h+JobInformation+8]
0x18000e997  test    eax, eax
0x18000e999  jz      short loc_18000E9A3
0x18000e99b  cmp     [rbp+3D0h+var_3F4], eax
0x18000e99e  jnb     short loc_18000E9A3
0x18000e9a0  mov     sil, r13b
0x18000e9a3  mov     [rsp+4D0h+var_4A0], sil
0x18000e9a8  xorps   xmm0, xmm0
0x18000e9ab  movups  [rsp+4D0h+JobInformation], xmm0
0x18000e9b0  xor     r9d, r9d; struct _GUID *
0x18000e9b3  lea     r8, [rsp+4D0h+JobInformation]; struct _GUID *
0x18000e9b8  xor     edx, edx; void *
0x18000e9ba  mov     rcx, r14; this
0x18000e9bd  call    ?GetContainerIdentifier@container_runtime@@YAXPEAXPEAU_GUID@@1PEAK@Z; container_runtime::GetContainerIdentifier(void *,_GUID *,_GUID *,ulong *)
0x18000e9c2  lea     rax, [rsp+4D0h+JobInformation]
0x18000e9c7  mov     [rsp+4D0h+var_4B0], rax; int
0x18000e9cc  lea     r9, [rsp+4D0h+var_4A0]
0x18000e9d1  lea     r8, [rbp+3D0h+var_430]
0x18000e9d5  lea     rdx, [rsp+4D0h+var_454]
0x18000e9da  lea     rcx, [rsp+4D0h+var_458]
0x18000e9df  call    ??$ContainerImageVersion@AEAKAEAKAEA_NAEA_NAEAU_GUID@@@ConvertToServerSilo@ContainerProvider@@SAXAEAK0AEA_N1AEAU_GUID@@@Z; ContainerProvider::ConvertToServerSilo::ContainerImageVersion<ulong &,ulong &,bool &,bool &,_GUID &>(ulong &,ulong &,bool &,bool &,_GUID &)
0x18000e9e4  test    sil, sil
0x18000e9e7  jz      loc_18000EB11
0x18000e9ed  mov     dword ptr [rsp+4D0h+JobInformation+0Ch], r13d
0x18000e9f2  mov     qword ptr [rsp+4D0h+JobInformation], r12
0x18000e9f7  mov     dword ptr [rsp+4D0h+JobInformation+8], ebx
0x18000e9fb  mov     r9d, 10h; JobInformationLength
0x18000ea01  lea     r8, [rsp+4D0h+JobInformation]; JobInformation
0x18000ea06  lea     edx, [r9+18h]; JobInformationClass
0x18000ea0a  mov     rcx, r14; JobHandle
0x18000ea0d  call    cs:__imp_NtSetInformationJobObject
0x18000ea14  nop     dword ptr [rax+rax+00h]
0x18000ea19  mov     rcx, [rbp+3D8h]; this
0x18000ea20  test    eax, eax
0x18000ea22  js      loc_18000EAE0
0x18000ea28  lea     rcx, [rbp+3D0h+var_3C0]
0x18000ea2c  call    ?Stop@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000ea31  nop
0x18000ea32  lea     rdx, aBootcontainer; "BootContainer"
0x18000ea39  lea     rcx, [rbp+3D0h+var_270]
0x18000ea40  call    ??0?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ea45  lea     rbx, ??_7BootContainer@ContainerProvider@@6B@; const ContainerProvider::BootContainer::`vftable'
0x18000ea4c  mov     [rbp+3D0h+var_270], rbx
0x18000ea53  mov     rdx, r14; void *
0x18000ea56  lea     rcx, [rbp+3D0h+var_270]; this
0x18000ea5d  call    ?StartActivity@BootContainer@ContainerProvider@@QEAAXPEAX@Z; ContainerProvider::BootContainer::StartActivity(void *)
0x18000ea62  nop
0x18000ea63  mov     rcx, r14; this
0x18000ea66  call    ?LaunchSmss@container_runtime@@YAXPEAX@Z; container_runtime::LaunchSmss(void *)
0x18000ea6b  lea     rcx, [rbp+3D0h+var_270]
0x18000ea72  call    ?Stop@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000ea77  nop
0x18000ea78  mov     [rbp+3D0h+var_270], rbx
0x18000ea7f  lea     rcx, [rbp+3D0h+var_270]
0x18000ea86  call    ?Destroy@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000ea8b  lea     rcx, [rbp+3D0h+var_270]
0x18000ea92  call    ??1?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000ea97  nop
0x18000ea98  lea     rcx, [rbp+3D0h+var_3F0]
0x18000ea9c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eaa1  nop
0x18000eaa2  lea     rcx, [rbp+3D0h+var_450]
0x18000eaa6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000eaab  nop
0x18000eaac  lea     rcx, [rbp+3D0h+var_3C0]; this
0x18000eab0  call    ??1ConvertToServerSilo@ContainerProvider@@QEAA@XZ; ContainerProvider::ConvertToServerSilo::~ConvertToServerSilo(void)
0x18000eab5  mov     rcx, [rbp+3D0h+var_40]
0x18000eabc  xor     rcx, rsp; StackCookie
0x18000eabf  call    __security_check_cookie
0x18000eac4  mov     rbx, [rsp+4D0h+arg_10]
0x18000eacc  add     rsp, 4A0h
0x18000ead3  pop     r15
0x18000ead5  pop     r14
0x18000ead7  pop     r13
0x18000ead9  pop     r12
0x18000eadb  pop     rdi
0x18000eadc  pop     rsi
0x18000eadd  pop     rbp
  ... truncated ...
```
