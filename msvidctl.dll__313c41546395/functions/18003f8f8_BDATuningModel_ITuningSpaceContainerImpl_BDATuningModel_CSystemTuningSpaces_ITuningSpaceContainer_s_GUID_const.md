# BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::Init(WTL::CString &)

- ea: `0x18003f8f8`
- end: `0x18003fba3`
- name: `?Init@?$ITuningSpaceContainerImpl@VCSystemTuningSpaces@BDATuningModel@@UITuningSpaceContainer@@$1?_GUID_5b692e84_e2f1_11d2_9493_00c04f72d980@@3U__s_GUID@@B$1?LIBID_TunerLib@@3U_GUID@@B@BDATuningModel@@QEAAJAEAVCString@WTL@@@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003cff8`

## callees

- `0x180004640`
- `0x18000c4f8`
- `0x18000df18`
- `0x18000e1b8`
- `0x18001d270`
- `0x1800395f8`
- `0x18003acc0`
- `0x18003f8f8`
- `0x18003fbac`
- `0x180040e44`
- `0x1800456f8`
- `0x1800eda14`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x18003fa7a`
- `KERNEL32!CreateMutexW` at `0x18003fa7a`
- `KERNEL32!LocalFree` at `0x18003f9e8`
- `KERNEL32!LocalFree` at `0x18003f9e8`
- `KERNEL32!CreateMutexExW` at `0x18003fa6b`
- `KERNEL32!CreateMutexExW` at `0x18003fa6b`
- `KERNEL32!GetLastError` at `0x18003fa8d`
- `KERNEL32!GetLastError` at `0x18003fb2c`
- `KERNEL32!GetLastError` at `0x18003fa8d`
- `KERNEL32!GetLastError` at `0x18003fb2c`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003f9bb`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003f9bb`

## string_xrefs

- `0x18003f9fe`: `setdacl attach gle=%08x`
- `0x18003fb37`: `convertStringDescriptor failed=%lx`
- `0x18003fa98`: `createmut gle=%lx`
- `0x18003fb1e`: `LoadCache failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::Init(
        __int64 a1,
        __int64 a2)
{
  int v4; // eax
  const char *v5; // rdx
  CVidCtlTrace *v6; // rcx
  unsigned int v7; // edi
  char IsEnabled; // al
  const WCHAR *v9; // rcx
  int v10; // ebx
  const char *v11; // rdx
  CVidCtlTrace *v12; // rcx
  HANDLE v13; // rax
  signed int LastError; // ebx
  const char *v15; // rdx
  CVidCtlTrace *v16; // rcx
  unsigned int v17; // r8d
  const unsigned __int16 *v18; // r9
  signed int Cache; // ebx
  const char *v21; // rdx
  CVidCtlTrace *v22; // rcx
  const char *v23; // rdx
  CVidCtlTrace *v24; // rcx
  char **v25; // [rsp+38h] [rbp-C8h]
  LPCWSTR lpName; // [rsp+40h] [rbp-C0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+50h] [rbp-B0h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v30[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  char v32[256]; // [rsp+A0h] [rbp-60h] BYREF
  char v33[256]; // [rsp+1A0h] [rbp+A0h] BYREF

  WTL::CString::CString((WTL::CString *)&lpName, L"Global\\{801461B2-33BD-11d3-B64C-00C04F79498E}.MTX");
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  v4 = ATL::CSecurityDescriptor::Initialize((ATL::CSecurityDescriptor *)v30);
  v7 = v4;
  if ( v4 < 0 )
  {
    CVidCtlTrace::TraceIfFailedHResult(v6, v5, "ds.Initialize failed", v4);
LABEL_16:
    ATL::CSecurityDescriptor::~CSecurityDescriptor((ATL::CSecurityDescriptor *)v30);
    WTL::CString::~CString((WTL::CString *)&lpName);
    return v7;
  }
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::GetImpl'::`2'::impl);
  v9 = L"D:(A;;0x00100001;;;BU)(A;;GA;;;BA)(A;;GA;;;SY)";
  if ( !IsEnabled )
    v9 = L"D:(A;;GR;;;BU)(A;;GA;;;BA)(A;;GA;;;SY)";
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v9, 1u, &SecurityDescriptor, &SecurityDescriptorSize)
    && SecurityDescriptor )
  {
    v10 = ATL::CSecurityDescriptor::Attach((PACL *)v30, SecurityDescriptor);
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
    if ( v10 < 0 )
    {
      StringCchPrintfA(v33, 0x100u, "setdacl attach gle=%08x", v10);
      CVidCtlTrace::TraceIfFailedHResult(v12, v11, v33, v7);
      v7 = v10;
      goto LABEL_16;
    }
    *(_QWORD *)&MutexAttributes.nLength = 24;
    *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
    MutexAttributes.lpSecurityDescriptor = *(LPVOID *)&v30[0];
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::GetImpl'::`2'::impl) )
      v13 = CreateMutexExW(&MutexAttributes, lpName, 0, 0x100001u);
    else
      v13 = CreateMutexW(&MutexAttributes, 0, lpName);
    *(_QWORD *)(a1 + 32) = v13;
    if ( !v13 )
    {
      LastError = GetLastError();
      StringCchPrintfA(v32, 0x100u, "createmut gle=%lx", LastError);
      CVidCtlTrace::TraceIfFailedHResult(v16, v15, v32, v7);
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = ATL::AtlSetErrorInfo2(
             &GUID_d02aac50_027e_11d3_9d8e_00c04f72d980,
             0xC0040532,
             v17,
             v18,
             &GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,
             LastError,
             hInstance,
             v25);
      goto LABEL_16;
    }
    Cache = BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::LoadCache(
              a1,
              a2);
    CVidCtlTrace::TraceIfFailedHResult(v22, v21, "LoadCache failed", Cache);
  }
  else
  {
    Cache = GetLastError();
    StringCchPrintfA(v32, 0x100u, "convertStringDescriptor failed=%lx", Cache);
    CVidCtlTrace::TraceIfFailedHResult(v24, v23, v32, v7);
    if ( Cache > 0 )
      Cache = (unsigned __int16)Cache | 0x80070000;
  }
  ATL::CSecurityDescriptor::~CSecurityDescriptor((ATL::CSecurityDescriptor *)v30);
  WTL::CString::~CString((WTL::CString *)&lpName);
  return (unsigned int)Cache;
}

```

## disassembly

```asm
0x18003f8f8  mov     [rsp-8+arg_10], rbx
0x18003f8fd  mov     [rsp-8+arg_18], rsi
0x18003f902  push    rbp
0x18003f903  push    rdi
0x18003f904  push    r14
0x18003f906  lea     rbp, [rsp-1B0h]
0x18003f90e  sub     rsp, 2B0h
0x18003f915  mov     rax, cs:__security_cookie
0x18003f91c  xor     rax, rsp
0x18003f91f  mov     [rbp+1C0h+var_20], rax
0x18003f926  mov     r14, rdx
0x18003f929  mov     rsi, rcx
0x18003f92c  lea     rdx, ?STR_MUTNAME@@3QBGB; "Global\\{801461B2-33BD-11d3-B64C-00C04F"...
0x18003f933  lea     rcx, [rsp+2C0h+lpName]; this
0x18003f938  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x18003f93d  nop
0x18003f93e  xorps   xmm0, xmm0
0x18003f941  movdqu  [rsp+2C0h+var_250], xmm0
0x18003f947  xorps   xmm1, xmm1
0x18003f94a  movdqu  [rbp+1C0h+var_240], xmm1
0x18003f94f  mov     [rbp+1C0h+var_230], 0
0x18003f957  lea     rcx, [rsp+2C0h+var_250]; this
0x18003f95c  call    ?Initialize@CSecurityDescriptor@ATL@@QEAAJXZ; ATL::CSecurityDescriptor::Initialize(void)
0x18003f961  mov     edi, eax
0x18003f963  test    eax, eax
0x18003f965  jns     short loc_18003F97B
0x18003f967  mov     r9d, eax; int
0x18003f96a  lea     r8, aDsInitializeFa; "ds.Initialize failed"
0x18003f971  call    ?TraceIfFailedHResult@CVidCtlTrace@@QEAAJPEBD0J@Z; CVidCtlTrace::TraceIfFailedHResult(char const *,char const *,long)
0x18003f976  jmp     loc_18003FAF5
0x18003f97b  mov     [rsp+2C0h+SecurityDescriptor], 0
0x18003f984  mov     [rsp+2C0h+SecurityDescriptorSize], 0
0x18003f98c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::GetImpl(void)'::`2'::impl
0x18003f993  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::__private_IsEnabled(void)
0x18003f998  lea     rdx, StringSecurityDescriptor; "D:(A;;GR;;;BU)(A;;GA;;;BA)(A;;GA;;;SY)"
0x18003f99f  lea     rcx, aDA0x00100001Bu; "D:(A;;0x00100001;;;BU)(A;;GA;;;BA)(A;;G"...
0x18003f9a6  test    al, al
0x18003f9a8  cmovz   rcx, rdx; StringSecurityDescriptor
0x18003f9ac  lea     r9, [rsp+2C0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18003f9b1  lea     r8, [rsp+2C0h+SecurityDescriptor]; SecurityDescriptor
0x18003f9b6  mov     edx, 1; StringSDRevision
0x18003f9bb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003f9c1  test    eax, eax
0x18003f9c3  jz      loc_18003FB2C
0x18003f9c9  mov     rdx, [rsp+2C0h+SecurityDescriptor]; pSecurityDescriptor
0x18003f9ce  test    rdx, rdx
0x18003f9d1  jz      loc_18003FB2C
0x18003f9d7  lea     rcx, [rsp+2C0h+var_250]; this
0x18003f9dc  call    ?Attach@CSecurityDescriptor@ATL@@QEAAJPEAX@Z; ATL::CSecurityDescriptor::Attach(void *)
0x18003f9e1  mov     ebx, eax
0x18003f9e3  mov     rcx, [rsp+2C0h+SecurityDescriptor]; hMem
0x18003f9e8  call    cs:__imp_LocalFree
0x18003f9ee  mov     [rsp+2C0h+SecurityDescriptor], 0
0x18003f9f7  test    ebx, ebx
0x18003f9f9  jns     short loc_18003FA2C
0x18003f9fb  mov     r9d, ebx
0x18003f9fe  lea     r8, aSetdaclAttachG; "setdacl attach gle=%08x"
0x18003fa05  mov     edx, 100h; unsigned __int64
0x18003fa0a  lea     rcx, [rbp+1C0h+var_120]; char *
0x18003fa11  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18003fa16  mov     r9d, edi; int
0x18003fa19  lea     r8, [rbp+1C0h+var_120]; char *
0x18003fa20  call    ?TraceIfFailedHResult@CVidCtlTrace@@QEAAJPEBD0J@Z; CVidCtlTrace::TraceIfFailedHResult(char const *,char const *,long)
0x18003fa25  mov     edi, ebx
0x18003fa27  jmp     loc_18003FAF5
0x18003fa2c  mov     qword ptr [rsp+2C0h+MutexAttributes.nLength], 18h
0x18003fa35  mov     qword ptr [rsp+2C0h+MutexAttributes.bInheritHandle], 0
0x18003fa3e  mov     rax, qword ptr [rsp+2C0h+var_250]
0x18003fa43  mov     [rsp+2C0h+MutexAttributes.lpSecurityDescriptor], rax
0x18003fa48  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::GetImpl(void)'::`2'::impl
0x18003fa4f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VidCtlMutexDacl>::__private_IsEnabled(void)
0x18003fa54  lea     rcx, [rsp+2C0h+MutexAttributes]; lpMutexAttributes
0x18003fa59  test    al, al
0x18003fa5b  jz      short loc_18003FA73
0x18003fa5d  mov     r9d, 100001h; dwDesiredAccess
0x18003fa63  xor     r8d, r8d; dwFlags
0x18003fa66  mov     rdx, [rsp+2C0h+lpName]; lpName
0x18003fa6b  call    cs:__imp_CreateMutexExW
0x18003fa71  jmp     short loc_18003FA80
0x18003fa73  mov     r8, [rsp+2C0h+lpName]; lpName
0x18003fa78  xor     edx, edx; bInitialOwner
0x18003fa7a  call    cs:__imp_CreateMutexW
0x18003fa80  mov     [rsi+20h], rax
0x18003fa84  test    rax, rax
0x18003fa87  jnz     loc_18003FB0E
0x18003fa8d  call    cs:__imp_GetLastError
0x18003fa93  mov     ebx, eax
0x18003fa95  mov     r9d, eax
0x18003fa98  lea     r8, aCreatemutGleLx; "createmut gle=%lx"
0x18003fa9f  mov     edx, 100h; unsigned __int64
0x18003faa4  lea     rcx, [rbp+1C0h+var_220]; char *
0x18003faa8  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18003faad  mov     r9d, edi; int
0x18003fab0  lea     r8, [rbp+1C0h+var_220]; char *
0x18003fab4  call    ?TraceIfFailedHResult@CVidCtlTrace@@QEAAJPEBD0J@Z; CVidCtlTrace::TraceIfFailedHResult(char const *,char const *,long)
0x18003fab9  mov     rax, cs:hInstance
0x18003fac0  test    ebx, ebx
0x18003fac2  jle     short loc_18003FACD
0x18003fac4  movzx   ebx, bx
0x18003fac7  or      ebx, 80070000h
0x18003facd  mov     [rsp+2C0h+var_290], rax; HINSTANCE
0x18003fad2  mov     [rsp+2C0h+var_298], ebx; int
0x18003fad6  lea     rax, _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980
0x18003fadd  mov     [rsp+2C0h+var_2A0], rax; struct _GUID *
0x18003fae2  mov     edx, 0C0040532h; dwMessageId
0x18003fae7  lea     rcx, _GUID_d02aac50_027e_11d3_9d8e_00c04f72d980; clsid
0x18003faee  call    ?AtlSetErrorInfo2@ATL@@YAJAEBU_GUID@@IKPEBG0JPEAUHINSTANCE__@@PEAPEAD@Z; ATL::AtlSetErrorInfo2(_GUID const &,uint,ulong,ushort const *,_GUID const &,long,HINSTANCE__ *,char * *)
0x18003faf3  mov     edi, eax
0x18003faf5  lea     rcx, [rsp+2C0h+var_250]; this
0x18003fafa  call    ??1CSecurityDescriptor@ATL@@QEAA@XZ; ATL::CSecurityDescriptor::~CSecurityDescriptor(void)
0x18003faff  nop
0x18003fb00  lea     rcx, [rsp+2C0h+lpName]; this
0x18003fb05  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18003fb0a  mov     eax, edi
0x18003fb0c  jmp     short loc_18003FB7C
0x18003fb0e  mov     rdx, r14
0x18003fb11  mov     rcx, rsi
0x18003fb14  call    ?LoadCache@?$ITuningSpaceContainerImpl@VCSystemTuningSpaces@BDATuningModel@@UITuningSpaceContainer@@$1?_GUID_5b692e84_e2f1_11d2_9493_00c04f72d980@@3U__s_GUID@@B$1?LIBID_TunerLib@@3U_GUID@@B@BDATuningModel@@QEAAJAEAVCString@WTL@@@Z; BDATuningModel::ITuningSpaceContainerImpl<BDATuningModel::CSystemTuningSpaces,ITuningSpaceContainer,&__s_GUID const _GUID_5b692e84_e2f1_11d2_9493_00c04f72d980,&_GUID const LIBID_TunerLib>::LoadCache(WTL::CString &)
0x18003fb19  mov     ebx, eax
0x18003fb1b  mov     r9d, eax; int
0x18003fb1e  lea     r8, aLoadcacheFaile; "LoadCache failed"
0x18003fb25  call    ?TraceIfFailedHResult@CVidCtlTrace@@QEAAJPEBD0J@Z; CVidCtlTrace::TraceIfFailedHResult(char const *,char const *,long)
0x18003fb2a  jmp     short loc_18003FB65
0x18003fb2c  call    cs:__imp_GetLastError
0x18003fb32  mov     ebx, eax
0x18003fb34  mov     r9d, eax
0x18003fb37  lea     r8, aConvertstringd; "convertStringDescriptor failed=%lx"
0x18003fb3e  mov     edx, 100h; unsigned __int64
0x18003fb43  lea     rcx, [rbp+1C0h+var_220]; char *
0x18003fb47  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18003fb4c  mov     r9d, edi; int
0x18003fb4f  lea     r8, [rbp+1C0h+var_220]; char *
0x18003fb53  call    ?TraceIfFailedHResult@CVidCtlTrace@@QEAAJPEBD0J@Z; CVidCtlTrace::TraceIfFailedHResult(char const *,char const *,long)
0x18003fb58  test    ebx, ebx
0x18003fb5a  jle     short loc_18003FB65
0x18003fb5c  movzx   ebx, bx
0x18003fb5f  or      ebx, 80070000h
0x18003fb65  lea     rcx, [rsp+2C0h+var_250]; this
0x18003fb6a  call    ??1CSecurityDescriptor@ATL@@QEAA@XZ; ATL::CSecurityDescriptor::~CSecurityDescriptor(void)
0x18003fb6f  nop
0x18003fb70  lea     rcx, [rsp+2C0h+lpName]; this
0x18003fb75  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x18003fb7a  mov     eax, ebx
0x18003fb7c  mov     rcx, [rbp+1C0h+var_20]
0x18003fb83  xor     rcx, rsp; StackCookie
0x18003fb86  call    __security_check_cookie
0x18003fb8b  lea     r11, [rsp+2C0h+var_10]
0x18003fb93  mov     rbx, [r11+30h]
0x18003fb97  mov     rsi, [r11+38h]
0x18003fb9b  mov     rsp, r11
0x18003fb9e  pop     r14
0x18003fba0  pop     rdi
0x18003fba1  pop     rbp
0x18003fba2  retn
```
