# Windows::Isolation::FsProv::Rtl::CreateIsolatedFilesystemFromProvider(ulong,Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)

- ea: `0x18001ccac`
- end: `0x18001cef3`
- name: `?CreateIsolatedFilesystemFromProvider@Rtl@FsProv@Isolation@Windows@@YAJKPEAU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1234@PEAU_ISOLATED_FILESYSTEM@134@PEAU_ISOLATED_FILESYSTEM_OBJECT@134@@Z`
- size: `583`
- prototype: `int(Windows::Isolation::FsProv::Rtl *__hidden this, unsigned int, struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *, struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *, struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM_OBJECT *)`
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800237b8`
- `0x1800bab38`
- `0x1800f908c`
- `0x1800f97ec`
- `0x1800f9cb0`
- `0x1800fa36c`

## callees

- `0x180012b1c`
- `0x18001c570`
- `0x18001ccac`
- `0x18001d4a4`
- `0x18001de74`
- `0x18001e044`
- `0x18004f2dc`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cdbe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cebe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cdbe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cebe`

## string_xrefs

- `0x18001cd6c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18001ce70`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x18001ccde`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\isofs_top.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::FsProv::Rtl::CreateIsolatedFilesystemFromProvider(
        Windows::Isolation::FsProv::Rtl *this,
        Windows::Isolation::FsProv::Rtl *a2,
        struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *a3,
        struct Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM *a4)
{
  __int64 v6; // r8
  __int64 v7; // rcx
  int IsolatedFilesystemRootObject; // ebx
  __int64 v9; // rcx
  __int64 v10; // r10
  __int64 v11; // r10
  unsigned int *v12; // r11
  signed int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v17; // [rsp+20h] [rbp-50h] BYREF
  __int128 v18; // [rsp+28h] [rbp-48h] BYREF
  const char *v19; // [rsp+38h] [rbp-38h] BYREF
  int v20; // [rsp+40h] [rbp-30h]
  unsigned int v21; // [rsp+48h] [rbp-28h]
  __int64 v22; // [rsp+A0h] [rbp+30h] BYREF

  v17 = 0;
  v22 = 0;
  v21 = -1073741595;
  v19 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\isofs_top.cpp";
  v18 = 0;
  if ( !a3 )
  {
    v20 = 1608;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v19);
    if ( v22 )
    {
      RtlCloseIsolatedFilesystemObjectHandle(v22);
      v22 = 0;
    }
    return v21;
  }
  *(_QWORD *)a3 = 0;
  if ( !Windows::Isolation::FsProv::Rtl::RtlIsIsolatedFilesystemProviderValid(a2, a2) )
  {
    v20 = 1609;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v19);
    return v21;
  }
  *((_QWORD *)&v18 + 1) = v6;
  IsolatedFilesystemRootObject = Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::Allocate(
                                   &v18,
                                   &v17);
  if ( IsolatedFilesystemRootObject < 0
    || a4
    && (IsolatedFilesystemRootObject = RtlGetIsolatedFilesystemRootObject(v7, v17, &v22),
        IsolatedFilesystemRootObject < 0) )
  {
    v9 = v22;
    if ( !v22 )
    {
LABEL_7:
      v10 = v17;
      goto LABEL_8;
    }
LABEL_6:
    RtlCloseIsolatedFilesystemObjectHandle(v9);
    v22 = 0;
    goto LABEL_7;
  }
  v14 = v17;
  v10 = *(_QWORD *)a3;
  v17 = *(_QWORD *)a3;
  *(_QWORD *)a3 = v14;
  if ( a4 )
  {
    v15 = v22;
    v9 = *(_QWORD *)a4;
    v22 = *(_QWORD *)a4;
    *(_QWORD *)a4 = v15;
  }
  else
  {
    v9 = v22;
  }
  IsolatedFilesystemRootObject = 0;
  if ( v9 )
    goto LABEL_6;
LABEL_8:
  if ( v10 )
  {
    ++g_nRtlCloseIsolatedFilesystemHandle;
    v21 = -1073741595;
    v19 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
    if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
      && (unsigned __int8)RtlIsTypeSafeHandleValid(v10) )
    {
      (*((void (__fastcall **)(_QWORD, __int64))v12 + 4))(*v12, v11);
      v13 = 0;
    }
    else
    {
      v20 = 292;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v19);
      v13 = v21;
    }
    if ( v13 < 0 )
      RaiseException(v13, 1u, 0, 0);
  }
  return (unsigned int)IsolatedFilesystemRootObject;
}

```

## disassembly

```asm
0x18001ccac  mov     [rsp-18h+arg_0], rbx
0x18001ccb1  mov     [rsp-18h+arg_8], rsi
0x18001ccb6  push    rbp
0x18001ccb7  push    rdi
0x18001ccb8  push    r15
0x18001ccba  mov     rbp, rsp
0x18001ccbd  sub     rsp, 70h
0x18001ccc1  mov     rsi, r8
0x18001ccc4  mov     [rbp+var_50], 0
0x18001cccc  mov     [rbp+arg_10], 0
0x18001ccd4  mov     r15d, 0C00000E5h
0x18001ccda  mov     [rbp+var_28], r15d
0x18001ccde  lea     rax, aOnecoreComNetf_112; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001cce5  mov     [rbp+var_38], rax
0x18001cce9  xorps   xmm0, xmm0
0x18001ccec  mov     rdi, r9
0x18001ccef  mov     r8, rdx
0x18001ccf2  movups  [rbp+var_48], xmm0
0x18001ccf6  test    rsi, rsi
0x18001ccf9  jz      loc_18001CE3A
0x18001ccff  mov     rcx, rdx; this
0x18001cd02  mov     qword ptr [rsi], 0
0x18001cd09  call    ?RtlIsIsolatedFilesystemProviderValid@Rtl@FsProv@Isolation@Windows@@YAEPEBU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1234@@Z; Windows::Isolation::FsProv::Rtl::RtlIsIsolatedFilesystemProviderValid(Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM const *)
0x18001cd0e  test    al, al
0x18001cd10  jnz     short loc_18001CD27
0x18001cd12  mov     [rbp+var_30], 649h
0x18001cd19  lea     rcx, [rbp+var_38]
0x18001cd1d  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18001cd22  jmp     loc_18001CEC4
0x18001cd27  lea     rdx, [rbp+var_50]
0x18001cd2b  mov     qword ptr [rbp+var_48+8], r8
0x18001cd2f  lea     rcx, [rbp+var_48]
0x18001cd33  call    ?Allocate@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@SAJAEAUFS_CONSTRUCTOR_DATA@Private@Fs@Isolation@5@AEAU_ISOLATED_FILESYSTEM@295@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::Allocate(Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA &,Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM &)
0x18001cd38  mov     ebx, eax
0x18001cd3a  test    eax, eax
0x18001cd3c  jns     loc_18001CDDE
0x18001cd42  mov     rcx, [rbp+arg_10]
0x18001cd46  test    rcx, rcx
0x18001cd49  jz      short loc_18001CD58
0x18001cd4b  call    RtlCloseIsolatedFilesystemObjectHandle
0x18001cd50  mov     [rbp+arg_10], 0
0x18001cd58  mov     r10, [rbp+var_50]
0x18001cd5c  test    r10, r10
0x18001cd5f  jz      loc_18001CEC7
0x18001cd65  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x18001cd6c  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001cd73  mov     [rbp+var_28], r15d
0x18001cd77  mov     [rbp+var_38], rax
0x18001cd7b  test    r10, r10
0x18001cd7e  jz      short loc_18001CDAA
0x18001cd80  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x18001cd87  test    r11, r11
0x18001cd8a  jz      short loc_18001CDC9
0x18001cd8c  mov     rdx, r11
0x18001cd8f  mov     rcx, r10
0x18001cd92  call    RtlIsTypeSafeHandleValid
0x18001cd97  test    al, al
0x18001cd99  jz      short loc_18001CDC9
0x18001cd9b  mov     ecx, [r11]
0x18001cd9e  mov     rdx, r10
0x18001cda1  mov     rax, [r11+20h]
0x18001cda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdaa  xor     ecx, ecx; dwExceptionCode
0x18001cdac  test    ecx, ecx
0x18001cdae  jns     loc_18001CEC7
0x18001cdb4  xor     r9d, r9d; lpArguments
0x18001cdb7  xor     r8d, r8d; nNumberOfArguments
0x18001cdba  lea     edx, [r9+1]; dwExceptionFlags
0x18001cdbe  call    cs:__imp_RaiseException
0x18001cdc4  jmp     loc_18001CEC7
0x18001cdc9  mov     [rbp+var_30], 124h
0x18001cdd0  lea     rcx, [rbp+var_38]
0x18001cdd4  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18001cdd9  mov     ecx, [rbp+var_28]
0x18001cddc  jmp     short loc_18001CDAC
0x18001cdde  test    rdi, rdi
0x18001cde1  jz      short loc_18001CDFA
0x18001cde3  mov     rdx, [rbp+var_50]
0x18001cde7  lea     r8, [rbp+arg_10]
0x18001cdeb  call    RtlGetIsolatedFilesystemRootObject
0x18001cdf0  mov     ebx, eax
0x18001cdf2  test    eax, eax
0x18001cdf4  js      loc_18001CD42
0x18001cdfa  mov     rax, [rbp+var_50]
0x18001cdfe  mov     r10, [rsi]
0x18001ce01  mov     [rbp+var_50], r10
0x18001ce05  mov     [rsi], rax
0x18001ce08  test    rdi, rdi
0x18001ce0b  jz      short loc_18001CE1D
0x18001ce0d  mov     rax, [rbp+arg_10]
0x18001ce11  mov     rcx, [rdi]
0x18001ce14  mov     [rbp+arg_10], rcx
0x18001ce18  mov     [rdi], rax
0x18001ce1b  jmp     short loc_18001CE21
0x18001ce1d  mov     rcx, [rbp+arg_10]
0x18001ce21  xor     ebx, ebx
0x18001ce23  test    rcx, rcx
0x18001ce26  jz      loc_18001CD5C
0x18001ce2c  call    RtlCloseIsolatedFilesystemObjectHandle
0x18001ce31  mov     [rbp+arg_10], rbx
0x18001ce35  jmp     loc_18001CD58
0x18001ce3a  lea     rcx, [rbp+var_38]
0x18001ce3e  mov     [rbp+var_30], 648h
0x18001ce45  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18001ce4a  mov     rcx, [rbp+arg_10]
0x18001ce4e  test    rcx, rcx
0x18001ce51  jz      short loc_18001CE60
0x18001ce53  call    RtlCloseIsolatedFilesystemObjectHandle
0x18001ce58  mov     [rbp+arg_10], 0
0x18001ce60  mov     r10, [rbp+var_50]
0x18001ce64  test    r10, r10
0x18001ce67  jz      short loc_18001CEC4
0x18001ce69  inc     cs:?g_nRtlCloseIsolatedFilesystemHandle@@3_KA; unsigned __int64 g_nRtlCloseIsolatedFilesystemHandle
0x18001ce70  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18001ce77  mov     [rbp+var_10], r15d
0x18001ce7b  mov     [rbp+var_20], rax
0x18001ce7f  test    r10, r10
0x18001ce82  jz      short loc_18001CEAE
0x18001ce84  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_FILESYSTEM@Rtl@Isolation@Windows@@VCFs@Private@Fs@34@UFS_CONSTRUCTOR_DATA@6734@VCFsTraits@6734@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_FILESYSTEM,Windows::Isolation::Fs::Private::CFs,Windows::Isolation::Fs::Private::FS_CONSTRUCTOR_DATA,Windows::Isolation::Fs::Private::CFsTraits>::ms_ptti
0x18001ce8b  test    r11, r11
0x18001ce8e  jz      short loc_18001CEDE
0x18001ce90  mov     rdx, r11
0x18001ce93  mov     rcx, r10
0x18001ce96  call    RtlIsTypeSafeHandleValid
0x18001ce9b  test    al, al
0x18001ce9d  jz      short loc_18001CEDE
0x18001ce9f  mov     ecx, [r11]
0x18001cea2  mov     rdx, r10
0x18001cea5  mov     rax, [r11+20h]
0x18001cea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceae  xor     ecx, ecx; dwExceptionCode
0x18001ceb0  test    ecx, ecx
0x18001ceb2  jns     short loc_18001CEC4
0x18001ceb4  xor     r9d, r9d; lpArguments
0x18001ceb7  xor     r8d, r8d; nNumberOfArguments
0x18001ceba  lea     edx, [r9+1]; dwExceptionFlags
0x18001cebe  call    cs:__imp_RaiseException
0x18001cec4  mov     ebx, [rbp+var_28]
0x18001cec7  lea     r11, [rsp+70h+var_s0]
0x18001cecc  mov     eax, ebx
0x18001cece  mov     rbx, [r11+20h]
0x18001ced2  mov     rsi, [r11+28h]
0x18001ced6  mov     rsp, r11
0x18001ced9  pop     r15
0x18001cedb  pop     rdi
0x18001cedc  pop     rbp
0x18001cedd  retn
0x18001cede  mov     [rbp+var_18], 124h
0x18001cee5  lea     rcx, [rbp+var_20]
0x18001cee9  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18001ceee  mov     ecx, [rbp+var_10]
0x18001cef1  jmp     short loc_18001CEB0
```
