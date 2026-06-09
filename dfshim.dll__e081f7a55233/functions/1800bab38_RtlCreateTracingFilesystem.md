# RtlCreateTracingFilesystem

- ea: `0x1800bab38`
- end: `0x1800bae09`
- name: `RtlCreateTracingFilesystem`
- size: `721`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800237b8`

## callees

- `0x1800069a9`
- `0x1800069b5`
- `0x1800069c1`
- `0x180012b1c`
- `0x18001ccac`
- `0x18001d478`
- `0x18001de74`
- `0x18004f2dc`
- `0x1800bab38`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bad31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bade9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bad31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bade9`

## string_xrefs

- `0x1800bacdc`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bad88`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800bab52`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\isofs_tracing.cpp`

## pseudocode

```c
__int64 __fastcall RtlCreateTracingFilesystem(__int64 a1, __int64 a2, __int64 *a3, __int64 *a4)
{
  int IsolatedFilesystemFromProvider; // ebx
  HANDLE ProcessHeap_0; // rax
  _QWORD *v9; // rax
  void (__fastcall ***v10)(_QWORD, _QWORD); // rdi
  Windows::Isolation::FsProv::Rtl *v11; // rcx
  HANDLE v12; // rax
  __int64 v13; // r10
  unsigned int *v14; // r11
  int v15; // ecx
  __int64 v16; // rdi
  __int64 v17; // rcx
  unsigned int *v18; // r10
  int v19; // ecx
  const char *v21; // [rsp+20h] [rbp-20h] BYREF
  int v22; // [rsp+28h] [rbp-18h]
  DWORD dwExceptionCode; // [rsp+30h] [rbp-10h]
  __int64 v24; // [rsp+80h] [rbp+40h] BYREF
  __int64 v25; // [rsp+88h] [rbp+48h] BYREF

  dwExceptionCode = -1073741595;
  v21 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\isofs_tracing.cpp";
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !(unsigned __int8)Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::IsValid(a2) )
  {
    v22 = 531;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v21);
    return dwExceptionCode;
  }
  if ( !a3 )
  {
    v22 = 533;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v21);
    return dwExceptionCode;
  }
  ProcessHeap_0 = GetProcessHeap_0();
  v9 = HeapAlloc_0(ProcessHeap_0, 0, 0x70u);
  v10 = (void (__fastcall ***)(_QWORD, _QWORD))v9;
  if ( !v9 )
    return (unsigned int)-1073741801;
  v9[3] = v9 + 9;
  v9[1] = off_1801363E0;
  v9[5] = off_1801363E0;
  v9[6] = &RtlpBaseIsolatedFilesystemObjectFunctions;
  v9[7] = &RtlpBaseIsolatedFilesystemFunctions;
  *v9 = &CTracingFilesystem::`vftable'{for `Windows::Isolation::Private::CLayeredObjectSystem'};
  v9[4] = &CTracingFilesystem::`vftable'{for `Windows::Isolation::Private::CBaseFilesystem'};
  v9[2] = v9 + 8;
  v9[8] = 0;
  v9[9] = 0;
  v9[10] = 0;
  v9[11] = 0;
  v9[12] = 0;
  IsolatedFilesystemFromProvider = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v9 + 56LL))(v9, a2);
  if ( IsolatedFilesystemFromProvider < 0 )
  {
LABEL_12:
    (**v10)(v10, 0);
    v12 = GetProcessHeap_0();
    HeapFree_0(v12, 0, v10);
    return (unsigned int)IsolatedFilesystemFromProvider;
  }
  v25 = 0;
  v24 = 0;
  IsolatedFilesystemFromProvider = Windows::Isolation::FsProv::Rtl::CreateIsolatedFilesystemFromProvider(
                                     v11,
                                     (Windows::Isolation::FsProv::Rtl *)(v10 + 6),
                                     (struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *)&v25,
                                     (struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *)((unsigned __int64)&v24
                                                                                            & -(__int64)(a4 != 0)));
  if ( IsolatedFilesystemFromProvider < 0 )
  {
    if ( v24 )
      RtlCloseIsolatedFilesystemObjectHandle(v24);
    if ( v25 )
    {
      ++g_nRtlCloseIsolatedFilesystemHandle;
      dwExceptionCode = -1073741595;
      v21 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v25) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v14 + 4))(*v14, v13);
        v15 = 0;
      }
      else
      {
        v22 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v21);
        v15 = dwExceptionCode;
      }
      if ( v15 < 0 )
        RaiseException(v15, 1u, 0, 0);
    }
    goto LABEL_12;
  }
  v16 = *a3;
  *a3 = v25;
  if ( a4 )
  {
    v17 = *a4;
    *a4 = v24;
  }
  else
  {
    v17 = v24;
  }
  IsolatedFilesystemFromProvider = 0;
  if ( v17 )
    RtlCloseIsolatedFilesystemObjectHandle(v17);
  if ( v16 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    dwExceptionCode = -1073741595;
    v21 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v16) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v18 + 4))(*v18, v16);
      v19 = 0;
    }
    else
    {
      v22 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v21);
      v19 = dwExceptionCode;
    }
    if ( v19 < 0 )
      RaiseException(v19, 1u, 0, 0);
  }
  return (unsigned int)IsolatedFilesystemFromProvider;
}

```

## disassembly

```asm
0x1800bab38  mov     [rsp-28h+arg_0], rbx
0x1800bab3d  push    rbp
0x1800bab3e  push    rsi
0x1800bab3f  push    rdi
0x1800bab40  push    r14
0x1800bab42  push    r15
0x1800bab44  mov     rbp, rsp
0x1800bab47  sub     rsp, 40h
0x1800bab4b  mov     [rbp+dwExceptionCode], 0C00000E5h
0x1800bab52  lea     rax, aOnecoreComNetf_10; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bab59  mov     [rbp+var_20], rax
0x1800bab5d  mov     rsi, r9
0x1800bab60  mov     r14, r8
0x1800bab63  mov     rbx, rdx
0x1800bab66  test    r8, r8
0x1800bab69  jz      short loc_1800BAB72
0x1800bab6b  mov     qword ptr [r8], 0
0x1800bab72  test    rsi, rsi
0x1800bab75  jz      short loc_1800BAB7E
0x1800bab77  mov     qword ptr [r9], 0
0x1800bab7e  mov     rcx, rbx
0x1800bab81  call    ?IsValid@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@SA_NU_ISOLATED_FILESYSTEM@2Isolation@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::IsValid(Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM)
0x1800bab86  test    al, al
0x1800bab88  jnz     short loc_1800BAB9C
0x1800bab8a  mov     [rbp+var_18], 213h
0x1800bab91  lea     rcx, [rbp+var_20]
0x1800bab95  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800bab9a  jmp     short loc_1800BABB1
0x1800bab9c  test    r14, r14
0x1800bab9f  jnz     short loc_1800BABB9
0x1800baba1  lea     rcx, [rbp+var_20]
0x1800baba5  mov     [rbp+var_18], 215h
0x1800babac  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800babb1  mov     ebx, [rbp+dwExceptionCode]
0x1800babb4  jmp     loc_1800BADF6
0x1800babb9  call    GetProcessHeap_0
0x1800babbe  xor     edx, edx; dwFlags
0x1800babc0  mov     rcx, rax; hHeap
0x1800babc3  lea     r8d, [rdx+70h]; dwBytes
0x1800babc7  call    HeapAlloc_0
0x1800babcc  mov     rdi, rax
0x1800babcf  test    rax, rax
0x1800babd2  jz      loc_1800BADF1
0x1800babd8  lea     rdx, [rdi+48h]
0x1800babdc  mov     [rdi+18h], rdx
0x1800babe0  lea     rax, off_1801363E0
0x1800babe7  mov     [rdi+8], rax
0x1800babeb  lea     rcx, [rdi+40h]
0x1800babef  mov     [rdi+28h], rax
0x1800babf3  lea     rax, ?RtlpBaseIsolatedFilesystemObjectFunctions@@3U_PROVIDER_ISOLATED_OBJECT_SYSTEM_FUNCTIONS@Rtl@ObjectProvider@Isolation@Windows@@B; Windows::Isolation::ObjectProvider::Rtl::_PROVIDER_ISOLATED_OBJECT_SYSTEM_FUNCTIONS const RtlpBaseIsolatedFilesystemObjectFunctions
0x1800babfa  mov     [rdi+30h], rax
0x1800babfe  lea     rax, ?RtlpBaseIsolatedFilesystemFunctions@@3U_ISOLATED_FILESYSTEM_PROVIDER_FUNCTIONS@Rtl@FsProv@Isolation@Windows@@B; Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FUNCTIONS const RtlpBaseIsolatedFilesystemFunctions
0x1800bac05  mov     [rdi+38h], rax
0x1800bac09  lea     rax, ??_7CTracingFilesystem@@6BCLayeredObjectSystem@Private@Isolation@Windows@@@; const CTracingFilesystem::`vftable'{for `Windows::Isolation::Private::CLayeredObjectSystem'}
0x1800bac10  mov     [rdi], rax
0x1800bac13  lea     rax, ??_7CTracingFilesystem@@6BCBaseFilesystem@Private@Isolation@Windows@@@; const CTracingFilesystem::`vftable'{for `Windows::Isolation::Private::CBaseFilesystem'}
0x1800bac1a  mov     [rdi+20h], rax
0x1800bac1e  mov     [rdi+10h], rcx
0x1800bac22  mov     qword ptr [rcx], 0
0x1800bac29  mov     qword ptr [rdx], 0
0x1800bac30  mov     qword ptr [rdx+8], 0
0x1800bac38  mov     qword ptr [rdx+10h], 0
0x1800bac40  mov     qword ptr [rdx+18h], 0
0x1800bac48  mov     rax, [rdi]
0x1800bac4b  mov     rdx, rbx
0x1800bac4e  mov     rcx, rdi
0x1800bac51  mov     rax, [rax+38h]
0x1800bac55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac5a  mov     ebx, eax
0x1800bac5c  test    eax, eax
0x1800bac5e  jns     short loc_1800BAC87
0x1800bac60  mov     rax, [rdi]
0x1800bac63  xor     edx, edx
0x1800bac65  mov     rcx, rdi
0x1800bac68  mov     rax, [rax]
0x1800bac6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac70  call    GetProcessHeap_0
0x1800bac75  mov     r8, rdi; lpMem
0x1800bac78  xor     edx, edx; dwFlags
0x1800bac7a  mov     rcx, rax; hHeap
0x1800bac7d  call    HeapFree_0
0x1800bac82  jmp     loc_1800BADF6
0x1800bac87  mov     rax, rsi
0x1800bac8a  mov     [rbp+arg_18], 0
0x1800bac92  neg     rax
0x1800bac95  mov     [rbp+arg_10], 0
0x1800bac9d  lea     rax, [rbp+arg_10]
0x1800baca1  sbb     r9, r9
0x1800baca4  lea     r8, [rbp+arg_18]; struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *
0x1800baca8  and     r9, rax; struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *
0x1800bacab  lea     rdx, [rdi+30h]; unsigned int
0x1800bacaf  call    ?CreateIsolatedFilesystemFromProvider@Rtl@FsProv@Isolation@Windows@@YAJKPEAU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1234@PEAU_ISOLATED_FILESYSTEM@134@PEAU_ISOLATED_FILESYSTEM_OBJECT@134@@Z; Windows::Isolation::FsProv::Rtl::CreateIsolatedFilesystemFromProvider(ulong,Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)
0x1800bacb4  mov     ebx, eax
0x1800bacb6  test    eax, eax
0x1800bacb8  jns     loc_1800BAD51
0x1800bacbe  mov     rcx, [rbp+arg_10]
0x1800bacc2  test    rcx, rcx
0x1800bacc5  jz      short loc_1800BACCC
0x1800bacc7  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800baccc  mov     r10, [rbp+arg_18]
0x1800bacd0  test    r10, r10
0x1800bacd3  jz      short loc_1800BAC60
0x1800bacd5  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800bacdc  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bace3  mov     [rbp+dwExceptionCode], 0C00000E5h
0x1800bacea  mov     [rbp+var_20], rax
0x1800bacee  test    r10, r10
0x1800bacf1  jz      short loc_1800BAD1D
0x1800bacf3  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800bacfa  test    r11, r11
0x1800bacfd  jz      short loc_1800BAD3C
0x1800bacff  mov     rdx, r11
0x1800bad02  mov     rcx, r10
0x1800bad05  call    RtlIsTypeSafeHandleValid
0x1800bad0a  test    al, al
0x1800bad0c  jz      short loc_1800BAD3C
0x1800bad0e  mov     ecx, [r11]
0x1800bad11  mov     rdx, r10
0x1800bad14  mov     rax, [r11+20h]
0x1800bad18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad1d  xor     ecx, ecx; dwExceptionCode
0x1800bad1f  test    ecx, ecx
0x1800bad21  jns     loc_1800BAC60
0x1800bad27  xor     r9d, r9d; lpArguments
0x1800bad2a  xor     r8d, r8d; nNumberOfArguments
0x1800bad2d  lea     edx, [r9+1]; dwExceptionFlags
0x1800bad31  call    cs:__imp_RaiseException
0x1800bad37  jmp     loc_1800BAC60
0x1800bad3c  mov     [rbp+var_18], 124h
0x1800bad43  lea     rcx, [rbp+var_20]
0x1800bad47  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800bad4c  mov     ecx, [rbp+dwExceptionCode]
0x1800bad4f  jmp     short loc_1800BAD1F
0x1800bad51  mov     rax, [rbp+arg_18]
0x1800bad55  mov     rdi, [r14]
0x1800bad58  mov     [r14], rax
0x1800bad5b  test    rsi, rsi
0x1800bad5e  jz      short loc_1800BAD6C
0x1800bad60  mov     rax, [rbp+arg_10]
0x1800bad64  mov     rcx, [rsi]
0x1800bad67  mov     [rsi], rax
0x1800bad6a  jmp     short loc_1800BAD70
0x1800bad6c  mov     rcx, [rbp+arg_10]
0x1800bad70  xor     ebx, ebx
0x1800bad72  test    rcx, rcx
0x1800bad75  jz      short loc_1800BAD7C
0x1800bad77  call    RtlCloseIsolatedFilesystemObjectHandle
0x1800bad7c  test    rdi, rdi
0x1800bad7f  jz      short loc_1800BADF6
0x1800bad81  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x1800bad88  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800bad8f  mov     r10, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x1800bad96  mov     [rbp+dwExceptionCode], 0C00000E5h
0x1800bad9d  mov     [rbp+var_20], rax
0x1800bada1  test    r10, r10
0x1800bada4  jz      short loc_1800BADC8
0x1800bada6  mov     rdx, r10
0x1800bada9  mov     rcx, rdi
0x1800badac  call    RtlIsTypeSafeHandleValid
0x1800badb1  test    al, al
0x1800badb3  jz      short loc_1800BADC8
0x1800badb5  mov     ecx, [r10]
0x1800badb8  mov     rdx, rdi
0x1800badbb  mov     rax, [r10+20h]
0x1800badbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800badc4  xor     ecx, ecx
0x1800badc6  jmp     short loc_1800BADDB
0x1800badc8  mov     [rbp+var_18], 124h
0x1800badcf  lea     rcx, [rbp+var_20]
0x1800badd3  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800badd8  mov     ecx, [rbp+dwExceptionCode]; dwExceptionCode
0x1800baddb  test    ecx, ecx
0x1800baddd  jns     short loc_1800BADF6
0x1800baddf  xor     r9d, r9d; lpArguments
0x1800bade2  xor     r8d, r8d; nNumberOfArguments
0x1800bade5  lea     edx, [r9+1]; dwExceptionFlags
0x1800bade9  call    cs:__imp_RaiseException
0x1800badef  jmp     short loc_1800BADF6
0x1800badf1  mov     ebx, 0C0000017h
0x1800badf6  mov     eax, ebx
0x1800badf8  mov     rbx, [rsp+40h+arg_0]
0x1800badfd  add     rsp, 40h
0x1800bae01  pop     r15
0x1800bae03  pop     r14
0x1800bae05  pop     rdi
0x1800bae06  pop     rsi
0x1800bae07  pop     rbp
0x1800bae08  retn
```
