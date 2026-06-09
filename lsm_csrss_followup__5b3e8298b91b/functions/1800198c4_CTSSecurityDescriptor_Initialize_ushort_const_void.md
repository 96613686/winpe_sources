# CTSSecurityDescriptor::Initialize(ushort const *,void *)

- ea: `0x1800198c4`
- end: `0x180019dbf`
- name: `?Initialize@CTSSecurityDescriptor@@QEAAJPEBGPEAX@Z`
- size: `1275`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019838`

## callees

- `0x180001120`
- `0x18000345c`
- `0x1800074c0`
- `0x180018d40`
- `0x1800198c4`
- `0x18001fc20`
- `0x18001fdd0`
- `0x180021254`
- `0x180026168`
- `0x18002a3dc`
- `0x18003dfdc`
- `0x18004b460`
- `0x18004bd84`
- `0x18004bf08`
- `0x180088ea4`
- `0x180093fe0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019b1a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019b2e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019b1a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180019b2e`
- `ntdll!RtlDeleteSecurityObject` at `0x180019d90`
- `ntdll!RtlDeleteSecurityObject` at `0x180019d90`

## string_xrefs

- `0x180019ae7`: `SecurityDescriptor not found for this listener`
- `0x180019ac1`: `Security`
- `0x180019b38`: `DefaultSecurity`
- `0x180019b5b`: `Querying Console default security descriptor`
- `0x180019b50`: `ConsoleSecurity`
- `0x180019b8f`: `ConsoleSecurity`
- `0x180019bf9`: `Creating default security descriptor in the registry and using it`
- `0x180019bc5`: `SecurityDescriptor registry not found`
- `0x180019c9b`: `Found security descriptor and using it.`
- `0x180019c4f`: `CreateDefault`
- `0x180019d1c`: `CTSSecurityDescriptor::Initialize`
- `0x180019cd3`: `Using security descriptor for this listener`
- `0x180019d12`: `CopySource failed: 0x%x in %s`
- `0x180019b24`: `Services`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::Initialize(CTSSecurityDescriptor *this, const unsigned __int16 *a2, void *a3)
{
  PSECURITY_DESCRIPTOR v3; // rdi
  unsigned __int16 *v6; // r14
  int Default; // ebx
  void *v8; // rax
  __int16 *v9; // rdx
  __int64 v10; // rax
  void *v11; // rsp
  CTSSecurityDescriptor *v12; // rcx
  int v13; // r8d
  int v14; // r9d
  CTSSecurityDescriptor *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  const unsigned __int16 *v18; // rbx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  int v22; // eax
  void *v23; // rcx
  void *v25; // [rsp+38h] [rbp-8h]
  unsigned __int16 v26[4]; // [rsp+40h] [rbp+0h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp+8h] BYREF
  unsigned int v28[2]; // [rsp+50h] [rbp+10h] BYREF
  unsigned __int16 *v29; // [rsp+58h] [rbp+18h] BYREF
  void *Block; // [rsp+60h] [rbp+20h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor[2]; // [rsp+68h] [rbp+28h] BYREF

  v3 = a3;
  v6 = 0;
  v29 = 0;
  ObjectDescriptor[0] = 0;
  Block = 0;
  *(_QWORD *)v28 = 0;
  if ( !a2 )
  {
    Default = -2147024809;
    goto LABEL_47;
  }
  if ( a3 )
    goto LABEL_38;
  Default = StringCbLengthW(a2, 0x42u, (unsigned __int64 *)v28);
  if ( Default < 0 )
  {
    if ( (unsigned int)dword_1800DA020 <= 3 )
      goto LABEL_46;
    v29 = (unsigned __int16 *)"Initialize";
    v27 = (unsigned __int64)"StringCbLength";
    *(_QWORD *)v26 = "Warning HResult failed";
    v25 = &v29;
    v8 = v26;
    v9 = word_1800CA9C2;
    goto LABEL_7;
  }
  v27 = *(_QWORD *)v28 + 126LL;
  *(_QWORD *)v26 = *(_QWORD *)v28 + 126LL;
  v10 = *(_QWORD *)v28 + 141LL;
  if ( *(_QWORD *)v28 + 141LL < (unsigned __int64)(*(_QWORD *)v28 + 126LL) )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
  ObjectDescriptor[1] = v26;
  if ( v26 )
  {
    Default = StringCbPrintfW(
                v26,
                *(_QWORD *)v28 + 126LL,
                L"%s\\%s",
                L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
                a2);
    if ( Default < 0 )
    {
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        *(_QWORD *)v26 = "Initialize";
        v27 = (unsigned __int64)"StringCbPrintf";
        v29 = (unsigned __int16 *)"Warning HResult failed";
        v25 = v26;
        v8 = &v29;
        v9 = &word_1800CAA66;
LABEL_7:
        v28[0] = Default;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800DA020,
          (_DWORD)v9,
          0,
          0,
          (__int64)v8,
          (__int64)&v27,
          (__int64)v28,
          (__int64)v25);
        goto LABEL_46;
      }
      goto LABEL_46;
    }
    if ( CTSSecurityDescriptor::GetSDValueFromRegistry(v12, v26, L"Security", (unsigned __int8 **)&Block, v28) >= 0 )
    {
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        *(_QWORD *)v26 = a2;
        v27 = (unsigned __int64)"Using security descriptor for this listener";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)this,
          (unsigned int)&dword_1800CAA34,
          v13,
          v14,
          (__int64)&v27,
          (__int64)v26);
      }
    }
    else
    {
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        *(_QWORD *)v26 = a2;
        v27 = (unsigned __int64)"SecurityDescriptor not found for this listener";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)this,
          (unsigned int)&word_1800CA916,
          v13,
          v14,
          (__int64)&v27,
          (__int64)v26);
      }
      if ( (unsigned int)_o__wcsicmp(a2, L"Console") && (unsigned int)_o__wcsicmp(a2, L"Services") )
      {
        v18 = L"DefaultSecurity";
      }
      else if ( (unsigned int)dword_1800DA020 <= 5 )
      {
        v18 = L"ConsoleSecurity";
      }
      else
      {
        *(_QWORD *)v26 = L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations";
        v18 = L"ConsoleSecurity";
        v27 = (unsigned __int64)L"ConsoleSecurity";
        *(_QWORD *)v28 = "Querying Console default security descriptor";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v15,
          (unsigned int)&unk_1800CA948,
          v16,
          v17,
          (__int64)v28,
          (__int64)&v27,
          (__int64)v26);
      }
      if ( CTSSecurityDescriptor::GetSDValueFromRegistry(
             v15,
             L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
             v18,
             (unsigned __int8 **)&Block,
             v28) < 0 )
      {
        if ( (unsigned int)dword_1800DA020 > 5 )
        {
          *(_QWORD *)v26 = v18;
          v27 = (unsigned __int64)"SecurityDescriptor registry not found";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            (_DWORD)this,
            (unsigned int)&dword_1800CAA04,
            v19,
            v20,
            (__int64)&v27,
            (__int64)v26);
        }
        if ( (unsigned int)dword_1800DA020 > 5 )
        {
          *(_QWORD *)v26 = "Creating default security descriptor in the registry and using it";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1800DA020,
            (unsigned int)&word_1800CA8B6,
            0,
            0,
            (__int64)v26);
        }
        Default = CTSSecurityDescriptor::CreateDefault(this, ObjectDescriptor);
        if ( Default < 0 )
        {
          if ( (unsigned int)dword_1800DA020 > 3 )
          {
            *(_QWORD *)v26 = "Initialize";
            v27 = (unsigned __int64)"CreateDefault";
            v29 = (unsigned __int16 *)"Warning HResult failed";
            v25 = v26;
            v8 = &v29;
            v9 = (__int16 *)&unk_1800CAAA8;
            goto LABEL_7;
          }
LABEL_46:
          if ( Default >= 0 )
            goto LABEL_49;
          goto LABEL_47;
        }
        v3 = ObjectDescriptor[0];
LABEL_38:
        v21 = CTSSecurityDescriptor::CopySource(this, a2, &v29);
        Default = v21;
        if ( v21 >= 0 )
        {
          v22 = CTSSecurityDescriptor::InitializeFromBlob(this, v3);
          Default = v22;
          if ( v22 >= 0 )
          {
            v23 = (void *)*((_QWORD *)this + 2);
            if ( v23 )
              operator delete(v23);
            *((_QWORD *)this + 2) = v29;
            v6 = 0;
            goto LABEL_46;
          }
          _DbgPrintMessage(
            8,
            "InitializeFromBlob failed: 0x%x in %s",
            (unsigned int)v22,
            "CTSSecurityDescriptor::Initialize");
        }
        else
        {
          _DbgPrintMessage(8, "CopySource failed: 0x%x in %s", (unsigned int)v21, "CTSSecurityDescriptor::Initialize");
        }
        v6 = v29;
        goto LABEL_46;
      }
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        *(_QWORD *)v26 = "Found security descriptor and using it.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_1800DA020,
          (unsigned int)&byte_1800CAB27,
          0,
          0,
          (__int64)v26);
      }
    }
    v3 = Block;
    goto LABEL_38;
  }
  Default = -2147024882;
LABEL_47:
  if ( v6 )
    operator delete(v6);
LABEL_49:
  if ( Block )
    operator delete(Block);
  if ( ObjectDescriptor[0] )
    RtlDeleteSecurityObject(ObjectDescriptor);
  return (unsigned int)Default;
}

```

## disassembly

```asm
0x1800198c4  mov     [rsp-8+arg_8], rdx
0x1800198c9  mov     [rsp-8+arg_0], rcx
0x1800198ce  push    rbp
0x1800198cf  push    rdi
0x1800198d0  push    r12
0x1800198d2  push    r14
0x1800198d4  push    r15
0x1800198d6  sub     rsp, 80h
0x1800198dd  lea     rbp, [rsp+40h]
0x1800198e2  mov     [rbp+60h+arg_10], rbx
0x1800198e9  mov     [rbp+60h+arg_18], rsi
0x1800198f0  mov     rax, cs:__security_cookie
0x1800198f7  xor     rax, rbp
0x1800198fa  mov     [rbp+60h+var_28], rax
0x1800198fe  mov     rdi, r8
0x180019901  mov     rsi, rdx
0x180019904  mov     r15, rcx
0x180019907  xor     r14d, r14d
0x18001990a  mov     [rbp+60h+var_48], r14
0x18001990e  mov     [rbp+60h+ObjectDescriptor], r14
0x180019912  mov     [rbp+60h+Block], r14
0x180019916  mov     qword ptr [rbp+60h+var_50], r14
0x18001991a  test    rdx, rdx
0x18001991d  jnz     short loc_180019929
0x18001991f  mov     ebx, 80070057h
0x180019924  jmp     loc_180019D6A
0x180019929  test    r8, r8
0x18001992c  jnz     loc_180019D00
0x180019932  lea     r8, [rbp+60h+var_50]; unsigned __int64 *
0x180019936  mov     edx, 42h ; 'B'; unsigned __int64
0x18001993b  mov     rcx, rsi; unsigned __int16 *
0x18001993e  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180019943  mov     ebx, eax
0x180019945  test    eax, eax
0x180019947  jns     short loc_1800199BE
0x180019949  mov     ecx, cs:dword_1800DA020
0x18001994f  cmp     ecx, 3
0x180019952  jbe     loc_180019D66
0x180019958  lea     rax, aInitialize; "Initialize"
0x18001995f  mov     [rbp+60h+var_48], rax
0x180019963  lea     rax, aStringcblength; "StringCbLength"
0x18001996a  mov     [rbp+60h+var_58], rax
0x18001996e  lea     rax, aWarningHresult; "Warning HResult failed"
0x180019975  mov     qword ptr [rbp+60h+var_60], rax
0x180019979  lea     rax, [rbp+60h+var_48]
0x18001997d  mov     [rsp+0A0h+var_68], rax
0x180019982  lea     rax, [rbp+60h+var_50]
0x180019986  mov     [rsp+0A0h+var_70], rax
0x18001998b  lea     rax, [rbp+60h+var_58]
0x18001998f  mov     [rsp+0A0h+var_78], rax
0x180019994  lea     rax, [rbp+60h+var_60]
0x180019998  lea     rdx, word_1800CA9C2
0x18001999f  xor     r9d, r9d
0x1800199a2  mov     [rbp+60h+var_50], ebx
0x1800199a5  mov     [rsp+0A0h+var_80], rax
0x1800199aa  xor     r8d, r8d
0x1800199ad  lea     rcx, dword_1800DA020
0x1800199b4  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800199b9  jmp     loc_180019D66
0x1800199be  mov     rdx, qword ptr [rbp+60h+var_50]
0x1800199c2  add     rdx, 7Eh ; '~'
0x1800199c6  mov     [rbp+60h+var_58], rdx
0x1800199ca  mov     qword ptr [rbp+60h+var_60], rdx
0x1800199ce  lea     rax, [rdx+0Fh]
0x1800199d2  cmp     rax, rdx
0x1800199d5  ja      short loc_1800199E1
0x1800199d7  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800199e1  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800199e5  call    _alloca_probe
0x1800199ea  sub     rsp, rax
0x1800199ed  lea     rdi, [rsp+0A0h+var_60]
0x1800199f2  mov     [rbp+60h+var_30], rdi
0x1800199f6  jmp     short loc_180019A26
0x1800199f8  call    _o__resetstkoflw_0
0x1800199fd  xor     edi, edi
0x1800199ff  mov     [rbp+60h+var_30], rdi
0x180019a03  mov     r8, qword ptr [rbp+60h+var_60]
0x180019a07  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x180019a0e  lea     ecx, [rdi+8]; int
0x180019a11  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019a16  mov     r15, [rbp+60h+arg_0]
0x180019a1a  mov     rsi, [rbp+60h+arg_8]
0x180019a1e  mov     r14, [rbp+60h+var_48]
0x180019a22  mov     rdx, [rbp+60h+var_58]; unsigned __int64
0x180019a26  test    rdi, rdi
0x180019a29  jnz     short loc_180019A35
0x180019a2b  mov     ebx, 8007000Eh
0x180019a30  jmp     loc_180019D6A
0x180019a35  mov     [rsp+0A0h+var_80], rsi
0x180019a3a  lea     r12, aSystemCurrentc_8; "System\\CurrentControlSet\\Control\\Ter"...
0x180019a41  mov     r9, r12
0x180019a44  lea     r8, aSS_0; "%s\\%s"
0x180019a4b  mov     rcx, rdi; unsigned __int16 *
0x180019a4e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019a53  mov     ebx, eax
0x180019a55  test    eax, eax
0x180019a57  jns     short loc_180019AB4
0x180019a59  mov     eax, cs:dword_1800DA020
0x180019a5f  cmp     eax, 3
0x180019a62  jbe     loc_180019D66
0x180019a68  lea     rax, aInitialize; "Initialize"
0x180019a6f  mov     qword ptr [rbp+60h+var_60], rax
0x180019a73  lea     rax, aStringcbprintf_1; "StringCbPrintf"
0x180019a7a  mov     [rbp+60h+var_58], rax
0x180019a7e  lea     rax, aWarningHresult; "Warning HResult failed"
0x180019a85  mov     [rbp+60h+var_48], rax
0x180019a89  lea     rax, [rbp+60h+var_60]
0x180019a8d  mov     [rsp+0A0h+var_68], rax
0x180019a92  lea     rax, [rbp+60h+var_50]
0x180019a96  mov     [rsp+0A0h+var_70], rax
0x180019a9b  lea     rax, [rbp+60h+var_58]
0x180019a9f  mov     [rsp+0A0h+var_78], rax
0x180019aa4  lea     rax, [rbp+60h+var_48]
0x180019aa8  lea     rdx, word_1800CAA66
0x180019aaf  jmp     loc_18001999F
0x180019ab4  lea     rax, [rbp+60h+var_50]
0x180019ab8  mov     [rsp+0A0h+var_80], rax; unsigned int *
0x180019abd  lea     r9, [rbp+60h+Block]; unsigned __int8 **
0x180019ac1  lea     r8, aSecurity; "Security"
0x180019ac8  mov     rdx, rdi; unsigned __int16 *
0x180019acb  call    ?GetSDValueFromRegistry@CTSSecurityDescriptor@@IEAAJPEBG0PEAPEAEPEAK@Z; CTSSecurityDescriptor::GetSDValueFromRegistry(ushort const *,ushort const *,uchar * *,ulong *)
0x180019ad0  test    eax, eax
0x180019ad2  mov     eax, cs:dword_1800DA020
0x180019ad8  jns     loc_180019CCA
0x180019ade  cmp     eax, 5
0x180019ae1  jbe     short loc_180019B10
0x180019ae3  mov     qword ptr [rbp+60h+var_60], rsi
0x180019ae7  lea     rax, aSecuritydescri_1; "SecurityDescriptor not found for this l"...
0x180019aee  mov     [rbp+60h+var_58], rax
0x180019af2  lea     rax, [rbp+60h+var_60]
0x180019af6  mov     [rsp+0A0h+var_78], rax
0x180019afb  lea     rax, [rbp+60h+var_58]
0x180019aff  mov     [rsp+0A0h+var_80], rax
0x180019b04  lea     rdx, word_1800CA916
0x180019b0b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180019b10  lea     rdx, aConsole; "Console"
0x180019b17  mov     rcx, rsi
0x180019b1a  call    cs:__imp__o__wcsicmp
0x180019b20  test    eax, eax
0x180019b22  jz      short loc_180019B41
0x180019b24  lea     rdx, aServices_0; "Services"
0x180019b2b  mov     rcx, rsi
0x180019b2e  call    cs:__imp__o__wcsicmp
0x180019b34  test    eax, eax
0x180019b36  jz      short loc_180019B41
0x180019b38  lea     rbx, aDefaultsecurit; "DefaultSecurity"
0x180019b3f  jmp     short loc_180019B96
0x180019b41  mov     eax, cs:dword_1800DA020
0x180019b47  cmp     eax, 5
0x180019b4a  jbe     short loc_180019B8F
0x180019b4c  mov     qword ptr [rbp+60h+var_60], r12
0x180019b50  lea     rbx, aConsolesecurit; "ConsoleSecurity"
0x180019b57  mov     [rbp+60h+var_58], rbx
0x180019b5b  lea     rax, aQueryingConsol; "Querying Console default security descr"...
0x180019b62  mov     qword ptr [rbp+60h+var_50], rax
0x180019b66  lea     rax, [rbp+60h+var_60]
0x180019b6a  mov     [rsp+0A0h+var_70], rax
0x180019b6f  lea     rax, [rbp+60h+var_58]
0x180019b73  mov     [rsp+0A0h+var_78], rax
0x180019b78  lea     rax, [rbp+60h+var_50]
0x180019b7c  mov     [rsp+0A0h+var_80], rax
0x180019b81  lea     rdx, unk_1800CA948
0x180019b88  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180019b8d  jmp     short loc_180019B96
0x180019b8f  lea     rbx, aConsolesecurit; "ConsoleSecurity"
0x180019b96  lea     rax, [rbp+60h+var_50]
0x180019b9a  mov     [rsp+0A0h+var_80], rax; unsigned int *
0x180019b9f  lea     r9, [rbp+60h+Block]; unsigned __int8 **
0x180019ba3  mov     r8, rbx; unsigned __int16 *
0x180019ba6  mov     rdx, r12; unsigned __int16 *
0x180019ba9  call    ?GetSDValueFromRegistry@CTSSecurityDescriptor@@IEAAJPEBG0PEAPEAEPEAK@Z; CTSSecurityDescriptor::GetSDValueFromRegistry(ushort const *,ushort const *,uchar * *,ulong *)
0x180019bae  test    eax, eax
0x180019bb0  mov     eax, cs:dword_1800DA020
0x180019bb6  jns     loc_180019C96
0x180019bbc  cmp     eax, 5
0x180019bbf  jbe     short loc_180019BEE
0x180019bc1  mov     qword ptr [rbp+60h+var_60], rbx
0x180019bc5  lea     rax, aSecuritydescri; "SecurityDescriptor registry not found"
0x180019bcc  mov     [rbp+60h+var_58], rax
0x180019bd0  lea     rax, [rbp+60h+var_60]
0x180019bd4  mov     [rsp+0A0h+var_78], rax
0x180019bd9  lea     rax, [rbp+60h+var_58]
0x180019bdd  mov     [rsp+0A0h+var_80], rax
0x180019be2  lea     rdx, dword_1800CAA04
0x180019be9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180019bee  mov     eax, cs:dword_1800DA020
0x180019bf4  cmp     eax, 5
0x180019bf7  jbe     short loc_180019C26
0x180019bf9  lea     rax, aCreatingDefaul; "Creating default security descriptor in"...
0x180019c00  mov     qword ptr [rbp+60h+var_60], rax
0x180019c04  lea     rax, [rbp+60h+var_60]
0x180019c08  mov     [rsp+0A0h+var_80], rax
0x180019c0d  xor     r9d, r9d
0x180019c10  xor     r8d, r8d
0x180019c13  lea     rdx, word_1800CA8B6
0x180019c1a  lea     rcx, dword_1800DA020
0x180019c21  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180019c26  lea     rdx, [rbp+60h+ObjectDescriptor]; void **
0x180019c2a  call    ?CreateDefault@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z; CTSSecurityDescriptor::CreateDefault(void * *)
0x180019c2f  mov     ebx, eax
0x180019c31  test    eax, eax
0x180019c33  jns     short loc_180019C90
0x180019c35  mov     eax, cs:dword_1800DA020
0x180019c3b  cmp     eax, 3
0x180019c3e  jbe     loc_180019D66
0x180019c44  lea     rax, aInitialize; "Initialize"
0x180019c4b  mov     qword ptr [rbp+60h+var_60], rax
0x180019c4f  lea     rax, aCreatedefault; "CreateDefault"
0x180019c56  mov     [rbp+60h+var_58], rax
0x180019c5a  lea     rax, aWarningHresult; "Warning HResult failed"
0x180019c61  mov     [rbp+60h+var_48], rax
0x180019c65  lea     rax, [rbp+60h+var_60]
0x180019c69  mov     [rsp+0A0h+var_68], rax
0x180019c6e  lea     rax, [rbp+60h+var_50]
0x180019c72  mov     [rsp+0A0h+var_70], rax
0x180019c77  lea     rax, [rbp+60h+var_58]
0x180019c7b  mov     [rsp+0A0h+var_78], rax
0x180019c80  lea     rax, [rbp+60h+var_48]
0x180019c84  lea     rdx, unk_1800CAAA8
0x180019c8b  jmp     loc_18001999F
0x180019c90  mov     rdi, [rbp+60h+ObjectDescriptor]
0x180019c94  jmp     short loc_180019D00
0x180019c96  cmp     eax, 5
0x180019c99  jbe     short loc_180019CFC
0x180019c9b  lea     rax, aFoundSecurityD; "Found security descriptor and using it."
0x180019ca2  mov     qword ptr [rbp+60h+var_60], rax
0x180019ca6  lea     rax, [rbp+60h+var_60]
0x180019caa  mov     [rsp+0A0h+var_80], rax
0x180019caf  xor     r9d, r9d
0x180019cb2  xor     r8d, r8d
0x180019cb5  lea     rdx, byte_1800CAB27
0x180019cbc  lea     rcx, dword_1800DA020
0x180019cc3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180019cc8  jmp     short loc_180019CFC
0x180019cca  cmp     eax, 5
0x180019ccd  jbe     short loc_180019CFC
0x180019ccf  mov     qword ptr [rbp+60h+var_60], rsi
0x180019cd3  lea     rax, aUsingSecurityD; "Using security descriptor for this list"...
0x180019cda  mov     [rbp+60h+var_58], rax
0x180019cde  lea     rax, [rbp+60h+var_60]
0x180019ce2  mov     [rsp+0A0h+var_78], rax
0x180019ce7  lea     rax, [rbp+60h+var_58]
0x180019ceb  mov     [rsp+0A0h+var_80], rax
0x180019cf0  lea     rdx, dword_1800CAA34
0x180019cf7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180019cfc  mov     rdi, [rbp+60h+Block]
0x180019d00  lea     r8, [rbp+60h+var_48]; unsigned __int16 **
0x180019d04  mov     rdx, rsi; unsigned __int16 *
0x180019d07  call    ?CopySource@CTSSecurityDescriptor@@IEAAJPEBGPEAPEAG@Z; CTSSecurityDescriptor::CopySource(ushort const *,ushort * *)
0x180019d0c  mov     ebx, eax
0x180019d0e  test    eax, eax
0x180019d10  jns     short loc_180019D33
0x180019d12  lea     rdx, aCopysourceFail; "CopySource failed: 0x%x in %s"
0x180019d19  mov     r8d, eax
0x180019d1c  lea     r9, aCtssecuritydes_2; "CTSSecurityDescriptor::Initialize"
0x180019d23  mov     ecx, 8; int
0x180019d28  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180019d2d  mov     r14, [rbp+60h+var_48]
0x180019d31  jmp     short loc_180019D66
0x180019d33  mov     rdx, rdi; void *
0x180019d36  mov     rcx, r15; this
0x180019d39  call    ?InitializeFromBlob@CTSSecurityDescriptor@@QEAAJPEAX@Z; CTSSecurityDescriptor::InitializeFromBlob(void *)
0x180019d3e  mov     ebx, eax
0x180019d40  test    eax, eax
0x180019d42  jns     short loc_180019D4D
0x180019d44  lea     rdx, aInitializefrom; "InitializeFromBlob failed: 0x%x in %s"
0x180019d4b  jmp     short loc_180019D19
0x180019d4d  mov     rcx, [r15+10h]; Block
0x180019d51  test    rcx, rcx
0x180019d54  jz      short loc_180019D5B
0x180019d56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019d5b  mov     rax, [rbp+60h+var_48]
0x180019d5f  mov     [r15+10h], rax
0x180019d63  xor     r14d, r14d
0x180019d66  test    ebx, ebx
0x180019d68  jns     short loc_180019D77
0x180019d6a  test    r14, r14
0x180019d6d  jz      short loc_180019D77
0x180019d6f  mov     rcx, r14; Block
0x180019d72  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019d77  mov     rcx, [rbp+60h+Block]; Block
0x180019d7b  test    rcx, rcx
0x180019d7e  jz      short loc_180019D85
0x180019d80  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019d85  cmp     [rbp+60h+ObjectDescriptor], 0
0x180019d8a  jz      short loc_180019D96
0x180019d8c  lea     rcx, [rbp+60h+ObjectDescriptor]; ObjectDescriptor
0x180019d90  call    cs:__imp_RtlDeleteSecurityObject
0x180019d96  mov     eax, ebx
0x180019d98  mov     rcx, [rbp+60h+var_28]
0x180019d9c  xor     rcx, rbp; StackCookie
0x180019d9f  call    __security_check_cookie
0x180019da4  mov     rbx, [rbp+60h+arg_10]
0x180019dab  mov     rsi, [rbp+60h+arg_18]
0x180019db2  lea     rsp, [rbp+40h]
0x180019db6  pop     r15
0x180019db8  pop     r14
0x180019dba  pop     r12
0x180019dbc  pop     rdi
0x180019dbd  pop     rbp
  ... truncated ...
```
