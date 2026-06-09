# CCSDirectTransaction::IsFileInstalled(CComponentAccessor const &,_LUNICODE_STRING const *,bool &)

- ea: `0x1800c5ee0`
- end: `0x1800c6285`
- name: `?IsFileInstalled@CCSDirectTransaction@@AEAAJAEBVCComponentAccessor@@PEBU_LUNICODE_STRING@@AEA_N@Z`
- size: `933`
- prototype: `__int64 __fastcall(CCSDirectTransaction *__hidden this, const struct CComponentAccessor *, const struct _LUNICODE_STRING *, bool *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c03a8`
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
- `0x1800bdf30`
- `0x1800be2f8`
- `0x1800c5ee0`
- `0x1800c8b40`
- `0x1800c8c08`
- `0x1800fe440`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c60ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6206`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c60ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c6206`

## string_xrefs

- `0x1800c609d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c61ad`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800c5f32`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\csd_transact.cpp`

## pseudocode

```c
__int64 __fastcall CCSDirectTransaction::IsFileInstalled(
        CCSDirectTransaction *this,
        const struct CComponentAccessor *a2,
        const struct _LUNICODE_STRING *a3,
        bool *a4)
{
  int PossiblyPendingRegistryValue; // ebx
  int v9; // eax
  int v10; // r9d
  int v11; // edx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r10
  unsigned int *v15; // r11
  signed int v16; // ecx
  __int64 v17; // r10
  unsigned int *v18; // r11
  signed int v19; // ecx
  void *v20; // rcx
  void *v21; // rcx
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h]
  void *lpMem; // [rsp+58h] [rbp-A8h]
  __int128 v27; // [rsp+60h] [rbp-A0h] BYREF
  void *v28; // [rsp+70h] [rbp-90h]
  _QWORD v29[2]; // [rsp+78h] [rbp-88h] BYREF
  const char *v30; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+90h] [rbp-70h]
  const struct _LUNICODE_STRING *v32; // [rsp+98h] [rbp-68h]
  int v33; // [rsp+A0h] [rbp-60h]
  __int128 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v36; // [rsp+C8h] [rbp-38h]
  _OWORD v37[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v38; // [rsp+F0h] [rbp-10h]
  _DWORD v39[4]; // [rsp+F8h] [rbp-8h] BYREF

  LODWORD(v32) = -1073741595;
  v29[0] = (char *)a2 + 8;
  v29[1] = g_LUNICODE_STRING_Files;
  v35[1] = (__int64)v39;
  v30 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\csd_transact.cpp";
  v27 = 0u;
  v28 = 0;
  v39[0] = -1073741772;
  v39[1] = -1073741766;
  v39[2] = -1073741811;
  v35[0] = 3;
  v36 = 0;
  v23 = 0;
  v25 = 0;
  v24 = 0;
  lpMem = 0;
  *a4 = 0;
  if ( !a3 )
  {
    LODWORD(v31) = 1924;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v30,
      &v30);
    return (unsigned int)v32;
  }
  PossiblyPendingRegistryValue = RtlpLUnicodeStringSanitizedLength(a3, &v23);
  if ( PossiblyPendingRegistryValue >= 0 )
  {
    v9 = RtlAllocateLUnicodeString(v23, &v24);
    PossiblyPendingRegistryValue = v9;
    if ( v9 >= 0 )
    {
      PossiblyPendingRegistryValue = RtlpSanitizeLUnicodeString(1u, a3, (struct _LUNICODE_STRING *)&v24);
      if ( PossiblyPendingRegistryValue >= 0 )
      {
        PossiblyPendingRegistryValue = CCSDirectTransaction::GetPossiblyPendingRegistryValue(
                                         (__int64)this,
                                         v11,
                                         (__int64)v29,
                                         2u,
                                         (__int64)&v24,
                                         &v27,
                                         v35);
        if ( PossiblyPendingRegistryValue >= 0 )
        {
          if ( (int)v36 >= 0 )
          {
            v13 = *((_QWORD *)this + 96);
            v23 = 0;
            v29[0] = 0;
            PossiblyPendingRegistryValue = RtlGetSystemIsolatedFilesystem(v12, v13, &v23);
            if ( PossiblyPendingRegistryValue < 0 )
              goto LABEL_10;
            PossiblyPendingRegistryValue = CCSDirectTransaction::GetComponentDirectory(
                                             this,
                                             a2,
                                             (struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)v29);
            if ( PossiblyPendingRegistryValue < 0 )
              goto LABEL_10;
            v30 = (const char *)48;
            v32 = a3;
            v38 = 0;
            v31 = v29[0];
            memset(v37, 0, sizeof(v37));
            v33 = 64;
            v34 = 0;
            PossiblyPendingRegistryValue = RtlIsolatedFilesystemQueryAttributesFile(v23, &v30, v37, v35);
            if ( PossiblyPendingRegistryValue < 0 )
            {
LABEL_10:
              if ( v29[0] )
              {
                RtlCloseIsolatedFilesystemObjectHandle(v29[0]);
                v29[0] = 0;
              }
              if ( v23 )
              {
                ++g_nRtlCloseIsolatedFilesystemHandle;
                LODWORD(v32) = -1073741595;
                v30 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
                if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                  && (unsigned __int8)RtlIsTypeSafeHandleValid(v23) )
                {
                  (*((void (__fastcall **)(_QWORD, __int64))v15 + 4))(*v15, v14);
                  v16 = 0;
                }
                else
                {
                  LODWORD(v31) = 292;
                  Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v30);
                  v16 = (int)v32;
                }
                if ( v16 < 0 )
                  RaiseException(v16, 1u, 0, 0);
                v23 = 0;
              }
              goto LABEL_33;
            }
            if ( (int)v36 >= 0 )
              *a4 = 1;
            if ( v29[0] )
            {
              RtlCloseIsolatedFilesystemObjectHandle(v29[0]);
              v29[0] = 0;
            }
            if ( v23 )
            {
              ++g_nRtlCloseIsolatedFilesystemHandle;
              LODWORD(v32) = -1073741595;
              v30 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v23) )
              {
                (*((void (__fastcall **)(_QWORD, __int64))v18 + 4))(*v18, v17);
                v19 = 0;
              }
              else
              {
                LODWORD(v31) = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v30);
                v19 = (int)v32;
              }
              if ( v19 < 0 )
                RaiseException(v19, 1u, 0, 0);
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
        (const char *)0x78C,
        v9,
        v10);
    }
  }
LABEL_33:
  v20 = lpMem;
  if ( lpMem )
  {
    v25 = 0;
    v24 = 0;
    lpMem = 0;
    IsolationFreeStringRoutine(v20);
  }
  v21 = v28;
  if ( v28 )
  {
    v28 = 0;
    v27 = 0u;
    IsolationFreeStringRoutine(v21);
  }
  return (unsigned int)PossiblyPendingRegistryValue;
}

```

## disassembly

```asm
0x1800c5ee0  push    rbp
0x1800c5ee2  push    rbx
0x1800c5ee3  push    rsi
0x1800c5ee4  push    rdi
0x1800c5ee5  push    r12
0x1800c5ee7  push    r13
0x1800c5ee9  push    r14
0x1800c5eeb  push    r15
0x1800c5eed  lea     rbp, [rsp-18h]
0x1800c5ef2  sub     rsp, 118h
0x1800c5ef9  mov     rax, cs:__security_cookie
0x1800c5f00  xor     rax, rsp
0x1800c5f03  mov     [rbp+50h+var_48], rax
0x1800c5f07  xor     r12d, r12d
0x1800c5f0a  mov     dword ptr [rbp+50h+var_B8], 0C00000E5h
0x1800c5f11  mov     [rsp+150h+var_E8], r12
0x1800c5f16  lea     rax, [rdx+8]
0x1800c5f1a  mov     [rsp+150h+var_D8], rax
0x1800c5f1f  lea     rax, g_LUNICODE_STRING_Files
0x1800c5f26  mov     [rbp+50h+var_D0], rax
0x1800c5f2a  lea     rax, [rbp+50h+var_58]
0x1800c5f2e  mov     [rbp+50h+var_90], rax
0x1800c5f32  lea     r13, aOnecoreComNetf_124; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c5f39  mov     [rbp+50h+var_C8], r13
0x1800c5f3d  mov     r14, r9
0x1800c5f40  mov     [rsp+150h+var_F0], r12
0x1800c5f45  mov     rsi, r8
0x1800c5f48  mov     [rsp+150h+var_E0], r12
0x1800c5f4d  mov     r15, rdx
0x1800c5f50  mov     [rbp+50h+var_58], 0C0000034h
0x1800c5f57  mov     rdi, rcx
0x1800c5f5a  mov     [rbp+50h+var_54], 0C000003Ah
0x1800c5f61  mov     [rbp+50h+var_50], 0C000000Dh
0x1800c5f68  mov     [rbp+50h+var_98], 3
0x1800c5f70  mov     [rbp+50h+var_88], r12
0x1800c5f74  mov     [rsp+150h+var_110], r12
0x1800c5f79  mov     [rsp+150h+var_100], r12
0x1800c5f7e  mov     [rsp+150h+var_108], r12
0x1800c5f83  mov     [rsp+150h+lpMem], r12
0x1800c5f88  mov     [r9], r12b
0x1800c5f8b  test    r8, r8
0x1800c5f8e  jnz     short loc_1800C5FAC
0x1800c5f90  mov     dword ptr [rbp+50h+var_C0], 784h
0x1800c5f97  lea     rdx, [rbp+50h+var_C8]
0x1800c5f9b  lea     rcx, [rbp+50h+var_C8]
0x1800c5f9f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800c5fa4  mov     ebx, dword ptr [rbp+50h+var_B8]
0x1800c5fa7  jmp     loc_1800C624B
0x1800c5fac  lea     rdx, [rsp+150h+var_110]; unsigned __int64 *
0x1800c5fb1  mov     rcx, rsi; struct _LUNICODE_STRING *
0x1800c5fb4  call    ?RtlpLUnicodeStringSanitizedLength@@YAJPEBU_LUNICODE_STRING@@PEA_K@Z; RtlpLUnicodeStringSanitizedLength(_LUNICODE_STRING const *,unsigned __int64 *)
0x1800c5fb9  mov     ebx, eax
0x1800c5fbb  test    eax, eax
0x1800c5fbd  js      loc_1800C620F
0x1800c5fc3  mov     rcx, [rsp+150h+var_110]
0x1800c5fc8  lea     rdx, [rsp+150h+var_108]
0x1800c5fcd  call    RtlAllocateLUnicodeString
0x1800c5fd2  mov     ebx, eax
0x1800c5fd4  test    eax, eax
0x1800c5fd6  jns     short loc_1800C5FED
0x1800c5fd8  mov     r8d, eax; int
0x1800c5fdb  mov     edx, 78Ch; char *
0x1800c5fe0  mov     rcx, r13; this
0x1800c5fe3  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x1800c5fe8  jmp     loc_1800C620F
0x1800c5fed  mov     r13d, 1
0x1800c5ff3  lea     r8, [rsp+150h+var_108]; struct _LUNICODE_STRING *
0x1800c5ff8  mov     ecx, r13d; unsigned int
0x1800c5ffb  mov     rdx, rsi; struct _LUNICODE_STRING *
0x1800c5ffe  call    ?RtlpSanitizeLUnicodeString@@YAJKPEBU_LUNICODE_STRING@@PEAU1@@Z; RtlpSanitizeLUnicodeString(ulong,_LUNICODE_STRING const *,_LUNICODE_STRING *)
0x1800c6003  mov     ebx, eax
0x1800c6005  test    eax, eax
0x1800c6007  js      loc_1800C620F
0x1800c600d  lea     rax, [rbp+50h+var_98]
0x1800c6011  mov     rcx, rdi
0x1800c6014  mov     [rsp+150h+var_120], rax
0x1800c6019  lea     r9d, [r13+1]
0x1800c601d  lea     rax, [rsp+150h+var_F0]
0x1800c6022  mov     [rsp+150h+var_128], rax
0x1800c6027  lea     r8, [rsp+150h+var_D8]
0x1800c602c  lea     rax, [rsp+150h+var_108]
0x1800c6031  mov     [rsp+150h+var_130], rax
0x1800c6036  call    ?GetPossiblyPendingRegistryValue@CCSDirectTransaction@@AEAAJW4HierarchyRootKey@CPendingRegistryWrite@1@PEBQEBU_LUNICODE_STRING@@_KPEBU4@PEAU_LBLOB@@PEAU_RTL_ALTERNATE_STATUS@@@Z; CCSDirectTransaction::GetPossiblyPendingRegistryValue(CCSDirectTransaction::CPendingRegistryWrite::HierarchyRootKey,_LUNICODE_STRING const * const *,unsigned __int64,_LUNICODE_STRING const *,_LBLOB *,_RTL_ALTERNATE_STATUS *)
0x1800c603b  mov     ebx, eax
0x1800c603d  test    eax, eax
0x1800c603f  js      loc_1800C620F
0x1800c6045  cmp     dword ptr [rbp+50h+var_88], r12d
0x1800c6049  jl      loc_1800C620C
0x1800c604f  mov     rdx, [rdi+300h]
0x1800c6056  lea     r8, [rsp+150h+var_110]
0x1800c605b  mov     [rsp+150h+var_110], r12
0x1800c6060  mov     [rsp+150h+var_D8], r12
0x1800c6065  call    RtlGetSystemIsolatedFilesystem
0x1800c606a  mov     ebx, eax
0x1800c606c  test    eax, eax
0x1800c606e  jns     loc_1800C6113
0x1800c6074  mov     rcx, [rsp+150h+var_D8]
0x1800c6079  test    rcx, rcx
0x1800c607c  jz      short loc_1800C6088
0x1800c607e  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c6083  mov     [rsp+150h+var_D8], r12
0x1800c6088  mov     r10, [rsp+150h+var_110]
0x1800c608d  test    r10, r10
0x1800c6090  jz      loc_1800C620F
0x1800c6096  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, r13; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c609d  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c60a4  mov     dword ptr [rbp+50h+var_B8], 0C00000E5h
0x1800c60ab  mov     [rbp+50h+var_C8], rax
0x1800c60af  test    r10, r10
0x1800c60b2  jz      short loc_1800C60DE
0x1800c60b4  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c60bb  test    r11, r11
0x1800c60be  jz      short loc_1800C60FE
0x1800c60c0  mov     rdx, r11
0x1800c60c3  mov     rcx, r10
0x1800c60c6  call    RtlIsTypeSafeHandleValid
0x1800c60cb  test    al, al
0x1800c60cd  jz      short loc_1800C60FE
0x1800c60cf  mov     ecx, [r11]
0x1800c60d2  mov     rdx, r10
0x1800c60d5  mov     rax, [r11+20h]
0x1800c60d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c60de  mov     ecx, r12d; dwExceptionCode
0x1800c60e1  test    ecx, ecx
0x1800c60e3  jns     short loc_1800C60F4
0x1800c60e5  xor     r9d, r9d; lpArguments
0x1800c60e8  xor     r8d, r8d; nNumberOfArguments
0x1800c60eb  mov     edx, r13d; dwExceptionFlags
0x1800c60ee  call    cs:__imp_RaiseException
0x1800c60f4  mov     [rsp+150h+var_110], r12
0x1800c60f9  jmp     loc_1800C620F
0x1800c60fe  mov     dword ptr [rbp+50h+var_C0], 124h
0x1800c6105  lea     rcx, [rbp+50h+var_C8]
0x1800c6109  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c610e  mov     ecx, dword ptr [rbp+50h+var_B8]
0x1800c6111  jmp     short loc_1800C60E1
0x1800c6113  lea     r8, [rsp+150h+var_D8]; struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *
0x1800c6118  mov     rdx, r15; struct CComponentAccessor *
0x1800c611b  mov     rcx, rdi; this
0x1800c611e  call    ?GetComponentDirectory@CCSDirectTransaction@@AEAAJAEBVCComponentAccessor@@AEAU_ISOLATED_FILESYSTEM_OBJECT@Rtl@Isolation@Windows@@@Z; CCSDirectTransaction::GetComponentDirectory(CComponentAccessor const &,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT &)
0x1800c6123  mov     ebx, eax
0x1800c6125  test    eax, eax
0x1800c6127  js      loc_1800C6074
0x1800c612d  mov     rcx, [rsp+150h+var_110]
0x1800c6132  lea     r9, [rbp+50h+var_98]
0x1800c6136  xorps   xmm0, xmm0
0x1800c6139  mov     [rbp+50h+var_C8], 30h ; '0'
0x1800c6141  xor     eax, eax
0x1800c6143  mov     [rbp+50h+var_B8], rsi
0x1800c6147  mov     [rbp+50h+var_60], rax
0x1800c614b  lea     r8, [rbp+50h+var_80]
0x1800c614f  mov     rax, [rsp+150h+var_D8]
0x1800c6154  lea     rdx, [rbp+50h+var_C8]
0x1800c6158  mov     [rbp+50h+var_C0], rax
0x1800c615c  movups  [rbp+50h+var_80], xmm0
0x1800c6160  mov     [rbp+50h+var_B0], 40h ; '@'
0x1800c6167  movups  [rbp+50h+var_70], xmm0
0x1800c616b  movdqu  [rbp+50h+var_A8], xmm0
0x1800c6170  call    RtlIsolatedFilesystemQueryAttributesFile
0x1800c6175  mov     ebx, eax
0x1800c6177  test    eax, eax
0x1800c6179  js      loc_1800C6074
0x1800c617f  cmp     dword ptr [rbp+50h+var_88], r12d
0x1800c6183  jl      short loc_1800C6188
0x1800c6185  mov     [r14], r13b
0x1800c6188  mov     rcx, [rsp+150h+var_D8]
0x1800c618d  test    rcx, rcx
0x1800c6190  jz      short loc_1800C619C
0x1800c6192  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800c6197  mov     [rsp+150h+var_D8], r12
0x1800c619c  mov     r10, [rsp+150h+var_110]
0x1800c61a1  test    r10, r10
0x1800c61a4  jz      short loc_1800C620C
0x1800c61a6  add     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA, r13; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800c61ad  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800c61b4  mov     dword ptr [rbp+50h+var_B8], 0C00000E5h
0x1800c61bb  mov     [rbp+50h+var_C8], rax
0x1800c61bf  test    r10, r10
0x1800c61c2  jz      short loc_1800C61F6
0x1800c61c4  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800c61cb  test    r11, r11
0x1800c61ce  jz      loc_1800C626D
0x1800c61d4  mov     rdx, r11
0x1800c61d7  mov     rcx, r10
0x1800c61da  call    RtlIsTypeSafeHandleValid
0x1800c61df  test    al, al
0x1800c61e1  jz      loc_1800C626D
0x1800c61e7  mov     ecx, [r11]
0x1800c61ea  mov     rdx, r10
0x1800c61ed  mov     rax, [r11+20h]
0x1800c61f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c61f6  mov     ecx, r12d; dwExceptionCode
0x1800c61f9  test    ecx, ecx
0x1800c61fb  jns     short loc_1800C620C
0x1800c61fd  xor     r9d, r9d; lpArguments
0x1800c6200  xor     r8d, r8d; nNumberOfArguments
0x1800c6203  mov     edx, r13d; dwExceptionFlags
0x1800c6206  call    cs:__imp_RaiseException
0x1800c620c  mov     ebx, r12d
0x1800c620f  mov     rcx, [rsp+150h+lpMem]; lpMem
0x1800c6214  test    rcx, rcx
0x1800c6217  jz      short loc_1800C622D
0x1800c6219  mov     [rsp+150h+var_100], r12
0x1800c621e  mov     [rsp+150h+var_108], r12
0x1800c6223  mov     [rsp+150h+lpMem], r12
0x1800c6228  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c622d  mov     rcx, [rsp+150h+var_E0]; lpMem
0x1800c6232  test    rcx, rcx
0x1800c6235  jz      short loc_1800C624B
0x1800c6237  mov     [rsp+150h+var_E0], r12
0x1800c623c  mov     [rsp+150h+var_F0], r12
0x1800c6241  mov     [rsp+150h+var_E8], r12
0x1800c6246  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800c624b  mov     eax, ebx
0x1800c624d  mov     rcx, [rbp+50h+var_48]
0x1800c6251  xor     rcx, rsp; StackCookie
0x1800c6254  call    __security_check_cookie
0x1800c6259  add     rsp, 118h
0x1800c6260  pop     r15
0x1800c6262  pop     r14
0x1800c6264  pop     r13
0x1800c6266  pop     r12
0x1800c6268  pop     rdi
0x1800c6269  pop     rsi
0x1800c626a  pop     rbx
0x1800c626b  pop     rbp
0x1800c626c  retn
0x1800c626d  mov     dword ptr [rbp+50h+var_C0], 124h
0x1800c6274  lea     rcx, [rbp+50h+var_C8]
0x1800c6278  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800c627d  mov     ecx, dword ptr [rbp+50h+var_B8]
0x1800c6280  jmp     loc_1800C61F9
```
