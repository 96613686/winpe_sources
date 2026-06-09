# CTSSecurityDescriptor::Initialize(ushort const *,void *)

- ea: `0x18000a66c`
- end: `0x18000ab7a`
- name: `?Initialize@CTSSecurityDescriptor@@QEAAJPEBGPEAX@Z`
- size: `1294`
- prototype: `__int64 __fastcall(CTSSecurityDescriptor *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a5e0`

## callees

- `0x180001120`
- `0x180003478`
- `0x1800077a0`
- `0x180009998`
- `0x18000a66c`
- `0x180022080`
- `0x180022190`
- `0x1800236a8`
- `0x180028254`
- `0x18002c434`
- `0x18004072c`
- `0x18004e850`
- `0x18004f174`
- `0x18004f318`
- `0x18008db9c`
- `0x180099530`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a8c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a8dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a8c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000a8dc`
- `ntdll!RtlDeleteSecurityObject` at `0x18000ab44`
- `ntdll!RtlDeleteSecurityObject` at `0x18000ab44`

## string_xrefs

- `0x18000a869`: `Security`
- `0x18000a8ec`: `DefaultSecurity`
- `0x18000a88f`: `SecurityDescriptor not found for this listener`
- `0x18000a904`: `ConsoleSecurity`
- `0x18000a943`: `ConsoleSecurity`
- `0x18000a979`: `SecurityDescriptor registry not found`
- `0x18000a90f`: `Querying Console default security descriptor`
- `0x18000aa03`: `CreateDefault`
- `0x18000a9ad`: `Creating default security descriptor in the registry and using it`
- `0x18000aa87`: `Using security descriptor for this listener`
- `0x18000aa4f`: `Found security descriptor and using it.`
- `0x18000aac6`: `CopySource failed: 0x%x in %s`
- `0x18000aad0`: `CTSSecurityDescriptor::Initialize`
- `0x18000a8d2`: `Services`

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
    if ( (unsigned int)dword_1800DF020 <= 3 )
      goto LABEL_46;
    v29 = (unsigned __int16 *)"Initialize";
    v27 = (unsigned __int64)"StringCbLength";
    *(_QWORD *)v26 = "Warning HResult failed";
    v25 = &v29;
    v8 = v26;
    v9 = word_1800CFB4A;
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
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        *(_QWORD *)v26 = "Initialize";
        v27 = (unsigned __int64)"StringCbPrintf";
        v29 = (unsigned __int16 *)"Warning HResult failed";
        v25 = v26;
        v8 = &v29;
        v9 = (__int16 *)&dword_1800CFBBC;
LABEL_7:
        v28[0] = Default;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800DF020,
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
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        *(_QWORD *)v26 = a2;
        v27 = (unsigned __int64)"Using security descriptor for this listener";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)this,
          (unsigned int)&word_1800CFBFE,
          v13,
          v14,
          (__int64)&v27,
          (__int64)v26);
      }
    }
    else
    {
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        *(_QWORD *)v26 = a2;
        v27 = (unsigned __int64)"SecurityDescriptor not found for this listener";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)this,
          (unsigned int)&word_1800CFA9E,
          v13,
          v14,
          (__int64)&v27,
          (__int64)v26);
      }
      if ( (unsigned int)_o__wcsicmp(a2, L"Console") && (unsigned int)_o__wcsicmp(a2, L"Services") )
      {
        v18 = L"DefaultSecurity";
      }
      else if ( (unsigned int)dword_1800DF020 <= 5 )
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
          (unsigned int)&unk_1800CFAD0,
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
        if ( (unsigned int)dword_1800DF020 > 5 )
        {
          *(_QWORD *)v26 = v18;
          v27 = (unsigned __int64)"SecurityDescriptor registry not found";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            (_DWORD)this,
            (unsigned int)&dword_1800CFB8C,
            v19,
            v20,
            (__int64)&v27,
            (__int64)v26);
        }
        if ( (unsigned int)dword_1800DF020 > 5 )
        {
          *(_QWORD *)v26 = "Creating default security descriptor in the registry and using it";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&dword_1800DF020,
            (unsigned int)&word_1800CFA3E,
            0,
            0,
            (__int64)v26);
        }
        Default = CTSSecurityDescriptor::CreateDefault(this, ObjectDescriptor);
        if ( Default < 0 )
        {
          if ( (unsigned int)dword_1800DF020 > 3 )
          {
            *(_QWORD *)v26 = "Initialize";
            v27 = (unsigned __int64)"CreateDefault";
            v29 = (unsigned __int16 *)"Warning HResult failed";
            v25 = v26;
            v8 = &v29;
            v9 = (__int16 *)&unk_1800CFC30;
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
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        *(_QWORD *)v26 = "Found security descriptor and using it.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_1800DF020,
          (unsigned int)&byte_1800CFCAF,
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
0x18000a66c  mov     [rsp-8+arg_8], rdx
0x18000a671  mov     [rsp-8+arg_0], rcx
0x18000a676  push    rbp
0x18000a677  push    rdi
0x18000a678  push    r12
0x18000a67a  push    r14
0x18000a67c  push    r15
0x18000a67e  sub     rsp, 80h
0x18000a685  lea     rbp, [rsp+40h]
0x18000a68a  mov     [rbp+60h+arg_10], rbx
0x18000a691  mov     [rbp+60h+arg_18], rsi
0x18000a698  mov     rax, cs:__security_cookie
0x18000a69f  xor     rax, rbp
0x18000a6a2  mov     [rbp+60h+var_28], rax
0x18000a6a6  mov     rdi, r8
0x18000a6a9  mov     rsi, rdx
0x18000a6ac  mov     r15, rcx
0x18000a6af  xor     r14d, r14d
0x18000a6b2  mov     [rbp+60h+var_48], r14
0x18000a6b6  mov     [rbp+60h+ObjectDescriptor], r14
0x18000a6ba  mov     [rbp+60h+Block], r14
0x18000a6be  mov     qword ptr [rbp+60h+var_50], r14
0x18000a6c2  test    rdx, rdx
0x18000a6c5  jnz     short loc_18000A6D1
0x18000a6c7  mov     ebx, 80070057h
0x18000a6cc  jmp     loc_18000AB1E
0x18000a6d1  test    r8, r8
0x18000a6d4  jnz     loc_18000AAB4
0x18000a6da  lea     r8, [rbp+60h+var_50]; unsigned __int64 *
0x18000a6de  mov     edx, 42h ; 'B'; unsigned __int64
0x18000a6e3  mov     rcx, rsi; unsigned __int16 *
0x18000a6e6  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000a6eb  mov     ebx, eax
0x18000a6ed  test    eax, eax
0x18000a6ef  jns     short loc_18000A766
0x18000a6f1  mov     ecx, cs:dword_1800DF020
0x18000a6f7  cmp     ecx, 3
0x18000a6fa  jbe     loc_18000AB1A
0x18000a700  lea     rax, aInitialize; "Initialize"
0x18000a707  mov     [rbp+60h+var_48], rax
0x18000a70b  lea     rax, aStringcblength; "StringCbLength"
0x18000a712  mov     [rbp+60h+var_58], rax
0x18000a716  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000a71d  mov     qword ptr [rbp+60h+var_60], rax
0x18000a721  lea     rax, [rbp+60h+var_48]
0x18000a725  mov     [rsp+0A0h+var_68], rax
0x18000a72a  lea     rax, [rbp+60h+var_50]
0x18000a72e  mov     [rsp+0A0h+var_70], rax
0x18000a733  lea     rax, [rbp+60h+var_58]
0x18000a737  mov     [rsp+0A0h+var_78], rax
0x18000a73c  lea     rax, [rbp+60h+var_60]
0x18000a740  lea     rdx, word_1800CFB4A
0x18000a747  xor     r9d, r9d
0x18000a74a  mov     [rbp+60h+var_50], ebx
0x18000a74d  mov     [rsp+0A0h+var_80], rax
0x18000a752  xor     r8d, r8d
0x18000a755  lea     rcx, dword_1800DF020
0x18000a75c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000a761  jmp     loc_18000AB1A
0x18000a766  mov     rdx, qword ptr [rbp+60h+var_50]
0x18000a76a  add     rdx, 7Eh ; '~'
0x18000a76e  mov     [rbp+60h+var_58], rdx
0x18000a772  mov     qword ptr [rbp+60h+var_60], rdx
0x18000a776  lea     rax, [rdx+0Fh]
0x18000a77a  cmp     rax, rdx
0x18000a77d  ja      short loc_18000A789
0x18000a77f  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000a789  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000a78d  call    _alloca_probe
0x18000a792  sub     rsp, rax
0x18000a795  lea     rdi, [rsp+0A0h+var_60]
0x18000a79a  mov     [rbp+60h+var_30], rdi
0x18000a79e  jmp     short loc_18000A7CE
0x18000a7a0  call    _o__resetstkoflw_0
0x18000a7a5  xor     edi, edi
0x18000a7a7  mov     [rbp+60h+var_30], rdi
0x18000a7ab  mov     r8, qword ptr [rbp+60h+var_60]
0x18000a7af  lea     rdx, aAllocaFailedFo; "alloca failed for %d bytes"
0x18000a7b6  lea     ecx, [rdi+8]; int
0x18000a7b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000a7be  mov     r15, [rbp+60h+arg_0]
0x18000a7c2  mov     rsi, [rbp+60h+arg_8]
0x18000a7c6  mov     r14, [rbp+60h+var_48]
0x18000a7ca  mov     rdx, [rbp+60h+var_58]; unsigned __int64
0x18000a7ce  test    rdi, rdi
0x18000a7d1  jnz     short loc_18000A7DD
0x18000a7d3  mov     ebx, 8007000Eh
0x18000a7d8  jmp     loc_18000AB1E
0x18000a7dd  mov     [rsp+0A0h+var_80], rsi
0x18000a7e2  lea     r12, aSystemCurrentc_8; "System\\CurrentControlSet\\Control\\Ter"...
0x18000a7e9  mov     r9, r12
0x18000a7ec  lea     r8, aSS_0; "%s\\%s"
0x18000a7f3  mov     rcx, rdi; unsigned __int16 *
0x18000a7f6  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a7fb  mov     ebx, eax
0x18000a7fd  test    eax, eax
0x18000a7ff  jns     short loc_18000A85C
0x18000a801  mov     eax, cs:dword_1800DF020
0x18000a807  cmp     eax, 3
0x18000a80a  jbe     loc_18000AB1A
0x18000a810  lea     rax, aInitialize; "Initialize"
0x18000a817  mov     qword ptr [rbp+60h+var_60], rax
0x18000a81b  lea     rax, aStringcbprintf_1; "StringCbPrintf"
0x18000a822  mov     [rbp+60h+var_58], rax
0x18000a826  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000a82d  mov     [rbp+60h+var_48], rax
0x18000a831  lea     rax, [rbp+60h+var_60]
0x18000a835  mov     [rsp+0A0h+var_68], rax
0x18000a83a  lea     rax, [rbp+60h+var_50]
0x18000a83e  mov     [rsp+0A0h+var_70], rax
0x18000a843  lea     rax, [rbp+60h+var_58]
0x18000a847  mov     [rsp+0A0h+var_78], rax
0x18000a84c  lea     rax, [rbp+60h+var_48]
0x18000a850  lea     rdx, dword_1800CFBBC
0x18000a857  jmp     loc_18000A747
0x18000a85c  lea     rax, [rbp+60h+var_50]
0x18000a860  mov     [rsp+0A0h+var_80], rax; unsigned int *
0x18000a865  lea     r9, [rbp+60h+Block]; unsigned __int8 **
0x18000a869  lea     r8, aSecurity; "Security"
0x18000a870  mov     rdx, rdi; unsigned __int16 *
0x18000a873  call    ?GetSDValueFromRegistry@CTSSecurityDescriptor@@IEAAJPEBG0PEAPEAEPEAK@Z; CTSSecurityDescriptor::GetSDValueFromRegistry(ushort const *,ushort const *,uchar * *,ulong *)
0x18000a878  test    eax, eax
0x18000a87a  mov     eax, cs:dword_1800DF020
0x18000a880  jns     loc_18000AA7E
0x18000a886  cmp     eax, 5
0x18000a889  jbe     short loc_18000A8B8
0x18000a88b  mov     qword ptr [rbp+60h+var_60], rsi
0x18000a88f  lea     rax, aSecuritydescri_1; "SecurityDescriptor not found for this l"...
0x18000a896  mov     [rbp+60h+var_58], rax
0x18000a89a  lea     rax, [rbp+60h+var_60]
0x18000a89e  mov     [rsp+0A0h+var_78], rax
0x18000a8a3  lea     rax, [rbp+60h+var_58]
0x18000a8a7  mov     [rsp+0A0h+var_80], rax
0x18000a8ac  lea     rdx, word_1800CFA9E
0x18000a8b3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000a8b8  lea     rdx, aConsole; "Console"
0x18000a8bf  mov     rcx, rsi
0x18000a8c2  call    cs:__imp__o__wcsicmp
0x18000a8c9  nop     dword ptr [rax+rax+00h]
0x18000a8ce  test    eax, eax
0x18000a8d0  jz      short loc_18000A8F5
0x18000a8d2  lea     rdx, aServices_0; "Services"
0x18000a8d9  mov     rcx, rsi
0x18000a8dc  call    cs:__imp__o__wcsicmp
0x18000a8e3  nop     dword ptr [rax+rax+00h]
0x18000a8e8  test    eax, eax
0x18000a8ea  jz      short loc_18000A8F5
0x18000a8ec  lea     rbx, aDefaultsecurit; "DefaultSecurity"
0x18000a8f3  jmp     short loc_18000A94A
0x18000a8f5  mov     eax, cs:dword_1800DF020
0x18000a8fb  cmp     eax, 5
0x18000a8fe  jbe     short loc_18000A943
0x18000a900  mov     qword ptr [rbp+60h+var_60], r12
0x18000a904  lea     rbx, aConsolesecurit; "ConsoleSecurity"
0x18000a90b  mov     [rbp+60h+var_58], rbx
0x18000a90f  lea     rax, aQueryingConsol; "Querying Console default security descr"...
0x18000a916  mov     qword ptr [rbp+60h+var_50], rax
0x18000a91a  lea     rax, [rbp+60h+var_60]
0x18000a91e  mov     [rsp+0A0h+var_70], rax
0x18000a923  lea     rax, [rbp+60h+var_58]
0x18000a927  mov     [rsp+0A0h+var_78], rax
0x18000a92c  lea     rax, [rbp+60h+var_50]
0x18000a930  mov     [rsp+0A0h+var_80], rax
0x18000a935  lea     rdx, unk_1800CFAD0
0x18000a93c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000a941  jmp     short loc_18000A94A
0x18000a943  lea     rbx, aConsolesecurit; "ConsoleSecurity"
0x18000a94a  lea     rax, [rbp+60h+var_50]
0x18000a94e  mov     [rsp+0A0h+var_80], rax; unsigned int *
0x18000a953  lea     r9, [rbp+60h+Block]; unsigned __int8 **
0x18000a957  mov     r8, rbx; unsigned __int16 *
0x18000a95a  mov     rdx, r12; unsigned __int16 *
0x18000a95d  call    ?GetSDValueFromRegistry@CTSSecurityDescriptor@@IEAAJPEBG0PEAPEAEPEAK@Z; CTSSecurityDescriptor::GetSDValueFromRegistry(ushort const *,ushort const *,uchar * *,ulong *)
0x18000a962  test    eax, eax
0x18000a964  mov     eax, cs:dword_1800DF020
0x18000a96a  jns     loc_18000AA4A
0x18000a970  cmp     eax, 5
0x18000a973  jbe     short loc_18000A9A2
0x18000a975  mov     qword ptr [rbp+60h+var_60], rbx
0x18000a979  lea     rax, aSecuritydescri; "SecurityDescriptor registry not found"
0x18000a980  mov     [rbp+60h+var_58], rax
0x18000a984  lea     rax, [rbp+60h+var_60]
0x18000a988  mov     [rsp+0A0h+var_78], rax
0x18000a98d  lea     rax, [rbp+60h+var_58]
0x18000a991  mov     [rsp+0A0h+var_80], rax
0x18000a996  lea     rdx, dword_1800CFB8C
0x18000a99d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000a9a2  mov     eax, cs:dword_1800DF020
0x18000a9a8  cmp     eax, 5
0x18000a9ab  jbe     short loc_18000A9DA
0x18000a9ad  lea     rax, aCreatingDefaul; "Creating default security descriptor in"...
0x18000a9b4  mov     qword ptr [rbp+60h+var_60], rax
0x18000a9b8  lea     rax, [rbp+60h+var_60]
0x18000a9bc  mov     [rsp+0A0h+var_80], rax
0x18000a9c1  xor     r9d, r9d
0x18000a9c4  xor     r8d, r8d
0x18000a9c7  lea     rdx, word_1800CFA3E
0x18000a9ce  lea     rcx, dword_1800DF020
0x18000a9d5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000a9da  lea     rdx, [rbp+60h+ObjectDescriptor]; void **
0x18000a9de  call    ?CreateDefault@CTSSecurityDescriptor@@IEAAJPEAPEAX@Z; CTSSecurityDescriptor::CreateDefault(void * *)
0x18000a9e3  mov     ebx, eax
0x18000a9e5  test    eax, eax
0x18000a9e7  jns     short loc_18000AA44
0x18000a9e9  mov     eax, cs:dword_1800DF020
0x18000a9ef  cmp     eax, 3
0x18000a9f2  jbe     loc_18000AB1A
0x18000a9f8  lea     rax, aInitialize; "Initialize"
0x18000a9ff  mov     qword ptr [rbp+60h+var_60], rax
0x18000aa03  lea     rax, aCreatedefault; "CreateDefault"
0x18000aa0a  mov     [rbp+60h+var_58], rax
0x18000aa0e  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000aa15  mov     [rbp+60h+var_48], rax
0x18000aa19  lea     rax, [rbp+60h+var_60]
0x18000aa1d  mov     [rsp+0A0h+var_68], rax
0x18000aa22  lea     rax, [rbp+60h+var_50]
0x18000aa26  mov     [rsp+0A0h+var_70], rax
0x18000aa2b  lea     rax, [rbp+60h+var_58]
0x18000aa2f  mov     [rsp+0A0h+var_78], rax
0x18000aa34  lea     rax, [rbp+60h+var_48]
0x18000aa38  lea     rdx, unk_1800CFC30
0x18000aa3f  jmp     loc_18000A747
0x18000aa44  mov     rdi, [rbp+60h+ObjectDescriptor]
0x18000aa48  jmp     short loc_18000AAB4
0x18000aa4a  cmp     eax, 5
0x18000aa4d  jbe     short loc_18000AAB0
0x18000aa4f  lea     rax, aFoundSecurityD; "Found security descriptor and using it."
0x18000aa56  mov     qword ptr [rbp+60h+var_60], rax
0x18000aa5a  lea     rax, [rbp+60h+var_60]
0x18000aa5e  mov     [rsp+0A0h+var_80], rax
0x18000aa63  xor     r9d, r9d
0x18000aa66  xor     r8d, r8d
0x18000aa69  lea     rdx, byte_1800CFCAF
0x18000aa70  lea     rcx, dword_1800DF020
0x18000aa77  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000aa7c  jmp     short loc_18000AAB0
0x18000aa7e  cmp     eax, 5
0x18000aa81  jbe     short loc_18000AAB0
0x18000aa83  mov     qword ptr [rbp+60h+var_60], rsi
0x18000aa87  lea     rax, aUsingSecurityD; "Using security descriptor for this list"...
0x18000aa8e  mov     [rbp+60h+var_58], rax
0x18000aa92  lea     rax, [rbp+60h+var_60]
0x18000aa96  mov     [rsp+0A0h+var_78], rax
0x18000aa9b  lea     rax, [rbp+60h+var_58]
0x18000aa9f  mov     [rsp+0A0h+var_80], rax
0x18000aaa4  lea     rdx, word_1800CFBFE
0x18000aaab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000aab0  mov     rdi, [rbp+60h+Block]
0x18000aab4  lea     r8, [rbp+60h+var_48]; unsigned __int16 **
0x18000aab8  mov     rdx, rsi; unsigned __int16 *
0x18000aabb  call    ?CopySource@CTSSecurityDescriptor@@IEAAJPEBGPEAPEAG@Z; CTSSecurityDescriptor::CopySource(ushort const *,ushort * *)
0x18000aac0  mov     ebx, eax
0x18000aac2  test    eax, eax
0x18000aac4  jns     short loc_18000AAE7
0x18000aac6  lea     rdx, aCopysourceFail; "CopySource failed: 0x%x in %s"
0x18000aacd  mov     r8d, eax
0x18000aad0  lea     r9, aCtssecuritydes_2; "CTSSecurityDescriptor::Initialize"
0x18000aad7  mov     ecx, 8; int
0x18000aadc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000aae1  mov     r14, [rbp+60h+var_48]
0x18000aae5  jmp     short loc_18000AB1A
0x18000aae7  mov     rdx, rdi; void *
0x18000aaea  mov     rcx, r15; this
0x18000aaed  call    ?InitializeFromBlob@CTSSecurityDescriptor@@QEAAJPEAX@Z; CTSSecurityDescriptor::InitializeFromBlob(void *)
0x18000aaf2  mov     ebx, eax
0x18000aaf4  test    eax, eax
0x18000aaf6  jns     short loc_18000AB01
0x18000aaf8  lea     rdx, aInitializefrom; "InitializeFromBlob failed: 0x%x in %s"
0x18000aaff  jmp     short loc_18000AACD
0x18000ab01  mov     rcx, [r15+10h]; Block
0x18000ab05  test    rcx, rcx
0x18000ab08  jz      short loc_18000AB0F
0x18000ab0a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ab0f  mov     rax, [rbp+60h+var_48]
0x18000ab13  mov     [r15+10h], rax
0x18000ab17  xor     r14d, r14d
0x18000ab1a  test    ebx, ebx
0x18000ab1c  jns     short loc_18000AB2B
0x18000ab1e  test    r14, r14
0x18000ab21  jz      short loc_18000AB2B
0x18000ab23  mov     rcx, r14; Block
0x18000ab26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ab2b  mov     rcx, [rbp+60h+Block]; Block
0x18000ab2f  test    rcx, rcx
0x18000ab32  jz      short loc_18000AB39
0x18000ab34  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ab39  cmp     [rbp+60h+ObjectDescriptor], 0
0x18000ab3e  jz      short loc_18000AB50
0x18000ab40  lea     rcx, [rbp+60h+ObjectDescriptor]; ObjectDescriptor
0x18000ab44  call    cs:__imp_RtlDeleteSecurityObject
0x18000ab4b  nop     dword ptr [rax+rax+00h]
0x18000ab50  mov     eax, ebx
0x18000ab52  mov     rcx, [rbp+60h+var_28]
0x18000ab56  xor     rcx, rbp; StackCookie
0x18000ab59  call    __security_check_cookie
0x18000ab5e  mov     rbx, [rbp+60h+arg_10]
0x18000ab65  mov     rsi, [rbp+60h+arg_18]
0x18000ab6c  lea     rsp, [rbp+40h]
0x18000ab70  pop     r15
0x18000ab72  pop     r14
  ... truncated ...
```
