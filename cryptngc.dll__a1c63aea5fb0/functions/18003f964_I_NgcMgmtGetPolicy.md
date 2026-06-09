# I_NgcMgmtGetPolicy

- ea: `0x18003f964`
- end: `0x18003fb10`
- name: `I_NgcMgmtGetPolicy`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180040b60`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x18003f964`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003fa72`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003fa72`
- `RPCRT4!NdrClientCall3` at `0x18003f9d7`
- `RPCRT4!NdrClientCall3` at `0x18003f9d7`

## string_xrefs

- `0x18003fabf`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtGetPolicy(PSRWLOCK *a1, int a2)
{
  void *v3; // rax
  int Pointer; // eax
  unsigned int v5; // ebx
  int v7[12]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7[0] = 20;
  v3 = NgcUtils::RpcClient::BindingHandle(*a1);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004F630, 0, 0, v3).Pointer;
  v5 = Pointer;
  if ( Pointer < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)v5,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v7[0] = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)word_1800630E2,
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
0x18003f964  mov     rax, rsp
0x18003f967  mov     [rax+20h], r9
0x18003f96b  mov     [rax+18h], r8
0x18003f96f  mov     [rax+10h], rdx
0x18003f973  mov     [rax+8], rcx
0x18003f977  push    rbx
0x18003f978  push    rsi
0x18003f979  push    rdi
0x18003f97a  push    r14
0x18003f97c  sub     rsp, 68h
0x18003f980  mov     rdi, r9
0x18003f983  mov     rsi, r8
0x18003f986  mov     r14, rdx
0x18003f989  xor     ebx, ebx
0x18003f98b  lea     ecx, [rbx+14h]
0x18003f98e  mov     [rsp+88h+var_30], ecx
0x18003f992  xor     eax, eax
0x18003f994  mov     [rsp+88h+var_40], eax
0x18003f998  cmp     eax, ecx
0x18003f99a  jnb     loc_18003FAA0
0x18003f9a0  mov     rcx, [rsp+88h+arg_0]
0x18003f9a8  mov     rcx, [rcx]; SRWLock
0x18003f9ab  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x18003f9b0  mov     [rsp+88h+var_38], 0
0x18003f9b9  mov     [rsp+88h+var_58], rdi
0x18003f9be  mov     [rsp+88h+var_60], rsi
0x18003f9c3  mov     [rsp+88h+var_68], r14
0x18003f9c8  mov     r9, rax
0x18003f9cb  xor     r8d, r8d; pReturnValue
0x18003f9ce  xor     edx, edx; nProcNum
0x18003f9d0  lea     rcx, stru_18004F630; pProxyInfo
0x18003f9d7  call    cs:__imp_NdrClientCall3
0x18003f9dd  mov     rbx, rax
0x18003f9e0  mov     [rsp+88h+var_38], rax
0x18003f9e5  mov     [rsp+88h+var_44], eax
0x18003f9e9  jmp     loc_18003FAA0
0x18003f9ee  mov     ecx, eax
0x18003f9f0  test    eax, eax
0x18003f9f2  jle     short loc_18003F9FD
0x18003f9f4  movzx   ecx, ax
0x18003f9f7  or      ecx, 80070000h; int
0x18003f9fd  mov     ebx, ecx
0x18003f9ff  mov     [rsp+88h+var_44], ecx
0x18003fa03  mov     [rsp+88h+var_48], 0
0x18003fa08  lea     rdx, [rsp+88h+var_48]; bool *
0x18003fa0d  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003fa12  test    al, al
0x18003fa14  jz      loc_18003FAA0
0x18003fa1a  mov     eax, cs:dword_18006E000
0x18003fa20  cmp     eax, 4
0x18003fa23  jbe     short loc_18003FA4C
0x18003fa25  mov     dword ptr [rsp+88h+var_38], ecx
0x18003fa29  lea     rax, [rsp+88h+var_38]
0x18003fa2e  mov     [rsp+88h+var_68], rax
0x18003fa33  xor     r9d, r9d
0x18003fa36  xor     r8d, r8d
0x18003fa39  lea     rdx, dword_18006310C
0x18003fa40  lea     rcx, dword_18006E000
0x18003fa47  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003fa4c  cmp     [rsp+88h+var_48], 0
0x18003fa51  jz      short loc_18003FA6D
0x18003fa53  mov     rcx, [rsp+88h+arg_0]
0x18003fa5b  mov     rcx, [rcx]; this
0x18003fa5e  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x18003fa63  mov     ebx, eax
0x18003fa65  mov     [rsp+88h+var_44], eax
0x18003fa69  test    eax, eax
0x18003fa6b  js      short loc_18003FAA0
0x18003fa6d  mov     ecx, 1F4h; dwMilliseconds
0x18003fa72  call    cs:__imp_Sleep
0x18003fa78  nop
0x18003fa79  mov     eax, [rsp+88h+var_40]
0x18003fa7d  inc     eax
0x18003fa7f  mov     rdi, [rsp+88h+arg_18]
0x18003fa87  mov     rsi, [rsp+88h+arg_10]
0x18003fa8f  mov     r14, [rsp+88h+arg_8]
0x18003fa97  mov     ecx, [rsp+88h+var_30]
0x18003fa9b  jmp     loc_18003F994
0x18003faa0  test    ebx, ebx
0x18003faa2  jns     short loc_18003FB04
0x18003faa4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003faab  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003fab0  test    al, al
0x18003fab2  jz      short loc_18003FAD2
0x18003fab4  mov     rcx, [rsp+88h]; this
0x18003fabc  mov     r9d, ebx; char *
0x18003fabf  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x18003fac6  mov     edx, 85h; void *
0x18003facb  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003fad0  jmp     short loc_18003FB04
0x18003fad2  mov     eax, cs:dword_18006E000
0x18003fad8  cmp     eax, 2
0x18003fadb  jbe     short loc_18003FB04
0x18003fadd  mov     [rsp+88h+var_30], ebx
0x18003fae1  lea     rax, [rsp+88h+var_30]
0x18003fae6  mov     [rsp+88h+var_68], rax
0x18003faeb  xor     r9d, r9d
0x18003faee  xor     r8d, r8d
0x18003faf1  lea     rdx, word_1800630E2
0x18003faf8  lea     rcx, dword_18006E000
0x18003faff  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003fb04  mov     eax, ebx
0x18003fb06  add     rsp, 68h
0x18003fb0a  pop     r14
0x18003fb0c  pop     rdi
0x18003fb0d  pop     rsi
0x18003fb0e  pop     rbx
0x18003fb0f  retn
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
