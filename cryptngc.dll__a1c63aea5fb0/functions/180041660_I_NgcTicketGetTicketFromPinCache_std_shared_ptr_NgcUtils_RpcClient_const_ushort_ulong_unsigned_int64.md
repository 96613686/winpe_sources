# I_NgcTicketGetTicketFromPinCache(std::shared_ptr<NgcUtils::RpcClient> const &,ushort *,ulong,unsigned __int64 *)

- ea: `0x180041660`
- end: `0x18004180c`
- name: `?I_NgcTicketGetTicketFromPinCache@@YAJAEBV?$shared_ptr@VRpcClient@NgcUtils@@@std@@PEAGKPEA_K@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800419e0`

## callees

- `0x1800158e0`
- `0x180017688`
- `0x180032e58`
- `0x180032e88`
- `0x180041460`
- `0x180041660`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004176f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004176f`
- `RPCRT4!RpcExceptionFilter` at `0x18004ac49`
- `RPCRT4!RpcExceptionFilter` at `0x18004ac49`
- `RPCRT4!NdrClientCall3` at `0x1800416d4`
- `RPCRT4!NdrClientCall3` at `0x1800416d4`

## string_xrefs

- `0x1800417bb`: `onecore\ds\security\ngc\kspsvc\ticket\ngcauthticketrpcclient.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcTicketGetTicketFromPinCache(PSRWLOCK *a1, int a2)
{
  void *v3; // rax
  int Pointer; // eax
  unsigned int v5; // ebx
  int v7[12]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7[0] = 20;
  v3 = NgcUtils::RpcClient::BindingHandle(*a1);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18004FB20, 3u, 0, v3).Pointer;
  v5 = Pointer;
  if ( Pointer < 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x14A,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\ticket\\ngcauthticketrpcclient.cpp",
        (const char *)v5,
        a2);
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v7[0] = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)&word_180063206,
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
0x180041660  mov     rax, rsp
0x180041663  mov     [rax+20h], r9
0x180041667  mov     [rax+18h], r8d
0x18004166b  mov     [rax+10h], rdx
0x18004166f  mov     [rax+8], rcx
0x180041673  push    rbx
0x180041674  push    rsi
0x180041675  push    rdi
0x180041676  push    r14
0x180041678  sub     rsp, 68h
0x18004167c  mov     rdi, r9
0x18004167f  mov     esi, r8d
0x180041682  mov     r14, rdx
0x180041685  xor     ebx, ebx
0x180041687  lea     ecx, [rbx+14h]
0x18004168a  mov     [rsp+88h+var_30], ecx
0x18004168e  xor     eax, eax
0x180041690  mov     [rsp+88h+var_40], eax
0x180041694  cmp     eax, ecx
0x180041696  jnb     loc_18004179C
0x18004169c  mov     rcx, [rsp+88h+arg_0]
0x1800416a4  mov     rcx, [rcx]; SRWLock
0x1800416a7  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x1800416ac  mov     [rsp+88h+var_38], 0
0x1800416b5  mov     [rsp+88h+var_58], rdi
0x1800416ba  mov     [rsp+88h+var_60], esi
0x1800416be  mov     [rsp+88h+var_68], r14
0x1800416c3  mov     r9, rax
0x1800416c6  xor     r8d, r8d; pReturnValue
0x1800416c9  lea     edx, [r8+3]; nProcNum
0x1800416cd  lea     rcx, stru_18004FB20; pProxyInfo
0x1800416d4  call    cs:__imp_NdrClientCall3
0x1800416da  mov     rbx, rax
0x1800416dd  mov     [rsp+88h+var_38], rax
0x1800416e2  mov     [rsp+88h+var_44], eax
0x1800416e6  jmp     loc_18004179C
0x1800416eb  mov     ecx, eax
0x1800416ed  test    eax, eax
0x1800416ef  jle     short loc_1800416FA
0x1800416f1  movzx   ecx, ax
0x1800416f4  or      ecx, 80070000h; int
0x1800416fa  mov     ebx, ecx
0x1800416fc  mov     [rsp+88h+var_44], ecx
0x180041700  mov     [rsp+88h+var_48], 0
0x180041705  lea     rdx, [rsp+88h+var_48]; bool *
0x18004170a  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x18004170f  test    al, al
0x180041711  jz      loc_18004179C
0x180041717  mov     eax, cs:dword_18006E000
0x18004171d  cmp     eax, 4
0x180041720  jbe     short loc_180041749
0x180041722  mov     dword ptr [rsp+88h+var_38], ecx
0x180041726  lea     rax, [rsp+88h+var_38]
0x18004172b  mov     [rsp+88h+var_68], rax
0x180041730  xor     r9d, r9d
0x180041733  xor     r8d, r8d
0x180041736  lea     rdx, word_18006323E
0x18004173d  lea     rcx, dword_18006E000
0x180041744  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180041749  cmp     [rsp+88h+var_48], 0
0x18004174e  jz      short loc_18004176A
0x180041750  mov     rcx, [rsp+88h+arg_0]
0x180041758  mov     rcx, [rcx]; this
0x18004175b  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x180041760  mov     ebx, eax
0x180041762  mov     [rsp+88h+var_44], eax
0x180041766  test    eax, eax
0x180041768  js      short loc_18004179C
0x18004176a  mov     ecx, 1F4h; dwMilliseconds
0x18004176f  call    cs:__imp_Sleep
0x180041775  nop
0x180041776  mov     eax, [rsp+88h+var_40]
0x18004177a  inc     eax
0x18004177c  mov     rdi, [rsp+88h+arg_18]
0x180041784  mov     esi, [rsp+88h+arg_10]
0x18004178b  mov     r14, [rsp+88h+arg_8]
0x180041793  mov     ecx, [rsp+88h+var_30]
0x180041797  jmp     loc_180041690
0x18004179c  test    ebx, ebx
0x18004179e  jns     short loc_180041800
0x1800417a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800417a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800417ac  test    al, al
0x1800417ae  jz      short loc_1800417CE
0x1800417b0  mov     rcx, [rsp+88h]; this
0x1800417b8  mov     r9d, ebx; char *
0x1800417bb  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\ngc\\kspsvc\\tic"...
0x1800417c2  mov     edx, 14Ah; void *
0x1800417c7  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800417cc  jmp     short loc_180041800
0x1800417ce  mov     eax, cs:dword_18006E000
0x1800417d4  cmp     eax, 2
0x1800417d7  jbe     short loc_180041800
0x1800417d9  mov     [rsp+88h+var_30], ebx
0x1800417dd  lea     rax, [rsp+88h+var_30]
0x1800417e2  mov     [rsp+88h+var_68], rax
0x1800417e7  xor     r9d, r9d
0x1800417ea  xor     r8d, r8d
0x1800417ed  lea     rdx, word_180063206
0x1800417f4  lea     rcx, dword_18006E000
0x1800417fb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180041800  mov     eax, ebx
0x180041802  add     rsp, 68h
0x180041806  pop     r14
0x180041808  pop     rdi
0x180041809  pop     rsi
0x18004180a  pop     rbx
0x18004180b  retn
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
