# I_NgcMgmtAddBioProtector

- ea: `0x18003f124`
- end: `0x18003f2d2`
- name: `I_NgcMgmtAddBioProtector`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800402a8`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x18003f124`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f234`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f234`
- `RPCRT4!NdrClientCall3` at `0x18003f199`
- `RPCRT4!NdrClientCall3` at `0x18003f199`

## string_xrefs

- `0x18003f281`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtAddBioProtector(PSRWLOCK *a1, int a2)
{
  void *v3; // rax
  int Pointer; // eax
  unsigned int v5; // ebx
  int v7[12]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7[0] = 20;
  v3 = NgcUtils::RpcClient::BindingHandle(*a1);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004F630, 6u, 0, v3).Pointer;
  v5 = Pointer;
  if ( Pointer < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x26F,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)v5,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v7[0] = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_180062F29,
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
0x18003f124  mov     rax, rsp
0x18003f127  mov     [rax+20h], r9
0x18003f12b  mov     [rax+18h], r8
0x18003f12f  mov     [rax+10h], rdx
0x18003f133  mov     [rax+8], rcx
0x18003f137  push    rbx
0x18003f138  push    rsi
0x18003f139  push    rdi
0x18003f13a  push    r14
0x18003f13c  sub     rsp, 68h
0x18003f140  mov     rdi, r9
0x18003f143  mov     rsi, r8
0x18003f146  mov     r14, rdx
0x18003f149  xor     ebx, ebx
0x18003f14b  lea     ecx, [rbx+14h]
0x18003f14e  mov     [rsp+88h+var_30], ecx
0x18003f152  xor     eax, eax
0x18003f154  mov     [rsp+88h+var_40], eax
0x18003f158  cmp     eax, ecx
0x18003f15a  jnb     loc_18003F262
0x18003f160  mov     rcx, [rsp+88h+arg_0]
0x18003f168  mov     rcx, [rcx]; SRWLock
0x18003f16b  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x18003f170  mov     [rsp+88h+var_38], 0
0x18003f179  mov     [rsp+88h+var_58], rdi
0x18003f17e  mov     [rsp+88h+var_60], rsi
0x18003f183  mov     [rsp+88h+var_68], r14
0x18003f188  mov     r9, rax
0x18003f18b  xor     r8d, r8d; pReturnValue
0x18003f18e  lea     edx, [r8+6]; nProcNum
0x18003f192  lea     rcx, stru_18004F630; pProxyInfo
0x18003f199  call    cs:__imp_NdrClientCall3
0x18003f19f  mov     rbx, rax
0x18003f1a2  mov     [rsp+88h+var_38], rax
0x18003f1a7  mov     [rsp+88h+var_44], eax
0x18003f1ab  jmp     loc_18003F262
0x18003f1b0  mov     ecx, eax
0x18003f1b2  test    eax, eax
0x18003f1b4  jle     short loc_18003F1BF
0x18003f1b6  movzx   ecx, ax
0x18003f1b9  or      ecx, 80070000h; int
0x18003f1bf  mov     ebx, ecx
0x18003f1c1  mov     [rsp+88h+var_44], ecx
0x18003f1c5  mov     [rsp+88h+var_48], 0
0x18003f1ca  lea     rdx, [rsp+88h+var_48]; bool *
0x18003f1cf  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003f1d4  test    al, al
0x18003f1d6  jz      loc_18003F262
0x18003f1dc  mov     eax, cs:dword_18006E000
0x18003f1e2  cmp     eax, 4
0x18003f1e5  jbe     short loc_18003F20E
0x18003f1e7  mov     dword ptr [rsp+88h+var_38], ecx
0x18003f1eb  lea     rax, [rsp+88h+var_38]
0x18003f1f0  mov     [rsp+88h+var_68], rax
0x18003f1f5  xor     r9d, r9d
0x18003f1f8  xor     r8d, r8d
0x18003f1fb  lea     rdx, byte_180062F59
0x18003f202  lea     rcx, dword_18006E000
0x18003f209  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f20e  cmp     [rsp+88h+var_48], 0
0x18003f213  jz      short loc_18003F22F
0x18003f215  mov     rcx, [rsp+88h+arg_0]
0x18003f21d  mov     rcx, [rcx]; this
0x18003f220  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x18003f225  mov     ebx, eax
0x18003f227  mov     [rsp+88h+var_44], eax
0x18003f22b  test    eax, eax
0x18003f22d  js      short loc_18003F262
0x18003f22f  mov     ecx, 1F4h; dwMilliseconds
0x18003f234  call    cs:__imp_Sleep
0x18003f23a  nop
0x18003f23b  mov     eax, [rsp+88h+var_40]
0x18003f23f  inc     eax
0x18003f241  mov     rdi, [rsp+88h+arg_18]
0x18003f249  mov     rsi, [rsp+88h+arg_10]
0x18003f251  mov     r14, [rsp+88h+arg_8]
0x18003f259  mov     ecx, [rsp+88h+var_30]
0x18003f25d  jmp     loc_18003F154
0x18003f262  test    ebx, ebx
0x18003f264  jns     short loc_18003F2C6
0x18003f266  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003f26d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003f272  test    al, al
0x18003f274  jz      short loc_18003F294
0x18003f276  mov     rcx, [rsp+88h]; this
0x18003f27e  mov     r9d, ebx; char *
0x18003f281  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x18003f288  mov     edx, 26Fh; void *
0x18003f28d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003f292  jmp     short loc_18003F2C6
0x18003f294  mov     eax, cs:dword_18006E000
0x18003f29a  cmp     eax, 2
0x18003f29d  jbe     short loc_18003F2C6
0x18003f29f  mov     [rsp+88h+var_30], ebx
0x18003f2a3  lea     rax, [rsp+88h+var_30]
0x18003f2a8  mov     [rsp+88h+var_68], rax
0x18003f2ad  xor     r9d, r9d
0x18003f2b0  xor     r8d, r8d
0x18003f2b3  lea     rdx, byte_180062F29
0x18003f2ba  lea     rcx, dword_18006E000
0x18003f2c1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f2c6  mov     eax, ebx
0x18003f2c8  add     rsp, 68h
0x18003f2cc  pop     r14
0x18003f2ce  pop     rdi
0x18003f2cf  pop     rsi
0x18003f2d0  pop     rbx
0x18003f2d1  retn
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
