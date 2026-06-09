# I_NgcGetKeyAttestationForContainerService(std::shared_ptr<NgcUtils::RpcClient> const &,_NGC_IDP_ACCOUNT_INFO *,ushort const *,uchar * *,ulong *,uchar * *,ulong *,_NGC_KEY_STATUS *)

- ea: `0x180032cb0`
- end: `0x180032e51`
- name: `?I_NgcGetKeyAttestationForContainerService@@YAJAEBV?$shared_ptr@VRpcClient@NgcUtils@@@std@@PEAU_NGC_IDP_ACCOUNT_INFO@@PEBGPEAPEAEPEAK34PEAW4_NGC_KEY_STATUS@@@Z`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800322f4`

## callees

- `0x180006538`
- `0x1800158e0`
- `0x180017688`
- `0x180032cb0`
- `0x180032e58`
- `0x180038d08`
- `0x180043e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180032dec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180032dec`

## string_xrefs

- `0x180032e2e`: `onecore\ds\security\ngc\cryptngc\dll\ngcattestation.cpp`

## pseudocode

```c
__int64 __fastcall I_NgcGetKeyAttestationForContainerService(
        PSRWLOCK *a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rsi
  unsigned int v13; // eax
  int KeyAttestationForContainerService; // ebx
  int v16; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v10 = a2[2];
  v11 = a2[1];
  v12 = *a2;
  v13 = (unsigned int)NgcUtils::RpcClient::BindingHandle(*a1);
  KeyAttestationForContainerService = GetKeyAttestationForContainerService(v13, v12, v11, v10, a3, a5, a4, a7, a6, a8);
  if ( KeyAttestationForContainerService >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14E,
    (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcattestation.cpp",
    (const char *)(unsigned int)KeyAttestationForContainerService,
    v16);
  return (unsigned int)KeyAttestationForContainerService;
}

```

## disassembly

```asm
0x180032cb0  mov     rax, rsp
0x180032cb3  mov     [rax+20h], r9
0x180032cb7  mov     [rax+18h], r8
0x180032cbb  mov     [rax+10h], rdx
0x180032cbf  mov     [rax+8], rcx
0x180032cc3  push    rbx
0x180032cc4  push    rsi
0x180032cc5  push    rdi
0x180032cc6  push    r14
0x180032cc8  push    r15
0x180032cca  sub     rsp, 70h
0x180032cce  mov     r14, r9
0x180032cd1  mov     r15, r8
0x180032cd4  mov     rsi, rdx
0x180032cd7  mov     [rsp+98h+var_30], rdx
0x180032cdc  xor     ebx, ebx
0x180032cde  lea     ecx, [rbx+14h]
0x180032ce1  mov     [rsp+98h+var_38], ecx
0x180032ce5  xor     eax, eax
0x180032ce7  mov     [rsp+98h+var_40], eax
0x180032ceb  cmp     eax, ecx
0x180032ced  jnb     loc_180032E1F
0x180032cf3  mov     rbx, [rdx+10h]
0x180032cf7  mov     rdi, [rdx+8]
0x180032cfb  mov     rsi, [rsi]
0x180032cfe  mov     rcx, [rsp+98h+arg_0]
0x180032d06  mov     rcx, [rcx]; SRWLock
0x180032d09  call    ?BindingHandle@RpcClient@NgcUtils@@QEBAQEAXXZ; NgcUtils::RpcClient::BindingHandle(void)
0x180032d0e  mov     rcx, rax
0x180032d11  mov     rax, [rsp+98h+arg_38]
0x180032d19  mov     [rsp+98h+var_50], rax
0x180032d1e  mov     rax, [rsp+98h+arg_28]
0x180032d26  mov     [rsp+98h+var_58], rax
0x180032d2b  mov     rax, [rsp+98h+arg_30]
0x180032d33  mov     [rsp+98h+var_60], rax
0x180032d38  mov     [rsp+98h+var_68], r14
0x180032d3d  mov     rax, [rsp+98h+arg_20]
0x180032d45  mov     [rsp+98h+var_70], rax
0x180032d4a  mov     [rsp+98h+var_78], r15
0x180032d4f  mov     r9, rbx
0x180032d52  mov     r8, rdi
0x180032d55  mov     rdx, rsi
0x180032d58  call    GetKeyAttestationForContainerService
0x180032d5d  mov     ebx, eax
0x180032d5f  mov     [rsp+98h+var_44], eax
0x180032d63  jmp     loc_180032E1F
0x180032d68  mov     ebx, eax
0x180032d6a  test    eax, eax
0x180032d6c  jle     short loc_180032D77
0x180032d6e  movzx   ebx, ax
0x180032d71  or      ebx, 80070000h
0x180032d77  mov     [rsp+98h+var_44], ebx
0x180032d7b  mov     [rsp+98h+var_48], 0
0x180032d80  lea     rdx, [rsp+98h+var_48]; bool *
0x180032d85  mov     ecx, ebx; int
0x180032d87  call    ?IsRecoverableRpcError@RpcClient@NgcUtils@@SA_NJPEA_N@Z; NgcUtils::RpcClient::IsRecoverableRpcError(long,bool *)
0x180032d8c  test    al, al
0x180032d8e  jz      loc_180032E1F
0x180032d94  mov     eax, cs:dword_18006E000
0x180032d9a  cmp     eax, 4
0x180032d9d  jbe     short loc_180032DC6
0x180032d9f  mov     [rsp+98h+var_3C], ebx
0x180032da3  lea     rax, [rsp+98h+var_3C]
0x180032da8  mov     [rsp+98h+var_78], rax
0x180032dad  xor     r9d, r9d
0x180032db0  xor     r8d, r8d
0x180032db3  lea     rdx, byte_18005E4C5
0x180032dba  lea     rcx, dword_18006E000
0x180032dc1  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180032dc6  cmp     [rsp+98h+var_48], 0
0x180032dcb  jz      short loc_180032DE7
0x180032dcd  mov     rcx, [rsp+98h+arg_0]
0x180032dd5  mov     rcx, [rcx]; this
0x180032dd8  call    ?Rebind@RpcClient@NgcUtils@@QEAAJXZ; NgcUtils::RpcClient::Rebind(void)
0x180032ddd  mov     ebx, eax
0x180032ddf  mov     [rsp+98h+var_44], eax
0x180032de3  test    eax, eax
0x180032de5  js      short loc_180032E1F
0x180032de7  mov     ecx, 1F4h; dwMilliseconds
0x180032dec  call    cs:__imp_Sleep
0x180032df2  nop
0x180032df3  mov     eax, [rsp+98h+var_40]
0x180032df7  inc     eax
0x180032df9  mov     r14, [rsp+98h+arg_18]
0x180032e01  mov     r15, [rsp+98h+arg_10]
0x180032e09  mov     rdx, [rsp+98h+arg_8]
0x180032e11  mov     ecx, [rsp+98h+var_38]
0x180032e15  mov     rsi, [rsp+98h+var_30]
0x180032e1a  jmp     loc_180032CE7
0x180032e1f  test    ebx, ebx
0x180032e21  jns     short loc_180032E43
0x180032e23  mov     rcx, [rsp+98h]; this
0x180032e2b  mov     r9d, ebx; char *
0x180032e2e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180032e35  mov     edx, 14Eh; void *
0x180032e3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e3f  mov     eax, ebx
0x180032e41  jmp     short loc_180032E45
0x180032e43  xor     eax, eax
0x180032e45  add     rsp, 70h
0x180032e49  pop     r15
0x180032e4b  pop     r14
0x180032e4d  pop     rdi
0x180032e4e  pop     rsi
0x180032e4f  pop     rbx
0x180032e50  retn
0x18004a34a  push    rbp
0x18004a34c  sub     rsp, 50h
0x18004a350  mov     rbp, rdx
0x18004a353  mov     rcx, [rcx]
0x18004a356  mov     ecx, [rcx]; ExceptionCode
0x18004a358  call    cs:__imp_RpcExceptionFilter
0x18004a35e  nop
0x18004a35f  add     rsp, 50h
0x18004a363  pop     rbp
0x18004a364  retn
```
