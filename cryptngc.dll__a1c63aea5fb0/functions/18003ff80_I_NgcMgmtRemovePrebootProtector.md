# I_NgcMgmtRemovePrebootProtector

- ea: `0x18003ff80`
- end: `0x1800400ef`
- name: `I_NgcMgmtRemovePrebootProtector`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180041068`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x18003ff80`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004006a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004006a`
- `RPCRT4!NdrClientCall3` at `0x18003ffd6`
- `RPCRT4!NdrClientCall3` at `0x18003ffd6`

## string_xrefs

- `0x1800400a1`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtRemovePrebootProtector(PSRWLOCK *a1, int a2)
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
  v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004F630, 0xAu, 0, v3).Pointer;
  Pointer = (unsigned int)v4.Pointer;
  v8.Pointer = v4.Pointer;
  if ( SLODWORD(v4.Simple) < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x3A7,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)Pointer,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v8.Pointer) = Pointer;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&unk_180062CB0,
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
0x18003ff80  mov     [rsp+arg_8], rdx
0x18003ff85  mov     [rsp+arg_0], rcx
0x18003ff8a  push    rbx
0x18003ff8b  push    rdi
0x18003ff8c  sub     rsp, 48h
0x18003ff90  mov     rdi, rdx
0x18003ff93  xor     ebx, ebx
0x18003ff95  lea     ecx, [rbx+14h]
0x18003ff98  mov     [rsp+58h+var_20], ecx
0x18003ff9c  xor     eax, eax
0x18003ff9e  mov     [rsp+58h+arg_18], eax
0x18003ffa2  cmp     eax, ecx
0x18003ffa4  jnb     loc_180040085
0x18003ffaa  mov     rcx, [rsp+58h+arg_0]
0x18003ffaf  mov     rcx, [rcx]; SRWLock
0x18003ffb2  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x18003ffb7  mov     [rsp+58h+arg_10], 0
0x18003ffc0  mov     [rsp+58h+var_38], rdi
0x18003ffc5  mov     r9, rax
0x18003ffc8  xor     r8d, r8d; pReturnValue
0x18003ffcb  lea     edx, [r8+0Ah]; nProcNum
0x18003ffcf  lea     rcx, stru_18004F630; pProxyInfo
0x18003ffd6  call    cs:__imp_NdrClientCall3
0x18003ffdc  mov     rbx, rax
0x18003ffdf  mov     [rsp+58h+arg_10], rax
0x18003ffe4  mov     [rsp+58h+var_28], eax
0x18003ffe8  jmp     loc_180040085
0x18003ffed  mov     ecx, eax
0x18003ffef  test    eax, eax
0x18003fff1  jle     short loc_18003FFFC
0x18003fff3  movzx   ecx, ax
0x18003fff6  or      ecx, 80070000h; int
0x18003fffc  mov     ebx, ecx
0x18003fffe  mov     [rsp+58h+var_28], ecx
0x180040002  mov     byte ptr [rsp+58h+arg_10], 0
0x180040007  lea     rdx, [rsp+58h+arg_10]; bool *
0x18004000c  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x180040011  test    al, al
0x180040013  jz      short loc_180040085
0x180040015  mov     eax, cs:dword_18006E000
0x18004001b  cmp     eax, 4
0x18004001e  jbe     short loc_180040047
0x180040020  mov     [rsp+58h+var_24], ecx
0x180040024  lea     rax, [rsp+58h+var_24]
0x180040029  mov     [rsp+58h+var_38], rax
0x18004002e  xor     r9d, r9d
0x180040031  xor     r8d, r8d
0x180040034  lea     rdx, byte_180062CE7
0x18004003b  lea     rcx, dword_18006E000
0x180040042  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180040047  cmp     byte ptr [rsp+58h+arg_10], 0
0x18004004c  jz      short loc_180040065
0x18004004e  mov     rcx, [rsp+58h+arg_0]
0x180040053  mov     rcx, [rcx]; this
0x180040056  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x18004005b  mov     ebx, eax
0x18004005d  mov     [rsp+58h+var_28], eax
0x180040061  test    eax, eax
0x180040063  js      short loc_180040085
0x180040065  mov     ecx, 1F4h; dwMilliseconds
0x18004006a  call    cs:__imp_Sleep
0x180040070  nop
0x180040071  mov     eax, [rsp+58h+arg_18]
0x180040075  inc     eax
0x180040077  mov     rdi, [rsp+58h+arg_8]
0x18004007c  mov     ecx, [rsp+58h+var_20]
0x180040080  jmp     loc_18003FF9E
0x180040085  test    ebx, ebx
0x180040087  jns     short loc_1800400E6
0x180040089  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180040090  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180040095  test    al, al
0x180040097  jz      short loc_1800400B4
0x180040099  mov     rcx, [rsp+58h]; this
0x18004009e  mov     r9d, ebx; char *
0x1800400a1  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x1800400a8  mov     edx, 3A7h; void *
0x1800400ad  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800400b2  jmp     short loc_1800400E6
0x1800400b4  mov     eax, cs:dword_18006E000
0x1800400ba  cmp     eax, 2
0x1800400bd  jbe     short loc_1800400E6
0x1800400bf  mov     dword ptr [rsp+58h+arg_10], ebx
0x1800400c3  lea     rax, [rsp+58h+arg_10]
0x1800400c8  mov     [rsp+58h+var_38], rax
0x1800400cd  xor     r9d, r9d
0x1800400d0  xor     r8d, r8d
0x1800400d3  lea     rdx, unk_180062CB0
0x1800400da  lea     rcx, dword_18006E000
0x1800400e1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800400e6  mov     eax, ebx
0x1800400e8  add     rsp, 48h
0x1800400ec  pop     rdi
0x1800400ed  pop     rbx
0x1800400ee  retn
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
