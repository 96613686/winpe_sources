# I_NgcMgmtChangePinSilent

- ea: `0x18003f7b0`
- end: `0x18003f95e`
- name: `I_NgcMgmtChangePinSilent`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800409a0`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x18003f7b0`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f8c0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f8c0`
- `RPCRT4!NdrClientCall3` at `0x18003f825`
- `RPCRT4!NdrClientCall3` at `0x18003f825`

## string_xrefs

- `0x18003f90d`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtChangePinSilent(PSRWLOCK *a1, int a2)
{
  void *v3; // rax
  int Pointer; // eax
  unsigned int v5; // ebx
  int v7[12]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7[0] = 20;
  v3 = NgcUtils::RpcClient::BindingHandle(*a1);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004F630, 3u, 0, v3).Pointer;
  v5 = Pointer;
  if ( Pointer < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)v5,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v7[0] = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)word_180062FC2,
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
0x18003f7b0  mov     rax, rsp
0x18003f7b3  mov     [rax+20h], r9
0x18003f7b7  mov     [rax+18h], r8
0x18003f7bb  mov     [rax+10h], rdx
0x18003f7bf  mov     [rax+8], rcx
0x18003f7c3  push    rbx
0x18003f7c4  push    rsi
0x18003f7c5  push    rdi
0x18003f7c6  push    r14
0x18003f7c8  sub     rsp, 68h
0x18003f7cc  mov     rdi, r9
0x18003f7cf  mov     rsi, r8
0x18003f7d2  mov     r14, rdx
0x18003f7d5  xor     ebx, ebx
0x18003f7d7  lea     ecx, [rbx+14h]
0x18003f7da  mov     [rsp+88h+var_30], ecx
0x18003f7de  xor     eax, eax
0x18003f7e0  mov     [rsp+88h+var_40], eax
0x18003f7e4  cmp     eax, ecx
0x18003f7e6  jnb     loc_18003F8EE
0x18003f7ec  mov     rcx, [rsp+88h+arg_0]
0x18003f7f4  mov     rcx, [rcx]; SRWLock
0x18003f7f7  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x18003f7fc  mov     [rsp+88h+var_38], 0
0x18003f805  mov     [rsp+88h+var_58], rdi
0x18003f80a  mov     [rsp+88h+var_60], rsi
0x18003f80f  mov     [rsp+88h+var_68], r14
0x18003f814  mov     r9, rax
0x18003f817  xor     r8d, r8d; pReturnValue
0x18003f81a  lea     edx, [r8+3]; nProcNum
0x18003f81e  lea     rcx, stru_18004F630; pProxyInfo
0x18003f825  call    cs:__imp_NdrClientCall3
0x18003f82b  mov     rbx, rax
0x18003f82e  mov     [rsp+88h+var_38], rax
0x18003f833  mov     [rsp+88h+var_44], eax
0x18003f837  jmp     loc_18003F8EE
0x18003f83c  mov     ecx, eax
0x18003f83e  test    eax, eax
0x18003f840  jle     short loc_18003F84B
0x18003f842  movzx   ecx, ax
0x18003f845  or      ecx, 80070000h; int
0x18003f84b  mov     ebx, ecx
0x18003f84d  mov     [rsp+88h+var_44], ecx
0x18003f851  mov     [rsp+88h+var_48], 0
0x18003f856  lea     rdx, [rsp+88h+var_48]; bool *
0x18003f85b  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003f860  test    al, al
0x18003f862  jz      loc_18003F8EE
0x18003f868  mov     eax, cs:dword_18006E000
0x18003f86e  cmp     eax, 4
0x18003f871  jbe     short loc_18003F89A
0x18003f873  mov     dword ptr [rsp+88h+var_38], ecx
0x18003f877  lea     rax, [rsp+88h+var_38]
0x18003f87c  mov     [rsp+88h+var_68], rax
0x18003f881  xor     r9d, r9d
0x18003f884  xor     r8d, r8d
0x18003f887  lea     rdx, word_180062FF2
0x18003f88e  lea     rcx, dword_18006E000
0x18003f895  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f89a  cmp     [rsp+88h+var_48], 0
0x18003f89f  jz      short loc_18003F8BB
0x18003f8a1  mov     rcx, [rsp+88h+arg_0]
0x18003f8a9  mov     rcx, [rcx]; this
0x18003f8ac  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x18003f8b1  mov     ebx, eax
0x18003f8b3  mov     [rsp+88h+var_44], eax
0x18003f8b7  test    eax, eax
0x18003f8b9  js      short loc_18003F8EE
0x18003f8bb  mov     ecx, 1F4h; dwMilliseconds
0x18003f8c0  call    cs:__imp_Sleep
0x18003f8c6  nop
0x18003f8c7  mov     eax, [rsp+88h+var_40]
0x18003f8cb  inc     eax
0x18003f8cd  mov     rdi, [rsp+88h+arg_18]
0x18003f8d5  mov     rsi, [rsp+88h+arg_10]
0x18003f8dd  mov     r14, [rsp+88h+arg_8]
0x18003f8e5  mov     ecx, [rsp+88h+var_30]
0x18003f8e9  jmp     loc_18003F7E0
0x18003f8ee  test    ebx, ebx
0x18003f8f0  jns     short loc_18003F952
0x18003f8f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003f8f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003f8fe  test    al, al
0x18003f900  jz      short loc_18003F920
0x18003f902  mov     rcx, [rsp+88h]; this
0x18003f90a  mov     r9d, ebx; char *
0x18003f90d  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x18003f914  mov     edx, 174h; void *
0x18003f919  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003f91e  jmp     short loc_18003F952
0x18003f920  mov     eax, cs:dword_18006E000
0x18003f926  cmp     eax, 2
0x18003f929  jbe     short loc_18003F952
0x18003f92b  mov     [rsp+88h+var_30], ebx
0x18003f92f  lea     rax, [rsp+88h+var_30]
0x18003f934  mov     [rsp+88h+var_68], rax
0x18003f939  xor     r9d, r9d
0x18003f93c  xor     r8d, r8d
0x18003f93f  lea     rdx, word_180062FC2
0x18003f946  lea     rcx, dword_18006E000
0x18003f94d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f952  mov     eax, ebx
0x18003f954  add     rsp, 68h
0x18003f958  pop     r14
0x18003f95a  pop     rdi
0x18003f95b  pop     rsi
0x18003f95c  pop     rbx
0x18003f95d  retn
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
