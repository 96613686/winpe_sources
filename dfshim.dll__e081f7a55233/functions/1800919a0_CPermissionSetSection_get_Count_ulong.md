# CPermissionSetSection::get_Count(ulong *)

- ea: `0x1800919a0`
- end: `0x180091c00`
- name: `?get_Count@CPermissionSetSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CPermissionSetSection *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180012910`
- `0x180012950`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x18004f2dc`
- `0x18007338c`
- `0x1800919a0`
- `0x1800d8368`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091a5d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091b31`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091a5d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180091b31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091ae7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091be1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091ae7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091be1`

## string_xrefs

- `0x180091a98`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180091b96`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x1800919ba`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CPermissionSetSection::get_Count(CPermissionSetSection *this, unsigned int *a2)
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
    v16 = 6831;
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v15);
    if ( v21 )
    {
      v20 = -1073741595;
      v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmp.h";
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
    v16 = 6832;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 6833;
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
    v6 = CdfEnumerateStringTable(*((_QWORD *)this + 4), &v21);
    v7 = v6;
    if ( v6 >= 0 )
    {
      for ( i = 0; ; ++i )
      {
        v12 = Windows::Cdf::Rtl::MovePosition(v21, 1, &v22);
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
        (const char *)0x1ABD,
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
        (const char *)0x1AB9,
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
      if ( CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti )
      {
        (*(void (__fastcall **)(_QWORD))(CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
                                       + 32))(*(unsigned int *)CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti);
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
0x1800919a0  mov     [rsp-28h+arg_0], rbx
0x1800919a5  push    rbp
0x1800919a6  push    rsi
0x1800919a7  push    rdi
0x1800919a8  push    r12
0x1800919aa  push    r14
0x1800919ac  mov     rbp, rsp
0x1800919af  sub     rsp, 50h
0x1800919b3  mov     [rbp+var_20], 8007054Fh
0x1800919ba  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800919c1  mov     [rbp+var_30], r12
0x1800919c5  mov     rdi, rdx
0x1800919c8  mov     [rbp+arg_8], 0
0x1800919d0  mov     rbx, rcx
0x1800919d3  mov     [rbp+arg_10], 0
0x1800919db  test    rdx, rdx
0x1800919de  jz      loc_180091B76
0x1800919e4  mov     dword ptr [rdx], 0
0x1800919ea  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x1800919f1  test    rdx, rdx
0x1800919f4  jz      loc_180091B60
0x1800919fa  mov     rcx, [rcx+18h]
0x1800919fe  call    RtlIsTypeSafeHandleValid
0x180091a03  test    al, al
0x180091a05  jz      loc_180091B60
0x180091a0b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE,_CDF_INTERNAL_STRING_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x180091a12  test    rdx, rdx
0x180091a15  jz      loc_180091B57
0x180091a1b  mov     rcx, [rbx+20h]
0x180091a1f  call    RtlIsTypeSafeHandleValid
0x180091a24  test    al, al
0x180091a26  jz      loc_180091B57
0x180091a2c  cmp     byte ptr [rbx+2Ch], 0
0x180091a30  jz      short loc_180091A3E
0x180091a32  mov     eax, [rbx+28h]
0x180091a35  xor     ebx, ebx
0x180091a37  mov     [rdi], eax
0x180091a39  jmp     loc_180091BEA
0x180091a3e  mov     rcx, [rbx+20h]
0x180091a42  lea     rdx, [rbp+arg_8]
0x180091a46  call    CdfEnumerateStringTable
0x180091a4b  mov     esi, eax
0x180091a4d  test    eax, eax
0x180091a4f  jns     loc_180091AF2
0x180091a55  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180091a5b  jnz     short loc_180091A63
0x180091a5d  call    cs:__imp_DebugBreak
0x180091a63  mov     r9d, esi; int
0x180091a66  lea     rcx, aStatusPropagat; "Status propagated"
0x180091a6d  mov     r8d, 1AB9h; char *
0x180091a73  mov     rdx, r12; char *
0x180091a76  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180091a7b  mov     ecx, esi; this
0x180091a7d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180091a82  mov     ebx, eax
0x180091a84  mov     rdx, [rbp+arg_8]
0x180091a88  test    rdx, rdx
0x180091a8b  jz      loc_180091BEA
0x180091a91  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180091a98  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091a9f  mov     [rbp+var_20], 0C00000E5h
0x180091aa6  mov     [rbp+var_30], rcx
0x180091aaa  test    rax, rax
0x180091aad  jnz     short loc_180091AC8
0x180091aaf  mov     [rbp+var_28], 401h
0x180091ab6  lea     rdx, [rbp+var_30]
0x180091aba  lea     rcx, [rbp+var_30]
0x180091abe  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091ac3  mov     ecx, [rbp+var_20]
0x180091ac6  jmp     short loc_180091AD5
0x180091ac8  mov     ecx, [rax]
0x180091aca  mov     rax, [rax+20h]
0x180091ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091ad3  xor     ecx, ecx; dwExceptionCode
0x180091ad5  test    ecx, ecx
0x180091ad7  jns     loc_180091BEA
0x180091add  xor     r9d, r9d; lpArguments
0x180091ae0  xor     r8d, r8d; nNumberOfArguments
0x180091ae3  lea     edx, [r9+1]; dwExceptionFlags
0x180091ae7  call    cs:__imp_RaiseException
0x180091aed  jmp     loc_180091BEA
0x180091af2  xor     esi, esi
0x180091af4  mov     rcx, [rbp+arg_8]
0x180091af8  lea     r8, [rbp+arg_10]
0x180091afc  mov     edx, 1
0x180091b01  call    ?MovePosition@Rtl@Cdf@Windows@@YAJU_CDF_STRING_TABLE_ENUMERATOR@123@_JAEA_J@Z; Windows::Cdf::Rtl::MovePosition(Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,__int64,__int64 &)
0x180091b06  mov     r14d, eax
0x180091b09  test    eax, eax
0x180091b0b  js      short loc_180091B28
0x180091b0d  cmp     [rbp+arg_10], 1
0x180091b12  jnz     short loc_180091B18
0x180091b14  inc     esi
0x180091b16  jmp     short loc_180091AF4
0x180091b18  mov     [rbx+28h], esi
0x180091b1b  mov     byte ptr [rbx+2Ch], 1
0x180091b1f  xor     ebx, ebx
0x180091b21  mov     [rdi], esi
0x180091b23  jmp     loc_180091A84
0x180091b28  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x180091b2f  jnz     short loc_180091B37
0x180091b31  call    cs:__imp_DebugBreak
0x180091b37  mov     r9d, r14d; int
0x180091b3a  lea     rcx, aStatusPropagat; "Status propagated"
0x180091b41  mov     r8d, 1ABDh; char *
0x180091b47  mov     rdx, r12; char *
0x180091b4a  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180091b4f  mov     ecx, r14d
0x180091b52  jmp     loc_180091A7D
0x180091b57  mov     [rbp+var_28], 1AB1h
0x180091b5e  jmp     short loc_180091B67
0x180091b60  mov     [rbp+var_28], 1AB0h
0x180091b67  lea     rdx, [rbp+var_30]
0x180091b6b  lea     rcx, [rbp+var_30]
0x180091b6f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091b74  jmp     short loc_180091BE7
0x180091b76  lea     rcx, [rbp+var_30]
0x180091b7a  mov     [rbp+var_28], 1AAFh
0x180091b81  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180091b86  mov     rdx, [rbp+arg_8]
0x180091b8a  test    rdx, rdx
0x180091b8d  jz      short loc_180091BE7
0x180091b8f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_STRING_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_STRING_TABLE_ENUMERATOR@@U_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_STRING_TABLE_ENUMERATOR,_CDF_INTERNAL_STRING_TABLE_ENUMERATOR,_CDF_STRING_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180091b96  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091b9d  mov     [rbp+var_8], 0C00000E5h
0x180091ba4  mov     [rbp+var_18], rcx
0x180091ba8  test    rax, rax
0x180091bab  jnz     short loc_180091BC6
0x180091bad  mov     [rbp+var_10], 401h
0x180091bb4  lea     rdx, [rbp+var_18]
0x180091bb8  lea     rcx, [rbp+var_18]
0x180091bbc  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091bc1  mov     ecx, [rbp+var_8]
0x180091bc4  jmp     short loc_180091BD3
0x180091bc6  mov     ecx, [rax]
0x180091bc8  mov     rax, [rax+20h]
0x180091bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091bd1  xor     ecx, ecx; dwExceptionCode
0x180091bd3  test    ecx, ecx
0x180091bd5  jns     short loc_180091BE7
0x180091bd7  xor     r9d, r9d; lpArguments
0x180091bda  xor     r8d, r8d; nNumberOfArguments
0x180091bdd  lea     edx, [r9+1]; dwExceptionFlags
0x180091be1  call    cs:__imp_RaiseException
0x180091be7  mov     ebx, [rbp+var_20]
0x180091bea  mov     eax, ebx
0x180091bec  mov     rbx, [rsp+50h+arg_0]
0x180091bf4  add     rsp, 50h
0x180091bf8  pop     r14
0x180091bfa  pop     r12
0x180091bfc  pop     rdi
0x180091bfd  pop     rsi
0x180091bfe  pop     rbp
0x180091bff  retn
```
