# I_NgcMgmtRemoveBioProtector

- ea: `0x18003fc90`
- end: `0x18003fdff`
- name: `I_NgcMgmtRemoveBioProtector`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180040d20`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x18003fc90`
- `0x180041460`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003fd7a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003fd7a`
- `RPCRT4!NdrClientCall3` at `0x18003fce6`
- `RPCRT4!NdrClientCall3` at `0x18003fce6`

## string_xrefs

- `0x18003fdb1`: `onecore\ds\security\ngc\kspsvc\mgmt\ngcmgmtrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcMgmtRemoveBioProtector(PSRWLOCK *a1, int a2)
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
  v4.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004F630, 7u, 0, v3).Pointer;
  Pointer = (unsigned int)v4.Pointer;
  v8.Pointer = v4.Pointer;
  if ( SLODWORD(v4.Simple) < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x2BC,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\mgmt\\ngcmgmtrpcclient.cpp",
        (const char *)Pointer,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v8.Pointer) = Pointer;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_180062E8D,
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
0x18003fc90  mov     [rsp+arg_8], rdx
0x18003fc95  mov     [rsp+arg_0], rcx
0x18003fc9a  push    rbx
0x18003fc9b  push    rdi
0x18003fc9c  sub     rsp, 48h
0x18003fca0  mov     rdi, rdx
0x18003fca3  xor     ebx, ebx
0x18003fca5  lea     ecx, [rbx+14h]
0x18003fca8  mov     [rsp+58h+var_20], ecx
0x18003fcac  xor     eax, eax
0x18003fcae  mov     [rsp+58h+arg_18], eax
0x18003fcb2  cmp     eax, ecx
0x18003fcb4  jnb     loc_18003FD95
0x18003fcba  mov     rcx, [rsp+58h+arg_0]
0x18003fcbf  mov     rcx, [rcx]; SRWLock
0x18003fcc2  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x18003fcc7  mov     [rsp+58h+arg_10], 0
0x18003fcd0  mov     [rsp+58h+var_38], rdi
0x18003fcd5  mov     r9, rax
0x18003fcd8  xor     r8d, r8d; pReturnValue
0x18003fcdb  lea     edx, [r8+7]; nProcNum
0x18003fcdf  lea     rcx, stru_18004F630; pProxyInfo
0x18003fce6  call    cs:__imp_NdrClientCall3
0x18003fcec  mov     rbx, rax
0x18003fcef  mov     [rsp+58h+arg_10], rax
0x18003fcf4  mov     [rsp+58h+var_28], eax
0x18003fcf8  jmp     loc_18003FD95
0x18003fcfd  mov     ecx, eax
0x18003fcff  test    eax, eax
0x18003fd01  jle     short loc_18003FD0C
0x18003fd03  movzx   ecx, ax
0x18003fd06  or      ecx, 80070000h; int
0x18003fd0c  mov     ebx, ecx
0x18003fd0e  mov     [rsp+58h+var_28], ecx
0x18003fd12  mov     byte ptr [rsp+58h+arg_10], 0
0x18003fd17  lea     rdx, [rsp+58h+arg_10]; bool *
0x18003fd1c  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18003fd21  test    al, al
0x18003fd23  jz      short loc_18003FD95
0x18003fd25  mov     eax, cs:dword_18006E000
0x18003fd2b  cmp     eax, 4
0x18003fd2e  jbe     short loc_18003FD57
0x18003fd30  mov     [rsp+58h+var_24], ecx
0x18003fd34  lea     rax, [rsp+58h+var_24]
0x18003fd39  mov     [rsp+58h+var_38], rax
0x18003fd3e  xor     r9d, r9d
0x18003fd41  xor     r8d, r8d
0x18003fd44  lea     rdx, unk_180062EC0
0x18003fd4b  lea     rcx, dword_18006E000
0x18003fd52  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003fd57  cmp     byte ptr [rsp+58h+arg_10], 0
0x18003fd5c  jz      short loc_18003FD75
0x18003fd5e  mov     rcx, [rsp+58h+arg_0]
0x18003fd63  mov     rcx, [rcx]; this
0x18003fd66  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x18003fd6b  mov     ebx, eax
0x18003fd6d  mov     [rsp+58h+var_28], eax
0x18003fd71  test    eax, eax
0x18003fd73  js      short loc_18003FD95
0x18003fd75  mov     ecx, 1F4h; dwMilliseconds
0x18003fd7a  call    cs:__imp_Sleep
0x18003fd80  nop
0x18003fd81  mov     eax, [rsp+58h+arg_18]
0x18003fd85  inc     eax
0x18003fd87  mov     rdi, [rsp+58h+arg_8]
0x18003fd8c  mov     ecx, [rsp+58h+var_20]
0x18003fd90  jmp     loc_18003FCAE
0x18003fd95  test    ebx, ebx
0x18003fd97  jns     short loc_18003FDF6
0x18003fd99  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18003fda0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18003fda5  test    al, al
0x18003fda7  jz      short loc_18003FDC4
0x18003fda9  mov     rcx, [rsp+58h]; this
0x18003fdae  mov     r9d, ebx; char *
0x18003fdb1  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\kspsvc\\mgm"...
0x18003fdb8  mov     edx, 2BCh; void *
0x18003fdbd  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003fdc2  jmp     short loc_18003FDF6
0x18003fdc4  mov     eax, cs:dword_18006E000
0x18003fdca  cmp     eax, 2
0x18003fdcd  jbe     short loc_18003FDF6
0x18003fdcf  mov     dword ptr [rsp+58h+arg_10], ebx
0x18003fdd3  lea     rax, [rsp+58h+arg_10]
0x18003fdd8  mov     [rsp+58h+var_38], rax
0x18003fddd  xor     r9d, r9d
0x18003fde0  xor     r8d, r8d
0x18003fde3  lea     rdx, byte_180062E8D
0x18003fdea  lea     rcx, dword_18006E000
0x18003fdf1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003fdf6  mov     eax, ebx
0x18003fdf8  add     rsp, 48h
0x18003fdfc  pop     rdi
0x18003fdfd  pop     rbx
0x18003fdfe  retn
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
