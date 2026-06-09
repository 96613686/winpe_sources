# CCSDirectTransaction::IsPrivateFileInstalled(CApplicationAccessor const &,CComponentAccessor const &,_LUNICODE_STRING const *,bool &)

- ea: `0x1800c6584`
- end: `0x1800c693f`
- name: `?IsPrivateFileInstalled@CCSDirectTransaction@@AEAAJAEBVCApplicationAccessor@@AEBVCComponentAccessor@@PEBU_LUNICODE_STRING@@AEA_N@Z`
- size: `955`
- prototype: `int(CCSDirectTransaction *__hidden this, const struct CApplicationAccessor *, const struct CComponentAccessor *, const struct _LUNICODE_STRING *, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c2ec4`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x180018b30`
- `0x18001de74`
- `0x18001ed80`
- `0x18003f260`
- `0x180040020`
- `0x18004f2dc`
- `0x1800be2f8`
- `0x1800be69c`
- `0x1800c6584`
- `0x1800c8b40`
- `0x1800c8c08`
- `0x1800fe440`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c67a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c68c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c67a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c68c0`

## string_xrefs

- `0x1800c6750`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c6866`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c65b2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`
- `0x1800c668d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::IsPrivateFileInstalled(
        CCSDirectTransaction *this,
        const struct CApplicationAccessor *a2,
        const struct CComponentAccessor *a3,
        const struct _LUNICODE_STRING *a4,
        bool *a5)
{
  int PossiblyPendingRegistryValue; // ebx
  int v10; // eax
  int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r10
  unsigned int *v16; // r11
  signed int v17; // ecx
  __int64 v18; // r10
  unsigned int *v19; // r11
  signed int v20; // ecx
  void *v21; // rcx
  void *v22; // rcx
  unsigned __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h]
  void *lpMem; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h]
  void *v30; // [rsp+70h] [rbp-90h]
  const char *v31; // [rsp+78h] [rbp-88h] BYREF
  const char *v32; // [rsp+80h] [rbp-80h] BYREF
  const char *v33; // [rsp+88h] [rbp-78h]
  const struct _LUNICODE_STRING *v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  _QWORD v37[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-40h]
  __int128 v39; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v40; // [rsp+D8h] [rbp-28h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  _DWORD v42[4]; // [rsp+F0h] [rbp-10h] BYREF

  v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp";
  LODWORD(v34) = -1073741595;
  *(_QWORD *)&v39 = (char *)a2 + 48;
  *((_QWORD *)&v39 + 1) = (char *)a3 + 8;
  *(_QWORD *)&v40 = g_LUNICODE_STRING_Files;
  v37[1] = v42;
  v29 = 0;
  v28 = 0;
  v30 = 0;
  v42[0] = -1073741772;
  v42[1] = -1073741766;
  v42[2] = -1073741811;
  v37[0] = 3;
  v38 = 0;
  v24 = 0;
  v26 = 0;
  v25 = 0;
  lpMem = 0;
  *a5 = 0;
  if ( !a4 )
  {
    LODWORD(v33) = 1852;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v32,
      &v32);
    return (unsigned int)v34;
  }
  PossiblyPendingRegistryValue = RtlpLUnicodeStringSanitizedLength(a4, &v24);
  if ( PossiblyPendingRegistryValue >= 0 )
  {
    v10 = RtlAllocateLUnicodeString(v24, &v25);
    PossiblyPendingRegistryValue = v10;
    if ( v10 >= 0 )
    {
      PossiblyPendingRegistryValue = RtlpSanitizeLUnicodeString(1u, a4, (struct _LUNICODE_STRING *)&v25);
      if ( PossiblyPendingRegistryValue >= 0 )
      {
        PossiblyPendingRegistryValue = CCSDirectTransaction::GetPossiblyPendingRegistryValue(
                                         this,
                                         v12,
                                         &v39,
                                         3,
                                         &v25,
                                         &v28,
                                         v37);
        if ( PossiblyPendingRegistryValue >= 0 )
        {
          if ( (int)v38 >= 0 )
          {
            v14 = *((_QWORD *)this + 96);
            v24 = 0;
            v31 = 0;
            PossiblyPendingRegistryValue = RtlGetSystemIsolatedFilesystem(v13, v14, &v24);
            if ( PossiblyPendingRegistryValue < 0 )
              goto LABEL_10;
            PossiblyPendingRegistryValue = CCSDirectTransaction::GetPrivateAssemblyInstallDirectory(
                                             (__int64)this,
                                             (__int64 *)a2,
                                             *(_QWORD *)a3,
                                             &v31);
            if ( PossiblyPendingRegistryValue < 0 )
              goto LABEL_10;
            v32 = (const char *)48;
            v34 = a4;
            v41 = 0;
            v33 = v31;
            v39 = 0;
            v35 = 64;
            v40 = 0;
            v36 = 0;
            PossiblyPendingRegistryValue = RtlIsolatedFilesystemQueryAttributesFile(v24, &v32, &v39, v37);
            if ( PossiblyPendingRegistryValue < 0 )
            {
LABEL_10:
              if ( v31 )
              {
                RtlCloseIsolatedFilesystemObjectHandle(v31);
                v31 = 0;
              }
              if ( v24 )
              {
                ++g_nRtlCloseIsolatedFilesystemHandle;
                LODWORD(v34) = -1073741595;
                v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                  && (unsigned __int8)RtlIsTypeSafeHandleValid(v24) )
                {
                  (*((void (__fastcall **)(_QWORD, __int64))v16 + 4))(*v16, v15);
                  v17 = 0;
                }
                else
                {
                  LODWORD(v33) = 292;
                  Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v32);
                  v17 = (int)v34;
                }
                if ( v17 < 0 )
                  RaiseException(v17, 1u, 0, 0);
                v24 = 0;
              }
              goto LABEL_33;
            }
            if ( (int)v38 >= 0 )
              *a5 = 1;
            if ( v31 )
            {
              RtlCloseIsolatedFilesystemObjectHandle(v31);
              v31 = 0;
            }
            if ( v24 )
            {
              ++g_nRtlCloseIsolatedFilesystemHandle;
              LODWORD(v34) = -1073741595;
              v32 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v24) )
              {
                (*((void (__fastcall **)(_QWORD, __int64))v19 + 4))(*v19, v18);
                v20 = 0;
              }
              else
              {
                LODWORD(v33) = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v32);
                v20 = (int)v34;
              }
              if ( v20 < 0 )
                RaiseException(v20, 1u, 0, 0);
            }
          }
          PossiblyPendingRegistryValue = 0;
        }
      }
    }
    else
    {
      Windows::ErrorHandling::COM::ReportNtErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp",
        (const char *)0x744,
        v10,
        v11);
    }
  }
LABEL_33:
  v21 = lpMem;
  if ( lpMem )
  {
    v26 = 0;
    v25 = 0;
    lpMem = 0;
    IsolationFreeStringRoutine(v21);
  }
  v22 = v30;
  if ( v30 )
  {
    v30 = 0;
    v28 = 0;
    v29 = 0;
    IsolationFreeStringRoutine(v22);
  }
  return (unsigned int)PossiblyPendingRegistryValue;
}

```

## disassembly

```asm
0x1800c6584  push    rbp
0x1800c6586  push    rbx
0x1800c6587  push    rsi
0x1800c6588  push    rdi
0x1800c6589  push    r12
0x1800c658b  push    r13
0x1800c658d  push    r14
0x1800c658f  push    r15
0x1800c6591  lea     rbp, [rsp-18h]
0x1800c6596  sub     rsp, 118h
0x1800c659d  mov     rax, cs:__security_cookie
0x1800c65a4  xor     rax, rsp
0x1800c65a7  mov     [rbp+50h+var_50], rax
0x1800c65ab  mov     r14, [rbp+50h+arg_20]
0x1800c65b2  lea     rax, aOnecoreComNetf_124; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c65b9  xor     r13d, r13d
0x1800c65bc  mov     [rbp+50h+var_D0], rax
0x1800c65c0  mov     dword ptr [rbp+50h+var_C0], 0C00000E5h
0x1800c65c7  lea     rax, [rdx+30h]
0x1800c65cb  mov     qword ptr [rbp+50h+var_88], rax
0x1800c65cf  lea     rax, [r8+8]
0x1800c65d3  mov     qword ptr [rbp+50h+var_88+8], rax
0x1800c65d7  lea     rax, g_LUNICODE_STRING_Files
0x1800c65de  mov     qword ptr [rbp+50h+var_78], rax
0x1800c65e2  lea     rax, [rbp+50h+var_60]
0x1800c65e6  mov     [rbp+50h+var_98], rax
0x1800c65ea  mov     rdi, r9
0x1800c65ed  mov     [rsp+150h+var_E8], r13
0x1800c65f2  mov     r12, r8
0x1800c65f5  mov     [rsp+150h+var_F0], r13
0x1800c65fa  mov     r15, rdx
0x1800c65fd  mov     [rsp+150h+var_E0], r13
0x1800c6602  mov     rsi, rcx
0x1800c6605  mov     [rbp+50h+var_60], 0C0000034h
0x1800c660c  mov     [rbp+50h+var_5C], 0C000003Ah
0x1800c6613  mov     [rbp+50h+var_58], 0C000000Dh
0x1800c661a  mov     [rbp+50h+var_A0], 3
0x1800c6622  mov     [rbp+50h+var_90], r13
0x1800c6626  mov     [rsp+150h+var_110], r13
0x1800c662b  mov     [rsp+150h+var_100], r13
0x1800c6630  mov     [rsp+150h+var_108], r13
0x1800c6635  mov     [rsp+150h+lpMem], r13
0x1800c663a  mov     [r14], r13b
0x1800c663d  test    r9, r9
0x1800c6640  jnz     short loc_1800C665E
0x1800c6642  mov     dword ptr [rbp+50h+var_C8], 73Ch
0x1800c6649  lea     rdx, [rbp+50h+var_D0]
0x1800c664d  lea     rcx, [rbp+50h+var_D0]
0x1800c6651  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800c6656  mov     ebx, dword ptr [rbp+50h+var_C0]
0x1800c6659  jmp     loc_1800C6905
0x1800c665e  lea     rdx, [rsp+150h+var_110]; unsigned __int64 *
0x1800c6663  mov     rcx, rdi; struct _LUNICODE_STRING *
0x1800c6666  call    ?RtlpLUnicodeStringSanitizedLength@@YAJPEBU_LUNICODE_STRING@@PEA_K@Z; RtlpLUnicodeStringSanitizedLength(_LUNICODE_STRING const *,unsigned __int64 *)
0x1800c666b  mov     ebx, eax
0x1800c666d  test    eax, eax
0x1800c666f  js      loc_1800C68C9
0x1800c6675  mov     rcx, [rsp+150h+var_110]
0x1800c667a  lea     rdx, [rsp+150h+var_108]
0x1800c667f  call    RtlAllocateLUnicodeString
0x1800c6684  mov     ebx, eax
0x1800c6686  test    eax, eax
0x1800c6688  jns     short loc_1800C66A3
0x1800c668a  mov     r8d, eax; int
0x1800c668d  lea     rcx, aOnecoreComNetf_124; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c6694  mov     edx, 744h; char *
0x1800c6699  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x1800c669e  jmp     loc_1800C68C9
0x1800c66a3  lea     r8, [rsp+150h+var_108]; struct _LUNICODE_STRING *
0x1800c66a8  mov     rdx, rdi; struct _LUNICODE_STRING *
0x1800c66ab  mov     ecx, 1; unsigned int
0x1800c66b0  call    ?RtlpSanitizeLUnicodeString@@YAJKPEBU_LUNICODE_STRING@@PEAU1@@Z; RtlpSanitizeLUnicodeString(ulong,_LUNICODE_STRING const *,_LUNICODE_STRING *)
0x1800c66b5  mov     ebx, eax
0x1800c66b7  test    eax, eax
0x1800c66b9  js      loc_1800C68C9
0x1800c66bf  lea     rax, [rbp+50h+var_A0]
0x1800c66c3  mov     r9d, 3
0x1800c66c9  mov     [rsp+150h+var_120], rax
0x1800c66ce  lea     r8, [rbp+50h+var_88]
0x1800c66d2  lea     rax, [rsp+150h+var_F0]
0x1800c66d7  mov     rcx, rsi
0x1800c66da  mov     [rsp+150h+var_128], rax
0x1800c66df  lea     rax, [rsp+150h+var_108]
0x1800c66e4  mov     [rsp+150h+var_130], rax
0x1800c66e9  call    ?GetPossiblyPendingRegistryValue@CCSDirectTransaction@@AEAAJW4HierarchyRootKey@CPendingRegistryWrite@1@PEBQEBU_LUNICODE_STRING@@_KPEBU4@PEAU_LBLOB@@PEAU_RTL_ALTERNATE_STATUS@@@Z; CCSDirectTransaction::GetPossiblyPendingRegistryValue(CCSDirectTransaction::CPendingRegistryWrite::HierarchyRootKey,_LUNICODE_STRING const * const *,unsigned __int64,_LUNICODE_STRING const *,_LBLOB *,_RTL_ALTERNATE_STATUS *)
0x1800c66ee  mov     ebx, eax
0x1800c66f0  test    eax, eax
0x1800c66f2  js      loc_1800C68C9
0x1800c66f8  cmp     dword ptr [rbp+50h+var_90], r13d
0x1800c66fc  jl      loc_1800C68C6
0x1800c6702  mov     rdx, [rsi+300h]
0x1800c6709  lea     r8, [rsp+150h+var_110]
0x1800c670e  mov     [rsp+150h+var_110], r13
0x1800c6713  mov     [rsp+150h+var_D8], r13
0x1800c6718  call    RtlGetSystemIsolatedFilesystem
0x1800c671d  mov     ebx, eax
0x1800c671f  test    eax, eax
0x1800c6721  jns     loc_1800C67C7
0x1800c6727  mov     rcx, [rsp+150h+var_D8]
0x1800c672c  test    rcx, rcx
0x1800c672f  jz      short loc_1800C673B
0x1800c6731  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c6736  mov     [rsp+150h+var_D8], r13
0x1800c673b  mov     r10, [rsp+150h+var_110]
0x1800c6740  test    r10, r10
0x1800c6743  jz      loc_1800C68C9
0x1800c6749  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c6750  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c6757  mov     dword ptr [rbp+50h+var_C0], 0C00000E5h
0x1800c675e  mov     [rbp+50h+var_D0], rax
0x1800c6762  test    r10, r10
0x1800c6765  jz      short loc_1800C6791
0x1800c6767  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c676e  test    r11, r11
0x1800c6771  jz      short loc_1800C67B2
0x1800c6773  mov     rdx, r11
0x1800c6776  mov     rcx, r10
0x1800c6779  call    RtlIsTypeSafeHandleValid
0x1800c677e  test    al, al
0x1800c6780  jz      short loc_1800C67B2
0x1800c6782  mov     ecx, [r11]
0x1800c6785  mov     rdx, r10
0x1800c6788  mov     rax, [r11+20h]
0x1800c678c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6791  mov     ecx, r13d; dwExceptionCode
0x1800c6794  test    ecx, ecx
0x1800c6796  jns     short loc_1800C67A8
0x1800c6798  xor     r9d, r9d; lpArguments
0x1800c679b  xor     r8d, r8d; nNumberOfArguments
0x1800c679e  lea     edx, [r9+1]; dwExceptionFlags
0x1800c67a2  call    cs:__imp_RaiseException
0x1800c67a8  mov     [rsp+150h+var_110], r13
0x1800c67ad  jmp     loc_1800C68C9
0x1800c67b2  mov     dword ptr [rbp+50h+var_C8], 124h
0x1800c67b9  lea     rcx, [rbp+50h+var_D0]
0x1800c67bd  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c67c2  mov     ecx, dword ptr [rbp+50h+var_C0]
0x1800c67c5  jmp     short loc_1800C6794
0x1800c67c7  mov     r8, [r12]
0x1800c67cb  lea     r9, [rsp+150h+var_D8]
0x1800c67d0  mov     rdx, r15
0x1800c67d3  mov     rcx, rsi
0x1800c67d6  call    ?GetPrivateAssemblyInstallDirectory@CCSDirectTransaction@@AEAAJAEBVCApplicationAccessor@@U_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@AEAU_ISOLATED_FILESYSTEM_OBJECT@456@@Z; CCSDirectTransaction::GetPrivateAssemblyInstallDirectory(CApplicationAccessor const &,Windows::Isolation::Rtl::_DEFINITION_IDENTITY,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT &)
0x1800c67db  mov     ebx, eax
0x1800c67dd  test    eax, eax
0x1800c67df  js      loc_1800C6727
0x1800c67e5  mov     rcx, [rsp+150h+var_110]
0x1800c67ea  lea     r9, [rbp+50h+var_A0]
0x1800c67ee  xorps   xmm0, xmm0
0x1800c67f1  mov     [rbp+50h+var_D0], 30h ; '0'
0x1800c67f9  xor     eax, eax
0x1800c67fb  mov     [rbp+50h+var_C0], rdi
0x1800c67ff  mov     [rbp+50h+var_68], rax
0x1800c6803  lea     r8, [rbp+50h+var_88]
0x1800c6807  mov     rax, [rsp+150h+var_D8]
0x1800c680c  lea     rdx, [rbp+50h+var_D0]
0x1800c6810  mov     [rbp+50h+var_C8], rax
0x1800c6814  movups  [rbp+50h+var_88], xmm0
0x1800c6818  mov     [rbp+50h+var_B8], 40h ; '@'
0x1800c681f  movups  [rbp+50h+var_78], xmm0
0x1800c6823  movdqu  [rbp+50h+var_B0], xmm0
0x1800c6828  call    RtlIsolatedFilesystemQueryAttributesFile
0x1800c682d  mov     ebx, eax
0x1800c682f  test    eax, eax
0x1800c6831  js      loc_1800C6727
0x1800c6837  cmp     dword ptr [rbp+50h+var_90], r13d
0x1800c683b  jl      short loc_1800C6841
0x1800c683d  mov     byte ptr [r14], 1
0x1800c6841  mov     rcx, [rsp+150h+var_D8]
0x1800c6846  test    rcx, rcx
0x1800c6849  jz      short loc_1800C6855
0x1800c684b  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c6850  mov     [rsp+150h+var_D8], r13
0x1800c6855  mov     r10, [rsp+150h+var_110]
0x1800c685a  test    r10, r10
0x1800c685d  jz      short loc_1800C68C6
0x1800c685f  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c6866  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c686d  mov     dword ptr [rbp+50h+var_C0], 0C00000E5h
0x1800c6874  mov     [rbp+50h+var_D0], rax
0x1800c6878  test    r10, r10
0x1800c687b  jz      short loc_1800C68AF
0x1800c687d  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c6884  test    r11, r11
0x1800c6887  jz      loc_1800C6927
0x1800c688d  mov     rdx, r11
0x1800c6890  mov     rcx, r10
0x1800c6893  call    RtlIsTypeSafeHandleValid
0x1800c6898  test    al, al
0x1800c689a  jz      loc_1800C6927
0x1800c68a0  mov     ecx, [r11]
0x1800c68a3  mov     rdx, r10
0x1800c68a6  mov     rax, [r11+20h]
0x1800c68aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c68af  mov     ecx, r13d; dwExceptionCode
0x1800c68b2  test    ecx, ecx
0x1800c68b4  jns     short loc_1800C68C6
0x1800c68b6  xor     r9d, r9d; lpArguments
0x1800c68b9  xor     r8d, r8d; nNumberOfArguments
0x1800c68bc  lea     edx, [r9+1]; dwExceptionFlags
0x1800c68c0  call    cs:__imp_RaiseException
0x1800c68c6  mov     ebx, r13d
0x1800c68c9  mov     rcx, [rsp+150h+lpMem]; lpMem
0x1800c68ce  test    rcx, rcx
0x1800c68d1  jz      short loc_1800C68E7
0x1800c68d3  mov     [rsp+150h+var_100], r13
0x1800c68d8  mov     [rsp+150h+var_108], r13
0x1800c68dd  mov     [rsp+150h+lpMem], r13
0x1800c68e2  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c68e7  mov     rcx, [rsp+150h+var_E0]; lpMem
0x1800c68ec  test    rcx, rcx
0x1800c68ef  jz      short loc_1800C6905
0x1800c68f1  mov     [rsp+150h+var_E0], r13
0x1800c68f6  mov     [rsp+150h+var_F0], r13
0x1800c68fb  mov     [rsp+150h+var_E8], r13
0x1800c6900  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c6905  mov     eax, ebx
0x1800c6907  mov     rcx, [rbp+50h+var_50]
0x1800c690b  xor     rcx, rsp; StackCookie
0x1800c690e  call    __security_check_cookie
0x1800c6913  add     rsp, 118h
0x1800c691a  pop     r15
0x1800c691c  pop     r14
0x1800c691e  pop     r13
0x1800c6920  pop     r12
0x1800c6922  pop     rdi
0x1800c6923  pop     rsi
0x1800c6924  pop     rbx
0x1800c6925  pop     rbp
0x1800c6926  retn
0x1800c6927  mov     dword ptr [rbp+50h+var_C8], 124h
0x1800c692e  lea     rcx, [rbp+50h+var_D0]
0x1800c6932  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c6937  mov     ecx, dword ptr [rbp+50h+var_C0]
0x1800c693a  jmp     loc_1800C68B2
```
