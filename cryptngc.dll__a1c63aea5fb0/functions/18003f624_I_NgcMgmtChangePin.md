# I_NgcMgmtChangePin

- ea: `0x18003f624`
- end: `0x18003f7a7`
- name: `I_NgcMgmtChangePin`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800407e4`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x18003f624`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f71c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f71c`
- `RPCRT4!NdrClientCall3` at `0x18003f688`
- `RPCRT4!NdrClientCall3` at `0x18003f688`

## string_xrefs

- `0x18003f758`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtChangePin(PSRWLOCK *a1, int a2)
{
  void *v3; // rax
  CLIENT_CALL_RETURN v4; // rax
  unsigned int Pointer; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  CLIENT_CALL_RETURN v8; // [rsp+78h] [rbp+20h] BYREF

  v3 = NgcUtils::RpcClient::BindingHandle(*a1);
  v8.Simple = 0;
  v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004F630, 2u, 0, v3).Pointer;
  Pointer = (unsigned int)v4.Pointer;
  v8.Pointer = v4.Pointer;
  if ( SLODWORD(v4.Simple) < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)Pointer,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v8.Pointer) = Pointer;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_180063055,
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
0x18003f624  mov     [rsp+arg_10], r8
0x18003f629  mov     [rsp+arg_8], rdx
0x18003f62e  mov     [rsp+arg_0], rcx
0x18003f633  push    rbx
0x18003f634  push    rsi
0x18003f635  push    rdi
0x18003f636  sub     rsp, 40h
0x18003f63a  mov     rdi, r8
0x18003f63d  mov     rsi, rdx
0x18003f640  xor     ebx, ebx
0x18003f642  lea     ecx, [rbx+14h]
0x18003f645  mov     [rsp+58h+var_1C], ecx
0x18003f649  xor     eax, eax
0x18003f64b  mov     [rsp+58h+var_24], eax
0x18003f64f  cmp     eax, ecx
0x18003f651  jnb     loc_18003F73C
0x18003f657  mov     rcx, [rsp+58h+arg_0]
0x18003f65c  mov     rcx, [rcx]; SRWLock
0x18003f65f  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x18003f664  mov     [rsp+58h+arg_18], 0
0x18003f66d  mov     [rsp+58h+var_30], rdi
0x18003f672  mov     [rsp+58h+var_38], rsi
0x18003f677  mov     r9, rax
0x18003f67a  xor     r8d, r8d; pReturnValue
0x18003f67d  lea     edx, [r8+2]; nProcNum
0x18003f681  lea     rcx, stru_18004F630; pProxyInfo
0x18003f688  call    cs:__imp_NdrClientCall3
0x18003f68e  mov     rbx, rax
0x18003f691  mov     [rsp+58h+arg_18], rax
0x18003f696  mov     [rsp+58h+var_28], eax
0x18003f69a  jmp     loc_18003F73C
0x18003f69f  mov     ecx, eax
0x18003f6a1  test    eax, eax
0x18003f6a3  jle     short loc_18003F6AE
0x18003f6a5  movzx   ecx, ax
0x18003f6a8  or      ecx, 80070000h; int
0x18003f6ae  mov     ebx, ecx
0x18003f6b0  mov     [rsp+58h+var_28], ecx
0x18003f6b4  mov     byte ptr [rsp+58h+arg_18], 0
0x18003f6b9  lea     rdx, [rsp+58h+arg_18]; bool *
0x18003f6be  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003f6c3  test    al, al
0x18003f6c5  jz      short loc_18003F73C
0x18003f6c7  mov     eax, cs:dword_18006E000
0x18003f6cd  cmp     eax, 4
0x18003f6d0  jbe     short loc_18003F6F9
0x18003f6d2  mov     [rsp+58h+var_20], ecx
0x18003f6d6  lea     rax, [rsp+58h+var_20]
0x18003f6db  mov     [rsp+58h+var_38], rax
0x18003f6e0  xor     r9d, r9d
0x18003f6e3  xor     r8d, r8d
0x18003f6e6  lea     rdx, byte_18006307F
0x18003f6ed  lea     rcx, dword_18006E000
0x18003f6f4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f6f9  cmp     byte ptr [rsp+58h+arg_18], 0
0x18003f6fe  jz      short loc_18003F717
0x18003f700  mov     rcx, [rsp+58h+arg_0]
0x18003f705  mov     rcx, [rcx]; this
0x18003f708  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x18003f70d  mov     ebx, eax
0x18003f70f  mov     [rsp+58h+var_28], eax
0x18003f713  test    eax, eax
0x18003f715  js      short loc_18003F73C
0x18003f717  mov     ecx, 1F4h; dwMilliseconds
0x18003f71c  call    cs:__imp_Sleep
0x18003f722  nop
0x18003f723  mov     eax, [rsp+58h+var_24]
0x18003f727  inc     eax
0x18003f729  mov     rdi, [rsp+58h+arg_10]
0x18003f72e  mov     rsi, [rsp+58h+arg_8]
0x18003f733  mov     ecx, [rsp+58h+var_1C]
0x18003f737  jmp     loc_18003F64B
0x18003f73c  test    ebx, ebx
0x18003f73e  jns     short loc_18003F79D
0x18003f740  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003f747  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003f74c  test    al, al
0x18003f74e  jz      short loc_18003F76B
0x18003f750  mov     rcx, [rsp+58h]; this
0x18003f755  mov     r9d, ebx; char *
0x18003f758  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x18003f75f  mov     edx, 125h; void *
0x18003f764  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003f769  jmp     short loc_18003F79D
0x18003f76b  mov     eax, cs:dword_18006E000
0x18003f771  cmp     eax, 2
0x18003f774  jbe     short loc_18003F79D
0x18003f776  mov     dword ptr [rsp+58h+arg_18], ebx
0x18003f77a  lea     rax, [rsp+58h+arg_18]
0x18003f77f  mov     [rsp+58h+var_38], rax
0x18003f784  xor     r9d, r9d
0x18003f787  xor     r8d, r8d
0x18003f78a  lea     rdx, byte_180063055
0x18003f791  lea     rcx, dword_18006E000
0x18003f798  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f79d  mov     eax, ebx
0x18003f79f  add     rsp, 40h
0x18003f7a3  pop     rdi
0x18003f7a4  pop     rsi
0x18003f7a5  pop     rbx
0x18003f7a6  retn
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
