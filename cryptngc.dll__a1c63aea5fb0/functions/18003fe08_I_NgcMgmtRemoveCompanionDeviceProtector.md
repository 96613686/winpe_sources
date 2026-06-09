# I_NgcMgmtRemoveCompanionDeviceProtector

- ea: `0x18003fe08`
- end: `0x18003ff77`
- name: `I_NgcMgmtRemoveCompanionDeviceProtector`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040ec4`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x18003fe08`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003fef2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003fef2`
- `RPCRT4!NdrClientCall3` at `0x18003fe5e`
- `RPCRT4!NdrClientCall3` at `0x18003fe5e`

## string_xrefs

- `0x18003ff29`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtRemoveCompanionDeviceProtector(PSRWLOCK *a1, int a2)
{
  void *v3; // rax
  CLIENT_CALL_RETURN v4; // rax
  unsigned int Pointer; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  CLIENT_CALL_RETURN v8; // [rsp+70h] [rbp+18h] BYREF
  int v9; // [rsp+78h] [rbp+20h]

  v9 = 0;
  v3 = NgcUtils::RpcClient::BindingHandle(*a1);
  v8.Simple = 0;
  v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004F630, 0xCu, 0, v3).Pointer;
  Pointer = (unsigned int)v4.Pointer;
  v8.Pointer = v4.Pointer;
  if ( SLODWORD(v4.Simple) < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x43D,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)Pointer,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v8.Pointer) = Pointer;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&unk_180062B50,
        0,
        0,
        (__int64)&v8);
    }
  }
  return Pointer;
}

```

## disassembly

```asm
0x18003fe08  mov     [rsp+arg_8], rdx
0x18003fe0d  mov     [rsp+arg_0], rcx
0x18003fe12  push    rbx
0x18003fe13  push    rdi
0x18003fe14  sub     rsp, 48h
0x18003fe18  mov     rdi, rdx
0x18003fe1b  xor     ebx, ebx
0x18003fe1d  lea     ecx, [rbx+14h]
0x18003fe20  mov     [rsp+58h+var_20], ecx
0x18003fe24  xor     eax, eax
0x18003fe26  mov     [rsp+58h+arg_18], eax
0x18003fe2a  cmp     eax, ecx
0x18003fe2c  jnb     loc_18003FF0D
0x18003fe32  mov     rcx, [rsp+58h+arg_0]
0x18003fe37  mov     rcx, [rcx]; SRWLock
0x18003fe3a  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x18003fe3f  mov     [rsp+58h+arg_10], 0
0x18003fe48  mov     [rsp+58h+var_38], rdi
0x18003fe4d  mov     r9, rax
0x18003fe50  xor     r8d, r8d; pReturnValue
0x18003fe53  lea     edx, [r8+0Ch]; nProcNum
0x18003fe57  lea     rcx, stru_18004F630; pProxyInfo
0x18003fe5e  call    cs:__imp_NdrClientCall3
0x18003fe64  mov     rbx, rax
0x18003fe67  mov     [rsp+58h+arg_10], rax
0x18003fe6c  mov     [rsp+58h+var_28], eax
0x18003fe70  jmp     loc_18003FF0D
0x18003fe75  mov     ecx, eax
0x18003fe77  test    eax, eax
0x18003fe79  jle     short loc_18003FE84
0x18003fe7b  movzx   ecx, ax
0x18003fe7e  or      ecx, 80070000h; int
0x18003fe84  mov     ebx, ecx
0x18003fe86  mov     [rsp+58h+var_28], ecx
0x18003fe8a  mov     byte ptr [rsp+58h+arg_10], 0
0x18003fe8f  lea     rdx, [rsp+58h+arg_10]; bool *
0x18003fe94  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003fe99  test    al, al
0x18003fe9b  jz      short loc_18003FF0D
0x18003fe9d  mov     eax, cs:dword_18006E000
0x18003fea3  cmp     eax, 4
0x18003fea6  jbe     short loc_18003FECF
0x18003fea8  mov     [rsp+58h+var_24], ecx
0x18003feac  lea     rax, [rsp+58h+var_24]
0x18003feb1  mov     [rsp+58h+var_38], rax
0x18003feb6  xor     r9d, r9d
0x18003feb9  xor     r8d, r8d
0x18003febc  lea     rdx, byte_180062B8F
0x18003fec3  lea     rcx, dword_18006E000
0x18003feca  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003fecf  cmp     byte ptr [rsp+58h+arg_10], 0
0x18003fed4  jz      short loc_18003FEED
0x18003fed6  mov     rcx, [rsp+58h+arg_0]
0x18003fedb  mov     rcx, [rcx]; this
0x18003fede  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x18003fee3  mov     ebx, eax
0x18003fee5  mov     [rsp+58h+var_28], eax
0x18003fee9  test    eax, eax
0x18003feeb  js      short loc_18003FF0D
0x18003feed  mov     ecx, 1F4h; dwMilliseconds
0x18003fef2  call    cs:__imp_Sleep
0x18003fef8  nop
0x18003fef9  mov     eax, [rsp+58h+arg_18]
0x18003fefd  inc     eax
0x18003feff  mov     rdi, [rsp+58h+arg_8]
0x18003ff04  mov     ecx, [rsp+58h+var_20]
0x18003ff08  jmp     loc_18003FE26
0x18003ff0d  test    ebx, ebx
0x18003ff0f  jns     short loc_18003FF6E
0x18003ff11  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003ff18  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003ff1d  test    al, al
0x18003ff1f  jz      short loc_18003FF3C
0x18003ff21  mov     rcx, [rsp+58h]; this
0x18003ff26  mov     r9d, ebx; char *
0x18003ff29  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x18003ff30  mov     edx, 43Dh; void *
0x18003ff35  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003ff3a  jmp     short loc_18003FF6E
0x18003ff3c  mov     eax, cs:dword_18006E000
0x18003ff42  cmp     eax, 2
0x18003ff45  jbe     short loc_18003FF6E
0x18003ff47  mov     dword ptr [rsp+58h+arg_10], ebx
0x18003ff4b  lea     rax, [rsp+58h+arg_10]
0x18003ff50  mov     [rsp+58h+var_38], rax
0x18003ff55  xor     r9d, r9d
0x18003ff58  xor     r8d, r8d
0x18003ff5b  lea     rdx, unk_180062B50
0x18003ff62  lea     rcx, dword_18006E000
0x18003ff69  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003ff6e  mov     eax, ebx
0x18003ff70  add     rsp, 48h
0x18003ff74  pop     rdi
0x18003ff75  pop     rbx
0x18003ff76  retn
0x18004acbf  push    rbp
0x18004acc1  sub     rsp, 30h
0x18004acc5  mov     rbp, rdx
0x18004acc8  mov     rcx, [rcx]
0x18004accb  mov     ecx, [rcx]; ExceptionCode
0x18004accd  call    cs:__imp_RpcExceptionFilter
0x18004acd3  nop
0x18004acd4  add     rsp, 30h
0x18004acd8  pop     rbp
0x18004acd9  retn
```
