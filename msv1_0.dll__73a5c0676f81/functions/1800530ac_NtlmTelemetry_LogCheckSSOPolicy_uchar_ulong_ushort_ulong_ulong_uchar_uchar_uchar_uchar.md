# NtlmTelemetry::LogCheckSSOPolicy(uchar,ulong,ushort,ulong,ulong,uchar,uchar,uchar,uchar)

- ea: `0x1800530ac`
- end: `0x180053299`
- name: `?LogCheckSSOPolicy@NtlmTelemetry@@YAXEKGKKEEEE@Z`
- size: `493`
- prototype: `void __fastcall(NtlmTelemetry *__hidden this, unsigned __int8, unsigned int, unsigned __int16, unsigned int, char, char, char, char, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18004de00`

## callees

- `0x180001b3c`
- `0x18001eaec`
- `0x18001f878`
- `0x180024bd0`
- `0x18002fb50`
- `0x1800530ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800531aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800531bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800531aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800531bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NtlmTelemetry::LogCheckSSOPolicy(
        NtlmTelemetry *this,
        int a2,
        __int16 a3,
        __int64 a4,
        unsigned int a5,
        char a6,
        char a7,
        char a8,
        char a9)
{
  char v11; // si
  __int16 v12; // r14
  __int16 v13; // r15
  __int64 v14; // rcx
  __int64 v15; // r8
  char v16; // [rsp+A0h] [rbp-80h] BYREF
  char v17; // [rsp+A1h] [rbp-7Fh] BYREF
  char v18; // [rsp+A2h] [rbp-7Eh] BYREF
  char v19; // [rsp+A3h] [rbp-7Dh] BYREF
  _BYTE v20[2]; // [rsp+A4h] [rbp-7Ch] BYREF
  __int16 v21; // [rsp+A6h] [rbp-7Ah] BYREF
  __int16 v22; // [rsp+A8h] [rbp-78h] BYREF
  __int16 v23; // [rsp+AAh] [rbp-76h] BYREF
  int v24; // [rsp+ACh] [rbp-74h] BYREF
  DWORD CurrentProcessId; // [rsp+B0h] [rbp-70h] BYREF
  int v26; // [rsp+B4h] [rbp-6Ch] BYREF
  DWORD v27; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-60h] BYREF
  char *v29; // [rsp+C8h] [rbp-58h] BYREF
  char *v30; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+D8h] [rbp-48h] BYREF
  _BYTE v32[32]; // [rsp+E0h] [rbp-40h] BYREF
  char v33; // [rsp+100h] [rbp-20h] BYREF
  char v34; // [rsp+300h] [rbp+1E0h] BYREF
  int v35; // [rsp+700h] [rbp+5E0h]
  _BYTE v36[8]; // [rsp+728h] [rbp+608h] BYREF

  v11 = (char)this;
  v12 = NtLmGlobalOrgSSOControl;
  v13 = NtLmGlobalMSASSOControl;
  if ( dword_1800861D8 && (unsigned __int8)tlgKeywordOn(&dword_1800861D8, 0x400000000000LL) )
  {
    SspTelemetry::ClientImageInfo::ClientImageInfo((SspTelemetry::ClientImageInfo *)v32, LsaFunctions);
    if ( (unsigned int)dword_1800861D8 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1800861D8, 0x400000000000LL) )
      {
        v28 = 0x1000000;
        v16 = a9;
        v17 = a8;
        v18 = a7;
        v19 = a6;
        v21 = v12;
        v22 = v13;
        v23 = a3;
        v24 = a2;
        v20[0] = v11;
        v29 = &v33;
        v30 = &v34;
        CurrentProcessId = GetCurrentProcessId();
        v26 = v35;
        v27 = GetCurrentProcessId();
        v31 = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          v14,
          byte_18007A939,
          v15,
          &v31,
          &v27,
          &v26,
          &CurrentProcessId,
          &v30,
          &v29,
          v20,
          &v24,
          &v23,
          &v22,
          &v21,
          &v19,
          &v18,
          &v17,
          &v16,
          &v28);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(v36);
  }
}

```

## disassembly

```asm
0x1800530ac  push    rbp
0x1800530ae  push    rbx
0x1800530af  push    rsi
0x1800530b0  push    rdi
0x1800530b1  push    r14
0x1800530b3  push    r15
0x1800530b5  lea     rbp, [rsp-628h]
0x1800530bd  sub     rsp, 748h
0x1800530c4  mov     rax, cs:__security_cookie
0x1800530cb  xor     rax, rsp
0x1800530ce  mov     [rbp+650h+var_40], rax
0x1800530d5  movzx   ebx, r8w
0x1800530d9  mov     edi, edx
0x1800530db  mov     sil, cl
0x1800530de  mov     r14d, cs:NtLmGlobalOrgSSOControl
0x1800530e5  mov     r15d, cs:NtLmGlobalMSASSOControl
0x1800530ec  mov     eax, cs:dword_1800861D8
0x1800530f2  test    eax, eax
0x1800530f4  jz      loc_18005327A
0x1800530fa  mov     rdx, 400000000000h
0x180053104  lea     rcx, dword_1800861D8
0x18005310b  call    _tlgKeywordOn
0x180053110  test    al, al
0x180053112  jz      loc_18005327A
0x180053118  mov     rdx, cs:LsaFunctions; struct _LSA_SECPKG_FUNCTION_TABLE *
0x18005311f  lea     rcx, [rbp+650h+var_690]; this
0x180053123  call    ??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z; SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)
0x180053128  nop
0x180053129  mov     eax, cs:dword_1800861D8
0x18005312f  cmp     eax, 5
0x180053132  jbe     loc_18005326E
0x180053138  mov     rdx, 400000000000h
0x180053142  lea     rcx, dword_1800861D8
0x180053149  call    _tlgKeywordOn
0x18005314e  test    al, al
0x180053150  jz      loc_18005326E
0x180053156  mov     [rbp+650h+var_6B0], 1000000h
0x18005315e  mov     al, [rbp+650h+arg_40]
0x180053164  mov     [rbp+650h+var_6D0], al
0x180053167  mov     al, [rbp+650h+arg_38]
0x18005316d  mov     [rbp+650h+var_6CF], al
0x180053170  mov     al, [rbp+650h+arg_30]
0x180053176  mov     [rbp+650h+var_6CE], al
0x180053179  mov     al, [rbp+650h+arg_28]
0x18005317f  mov     [rbp+650h+var_6CD], al
0x180053182  mov     [rbp+650h+var_6CA], r14w
0x180053187  mov     [rbp+650h+var_6C8], r15w
0x18005318c  mov     [rbp+650h+var_6C6], bx
0x180053190  mov     [rbp+650h+var_6C4], edi
0x180053193  mov     [rbp+650h+var_6CC], sil
0x180053197  lea     rax, [rbp+650h+var_670]
0x18005319b  mov     [rbp+650h+var_6A8], rax
0x18005319f  lea     rax, [rbp+650h+var_470]
0x1800531a6  mov     [rbp+650h+var_6A0], rax
0x1800531aa  call    cs:__imp_GetCurrentProcessId
0x1800531b0  mov     [rbp+650h+var_6C0], eax
0x1800531b3  mov     eax, [rbp+650h+var_70]
0x1800531b9  mov     [rbp+650h+var_6BC], eax
0x1800531bc  call    cs:__imp_GetCurrentProcessId
0x1800531c2  mov     [rbp+650h+var_6B8], eax
0x1800531c5  mov     [rbp+650h+var_698], 1
0x1800531cd  lea     rax, [rbp+650h+var_6B0]
0x1800531d1  mov     [rsp+770h+var_6E0], rax
0x1800531d9  lea     rax, [rbp+650h+var_6D0]
0x1800531dd  mov     [rsp+770h+var_6E8], rax
0x1800531e5  lea     rax, [rbp+650h+var_6CF]
0x1800531e9  mov     [rsp+770h+var_6F0], rax
0x1800531f1  lea     rax, [rbp+650h+var_6CE]
0x1800531f5  mov     [rsp+770h+var_6F8], rax
0x1800531fa  lea     rax, [rbp+650h+var_6CD]
0x1800531fe  mov     [rsp+770h+var_700], rax
0x180053203  lea     rax, [rbp+650h+var_6CA]
0x180053207  mov     [rsp+770h+var_708], rax
0x18005320c  lea     rax, [rbp+650h+var_6C8]
0x180053210  mov     [rsp+770h+var_710], rax
0x180053215  lea     rax, [rbp+650h+var_6C6]
0x180053219  mov     [rsp+770h+var_718], rax
0x18005321e  lea     rax, [rbp+650h+var_6C4]
0x180053222  mov     [rsp+770h+var_720], rax
0x180053227  lea     rax, [rbp+650h+var_6CC]
0x18005322b  mov     [rsp+770h+var_728], rax
0x180053230  lea     rax, [rbp+650h+var_6A8]
0x180053234  mov     [rsp+770h+var_730], rax
0x180053239  lea     rax, [rbp+650h+var_6A0]
0x18005323d  mov     [rsp+770h+var_738], rax
0x180053242  lea     rax, [rbp+650h+var_6C0]
0x180053246  mov     [rsp+770h+var_740], rax
0x18005324b  lea     rax, [rbp+650h+var_6BC]
0x18005324f  mov     [rsp+770h+var_748], rax
0x180053254  lea     rax, [rbp+650h+var_6B8]
0x180053258  mov     [rsp+770h+var_750], rax
0x18005325d  lea     r9, [rbp+650h+var_698]
0x180053261  lea     rdx, byte_18007A939
0x180053268  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$00@@U2@U?$_tlgWrapperByVal@$01@@U5@U5@U4@U4@U4@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapperByVal@$01@@6655552@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x18005326d  nop
0x18005326e  lea     rcx, [rbp+650h+var_48]
0x180053275  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROCESS_BASIC_INFORMATION@@P6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROCESS_BASIC_INFORMATION *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROCESS_BASIC_INFORMATION *,_PROCESS_BASIC_INFORMATION *,0,std::nullptr_t>>(void)
0x18005327a  mov     rcx, [rbp+650h+var_40]
0x180053281  xor     rcx, rsp; StackCookie
0x180053284  call    __security_check_cookie
0x180053289  add     rsp, 748h
0x180053290  pop     r15
0x180053292  pop     r14
0x180053294  pop     rdi
0x180053295  pop     rsi
0x180053296  pop     rbx
0x180053297  pop     rbp
0x180053298  retn
```
