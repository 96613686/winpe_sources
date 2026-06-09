# I_NgcMgmtEnumContainers

- ea: `0x180024494`
- end: `0x180024640`
- name: `I_NgcMgmtEnumContainers`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a014`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180024494`
- `0x180032e58`
- `0x180032e88`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800245a2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800245a2`
- `RPCRT4!RpcExceptionFilter` at `0x18004b024`
- `RPCRT4!RpcExceptionFilter` at `0x18004b024`
- `RPCRT4!NdrClientCall3` at `0x180024507`
- `RPCRT4!NdrClientCall3` at `0x180024507`

## string_xrefs

- `0x1800245ef`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtEnumContainers(PSRWLOCK *a1, int a2)
{
  void *v3; // rax
  int Pointer; // eax
  unsigned int v5; // ebx
  int v7[12]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7[0] = 20;
  v3 = NgcUtils::RpcClient::BindingHandle(*a1);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, v3).Pointer;
  v5 = Pointer;
  if ( Pointer < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)v5,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v7[0] = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&dword_180063174,
        0,
        0,
        (__int64)v7);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180024494  mov     rax, rsp
0x180024497  mov     [rax+20h], r9
0x18002449b  mov     [rax+18h], r8
0x18002449f  mov     [rax+10h], rdx
0x1800244a3  mov     [rax+8], rcx
0x1800244a7  push    rbx
0x1800244a8  push    rsi
0x1800244a9  push    rdi
0x1800244aa  push    r14
0x1800244ac  sub     rsp, 68h
0x1800244b0  mov     rdi, r9
0x1800244b3  mov     rsi, r8
0x1800244b6  mov     r14, rdx
0x1800244b9  xor     ebx, ebx
0x1800244bb  lea     ecx, [rbx+14h]
0x1800244be  mov     [rsp+88h+var_30], ecx
0x1800244c2  xor     eax, eax
0x1800244c4  mov     [rsp+88h+var_40], eax
0x1800244c8  cmp     eax, ecx
0x1800244ca  jnb     loc_1800245D0
0x1800244d0  mov     rcx, [rsp+88h+arg_0]
0x1800244d8  mov     rcx, [rcx]; SRWLock
0x1800244db  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x1800244e0  mov     [rsp+88h+var_38], 0
0x1800244e9  mov     [rsp+88h+var_58], rdi
0x1800244ee  mov     [rsp+88h+var_60], rsi
0x1800244f3  mov     [rsp+88h+var_68], r14
0x1800244f8  mov     r9, rax
0x1800244fb  xor     r8d, r8d; pReturnValue
0x1800244fe  xor     edx, edx; nProcNum
0x180024500  lea     rcx, pProxyInfo; pProxyInfo
0x180024507  call    cs:__imp_NdrClientCall3
0x18002450d  mov     rbx, rax
0x180024510  mov     [rsp+88h+var_38], rax
0x180024515  mov     [rsp+88h+var_44], eax
0x180024519  jmp     loc_1800245D0
0x18002451e  mov     ecx, eax
0x180024520  test    eax, eax
0x180024522  jle     short loc_18002452D
0x180024524  movzx   ecx, ax
0x180024527  or      ecx, 80070000h; int
0x18002452d  mov     ebx, ecx
0x18002452f  mov     [rsp+88h+var_44], ecx
0x180024533  mov     [rsp+88h+var_48], 0
0x180024538  lea     rdx, [rsp+88h+var_48]; bool *
0x18002453d  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x180024542  test    al, al
0x180024544  jz      loc_1800245D0
0x18002454a  mov     eax, cs:dword_18006E000
0x180024550  cmp     eax, 4
0x180024553  jbe     short loc_18002457C
0x180024555  mov     dword ptr [rsp+88h+var_38], ecx
0x180024559  lea     rax, [rsp+88h+var_38]
0x18002455e  mov     [rsp+88h+var_68], rax
0x180024563  xor     r9d, r9d
0x180024566  xor     r8d, r8d
0x180024569  lea     rdx, byte_1800631A3
0x180024570  lea     rcx, dword_18006E000
0x180024577  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002457c  cmp     [rsp+88h+var_48], 0
0x180024581  jz      short loc_18002459D
0x180024583  mov     rcx, [rsp+88h+arg_0]
0x18002458b  mov     rcx, [rcx]; this
0x18002458e  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x180024593  mov     ebx, eax
0x180024595  mov     [rsp+88h+var_44], eax
0x180024599  test    eax, eax
0x18002459b  js      short loc_1800245D0
0x18002459d  mov     ecx, 1F4h; dwMilliseconds
0x1800245a2  call    cs:__imp_Sleep
0x1800245a8  nop
0x1800245a9  mov     eax, [rsp+88h+var_40]
0x1800245ad  inc     eax
0x1800245af  mov     rdi, [rsp+88h+arg_18]
0x1800245b7  mov     rsi, [rsp+88h+arg_10]
0x1800245bf  mov     r14, [rsp+88h+arg_8]
0x1800245c7  mov     ecx, [rsp+88h+var_30]
0x1800245cb  jmp     loc_1800244C4
0x1800245d0  test    ebx, ebx
0x1800245d2  jns     short loc_180024634
0x1800245d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800245db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800245e0  test    al, al
0x1800245e2  jz      short loc_180024602
0x1800245e4  mov     rcx, [rsp+88h]; this
0x1800245ec  mov     r9d, ebx; char *
0x1800245ef  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x1800245f6  mov     edx, 34h ; '4'; void *
0x1800245fb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180024600  jmp     short loc_180024634
0x180024602  mov     eax, cs:dword_18006E000
0x180024608  cmp     eax, 2
0x18002460b  jbe     short loc_180024634
0x18002460d  mov     [rsp+88h+var_30], ebx
0x180024611  lea     rax, [rsp+88h+var_30]
0x180024616  mov     [rsp+88h+var_68], rax
0x18002461b  xor     r9d, r9d
0x18002461e  xor     r8d, r8d
0x180024621  lea     rdx, dword_180063174
0x180024628  lea     rcx, dword_18006E000
0x18002462f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180024634  mov     eax, ebx
0x180024636  add     rsp, 68h
0x18002463a  pop     r14
0x18002463c  pop     rdi
0x18002463d  pop     rsi
0x18002463e  pop     rbx
0x18002463f  retn
0x18004b016  push    rbp
0x18004b018  sub     rsp, 40h
0x18004b01c  mov     rbp, rdx
0x18004b01f  mov     rcx, [rcx]
0x18004b022  mov     ecx, [rcx]; ExceptionCode
0x18004b024  call    cs:__imp_RpcExceptionFilter
0x18004b02a  nop
0x18004b02b  add     rsp, 40h
0x18004b02f  pop     rbp
0x18004b030  retn
```
