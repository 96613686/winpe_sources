# I_NgcMgmtAddPrebootProtector

- ea: `0x18003f464`
- end: `0x18003f61d`
- name: `I_NgcMgmtAddPrebootProtector`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040624`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x18003f464`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f57f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003f57f`
- `RPCRT4!NdrClientCall3` at `0x18003f4e4`
- `RPCRT4!NdrClientCall3` at `0x18003f4e4`

## string_xrefs

- `0x18003f5cc`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtAddPrebootProtector(PSRWLOCK *a1, int a2)
{
  void *v3; // rax
  int Pointer; // eax
  unsigned int v5; // ebx
  int v7[12]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7[0] = 20;
  v3 = NgcUtils::RpcClient::BindingHandle(*a1);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004F630, 9u, 0, v3).Pointer;
  v5 = Pointer;
  if ( Pointer < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x358,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)v5,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v7[0] = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&dword_180062D54,
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
0x18003f464  mov     rax, rsp
0x18003f467  mov     [rax+20h], r9
0x18003f46b  mov     [rax+18h], r8
0x18003f46f  mov     [rax+10h], rdx
0x18003f473  mov     [rax+8], rcx
0x18003f477  push    rbx
0x18003f478  push    rsi
0x18003f479  push    rdi
0x18003f47a  push    r14
0x18003f47c  sub     rsp, 68h
0x18003f480  mov     rdi, r9
0x18003f483  mov     rsi, r8
0x18003f486  mov     r14, rdx
0x18003f489  xor     ebx, ebx
0x18003f48b  lea     ecx, [rbx+14h]
0x18003f48e  mov     [rsp+88h+var_30], ecx
0x18003f492  xor     eax, eax
0x18003f494  mov     [rsp+88h+var_40], eax
0x18003f498  cmp     eax, ecx
0x18003f49a  jnb     loc_18003F5AD
0x18003f4a0  mov     rcx, [rsp+88h+arg_0]
0x18003f4a8  mov     rcx, [rcx]; SRWLock
0x18003f4ab  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x18003f4b0  mov     [rsp+88h+var_38], 0
0x18003f4b9  mov     ecx, [rsp+88h+arg_20]
0x18003f4c0  mov     [rsp+88h+var_50], ecx
0x18003f4c4  mov     [rsp+88h+var_58], rdi
0x18003f4c9  mov     [rsp+88h+var_60], rsi
0x18003f4ce  mov     [rsp+88h+var_68], r14
0x18003f4d3  mov     r9, rax
0x18003f4d6  xor     r8d, r8d; pReturnValue
0x18003f4d9  lea     edx, [r8+9]; nProcNum
0x18003f4dd  lea     rcx, stru_18004F630; pProxyInfo
0x18003f4e4  call    cs:__imp_NdrClientCall3
0x18003f4ea  mov     rbx, rax
0x18003f4ed  mov     [rsp+88h+var_38], rax
0x18003f4f2  mov     [rsp+88h+var_44], eax
0x18003f4f6  jmp     loc_18003F5AD
0x18003f4fb  mov     ecx, eax
0x18003f4fd  test    eax, eax
0x18003f4ff  jle     short loc_18003F50A
0x18003f501  movzx   ecx, ax
0x18003f504  or      ecx, 80070000h; int
0x18003f50a  mov     ebx, ecx
0x18003f50c  mov     [rsp+88h+var_44], ecx
0x18003f510  mov     [rsp+88h+var_48], 0
0x18003f515  lea     rdx, [rsp+88h+var_48]; bool *
0x18003f51a  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003f51f  test    al, al
0x18003f521  jz      loc_18003F5AD
0x18003f527  mov     eax, cs:dword_18006E000
0x18003f52d  cmp     eax, 4
0x18003f530  jbe     short loc_18003F559
0x18003f532  mov     dword ptr [rsp+88h+var_38], ecx
0x18003f536  lea     rax, [rsp+88h+var_38]
0x18003f53b  mov     [rsp+88h+var_68], rax
0x18003f540  xor     r9d, r9d
0x18003f543  xor     r8d, r8d
0x18003f546  lea     rdx, unk_180062D88
0x18003f54d  lea     rcx, dword_18006E000
0x18003f554  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f559  cmp     [rsp+88h+var_48], 0
0x18003f55e  jz      short loc_18003F57A
0x18003f560  mov     rcx, [rsp+88h+arg_0]
0x18003f568  mov     rcx, [rcx]; this
0x18003f56b  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x18003f570  mov     ebx, eax
0x18003f572  mov     [rsp+88h+var_44], eax
0x18003f576  test    eax, eax
0x18003f578  js      short loc_18003F5AD
0x18003f57a  mov     ecx, 1F4h; dwMilliseconds
0x18003f57f  call    cs:__imp_Sleep
0x18003f585  nop
0x18003f586  mov     eax, [rsp+88h+var_40]
0x18003f58a  inc     eax
0x18003f58c  mov     rdi, [rsp+88h+arg_18]
0x18003f594  mov     rsi, [rsp+88h+arg_10]
0x18003f59c  mov     r14, [rsp+88h+arg_8]
0x18003f5a4  mov     ecx, [rsp+88h+var_30]
0x18003f5a8  jmp     loc_18003F494
0x18003f5ad  test    ebx, ebx
0x18003f5af  jns     short loc_18003F611
0x18003f5b1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003f5b8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003f5bd  test    al, al
0x18003f5bf  jz      short loc_18003F5DF
0x18003f5c1  mov     rcx, [rsp+88h]; this
0x18003f5c9  mov     r9d, ebx; char *
0x18003f5cc  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x18003f5d3  mov     edx, 358h; void *
0x18003f5d8  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003f5dd  jmp     short loc_18003F611
0x18003f5df  mov     eax, cs:dword_18006E000
0x18003f5e5  cmp     eax, 2
0x18003f5e8  jbe     short loc_18003F611
0x18003f5ea  mov     [rsp+88h+var_30], ebx
0x18003f5ee  lea     rax, [rsp+88h+var_30]
0x18003f5f3  mov     [rsp+88h+var_68], rax
0x18003f5f8  xor     r9d, r9d
0x18003f5fb  xor     r8d, r8d
0x18003f5fe  lea     rdx, dword_180062D54
0x18003f605  lea     rcx, dword_18006E000
0x18003f60c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003f611  mov     eax, ebx
0x18003f613  add     rsp, 68h
0x18003f617  pop     r14
0x18003f619  pop     rdi
0x18003f61a  pop     rsi
0x18003f61b  pop     rbx
0x18003f61c  retn
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
