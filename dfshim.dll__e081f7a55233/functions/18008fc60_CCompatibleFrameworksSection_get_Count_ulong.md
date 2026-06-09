# CCompatibleFrameworksSection::get_Count(ulong *)

- ea: `0x18008fc60`
- end: `0x18008fec0`
- name: `?get_Count@CCompatibleFrameworksSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CCompatibleFrameworksSection *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180012910`
- `0x180012950`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x180048d70`
- `0x180048f4c`
- `0x18004f2dc`
- `0x18008fc60`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008fd1d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008fdf1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008fd1d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18008fdf1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fda7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fea1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fda7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008fea1`

## string_xrefs

- `0x18008fd58`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008fe56`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18008fc7a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CCompatibleFrameworksSection::get_Count(CCompatibleFrameworksSection *this, unsigned int *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int v7; // esi
  int v8; // edx
  unsigned __int64 v9; // rcx
  signed int v10; // ecx
  unsigned int i; // esi
  int v12; // r14d
  signed int v13; // ecx
  const char *v15; // [rsp+20h] [rbp-30h] BYREF
  int v16; // [rsp+28h] [rbp-28h]
  unsigned int v17; // [rsp+30h] [rbp-20h]
  const char *v18; // [rsp+38h] [rbp-18h] BYREF
  int v19; // [rsp+40h] [rbp-10h]
  int v20; // [rsp+48h] [rbp-8h]
  __int64 v21; // [rsp+88h] [rbp+38h] BYREF
  __int64 v22; // [rsp+90h] [rbp+40h] BYREF

  v17 = -2147023537;
  v15 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp";
  v21 = 0;
  v22 = 0;
  if ( !a2 )
  {
    v16 = 8660;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v15);
    if ( v21 )
    {
      v20 = -1073741595;
      v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
        v13 = 0;
      }
      else
      {
        v19 = 1025;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
          &v18,
          &v18);
        v13 = v20;
      }
      if ( v13 < 0 )
        RaiseException(v13, 1u, 0, 0);
    }
    return v17;
  }
  *a2 = 0;
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 3)) )
  {
    v16 = 8661;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE,_CDF_INTERNAL_ULONG_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 8662;
LABEL_29:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
      &v15,
      &v15);
    return v17;
  }
  if ( *((_BYTE *)this + 44) )
  {
    v4 = *((_DWORD *)this + 10);
    v5 = 0;
    *a2 = v4;
  }
  else
  {
    v6 = CdfEnumerateUlongTable(*((_QWORD *)this + 4), &v21);
    v7 = v6;
    if ( v6 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v12 = CdfMoveUlongTableEnumeratorPosition(v21, 1, &v22);
        if ( v12 < 0 )
          break;
        if ( v22 != 1 )
        {
          *((_DWORD *)this + 10) = i;
          *((_BYTE *)this + 44) = 1;
          v5 = 0;
          *a2 = i;
          goto LABEL_13;
        }
      }
      if ( v12 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x21E2,
        v12,
        (unsigned int)v15);
      v9 = (unsigned int)v12;
    }
    else
    {
      if ( v6 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\whidbey\\objfre\\amd64\\com_cms.cpp",
        (const char *)0x21DE,
        v7,
        (unsigned int)v15);
      v9 = v7;
    }
    v5 = Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v9, v8);
LABEL_13:
    if ( v21 )
    {
      v17 = -1073741595;
      v15 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
        v10 = 0;
      }
      else
      {
        v16 = 1025;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
          &v15,
          &v15);
        v10 = v17;
      }
      if ( v10 < 0 )
        RaiseException(v10, 1u, 0, 0);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18008fc60  mov     [rsp-28h+arg_0], rbx
0x18008fc65  push    rbp
0x18008fc66  push    rsi
0x18008fc67  push    rdi
0x18008fc68  push    r12
0x18008fc6a  push    r14
0x18008fc6c  mov     rbp, rsp
0x18008fc6f  sub     rsp, 50h
0x18008fc73  mov     [rbp+var_20], 8007054Fh
0x18008fc7a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008fc81  mov     [rbp+var_30], r12
0x18008fc85  mov     rdi, rdx
0x18008fc88  mov     [rbp+arg_8], 0
0x18008fc90  mov     rbx, rcx
0x18008fc93  mov     [rbp+arg_10], 0
0x18008fc9b  test    rdx, rdx
0x18008fc9e  jz      loc_18008FE36
0x18008fca4  mov     dword ptr [rdx], 0
0x18008fcaa  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x18008fcb1  test    rdx, rdx
0x18008fcb4  jz      loc_18008FE20
0x18008fcba  mov     rcx, [rcx+18h]
0x18008fcbe  call    RtlIsTypeSafeHandleValid
0x18008fcc3  test    al, al
0x18008fcc5  jz      loc_18008FE20
0x18008fccb  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE,_CDF_INTERNAL_ULONG_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x18008fcd2  test    rdx, rdx
0x18008fcd5  jz      loc_18008FE17
0x18008fcdb  mov     rcx, [rbx+20h]
0x18008fcdf  call    RtlIsTypeSafeHandleValid
0x18008fce4  test    al, al
0x18008fce6  jz      loc_18008FE17
0x18008fcec  cmp     byte ptr [rbx+2Ch], 0
0x18008fcf0  jz      short loc_18008FCFE
0x18008fcf2  mov     eax, [rbx+28h]
0x18008fcf5  xor     ebx, ebx
0x18008fcf7  mov     [rdi], eax
0x18008fcf9  jmp     loc_18008FEAA
0x18008fcfe  mov     rcx, [rbx+20h]
0x18008fd02  lea     rdx, [rbp+arg_8]
0x18008fd06  call    CdfEnumerateUlongTable
0x18008fd0b  mov     esi, eax
0x18008fd0d  test    eax, eax
0x18008fd0f  jns     loc_18008FDB2
0x18008fd15  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18008fd1b  jnz     short loc_18008FD23
0x18008fd1d  call    cs:__imp_DebugBreak
0x18008fd23  mov     r9d, esi; int
0x18008fd26  lea     rcx, aStatusPropagat; "Status propagated"
0x18008fd2d  mov     r8d, 21DEh; char *
0x18008fd33  mov     rdx, r12; char *
0x18008fd36  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008fd3b  mov     ecx, esi; this
0x18008fd3d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18008fd42  mov     ebx, eax
0x18008fd44  mov     rdx, [rbp+arg_8]
0x18008fd48  test    rdx, rdx
0x18008fd4b  jz      loc_18008FEAA
0x18008fd51  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008fd58  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008fd5f  mov     [rbp+var_20], 0C00000E5h
0x18008fd66  mov     [rbp+var_30], rcx
0x18008fd6a  test    rax, rax
0x18008fd6d  jnz     short loc_18008FD88
0x18008fd6f  mov     [rbp+var_28], 401h
0x18008fd76  lea     rdx, [rbp+var_30]
0x18008fd7a  lea     rcx, [rbp+var_30]
0x18008fd7e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008fd83  mov     ecx, [rbp+var_20]
0x18008fd86  jmp     short loc_18008FD95
0x18008fd88  mov     ecx, [rax]
0x18008fd8a  mov     rax, [rax+20h]
0x18008fd8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fd93  xor     ecx, ecx; dwExceptionCode
0x18008fd95  test    ecx, ecx
0x18008fd97  jns     loc_18008FEAA
0x18008fd9d  xor     r9d, r9d; lpArguments
0x18008fda0  xor     r8d, r8d; nNumberOfArguments
0x18008fda3  lea     edx, [r9+1]; dwExceptionFlags
0x18008fda7  call    cs:__imp_RaiseException
0x18008fdad  jmp     loc_18008FEAA
0x18008fdb2  xor     esi, esi
0x18008fdb4  mov     rcx, [rbp+arg_8]
0x18008fdb8  lea     r8, [rbp+arg_10]
0x18008fdbc  mov     edx, 1
0x18008fdc1  call    CdfMoveUlongTableEnumeratorPosition
0x18008fdc6  mov     r14d, eax
0x18008fdc9  test    eax, eax
0x18008fdcb  js      short loc_18008FDE8
0x18008fdcd  cmp     [rbp+arg_10], 1
0x18008fdd2  jnz     short loc_18008FDD8
0x18008fdd4  inc     esi
0x18008fdd6  jmp     short loc_18008FDB4
0x18008fdd8  mov     [rbx+28h], esi
0x18008fddb  mov     byte ptr [rbx+2Ch], 1
0x18008fddf  xor     ebx, ebx
0x18008fde1  mov     [rdi], esi
0x18008fde3  jmp     loc_18008FD44
0x18008fde8  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x18008fdef  jnz     short loc_18008FDF7
0x18008fdf1  call    cs:__imp_DebugBreak
0x18008fdf7  mov     r9d, r14d; int
0x18008fdfa  lea     rcx, aStatusPropagat; "Status propagated"
0x18008fe01  mov     r8d, 21E2h; char *
0x18008fe07  mov     rdx, r12; char *
0x18008fe0a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18008fe0f  mov     ecx, r14d
0x18008fe12  jmp     loc_18008FD3D
0x18008fe17  mov     [rbp+var_28], 21D6h
0x18008fe1e  jmp     short loc_18008FE27
0x18008fe20  mov     [rbp+var_28], 21D5h
0x18008fe27  lea     rdx, [rbp+var_30]
0x18008fe2b  lea     rcx, [rbp+var_30]
0x18008fe2f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008fe34  jmp     short loc_18008FEA7
0x18008fe36  lea     rcx, [rbp+var_30]
0x18008fe3a  mov     [rbp+var_28], 21D4h
0x18008fe41  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18008fe46  mov     rdx, [rbp+arg_8]
0x18008fe4a  test    rdx, rdx
0x18008fe4d  jz      short loc_18008FEA7
0x18008fe4f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x18008fe56  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18008fe5d  mov     [rbp+var_8], 0C00000E5h
0x18008fe64  mov     [rbp+var_18], rcx
0x18008fe68  test    rax, rax
0x18008fe6b  jnz     short loc_18008FE86
0x18008fe6d  mov     [rbp+var_10], 401h
0x18008fe74  lea     rdx, [rbp+var_18]
0x18008fe78  lea     rcx, [rbp+var_18]
0x18008fe7c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x18008fe81  mov     ecx, [rbp+var_8]
0x18008fe84  jmp     short loc_18008FE93
0x18008fe86  mov     ecx, [rax]
0x18008fe88  mov     rax, [rax+20h]
0x18008fe8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fe91  xor     ecx, ecx; dwExceptionCode
0x18008fe93  test    ecx, ecx
0x18008fe95  jns     short loc_18008FEA7
0x18008fe97  xor     r9d, r9d; lpArguments
0x18008fe9a  xor     r8d, r8d; nNumberOfArguments
0x18008fe9d  lea     edx, [r9+1]; dwExceptionFlags
0x18008fea1  call    cs:__imp_RaiseException
0x18008fea7  mov     ebx, [rbp+var_20]
0x18008feaa  mov     eax, ebx
0x18008feac  mov     rbx, [rsp+50h+arg_0]
0x18008feb4  add     rsp, 50h
0x18008feb8  pop     r14
0x18008feba  pop     r12
0x18008febc  pop     rdi
0x18008febd  pop     rsi
0x18008febe  pop     rbp
0x18008febf  retn
```
