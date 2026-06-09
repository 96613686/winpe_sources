# I_NgcTicketCreateForSmartCard(std::shared_ptr<NgcUtils::RpcClient> const &,_NGC_RPC_GESTURE_INFO *,ushort *,int,unsigned __int64 *)

- ea: `0x18004149c`
- end: `0x180041657`
- name: `?I_NgcTicketCreateForSmartCard@@YAJAEBV?$shared_ptr@VRpcClient@NgcUtils@@@std@@PEAU_NGC_RPC_GESTURE_INFO@@PEAGHPEA_K@Z`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180041814`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x180041460`
- `0x18004149c`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800415c0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800415c0`
- `RPCRT4!NdrClientCall3` at `0x18004151c`
- `RPCRT4!NdrClientCall3` at `0x18004151c`

## string_xrefs

- `0x180041602`: `onecore\ds\security\ngc\kspsvc\ticket\ngcauthticketrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcTicketCreateForSmartCard(PSRWLOCK *a1, int a2, __int64 a3, unsigned int a4)
{
  void *v5; // rax
  int Pointer; // eax
  unsigned int v7; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned int v10; // [rsp+98h] [rbp+20h] BYREF

  v10 = a4;
  v5 = NgcUtils::RpcClient::BindingHandle(*a1);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004FB20, 2u, 0, v5).Pointer;
  v7 = Pointer;
  if ( Pointer < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\ticket\\ngcauthticketrpcclient.cpp",
        (const char *)v7,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v10 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_1800632A1,
        0,
        0,
        (__int64)&v10);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18004149c  mov     rax, rsp
0x18004149f  mov     [rax+20h], r9d
0x1800414a3  mov     [rax+18h], r8
0x1800414a7  mov     [rax+10h], rdx
0x1800414ab  mov     [rax+8], rcx
0x1800414af  push    rbx
0x1800414b0  push    rsi
0x1800414b1  push    rdi
0x1800414b2  sub     rsp, 60h
0x1800414b6  mov     rdi, r8
0x1800414b9  mov     rsi, rdx
0x1800414bc  xor     ebx, ebx
0x1800414be  lea     ecx, [rbx+14h]
0x1800414c1  mov     [rsp+78h+var_28], ecx
0x1800414c5  xor     eax, eax
0x1800414c7  mov     [rsp+78h+var_34], eax
0x1800414cb  cmp     eax, ecx
0x1800414cd  jnb     loc_1800415E6
0x1800414d3  mov     rcx, [rsp+78h+arg_0]
0x1800414db  mov     rcx, [rcx]; SRWLock
0x1800414de  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x1800414e3  mov     [rsp+78h+var_30], 0
0x1800414ec  mov     rcx, [rsp+78h+arg_20]
0x1800414f4  mov     [rsp+78h+var_40], rcx
0x1800414f9  mov     [rsp+78h+var_48], 0
0x180041501  mov     [rsp+78h+var_50], rdi
0x180041506  mov     [rsp+78h+var_58], rsi
0x18004150b  mov     r9, rax
0x18004150e  xor     r8d, r8d; pReturnValue
0x180041511  lea     edx, [r8+2]; nProcNum
0x180041515  lea     rcx, stru_18004FB20; pProxyInfo
0x18004151c  call    cs:__imp_NdrClientCall3
0x180041522  mov     rbx, rax
0x180041525  mov     [rsp+78h+var_30], rax
0x18004152a  mov     [rsp+78h+var_38], eax
0x18004152e  jmp     loc_1800415E6
0x180041533  mov     ecx, eax
0x180041535  test    eax, eax
0x180041537  jle     short loc_180041542
0x180041539  movzx   ecx, ax
0x18004153c  or      ecx, 80070000h; int
0x180041542  mov     ebx, ecx
0x180041544  mov     [rsp+78h+var_38], ecx
0x180041548  mov     byte ptr [rsp+78h+arg_18], 0
0x180041550  lea     rdx, [rsp+78h+arg_18]; bool *
0x180041558  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18004155d  test    al, al
0x18004155f  jz      loc_1800415E6
0x180041565  mov     eax, cs:dword_18006E000
0x18004156b  cmp     eax, 4
0x18004156e  jbe     short loc_180041597
0x180041570  mov     dword ptr [rsp+78h+var_30], ecx
0x180041574  lea     rax, [rsp+78h+var_30]
0x180041579  mov     [rsp+78h+var_58], rax
0x18004157e  xor     r9d, r9d
0x180041581  xor     r8d, r8d
0x180041584  lea     rdx, word_1800632D6
0x18004158b  lea     rcx, dword_18006E000
0x180041592  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180041597  cmp     byte ptr [rsp+78h+arg_18], 0
0x18004159f  jz      short loc_1800415BB
0x1800415a1  mov     rcx, [rsp+78h+arg_0]
0x1800415a9  mov     rcx, [rcx]; this
0x1800415ac  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x1800415b1  mov     ebx, eax
0x1800415b3  mov     [rsp+78h+var_38], eax
0x1800415b7  test    eax, eax
0x1800415b9  js      short loc_1800415E6
0x1800415bb  mov     ecx, 1F4h; dwMilliseconds
0x1800415c0  call    cs:__imp_Sleep
0x1800415c6  nop
0x1800415c7  mov     eax, [rsp+78h+var_34]
0x1800415cb  inc     eax
0x1800415cd  mov     rdi, [rsp+78h+arg_10]
0x1800415d5  mov     rsi, [rsp+78h+arg_8]
0x1800415dd  mov     ecx, [rsp+78h+var_28]
0x1800415e1  jmp     loc_1800414C7
0x1800415e6  test    ebx, ebx
0x1800415e8  jns     short loc_18004164D
0x1800415ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800415f1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800415f6  test    al, al
0x1800415f8  jz      short loc_180041615
0x1800415fa  mov     rcx, [rsp+78h]; this
0x1800415ff  mov     r9d, ebx; char *
0x180041602  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\kspsvc\\tic"...
0x180041609  mov     edx, 0F1h; void *
0x18004160e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180041613  jmp     short loc_18004164D
0x180041615  mov     eax, cs:dword_18006E000
0x18004161b  cmp     eax, 2
0x18004161e  jbe     short loc_18004164D
0x180041620  mov     [rsp+78h+arg_18], ebx
0x180041627  lea     rax, [rsp+78h+arg_18]
0x18004162f  mov     [rsp+78h+var_58], rax
0x180041634  xor     r9d, r9d
0x180041637  xor     r8d, r8d
0x18004163a  lea     rdx, byte_1800632A1
0x180041641  lea     rcx, dword_18006E000
0x180041648  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18004164d  mov     eax, ebx
0x18004164f  add     rsp, 60h
0x180041653  pop     rdi
0x180041654  pop     rsi
0x180041655  pop     rbx
0x180041656  retn
0x18004ac3b  push    rbp
0x18004ac3d  sub     rsp, 40h
0x18004ac41  mov     rbp, rdx
0x18004ac44  mov     rcx, [rcx]
0x18004ac47  mov     ecx, [rcx]; ExceptionCode
0x18004ac49  call    cs:__imp_RpcExceptionFilter
0x18004ac4f  nop
0x18004ac50  add     rsp, 40h
0x18004ac54  pop     rbp
0x18004ac55  retn
```
