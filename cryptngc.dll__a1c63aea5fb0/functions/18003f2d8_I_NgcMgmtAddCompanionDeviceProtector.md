# I_NgcMgmtAddCompanionDeviceProtector

- ea: `0x18003f2d8`
- end: `0x18003f45b`
- name: `I_NgcMgmtAddCompanionDeviceProtector`
- size: `387`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040468`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x18003f2d8`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f3d0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f3d0`
- `RPCRT4!NdrClientCall3` at `0x18003f33c`
- `RPCRT4!NdrClientCall3` at `0x18003f33c`

## string_xrefs

- `0x18003f40c`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtAddCompanionDeviceProtector(PSRWLOCK *a1, int a2)
{
  void *v3; // rax
  CLIENT_CALL_RETURN v4; // rax
  unsigned int Pointer; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  CLIENT_CALL_RETURN v8; // [rsp+78h] [rbp+20h] BYREF

  v3 = NgcUtils::RpcClient::BindingHandle(*a1);
  v8.Simple = 0;
  v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004F630, 0xBu, 0, v3).Pointer;
  Pointer = (unsigned int)v4.Pointer;
  v8.Pointer = v4.Pointer;
  if ( SLODWORD(v4.Simple) < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x3F2,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)Pointer,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v8.Pointer) = Pointer;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&dword_180062C04,
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
0x18003f2d8  mov     [rsp+arg_10], r8
0x18003f2dd  mov     [rsp+arg_8], rdx
0x18003f2e2  mov     [rsp+arg_0], rcx
0x18003f2e7  push    rbx
0x18003f2e8  push    rsi
0x18003f2e9  push    rdi
0x18003f2ea  sub     rsp, 40h
0x18003f2ee  mov     rdi, r8
0x18003f2f1  mov     rsi, rdx
0x18003f2f4  xor     ebx, ebx
0x18003f2f6  lea     ecx, [rbx+14h]
0x18003f2f9  mov     [rsp+58h+var_1C], ecx
0x18003f2fd  xor     eax, eax
0x18003f2ff  mov     [rsp+58h+var_24], eax
0x18003f303  cmp     eax, ecx
0x18003f305  jnb     loc_18003F3F0
0x18003f30b  mov     rcx, [rsp+58h+arg_0]
0x18003f310  mov     rcx, [rcx]; SRWLock
0x18003f313  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x18003f318  mov     [rsp+58h+arg_18], 0
0x18003f321  mov     [rsp+58h+var_30], rdi
0x18003f326  mov     [rsp+58h+var_38], rsi
0x18003f32b  mov     r9, rax
0x18003f32e  xor     r8d, r8d; pReturnValue
0x18003f331  lea     edx, [r8+0Bh]; nProcNum
0x18003f335  lea     rcx, stru_18004F630; pProxyInfo
0x18003f33c  call    cs:__imp_NdrClientCall3
0x18003f342  mov     rbx, rax
0x18003f345  mov     [rsp+58h+arg_18], rax
0x18003f34a  mov     [rsp+58h+var_28], eax
0x18003f34e  jmp     loc_18003F3F0
0x18003f353  mov     ecx, eax
0x18003f355  test    eax, eax
0x18003f357  jle     short loc_18003F362
0x18003f359  movzx   ecx, ax
0x18003f35c  or      ecx, 80070000h; int
0x18003f362  mov     ebx, ecx
0x18003f364  mov     [rsp+58h+var_28], ecx
0x18003f368  mov     byte ptr [rsp+58h+arg_18], 0
0x18003f36d  lea     rdx, [rsp+58h+arg_18]; bool *
0x18003f372  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003f377  test    al, al
0x18003f379  jz      short loc_18003F3F0
0x18003f37b  mov     eax, cs:dword_18006E000
0x18003f381  cmp     eax, 4
0x18003f384  jbe     short loc_18003F3AD
0x18003f386  mov     [rsp+58h+var_20], ecx
0x18003f38a  lea     rax, [rsp+58h+var_20]
0x18003f38f  mov     [rsp+58h+var_38], rax
0x18003f394  xor     r9d, r9d
0x18003f397  xor     r8d, r8d
0x18003f39a  lea     rdx, unk_180062C40
0x18003f3a1  lea     rcx, dword_18006E000
0x18003f3a8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f3ad  cmp     byte ptr [rsp+58h+arg_18], 0
0x18003f3b2  jz      short loc_18003F3CB
0x18003f3b4  mov     rcx, [rsp+58h+arg_0]
0x18003f3b9  mov     rcx, [rcx]; this
0x18003f3bc  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x18003f3c1  mov     ebx, eax
0x18003f3c3  mov     [rsp+58h+var_28], eax
0x18003f3c7  test    eax, eax
0x18003f3c9  js      short loc_18003F3F0
0x18003f3cb  mov     ecx, 1F4h; dwMilliseconds
0x18003f3d0  call    cs:__imp_Sleep
0x18003f3d6  nop
0x18003f3d7  mov     eax, [rsp+58h+var_24]
0x18003f3db  inc     eax
0x18003f3dd  mov     rdi, [rsp+58h+arg_10]
0x18003f3e2  mov     rsi, [rsp+58h+arg_8]
0x18003f3e7  mov     ecx, [rsp+58h+var_1C]
0x18003f3eb  jmp     loc_18003F2FF
0x18003f3f0  test    ebx, ebx
0x18003f3f2  jns     short loc_18003F451
0x18003f3f4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003f3fb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003f400  test    al, al
0x18003f402  jz      short loc_18003F41F
0x18003f404  mov     rcx, [rsp+58h]; this
0x18003f409  mov     r9d, ebx; char *
0x18003f40c  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x18003f413  mov     edx, 3F2h; void *
0x18003f418  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003f41d  jmp     short loc_18003F451
0x18003f41f  mov     eax, cs:dword_18006E000
0x18003f425  cmp     eax, 2
0x18003f428  jbe     short loc_18003F451
0x18003f42a  mov     dword ptr [rsp+58h+arg_18], ebx
0x18003f42e  lea     rax, [rsp+58h+arg_18]
0x18003f433  mov     [rsp+58h+var_38], rax
0x18003f438  xor     r9d, r9d
0x18003f43b  xor     r8d, r8d
0x18003f43e  lea     rdx, dword_180062C04
0x18003f445  lea     rcx, dword_18006E000
0x18003f44c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f451  mov     eax, ebx
0x18003f453  add     rsp, 40h
0x18003f457  pop     rdi
0x18003f458  pop     rsi
0x18003f459  pop     rbx
0x18003f45a  retn
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
