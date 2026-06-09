# CHashElementSection::get_Count(ulong *)

- ea: `0x180091730`
- end: `0x180091990`
- name: `?get_Count@CHashElementSection@@UEAAJPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CHashElementSection *__hidden this, unsigned int *)`
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
- `0x180091730`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800917ed`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800918c1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800917ed`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800918c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091877`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091971`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091877`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180091971`

## string_xrefs

- `0x180091828`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x180091926`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmp.h`
- `0x18009174a`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\whidbey\objfre\amd64\com_cms.cpp`

## pseudocode

```c
__int64 __fastcall CHashElementSection::get_Count(CHashElementSection *this, unsigned int *a2)
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
    v16 = 4703;
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
    v16 = 4704;
    goto LABEL_29;
  }
  if ( !CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE,_CDF_INTERNAL_ULONG_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
    || !(unsigned __int8)RtlIsTypeSafeHandleValid(*((_QWORD *)this + 4)) )
  {
    v16 = 4705;
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
        (const char *)0x126D,
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
        (const char *)0x1269,
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
0x180091730  mov     [rsp-28h+arg_0], rbx
0x180091735  push    rbp
0x180091736  push    rsi
0x180091737  push    rdi
0x180091738  push    r12
0x18009173a  push    r14
0x18009173c  mov     rbp, rsp
0x18009173f  sub     rsp, 50h
0x180091743  mov     [rbp+var_20], 8007054Fh
0x18009174a  lea     r12, aOnecoreComNetf_116; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180091751  mov     [rbp+var_30], r12
0x180091755  mov     rdi, rdx
0x180091758  mov     [rbp+arg_8], 0
0x180091760  mov     rbx, rcx
0x180091763  mov     [rbp+arg_10], 0
0x18009176b  test    rdx, rdx
0x18009176e  jz      loc_180091906
0x180091774  mov     dword ptr [rdx], 0
0x18009177a  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF@Rtl@Cdf@Windows@@U_CDF_INTERNAL@@U_LBLOB@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF,_CDF_INTERNAL,_LBLOB>::ms_ptti
0x180091781  test    rdx, rdx
0x180091784  jz      loc_1800918F0
0x18009178a  mov     rcx, [rcx+18h]
0x18009178e  call    RtlIsTypeSafeHandleValid
0x180091793  test    al, al
0x180091795  jz      loc_1800918F0
0x18009179b  mov     rdx, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE@@U_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE,_CDF_INTERNAL_ULONG_TABLE,_CDF_GENERIC_TABLE_CONSTRUCTOR_DATA>::ms_ptti
0x1800917a2  test    rdx, rdx
0x1800917a5  jz      loc_1800918E7
0x1800917ab  mov     rcx, [rbx+20h]
0x1800917af  call    RtlIsTypeSafeHandleValid
0x1800917b4  test    al, al
0x1800917b6  jz      loc_1800918E7
0x1800917bc  cmp     byte ptr [rbx+2Ch], 0
0x1800917c0  jz      short loc_1800917CE
0x1800917c2  mov     eax, [rbx+28h]
0x1800917c5  xor     ebx, ebx
0x1800917c7  mov     [rdi], eax
0x1800917c9  jmp     loc_18009197A
0x1800917ce  mov     rcx, [rbx+20h]
0x1800917d2  lea     rdx, [rbp+arg_8]
0x1800917d6  call    CdfEnumerateUlongTable
0x1800917db  mov     esi, eax
0x1800917dd  test    eax, eax
0x1800917df  jns     loc_180091882
0x1800917e5  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800917eb  jnz     short loc_1800917F3
0x1800917ed  call    cs:__imp_DebugBreak
0x1800917f3  mov     r9d, esi; int
0x1800917f6  lea     rcx, aStatusPropagat; "Status propagated"
0x1800917fd  mov     r8d, 1269h; char *
0x180091803  mov     rdx, r12; char *
0x180091806  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x18009180b  mov     ecx, esi; this
0x18009180d  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180091812  mov     ebx, eax
0x180091814  mov     rdx, [rbp+arg_8]
0x180091818  test    rdx, rdx
0x18009181b  jz      loc_18009197A
0x180091821  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180091828  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18009182f  mov     [rbp+var_20], 0C00000E5h
0x180091836  mov     [rbp+var_30], rcx
0x18009183a  test    rax, rax
0x18009183d  jnz     short loc_180091858
0x18009183f  mov     [rbp+var_28], 401h
0x180091846  lea     rdx, [rbp+var_30]
0x18009184a  lea     rcx, [rbp+var_30]
0x18009184e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091853  mov     ecx, [rbp+var_20]
0x180091856  jmp     short loc_180091865
0x180091858  mov     ecx, [rax]
0x18009185a  mov     rax, [rax+20h]
0x18009185e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091863  xor     ecx, ecx; dwExceptionCode
0x180091865  test    ecx, ecx
0x180091867  jns     loc_18009197A
0x18009186d  xor     r9d, r9d; lpArguments
0x180091870  xor     r8d, r8d; nNumberOfArguments
0x180091873  lea     edx, [r9+1]; dwExceptionFlags
0x180091877  call    cs:__imp_RaiseException
0x18009187d  jmp     loc_18009197A
0x180091882  xor     esi, esi
0x180091884  mov     rcx, [rbp+arg_8]
0x180091888  lea     r8, [rbp+arg_10]
0x18009188c  mov     edx, 1
0x180091891  call    CdfMoveUlongTableEnumeratorPosition
0x180091896  mov     r14d, eax
0x180091899  test    eax, eax
0x18009189b  js      short loc_1800918B8
0x18009189d  cmp     [rbp+arg_10], 1
0x1800918a2  jnz     short loc_1800918A8
0x1800918a4  inc     esi
0x1800918a6  jmp     short loc_180091884
0x1800918a8  mov     [rbx+28h], esi
0x1800918ab  mov     byte ptr [rbx+2Ch], 1
0x1800918af  xor     ebx, ebx
0x1800918b1  mov     [rdi], esi
0x1800918b3  jmp     loc_180091814
0x1800918b8  cmp     r14d, cs:g_NTSTATUS_to_break_on_propagate
0x1800918bf  jnz     short loc_1800918C7
0x1800918c1  call    cs:__imp_DebugBreak
0x1800918c7  mov     r9d, r14d; int
0x1800918ca  lea     rcx, aStatusPropagat; "Status propagated"
0x1800918d1  mov     r8d, 126Dh; char *
0x1800918d7  mov     rdx, r12; char *
0x1800918da  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800918df  mov     ecx, r14d
0x1800918e2  jmp     loc_18009180D
0x1800918e7  mov     [rbp+var_28], 1261h
0x1800918ee  jmp     short loc_1800918F7
0x1800918f0  mov     [rbp+var_28], 1260h
0x1800918f7  lea     rdx, [rbp+var_30]
0x1800918fb  lea     rcx, [rbp+var_30]
0x1800918ff  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091904  jmp     short loc_180091977
0x180091906  lea     rcx, [rbp+var_30]
0x18009190a  mov     [rbp+var_28], 125Fh
0x180091911  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x180091916  mov     rdx, [rbp+arg_8]
0x18009191a  test    rdx, rdx
0x18009191d  jz      short loc_180091977
0x18009191f  mov     rax, cs:?ms_ptti@?$CCdfInternalGenericBaseClass@U_CDF_ULONG_TABLE_ENUMERATOR@Rtl@Cdf@Windows@@U_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR@@U_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA@@@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@Rtl@Provider@TypeSafeHandle@Windows@@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * CCdfInternalGenericBaseClass<Windows::Cdf::Rtl::_CDF_ULONG_TABLE_ENUMERATOR,_CDF_INTERNAL_ULONG_TABLE_ENUMERATOR,_CDF_ULONG_TABLE_ENUMERATOR_CONSTRUCTOR_DATA>::ms_ptti
0x180091926  lea     rcx, aOnecoreComNetf_0; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18009192d  mov     [rbp+var_8], 0C00000E5h
0x180091934  mov     [rbp+var_18], rcx
0x180091938  test    rax, rax
0x18009193b  jnz     short loc_180091956
0x18009193d  mov     [rbp+var_10], 401h
0x180091944  lea     rdx, [rbp+var_18]
0x180091948  lea     rcx, [rbp+var_18]
0x18009194c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180091951  mov     ecx, [rbp+var_8]
0x180091954  jmp     short loc_180091963
0x180091956  mov     ecx, [rax]
0x180091958  mov     rax, [rax+20h]
0x18009195c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091961  xor     ecx, ecx; dwExceptionCode
0x180091963  test    ecx, ecx
0x180091965  jns     short loc_180091977
0x180091967  xor     r9d, r9d; lpArguments
0x18009196a  xor     r8d, r8d; nNumberOfArguments
0x18009196d  lea     edx, [r9+1]; dwExceptionFlags
0x180091971  call    cs:__imp_RaiseException
0x180091977  mov     ebx, [rbp+var_20]
0x18009197a  mov     eax, ebx
0x18009197c  mov     rbx, [rsp+50h+arg_0]
0x180091984  add     rsp, 50h
0x180091988  pop     r14
0x18009198a  pop     r12
0x18009198c  pop     rdi
0x18009198d  pop     rsi
0x18009198e  pop     rbp
0x18009198f  retn
```
